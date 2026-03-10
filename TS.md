# TypeScript Notes — Staff Engineer Level

## PART 1: INTERFACES

---

## Q1) What is the difference between `interface` and `type` alias, and when should you use each?

Both can describe object shapes, but they have meaningful differences that matter at scale.

**`interface`:**
- Supports declaration merging — multiple declarations with the same name are merged automatically.
- Extends other interfaces with `extends` — cleaner for inheritance hierarchies.
- Error messages tend to be more readable when used as object shapes.
- Preferred for public API contracts in libraries and design systems.

**`type` alias:**
- Can describe anything: primitives, unions, intersections, tuples, mapped types, conditional types.
- Cannot be merged — a second `type Foo` declaration is an error.
- Required when you need union types, conditional types, or mapped types.
- Preferred for complex type computations and internal implementation types.

```ts
// Interface — good for object contracts
interface User {
  id: number;
  name: string;
  email: string;
}

// Extends cleanly
interface AdminUser extends User {
  permissions: string[];
}

// Type — required for unions
type Status = "idle" | "loading" | "success" | "error";

// Type — required for intersections and complex shapes
type ApiResponse<T> = { data: T; status: number } & { requestId: string };
```

**Declaration merging (interface only) — useful for augmenting third-party types:**
```ts
// Extend Express Request type in a library
interface Request {
  user?: AuthenticatedUser;
}
```

### Staff-level guidance
Pick one convention per codebase and document it. A common team standard: use `interface` for all object shapes that represent domain entities or API contracts, use `type` for everything else (unions, utilities, computed types). Consistency matters more than which you pick.

### Quick recall
- `interface`: object shapes, extendable, mergeable — prefer for public contracts.
- `type`: unions, intersections, computed types — required for complex type logic.
- Never mix randomly — define a team convention.

---

## Q2) What is structural typing and why does it matter in practice?

TypeScript uses **structural typing** (duck typing), not nominal typing. A type is compatible if its shape matches — the name does not matter.

```ts
interface Point2D { x: number; y: number; }
interface Coordinate { x: number; y: number; }

const p: Point2D = { x: 1, y: 2 };
const c: Coordinate = p; // ✅ compatible — same shape
```

This has real implications:
- Two unrelated interfaces with the same shape are assignable to each other — intentional or not.
- Extra properties are allowed when assigned via a variable, but not in object literals (excess property checking).

```ts
interface Config { url: string; }

const obj = { url: "https://api.example.com", timeout: 5000 };
const config: Config = obj; // ✅ — structural match via variable

const config2: Config = { url: "https://api.example.com", timeout: 5000 }; // ❌ excess property error
```

**Branded/nominal types** when you need stricter identity:
```ts
type UserId = string & { readonly __brand: "UserId" };
type OrderId = string & { readonly __brand: "OrderId" };

function getUser(id: UserId) { /* ... */ }

const orderId = "order-123" as OrderId;
getUser(orderId); // ❌ — catches accidental ID misuse at compile time
```

### Quick recall
- TypeScript checks shape, not name.
- Excess property checking only applies to object literals.
- Use branded types to enforce semantic identity for IDs and tokens.

---

## Q3) How do you model discriminated unions and why are they powerful?

A discriminated union is a union of types that share a common literal field (the discriminant). TypeScript narrows the type automatically based on that field.

```ts
type ApiState<T> =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: T }
  | { status: "error"; error: Error };

function renderUser(state: ApiState<User>) {
  switch (state.status) {
    case "idle":     return <Placeholder />;
    case "loading":  return <Spinner />;
    case "success":  return <UserCard user={state.data} />; // data is available here
    case "error":    return <ErrorMessage error={state.error} />;
  }
}
```

**Exhaustiveness checking** — TypeScript can verify all cases are handled:
```ts
function assertNever(x: never): never {
  throw new Error(`Unhandled case: ${JSON.stringify(x)}`);
}

// Add default case to switch:
default: return assertNever(state); // compile error if a new status is added but not handled
```

This pattern is one of the most valuable TypeScript features for building maintainable systems. Adding a new status variant causes a compile error at every unhandled switch — far better than a runtime bug.

### Quick recall
- Discriminated union = shared literal field + union.
- TypeScript narrows automatically in switch/if.
- Use `assertNever` for exhaustiveness — new variants become compile errors.

---

## PART 2: GENERICS

---

## Q4) What are generics and when should you use them?

Generics let you write code that works across types while preserving type information. Use them when the logic is the same but the type varies, and you need the type relationship preserved (input type flows to output type).

```ts
// Without generics — loses type info
function first(arr: any[]): any { return arr[0]; }

// With generics — type flows through
function first<T>(arr: T[]): T | undefined { return arr[0]; }

const name = first(["Ashish", "Rahul"]); // inferred as string | undefined
const id = first([1, 2, 3]);             // inferred as number | undefined
```

When **not** to use generics: if the type does not actually vary across usages, or if you are just using `T` as a synonym for `any`. A generic that is used only once in a signature and never constrains anything is a code smell.

### Quick recall
- Generics when: logic is same, type varies, relationship must be preserved.
- Avoid: single-use `T` that adds no constraint — that is just `any` with extra steps.

---

## Q5) What are generic constraints and how do you use them?

Constraints narrow what types a generic parameter can accept. Use `extends` to require certain shape.

```ts
// Constrain to objects with an id field
function findById<T extends { id: number }>(items: T[], id: number): T | undefined {
  return items.find(item => item.id === id);
}

findById([{ id: 1, name: "Ashish" }], 1); // ✅
findById(["string"], 1);                   // ❌ — string has no id
```

**`keyof` constraint** — ensures key exists on type:
```ts
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user = { id: 1, name: "Ashish", email: "a@b.com" };
getProperty(user, "name");   // ✅ returns string
getProperty(user, "phone");  // ❌ compile error — phone not on User
```

### Quick recall
- `extends` constrains what types are accepted.
- `K extends keyof T` is the pattern for type-safe property access.

---

## Q6) What are generic defaults and conditional types?

**Generic defaults** — provide a fallback type when none is given:
```ts
interface PaginatedResponse<T, Meta = { total: number; page: number }> {
  data: T[];
  meta: Meta;
}

type UserList = PaginatedResponse<User>; // Meta defaults to { total, page }
type CustomList = PaginatedResponse<User, { cursor: string }>; // Meta overridden
```

**Conditional types** — type-level if/else:
```ts
type IsArray<T> = T extends any[] ? true : false;

type A = IsArray<string[]>; // true
type B = IsArray<string>;   // false
```

**`infer` keyword** — extract a type from a conditional:
```ts
type UnwrapPromise<T> = T extends Promise<infer U> ? U : T;

type A = UnwrapPromise<Promise<string>>; // string
type B = UnwrapPromise<number>;          // number
```

This is how many utility types in TypeScript's standard library are built internally.

### Quick recall
- Generic defaults prevent repetitive type arguments.
- Conditional types = type-level ternary.
- `infer` extracts a type from within a conditional — used to unwrap wrappers like Promise, Array, etc.

---

## Q7) How do generics work with React components?

Generic components allow typed props that flow from usage rather than being hardcoded.

```tsx
interface SelectProps<T> {
  options: T[];
  value: T;
  onChange: (value: T) => void;
  getLabel: (option: T) => string;
}

function Select<T>({ options, value, onChange, getLabel }: SelectProps<T>) {
  return (
    <select value={getLabel(value)} onChange={e => {
      const selected = options.find(o => getLabel(o) === e.target.value);
      if (selected !== undefined) onChange(selected);
    }}>
      {options.map(o => (
        <option key={getLabel(o)} value={getLabel(o)}>{getLabel(o)}</option>
      ))}
    </select>
  );
}

// Usage — T is inferred as User
<Select
  options={users}
  value={selectedUser}
  onChange={setSelectedUser}
  getLabel={u => u.name}
/>
```

Generic components are common in design systems — a `Table<T>`, `List<T>`, or `Select<T>` that works with any data shape is far more reusable than one typed to a specific domain model.

### Quick recall
- Generic components: type flows from usage, not from component internals.
- Common in design systems: Table, List, Select, Autocomplete.
- `function Component<T>` syntax — arrow functions need `<T,>` to avoid JSX ambiguity.

---

## PART 3: UTILITY TYPES

---

## Q8) What are the most important built-in utility types?

### Partial, Required, Readonly
```ts
interface User { id: number; name: string; email: string; }

type PartialUser = Partial<User>;   // all fields optional
type RequiredUser = Required<User>; // all fields required
type ReadonlyUser = Readonly<User>; // all fields readonly
```

**Real use case:** `Partial<T>` is essential for update/patch operations where only some fields change.

```ts
async function updateUser(id: number, patch: Partial<Omit<User, "id">>) {
  // Only the provided fields are updated
}
```

### Pick and Omit
```ts
type UserPreview = Pick<User, "id" | "name">;       // keep only these fields
type UserWithoutId = Omit<User, "id">;              // remove id field
```

**Real use case:** `Omit` is the standard pattern for "create" payloads (strip `id` before sending to API).

### Record
```ts
type StatusMap = Record<string, ApiState<User>>;
type PermissionMap = Record<UserId, Permission[]>;
```

**Real use case:** typed dictionaries and lookup maps.

### Extract and Exclude
```ts
type Status = "idle" | "loading" | "success" | "error";

type ActiveStatus = Extract<Status, "loading" | "success">;   // "loading" | "success"
type DoneStatus = Exclude<Status, "idle" | "loading">;        // "success" | "error"
```

### ReturnType, Parameters, Awaited
```ts
async function fetchUser(id: number): Promise<User> { /* ... */ }

type FetchUserReturn = Awaited<ReturnType<typeof fetchUser>>; // User
type FetchUserParams = Parameters<typeof fetchUser>;          // [number]
```

**Real use case:** derive types from existing functions rather than duplicating them — keeps types in sync automatically.

### Quick recall
- `Partial` for patches/updates. `Omit` for create payloads.
- `Pick` for projections. `Record` for typed maps.
- `Extract`/`Exclude` for filtering unions.
- `ReturnType` + `Awaited` to derive types from functions — avoids duplication.

---

## Q9) How do you build custom utility types?

Understanding how to compose utility types is a Staff-level differentiator. Most custom utilities combine mapped types, conditional types, and `keyof`/`infer`.

**DeepPartial — recursively make all nested fields optional:**
```ts
type DeepPartial<T> = T extends object
  ? { [K in keyof T]?: DeepPartial<T[K]> }
  : T;
```

**NonNullableFields — strip null/undefined from all fields:**
```ts
type NonNullableFields<T> = {
  [K in keyof T]: NonNullable<T[K]>;
};
```

**PickByValue — pick fields matching a value type:**
```ts
type PickByValue<T, V> = {
  [K in keyof T as T[K] extends V ? K : never]: T[K];
};

interface Form {
  name: string;
  age: number;
  active: boolean;
}

type StringFields = PickByValue<Form, string>; // { name: string }
```

**Flatten a union of objects:**
```ts
type Flatten<T> = T extends any[] ? T[number] : T;

type A = Flatten<string[]>; // string
type B = Flatten<string>;   // string
```

### Quick recall
- Custom utilities = mapped types + conditional types + `keyof`/`infer`.
- `DeepPartial`, `PickByValue`, `NonNullableFields` are common interview questions.
- Being able to read and write these shows genuine TypeScript depth.

---

## Q10) What are mapped types and template literal types?

**Mapped types** — transform every key in a type:
```ts
type Getters<T> = {
  [K in keyof T as `get${Capitalize<string & K>}`]: () => T[K];
};

interface User { id: number; name: string; }

type UserGetters = Getters<User>;
// { getId: () => number; getName: () => string; }
```

**Template literal types** — string manipulation at type level:
```ts
type EventName<T extends string> = `on${Capitalize<T>}`;

type ClickEvent = EventName<"click">; // "onClick"
type ChangeEvent = EventName<"change">; // "onChange"

// Practical: type-safe event handler map
type HandlerMap = {
  [K in "click" | "focus" | "blur" as EventName<K>]: (e: Event) => void;
};
// { onClick: ...; onFocus: ...; onBlur: ...; }
```

These features are powerful for building type-safe APIs in design systems and libraries — generating handler prop names, CSS variable maps, i18n key shapes, and more.

### Quick recall
- Mapped types transform every key — combine with `as` for key remapping.
- Template literal types do string manipulation at type level.
- Used in design system and library APIs to generate type-safe prop names automatically.

---

## Q11) How should TypeScript be used at Staff level across an org?

TypeScript discipline is a platform concern at Staff level, not just a personal practice.

**Strict mode non-negotiable:** `"strict": true` in `tsconfig.json` is the baseline. This enables `strictNullChecks`, `noImplicitAny`, `strictFunctionTypes`, and others. New projects should never start without it. Migrating existing projects: use `// @ts-strict-ignore` directives as temporary scaffolding, track and reduce count over time.

**Shared type packages:** For monorepos or microfrontend architectures, domain types (User, Order, Permission, ApiResponse) should live in a shared package imported by all apps. Prevents type drift where frontend and backend diverge silently.

**API contract types from source of truth:** Generate TypeScript types from OpenAPI specs (`openapi-typescript`), GraphQL schemas (`graphql-code-generator`), or Zod schemas (`z.infer<typeof schema>`). Never hand-write types that mirror a backend contract — they will drift.

**`satisfies` operator (TS 4.9+):** Validates that a value matches a type without widening it.
```ts
const config = {
  endpoints: { users: "/api/users", orders: "/api/orders" }
} satisfies Record<string, { [key: string]: string }>;

// config.endpoints.users is still typed as string literal "/api/users"
// not widened to string
```

### Quick recall
- `strict: true` is non-negotiable. No exceptions for new code.
- Generate types from API specs — never hand-write backend contracts.
- Shared type packages for monorepos/microfrontends.
- `satisfies` for validation without type widening.