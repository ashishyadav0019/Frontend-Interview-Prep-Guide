# System Design Catalog

- Total items: **35**

## Table of Contents

- [1. Introduction](#1-introduction)
- [2. Requirements](#2-requirements)
- [3. Architecture](#3-architecture)
- [4. Data Model](#4-data-model)
- [5. Interface Communication](#5-interface-communication)
- [6. API Design](#6-api-design)
- [7. Optimizations](#7-optimizations)
- [8. Design Auto Complete Search](#8-design-auto-complete-search)
- [9. Design Chat App](#9-design-chat-app)
- [10. Design Google Calendar](#10-design-google-calendar)
- [11. Design Sprint Board](#11-design-sprint-board)
- [12. Design Facebook Newsfeed](#12-design-facebook-newsfeed)
- [13. Design Pintrest](#13-design-pintrest)
- [14. Rich Text Editor](#14-rich-text-editor)
- [15. Design mentions](#15-design-mentions)
- [16. Build ChatGPT (Frontend)](#16-build-chatgpt-frontend)
- [17. Design Airbnb](#17-design-airbnb)
- [18. (Bonus) General System Design Fundamentals](#18-bonus-general-system-design-fundamentals)
- [19. SSR vs CSR](#19-ssr-vs-csr)
- [20. Security](#20-security)
- [21. XSS vs CORS](#21-xss-vs-cors)
- [22. Image Caching Strategies](#22-image-caching-strategies)
- [23. Broadcast Channels](#23-broadcast-channels)
- [24. IndexedDB](#24-indexeddb)
- [25. Core Web Vitals](#25-core-web-vitals)
- [26. Web Accessibility](#26-web-accessibility)
- [27. ARIA roles](#27-aria-roles)
- [28. Network Requests](#28-network-requests)
- [29. Web Protocols Cheat Sheet](#29-web-protocols-cheat-sheet)
- [30. Image Optimizations Strategies](#30-image-optimizations-strategies)
- [31. Apollo Cache](#31-apollo-cache)
- [32. Normalization](#32-normalization)
- [33. Design E-Commerce Platform](#33-design-e-commerce-platform)
- [34. Design Netflix](#34-design-netflix)
- [35. Design A Scalable Frontend Architecture](#35-design-a-scalable-frontend-architecture)

---

## 1. Introduction

- Difficulty: 🟠 Medium
- Subtitle: Master frontend system design interviews with this comprehensive guide series.
- Video Link: https://www.youtube.com/watch?v=NEzu4FD25KM
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-28.png

### Content

<h1>Frontend System Design Interview Handbook &#8211; 2025</h1>
<p><iframe loading="lazy" title="YouTube video player" src="https://www.youtube.com/embed/NEzu4FD25KM?si=T_73LkGb9u7hqXju" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen"></iframe></p>
<hr />
<p>Welcome to the <strong>Frontend System Design Handbook</strong>.</p>
<p>This frontend system design playbook explains exactly what a frontend system design interview is, why companies use them, and how to ace yours.</p>
<p>You’ll learn how frontend interviews differ from backend interviews, what interviewers care about, how you’ll be graded, and a simple framework (<strong>RADIO</strong>) to structure your responses.</p>
<p>This <strong>Frontend System Design Handbook</strong> provides a concise overview of the topics we’ll cover in this series, including real-world interview questions and key frontend concepts. The handbook will cover both fundamental and advanced topics in frontend system design.</p>
<h2>What to Expect</h2>
<p>In this first article, we’ll cover:</p>
<ul>
<li>What is a Frontend System Design Interview?</li>
<li>How Frontend Interviews Differ from Backend Interviews</li>
<li>What Interviewers Look For</li>
<li>How You’ll Be Graded</li>
<li>How to Approach the Interview Strategically</li>
<li>Introducing the RADIO Framework</li>
<li>Topics Covered in This Series
<ul>
<li>Core Framework (RADIO)</li>
<li>Real-World Design Questions</li>
<li>Frontend Fundamentals &amp; Deep Dives</li>
<li>General System Design Fundamentals (Bonus)</li>
</ul>
</li>
<li>Preparation Material Required</li>
</ul>
<hr />
<h2>What Is a Frontend System Design Interview?</h2>
<p>Frontend system design interviews test your ability to architect large, scalable UI systems, not just individual components, but entire frontend architectures.</p>
<p>Based on your architectural decisions, companies use these interviews to see whether you’re at a junior, mid-level, or senior level.</p>
<p>Interviewers want to see if you can design frontends that scale across:</p>
<ul>
<li>User</li>
<li>Teams</li>
<li>Feature complexity</li>
</ul>
<p>Instead of just building buttons or styling pages, you’ll discuss state management, data flow, routing, performance, and UX at scale. Effective application state management is crucial in handling data flow and state within complex, component-based applications, often utilizing architectural patterns and libraries like Flux and Redux.</p>
<hr />
<h2>Frontend vs Backend System Design Interviews</h2>
<p>If you’ve done system design interviews before, they probably focused on <a href="https://frontendlead.com/system-design/general-system-design-funamentals">backend</a> systems: databases, distributed architecture, and API design. Frontend interviews have similarities, but their emphasis is different.</p>
<p>Here’s a comparison:</p>
<table>
<tbody>
<tr>
<th>Aspect</th>
<th>Backend</th>
<th>Frontend</th>
<th>Applies to Both?</th>
</tr>
<tr>
<td colspan="1" rowspan="1">Main Focus</td>
<td colspan="1" rowspan="1">Scalable distributed systems</td>
<td colspan="1" rowspan="1">Scalable UI architectures</td>
<td colspan="1" rowspan="1">✅</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Scale Discussion</td>
<td colspan="1" rowspan="1">Servers, databases, traffic</td>
<td colspan="1" rowspan="1">Components, app structure, and users</td>
<td colspan="1" rowspan="1">✅</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Typical Concepts</td>
<td colspan="1" rowspan="1">Sharding, load balancing, and rate limiting</td>
<td colspan="1" rowspan="1">State management, routing, and lazy loading</td>
<td colspan="1" rowspan="1">⚠️ <em>(Different techniques)</em></td>
</tr>
<tr>
<td colspan="1" rowspan="1">Data Handling</td>
<td colspan="1" rowspan="1">Table schemas, replication, and indexing</td>
<td colspan="1" rowspan="1">Client-side stores, caching, and fetching</td>
<td colspan="1" rowspan="1">✅</td>
</tr>
<tr>
<td colspan="1" rowspan="1">API Design</td>
<td colspan="1" rowspan="1">REST, gRPC, GraphQL, versioning</td>
<td colspan="1" rowspan="1">Knowing what APIs to call and how to consume them</td>
<td colspan="1" rowspan="1">✅</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Protocol Decisions</td>
<td colspan="1" rowspan="1">HTTP, gRPC, WebSockets</td>
<td colspan="1" rowspan="1">HTTP, WebSockets, SSE</td>
<td colspan="1" rowspan="1">✅</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Performance</td>
<td colspan="1" rowspan="1">Latency, throughput, uptime</td>
<td colspan="1" rowspan="1">Bundle size, TTI, re-renders</td>
<td colspan="1" rowspan="1">✅</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Protocol Performance Differences</td>
<td colspan="1" rowspan="1">HTTP/1.1, HTTP/2, HTTP/3</td>
<td colspan="1" rowspan="1">HTTP/1.1, HTTP/2, HTTP/3</td>
<td colspan="1" rowspan="1">✅ <em>(Different impact on web application performance)</em></td>
</tr>
<tr>
<td colspan="1" rowspan="1">Interview Goal</td>
<td colspan="1" rowspan="1">Design and scale backend systems</td>
<td colspan="1" rowspan="1">Design and scale front-end systems</td>
<td colspan="1" rowspan="1">❌ <em>(Different focus)</em></td>
</tr>
</tbody>
</table>
<hr />
<h2>What Interviewers Look For</h2>
<p>Interviewers want clarity, structure, and transparent decision-making. They’re grading you on:</p>
<ul>
<li>How do you clarify the scope and requirements</li>
<li>Choices in state management and architecture, including how components or micro frontends are responsible for specific features or aspects of an application</li>
<li>How you handle performance, UX, and scalability trade-offs</li>
<li>Your understanding of modern frontend concepts (SSR vs CSR, caching strategies, etc.)</li>
</ul>
<p>The difference between junior and senior answers:</p>
<table>
<colgroup>
<col />
<col /></colgroup>
<tbody>
<tr>
<th colspan="1" rowspan="1">Junior Answers</th>
<th colspan="1" rowspan="1">Senior Answers</th>
</tr>
<tr>
<td colspan="1" rowspan="1">Only mention familiar tech</td>
<td colspan="1" rowspan="1">Discuss trade-offs between tech choices</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Focus solely on UI details</td>
<td colspan="1" rowspan="1">Address architecture, scalability, and maintainability</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Skip clarifying questions</td>
<td colspan="1" rowspan="1">Clarify requirements, scope, and edge cases early</td>
</tr>
</tbody>
</table>
<h2></h2>
<hr />
<h2>How You’ll Be Graded</h2>
<p>Interviewers typically grade frontend system design interviews across five main categories:</p>
<table>
<colgroup>
<col />
<col />
<col /></colgroup>
<tbody>
<tr>
<th colspan="1" rowspan="1">Category</th>
<th colspan="1" rowspan="1">Description</th>
<th colspan="1" rowspan="1">Example</th>
</tr>
<tr>
<td colspan="1" rowspan="1"><strong>Scope &amp; Requirements</strong></td>
<td colspan="1" rowspan="1">Did you clearly understand and clarify the problem?</td>
<td colspan="1" rowspan="1">Asked clarifying questions about the user base and platforms</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><strong>Architecture &amp; State Management</strong></td>
<td colspan="1" rowspan="1">Did you choose an appropriate architecture?</td>
<td colspan="1" rowspan="1">Explained clearly why you chose React Context vs. Redux</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><strong>Data Handling &amp; API Design</strong></td>
<td colspan="1" rowspan="1">How well did you plan your data flow and API interactions?</td>
<td colspan="1" rowspan="1">Clearly outlined caching strategies and API data structures</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><strong>Performance &amp; Optimization</strong></td>
<td colspan="1" rowspan="1">Did you address performance, accessibility, and production readiness?</td>
<td colspan="1" rowspan="1">Mentioned lazy loading, Core Web Vitals, and accessibility</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><strong>Communication &amp; Trade-offs</strong></td>
<td colspan="1" rowspan="1">Could you clearly explain your reasoning and handle trade-offs effectively?</td>
<td colspan="1" rowspan="1">Clearly stated why SSR was chosen for SEO despite the complexity.</td>
</tr>
</tbody>
</table>
<p>Your goal isn’t just to come up with the “right” answer but to demonstrate your thought process and rationale behind each choice. Interviewers will look for key points in your responses, such as clarity, structure, and decision-making.</p>
<hr />
<h2>How to Approach the Interview Strategically</h2>
<p><strong>Clarify the Scope First</strong></p>
<p>Always start by clarifying:</p>
<ul>
<li>User requirements</li>
<li>Platforms and devices</li>
<li>Need for offline support</li>
<li>Real-time requirements</li>
</ul>
<p><strong>Manage Your Time Wisely</strong></p>
<p>Aim to split your interview time like this:</p>
<ul>
<li><strong>20%</strong> Clarifying requirements</li>
<li><strong>30%</strong> High-level architecture</li>
<li><strong>30%</strong> Deep dives into key decisions</li>
<li><strong>20%</strong> Trade-offs and wrap-up</li>
</ul>
<p><strong>Communicate Trade-Offs</strong></p>
<p>Interviewers expect clear reasoning behind your choices:</p>
<blockquote><p>“I chose React Query over Redux because it simplifies data fetching and reduces unnecessary re-renders. The trade-off is slightly less centralized state management, but it fits this app’s use case.”</p></blockquote>
<p>When discussing high-level architecture, emphasize how developers utilize component-based and modular architectures to develop modular, reusable, and optimized software for complex applications. This approach ensures that the software can handle complex requirements efficiently and is easier to maintain and extend.</p>
<hr />
<h2>Introducing the RADIO Framework</h2>
<p>RADIO provides a clear, straightforward way to handle front-end system design interviews. Yangshun Tay is credited with making it popular. It covers Requirements, Architecture, Dataflow, Interface, and Optimizations. This isn’t about memorizing steps or processes. Instead, RADIO helps you organize your thoughts, break down complex problems, and communicate your solutions.</p>
<table>
<colgroup>
<col />
<col />
<col /></colgroup>
<tbody>
<tr>
<th colspan="1" rowspan="1">Letter</th>
<th colspan="1" rowspan="1">Meaning</th>
<th colspan="1" rowspan="1">What it Covers</th>
</tr>
<tr>
<td colspan="1" rowspan="1">R</td>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/defining-frontend-requirements-system-design" target="_blank" rel="noopener noreferrer">Requirements</a></td>
<td colspan="1" rowspan="1">Clarify the scope and ask questions</td>
</tr>
<tr>
<td colspan="1" rowspan="1">A</td>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/mastering-frontend-architecture-design-insights" target="_blank" rel="noopener noreferrer">Architecture</a></td>
<td colspan="1" rowspan="1">Component structure, state, and routing</td>
</tr>
<tr>
<td colspan="1" rowspan="1">D</td>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/client-only-data-management-frontend-design" target="_blank" rel="noopener noreferrer">Dataflow</a></td>
<td colspan="1" rowspan="1">How data moves, storage, and caching, including unidirectional data flow, which simplifies application state management by enforcing a single direction of data flow</td>
</tr>
<tr>
<td colspan="1" rowspan="1">I</td>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/api-design-best-practices" target="_blank" rel="noopener noreferrer">Interface</a></td>
<td colspan="1" rowspan="1">UX, interactions, edge cases</td>
</tr>
<tr>
<td colspan="1" rowspan="1">O</td>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/performace-frontend-system-design">Optimizations</a></td>
<td colspan="1" rowspan="1">Performance, accessibility, and production-readiness</td>
</tr>
</tbody>
</table>
<p>It’s a practical roadmap, not a strict rulebook, to keep your response clear and focused.</p>
<hr />
<h2>Frontend System Design Handbook Topics</h2>
<p>Here’s what’s coming up in this series:</p>
<p>Understanding how large systems are built can benefit early engineers as part of their advanced learning journey.</p>
<hr />
<h3>Core Framework (RADIO) In Depth</h3>
<ul>
<li><a href="https://frontendlead.com/system-design/defining-frontend-requirements-system-design" target="_blank" rel="noopener noreferrer">Requirements</a> gathering and scope definition</li>
<li><a href="https://frontendlead.com/system-design/mastering-frontend-architecture-design-insights" target="_blank" rel="noopener noreferrer">Architecture</a>, components, state, and routing</li>
<li><a href="https://frontendlead.com/system-design/client-only-data-management-frontend-design" target="_blank" rel="noopener noreferrer">Data</a> modeling, stores, and caching strategies</li>
<li><a href="https://frontendlead.com/system-design/understanding-communication-http-rest-graphql-sse" target="_blank" rel="noopener noreferrer">Interface</a> communication and interactions</li>
<li><a href="https://frontendlead.com/system-design/api-design-best-practices" target="_blank" rel="noopener noreferrer">API</a> consumption and optimization</li>
<li><span style="box-sizing: border-box; margin: 0px; padding: 0px;"><a href="https://frontendlead.com/system-design/performace-frontend-system-design" target="_blank" rel="noopener">Optimizations:</a> How do you make the frontend more performant?</span></li>
</ul>
<hr />
<h3>Real-World Design Questions</h3>
<p>After covering the fundamentals, we’ll walk through realistic frontend design scenarios you might see in actual interviews. These include building a Facebook-style newsfeed, real-time chat apps, rich text editors, Pinterest-like layouts, Google Calendar, and Jira-style boards. Practicing these real-world examples will give you confidence in tackling your interviews.</p>
<table>
<colgroup>
<col />
<col /></colgroup>
<tbody>
<tr>
<th colspan="1" rowspan="1">Topic</th>
<th colspan="1" rowspan="1">Description</th>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/design-facebook-newsfeed" target="_blank" rel="noopener noreferrer"><strong>Building Facebook</strong></a></td>
<td colspan="1" rowspan="1">How to design a scalable, real-time social feed with notifications, posts, and likes.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/rich-text-editor" target="_blank" rel="noopener noreferrer"><strong>Building a Rich Text Editor.</strong></a></td>
<td colspan="1" rowspan="1">How to design a lightweight, fast editor that supports formatting, undo/redo, and embedded content.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/design-mentions-and-hashtags" target="_blank" rel="noopener noreferrer"><strong>Building @mentions</strong></a></td>
<td colspan="1" rowspan="1">How to design mention tagging across large user bases with real-time suggestions and selection.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/chat-application-frontend-system-design" target="_blank" rel="noopener noreferrer"><strong>Building a Chat Application</strong></a></td>
<td colspan="1" rowspan="1">How to design a responsive, real-time messaging interface with delivery and read receipts. Flux architecture can help manage application state and data flow in complex component-based apps, ensuring scalability and frequent updates.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/design-pintrest" target="_blank" rel="noopener noreferrer"><strong>Designing Pinterest</strong></a></td>
<td colspan="1" rowspan="1">How to design a dynamic, scrollable grid layout with personalized content and pinning features.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/design-google-calendar-frontend-system-design" target="_blank" rel="noopener noreferrer"><strong>Designing Google Calendar</strong></a></td>
<td colspan="1" rowspan="1">How to design a calendar UI with drag-and-drop, recurring events, and real-time sync.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/frontend-autocomplete-system-design-guide" target="_blank" rel="noopener noreferrer"><strong>Designing Auto Complete Search</strong></a></td>
<td colspan="1" rowspan="1">Design a fast, responsive input that suggests ranked search results as you type.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/design-sprint-board-frontend-system-design" target="_blank" rel="noopener noreferrer"><strong>Designing a Jira-like Sprint Board</strong></a></td>
<td colspan="1" rowspan="1">How to design a drag-and-drop task board with swimlanes, backlog, and real-time collaboration.</td>
</tr>
</tbody>
</table>
<hr />
<h3>Frontend Fundamentals &amp; Deep Dives</h3>
<p>This section goes deeper into specific frontend topics you’ll need to know well. We’ll discuss server-side vs client-side rendering, browser security issues like XSS and CORS, caching with IndexedDB and Apollo, optimizing images, Core Web Vitals, accessibility best practices, network request patterns, web protocols, and data normalization. These deep dives will help solidify your understanding so you can apply these concepts in your interviews.</p>
<table>
<colgroup>
<col />
<col /></colgroup>
<tbody>
<tr>
<th colspan="1" rowspan="1">Topic</th>
<th colspan="1" rowspan="1">Description</th>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/server-side-rendering-vs-client-side-rendering-guide" target="_blank" rel="noopener noreferrer"><strong>Server-Side vs Client-Side Rendering</strong></a></td>
<td colspan="1" rowspan="1">When and why to use SSR or CSR depends on your use case.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/frontend-security-best-practices-for-web-applications" target="_blank" rel="noopener noreferrer"><strong>Front-End Security (XSS vs CORS)</strong></a></td>
<td colspan="1" rowspan="1">Understand and mitigate common security issues in the browser.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/image-caching-strategies-for-web-performance" target="_blank" rel="noopener noreferrer"><strong>Image Caching Strategies</strong></a></td>
<td colspan="1" rowspan="1">Techniques for optimizing and caching images for performance.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/broadcast-channels-in-web" target="_blank" rel="noopener noreferrer"><strong>Broadcast Signals</strong></a></td>
<td colspan="1" rowspan="1">Share state or events across tabs or isolated parts of the app.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/mastering-indexed-db-client-side-storage-guide" target="_blank" rel="noopener noreferrer"><strong>IndexedDB and Caching</strong></a></td>
<td colspan="1" rowspan="1">Use local storage for offline-first experiences and faster loads. Popular libraries like Redux and Vuex facilitate the implementation of component-based architectures and manage application state through standardized approaches.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/core-web-vitals" target="_blank" rel="noopener noreferrer"><strong>Core Web Vitals</strong></a></td>
<td colspan="1" rowspan="1">Metrics like LCP, FID, and CLS to measure frontend performance.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/web-accessibility" target="_blank" rel="noopener noreferrer"><strong>Web Accessibility (ARIA roles)</strong></a></td>
<td colspan="1" rowspan="1">Implement accessible components for screen readers and keyboard users.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/data-fetching-strategies-web-performance-guide" target="_blank" rel="noopener noreferrer"><strong>Network Requests</strong></a></td>
<td colspan="1" rowspan="1">Optimize fetch patterns, retries, and background updates.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/apollo-cache" target="_blank" rel="noopener noreferrer"><strong>Apollo Caching</strong></a></td>
<td colspan="1" rowspan="1">Manage and cache GraphQL responses on the client side.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/web-image-optimizations-guide" target="_blank" rel="noopener noreferrer"><strong>Image Optimization Strategies</strong></a></td>
<td colspan="1" rowspan="1">Serve correctly sized and formatted images for different devices.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/web-protocols-cheat-sheet" target="_blank" rel="noopener noreferrer"><strong>Web Protocols Cheat Sheet</strong></a></td>
<td colspan="1" rowspan="1">Quick guide to HTTP, WebSockets, SSE, and more.</td>
</tr>
<tr>
<td colspan="1" rowspan="1"><a href="https://frontendlead.com/system-design/normalized-vs-non-normalized-caching-explained" target="_blank" rel="noopener noreferrer"><strong>Data Normalization</strong></a></td>
<td colspan="1" rowspan="1">Structure frontend state to be efficient, predictable, and scalable.</td>
</tr>
</tbody>
</table>
<hr />
<h3>Bonus: General System Design Fundamentals</h3>
<p>We’ll also discuss <a href="https://frontendlead.com/system-design/general-system-design-fundamentals">general system design</a> topics, such as rate limiting, load balancing, and high-level scalability principles. You might be asking why, if this is a front-end system design guide. There are times when you may be participating in a full-stack interview, and the interviewer may ask questions about full-stack concepts, so it’s beneficial to have a high-level overview to be prepared.</p>
<p>Here is a high-level overview of general system design fundamentals we will cover:</p>
<table>
<colgroup>
<col />
<col /></colgroup>
<tbody>
<tr>
<th colspan="1" rowspan="1">Topic</th>
<th colspan="1" rowspan="1">Description</th>
</tr>
<tr>
<td colspan="1" rowspan="1">General System Design Fundamentals</td>
<td colspan="1" rowspan="1">Key backend concepts you’ll need for full-stack interviews.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">R.A.I.L.S Framework</td>
<td colspan="1" rowspan="1">A structured approach: Requirements, Architecture, Interfaces, Latency/Load, Storage/Scaling.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Requirements &amp; Scope</td>
<td colspan="1" rowspan="1">Defining system goals, constraints, and clarifying questions.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Architecture</td>
<td colspan="1" rowspan="1">High-level system components and their communication mechanisms.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Data Flow</td>
<td colspan="1" rowspan="1">Clearly defining how data moves through system services.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Interfaces</td>
<td colspan="1" rowspan="1">Designing public APIs and internal service communication.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Latency, Load, and Limits</td>
<td colspan="1" rowspan="1">Estimating traffic, performance expectations, and bottlenecks.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Storage and Scaling</td>
<td colspan="1" rowspan="1">Database selection, schemas, indexing, sharding, and caching.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Core System Design Concepts</td>
<td colspan="1" rowspan="1">Essential principles like API design, authentication, authorization, hashing, data modeling, and indexing.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Databases</td>
<td colspan="1" rowspan="1">Database types, transactions, schema design, and consistency models.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Caching</td>
<td colspan="1" rowspan="1">Layers (CDN, Redis), invalidation strategies, and eviction policies.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Asynchronous Processing</td>
<td colspan="1" rowspan="1">Message queues, async job patterns, and retry mechanisms.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Load Balancing &amp; Scalability</td>
<td colspan="1" rowspan="1">Load balancers, scaling algorithms, and session management.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Rate Limiting &amp; Throttling</td>
<td colspan="1" rowspan="1">Implementing per-user or endpoint limits using token buckets, Redis.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Fault Tolerance &amp; Reliability</td>
<td colspan="1" rowspan="1">Retry strategies, circuit breakers, and graceful degradation.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Observability</td>
<td colspan="1" rowspan="1">Monitoring, structured logging, tracing, and health checks.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Infrastructure &amp; Deployment</td>
<td colspan="1" rowspan="1">Containerization, orchestration (Kubernetes), CI/CD pipelines. Developers can split code into manageable modules to develop, test, and deploy them independently, enhancing maintainability and reducing conflicts during collaborative development.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Security</td>
<td colspan="1" rowspan="1">Transport security, data encryption, and application security.</td>
</tr>
<tr>
<td colspan="1" rowspan="1">Practice System Design Scenarios</td>
<td colspan="1" rowspan="1">Real-world design examples like chat apps, notification systems, and feeds.</td>
</tr>
</tbody>
</table>
<hr />
<h2>Preparation Material</h2>
<p>This series assumes you’re familiar with frontend basics.</p>
<p>If needed, brush up on:</p>
<ul>
<li>State management (Redux, Context, Zustand)</li>
<li>React best practices (Hooks, lazy loading)</li>
<li>API design principles (REST, GraphQL)</li>
<li>Web performance fundamentals</li>
</ul>
<p>Effective resource management is crucial in application development to optimize performance and ensure scalability. This handbook will guide you through each of these steps.</p>
<p>Projects like building smaller-scale versions of apps like Instagram, Slack, or Google Docs can also build intuition and confidence.</p>
<p>With that, you’re ready to start.</p>
<hr />
<p>Next, we’ll move on to <strong>“Requirements” (the R in RADIO)</strong>, and I’ll show you exactly how to prepare for success from the start.</p>


---

## 2. Requirements

- Difficulty: 🟠 Medium
- Subtitle: Foundation of robust frontend design: Defining essential system requirements.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40.png

### Content

<h1>R &#8211; Requirements: Laying the Foundation</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1694" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40.png" alt="Frontend System Design Requirements" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-40-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<hr />
<p class="" data-start="204" data-end="472">In the Requirements phase, your main goal is to clarify precisely what you&#8217;re building. Spend no more than <strong data-start="309" data-end="322">5 minutes</strong> here. Quickly define functional requirements and non-functional requirements, and do some basic napkin math to understand the scale you&#8217;re dealing with.</p>
<blockquote>
<p data-start="204" data-end="472"><em><strong>Please spend no more than 10% of your interview explaining this portion.</strong></em></p>
</blockquote>
<p class="" data-start="474" data-end="612">Remember, your interviewer may not explicitly state all the requirements. Ask clarifying questions and structure your thinking.</p>
<hr />
<h3 class="" data-start="614" data-end="657">Step 1: Clarify Functional Requirements</h3>
<p class="" data-start="659" data-end="757">Divide your requirements clearly into <strong data-start="697" data-end="710">Must-have</strong> (core) features and <strong data-start="731" data-end="747">Nice-to-have</strong> features:</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="759" data-end="1586">
<thead data-start="759" data-end="827">
<tr data-start="759" data-end="827">
<th data-start="759" data-end="781" data-col-size="sm">Type</th>
<th data-start="781" data-end="827" data-col-size="md">Example</th>
</tr>
</thead>
<tbody data-start="897" data-end="1586">
<tr data-start="897" data-end="965">
<td data-start="897" data-end="919" data-col-size="sm"><strong data-start="899" data-end="912">Must-have</strong></td>
<td data-col-size="md" data-start="919" data-end="965">Infinite scrolling feed</td>
</tr>
<tr data-start="966" data-end="1034">
<td data-start="966" data-end="988" data-col-size="sm"></td>
<td data-start="988" data-end="1034" data-col-size="md">Users can react (like, heart, etc.)</td>
</tr>
<tr data-start="1035" data-end="1103">
<td data-start="1035" data-end="1057" data-col-size="sm"></td>
<td data-start="1057" data-end="1103" data-col-size="md">Posts support images, videos, and text content.</td>
</tr>
<tr data-start="1104" data-end="1172">
<td data-start="1104" data-end="1126" data-col-size="sm"></td>
<td data-col-size="md" data-start="1126" data-end="1172">Users can create, edit, and delete posts.</td>
</tr>
<tr data-start="1173" data-end="1241">
<td data-start="1173" data-end="1195" data-col-size="sm"></td>
<td data-start="1195" data-end="1241" data-col-size="md">Basic user profiles (name, avatar, etc.)</td>
</tr>
<tr data-start="1242" data-end="1310">
<td data-start="1242" data-end="1264" data-col-size="sm"><strong data-start="1244" data-end="1260">Nice-to-have</strong></td>
<td data-col-size="md" data-start="1264" data-end="1310">Internationalization (multi-language)</td>
</tr>
<tr data-start="1311" data-end="1379">
<td data-start="1311" data-end="1333" data-col-size="sm"></td>
<td data-start="1333" data-end="1379" data-col-size="md">Detailed analytics &amp; tracking</td>
</tr>
<tr data-start="1380" data-end="1448">
<td data-start="1380" data-end="1402" data-col-size="sm"></td>
<td data-start="1402" data-end="1448" data-col-size="md">Advanced privacy controls</td>
</tr>
<tr data-start="1449" data-end="1517">
<td data-start="1449" data-end="1471" data-col-size="sm"></td>
<td data-col-size="md" data-start="1471" data-end="1517">Search functionality</td>
</tr>
<tr data-start="1518" data-end="1586">
<td data-start="1518" data-end="1540" data-col-size="sm"></td>
<td data-col-size="md" data-start="1540" data-end="1586">Accessibility support</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<hr />
<h3 class="" data-start="1588" data-end="1635">Step 2: Clarify Non-Functional Requirements</h3>
<p class="" data-start="1637" data-end="1740">Non-functional requirements cover what&#8217;s happening under the hood (performance, scalability, UX, etc.):</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="1742" data-end="2441">
<thead data-start="1742" data-end="1811">
<tr data-start="1742" data-end="1811">
<th data-start="1742" data-end="1765" data-col-size="sm">Area</th>
<th data-start="1765" data-end="1811" data-col-size="md">Example Considerations</th>
</tr>
</thead>
<tbody data-start="1882" data-end="2441">
<tr data-start="1882" data-end="1951">
<td data-start="1882" data-end="1905" data-col-size="sm"><strong data-start="1884" data-end="1899">Performance</strong></td>
<td data-col-size="md" data-start="1905" data-end="1951">Fast load times (under 500ms per load)</td>
</tr>
<tr data-start="1952" data-end="2021">
<td data-start="1952" data-end="1975" data-col-size="sm"><strong data-start="1954" data-end="1972">Mobile Support</strong></td>
<td data-start="1975" data-end="2021" data-col-size="md">Mobile-first design, responsive layouts</td>
</tr>
<tr data-start="2022" data-end="2091">
<td data-start="2022" data-end="2045" data-col-size="sm"><strong data-start="2024" data-end="2042">Offline Access</strong></td>
<td data-start="2045" data-end="2091" data-col-size="md">Cache recent posts, support offline reads</td>
</tr>
<tr data-start="2092" data-end="2161">
<td data-start="2092" data-end="2115" data-col-size="sm"><strong data-start="2094" data-end="2111">Accessibility</strong></td>
<td data-col-size="md" data-start="2115" data-end="2161">Keyboard navigation, screen-reader support</td>
</tr>
<tr data-start="2162" data-end="2231">
<td data-start="2162" data-end="2185" data-col-size="sm"><strong data-start="2164" data-end="2176">Security</strong></td>
<td data-col-size="md" data-start="2185" data-end="2231">Secure authentication, XSS prevention</td>
</tr>
<tr data-start="2232" data-end="2301">
<td data-start="2232" data-end="2255" data-col-size="sm"><strong data-start="2234" data-end="2249">Scalability</strong></td>
<td data-start="2255" data-end="2301" data-col-size="md">The system must scale to millions of users</td>
</tr>
<tr data-start="2302" data-end="2371">
<td data-start="2302" data-end="2325" data-col-size="sm"><strong data-start="2304" data-end="2321">Observability</strong></td>
<td data-col-size="md" data-start="2325" data-end="2371">Error logging, monitoring performance</td>
</tr>
<tr data-start="2372" data-end="2441">
<td data-start="2372" data-end="2395" data-col-size="sm"><strong data-start="2374" data-end="2394">Data Consistency</strong></td>
<td data-col-size="md" data-start="2395" data-end="2441">Real-time updates vs eventual consistency</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<hr />
<h3 class="" data-start="2443" data-end="2485">Step 3: Napkin Math (Scale Estimation &#8211; Optional)</h3>
<p class="" data-start="2487" data-end="2540">Do this very fast; this example below is a detailed outline, but spend no more than a minute discussing this during your interview.</p>
<p class="" data-start="2487" data-end="2540">Quick math to get a feel for the scale of the system:</p>
<p class="" data-start="2542" data-end="2628"><strong data-start="2542" data-end="2562">Example scenario</strong>:<br data-start="2563" data-end="2566" /><em data-start="2566" data-end="2628">&#8220;Let’s estimate traffic for a simplified Facebook newsfeed.&#8221;</em></p>
<ul data-start="2630" data-end="3116">
<li class="" data-start="2630" data-end="2682">
<p class="" data-start="2632" data-end="2682"><strong data-start="2632" data-end="2645">User Base</strong>: 10 million Daily Active Users (DAU)</p>
</li>
<li class="" data-start="2683" data-end="2733">
<p class="" data-start="2685" data-end="2733"><strong data-start="2685" data-end="2719">Average Posts per User per Day</strong>: ~2 posts/day</p>
</li>
<li class="" data-start="2734" data-end="2827">
<p class="" data-start="2736" data-end="2827"><strong data-start="2736" data-end="2759">Total Posts per Day</strong>:<br data-start="2760" data-end="2763" />10 million users × 2 posts/user/day = <strong data-start="2803" data-end="2827">20 million posts/day</strong></p>
</li>
<li class="" data-start="2828" data-end="3116">
<p class="" data-start="2830" data-end="2911"><strong data-start="2830" data-end="2857">Peak traffic assumption</strong>:<br data-start="2858" data-end="2861" />Assume peak hours have about 2× average traffic:</p>
<ul data-start="2914" data-end="3116">
<li class="" data-start="2914" data-end="2985">
<p class="" data-start="2916" data-end="2985">Average posts/hour: 20 million posts / 24 hours ≈ , <strong data-start="2966" data-end="2985">830K posts/hour</strong></p>
</li>
<li class="" data-start="2988" data-end="3045">
<p class="" data-start="2990" data-end="3045">Peak posts/hour: 830K × 2 ≈ <strong data-start="3018" data-end="3045">1.66 million posts/hour</strong></p>
</li>
<li class="" data-start="3048" data-end="3116">
<p class="" data-start="3050" data-end="3116">Peak posts/second: 1.66 million / 3600 seconds ≈ <strong data-start="3099" data-end="3116">460 posts/sec</strong></p>
</li>
</ul>
</li>
</ul>
<p class="" data-start="3118" data-end="3148"><strong data-start="3118" data-end="3145">Reads (News Feed views)</strong>:</p>
<ul data-start="3149" data-end="3475">
<li class="" data-start="3149" data-end="3180">
<p class="" data-start="3151" data-end="3180">Users open the app ~5 times/day</p>
</li>
<li class="" data-start="3181" data-end="3265">
<p class="" data-start="3183" data-end="3265">Total daily feed requests: 10 million users × 5 = <strong data-start="3233" data-end="3265">50 million feed requests/day</strong></p>
</li>
<li class="" data-start="3266" data-end="3334">
<p class="" data-start="3268" data-end="3334">Average feed requests/hour: 50 million / 24 ≈ <strong data-start="3314" data-end="3334">2.1 million/hour</strong></p>
</li>
<li class="" data-start="3335" data-end="3410">
<p class="" data-start="3337" data-end="3410">Peak hourly requests (2× average): 2.1 million × 2 ≈ <strong data-start="3390" data-end="3410">4.2 million/hour</strong></p>
</li>
<li class="" data-start="3411" data-end="3475">
<p class="" data-start="3413" data-end="3475">Peak requests/sec: 4.2 million / 3600 ≈ <strong data-start="3453" data-end="3475">1,167 requests/sec</strong></p>
</li>
</ul>
<p class="" data-start="3477" data-end="3496">Summarized clearly:</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="3498" data-end="4155">
<thead data-start="3498" data-end="3591">
<tr data-start="3498" data-end="3591">
<th data-start="3498" data-end="3532" data-col-size="sm">Metric</th>
<th data-start="3532" data-end="3565" data-col-size="sm">Calculation</th>
<th data-start="3565" data-end="3591" data-col-size="sm">Approx. Value</th>
</tr>
</thead>
<tbody data-start="3686" data-end="4155">
<tr data-start="3686" data-end="3779">
<td data-start="3686" data-end="3720" data-col-size="sm">Daily Active Users</td>
<td data-col-size="sm" data-start="3720" data-end="3753">Given</td>
<td data-col-size="sm" data-start="3753" data-end="3779">10 million</td>
</tr>
<tr data-start="3780" data-end="3873">
<td data-start="3780" data-end="3814" data-col-size="sm">Daily Posts</td>
<td data-col-size="sm" data-start="3814" data-end="3847">10M DAU × 2 posts/day</td>
<td data-col-size="sm" data-start="3847" data-end="3873">20 million/day</td>
</tr>
<tr data-start="3874" data-end="3967">
<td data-start="3874" data-end="3908" data-col-size="sm">Peak Posts/Second</td>
<td data-col-size="sm" data-start="3908" data-end="3941">(20M ÷ 24 ÷ 3600) × 2</td>
<td data-col-size="sm" data-start="3941" data-end="3967">~460 posts/sec</td>
</tr>
<tr data-start="3968" data-end="4061">
<td data-start="3968" data-end="4002" data-col-size="sm">Daily Feed Requests</td>
<td data-col-size="sm" data-start="4002" data-end="4035">10M users × 5/day</td>
<td data-col-size="sm" data-start="4035" data-end="4061">50 million/day</td>
</tr>
<tr data-start="4062" data-end="4155">
<td data-start="4062" data-end="4096" data-col-size="sm">Peak Feed Requests/Second</td>
<td data-col-size="sm" data-start="4096" data-end="4129">(50M ÷ 24 ÷ 3600) × 2</td>
<td data-col-size="sm" data-start="4129" data-end="4155">~1,167 requests/sec</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="4157" data-end="4254">Use this math to reason clearly about infrastructure and architecture choices in the following phases.</p>
<p data-start="4157" data-end="4254">You can list this in one sentence in your interview:</p>
<blockquote><p>Assuming 10M DAUs making 2 posts/day gives 20M posts/day (~460 posts/sec peak), and each user fetching the feed 5 times/day gives 50M feed requests/day (~1,167 req/sec peak), we can use these to reason about scaling and infra needs.</p></blockquote>
<hr />
<h3 class="" data-start="4256" data-end="4312">Step 4: Clarify User Roles and Access Patterns</h3>
<p class="" data-start="4314" data-end="4382">You can also clarify about user roles and expected behavior:</p>
<ul data-start="4384" data-end="4560">
<li class="" data-start="4384" data-end="4451">
<p class="" data-start="4386" data-end="4451"><strong data-start="4386" data-end="4404">Types of Users</strong>: regular users, admins/moderators, guest users</p>
</li>
<li class="" data-start="4452" data-end="4560">
<p class="" data-start="4454" data-end="4560"><strong data-start="4454" data-end="4470">User actions</strong>: reading posts, liking/reacting, posting content, editing content, and moderation (by admins)</p>
</li>
<li data-start="4452" data-end="4560"><span style="box-sizing: border-box; margin: 0px; padding: 0px;"><strong>Authentication: </strong>Do they require authentication, or can they view without it?</span></li>
</ul>
<hr />
<h3 class="" data-start="4562" data-end="4605">Step 5: Clarify Data Requirements</h3>
<p class="" data-start="4607" data-end="4662">Briefly outline clearly what kind of data you&#8217;ll store:</p>
<ul data-start="4664" data-end="4927">
<li class="" data-start="4664" data-end="4726">
<p class="" data-start="4666" data-end="4726"><strong data-start="4666" data-end="4679">User Data</strong>: Profile info, preferences, social connections</p>
</li>
<li class="" data-start="4727" data-end="4802">
<p class="" data-start="4729" data-end="4802"><strong data-start="4729" data-end="4742">Post Data</strong>: Content, timestamps, media references, reactions, comments</p>
</li>
<li class="" data-start="4803" data-end="4875">
<p class="" data-start="4805" data-end="4875"><strong data-start="4805" data-end="4819">Media Data</strong>: Images/videos stored separately (CDN or media storage)</p>
</li>
<li class="" data-start="4876" data-end="4927">
<p class="" data-start="4878" data-end="4927"><strong data-start="4878" data-end="4890">Metadata</strong>: analytics, logging, and monitoring data</p>
</li>
</ul>
<hr />
<h3 class="" data-start="4929" data-end="4972">Example Walkthrough &#8211; Designing Facebook News Feed</h3>
<p class="" data-start="4974" data-end="5043">Summarize the requirements again after your clarifying questions:</p>
<p class="" data-start="5045" data-end="5072"><strong data-start="5045" data-end="5072">Functional (Must-have):</strong></p>
<ul data-start="5073" data-end="5207">
<li class="" data-start="5073" data-end="5103">
<p class="" data-start="5075" data-end="5103">Infinite-scrolling news feed</p>
</li>
<li class="" data-start="5104" data-end="5134">
<p class="" data-start="5106" data-end="5134">Posts (images, videos, text)</p>
</li>
<li class="" data-start="5135" data-end="5152">
<p class="" data-start="5137" data-end="5152">Likes/Reactions</p>
</li>
<li class="" data-start="5153" data-end="5174">
<p class="" data-start="5155" data-end="5174">Basic user profiles</p>
</li>
<li class="" data-start="5175" data-end="5207">
<p class="" data-start="5177" data-end="5207">Post creation/editing/deletion</p>
</li>
</ul>
<p class="" data-start="5209" data-end="5226"><strong data-start="5209" data-end="5226">Nice-to-have:</strong></p>
<ul data-start="5227" data-end="5357">
<li class="" data-start="5227" data-end="5251">
<p class="" data-start="5229" data-end="5251">Multi-language support</p>
</li>
<li class="" data-start="5252" data-end="5281">
<p class="" data-start="5254" data-end="5281">User analytics and tracking</p>
</li>
<li class="" data-start="5282" data-end="5309">
<p class="" data-start="5284" data-end="5309">Advanced privacy controls</p>
</li>
<li class="" data-start="5310" data-end="5334">
<p class="" data-start="5312" data-end="5334">Accessibility features</p>
</li>
<li class="" data-start="5335" data-end="5357">
<p class="" data-start="5337" data-end="5357">Search functionality</p>
</li>
</ul>
<p class="" data-start="5359" data-end="5378"><strong data-start="5359" data-end="5378">Non-functional:</strong></p>
<ul data-start="5379" data-end="5646">
<li class="" data-start="5379" data-end="5416">
<p class="" data-start="5381" data-end="5416">Performance: Load feeds under 500ms</p>
</li>
<li class="" data-start="5417" data-end="5446">
<p class="" data-start="5419" data-end="5446">Mobile-first, responsive UI</p>
</li>
<li class="" data-start="5447" data-end="5473">
<p class="" data-start="5449" data-end="5473">Offline-friendly caching</p>
</li>
<li class="" data-start="5474" data-end="5511">
<p class="" data-start="5476" data-end="5511">Real-time or near real-time updates</p>
</li>
<li class="" data-start="5512" data-end="5561">
<p class="" data-start="5514" data-end="5561">Scalable architecture (millions of daily users)</p>
</li>
<li class="" data-start="5562" data-end="5603">
<p class="" data-start="5564" data-end="5603">Secure authentication and data handling</p>
</li>
<li class="" data-start="5604" data-end="5646">
<p class="" data-start="5606" data-end="5646">Accessibility and observability features</p>
</li>
</ul>
<p class="" data-start="5648" data-end="5672"><strong data-start="5648" data-end="5672">Scale (Napkin Math):</strong></p>
<ul data-start="5673" data-end="5813">
<li class="" data-start="5673" data-end="5704">
<p class="" data-start="5675" data-end="5704">10 million Daily Active Users</p>
</li>
<li class="" data-start="5705" data-end="5752">
<p class="" data-start="5707" data-end="5752">20 million posts/day (~460 posts/sec at peak)</p>
</li>
<li class="" data-start="5753" data-end="5813">
<p class="" data-start="5755" data-end="5813">50 million feed requests/day (~1,167 requests/sec at peak)</p>
</li>
</ul>
<hr class="" data-start="5815" data-end="5818" />
<p class="" data-start="5820" data-end="5930">Once you&#8217;ve clearly outlined these requirements, you can confidently proceed to the <strong data-start="5903" data-end="5923">Architecture (A)</strong> stage.</p>


---

## 3. Architecture

- Difficulty: 🔴 Hard
- Subtitle: Unlock scalable frontend designs with key architectural insights and principles.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39.png

### Content

<h1>Architecture and High-Level Design in Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1692" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39.png" alt="Frontend System Design Component Design" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-39-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<hr />
<p>The architecture portion of front-end system design interviews is arguably one, if not the most critical and time-consuming portion of the interview. The point of this round is for you to show how you’d lay out your component hierarchy and how all of those pieces connect within your front-end infrastructure.</p>
<blockquote><p><i><b>Start by spending 20% of your interview discussing high-level architecture design, and then come back to this to add more features as you encounter them, all in all, 30% of your interview can be spent here.</b></i></p></blockquote>
<p>You can cover a lot of ground here, and you’ll probably return to this section as you explore topics like performance, state management, or data flow.</p>
<p>For example, if you’re building an infinite scrolling list, you might first lay out your high-level components, then come back to explain how your <code>FeedList</code> component will use virtualization (like <code>react-window</code> or <code>react-virtualized</code>) and an <code>IntersectionObserver</code> to trigger new fetches.</p>
<p>Considering the requirements, your goal is to develop a product/system architecture by identifying the key components of the product, how they interact with each other, and how they are related.</p>
<p>Remember to focus on the <b>client-side architecture</b>, not the back end. Diagrams are your friends here. Each component can be represented using a rectangle. Your high-level design usually resembles a few rectangular boxes with arrows between them to demonstrate the data flow.</p>
<p>It is also possible to have components within components; in that case, draw the parent using bigger rectangles since they need to fit multiple subcomponents.</p>
<p>Think about breaking your components into individual parts. Each part provides its specific purpose.</p>
<hr />
<h3>Diagramming Your Architecture</h3>
<p>You’ll need to draw or outline your component hierarchy clearly. Most interviewers expect some visuals.</p>
<p>You will generally either design this artwork diagram virtually using one of the tools below or, if in person, draw it on a whiteboard.</p>
<ul>
<li><a href="https://lucidchart.com" rel="noreferrer">LucidChart</a>: This is a paid platform for drawing diagrams with many features.</li>
<li><a href="https://excalidraw.com/">Excalidraw</a>: A user-friendly tool for creating hand-drawn-like diagrams.</li>
<li><a href="https://app.diagrams.net/">diagrams.net</a>: A versatile tool for creating diagrams and flowcharts.</li>
</ul>
<p>Practice sketching standard layouts so you’re not fumbling with tools during the interview.</p>
<hr />
<h3>Backend Blackbox</h3>
<p>In front-end system design interviews, we can treat the server as a black box and assume it exposes some APIs you can call via HTTP/WebSockets. The server handles client requests, processes them, and returns the appropriate responses. It can also manage data storage and retrieval, ensuring the client can access the necessary information.</p>
<p>The only time you may need to discuss the backend is during <a href="https://frontendlead.com/system-design/api-design-best-practices">API</a> design, more on that in the following few articles. Even still, you won&#8217;t be asked to build the table schemas, etc, more about the expected request and response from the backend.</p>
<p>Now, if you are in a full-stack loop, then yes, study up on backend principles. <a href="https://frontendlead.com/system-design/general-system-design-fundamentals">Here</a> is an article that walks you through backend fundamentals. Clarify with your interviewer how much you should speak about the front end vs. the backend.</p>
<p>Is it 50/50, 30/70, etc, that can help you guide your interview immediately.</p>
<hr />
<h3>Focus on the Client-Side</h3>
<p>Remember, your job is to lay out the <strong>client-side architecture</strong>. Don’t get bogged down in the backend unless asked to. You want to separate concerns: parent containers, dumb/presentational components, smart containers, reusable UI widgets, etc.</p>
<hr />
<h3>Separation of Concern (MVC vs MVVM)</h3>
<p>There’s no single correct answer here. I like using the MVVM (Model-View-ViewModel) pattern because it creates a clean separation between business logic, state, and UI layers. However, MVC (Model-View-Controller) and similar patterns are also totally valid. The main thing is that your architecture is organized and clear, and you can explain why you chose it.</p>
<h3>Examples</h3>
<p>I’ll show two example architectures:</p>
<ol>
<li><strong>Airbnb Front-End (MVVM Example)</strong></li>
<li><strong>Sprint Board (MVC Example)</strong></li>
</ol>
<h3>Commonalities between the two</h3>
<ul>
<li><strong>Component Hierarchy:</strong> Show how you break down the UI into logical, reusable pieces.</li>
<li><strong>Separation of Concerns:</strong> Make it clear what each component is responsible for. Keep business logic out of pure UI components.</li>
<li><strong>Reusability:</strong> Identify which components can be reused elsewhere in the app.</li>
<li><strong>Data Flow:</strong> Sketch out where state lives (local vs global), how it moves between components, and how components communicate (props, context, events, etc.).</li>
<li><strong>Extensibility:</strong> Briefly mention how your architecture could adapt as features grow.</li>
</ul>
<h3>Tip</h3>
<p>Please return to this diagram and update it as you answer follow-up questions about features, performance, or scaling. Don’t be afraid to revise your architecture in real time; it shows you can adapt as new requirements arise.</p>
<hr />
<h2>Design a Simple Airbnb Client Architecture (MVVM)</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1654" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-05-18-at-1.08.39-PM.png" alt="Design Airbnb - Frontend System Design" width="887" height="873" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-05-18-at-1.08.39-PM.png 887w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-05-18-at-1.08.39-PM-300x295.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-05-18-at-1.08.39-PM-768x756.png 768w" sizes="(max-width: 887px) 100vw, 887px" /></p>
<p>This diagram lays out a modern frontend architecture using the MVVM pattern, and is typical of what you’d want to describe in a system design interview.</p>
<p>Let’s walk through each piece and how the data flows.</p>
<hr />
<h3>High-Level Overview</h3>
<p>Everything here lives on the client. The client&#8217;s main job is to manage routing, state, business logic, rendering, and optimizations like image loading and caching.</p>
<h4>User &amp; Routing</h4>
<ul>
<li><strong>User → React Router</strong><br />
The user interacts with the app, which React Router manages. Based on the URL, routing determines which screen (or view) to show.</li>
</ul>
<hr />
<h4>MVVM Layers</h4>
<ul>
<li><strong>View Model</strong><br />
This is the main bridge between the UI and your business logic. It talks to the network layer (for API calls), manages local state with something like React Context (shown here as &#8220;Store&#8221;), and prepares data for the UI to consume.</p>
<ul>
<li>Please consider the View Model, the smart layer: it fetches data, manages state, and exposes exactly what the view needs.</li>
</ul>
</li>
<li><strong>Store (useContext)</strong><br />
The Store holds shared app state, such as user sessions, cached data, feature toggles, etc., and lets the View Model read/write to it.</p>
<ul>
<li>Context API, Redux, Zustand, or similar could power a React app.</li>
</ul>
</li>
<li><strong>Network</strong><br />
It handles all API requests. The View Model calls the network to fetch or post data and then updates the Store as needed.</li>
</ul>
<hr />
<h4>View Layer</h4>
<ul>
<li><strong><code>&lt;BookingsListContainer /&gt;</code></strong><br />
The container component connects to the View Model (typically via a <code>useViewModel</code> hook). It orchestrates fetching data and renders the correct UI components.</p>
<ul>
<li>This keeps the UI layer as dumb as possible; it just renders what it’s given.</li>
</ul>
</li>
<li><strong><code>&lt;VirtualizedList/&gt;</code></strong><br />
To handle infinite scrolling efficiently, we use a virtualized list. This only renders items in the viewport, boosting performance and smooth scrolling.</li>
<li><strong><code>&lt;BookingCard/&gt;</code>, <code>&lt;ImageSlideshow/&gt;</code></strong><br />
These are presentational components nested inside the virtualized list. Each is focused on rendering a specific part of the UI and receives all its data via props from the parent/container.</li>
</ul>
<hr />
<h4>Image Optimization</h4>
<ul>
<li><strong><code>Image Manager</code> &amp; <code>Cache</code></strong><br />
Image-heavy apps need brilliant image handling. The Image Manager decides when and how to fetch images, pulls from the Image Cache if available, and requests new photos from the Image Service (usually via API).</li>
<li><strong><code>Image Service</code></strong><br />
A backend service for fetching, resizing, or optimizing images on demand.</li>
</ul>
<hr />
<h4>API Layer</h4>
<ul>
<li>The only way to contact the backend is through the network layer&#8217;s API. Everything else is client-side.</li>
</ul>
<hr />
<h3>Why This Architecture Works</h3>
<ul>
<li><strong>Clear separation of concerns:</strong><br />
Business logic (View Model), state (Store), rendering (View), and resource management (Image Manager/Cache) are all isolated and testable.</li>
<li><strong>Extensible:</strong><br />
Easy to add features like offline caching, loading states, error boundaries, and analytics.</li>
<li><strong>Performant:</strong><br />
Virtualized lists and aggressive image caching reduce client memory and boost UX.</li>
<li><strong>Testable and maintainable:</strong><br />
UI components are as dumb as possible. State and logic changes are isolated and easy to cover with unit tests.</li>
</ul>
<hr />
<h3>How to Use This in an Interview</h3>
<p>Talk through each piece, and show how data and user actions flow through the system. Point out how you’d handle edge cases (loading, errors, caching) and how each layer could be extended for future requirements (adding chat, more media, new screens, etc.).</p>
<p>You want your interviewer to see that you’re thinking about:</p>
<ul>
<li>Modularity</li>
<li>Performance</li>
<li>Scalability</li>
<li>Real-world UX tradeoffs</li>
</ul>
<p>That’s the goal with a diagram like this. If you’re asked to go deeper, you can pick any part (like image caching or the virtualized list) and explain exactly how you’d implement it.</p>
<hr />
<h3>Here is the same diagram but using pseudocode:</h3>
<pre><code>
&lt;!-- High-level pseudocode example based on the frontend architecture diagram --&gt;

&lt;!-- App entry point --&gt;
&lt;App&gt;
  &lt;Router&gt;
    &lt;!-- Handles navigation between different screens --&gt;
    &lt;Route path="/bookings"&gt;
      &lt;BookingsListContainer /&gt;
    &lt;/Route&gt;
    &lt;!-- ...other routes --&gt;
  &lt;/Router&gt;
&lt;/App&gt;

&lt;!-- Bookings List Container (MVVM pattern) --&gt;
&lt;BookingsListContainer&gt;
  &lt;!-- useViewModel() handles business logic, state, API calls --&gt;
  &lt;BookingsListContainerView&gt;
    &lt;BookingsList&gt;
      &lt;!-- Render a list of bookings --&gt;
      &lt;BookingsCard&gt;
        &lt;ImageSlideShow /&gt;
      &lt;/BookingsCard&gt;
      &lt;!-- Repeat BookingsCard for each booking --&gt;
    &lt;/BookingsList&gt;
  &lt;/BookingsListContainerView&gt;
&lt;/BookingsListContainer&gt;

&lt;!-- ViewModel logic (abstracted) --&gt;
&lt;!--
  useViewModel() {
    // Fetch data from API using the network layer
    // Interact with Store (useContext or other state management)
    // Return state and actions for the UI
  }
--&gt;

&lt;!-- ImgManager component handles image requests and caching --&gt;
&lt;!--
  ImgManager(src) {
    // Check ImageCache first
    // If not cached, fetch from ImageService
    // Preload images, manage cache eviction
  }
--&gt;

&lt;!-- ImageCache could use memory, IndexedDB, or browser cache --&gt;

&lt;!-- ImageService interacts with backend to fetch/optimize images --&gt;

&lt;!-- BookingCard and ImageSlideShow are presentational components --&gt;</code></pre>
<div aria-hidden="true" data-edge="true"></div>
<div aria-hidden="true" data-edge="true">Deeper dive on how to use <a href="https://frontendlead.com/handbook/mvvm-in-react">MVVM in React</a>.</div>
<div aria-hidden="true" data-edge="true"></div>
<div aria-hidden="true" data-edge="true">Now, let&#8217;s compare this to a MVC model using the sprint board example.</div>
<hr />
<h2>Design a Sprint Board Client Architecture (MVC)</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1404" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-1.png" alt="" width="1140" height="878" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-1.png 1140w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-1-300x231.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-1-1024x789.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-1-768x591.png 768w" sizes="(max-width: 1140px) 100vw, 1140px" /></p>
<p class="" data-start="228" data-end="415">This diagram describes a classic frontend architecture using the MVC (Model-View-Controller) pattern. It is precisely the style of answer you’d want to provide in a system design interview.</p>
<p class="" data-start="417" data-end="500">Let’s break down each section and see how data and actions flow through the system.</p>
<h3 class="" data-start="502" data-end="525">High-Level Overview</h3>
<p class="" data-start="527" data-end="743">Everything here lives on the client. The client’s job is to manage the board state, handle user interactions (like creating a new board or moving tickets), trigger server updates, and reflect those changes in the UI.</p>
<hr class="" data-start="745" data-end="748" />
<h3 class="" data-start="750" data-end="785">User Actions &amp; Controller Layer</h3>
<p class="" data-start="787" data-end="805"><strong data-start="787" data-end="803">User Actions</strong></p>
<ul data-start="806" data-end="927">
<li class="" data-start="806" data-end="927">
<p class="" data-start="808" data-end="927">The user creates a new board or interacts with existing tickets (e.g., dragging and dropping to a new column, updating a ticket).</p>
</li>
</ul>
<p class="" data-start="929" data-end="962"><strong data-start="929" data-end="962">Board Controller (Controller)</strong></p>
<ul data-start="963" data-end="1214">
<li class="" data-start="963" data-end="1012">
<p class="" data-start="965" data-end="1012">The Board Controller receives all user actions.</p>
</li>
<li class="" data-start="1013" data-end="1159">
<p class="" data-start="1015" data-end="1159">For example, when a ticket is dragged to a new column, the controller processes that interaction, updates the state, and coordinates server updates.</p>
</li>
<li class="" data-start="1160" data-end="1214">
<p class="" data-start="1162" data-end="1214">Separates concerns: keeps logic out of the UI layer.</p>
</li>
</ul>
<hr class="" data-start="1216" data-end="1219" />
<h3 class="" data-start="1221" data-end="1238">Example Flows</h3>
<h4 class="" data-start="1240" data-end="1265">Creating a New Board</h4>
<ul data-start="1266" data-end="1501">
<li class="" data-start="1266" data-end="1306">
<p class="" data-start="1268" data-end="1306">The user clicks to create a new board.</p>
</li>
<li class="" data-start="1307" data-end="1357">
<p class="" data-start="1309" data-end="1357">The Board Controller handles the creation logic.</p>
</li>
<li class="" data-start="1358" data-end="1417">
<p class="" data-start="1360" data-end="1417">Sends the request to the Controller and Data Model Store.</p>
</li>
<li class="" data-start="1418" data-end="1501">
<p class="" data-start="1420" data-end="1501">Updates are reflected in the Data Model, and the UI rerenders the new board view.</p>
</li>
</ul>
<h4 class="" data-start="1503" data-end="1533">Updating Existing Tickets</h4>
<ul data-start="1534" data-end="1876">
<li class="" data-start="1534" data-end="1767">
<p class="" data-start="1536" data-end="1560">The user drags a ticket:</p>
<ul data-start="1563" data-end="1767">
<li class="" data-start="1563" data-end="1617">
<p class="" data-start="1565" data-end="1617"><strong data-start="1565" data-end="1580">Drag Start:</strong> The Controller starts tracking the drag.</p>
</li>
<li class="" data-start="1620" data-end="1688">
<p class="" data-start="1622" data-end="1688"><strong data-start="1622" data-end="1635">Drag End:</strong> When dropped, the controller gets the new column ID.</p>
</li>
<li class="" data-start="1691" data-end="1767">
<p class="" data-start="1693" data-end="1767"><strong data-start="1693" data-end="1711">Server Update:</strong> The controller triggers a server update for the change.</p>
</li>
</ul>
</li>
<li class="" data-start="1768" data-end="1876">
<p class="" data-start="1770" data-end="1876">Once confirmed, the controller updates the Data Model Store, and the UI reflects the updated ticket state.</p>
</li>
</ul>
<hr class="" data-start="1878" data-end="1881" />
<h3 class="" data-start="1883" data-end="1892">Views</h3>
<p class="" data-start="1894" data-end="1907"><strong data-start="1894" data-end="1907">Views Box</strong></p>
<ul data-start="1908" data-end="2194">
<li class="" data-start="1908" data-end="1987">
<p class="" data-start="1910" data-end="1987">Contains all UI elements, including the Sprint Board and the Create Composer.</p>
</li>
<li class="" data-start="1988" data-end="2066">
<p class="" data-start="1990" data-end="2066">Each of these views contains child components and handles user interactions.</p>
</li>
<li class="" data-start="2067" data-end="2194">
<p class="" data-start="2069" data-end="2194">These are the “dumb” view layers; they render what the controller and model provide, and never handle business logic directly.</p>
</li>
</ul>
<hr class="" data-start="2196" data-end="2199" />
<h3 class="" data-start="2201" data-end="2234">Controller &amp; Data Model Store</h3>
<ul data-start="2236" data-end="2552">
<li class="" data-start="2236" data-end="2332">
<p class="" data-start="2238" data-end="2332"><strong data-start="2238" data-end="2253">Controller:</strong> Acts as the central logic hub, handling data flow between the view and the model.</p>
</li>
<li class="" data-start="2333" data-end="2474">
<p class="" data-start="2335" data-end="2474"><strong data-start="2335" data-end="2356">Data Model Store:</strong> Stores app state, manages updates, and ensures consistency between what the user sees and what’s stored in the model.</p>
</li>
<li class="" data-start="2475" data-end="2552">
<p class="" data-start="2477" data-end="2552"><strong data-start="2477" data-end="2492">Data Model:</strong> The source of truth for all board, ticket, and column data.</p>
</li>
</ul>
<hr class="" data-start="2554" data-end="2557" />
<h3 class="" data-start="2559" data-end="2590">Why This Architecture Works</h3>
<ul data-start="2592" data-end="3221">
<li class="" data-start="2592" data-end="2822">
<p class="" data-start="2594" data-end="2621"><strong data-start="2594" data-end="2619">Clear MVC Separation:</strong></p>
<ul data-start="2624" data-end="2822">
<li class="" data-start="2624" data-end="2684">
<p class="" data-start="2626" data-end="2684">Controller: Handles user actions and orchestrates updates.</p>
</li>
<li class="" data-start="2687" data-end="2759">
<p class="" data-start="2689" data-end="2759">View: Renders state, receives updates, and reflects UI changes.</p>
</li>
<li class="" data-start="2762" data-end="2822">
<p class="" data-start="2764" data-end="2822">Model: Stores data, updates state, syncs with the backend.</p>
</li>
</ul>
</li>
<li class="" data-start="2824" data-end="2952">
<p class="" data-start="2826" data-end="2858"><strong data-start="2826" data-end="2856">Testable and Maintainable:</strong></p>
<ul data-start="2861" data-end="2952">
<li class="" data-start="2861" data-end="2899">
<p class="" data-start="2863" data-end="2899">Logic is isolated in the controller.</p>
</li>
<li class="" data-start="2902" data-end="2952">
<p class="" data-start="2904" data-end="2952">The view is pure UI and easy to test or replace.</p>
</li>
</ul>
</li>
<li class="" data-start="2954" data-end="3082">
<p class="" data-start="2956" data-end="2973"><strong data-start="2956" data-end="2971">Extensible:</strong></p>
<ul data-start="2976" data-end="3082">
<li class="" data-start="2976" data-end="3082">
<p class="" data-start="2978" data-end="3082">Easy to add new features (e.g., new board actions, advanced ticket filtering, multi-user collaboration).</p>
</li>
</ul>
</li>
<li class="" data-start="3084" data-end="3221">
<p class="" data-start="3086" data-end="3114"><strong data-start="3086" data-end="3112">Predictable Data Flow:</strong></p>
<ul data-start="3117" data-end="3221">
<li class="" data-start="3117" data-end="3221">
<p class="" data-start="3119" data-end="3221">All user actions are handled in the controller, keeping logic centralized and state changes traceable.</p>
</li>
</ul>
</li>
</ul>
<hr class="" data-start="3223" data-end="3226" />
<h3 class="" data-start="3228" data-end="3263">How to Use This in an Interview</h3>
<p class="" data-start="3265" data-end="3521">Talk through each part, and show how a user action (like dragging a ticket) travels through the controller, updates the model, and finally renders in the view. Point out how the controller and model store can handle server updates and optimistic UI.</p>
<p class="" data-start="3523" data-end="3693">If asked to go deeper, you can walk through edge cases (conflicting updates, failed server responses, offline mode) and explain how MVC helps handle each scenario.</p>
<hr class="" data-start="3695" data-end="3698" />
<h3 class="" data-start="3700" data-end="3735">Pseudocode for MVC Sprint Board</h3>
<pre><code>
&lt;!-- High-level pseudocode based on the Sprint Board MVC architecture --&gt;

&lt;!-- App entry point --&gt;
&lt;App&gt;
  &lt;!-- Main Controller handles all board actions --&gt;
  &lt;BoardController&gt;
    &lt;!-- Views handle rendering only --&gt;
    &lt;SprintBoard&gt;
      &lt;!-- Child Components for columns, tickets, etc. --&gt;
    &lt;/SprintBoard&gt;
    &lt;CreateComposer /&gt;
  &lt;/BoardController&gt;
&lt;/App&gt;

&lt;!-- Example User Action Flow --&gt;
&lt;!--
  User drags a ticket:
    BoardController handles dragStart event
    On dragEnd, BoardController gets new column id
    BoardController sends update to DataModelStore
    DataModelStore updates DataModel and triggers server update
    On success, View rerenders with new ticket position
--&gt;

&lt;!-- DataModelStore maintains app state and syncs with backend --&gt;

&lt;!-- Views (SprintBoard, CreateComposer, Child Components) are dumb, render-only --&gt;

&lt;!-- DataModel is the source of truth for board/ticket/column data --&gt;
</code></pre>
<hr class="" data-start="4676" data-end="4679" />
<p class="" data-start="4681" data-end="4880">You want to use this approach to talk through a sprint board frontend using MVC.</p>
<p class="" data-start="4681" data-end="4880"><br data-start="4772" data-end="4775" />Keep your answer clear, actionable, and easy to reference for whiteboard and live coding interviews.</p>
<hr />
<h3>Additional Considerations for Front-End Architecture</h3>
<p>When designing the architecture for a front-end application, there are several additional considerations to keep in mind:</p>
<table>
<thead>
<tr>
<th>Aspect</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><b>Performance</b></td>
<td>Ensure that the application is responsive and performs well under various conditions. This can involve optimizing the UI rendering, minimizing the number of network requests, and reducing the size of the data being transferred. Techniques such as lazy loading, caching, and debouncing can help improve the application&#8217;s performance.</td>
</tr>
<tr>
<td><b>Scalability</b></td>
<td>Design the application to handle increasing users and data. This can involve using techniques such as pagination, infinite scrolling, and virtualized lists to manage large amounts of data. It can also include designing the architecture to support horizontal scaling, such as using load balancers and distributed data stores.</td>
</tr>
<tr>
<td><b>Maintainability</b></td>
<td>Ensure that the application is easy to maintain and extend. This can involve using modular components, following coding standards, and writing tests. It can also include managing the codebase using tools such as linters, code formatters, and version control systems.</td>
</tr>
<tr>
<td><b>Security</b></td>
<td>Protect the application from security threats like cross-site scripting (XSS), cross-site request forgery (CSRF), and SQL injection. This can involve using techniques such as input validation, output encoding, and secure communication protocols. It can also include the following best practices for authentication and authorization, such as using OAuth and JWT.</td>
</tr>
<tr>
<td><b>User Experience</b></td>
<td>Design the application to provide a positive user experience. This can involve using techniques such as responsive design, accessibility, and internationalization. It can also include the following best UI design practices: consistent layouts, straightforward navigation, and intuitive interactions.</td>
</tr>
</tbody>
</table>
<hr />
<p>If you are with me so far, congrats, because I know that wasn&#8217;t easy. The good news is that you can apply this architectural diagram system to any frontend system design interview forever.</p>
<p>Now, let&#8217;s move <span style="box-sizing: border-box; margin: 0px; padding: 0px;">on to the <strong>(D) in R.A.D.I.O</strong>, the data model portion of the </span>Frontend System Design interview.</p>


---

## 4. Data Model

- Difficulty: 🔴 Hard
- Subtitle: Master client-only data management for seamless frontend system design.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41.png

### Content

<h1>State and Client Data Model In Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1696" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41.png" alt="Frontend System Design Data Model" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-41-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<p class="" data-start="177" data-end="440">In this portion of the interview, spend about half your time discussing how you’ll handle state on the client, and the other half on the actual data model you’ll use in your frontend.</p>
<p data-start="177" data-end="440"><em><strong>Please spend no more than 15% of your interview explaining this portion.</strong></em></p>
<hr />
<h2 data-start="442" data-end="476">State Management on the Client</h2>
<p class="" data-start="478" data-end="698">State management is one of those things everyone has an opinion about. There are plenty of options, each with its strengths and trade-offs.</p>
<p class="" data-start="478" data-end="698">Here are the most common choices you’ll see in real-world frontend projects.</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="700" data-end="1557">
<thead data-start="700" data-end="730">
<tr data-start="700" data-end="730">
<th data-start="700" data-end="715" data-col-size="sm">Type</th>
<th data-start="715" data-end="730" data-col-size="xl">Description</th>
</tr>
</thead>
<tbody data-start="762" data-end="1557">
<tr data-start="762" data-end="887">
<td data-start="762" data-end="777" data-col-size="sm">useState</td>
<td data-start="777" data-end="887" data-col-size="xl">React&#8217;s built-in hook manages the local component state. It is best for isolated UI pieces or small components.</td>
</tr>
<tr data-start="888" data-end="1072">
<td data-start="888" data-end="903" data-col-size="sm">useContext</td>
<td data-start="903" data-end="1072" data-col-size="xl">Built-in React API for passing data through the component tree without prop drilling. Works well for global values like authentication, themes, or language settings.</td>
</tr>
<tr data-start="1073" data-end="1215">
<td data-start="1073" data-end="1088" data-col-size="sm">Redux</td>
<td data-start="1088" data-end="1215" data-col-size="xl">Powerful state management library for large, complex apps that need global state and strict control over how state changes.</td>
</tr>
<tr data-start="1216" data-end="1336">
<td data-start="1216" data-end="1231" data-col-size="sm">Recoil</td>
<td data-start="1231" data-end="1336" data-col-size="xl">Provides atomic state and derived data, making managing and sharing state across components easier.</td>
</tr>
<tr data-start="1337" data-end="1451">
<td data-start="1337" data-end="1352" data-col-size="sm">Zustand</td>
<td data-start="1352" data-end="1451" data-col-size="xl">Minimalistic and flexible state management, simple API, good performance for medium-sized apps.</td>
</tr>
<tr data-start="1452" data-end="1557">
<td data-start="1452" data-end="1467" data-col-size="sm">MobX</td>
<td data-col-size="xl" data-start="1467" data-end="1557">Uses observables for automatic state tracking, helps with complex reactivity patterns.</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="1559" data-end="1736">A combination of useContext and useState for most front-end apps covers most cases. It keeps things simple and easy to follow, especially when the app is not massive.</p>
<hr class="" data-start="1738" data-end="1741" />
<h3 class="" data-start="1989" data-end="2027">UseContext vs Redux: Pros and Cons</h3>
<p class="" data-start="2029" data-end="2113">If you’re comparing useContext to Redux, it’s pretty clear-cut for most modern apps.</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="2115" data-end="2977">
<thead data-start="2115" data-end="2222">
<tr data-start="2115" data-end="2222">
<th data-start="2115" data-end="2132" data-col-size="sm"></th>
<th data-start="2132" data-end="2174" data-col-size="sm">useContext</th>
<th data-start="2174" data-end="2222" data-col-size="md">Redux</th>
</tr>
</thead>
<tbody data-start="2331" data-end="2977">
<tr data-start="2331" data-end="2438">
<td data-start="2331" data-end="2348" data-col-size="sm">Setup</td>
<td data-start="2348" data-end="2390" data-col-size="sm">Minimal, comes with React</td>
<td data-col-size="md" data-start="2390" data-end="2438">Lots of setup, external library</td>
</tr>
<tr data-start="2439" data-end="2546">
<td data-start="2439" data-end="2456" data-col-size="sm">Complexity</td>
<td data-start="2456" data-end="2498" data-col-size="sm">Straightforward, easy to reason about</td>
<td data-col-size="md" data-start="2498" data-end="2546">Heavy, introduces extra layers and patterns</td>
</tr>
<tr data-start="2547" data-end="2654">
<td data-start="2547" data-end="2564" data-col-size="sm">Performance</td>
<td data-col-size="sm" data-start="2564" data-end="2606">Good for most apps</td>
<td data-col-size="md" data-start="2606" data-end="2654">Not better for performance</td>
</tr>
<tr data-start="2655" data-end="2762">
<td data-start="2655" data-end="2672" data-col-size="sm">Flexibility</td>
<td data-start="2672" data-end="2714" data-col-size="sm">Enough for most global data</td>
<td data-col-size="md" data-start="2714" data-end="2762">Useful mainly for legacy or massive codebases</td>
</tr>
<tr data-start="2763" data-end="2869">
<td data-start="2763" data-end="2780" data-col-size="sm">Tooling</td>
<td data-col-size="sm" data-start="2780" data-end="2821">Basic</td>
<td data-col-size="md" data-start="2821" data-end="2869">Has its own set of devtools</td>
</tr>
<tr data-start="2870" data-end="2977">
<td data-start="2870" data-end="2887" data-col-size="sm">Learning Curve</td>
<td data-col-size="sm" data-start="2887" data-end="2929">Quick for any React dev</td>
<td data-col-size="md" data-start="2929" data-end="2977">Steep and often not worth it</td>
</tr>
</tbody>
</table>
</div>
</div>
<p class="" data-start="2766" data-end="2991">In most cases, useContext provides everything you need for a global state. It keeps things clean, is easy to debug, and doesn’t require learning a whole new system.</p>
<hr />
<h3 class="" data-start="240" data-end="264">Data to be Persisted</h3>
<p class="" data-start="266" data-end="569">Sometimes, you need data to persist across page refreshes or support offline access. Most of the time, fetching the latest data from the server is enough. But if you want to reduce server requests, speed up your app, or enable offline support, you’ll need client-side storage.</p>
<p class="" data-start="571" data-end="762">On the web, your main options are local storage, session storage, IndexedDB, and cookies. Each has its own strengths and limitations, especially regarding storage size and data structure.</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="764" data-end="1585">
<thead data-start="764" data-end="900">
<tr data-start="764" data-end="900">
<th data-start="764" data-end="783" data-col-size="sm">Storage Type</th>
<th data-start="783" data-end="845" data-col-size="md">Pros</th>
<th data-start="845" data-end="900" data-col-size="md">Cons</th>
</tr>
</thead>
<tbody data-start="1038" data-end="1585">
<tr data-start="1038" data-end="1174">
<td data-start="1038" data-end="1057" data-col-size="sm">Local Storage</td>
<td data-start="1057" data-end="1119" data-col-size="md">Simple, persists after refresh, easy to use</td>
<td data-col-size="md" data-start="1119" data-end="1174">Synchronous, small size limit, plain string values</td>
</tr>
<tr data-start="1175" data-end="1311">
<td data-start="1175" data-end="1194" data-col-size="sm">Session Storage</td>
<td data-start="1194" data-end="1256" data-col-size="md">Same as local storage, but data clears on tab close</td>
<td data-col-size="md" data-start="1256" data-end="1311">Data lost on close, small size limit</td>
</tr>
<tr data-start="1312" data-end="1448">
<td data-start="1312" data-end="1331" data-col-size="sm">IndexedDB</td>
<td data-start="1331" data-end="1393" data-col-size="md">Ample storage, supports complex objects, asynchronous</td>
<td data-col-size="md" data-start="1393" data-end="1448">API is more complex, browser quirks</td>
</tr>
<tr data-start="1449" data-end="1585">
<td data-start="1449" data-end="1468" data-col-size="sm">Cookies</td>
<td data-col-size="md" data-start="1468" data-end="1530">Sent with requests, used for auth/session</td>
<td data-col-size="md" data-start="1530" data-end="1585">Tiny size, less secure, and outdated for data</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<hr />
<h3 data-start="1587" data-end="1938">Scoped vs Global State</h3>
<p class="" data-start="1587" data-end="1938">When it comes to state, it’s crucial not to default to global state for everything. Most of the time, having a scoped state at the component or feature level simplifies and makes your app more performant. Only reach for global state (with tools like useContext) when you truly need to share data between different views or parts of your app.</p>
<p class="" data-start="1940" data-end="2035">Here’s a quick table comparing scoped state to global state, especially in terms of re-renders:</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="2037" data-end="2660">
<thead data-start="2037" data-end="2149">
<tr data-start="2037" data-end="2149">
<th data-start="2037" data-end="2055" data-col-size="sm">State Type</th>
<th data-start="2055" data-end="2106" data-col-size="md">Use Case</th>
<th data-start="2106" data-end="2149" data-col-size="lg">Impact on Re-renders</th>
</tr>
</thead>
<tbody data-start="2263" data-end="2660">
<tr data-start="2263" data-end="2443">
<td data-start="2263" data-end="2281" data-col-size="sm">Scoped State</td>
<td data-col-size="md" data-start="2281" data-end="2332">State used only in one component or a small subtree</td>
<td data-col-size="lg" data-start="2332" data-end="2443">Only the owning component and its children re-render when the state changes. Keeps updates local and efficient.</td>
</tr>
<tr data-start="2444" data-end="2660">
<td data-start="2444" data-end="2462" data-col-size="sm">Global State</td>
<td data-col-size="md" data-start="2462" data-end="2521">State is shared across multiple views or distant components</td>
<td data-col-size="lg" data-start="2521" data-end="2660">All components that consume the global state will re-render on any state change, which can impact performance if not managed carefully.</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="2662" data-end="2805">Choosing the proper scope for your state helps avoid unnecessary re-renders and keeps your app fast. Use global state only when truly necessary.</p>
<p class="" data-start="1780" data-end="1837">Next up, an example for building out a client data model.</p>
<hr />
<h2>Client Data Model</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-563" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.42-PM.png" alt="" width="815" height="335" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.42-PM.png 815w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.42-PM-300x123.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.42-PM-768x316.png 768w" sizes="(max-width: 815px) 100vw, 815px" /></p>
<p>A clear and well-defined client data model is the foundation of a reliable frontend architecture. The data model lays out the types you need to render content on the client, and it should mirror the actual entities your UI works with. Good modeling helps keep your state predictable, makes components easier to build, and allows for efficient updates and rendering.</p>
<p>When building out your client data model, start by identifying the core entities in your app. For a feed-based product, this might include things like users, feed items, comments, and user settings. Group related data together and keep your types organized, so it&#8217;s clear how each piece of state fits into the overall app structure.</p>
<p>The following example demonstrates how to structure your types using TypeScript. This approach makes the shape of your data explicit and helps with both development and maintenance.</p>
<pre><code class="language-ts">
// Root app state
type App = {
  user: User;
  settings: UserSettings;
  feed: Feed;
};

// Feed and feed items
type Feed = {
  items: FeedItem[];
  page: number;
  size: number;
};

type FeedItem = {
  type: FeedItemType;
  creationDate: string;
  author: User;
  content: FeedItemContent;
  comments: FeedItemComment[];
};

type FeedItemContent = {
  title: StyledText;
  body: StyledText;
  media?: Media;
};

// Supporting types
type User = {
  name: string;
  // ...other user fields
};

type UserSettings = {
  timeZone: string;
  accessibilityPreferences: AccessibilityPreferences;
  // ...other settings
};

type FeedItemComment = {
  author: User;
  content: StyledText;
  creationDate: string;
  // ...other comment fields
};

type StyledText = {
  // Rich text, colors, links, mentions, etc.
  // Server-driven UI structure
};

type Media = {
  url: string;
  type: 'image' | 'video' | 'audio';
  // ...other media fields
};

type FeedItemType = 'post' | 'announcement' | 'update'; // Example types

type AccessibilityPreferences = {
  fontSize: string;
  contrastMode: boolean;
  // ...other preferences
};
</code></pre>
<p>In this model, each type is built for a clear responsibility. The <code>App</code> root type holds the user, settings, and feed data. The <code>Feed</code> list contains <code>FeedItem</code> objects, each with metadata, content, and comments. Content and comments use a <code>StyledText</code> structure to support rich text, colors, links, and mentions. User settings are scoped to the user, making room for accessibility features.</p>
<p>Modeling your client data this way keeps the shape of your state explicit, so you always know what to expect in your components. It also sets you up for scalable code, as new features or entities can be added to the types without significant rewrites. Well-structured models lead to easier debugging and better overall performance on your front end.</p>
<p>&nbsp;</p>
<hr />
<h2>Data Normalization</h2>
<p>Whenever possible, aim for a normalized data structure on the client. Normalization means storing each entity type (like users, posts, and comments) separately by ID rather than nesting full objects within other objects. This approach avoids data duplication, keeps your state consistent, and simplifies updates.</p>
<p>Here’s a quick example of a non-normalized versus normalized state shape:</p>
<p><strong>Non-normalized:</strong></p>
<pre><code class="language-ts">
const feed = [
  {
    id: "post1",
    author: { id: "user1", name: "Alice" },
    content: "Hello world",
    comments: [
      { id: "comment1", author: { id: "user2", name: "Bob" }, text: "Nice post!" }
    ]
  }
];
</code></pre>
<p><strong>Normalized:</strong></p>
<pre><code class="language-ts">
const users = {
  user1: { id: "user1", name: "Alice" },
  user2: { id: "user2", name: "Bob" }
};

const posts = {
  post1: {
    id: "post1",
    authorId: "user1",
    content: "Hello world",
    commentIds: ["comment1"]
  }
};

const comments = {
  comment1: {
    id: "comment1",
    authorId: "user2",
    text: "Nice post!"
  }
};
</code></pre>
<p>With normalization, updates to a user or comment happen in a single place, and you never have to worry about stale or duplicated data across the app. This pattern works well for any frontend that handles dynamic or relational data.</p>
<hr />
<p>Next, let&#8217;s move on to the <strong>I in R.A.D.I.O</strong>, which stands for Interface design. This is a fancy saying, &#8220;Let&#8217;s build the API layer.&#8221;</p>


---

## 5. Interface Communication

- Difficulty: 🟠 Medium
- Subtitle: Explore the essentials of web tech: HTTP, REST, GraphQL, and SSE.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42.png

### Content

<h1>Interface Communication Frontend System Design Interviews</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1698" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42.png" alt="Interface Communication For Frontend System Design" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-42-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<article>The “I” in the RADIO framework stands for Interface, which is partially about how the front-end system communicates with the backend (interface communication) and how it will format its request and response (API layer). </article>
<article></article>
<article></article>
<article>This section is critical, but it shouldn’t take more than 15 percent of your interview time unless the interviewer wants to discuss it in depth. Let&#8217;s simplify this section so that the first half is focused on the interface layer, and the following article will focus on the API design layer.</article>
<article>
<blockquote><p><em><strong>Please spend no more than 5% of your interview explaining the interface communication layer and 10% on the api layer.</strong></em></p></blockquote>
<p>Before diving into API design, determine your protocol for the API layer. The right choice depends on the nature of the app and its requirements. For example, if you’re building a chat application, real-time, two-way communication is key, so WebSockets make sense. If you’re streaming updates in one direction, such as an AI chat response, server-sent events (SSE) are a good fit. Regular HTTP requests do the job for use cases like a news feed or simple data fetches as the user scrolls.</p>
<p>Here’s a table that compares the main protocols you might consider:</p>
<table>
<thead>
<tr>
<th>Protocol</th>
<th>Description</th>
<th>Best Use Case</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>HTTP (REST)</td>
<td>Traditional request-response, stateless, one-way</td>
<td>Fetching data, CRUD apps, news feeds, and most APIs</td>
<td>Simple, well-supported, cacheable, easy to debug</td>
<td>No real-time, can be chatty for frequent updates</td>
</tr>
<tr>
<td>Short Polling</td>
<td>The client frequently requests new data on a timer</td>
<td>Low-frequency updates, simple notifications</td>
<td>Easy to implement, no persistent connection</td>
<td>Wastes bandwidth, latency, and is not efficient at scale</td>
</tr>
<tr>
<td>Long Polling</td>
<td>Client requests data, server holds connection until update or timeout</td>
<td>Near real-time updates, legacy support</td>
<td>More responsive than short polling, simple fallback</td>
<td>Can tie up server resources, and is more complex to scale</td>
</tr>
<tr>
<td>Server-Sent Events (SSE)</td>
<td>Server pushes updates to client, client receives in real time (one-way)</td>
<td>Live feeds, notifications, streaming responses</td>
<td>Simple API, built-in reconnect, works over HTTP</td>
<td>One-way only, not supported in all browsers</td>
</tr>
<tr>
<td>WebSockets</td>
<td>Full duplex, persistent two-way communication</td>
<td>Chat, multiplayer games, and collaborative editing</td>
<td>Real-time, efficient, low-latency</td>
<td>More complex, requires a stateful server, and can be harder to scale</td>
</tr>
<tr>
<td>GraphQL</td>
<td>Client defines queries, gets exactly the data needed in one request</td>
<td>Apps with complex or nested data, mobile, SPAs</td>
<td>Reduces over-fetching, is flexible, and promotes introspection</td>
<td>Requires schema, learning curve, and can hide complexity</td>
</tr>
</tbody>
</table>
<p>Protocol choice should match your product’s requirements. Real-time needs? Think WebSockets. One-way streaming? Try SSE. Standard API data fetching? Go with REST or GraphQL. For most standard apps, HTTP REST remains a reliable default.</p>
<p>You can find a deeper dive for each in this <a href="https://frontendlead.com/system-design/web-protocols-cheat-sheet">article</a>.</p>
</article>
<hr />
<p>Next, look into designing the API in frontend system design interviews. You might be wondering (probably not), shouldn&#8217;t <strong>R.A.D.I.O</strong> have an extra <strong>A</strong>, for API design? While you may be right, we don&#8217;t talk about it.</p>
<p>Now let&#8217;s proceed.</p>


---

## 6. API Design

- Difficulty: 🔴 Hard
- Subtitle: Discover the art of API design for front-end excellence.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43.png

### Content

<h1>API Design in Front-End Systems</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1700" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43.png" alt="Frontend System Design API Design" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-43-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<p>The API layer is the bridge between your frontend and the backend server. Whenever your app needs to load data, create new posts, update content, or listen for changes, it communicates with the server through APIs. The protocol you choose for this communication depends on the type of application you are building and its real-time requirements.</p>
<blockquote><p><em><strong>Please spend no more than 20% of your interview explaining this portion.</strong></em></p></blockquote>
<hr />
<h3>Choosing the Right API Protocol</h3>
<p>The choice of API protocol comes down to the application&#8217;s needs. Here’s a quick reference table of common front-end application types and the protocols that make the most sense for each:</p>
<table>
<thead>
<tr>
<th>App Type</th>
<th>Example Feature</th>
<th>Recommended API Protocol</th>
</tr>
</thead>
<tbody>
<tr>
<td>Chat Application</td>
<td>Real-time messaging between users</td>
<td>WebSockets</td>
</tr>
<tr>
<td>News Feed</td>
<td>Scrolling to load posts, pulling new content</td>
<td>HTTP REST</td>
</tr>
<tr>
<td>Live Notifications</td>
<td>Instant alerts or status updates</td>
<td>Server-Sent Events (SSE) or WebSockets</td>
</tr>
<tr>
<td>Collaborative Editing</td>
<td>Multiple users editing the same document</td>
<td>WebSockets</td>
</tr>
<tr>
<td>AI/Streaming Response</td>
<td>Streaming generated text (like ChatGPT)</td>
<td>Server-Sent Events (SSE)</td>
</tr>
<tr>
<td>Profile or Settings Management</td>
<td>Fetching and updating user preferences</td>
<td>HTTP REST or GraphQL</td>
</tr>
<tr>
<td>Analytics Dashboard</td>
<td>Loading and filtering reports or metrics</td>
<td>HTTP REST or GraphQL</td>
</tr>
</tbody>
</table>
<hr />
<h3>Designing API Endpoints Example: Facebook-Style News Feed</h3>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-567" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.16-PM.png" alt="Frontend System Design API Design" width="676" height="335" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.16-PM.png 676w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.32.16-PM-300x149.png 300w" sizes="(max-width: 676px) 100vw, 676px" /></p>
<p>Most data fetching can be handled with HTTP-based APIs for a typical news feed or social app. GraphQL is an excellent choice if your data is complex and clients want to specify what fields they need. Below is a set of example endpoints for a Facebook-style feed, showing how you might structure queries and mutations for getting a feed, getting a specific feed item, and creating a new post.</p>
<pre><code class="language-graphql">
// Get Feed (Cursor-based pagination)
GET /api/v1/gql/feed
Input: {
  cursor: string,       // Optional, points to the last item from the previous fetch
  limit: number,        // How many items to fetch
  post_types: [PostType], // filter feed items by type
  // ...other filters
}
Headers: {
  user_id: string // used for authentication and personalized feeds
}
// Response: List of FeedItems, next cursor, etc.

// Get Feed Item
GET /api/v1/gql/feed-item
Input: {
  post_id: string
}
Headers: {
  user_id: string
}
// Response: Single FeedItem with comments and metadata

// Create Post
POST /api/v1/gql/create-feed-post
Input: {
  title: String,
  media: [Media],
  // ...other post fields
}
Headers: {
  user_id: string
}
// Response: Status code, created post ID, errors if any
</code></pre>
<hr />
<h3>Expected Response: News Feed Example</h3>
<pre><code class="language-json">
{
  "data": [
    {
      "id": "post1",
      "author": { "id": "user1", "name": "Alice" },
      "content": "Hello world",
      "createdAt": "2024-05-19T18:24:00Z",
      "media": [{ "url": "...", "type": "image" }],
      "comments": [
        { "id": "comment1", "author": { "id": "user2", "name": "Bob" }, "text": "Nice post!" }
      ]
    },
    // more posts...
  ],
  "nextCursor": "YXJyYXljb25uZWN0aW9uOjEw",  // base64 encoded cursor for next fetch
  "hasMore": true
}
</code></pre>
<hr />
<h3>Why Cursor-Based Pagination?</h3>
<p>Cursor-based pagination is preferred for news feeds and infinite scrolling because it is more robust when data changes rapidly. Unlike page-based pagination (pages 1, 2, and 3), which can show duplicate or missing results if new posts are added or old ones are deleted between requests, cursor-based pagination always starts from the last item received. This keeps the data consistent as the user scrolls and ensures smooth UX even as new posts arrive.</p>
<p>Cursor-based approaches are also more scalable for large datasets and prevent issues with users seeing the duplicate content twice or skipping content when the feed updates quickly. The server returns a cursor pointing to the following item, which the client uses to fetch the next set of results.</p>
<hr />
<h3>Best Practices for API Design</h3>
<ul>
<li><strong>Version your API:</strong> Always include a version number in your API path, such as <code>/api/v1/...</code>, to avoid breaking changes for clients when you need to evolve your API over time.</li>
<li><strong>Consistent naming conventions:</strong> Use clear, predictable endpoint names and stick to a consistent case (camelCase or snake_case).</li>
<li><strong>Authentication:</strong> Pass authentication tokens or user IDs using secure headers. Avoid sensitive data in URLs or query parameters.</li>
<li><strong>Explicit status codes:</strong> Always return the correct HTTP status codes for success, errors, or unauthorized requests (200, 201, 400, 401, 404, 500, etc).</li>
<li><strong>Clear error messages:</strong> Provide meaningful error objects with error codes and messages so the frontend can handle problems gracefully.</li>
<li><strong>Flexible filtering and sorting:</strong> Allow clients to filter, sort, and paginate data to reduce unnecessary payloads and improve performance.</li>
<li><strong>Minimal over-fetching:</strong> With GraphQL or well-designed REST, the client can specify which fields to use to reduce bandwidth and improve speed.</li>
<li><strong>Documentation:</strong> Keep API contracts well-documented and updated so frontend and backend teams stay in sync.</li>
</ul>
<p>Good API design keeps your frontend flexible, makes your system easy to debug, and allows you to scale easily as your product grows.</p>
<hr />
<p>&nbsp;</p>
<h3>API Request Headers and Response Format</h3>
<p>Every API call your frontend makes should clearly define what headers are sent and what response body is expected in return. Proper headers ensure security, user personalization, and reliable communication. The response structure should be predictable and easy to transform into your client-side data store.</p>
<h4>Common Request Headers</h4>
<ul>
<li><strong>Authorization</strong>: <code>Bearer &lt;token&gt;</code> – used for authenticating the user session.</li>
<li><strong>Content-Type</strong>: <code>application/json</code> – specifies the format of the request body.</li>
<li><strong>X-User-ID</strong>: User identifier for tracking or personalization (when sessions are stateless).</li>
<li><strong>Accept-Language</strong>: Sets the preferred language for localized responses.</li>
<li><strong>X-Request-ID</strong>: Optional, used for tracing and debugging across distributed systems.</li>
</ul>
<pre><code class="language-http">
GET /api/v1/gql/feed
Authorization: Bearer eyJhbGciOi...
Content-Type: application/json
X-User-ID: user_12345
Accept-Language: en-US
X-Request-ID: 123e4567-e89b-12d3-a456-426614174000
</code></pre>
<h4>Expected Response Body</h4>
<p>The response body should return all necessary information for rendering the UI and updating your client data model. Here’s a sample for a feed endpoint:</p>
<pre><code class="language-json">
{
  "data": [
    {
      "id": "post_1",
      "author": {
        "id": "user_123",
        "name": "Alice"
      },
      "content": "Hello world",
      "createdAt": "2024-05-19T18:24:00Z",
      "media": [
        { "url": "https://cdn.example.com/image1.jpg", "type": "image" }
      ],
      "comments": [
        {
          "id": "comment_1",
          "author": {
            "id": "user_456",
            "name": "Bob"
          },
          "text": "Nice post!",
          "createdAt": "2024-05-19T18:25:00Z"
        }
      ]
    }
    // ...more posts
  ],
  "nextCursor": "YXJyYXljb25uZWN0aW9uOjEw",
  "hasMore": true
}
</code></pre>
<h4>Transforming the Response on the Client</h4>
<p>When the response arrives, map and normalize the data to match your local client data model. Extract users, posts, and comments into separate entities for easier updates and caching. This makes rendering faster and future data changes more predictable.</p>
<hr />
<p>Next up, let&#8217;s finally discuss the <strong>O in R.A.D.I.O</strong>, which is <strong>Optimizations</strong>.</p>


---

## 7. Optimizations

- Difficulty: 🔴 Hard
- Subtitle: Maximize your front-end system's speed, efficiency, and security with our expert design strategies.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44.png

### Content

<h1>Performance Optimizations For Frontend System Design Interviews</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1702" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44.png" alt="Frontend Performance and Optimizations" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-44-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<p>Once you’ve wrapped up all the core topics in your front-end system design interview, architectural design, API design, client data modeling, and more, this is your chance to stand out. The last part of your interview is where you shift gears and dive into front-end optimizations.</p>
<p>When it comes to optimizations, you want to think about every aspect that affects your app’s performance and user experience, but focus on what matters for the specific question you’re solving. This article gives a high-level overview of the most critical optimization techniques you can bring up in any front-end system design interview. Don’t feel pressured to use every method you know; instead, select the optimizations that best fit the scenario in front of you.</p>
<blockquote><p><em><strong>Please spend no more than 20% of your interview explaining this portion.</strong></em></p></blockquote>
<p>High-performing frontends scale well, respond quickly, and stay consistent across all types of user hardware. If your app only works for people with the latest devices, you&#8217;ve missed a massive part of what real-world performance means.</p>
<hr />
<h3>Types of Front-End Performance Bottlenecks</h3>
<p>Performance issues can come from many sources. You want to consider:</p>
<ul>
<li><strong>Network bottlenecks</strong>: Large payloads, slow APIs, or too many requests.</li>
<li><strong>Rendering bottlenecks</strong>: Too much DOM, inefficient updates, or unoptimized rendering cycles.</li>
<li><strong>JavaScript execution</strong>: Heavy libraries, unnecessary code, or blocking scripts.</li>
<li><strong>Asset delivery</strong>: Large images, fonts, or video assets that slow down page loads.</li>
<li><strong>Device constraints</strong>: Slow CPUs, low memory, or poor graphics on specific user devices.</li>
</ul>
<hr />
<h3>How to Measure Performance</h3>
<p>Before you optimize, you need to measure. There are two main ways to do this:</p>
<ol>
<li><strong>Local Measurement</strong><br />
Use tools like <a href="https://pagespeed.web.dev/">Google PageSpeed Insights</a>, Chrome DevTools, Lighthouse, or React/Redux profiling tools. These help you understand how your app performs in a controlled environment and can pinpoint slow components or rendering bottlenecks.</li>
<li><strong>User-Centric (Real-World) Measurement</strong><br />
You must collect and analyze real user metrics if you want an accurate picture of your app’s performance for your entire user base. Instrument your frontend to track key metrics such as:</p>
<ul>
<li><strong>TTI (Time to Interactive):</strong> When the page is usable and responsive.</li>
<li><strong>FPS (Frames Per Second):</strong> For scroll and animation smoothness.</li>
<li><strong>FCP (First Contentful Paint):</strong> When meaningful content is first visible.</li>
<li><strong>Other metrics</strong><strong> include the</strong> largest contentful paint, cumulative layout shift, etc.</li>
</ul>
<p>Send these metrics to your telemetry or analytics system (e.g., Datadog, Grafana, or a custom dashboard) so you can monitor how changes impact real users, spot regressions, and prioritize improvements that matter.</li>
</ol>
<p>The most effective optimizations are always informed by real data, not just best guesses. Start with measurement, then dig into bottlenecks, and only then plan your performance improvements.</p>
<hr />
<h2>Network Performance</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-579" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.27-PM.png" alt="" width="924" height="557" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.27-PM.png 924w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.27-PM-300x181.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.27-PM-768x463.png 768w" sizes="(max-width: 924px) 100vw, 924px" /></p>
<p>Network performance is one of the most critical levers for speeding up your front-end. You can write the best JavaScript in the world, but users will still have a bad time if your network stack is slow or inefficient. Based on the diagram above, here’s a breakdown of the main strategies you can use to optimize network performance.</p>
<ul>
<li><strong>HTTP/2 and Multiplexing</strong>:<br />
HTTP/2 allows multiple requests to be sent over a single connection, reducing round-trip times and speeding up how assets load. Always enable HTTP/2 on your server if possible.</li>
<li><strong>Compression Headers</strong>:<br />
Use Brotli or GZIP compression on all text-based assets. This shrinks payloads and reduces download times. Always set up CSS, JS, and JSON compression headers on your server.</li>
<li><strong>Caching</strong>:<br />
Innovative caching strategies make a huge difference. Use browser cache, set up appropriate cache-control headers, and leverage caching solutions like Apollo Client for GraphQL data. The less you hit the network, the faster your app feels.</li>
<li><strong>Batch Requests</strong>:<br />
When possible, group similar network requests into a single batch. This reduces the number of round trips and makes better use of available bandwidth.</li>
<li><strong>Image Optimization</strong>:<br />
Don’t just serve original images. Use a microservice or cloud provider to compress and resize images on the fly. Always pull pictures at the exact size needed for the UI. This avoids wasting bytes on oversized assets.</li>
<li><strong>Bundle Splitting and Lazy Loading</strong>:<br />
Break your JavaScript into separate bundles for app code and vendor code. Only load what you need, when you need it. Lazy load heavy UI parts, like user profiles or the feed. This keeps initial loads fast and reduces unnecessary network requests.</li>
<li><strong>Compress Everything</strong>:<br />
Always compress your assets, whether you’re shipping JS, CSS, images, or data. Smaller files mean faster delivery and a snappier user experience.</li>
</ul>
<p>These optimizations work together to keep your app responsive, efficient, and scalable. When discussing network performance in interviews, focus on practical strategies like compression, caching, batching, and lazy loading. Mention how HTTP/2 and image optimization can unlock even more speed, especially for users on slow or unreliable connections.</p>
<hr />
<h3>Rendering Performance</h3>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-580" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.51-PM.png" alt="" width="988" height="634" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.51-PM.png 988w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.51-PM-300x193.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.51-PM-768x493.png 768w" sizes="(max-width: 988px) 100vw, 988px" /></p>
<p>Rendering is where users differentiate between a slow and a fast app. If your UI lags, jumps around, or doesn’t load content in the correct order, people notice immediately. Based on the diagram above, here are some actionable strategies to optimize rendering performance.</p>
<ul>
<li><strong>Server Side Rendering (SSR):</strong><br />
Rendering pages on the server can dramatically improve perceived speed. Tools like Next.js make SSR easier, help with SEO, and load critical content fast.</li>
<li><strong>Application Cache:</strong><br />
Use local storage, cookies, and session storage to avoid unnecessary re-renders and make your app feel snappier for repeat users.</li>
<li><strong>Handle States:</strong><br />
Always manage loading, error, and success states. Show skeleton screens or spinners to make the app feel responsive even before data arrives.</li>
<li><strong>Avoid Duplication and Race Conditions:</strong><br />
Fetch the same data only once, and handle concurrent requests to avoid weird bugs or flickering UIs.</li>
<li><strong>Mobile Friendly:</strong><br />
Design and test your rendering pipeline on real mobile devices, not just desktop emulators.</li>
<li><strong>Preload and Import Only What You Need:</strong><br />
Preload JavaScript bundles when necessary, and use dynamic imports to load only the code required for the visible view.</li>
<li><strong>Optimize Time to Interactive (TTI):</strong><br />
Track when the UI is first usable, and use metrics like First Contentful Paint (FCP) to log when key network requests start and end, and when components render with real data.</li>
<li><strong>Focus on Above the Fold Content:</strong><br />
Make sure the stuff users see first loads. Defer non-critical resources and prioritize above-the-fold content.</li>
<li><strong>Tree Shaking and Dead Code Elimination:</strong><br />
Remove unused code and bundles. Use tree shaking to ensure only what’s needed is shipped to the browser.</li>
<li><strong>Virtualization for Long Lists:</strong><br />
Only render visible items in large lists. Replace nodes instead of creating and destroying them for better scroll performance.</li>
<li><strong>CSS Optimization:</strong><br />
Avoid layout thrashing and reflows. Use CSS animations instead of JS, inline CSS in JS if it reduces render time, and keep class names simple.</li>
<li><strong>Rate Limiting, Debouncing, and Throttling:</strong><br />
For input events and scrolling, debounce or throttle handlers to avoid unnecessary renders and wasted computation.</li>
</ul>
<p>Rendering performance is about doing the minimum work needed to show the user what matters, as quickly as possible. Instrument your app to log key milestones, measure what actually renders, and always test your optimizations on both desktop and real mobile hardware. Prioritize smoothness and responsiveness at every step.</p>
<hr />
<h2>User Experience Optimizations</h2>
<h3>Mobile-Friendly Design</h3>
<ul>
<li>Ensure your application is responsive and mobile-friendly, considering various screen sizes and orientations.</li>
<li>Implement loaders, error states, and empty states to provide informative feedback to users.</li>
<li>Handle rendering images of different dimensions gracefully to maintain a cohesive user experience.</li>
</ul>
<h3>Network</h3>
<ul>
<li>Handle various network states, such as success, pending, and error states, to guide users through different stages of interactions.</li>
<li>Manage concurrent requests to prevent race conditions and avoid duplicate requests, especially after user actions like form submissions.</li>
<li>Consolidate requests using techniques like debounce, throttle, or rate limiting to minimize server load.</li>
<li>Leverage caching effectively to reuse previous responses and reduce the need for network round-trip.</li>
</ul>
<hr />
<h2>Accessibility (a11y)</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-581" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.58-PM.png" alt="" width="365" height="296" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.58-PM.png 365w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-09-15-at-2.40.58-PM-300x243.png 300w" sizes="(max-width: 365px) 100vw, 365px" /></p>
<ul>
<li>Implement keyboard navigation features, including a list of shortcuts, and ensure that tappable items are accessible via keyboard input.</li>
<li>Semantic HTML5 elements should be used, and ARIA roles, states, and properties should be added to enhance accessibility for users with disabilities.</li>
<li>Ensure proper color contrast and consider supporting dark mode for improved readability.</li>
<li>Design elements with various text sizes and multilingual support in mind.</li>
<li>Test your application for cross-device compatibility and edge cases.</li>
</ul>
<hr />
<h2>Security</h2>
<p><img decoding="async" src="https://cdn.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/https://cdn.filestackcontent.com/lZXZysNoRH6EUtIVynAC" data-imageloader="" data-imageloader-src="https://cdn.filestackcontent.com/lZXZysNoRH6EUtIVynAC" /></p>
<p>Security is a critical part of every front-end system design. Even if you build the fastest, smoothest UI, leaving security gaps can put your users and business at risk. Here are some of the most critical security measures for any modern frontend.</p>
<ul>
<li><strong>Cross-Site Scripting (XSS) Prevention:</strong><br />
Always sanitize any user-generated content before rendering it in the DOM. Never inject raw HTML from untrusted sources. Use built-in framework protections, and escape text in templates to avoid malicious scripts.</li>
<li><strong>Rate Limiting:</strong><br />
Protect your endpoints from abuse by limiting the number of requests that can be made from a single user or IP. Use server-side and, where applicable, client-side throttling to discourage brute force attacks and resource hogging.</li>
<li><strong>CORS (Cross-Origin Resource Sharing):</strong><br />
Configure CORS headers properly on your backend, allowing only trusted origins to access your APIs. Never use a wildcard <code>*</code> origin in production. Make sure credentials are handled securely if you’re using cookies or tokens.</li>
<li><strong>CSRF (Cross-Site Request Forgery) Protection:</strong><br />
Use anti-CSRF tokens on all state-changing requests. Modern frameworks and libraries provide built-in helpers for this.</li>
<li><strong>Authentication and Authorization:</strong><br />
Never trust client-side checks for sensitive actions. Ensure that every sensitive API call is authenticated and user permissions are validated on the server.</li>
<li><strong>Secure Storage:</strong><br />
Avoid storing sensitive tokens in <code>localStorage</code> or <code>sessionStorage</code> where possible. Prefer httpOnly, secure cookies for session tokens to protect against XSS.</li>
<li><strong>Content Security Policy (CSP):</strong><br />
Set strong CSP headers to prevent inline scripts and control what resources the browser can load. This can help stop many XSS attacks before they start.</li>
<li><strong>HTTPS Everywhere:</strong><br />
Always use HTTPS in production. Redirect all HTTP traffic to HTTPS to protect data in transit.</li>
<li><strong>Error Handling:</strong><br />
Never leak sensitive info in error messages sent to the frontend. Display user-friendly errors and log full details server-side only.</li>
<li><strong>Dependency Auditing:</strong><br />
Regularly audit your dependencies for known vulnerabilities. Use tools like <code>npm audit</code> or <code>yarn audit</code> as part of your CI pipeline.</li>
</ul>
<p>Front-end security is a layered approach: sanitize, validate, authenticate, and audit at every stage. These practices help protect your app and users from the most common threats in modern web development.</p>
<hr />
<p>That takes care of <strong>R.A.D.I.O</strong>, now let&#8217;s move on to real-world examples.</p>


---

## 8. Design Auto Complete Search

- Difficulty: 🟠 Medium
- Subtitle: Designing a scalable, flexible autocomplete component for various frontends.
- Video Link: https://youtu.be/Ntmy-z-b4pk?si=N7WygjzjVzo8tcbM
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-15-at-9.19.35-AM-1.png

### Content

<h1>Design Google Search</h1>
<p><iframe loading="lazy" title="Design Autocomplete / Typeahead - Frontend System Design Guide" width="500" height="281" src="https://www.youtube.com/embed/Ntmy-z-b4pk?feature=oembed" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></p>
<h3>Overview</h3>
<p>The objective is to design a versatile and scalable autocomplete component for frontend applications. This component must be engineered to be reusable across different projects and flexible enough to handle various data sources. It should accept a direct API endpoint or static data as input and render suggestions accordingly.</p>
<h3>Key Features</h3>
<ol>
<li>Flexibility in Data Sources: The component should be capable of handling different types of data inputs. It can be configured to fetch data from a provided API endpoint or to use an array of static data.</li>
<li>Customizable Rendering: The appearance and structure of the rendered suggestions should be customizable, allowing consumers to adapt the component to fit the design and functionality of their specific application.</li>
<li>Efficient Data Handling: When dealing with large datasets or dynamic data from an API, the component must efficiently manage data to ensure a smooth user experience, especially regarding response time and display.</li>
<li>Scalability: The component should be optimized for performance, ensuring it remains efficient and responsive even as the data size or the number of users grows.</li>
<li>Ease of Integration: It should be straightforward to integrate into existing projects, requiring minimal setup and configuration.</li>
<li>User Interaction and Accessibility: The component must be intuitive to use, with support for keyboard navigation and adherence to accessibility standards.</li>
</ol>
<h2>Solution</h2>
<p>Full Diagram can be found below:</p>
<p><img loading="lazy" decoding="async" class="alignnone wp-image-1557 size-full" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Autocomplete.svg" alt="" width="5460" height="1607" /></p>
<h3>Clarifying Questions</h3>
<p>Before designing and developing the autocomplete component, it&#8217;s crucial to address several clarifying questions. These questions help in understanding the specific requirements and expectations for the component, ensuring that the final product aligns with its users&#8217; needs and the technical constraints of the environments in which it will be used.</p>
<h3>Key Clarifying Questions</h3>
<ol>
<li>Results Support: What types of results should the autocomplete support? Should it cater to only text-based inputs, or include images, links, or multi-format data?</li>
<li>Device Compatibility: On which devices will this component be used? Does it need to be responsive and adaptable to various screen sizes and input methods (e.g., touch, mouse, keyboard)?</li>
<li>Fuzzy Search Capability: Is fuzzy search functionality required on the client side? For instance, should the component utilize algorithms like the Levenshtein distance to identify similarities between input strings and suggest results, even with minor typos or variations?</li>
<li>Data Source Flexibility: Should the component strictly rely on an API endpoint for data, or should we also support searching through client-side (local) data without making network requests?</li>
<li>Offline Usage: Should offline functionality be supported? If so, how should the component handle data fetching and caching for offline usage?</li>
<li>Performance and Scalability: What are the performance expectations regarding response time and scalability, especially when dealing with large datasets or high user traffic?</li>
<li>Customizability and Integration: How customizable should the component be regarding styling and integration with various frontend frameworks or libraries?</li>
</ol>
<p>Addressing these questions is crucial for developing a clear roadmap for a functional autocomplete component that aligns with the specific needs and constraints of its intended use cases.</p>
<h3>Functional Requirements</h3>
<ol>
<li>Plug-and-Play Capability: The component should be sufficiently generalized to integrate seamlessly into various environments or applications with minimal configuration.</li>
<li>Customizable UI: Both the input field and search results UI must be customizable, allowing users to tailor the look and feel to match their application’s design.</li>
<li>Data Source Versatility: The component must support both asynchronous data fetching (for API endpoints) and static data (client-side data), providing flexibility in how data is sourced and managed.</li>
</ol>
<h3>Non-Functional Requirements</h3>
<ol>
<li>Device and Screen Size Compatibility: The component should be responsive and supported across all devices and screen sizes.</li>
<li>Configurable Highlighting: Search result highlighting should be configurable, enhancing the user experience by making it easier to identify relevant suggestions.</li>
<li>API Flexibility: Support for both client-only and server-only API configurations, allowing for varied backend and frontend architectures.</li>
<li>Infinite Scrolling: Implementation of endless scrolling for search results, providing a seamless experience when dealing with large datasets.</li>
<li>Edge Case Handling: Robust handling of edge cases to ensure reliability and consistency in various scenarios.</li>
<li>Offline Usage: It is possible to read from a cache for offline usage, enabling functionality even without an active internet connection.</li>
<li>Comprehensive State Management: Proper handling of loading, error, and success states, ensuring clear communication of the component’s status to the user.</li>
<li>Accessibility (A11y) Support: Adherence to accessibility standards ensures the component is usable by as wide an audience as possible, including those with disabilities.</li>
<li>Internationalization: Support for internationalization, including integration with tools like Smartling and utilization of the HTML <code>lang</code> attribute, to cater to a global user base.</li>
<li>Best Practices: Adherence to industry best practices in coding, design, and user experience to ensure a high-quality, reliable, and user-friendly component.</li>
</ol>
<h2>High-Level Component Design</h2>
<p>The graphic depicts a structured approach to the autocomplete component design. Let&#8217;s break down the responsibilities of each element within this architecture.<br />
<img loading="lazy" decoding="async" class="alignnone size-full wp-image-586" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-15-at-9.08.12-AM.png" alt="" width="867" height="586" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-15-at-9.08.12-AM.png 867w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-15-at-9.08.12-AM-300x203.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-15-at-9.08.12-AM-768x519.png 768w" sizes="(max-width: 867px) 100vw, 867px" /></p>
<h3>View/UI Layer</h3>
<ul>
<li>Input UI: This is where the user interacts with the component, typically a text input field. It captures the user&#8217;s keystrokes and triggers search queries.</li>
<li>Results UI: This displays the search results dynamically according to the user type. It should update in real-time and allow the user to select from the suggested options.</li>
</ul>
<h3>Controller Layer</h3>
<ul>
<li>Controller: This acts as the intermediary between the View/UI and the data sources (Cache or Server). It processes user input, sends search queries, and retrieves results.</li>
</ul>
<h3>Data Management Layer</h3>
<ul>
<li>Cache: A temporary storage mechanism that holds previously fetched results to improve performance by reducing the number of server requests needed for repeated queries.</li>
<li>Server: The external data source, typically a backend API, where queries are sent to fetch results that are not available in the Cache.</li>
</ul>
<p>The Controller plays a pivotal role in this architecture. It must intelligently decide when to use cached results versus when to make a new query to the Server. It should also manage the state of the UI, displaying loading indicators or error messages as appropriate.</p>
<p>The Results UI is directly connected to the Controller, ensuring that the display of suggestions is updated promptly as new data is available. Similarly, the Input UI must communicate user input to the Controller without delay, providing a smooth and responsive experience.</p>
<p>This high-level design ensures that the autocomplete component is modular, with clear separation of concerns, facilitating maintenance and scalability.</p>
<h2>Data Model Design</h2>
<p>This segment will discuss the data types and their roles in the autocomplete component. This will clearly explain how data is structured, managed, and utilized within the system.</p>
<pre><code>
type NetworkContext = {
    url: String,
    resultsKey: Optional[str] // default results['data']
    pagination: Optional[PaginationContext],
    retryCount: Optional[int],
    timeoutDuration: Optional[int]
}
type PaginationContext = {
    type: Optional[Enum] // &lt;offset, cursor, none&gt;,
    page: Optional[int] // start page
    limit: Optional[int] // limit number of results
    nextCursor: Optional[int] // start cursor,
}
type ActionType = {
    type: 'deeplink' | 'expand',
    url: str,
    otherMetadata...
}
type AutoCompleteResult = {
    title: Optional[String],
    subtitle: Optional[String],
    avatar: Optional[String],
    actionType: Optional[ActionType]
}
type ClientContext = {
    results: List[AutoCompleteResult],
    pagination: Optional[PaginationContext]
}
type CacheContext = {
    type: Optional['network only' | 'network &amp; cache' | 'cache'] = None
}
type AutoCompleteProps = {
    // Data
    dataContext: Optional[NetworkContext | ClientContext]
    onFetchedResults: Optional[Promise&lt;results, (page &amp; limit) or cursor&gt;]
    minSearchLength: Optional[int]
    // cache
    cacheContext: Optional[CacheContext]
    // interactions
    onChange: Optional[EventHandler] // on text change
    onFocus: Optional[EventHandler] // on text focus
    onBlur: Optional[EventHandler] // on text blur
    onSelect: Optional[EventHandler[Row]] // on selecting a specific row
    // styling
    style: Optional[StyleObj]
    className: Optional[str]
    resultsRenderer: Optional[Function | JSX]
    truncateLongStrings: Optional[Bool]
    shouldAutofocus: Option[Bool]
    // debounce
    debounce: Optional[Bool]
    debounceDuration: Optional[int]
    minQueryLength: Optional[int]
}
</code></pre>
<h3>NetworkContext</h3>
<ul>
<li>url: The endpoint URL for the API where the search queries will be sent.</li>
<li>resultsKey: A key to extract the results from the API response. Defaults to <code>results['data']</code> if not specified.</li>
<li>pagination: An optional object of <code>PaginationContext</code> type for handling pagination of results.</li>
<li>retryCount: An optional integer defining how many times a failed request should be retried.</li>
<li>timeoutDuration: An optional integer specifying the timeout duration for the network request in milliseconds.</li>
</ul>
<h3><code>PaginationContext</code></h3>
<ul>
<li>type: An optional enumeration defining the pagination strategy (offset, cursor, none).</li>
<li>page: An optional integer indicating the starting page number for pagination.</li>
<li>limit: An optional integer defining the maximum number of results to be returned.</li>
<li>nextCursor: An optional integer used as a cursor for the next set of results, typically in cursor-based pagination.</li>
</ul>
<h3><code>ActionType</code></h3>
<ul>
<li>type: Specifies the action type, like &#8216;deeplink&#8217; for redirecting or &#8216;expand&#8217; for additional UI interaction.</li>
<li>url: A string URL to be used in conjunction with the action type.</li>
<li>otherMetadata: Additional metadata that might be required for the action.</li>
</ul>
<h3><code>AutoCompleteResult</code></h3>
<ul>
<li>title: An optional string for the main text of a result.</li>
<li>subtitle: An optional string for secondary text.</li>
<li>avatar: An optional string URL for an image associated with the result.</li>
<li>actionType: An optional <code>ActionType</code> defining what action occurs when a result is selected.</li>
</ul>
<h3><code>ClientContext</code></h3>
<ul>
<li>results: A list of <code>AutoCompleteResult</code> objects, which are used to render each result row in the UI.</li>
<li>pagination: An optional <code>PaginationContext</code> for managing client-side pagination.</li>
</ul>
<h3><code>CacheContext</code></h3>
<ul>
<li>type: An optional enumeration to define the caching strategy, such as &#8216;network only&#8217;, &#8216;network &amp; cache&#8217;, or &#8216;cache&#8217;.</li>
</ul>
<h3><code>AutoCompleteProps</code></h3>
<ul>
<li>dataContext: An optional union type of either <code>NetworkContext</code> or <code>ClientContext</code>, allowing the consumer to specify if they are using an API or static data.</li>
<li>onFetchedResults: An optional promise that fetches results data from the API, with the consumer having the option to process this data.</li>
<li>minSearchLength: An optional integer that determines the minimum search length before fetching results.</li>
<li>cacheContext: An optional <code>CacheContext</code> detailing the caching strategy.</li>
<li>onChange, onFocus, onBlur, onSelect: Optional event handlers for various user interactions with the input field.</li>
<li>style: An optional <code>StyleObj</code> for CSS-in-JS styling.</li>
<li>className: An optional string for CSS class name.</li>
<li>resultsRenderer: An optional function or JSX to allow the consumer to render custom UI in the results.</li>
<li>truncateLongStrings: An optional boolean to truncate long strings in the search results.</li>
<li>shouldAutofocus: An optional boolean to determine if the input field should be auto-focused on page render.</li>
<li>debounce: An optional boolean to decide if keystrokes should be debounced.</li>
<li>debounceDuration: An optional integer specifying the debounce duration for keystrokes.</li>
</ul>
<p>These data models provide the foundation for a robust, flexible, and customizable autocomplete component. They ensure that the element can be tailored to a wide range of use cases and efficiently handle various data types and interactions.</p>
<h2>Expected API Request and Response</h2>
<h3>API Request</h3>
<p>When the autocomplete component requests data from the server, it typically sends query parameters to fetch relevant suggestions based on the user&#8217;s input. For an offset-based pagination, it may include parameters like <code>page</code> and <code>limit</code>, whereas for cursor-based pagination, it might send the <code>nextCursor</code> and <code>limit</code>. These are sent as part of the HTTP request, usually as a GET request, to the API endpoint specified in the <code>NetworkContext</code>.</p>
<h3>API Response</h3>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-587" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-13-at-6.12.08-PM.png" alt="" width="563" height="279" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-13-at-6.12.08-PM.png 563w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-11-13-at-6.12.08-PM-300x149.png 300w" sizes="(max-width: 563px) 100vw, 563px" /></p>
<p>The server response expected by the autocomplete component is a JSON object structured to include pagination details and a list of result items. The structure is as follows:</p>
<ul>
<li>page: (int) The current page number of results, used for offset-based pagination.</li>
<li>limit: (int) The number of results per page or request.</li>
<li>total: (int) The total number of results available for offset-based pagination.</li>
<li>hasNextPage: (bool) A flag indicating whether there are more pages to fetch, used for offset-based pagination.</li>
<li>nextCursor: (uuid) A unique identifier used to fetch the next set of results in cursor-based pagination.</li>
</ul>
<p>Nested within the response is a list of results prefixed by a key (e.g., &#8216;some.pre.fix&#8217;). Each item in the list is an object representing an individual result, with the following attributes:</p>
<ul>
<li>title: (str) The main text of a suggestion.</li>
<li>subtitle: (str) A secondary text providing additional information.</li>
<li>avatar: (str) A URL to an image associated with the suggestion.</li>
<li>Action: (str) The type of action to perform on selecting the suggestion, such as &#8216;deeplink&#8217;.</li>
<li>url: (str) The URL to which the &#8216;deeplink&#8217; action will navigate.</li>
</ul>
<p>The components <code>Controller</code> will parse this response, extracting the relevant data based on the <code>resultsKey</code> specifications in the <code>NetworkContext</code>. It will then update the <code>Results UI</code> accordingly.</p>
<p>For example, if the <code>resultsKey</code> is set to <code>'some.pre.fix'</code>, the controller will look for this key in the JSON response and render the associated results list.</p>
<h2>Handling Edge Cases, Caching, and Offline Usage</h2>
<h3>Edge Cases</h3>
<h4>1. Handling Concurrent Requests/Race Conditions</h4>
<p>The autocomplete component should implement a strategy to manage concurrent requests to ensure that it displays results for the most recent user input and not necessarily the latest response received. Due to network latency, the latter may not correspond to the latest query.</p>
<p>Given the presence of a cache system, maintaining a map of results keyed by the search query string is the preferred method. This approach allows the component to present results matching the current input value, even if the responses arrive out of order. It efficiently leverages the cache by referencing past search queries, avoiding unnecessary network requests.</p>
<h4>2. Offline Usage</h4>
<p>For offline scenarios, the component can enhance user experience by:</p>
<ul>
<li>Relying solely on cached results when no network connection is available. While this limits the results to previously searched terms, it provides some functionality without a live connection.</li>
<li>Preventing network requests to save CPU cycles and battery life.</li>
<li>Indicating within the UI that the component is offline to set appropriate user expectations.</li>
</ul>
<h3>Cache Strategies</h3>
<h4>1. Hash Map Cache</h4>
<p>A hash map with the search query as the key and results as the value is a straightforward approach. However, if not appropriately managed, it can lead to duplicate entries.</p>
<p>Example:</p>
<pre class="ql-syntax" spellcheck="false"><code>const cache = {
  go: [
    { type: 'business', text: 'goggie' },
  ],
  goog: [
    { type: 'business', text: 'goggie' },

    { type: 'business', text: 'google' },
  ],
}</code></pre>
<h4>2. List of Results</h4>
<p>Storing results as a list can lead to inefficiencies in search time (O(n)) due to the need to filter through all results to find matches.</p>
<p>Example:</p>
<pre><code>const results = [
  { type: 'business', text: 'goggie' },
  { type: 'business', text: 'google' },
];</code></pre>
<h4>3. Normalized Store</h4>
<p>A normalized store, where each result is stored once and referenced by IDs in search query arrays, is the most efficient and scalable option, especially for applications with longer sessions and more extensive data.</p>
<p>Example:</p>
<pre><code>{
 'results': {
    1: { id: 1, type: 'business', text: 'goggie' },
    2: { id: 2, type: 'business', text: 'google' },
 },
 'searches': {
    go: [1],
    goo: [1,2],
 }
}</code></pre>
<p>Which Cache Structure to Use?</p>
<ul>
<li>The first option may suffice for short-lived websites or sessions due to its simplicity.</li>
<li>Due to its efficient storage and retrieval, the normalized store is the best approach for long-lived websites or applications with extensive and repetitive use, like Facebook.</li>
</ul>
<h2>Implementing Infinite Scrolling</h2>
<p>Infinite scrolling is a crucial feature for modern web applications, particularly for components like autocomplete, which can potentially display many results. It provides a better user experience by loading data as needed, without overwhelming the user with excessive information at once.</p>
<h3>Infinite Scrolling Strategies</h3>
<h4>1. Cursor-Based Pagination</h4>
<p>Cursor-based pagination is advantageous for real-time applications where the dataset is continuously changing. It fetches the next set using a pointer to the last item in the results.</p>
<p>Pros:</p>
<ul>
<li>It allows for a seamless continuation of the data stream, which is ideal for real-time updates.</li>
</ul>
<p>Cons:</p>
<ul>
<li>The inability to jump to a specific page can limit users&#8217; ability to navigate to a known position in the list.</li>
</ul>
<p>Example Request and Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>Request:
{
    "cursor": "some cursor",
    "size": 10
}


Response:
"pagination": {
   "size": 10,
   "next_cursor": "some next cursor"
}</code></pre>
<h4>2. Offset-Based Pagination</h4>
<p>Offset-based pagination is a suitable option for applications where jumping to specific pages is necessary. It&#8217;s straightforward and uses page numbers and size to fetch data.</p>
<p>Pros:</p>
<ul>
<li>Easy implementation and direct navigation to any page.</li>
</ul>
<p>Cons:</p>
<ul>
<li>Potential performance issues with large datasets, as SQL queries become more expensive with higher offsets.</li>
</ul>
<p>Example Request and Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>Request:
{
    "page": 1,
    "limit": 10
}


Response:
"pagination": {
   "size": 10,
   "page": 1,
   "next_page": true,
   "total_pages": 100
}</code></pre>
<h3>Scroll Behavior Implementation</h3>
<h4>Intersection Observer</h4>
<p>This modern API allows performant asynchronous tracking of the intersection between an element and its ancestor elements or the viewport.</p>
<p>Advantages:</p>
<ul>
<li>It runs on a secondary thread, which ensures the main thread is not blocked.</li>
<li>It&#8217;s inherently performant and built for purposes like infinite scrolling.</li>
</ul>
<p>Usage:</p>
<ul>
<li>A loading node is observed, and new items are fetched and rendered when it comes into view.</li>
<li>A threshold can trigger loading before the node is in view, providing a smoother experience.</li>
</ul>
<h4>Window.Scroll</h4>
<p>This more traditional approach offers greater configurability but requires additional custom code to achieve performance comparable to the Intersection Observer.<br class="softbreak" /><br class="softbreak" />Also, consider using virtualization, which means recycling dom nodes.</p>
<h2>Debouncing to Reduce Server Load on Change</h2>
<p>When designing interactive components, such as an autocomplete widget, it&#8217;s essential to consider the frequency at which user actions trigger data requests. Every keystroke in an autocomplete field could send a request to the server for matching results. If not managed properly, this can result in a significant performance bottleneck due to the high volume of requests, leading to an overburdened server and a laggy user experience.</p>
<p>To mitigate this, a common strategy employed is debouncing. Debouncing is a programming technique that prevents time-consuming tasks from being executed too frequently, which can harm performance or user experience. In the context of an autocomplete component, debouncing means waiting for a certain amount of time after the last keystroke before sending a request to the server. Suppose the user types another character; the timer resets. This way, we only send a request after the user has stopped typing for a predetermined time, rather than on every keystroke.</p>
<p>Benefits of Debouncing:</p>
<ul>
<li>Reduced Server Load: By limiting the number of requests sent to the server, debouncing reduces the load, helping prevent server overload, especially during peak usage times.</li>
<li>Improved User Experience: Debouncing minimizes the lag between user actions and the application&#8217;s responses, ensuring the application remains responsive and fluid.</li>
<li>Lowered Network Traffic: Fewer requests mean less data being sent over the network, which can reduce costs and improve performance for users on slower internet connections.</li>
<li>Avoidance of Race Conditions: Debouncing can also help mitigate the risks of race conditions, where the server might return responses out of sequence, by reducing the number of requests.</li>
</ul>
<p>Implementation Considerations:</p>
<ul>
<li>Timing: The debounce duration should be chosen carefully to ensure optimal performance. If it is too short, you may not be able to significantly reduce the load; if it is too long, the user experience may suffer due to perceptible delays in response.</li>
<li>User Behavior: Considering user behavior is crucial when setting the debounce time. For example, if users typically type quickly, a slightly longer debounce time might be appropriate to ensure that the system responds when they have likely finished typing a thought.</li>
<li>Feedback: During the debounce delay, it&#8217;s essential to provide visual feedback, such as a loading spinner, to indicate that the application is processing the user&#8217;s input.</li>
</ul>
<p>By incorporating a debounce strategy, the autocomplete component becomes more scalable and efficient, effectively reducing unnecessary server load while maintaining a smooth user experience.</p>
<h2>Accessibility and Best Practices</h2>
<h3>Accessibility (A11y)</h3>
<p>Ensuring that the autocomplete component is accessible is paramount. Accessibility features enable users with disabilities to navigate and interact with web content effectively. Here are some key accessibility practices to implement:</p>
<ul>
<li>Semantic HTML: Use semantic HTML tags to convey meaning and structure. For instance, <code>&lt;input&gt;</code> for input fields, <code>&lt;ul&gt;</code> for lists of results, and <code>&lt;li&gt;</code> for individual items.</li>
<li class="ql-indent-1">ARIA Labels and Roles: Implement ARIA (Accessible Rich Internet Applications) attributes to enhance the accessibility of UI components that cannot be adequately described with HTML alone. For example:<code>role="listbox"</code> For the container that holds the list of results to inform assistive technologies that it contains selectable options.</li>
<li class="ql-indent-1"><code>role="combobox"</code> for the input field to indicate that it is a composite widget that allows both input and selection.</li>
<li class="ql-indent-1"><code>aria-autocomplete="both"</code> to suggest that the combobox provides suggestions that complete the typed text and enable the user to select from pre-defined options.</li>
<li>Tab Index: Ensure the tab order is logical and intuitive, allowing users to navigate the component using the keyboard.</li>
<li>High Contrast: Design with high contrast ratios to make text and UI elements stand out, especially for users with visual impairments.</li>
<li>Dark Mode Support: Offer a dark mode version of the component to reduce eye strain and accommodate user preferences for a darker color scheme.</li>
</ul>
<h3>Best Practices</h3>
<p>Beyond accessibility, adhering to best practices in web development can vastly improve the autocomplete component&#8217;s performance, maintainability, and security.</p>
<ul>
<li>Minification: Minify CSS and JavaScript files to reduce size and improve load times and performance.</li>
<li>Lazy Loading: Implement lazy loading for code and images, which defers the loading of non-critical resources until page load time and loads them only when needed.</li>
<li>Bundle Splitting: Use bundle splitting to break down a large JavaScript bundle into smaller chunks that can be loaded on demand, reducing the initial load time.</li>
<li>Tree Shaking: Employ tree shaking to eliminate unused code from your final bundle, ensuring that only the necessary code is included.</li>
<li>Testing: Write unit and integration tests to catch bugs early and ensure that individual components and their interactions work as intended.</li>
<li>Observability: Implement monitoring and logging to observe the component&#8217;s performance in real-time, which aids in debugging and optimizing the component.</li>
<li>Security: Sanitize user input to secure the component against common web vulnerabilities, such as Cross-Site Scripting (XSS). Ensure proper handling of Cross-Origin Resource Sharing (CORS) policies to prevent unauthorized access to resources.</li>
</ul>
<p>Incorporating these accessibility and best practice guidelines will result in a robust, user-friendly, and secure autocomplete component that can be reliably integrated into any web application.</p>
<p>In conclusion, design and implement a general-purpose, scalable, and reusable front-end autocomplete component. Each article segment builds upon the previous one, forming a cohesive blueprint for a practical user interface element.</p>


---

## 9. Design Chat App

- Difficulty: 🔴 Hard
- Subtitle: Designing chat apps with real-time messaging and offline support.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.51.59-AM.png

### Content

<h1>Design Chat Application &#8211; Frontend System Design Guide</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-591" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.53.19-AM.png" alt="" width="492" height="360" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.53.19-AM.png 492w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.53.19-AM-300x220.png 300w" sizes="(max-width: 492px) 100vw, 492px" /></p>
<h2>Requirements</h2>
<h3>Functional</h3>
<p>You provided the following main functional requirements:</p>
<ol>
<li class="">Real-time sending and receiving of messages across devices.</li>
<li class="">Offline support: Messages sent offline should be stored and then sent when the user comes back online.</li>
</ol>
<p>Clarifying Questions:</p>
<ol>
<li class="">Is there any authentication required for users?
<ol type="a">
<li class="">Assume users are authenticated.</li>
</ol>
</li>
<li class="">Do we need features like message read indicators, typing indicators, or group chats?
<ol type="a">
<li class="">If we have time at the end, right now, out of scope.</li>
</ol>
</li>
<li class="">What about media messages, like images, videos, or files?
<ol type="a">
<li class="">If we have time at the end, right now, out of scope.</li>
</ol>
</li>
<li class="">Is message history preserved indefinitely, or is there some sort of retention policy?
<ol type="a">
<li class="">We will leave that up to you to follow best practices.</li>
</ol>
</li>
<li class="">How should notifications be handled?
<ol type="a">
<li class="">Out of scope right now.</li>
</ol>
</li>
</ol>
<h3>Non-Functional</h3>
<ol>
<li class="">Observability: Given that every user might send or receive messages multiple times a day, and if there are thousands or even millions of users, the log volume can be substantial. Depending on the volume, logs can contribute significantly to the costs. Consider storing logs selectively or aggregating them. Monitoring and alerting should be in place for the chat system&#8217;s health and performance metrics.</li>
<li class="">Devices: To be clarified. (Assuming web for desktop and mobile as well as native mobile apps for iOS and Android.)</li>
<li class="">Demographics: Given that it&#8217;s a chat application, it&#8217;s safe to assume a global audience unless specified.</li>
<li class="">Accessibility: The application should follow web accessibility standards like WCAG. Features like screen reader support, high contrast mode, keyboard accessibility, etc., should be integrated.</li>
<li class="">Performance: Users expect real-time applications to be fast and responsive. Latency should be minimized, especially in message delivery.</li>
</ol>
<h2>High-Level Architecture Design</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-592" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.51.59-AM.png" alt="" width="808" height="675" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.51.59-AM.png 808w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.51.59-AM-300x251.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-13-at-9.51.59-AM-768x642.png 768w" sizes="(max-width: 808px) 100vw, 808px" /></p>
<h3>MVC Model</h3>
<p>Model: Represents the data structures and the business logic.</p>
<ul>
<li class="">User Data: Includes user credentials, JWT tokens, and user profile data.</li>
<li class="">Chat Data: Conversations and messages associated with each user.</li>
</ul>
<p>View: Represents the UI of the application.</p>
<ul>
<li class="">Conversations Screen: List of ongoing conversations.</li>
<li class="">Conversation Detail Screen: Detailed view of a single conversation with messages.</li>
</ul>
<p>Controller: Manages the data flow into the model object and updates the view whenever data changes.</p>
<ul>
<li class="">Handles user input, server responses, and data persistence.</li>
</ul>
<h3>Communication with the Server</h3>
<p>We&#8217;d primarily be using WebSockets for real-time bidirectional communication. WebSockets are chosen for instant message sending/receiving without the overhead of repeatedly establishing connections, which would be the case in HTTP long-polling.</p>
<p><strong>Data Flow:</strong></p>
<ol>
<li class="">User logs in, and after successful authentication, receives a JWT.</li>
<li class="">The client establishes a WebSocket connection using the JWT for authentication.</li>
<li class="">For offline messages, the client stores them locally. Once back online, the client sends these messages over the WebSocket.</li>
<li class="">The server processes the incoming messages, persists them, and broadcasts to the intended recipient(s).</li>
</ol>
<p>On the Conversations Screen, when a new message arrives, the respective conversation bubbles up. On the Conversation Detail Screen, new messages appear in real-time.</p>
<ol>
<li class="">A &#8220;User&#8221; box sends an &#8220;Authenticate&#8221; action to a &#8220;Server&#8221; box.</li>
<li class="">The &#8220;Server&#8221; box responds with &#8220;JWT.&#8221;</li>
<li class="">The &#8220;User&#8221; box initiates &#8220;WebSocket Connection&#8221; to the &#8220;Server&#8221; box, which is authenticated using the JWT.</li>
<li class="">Bi-directional arrows represent ongoing &#8220;Message Exchange&#8221; between the &#8220;User&#8221; box and the &#8220;Server&#8221; box over the WebSocket.</li>
</ol>
<h3>Device Support</h3>
<p>Given the requirements and the usual expectations for such applications:</p>
<ul>
<li class="">Web: Progressive Web Application (PWA) to support both desktop and mobile browsers. PWAs can also provide offline capabilities using service workers.</li>
<li class="">Mobile: Native apps for iOS and Android. They provide better integration with device capabilities and can utilize local storage for offline message support.</li>
</ul>
<p>The high-level architecture gives an overview of the structure and data flow of our chat application.</p>
<h2>Handling Infinite Scrolling in our API</h2>
<h3>Offset-based Pagination:</h3>
<ul>
<li class="">Uses a numeric offset to skip a fixed number of records.</li>
<li class="">Can be inefficient for large datasets because databases might scan from the start of the table to the offset.</li>
<li class="">In a real-time chat scenario, if new messages are inserted at the start (newer messages), the offset can skip or duplicate messages, leading to a poor user experience.</li>
</ul>
<h3>Cursor-based Pagination:</h3>
<ul>
<li class="">Uses a &#8220;cursor&#8221; (often a unique ID or a timestamp) to navigate through records.</li>
<li class="">More efficient for databases since they can jump directly to a record.</li>
<li class="">Handles real-time data more gracefully. Even if new messages are added, using a unique ID or timestamp as a cursor ensures users won&#8217;t see duplicates or miss messages.</li>
<li class="">Well-suited for frequently updated datasets, like real-time chat messages.</li>
</ul>
<p>Given the advantages of cursor-based pagination, especially in the context of a real-time chat application, I&#8217;d recommend using it.</p>
<p><strong>Intersection Observer vs Scroll Based</strong></p>
<p>We should use intersection observer due to it&#8217;s performant nature (not running on the main thread) vs using window.scroll and having to debounce and customize it.</p>
<h2>API Design</h2>
<p>Given the real-time nature of the application, the primary communication will be over WebSockets. However, we&#8217;ll also need some HTTP-based endpoints for the initial setup, like authentication.</p>
<h3>Protocol</h3>
<ul>
<li>HTTP/HTTPS: For authentication and initial setup. HTTPS ensures encrypted and secure data transfer.</li>
<li>WebSockets (over TLS for encryption, <code>wss</code>): For real-time bidirectional communication between the client and server.</li>
</ul>
<h3><strong>Authentication</strong></h3>
<p>To log a user in and receive a JWT.</p>
<p>Endpoint:</p>
<pre><code>/api/auth/login</code></pre>
<p>Method:</p>
<pre><code>POST</code></pre>
<p>Request:</p>
<pre class="ql-syntax" spellcheck="false"><code>{ "username": "exampleUser", "password": "examplePass" } </code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{ "token": "jwtTokenStringHere", "user": { "id": "user123", "name": "Alice" } } </code></pre>
<h3><strong>Get Conversations</strong></h3>
<p>Retrieve a list of conversations for a user.</p>
<p>Endpoint:</p>
<pre><code>/api/conversations</code><code>?afterId=cnv123&amp;limit=10</code></pre>
<p>Method:</p>
<pre><code>GET</code></pre>
<p>Headers:</p>
<pre class="ql-syntax" spellcheck="false"><code>Authorization: Bearer jwtTokenStringHere </code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
    "conversations": [
        {
            "id": "conv1",
            "lastMessage": {
                "id": "msg567",
                "content": "How are you?",
                "timestamp": 1676543289
            },
            "participants": ["user123", "user456"]
        },
        // ... other conversations
    ]
}</code></pre>
<h3><strong>Get Messages for a Conversation</strong></h3>
<p>Retrieve messages for a specific conversation.</p>
<p>Endpoint:</p>
<pre><code>/api/conversations/:conversationId/messages?afterId=msg123&amp;limit=10</code></pre>
<p>Method:</p>
<pre><code>GET</code></pre>
<p>Headers:</p>
<pre class="ql-syntax" spellcheck="false"><code>Authorization: Bearer jwtTokenStringHere</code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
    "messages": [
        {
            "id": "msg124",
            "content": "Hey!",
            "senderId": "user456",
            "timestamp": 1676543290
        },
        // ... other messages
    ]
}</code></pre>
<h3><strong>Send a Message</strong></h3>
<p>Send a message within a conversation.</p>
<p>Endpoint:</p>
<pre><code>/api/conversations/:conversationId/messages</code></pre>
<p>Method:</p>
<pre><code>POST</code></pre>
<p>Headers:</p>
<pre class="ql-syntax" spellcheck="false"><code>Authorization: Bearer jwtTokenStringHere </code></pre>
<p>Request:</p>
<pre class="ql-syntax" spellcheck="false"><code>{ "content": "Hi there!" } </code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
    "message": {
        "id": "msg789",
        "content": "Hi there!",
        "senderId": "user123",
        "timestamp": 1676543390
    }
}</code></pre>
<h3><strong>Update Message Status</strong> (for offline handling)</h3>
<p>When the client comes back online and wants to update the status of messages that were sent offline.</p>
<p>Endpoint: <code>/api/messages/:messageId/status</code></p>
<p>Method: <code>PUT</code></p>
<p>Headers:</p>
<pre class="ql-syntax" spellcheck="false"><code>Authorization: Bearer jwtTokenStringHere </code></pre>
<p><br class="softbreak" />Request:</p>
<pre class="ql-syntax" spellcheck="false"><code>{ "isSent": true } </code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
    "message": {
        "id": "msg789",
        "isSent": true
    }
}</code></pre>
<h2>Client Data Model</h2>
<h3>Data Types</h3>
<pre class="ql-syntax" spellcheck="false"><code>interface User {
    id: string;
    name: string; // This can include other fields like avatar, status, etc.
}


interface Message {
    id: string;
    content: string;
    senderId: string; // Reference to User's ID
    timestamp: number; // POSIX timestamp for message time
    isSent: boolean;   // Indicates if the message was sent (useful for offline scenarios)
}


interface Conversation {
    id: string;
    lastMessageId: string; // ID of the last message in the conversation for easy retrieval and ordering
    participantIds: string[]; // IDs of the participants
}</code></pre>
<h3>Client Store</h3>
<pre class="ql-syntax" spellcheck="false"><code>interface ClientStore {
    users: { [id: string]: User };               // Dictionary of users
    messages: { [id: string]: Message };        // Dictionary of messages
    conversations: { [id: string]: Conversation }; // Dictionary of conversations
    currentConversationId: string | null;       // The ID of the currently selected conversation
}</code></pre>
<p>Explained:</p>
<ul>
<li><code>users</code>: A dictionary of all users the client knows about. Each user can be fetched using their <code>id</code>.</li>
<li><code>messages</code>: All messages are stored in a dictionary. This makes it easy to fetch a specific message and also helps in ensuring each message is stored only once, even if it&#8217;s part of multiple conversations.</li>
<li><code>conversations</code>: Conversations are stored in a dictionary as well. For each conversation, we store participant IDs and the ID of the last message. This helps in ordering conversations based on the latest message.</li>
<li><code>currentConversationId</code>: This field helps in tracking which conversation is currently being viewed or acted upon by the user.</li>
</ul>
<p>The above model makes it easy to fetch specific entities (users, messages, conversations) by their IDs, ensuring efficient updates and minimal redundancy. Also, using TypeScript provides the added advantage of type-safety, making it easier to manage and less prone to errors.</p>
<h2>Optimizations</h2>
<h4>Virtualization</h4>
<p>Given that a user can have many messages in a conversation, rendering all of them can affect performance. Virtualization techniques, like using a library such as <code>react-virtualized</code> or <code>react-window</code>, allow us to render only the messages visible in the viewport, boosting performance. This is particularly useful for the chat messages view.</p>
<p>Trade-offs:</p>
<ul>
<li>Pros: Reduced DOM nodes and improved performance, especially for long chat histories.</li>
<li>Cons: Complexity in implementation, especially with dynamic message heights. Scroll behavior might feel a bit different from native scrolling for some users.</li>
</ul>
<h3>Debouncing/Throttle</h3>
<p>To improve the user experience and reduce the number of unnecessary operations:</p>
<ul>
<li>Debounce the search or filter operations in the conversation list. If a user is quickly typing in a search bar to find a specific conversation, you want to wait until they&#8217;ve stopped typing for a brief moment before executing the search.</li>
<li>Throttle real-time updates to the UI. If many messages are coming in rapid succession, you might choose to batch these updates slightly, so the UI isn&#8217;t constantly re-rendering.</li>
</ul>
<p>Trade-offs:</p>
<ul>
<li>Pros: Reduces the number of operations, API calls, or renders, improving efficiency.</li>
<li>Cons: Might introduce a tiny lag in UI updates (especially with debouncing), but this is generally acceptable for the improved efficiency.</li>
</ul>
<h3>Caching</h3>
<p>Storing frequently accessed data locally (like recent conversations or messages) can vastly improve performance. Tools like <code>IndexedDB</code> can be used for this purpose, especially considering the offline support requirement.</p>
<p>Trade-offs:</p>
<ul>
<li>Pros: Rapid data retrieval, reduced API calls, and improved offline experience.</li>
<li>Cons: Need to manage cache invalidation, and there&#8217;s potential for displaying stale data if not managed correctly.</li>
</ul>
<h3>Normalization</h3>
<p>Using normalized vs. non-normalized data for caching largely depends on the specific use case and the operations you perform on the data. Let&#8217;s first discuss the pros and cons of each approach before diving into the code examples:</p>
<ol>
<li class="ql-indent-1">Advantages:Reduces redundancy: Only one copy of each piece of data.</li>
<li class="ql-indent-1">Ensures consistency: When an item is updated, there&#8217;s only one place to update, so all references stay consistent.</li>
<li class="ql-indent-1">Can be more efficient in storage when there&#8217;s a lot of redundant data.</li>
<li class="ql-indent-1">Disadvantages:Reading operations might be a bit complex because you&#8217;d need to reconstruct data from various references.</li>
</ol>
<h3>Non-Normalized</h3>
<ol>
<li class="ql-indent-1">Advantages:Simplifies read operations: You get the entire structure as-is, without needing to reconstruct it.</li>
<li class="ql-indent-1">Faster for use cases where reading is more frequent than writing.</li>
<li class="ql-indent-1">Disadvantages:Redundant data can lead to inconsistencies. If data is updated in one place, it might still be outdated in another.</li>
<li class="ql-indent-1">Might consume more storage.</li>
</ol>
<p>For a chat application, given the frequency of reading operations (e.g., displaying messages) and the potential complexity of chat structures (nested messages, references to users, etc.), normalized data can be a good choice for cache.</p>
<p>Let&#8217;s consider a simple scenario where you want to store conversations with messages:</p>
<p><strong>Non-Normalized:</strong></p>
<pre class="ql-syntax" spellcheck="false"><code>interface User {
    id: string;
    name: string;
}

interface Message {
    id: string;
    content: string;
    sender: User;
}

interface Conversation {
    id: string;
    participants: User[];
    messages: Message[];
}

// Example of non-normalized data:
const conversation: Conversation = {
    id: "conv1",
    participants: [
        { id: "user1", name: "Alice" },
        { id: "user2", name: "Bob" }
    ],
    messages: [
        { id: "msg1", content: "Hi Bob!", sender: { id: "user1", name: "Alice" } },
        { id: "msg2", content: "Hey Alice!", sender: { id: "user2", name: "Bob" } }
    ]
};</code></pre>
<p><strong>Normalized Data Example</strong></p>
<pre class="ql-syntax" spellcheck="false"><code>interface User {
    id: string;
    name: string;
}


interface Message {
    id: string;
    content: string;
    senderId: string; // Reference to User
}


interface Conversation {
    id: string;
    participantIds: string[]; // Reference to Users
    messageIds: string[];     // Reference to Messages
}


const users: { [key: string]: User } = {
    "user1": { id: "user1", name: "Alice" },
    "user2": { id: "user2", name: "Bob" }
};


const messages: { [key: string]: Message } = {
    "msg1": { id: "msg1", content: "Hi Bob!", senderId: "user1" },
    "msg2": { id: "msg2", content: "Hey Alice!", senderId: "user2" }
};


const conversation: Conversation = {
    id: "conv1",
    participantIds: ["user1", "user2"],
    messageIds: ["msg1", "msg2"]
};</code></pre>
<p>In the non-normalized example, all data is directly embedded in the <code>Conversation</code> structure. In the normalized version, we have separate dictionaries (or maps) for users and messages, and we reference them by IDs in the conversation.</p>
<p>For the chat application, the normalized approach can help in ensuring that when a user&#8217;s details (e.g., name) change, they&#8217;re updated consistently across all conversations and messages without redundancy.</p>


---

## 10. Design Google Calendar

- Difficulty: 🔴 Hard
- Subtitle: Designing an efficient, user-friendly frontend for a Google Calendar-like app.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/1_hGA3brGOXFqxIGh0uq1rNg.png

### Content

<h1>Design Google Calendar &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-596" src="https://api.frontendlead.com/wp-content/uploads/2024/03/1_hGA3brGOXFqxIGh0uq1rNg.png" alt="" width="975" height="501" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/1_hGA3brGOXFqxIGh0uq1rNg.png 975w, https://api.frontendlead.com/wp-content/uploads/2024/03/1_hGA3brGOXFqxIGh0uq1rNg-300x154.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/1_hGA3brGOXFqxIGh0uq1rNg-768x395.png 768w" sizes="(max-width: 975px) 100vw, 975px" /></p>
<h2>Introduction</h2>
<p>Frontend system design is an essential skill for developers aiming to build robust and scalable applications. This article delves into the frontend system design of a Google Calendar-like application. We&#8217;ll walk you through the entire process, emphasizing requirements gathering, high-level architecture design, API design, edge case management, client data modeling, and optimization strategies.</p>
<p><em>Diagrams are coming soon.</em></p>
<h2>1. Requirements</h2>
<h3>Functional Requirements</h3>
<ol>
<li class="">View Events: Users should be able to view events in daily, weekly, and monthly formats.</li>
<li class="">Conflict Resolution: The application should detect and provide options to resolve conflicting events.</li>
<li class="">Create New Events: Users should be able to create new events.</li>
</ol>
<p>Conflict Resolution in Detail: Conflict resolution involves detecting overlapping events and providing users with options to adjust the event times to avoid conflicts. We&#8217;ll develop a conflict detection algorithm to identify these cases.</p>
<h3>Non-Functional Requirements</h3>
<ol>
<li class="">Observability: Ensure logging mechanisms to track system health and performance, keeping in mind the cost implications of log storage.</li>
<li class="">Device Support: The application should be compatible with various devices including desktops, tablets, and smartphones.</li>
<li class="">Demographics and Accessibility: The design should be inclusive, catering to a diverse user base with features like screen readers and keyboard navigation for accessibility.</li>
<li class="">Performance: Ensure swift loading times and responsiveness to provide a seamless user experience.</li>
</ol>
<h3>2. High-Level Architecture Design</h3>
<h4>Model-View-Controller (MVC) Architecture</h4>
<p>In the MVC architecture, the application is divided into three interconnected components:</p>
<ol>
<li>Model: Represents the data layer of the application. It communicates with the database and updates the view whenever the data changes.</li>
<li>View: Represents the user interface and the presentation of the data. It displays the data from the model to the user and sends the user commands to the controller.</li>
<li>Controller: Interacts with both the model and the view. It takes the user input from the view, processes it (with possible updates to the model), and returns the output display.</li>
</ol>
<h4>High-Level Component Design and Data Flow</h4>
<ul>
<li class="ql-indent-2">Client-Side (Browser):View Components:Calendar View: Displays the calendar in daily, weekly, or monthly views.</li>
<li class="ql-indent-2">Event View: Displays details of a selected event.</li>
<li class="ql-indent-1">Event Creation Modal: Allows users to create new events.</li>
<li class="ql-indent-2">Server-Side:Controller Components:Event Controller: Manages the creation, viewing, and editing of events.</li>
<li class="ql-indent-1">Conflict Resolution Controller: Manages the detection and resolution of conflicting events.</li>
<li class="ql-indent-2">Database:Model Components:Event Model: Stores the event details such as title, date, time, location, and attendees.</li>
<li class="ql-indent-1">User Model: Stores user information, preferences, and event associations.</li>
</ul>
<h4>Data Flow:</h4>
<ol>
<li>The view sends a user request to the controller.</li>
<li>The controller interacts with the model to retrieve/update data based on the user request.</li>
<li>The model interacts with the database to perform CRUD (Create, Read, Update, Delete) operations.</li>
<li>The model returns the data to the controller.</li>
<li>The controller updates the view based on the data from the model.</li>
<li>The view displays the updated data to the user.</li>
</ol>
<h2>API Design</h2>
<h3>Protocol Choice</h3>
<p>For the Google Calendar application, we would primarily be using HTTP/HTTPS as the protocol for request-response communication between the client and server. Here are the reasons and situations where different techniques would be used:</p>
<ol>
<li>HTTP/HTTPS (REST): For the basic CRUD operations like creating, reading, updating, or deleting events. It is stateless and each request from client to server must contain all the information the server needs to fulfill that request (like user authentication data).</li>
<li>WebSockets: This could be used for real-time updates to the calendar. When an event is added/updated by one user, it can be reflected in real-time to other users who are viewing the same calendar (if it&#8217;s a shared calendar).</li>
<li>Long Polling: In situations where real-time updates are not critical, we could use Long Polling to reduce the number of HTTP requests made to the server. This would be an optimization to consider based on the specific requirements and user base of the application.</li>
</ol>
<p>Given that we don&#8217;t have to deal with real-time, we will choose to go with HTTP route.</p>
<p>Endpoints</p>
<p><strong>Retrieve All Events</strong></p>
<p>Endpoint:</p>
<pre><code>GET /events</code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "status": "success",
  "data": [
    {
      "eventId": "12345",
      "title": "Meeting with Bob",
      "date": "2023-09-30",
      "time": "10:00 AM",
      "location": "Room 301",
      "attendees": ["bob@example.com", "alice@example.com"]
    },
    {
      "eventId": "12346",
      "title": "Project Presentation",
      "date": "2023-10-01",
      "time": "02:00 PM",
      "location": "Conference Room",
      "attendees": ["team@example.com"]
    }
  ]
}</code></pre>
<p>&nbsp;</p>
<p><strong>Update an Existing Event</strong></p>
<p>Endpoint:</p>
<pre><code>PUT /events/:eventId</code></pre>
<p>Request Body:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "title": "Meeting with Bob and Alice",
  "date": "2023-09-30",
  "time": "11:00 AM",
  "location": "Room 302",
  "attendees": ["bob@example.com", "alice@example.com"]
}</code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "status": "success",
  "data": {
    "eventId": "12345",
    "title": "Meeting with Bob and Alice",
    "date": "2023-09-30",
    "time": "11:00 AM",
    "location": "Room 302",
    "attendees": ["bob@example.com", "alice@example.com"]
  }
}</code></pre>
<p><strong>Delete an Event</strong></p>
<p>Endpoint:</p>
<pre><code>DELETE /events/:eventId</code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "status": "success",
  "message": "Event deleted successfully"
}</code></pre>
<p><strong>Get Conflicting Events</strong></p>
<p>Endpoint:</p>
<pre><code>GET /events/conflicts</code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "status": "success",
  "data": [
    {
      "eventId": "12345",
      "conflictingEventId": "12347",
      "date": "2023-09-30",
      "time": "10:00 AM to 11:00 AM"
    }
  ]
}</code></pre>
<p><strong>Resolve a Conflicting Event</strong></p>
<p>Endpoint:</p>
<pre><code><code>PUT /events/conflicts/:eventId</code></code></pre>
<p>Request Body:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "resolutionAction": "reschedule",
  "newDate": "2023-10-01",
  "newTime": "09:00 AM"
}</code></pre>
<p>Response:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  "status": "success",
  "message": "Conflict resolved successfully"
}</code></pre>
<h3>Conflict Detection</h3>
<p>The conflict detection phase is a crucial step in maintaining a seamless calendar experience. It identifies overlapping events, which could be a potential cause of scheduling conflicts. Here&#8217;s how it can be broken down step-by-step with examples:</p>
<p>Step 1: Identify Event Details</p>
<p>Explanation: When a user creates or updates an event, the system collects all the necessary details related to the event, such as the event date, start time, end time, and list of attendees.</p>
<p>Example: A user attempts to schedule a &#8220;Project Kickoff&#8221; meeting on September 20th, from 10:00 AM to 11:00 AM, with attendees A, B, and C.</p>
<p>Step 2: Check Existing Events for Attendees</p>
<p>Explanation: The system then cross-references the proposed time slot with existing events in the calendar for all the listed attendees. This helps in identifying any overlapping events.</p>
<p>Example: The system checks the calendars of attendees A, B, and C for any events scheduled from 10:00 AM to 11:00 AM on September 20th.</p>
<p>Step 3: Conflict Analysis</p>
<p>Explanation: If an overlapping event is found, it is flagged as a conflict. The system considers various parameters such as the exact time overlap, the attendees involved, and the nature of the conflicting event (whether it is a one-time event or part of a recurring series).</p>
<p>Example: The system finds that attendee B has a &#8220;Client Meeting&#8221; scheduled from 10:30 AM to 11:30 AM on the same day, which conflicts with the proposed &#8220;Project Kickoff&#8221; meeting.</p>
<p>Step 4: Granular Conflict Detection</p>
<p>Explanation: In more sophisticated systems, conflict detection can be more granular, considering even more aspects such as the location of the event (in case of physical meetings), whether the conflicting event can be moved or not, etc.</p>
<p>Example: The system notes that the &#8220;Client Meeting&#8221; for attendee B is at a different location, and moving it might not be feasible due to the logistical constraints.</p>
<p>Step 5: Conflict Notification Preparation</p>
<p>Explanation: Once the conflict is detected, the system prepares to notify the user about the conflict, providing detailed information about the conflicting events, including who is involved and what the overlapping time slots are.</p>
<p>Example: The system prepares a notification to inform the user that there is a conflict with attendee B&#8217;s &#8220;Client Meeting&#8221; from 10:30 AM to 11:30 AM, suggesting potential resolutions such as rescheduling the &#8220;Project Kickoff&#8221; meeting or finding a different time slot that suits all attendees.</p>
<p>Code Example:</p>
<pre><code>function sortEventsByStartTime(events) {
    // Sorts the events by start time in ascending order
    return events.sort((a, b) => new Date(a.startTime) - new Date(b.startTime));
}

function detectConflicts(events) {
    // Initialize an empty list to store conflict groups
    let conflictGroups = [];

    // Helper function to add events to conflict groups
    function addToConflictGroup(event1, event2) {
        for (let group of conflictGroups) {
            if (group.has(event1) || group.has(event2)) {
                group.add(event1);
                group.add(event2);
                return;
            }
        }
        // If neither event is in a conflict group, create a new group
        let newGroup = new Set([event1, event2]);
        conflictGroups.push(newGroup);
    }

    // Sort events by start time
    let sortedEvents = sortEventsByStartTime(events);

    // Iterate over the sorted events and check for conflicts
    for (let i = 0; i < sortedEvents.length - 1; i++) {
        let currentEvent = sortedEvents[i];
        let nextEvent = sortedEvents[i + 1];

        // Check if the current event ends after the next event starts
        if (new Date(currentEvent.endTime) > new Date(nextEvent.startTime)) {
            // A conflict is found, add the events to a conflict group
            addToConflictGroup(currentEvent, nextEvent);
        }
    }

    // Return the list of conflict groups
    return conflictGroups;
}

// Usage:
let events = [
    { startTime: '2023-09-20T09:30:00', endTime: '2023-09-20T10:30:00', attendees: ['B'] },
    { startTime: '2023-09-20T10:00:00', endTime: '2023-09-20T11:00:00', attendees: ['A', 'B', 'C'] },
    { startTime: '2023-09-20T10:30:00', endTime: '2023-09-20T11:30:00', attendees: ['C'] }
];

console.log(detectConflicts(events));
</code></pre>
<h3>Edge Cases</h3>
<p>Handling edge cases is a critical part of system design to ensure a robust and reliable application. Here are some potential edge cases and how we might handle them:</p>
<ol>
<li>Concurrent Event Creation:</li>
<li class="ql-indent-1">Scenario: Two or more users attempt to create events that overlap in time and involve the same attendees.</li>
<li class="ql-indent-1">Solution: Implement an optimistic concurrency control mechanism. When an attempt to create an event is made, check for conflicts and notify the user if any conflicts exist.</li>
<li>Large Number of Attendees:</li>
<li class="ql-indent-1">Scenario: An event is created with a large number of attendees, potentially causing performance issues when checking for conflicts or sending notifications.</li>
<li class="ql-indent-1">Solution: Implement batch processing for operations like conflict checking and notifications, potentially in a background job to avoid blocking the main application thread.</li>
<li>Time Zone Differences:</li>
<li class="ql-indent-1">Scenario: Attendees are in different time zones, which can cause confusion regarding the timing of events.</li>
<li class="ql-indent-1">Solution: Store times in a universal format (like UTC) and convert to the local time zone of each attendee when displaying event details or sending notifications.</li>
<li>Invalid or Malformed Data Input:</li>
<li class="ql-indent-1">Scenario: A user inputs invalid or malformed data when creating or updating an event (e.g., an incorrect date format).</li>
<li class="ql-indent-1">Solution: Implement robust input validation to catch invalid or malformed data and provide the user with clear error messages.</li>
<li>Failure to Send Notifications:</li>
<li class="ql-indent-1">Scenario: The system fails to send notifications (due to network issues, third-party service downtimes, etc.).</li>
<li class="ql-indent-1">Solution: Implement a retry mechanism for failed notifications, possibly coupled with a logging system to track failed notification attempts and address them accordingly.</li>
</ol>
<h2>Client Data Model</h2>
<p>The Client Data Model is essentially how we structure and manage data on the client side. This involves creating data structures to hold events, managing the retrieval of data from the server, and implementing mechanisms for updating the data when changes occur. Here, I&#8217;ll detail how we might build out the client store considering performance, potential caching mechanisms, and normalization.</p>
<h3>Client Store Structure</h3>
<p>We would have a centralized store (like Redux or Vuex store) to hold and manage the data for the application. The store structure would look something like this:</p>
<pre class="ql-syntax" spellcheck="false"><code>{
  events: [],  // Array to store event objects
  users: [],   // Array to store user objects (attendees)
  views: {     // Object to store current view settings (day, week, month)
    currentView: 'week',
  },
  filters: {}, // Object to store any active filters (like showing only certain calendars)
}</code></pre>
<h3>Performance Considerations</h3>
<p>To enhance performance, especially when dealing with a large number of events, we would need to consider techniques such as:</p>
<ol>
<li>Lazy Loading: Load only a subset of events initially and then load more as needed.</li>
<li>Indexed Lookup: Create indexed lookups for events based on dates or user IDs to quickly find relevant events.</li>
</ol>
<h3>Caching Mechanisms</h3>
<p>To minimize the number of server requests and enhance user experience, we might consider:</p>
<ol>
<li>Service Workers: Implementing service workers to cache server responses locally.</li>
<li>State Persistence: Persisting the client store locally (like local storage) so that it&#8217;s available even after page reloads.</li>
</ol>
<h3>Normalization</h3>
<p>Normalizing the data structure helps to minimize data redundancy and maintain data consistency. For example:</p>
<ol>
<li>Event Attendees: Instead of storing attendee details directly within event objects, we can store user (attendee) objects separately and reference them by ID in event objects.</li>
</ol>
<h2>Optimizations</h2>
<p>In the optimization phase, we will explore various techniques and strategies to enhance the application&#8217;s performance, accessibility, internationalization, and overall user experience. Here, I will outline potential optimizations that can be implemented in the Google Calendar application</p>
<p>1 Virtualization</p>
<p>Definition: Virtualization is a technique where we render only a subset of the items in the list that are currently visible within the viewport, improving the performance significantly when dealing with large lists of data.</p>
<p>Implementation in Calendar:</p>
<ol>
<li>Event List Virtualization: When displaying a list of events for a day/week/month, use a virtualized list to only render the events currently in view.</li>
<li>Calendar Grid Virtualization: Similarly, when displaying the calendar grid, only render the cells that are currently in view.</li>
</ol>
<h3>Debouncing/Throttle/Rate Limiting</h3>
<p>Definition: These are techniques to limit the number of requests or function executions in a given period, enhancing performance and preventing potential server overloads.</p>
<p>Implementation in Calendar:</p>
<ol>
<li>Debouncing: Implement debouncing in the event search functionality to limit the number of server requests while the user is typing.</li>
<li>Rate Limiting: Limit the rate of API requests to prevent overloading the server, especially during mass event updates or uploads.</li>
</ol>
<h3>Performance</h3>
<p>Further performance optimizations could include:</p>
<ol>
<li>Minimizing Client-Side Rendering Time: Using techniques like memoization to prevent unnecessary re-renders.</li>
<li>Optimizing Server Responses: Reducing the size of server responses by using techniques like data pagination.</li>
</ol>
<h3>Accessibility</h3>
<p>Ensuring the application is accessible to all users is crucial. Strategies here might involve:</p>
<ol>
<li>Keyboard Navigation: Ensuring that all functionalities are accessible via keyboard.</li>
<li>Screen Reader Support: Implementing proper ARIA attributes to support screen readers.</li>
</ol>
<h3>Internationalization</h3>
<p>To support a global user base, we would implement internationalization features such as:</p>
<ol>
<li>Language Support: Allowing users to select their preferred language.</li>
<li>Time Zone Support: Displaying dates and times according to the user&#8217;s time zone.</li>
</ol>
<h3>Additional Optimizations</h3>
<p>Other potential optimizations can be:</p>
<ol>
<li>Responsive Design: Ensuring that the application functions well and looks good on all device types, including mobiles and tablets.</li>
<li>Offline Support: Implementing service workers to allow for offline usage and sync once the connection is re-established.</li>
</ol>
<h2>Bonus</h2>
<h3>Pagination</h3>
<p>When the server returns a substantial number of events, it can potentially lead to performance issues, including increased loading times and decreased responsiveness. Here are some strategies and updates to our API design to manage this effectively:</p>
<h3>Data Pagination</h3>
<p>Explanation: Data pagination involves breaking the data into smaller chunks and loading them as needed, rather than retrieving all events at once.</p>
<p>Implementation in API:</p>
<ul>
<li>Endpoint: <code>GET /events?page=1&amp;limit=100</code> &#8211; This endpoint will allow fetching events in pages, with a set number of events per page.</li>
<li>Client-side: Implement a lazy loading mechanism in the client application to load more events as the user scrolls, ensuring a smooth user experience.</li>
</ul>
<h3>Data Filtering</h3>
<p>Explanation: Implement filtering options in the API to allow the client to request only the necessary data, based on various parameters like time range, event type, etc.</p>
<p>Implementation in API, endpoint:</p>
<pre><code>GET /events?startDate=2023-01-01&amp;endDate=2023-01-31</code></pre>
<p>This will fetch events within a specified date range, reducing the volume of data retrieved in a single request.</p>
<h3>Data Compression</h3>
<p>Explanation: Using data compression techniques to reduce the size of the data transmitted between the server and the client.</p>
<p>Implementation in API:</p>
<ul>
<li>Enable gzip or Brotli compression on the server to reduce the size of the API responses.</li>
</ul>
<h3>Web Sockets for Real-Time Updates</h3>
<p>Explanation: To manage real-time updates more efficiently, especially when dealing with a large volume of data.</p>
<p>Implementation in API:</p>
<ul>
<li>Use WebSockets to push updates to the client, avoiding the need to fetch the entire dataset repeatedly.</li>
</ul>
<p>By implementing these strategies, we can ensure that the application remains responsive and provides a seamless user experience, even when handling a large volume of events.</p>
<p>In crafting the frontend system design for an application akin to Google Calendar, we have traversed through the foundational layers of functional and non-functional requirements, delved into the MVC architecture for a seamless division of tasks, and outlined the high-level components that make up the user experience. We discussed strategies for API communication, from RESTful practices to the employment of WebSockets for real-time interaction, and addressed the significance of a structured approach to conflict resolution. Alongside, we emphasized the importance of observability, device support, and a design that champions accessibility and performance. As we prepare to detail the diagrams that will bring clarity to our discussed concepts, we acknowledge that each design decision we make—from the APIs we craft to the data models we architect—serves the paramount goal of delivering an application that not only meets the immediate user needs but also anticipates and adapts to the evolving dynamics of usage patterns and technological advancements.</p>
<p>Best of luck in your interview!</p>


---

## 11. Design Sprint Board

- Difficulty: 🟠 Medium
- Subtitle: Designing an efficient, secure, and accessible sprint board for agile teams.
- Video Link: https://www.youtube.com/watch?v=1tsAdkqunqQ
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-1.png

### Content

<h1>Design a Sprint Board &#8211; Frontend System Design</h1>
<p><iframe loading="lazy" title="Design JIRA Sprint Board - Frontend System Design Guide" width="500" height="281" src="https://www.youtube.com/embed/1tsAdkqunqQ?feature=oembed" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></p>
<p>Our aim is to design a digital Sprint Board similar to Jira, tailored to enhance team collaboration and streamline workflow management.</p>
<p>This digital Sprint Board will be an interactive web application where team members can manage tasks, represented as tickets, across various stages of development. The design focuses on simplicity, usability, and efficiency, ensuring that teams can focus on delivering value without the tool becoming an impediment.</p>
<p>Full Diagram can be found below:<br />
<img loading="lazy" decoding="async" class="alignnone wp-image-1553 size-full" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-Build-Asana_Jira.svg" alt="" width="5992" height="2676" /></p>
<h2>Requirements</h2>
<h3>Functional Requirements:</h3>
<ul>
<li><strong>Managing Existing Sprint</strong>: Users must be able to view and interact with the current sprint, with the ability to update the status of tickets as they move through stages.</li>
<li><strong>Create New Tickets</strong>: The application allows users to add new tickets to the sprint board, including the description, assignment, and priority of the task.</li>
<li><strong>Reorder Tickets by Columns</strong>: Tickets can be dynamically reordered within columns, reflecting priority changes or task progression. Each ticket is limited to one assignee at any given time to ensure clear responsibility.</li>
<li><strong>Create New Columns</strong>: Teams can customize their workflow by adding new columns, enabling them to represent unique stages in their development process.</li>
</ul>
<h3>Non-functional Requirements:</h3>
<ul>
<li><strong>Client-Side Rendering (CSR) vs. Server-Side Rendering (SSR)</strong>: The design should account for the most suitable rendering approach, striking a balance between performance and SEO needs.</li>
<li><strong>Responsive Design</strong>: The board should be accessible on various devices, prioritizing a web-first design approach.</li>
<li><strong>Illusion of Real-Time</strong>: While not strictly real-time, the application should provide users with the illusion of real-time updates, ensuring a smooth and responsive experience.</li>
<li><strong>Shimmer Loaders</strong>: To enhance perceived performance, shimmer loaders will be used to indicate loading states in a graceful manner.</li>
<li><strong>Accessibility (A11y) Friendly</strong>: The design must be inclusive, adhering to accessibility standards to support users with disabilities.</li>
<li><strong>Performance</strong>: The application should be optimized for speed, minimizing load times and ensuring quick interaction responses.</li>
<li><strong>Internationalization</strong>: The application should be designed to support multiple languages and regions.</li>
<li><strong>Observability/Tracking</strong>: Incorporate analytics and monitoring to track user interactions and application performance.</li>
</ul>
<h3>Edge Cases:</h3>
<ul>
<li><strong>New Ticket Creation</strong>: The system must handle the creation of new tickets without hiccups.</li>
<li><strong>Infinite Scrolling</strong>: Implement infinite scrolling using the Intersection Observer API to load tickets as needed without overwhelming the browser.</li>
<li><strong>Drag and Drop in Real-Time</strong>: Ensure a seamless, real-time experience when dragging and dropping tickets, even on slower connections.</li>
</ul>
<p>In the following sections, we will delve into the system design, addressing these requirements and ensuring a robust solution that caters to the needs of agile development teams.</p>
<h2>High-Level Architecture</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-603" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM.png" alt="" width="1140" height="878" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM.png 1140w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-300x231.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-1024x789.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.34.06-AM-768x591.png 768w" sizes="(max-width: 1140px) 100vw, 1140px" /></p>
<p>Examining the high-level architecture provided, we can structure our discussion around the key components and their interactions within the context of a Sprint Board application. Here&#8217;s a breakdown of the architecture:</p>
<h3>Views:</h3>
<ol>
<li><strong>Sprint Board View</strong>: This is the central interface where the sprint board is displayed. It consists of child components that represent different columns (e.g., Todo, In Progress, Done) and tickets within those columns.</li>
<li><strong>Create Composer View</strong>: This interface is used for creating new tickets. It includes child components for input forms, assignment selectors, and priority settings.</li>
</ol>
<p>Both these views will interact with the Board Controller, which acts as an intermediary between the views and the data model store.</p>
<h3>Board Controller:</h3>
<p>The Board Controller is responsible for orchestrating the creation of new boards and updating existing tickets. It communicates with the views to reflect the changes in the UI and interacts with the Data Model Store to fetch and update data.</p>
<h3>Creating a New Board:</h3>
<p>This process begins at the interface but is coordinated by the Board Controller, which initializes a new board structure in the Data Model Store.</p>
<h3>Updating Existing Tickets:</h3>
<ol>
<li><strong>Ticket Interaction</strong>: This feature involves drag-and-drop functionality for moving tickets between columns.
<ul>
<li><strong>Drag Start</strong>: The process begins when a user initiates a drag action on a ticket.</li>
<li><strong>Drag End (Drop)</strong>: It concludes when the ticket is dropped into a new column, at which point the id of the new column is determined.</li>
<li><strong>Server Update</strong>: Once the drop action is completed, the Board Controller sends a request to update the server with the new ticket location.</li>
</ul>
</li>
</ol>
<h3>Data Model Store:</h3>
<p>This component stores the application&#8217;s state, including details of all boards, columns, and tickets. It ensures that the UI is in sync with the backend data model.</p>
<h3>Data Model:</h3>
<p>The data model represents the backend storage structure, which could be a database or a cloud-based data service. It stores the persistent data of tickets, columns, board configurations, and other related information.</p>
<h3>Controller Interactions:</h3>
<p>The controller manages interactions between the UI and the Data Model Store. This includes processing user actions, such as creating new tickets, moving tickets between columns, and saving these changes back to the Data Model.</p>
<h3>Considerations for Scalability and Maintainability:</h3>
<ul>
<li><strong>Componentization</strong>: Ensure that components in the views are reusable and encapsulated.</li>
<li><strong>State Management</strong>: Use Redux or Context API to manage the application state for predictable state management.</li>
<li><strong>Data Flow</strong>: Adopt a unidirectional data flow to ensure that the state changes are predictable and debuggable.</li>
<li><strong>API Layer</strong>: Implement a service or API layer for all server interactions to decouple the frontend from the backend, making it easier to manage changes on either side.</li>
<li><strong>Optimistic Updates</strong>: Apply optimistic UI updates to make the application feel faster. For instance, when a ticket is moved, the UI should immediately reflect this change before the server confirms the update.</li>
<li><strong>Error Handling</strong>: Incorporate robust error handling to manage failures in network requests or server updates.</li>
</ul>
<p>Incorporating the elements of the image and the noted use cases, let&#8217;s discuss how new ticket creation and dragging will work in our sprint board application.</p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-604" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.38.34-AM.png" alt="" width="1330" height="822" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.38.34-AM.png 1330w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.38.34-AM-300x185.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.38.34-AM-1024x633.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-10.38.34-AM-768x475.png 768w" sizes="(max-width: 1330px) 100vw, 1330px" /></p>
<h3>New Ticket Creation</h3>
<p>When a user decides to create a new ticket, they will interact with the &#8220;Create new ticket modal&#8221; component, which consists of the following fields:</p>
<ol>
<li><strong>Title</strong>: A short, descriptive title for the new ticket.</li>
<li><strong>Description</strong>: A detailed explanation of the task or issue.</li>
<li><strong>Additional Fields</strong>: Other relevant fields such as assignee, labels, priority, etc., which are represented by ellipsis (&#8230;) in the modal.</li>
<li><strong>Create Button</strong>: To submit the new ticket information.</li>
</ol>
<p>Additional options, such as whether to add the ticket to the current sprint, can also be provided.</p>
<p>Upon clicking the &#8220;Create&#8221; button, the new ticket will be posted to the sprint board. The image outlines a use case where a new ticket, upon creation, should be the last item in the &#8220;In Progress&#8221; section. However, the board could provide the flexibility to add it to different columns based on the team&#8217;s workflow.</p>
<h3>Dragging and Dropping Tickets</h3>
<p>The sprint board will also have draggable tickets that can be moved between columns (&#8220;Todo&#8221;, &#8220;In Progress&#8221;, and &#8220;Done&#8221;) to reflect their current status. Dragging is initiated by the user starting a drag event, typically by clicking and holding a ticket.</p>
<p>Here&#8217;s how the process works according to the use cases described:</p>
<ol>
<li><strong>Initiating Drag</strong>: The ticket becomes draggable when the The <code>draggable=true</code> property is set, and the <code>ondragstart</code> event handler is initialized.</li>
<li><span style="box-sizing: border-box; margin: 0px; padding: 0px;"><strong>While dragging</strong>, Visual cues such as a change in ticket style or a placeholder in the target column help indicate the action in progress.</span></li>
<li><strong>Dropping the Ticket</strong>: The the <code>ondrop</code> event handler in the target column receives the ticket. The ticket&#8217;s new position is the end of the list in the new column as per the specified use cases.</li>
<li><strong>Server Update</strong>: An API call is made to update the ticket&#8217;s status and position in the database. This operation can be designed to occur optimistically, updating the UI before receiving confirmation from the server to make the experience feel real-time.</li>
</ol>
<h4>Implementation Details:</h4>
<ul>
<li><strong>Consistent Vertical Positioning</strong>: To maintain ticket positioning within columns, a sorting identifier or index must be stored and updated for each ticket. This ensures that the order is preserved and respected across different sessions and user interactions.</li>
<li><strong>Ticket Movement Logic</strong>: The logic for moving tickets must ensure that the removal from one column and the addition to another are atomic operations. This could mean that the backend or frontend state management temporarily locks the ticket during this operation, preventing other operations from conflicting.</li>
<li><strong>API Call on Drag End</strong>: When a ticket is dropped into a new column, an API call is triggered to update the ticket’s metadata in the database, specifically its &#8216;status&#8217; field and any other relevant ordering fields.</li>
</ul>
<h3>Accessibility and User Experience</h3>
<ul>
<li><strong>Keyboard Navigation</strong>: Ensure that tickets can also be moved using keyboard navigation to support users who cannot use a mouse or prefer keyboard shortcuts.</li>
<li><strong>Screen Reader Support</strong>: Descriptive ARIA roles and properties should be used to ensure that screen readers accurately convey the drag-and-drop process to visually impaired users.</li>
<li><strong>Feedback</strong>: Provide immediate visual or auditory feedback when a ticket is picked up, moved, or dropped, enhancing the overall user experience.</li>
</ul>
<p>By addressing these considerations, the sprint board will become an intuitive and effective tool for managing the development process within an Agile framework.</p>
<h2>API Design for Sprint Board Application</h2>
<section>
<h3>Pulling the Current Board</h3>
<p>To retrieve the current board, a <code>GET</code> request is made. The board&#8217;s data, including columns and tickets, is returned in a structured format.</p>
<pre><code>
  const getBoard = async (boardId, limit, page) =&gt; {
    try {
      const response = await fetch(\`/api/board/\${boardId}?limit=\${limit}&amp;page=\${page}\`, {
        method: 'GET',
        headers: {
          'Authorization': \`Bearer \${your_jwt_token}\`,
          'Content-Type': 'application/json'
        }
      });
      const boardData = await response.json();
      return boardData;
    } catch (error) {
      console.error('Error fetching board:', error);
    }
  };
  </code></pre>
</section>
<section>
<h3>Creating New Tickets</h3>
<p>To create a new ticket, a <code>POST</code> request is made with the ticket details in the request body.</p>
<pre><code>
  const createTicket = async (title, points, boardId) =&gt; {
    try {
      const response = await fetch('/api/ticket', {
        method: 'POST',
        headers: {
          'Authorization': \`Bearer \${your_jwt_token}\`,
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({ title, points, boardId })
      });
      if (!response.ok) throw new Error('Ticket creation failed');
      return await response.json();
    } catch (error) {
      console.error('Error creating ticket:', error);
    }
  };
  </code></pre>
</section>
<section>
<h3>Moving Existing Tickets</h3>
<p>To move an existing ticket, a <code>POST</code> request is made to transition the ticket from one column to another.</p>
<pre><code>
  const moveTicket = async (boardId, ticketId, targetColumnId) =&gt; {
    try {
      const response = await fetch('/api/ticket/move', {
        method: 'POST',
        headers: {
          'Authorization': \`Bearer \${your_jwt_token}\`,
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({ boardId, ticketId, targetColumnId })
      });
      if (!response.ok) throw new Error('Ticket move failed');
      return await response.json();
    } catch (error) {
      console.error('Error moving ticket:', error);
    }
  };
  </code></pre>
</section>
<section>
<h3>Creating New Column</h3>
<p>To add a new column to the board, a <code>POST</code> request is made with the column name and associated board ID.</p>
<pre><code>
  const createColumn = async (boardId, columnName) =&gt; {
    try {
      const response = await fetch('/api/column', {
        method: 'POST',
        headers: {
          'Authorization': \`Bearer \${your_jwt_token}\`,
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({ boardId, name: columnName })
      });
      if (!response.ok) throw new Error('Column creation failed');
      return await response.json();
    } catch (error) {
      console.error('Error creating column:', error);
    }
  };
  </code></pre>
</section>
<h2>Communication Protocols: Choosing GraphQL for Our Sprint Board Application</h2>
<section>
<h3>Overview of Communication Protocols</h3>
<p>In the development of web applications, choosing the proper communication protocol is crucial for ensuring efficient data exchange between the client and server. Various protocols offer different benefits and come with their own sets of trade-offs.</p>
</section>
<section>
<h3>Polling, Long Polling, and REST</h3>
<p>Traditional methods, such as polling and long polling, involve the client sending repeated requests to the server to check for updates. While these methods are widely supported and simple to implement, they are not the most efficient. The constant stream of requests can lead to slower performance due to the overhead of HTTP requests and latency in responses.</p>
</section>
<section>
<h3>WebSockets</h3>
<p>WebSockets provide a persistent, bidirectional communication channel, which allows for real-time data transfer. This method is faster than polling because it eliminates the need for repeated requests. However, it can be more expensive due to the persistent connections and may face challenges with firewalls and load balancers, especially when not using HTTP/2.</p>
</section>
<section>
<h3>GraphQL</h3>
<p>GraphQL is a query language that enables clients to request exactly the data they need, making it highly efficient. It&#8217;s type-friendly and works well with HTTP/2, bringing the benefits of modern transport protocols, such as efficient use of headers and multiplexing. While it may lead to pulling all connected nodes, potentially increasing latency if not managed correctly, it allows for precise and optimized data retrieval.</p>
</section>
<section>
<h3>Why GraphQL for Our Application</h3>
<p>For our Sprint Board Application, GraphQL is the protocol of choice due to its flexibility and efficiency. It enables us to:</p>
<ul>
<li>Fetch specific data related to board columns, tickets, and sprints with a single request.</li>
<li>Minimize over-fetching and under-fetching of data, which is common in REST.</li>
<li>Combine multiple operations into a single HTTP request to reduce network overhead.</li>
<li>Effortlessly evolve the API without versioning, benefiting from a strong type system to build reliable client-side applications.</li>
</ul>
<p>The ability to pull precisely the data we need, when we need it, without the extra overhead, makes GraphQL the ideal candidate for our web application, where performance, scalability, and real-time updates are key.</p>
</section>
<p>&nbsp;</p>
<h2>Optimization Strategies for the Sprint Board Application</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-606" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.01.42-AM.png" alt="" width="1184" height="490" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.01.42-AM.png 1184w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.01.42-AM-300x124.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.01.42-AM-1024x424.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.01.42-AM-768x318.png 768w" sizes="(max-width: 1184px) 100vw, 1184px" /></p>
<section>
<h3>Network Optimizations</h3>
<ul>
<li><strong>Images:</strong> Pull specific image sizes based on the viewport using web-compressed formats like WebP, when available; otherwise, use PNG.</li>
<li><strong>Compression:</strong> Utilize GZIP or Brotli for text compression to minimize the payload size sent over the network.</li>
</ul>
</section>
<section>
<h3>Rendering Optimizations</h3>
<ul>
<li><strong>Paginating Tickets:</strong> Implement infinite scrolling with the Intersection Observer API to load tickets as they enter the viewport, reducing initial load times.</li>
<li><strong>Virtualization:</strong> Virtualize the rendering of tickets to replace nodes in the DOM rather than re-creating them, which is beneficial for performance when dealing with long lists.</li>
<li><strong>Hybrid Rendering:</strong> Utilize a combination of Server-Side Rendering (SSR) for the initial load and Client-Side Rendering (CSR) for dynamic interactions, capitalizing on the strengths of both rendering methods.</li>
</ul>
</section>
<section>
<h3>JavaScript Optimizations</h3>
<ul>
<li><strong>Webpack:</strong> Utilize Webpack for polyfills and compression to ensure compatibility and efficiency.</li>
<li><strong>Dynamic Imports:</strong> Import only what you need and use lazy loading for non-critical features such as modals.</li>
<li><strong>Code Splitting:</strong> Implement bundle splitting to separate critical resources and defer non-critical ones, which can reduce the initial load time.</li>
<li><strong>CSS Optimization:</strong> Inline CSS in JavaScript for specific components to avoid excess, unused styles loading.</li>
<li><strong>Testing:</strong> Implement unit tests to cover all functionalities, ensuring that each component works correctly.</li>
</ul>
</section>
<section>
<h3>Build Outputs</h3>
<ul>
<li><strong>Vendor Splitting:</strong> Separate vendor libraries from the main code to cache them independently, as they change less frequently.</li>
<li><strong>Board-specific Code:</strong> Keep board-related code separate to load only when the board is being used.</li>
</ul>
</section>
<h2>Security and Accessibility in Sprint Board Application</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-607" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.06.55-AM.png" alt="" width="1480" height="500" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.06.55-AM.png 1480w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.06.55-AM-300x101.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.06.55-AM-1024x346.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.06.55-AM-768x259.png 768w" sizes="(max-width: 1480px) 100vw, 1480px" /></p>
<section>
<h3>Security Considerations</h3>
<p>Security is paramount in any web application, as it protects sensitive data and maintains user trust. In our Sprint Board application, we implement several security measures:</p>
<ul>
<li><strong>Authentication:</strong> Utilize secure authentication methods, such as OAuth or JSON Web Tokens (JWT), to manage user sessions.</li>
<li><strong>Data Validation:</strong> Rigorously validate all data on the server side to prevent SQL injection and other forms of attacks.</li>
<li><strong>API Security:</strong> Protect APIs with rate limiting and access controls to prevent abuse.</li>
<li><strong>HTTPS:</strong> Employ HTTPS to encrypt data in transit and prevent man-in-the-middle attacks.</li>
<li><strong>Content Security Policy (CSP):</strong> Define a CSP to mitigate cross-site scripting (XSS) and data injection risks.</li>
<li><strong>Regular Audits:</strong> Conduct regular security audits and update dependencies to patch known vulnerabilities.</li>
</ul>
</section>
<section>
<h3>Accessibility Considerations</h3>
<p>Ensuring that our application is accessible to all users, including those with disabilities, is not just a legal mandate but also a moral obligation. To this end, we integrate the following accessibility practices:</p>
<ul>
<li><strong>Semantic HTML:</strong> Use semantic HTML tags to provide meaningful structure and help screen readers interpret the content.</li>
<li><strong>Aria Attributes:</strong> Apply ARIA (Accessible Rich Internet Applications) attributes to enhance accessibility, especially in dynamic content and complex user interfaces.</li>
<li><strong>Keyboard Navigation:</strong> Ensure all interactive elements are operable with keyboard-only controls.</li>
<li>Maintain high contrast ratios for text and interactive elements to support users with visual impairments.</li>
<li><strong>Alt Text for Images:</strong> Provide descriptive alt text for images, so screen readers can convey the information they contain.</li>
<li><strong>Responsive Design:</strong> Ensure the application is usable on a range of devices and screen sizes.</li>
<li><strong>Error Handling:</strong> Design clear error messages and provide suggestions for resolution to assist users when they encounter input errors.</li>
<li><strong>Testing:</strong> Perform accessibility testing with real users, including those who rely on assistive technologies.</li>
</ul>
</section>
<footer>
<h2>Conclusion</h2>
<p>With a keen eye on both functional and non-functional requirements, we have tailored a system that promises to deliver on performance and ensure security and accessibility for all users.</p>
<p>Our focus on employing GraphQL for efficient data handling, using modern web technologies for a seamless user experience, and emphasizing security and accessibility standards demonstrates our commitment to building robust, user-friendly, and inclusive web applications. As we move forward, we will continue to refine our practices, adapt to new challenges, and prioritize the needs of our users and stakeholders.</p>
</footer>


---

## 12. Design Facebook Newsfeed

- Difficulty: 🟠 Medium
- Subtitle: Elevate your NewsFeed design with expert frontend strategies.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.29.06-AM.png

### Content

<h1>Design Facebook Newsfeed &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone wp-image-1559 size-full" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Design-Facebook.svg" alt="" width="8420" height="3000" /></p>
<p>&nbsp;</p>
<header>Welcome to our in-depth exploration of building a Facebook-like NewsFeed feature from a frontend system design perspective. This comprehensive guide will walk you through the essential phases of creating an engaging and robust NewsFeed that users love interacting with daily.</header>
<header>
<hr />
</header>
<article>
<section>
<h2>Introduction</h2>
<p>The News Feed is the heart of any social media platform, serving as the central hub for user interaction and content discovery. Designing such a feature involves a meticulous approach to understanding user requirements, crafting a scalable architecture, ensuring seamless API communication, and maintaining high performance. Moreover, we must not overlook crucial aspects such as security and accessibility to provide all users an inclusive and safe environment.</p>
<p>In this article, we&#8217;ll delve into the core components of system design for a NewsFeed, covering:</p>
<ul>
<li>Clarifying Questions: Outlining the initial inquiries to shape our design approach.</li>
<li>Requirements: Detailing both functional and nonfunctional aspects that our NewsFeed must fulfill.</li>
<li>High-Level Architecture Design: Sketching the blueprint of our system’s structure.</li>
<li>API Design: Defining how our front end will communicate with the server and fetch data.</li>
<li>Optimizations: Identifying techniques to enhance performance and user experience.</li>
<li>Security and Accessibility: Addressing the safeguarding of user data and ensuring accessibility for a diverse user base.</li>
</ul>
<p>By the end of this article, you’ll have a clear roadmap to designing a NewsFeed that not only functions effectively but also scales gracefully with your user base and stands the test of time.</p>
</section>
</article>
<h2>Clarifying Questions for NewsFeed System Design</h2>
<section>
<ul>
<li style="font-weight: 400;" aria-level="1"><span style="font-weight: 400;">What are the core features to be supported?</span></li>
<li style="font-weight: 400;" aria-level="1"><span style="font-weight: 400;">What kind of posts are supported?</span></li>
<li style="font-weight: 400;" aria-level="1"><span style="font-weight: 400;">What pagination UX should be used for the feed?</span></li>
<li style="font-weight: 400;" aria-level="1"><span style="font-weight: 400;">Will the application be used on mobile devices?</span></li>
<li style="font-weight: 400;" aria-level="1"><span style="font-weight: 400;">Any UX we would like offline?</span></li>
</ul>
</section>
<section>
<h2>Requirements</h2>
<h3>Functional Requirements</h3>
<p>The NewsFeed we are aiming to design will focus on the following user-centric functionalities:</p>
<ul>
<li>Display a curated list of posts from the user and their friends, promoting social interaction and content engagement.</li>
<li>Facilitate liking and reacting to feed posts, allowing users to express their emotions and thoughts dynamically.</li>
<li>Enable the creation and publishing of new posts, empowering users to share their experiences and updates effortlessly.</li>
<li>Support primarily text and image-based posts, potentially expanding to other types of content as the application evolves.</li>
<li>Implement infinite scrolling for a fluid and uninterrupted browsing experience, loading content as the user scrolls.</li>
</ul>
<h3>Nonfunctional Requirements</h3>
<p>To complement the functional aspects, our system will also adhere to key nonfunctional requirements:</p>
<ul>
<li><strong>Performance:</strong> The NewsFeed must be optimized for quick load times and responsive interactions, even under heavy user load.</li>
<li><strong>Internationalization</strong> will support multiple languages and regional settings, catering to a global user base.</li>
<li><strong>Accessibility (A11y):</strong> The design will be inclusive and meet accessibility standards to serve users with different abilities.</li>
<li><strong>Observability:</strong> Incorporate comprehensive logging and monitoring to track system health and user activities.</li>
<li><strong>Security:</strong> Robust security measures will be in place to protect user data and privacy.</li>
<li><strong>Best Practices:</strong> The application will be developed using industry-standard code quality, maintainability, and scalability best practices.</li>
<li><strong>Mobile Friendliness:</strong> NewsFeed will offer a seamless mobile experience responsive to various device sizes.</li>
<li><strong>Offline Accessibility:</strong> Though not a requirement for basic functionality, the ability to access specific data offline will be considered a valuable feature.</li>
</ul>
</section>
<section>
<h2>High-Level Architecture Design</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-611" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.42.10-AM.png" alt="" width="1028" height="976" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.42.10-AM.png 1028w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.42.10-AM-300x285.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.42.10-AM-1024x972.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.42.10-AM-768x729.png 768w" sizes="(max-width: 1028px) 100vw, 1028px" /></p>
<p>The design of our NewsFeed system employs a classic MVC (Model-View-Controller) architectural pattern, which will be discussed in the context of both client-side and server-side operations.</p>
<h3>Server-Side Architecture</h3>
<p>The backend, depicted as a &#8216;Blackbox Server&#8217;, interacts with the frontend through a well-defined API, transmitting data in JSON format. This abstraction lets us focus on the frontend design, assuming the server can provide the necessary endpoints and handle business logic, database operations, and authentication securely and efficiently.</p>
<h3>Client-Side Architecture</h3>
<p>On the client side, our application is split into several key components:</p>
<ul>
<li><strong>Controller:</strong> Acts as the intermediary between the View layer and the Data Model, handling user interactions, communicating with the backend API, and managing the application&#8217;s state.</li>
<li><strong>Data Model (Store):</strong> A centralized store for the application&#8217;s state, including the list of feed items, user data, and other relevant state information. This store reacts to actions dispatched by the Controller to update the state.</li>
<li><strong>View Layer:</strong> Contains:
<ul>
<li><strong>Feed Container View:</strong> The main container holds individual feed items and the post composer.</li>
<li><strong>Post Composer:</strong> The interface through which users create new posts.</li>
<li><strong>Feed Item View:</strong> This component is responsible for rendering individual feed items and is further broken down into:
<ul>
<li><strong>Header View:</strong> Displays the author&#8217;s information and post metadata, including timestamps.</li>
<li><strong>Body View:</strong> Displays the main content of the feed post, such as text, images, or videos.</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>The client architecture supports the dynamic addition of content through the Post Composer and the infinite scroll functionality, enabling a continuous flow of feed items as users scroll through the NewsFeed.</p>
</section>
<section>
<h2>Client Data Model</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-612" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.44.14-AM.png" alt="" width="1458" height="788" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.44.14-AM.png 1458w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.44.14-AM-300x162.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.44.14-AM-1024x553.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.44.14-AM-768x415.png 768w" sizes="(max-width: 1458px) 100vw, 1458px" /></p>
<p>The client data model is integral to managing state within our NewsFeed application. It ensures data is organized, easily accessible, and maintains integrity throughout user interaction. Below are the code structures for the data models that represent the state of our application.</p>
<h3>App State Model</h3>
<pre><code>
  const App = {
    user: User,
    settings: UserSettings,
    feed: Feed
  };
  </code></pre>
<h3>User Model</h3>
<pre><code>
  const User = {
    name: 'string',
    // ...other user properties
  };
  </code></pre>
<h3>User Settings Model</h3>
<pre><code>
  const UserSettings = {
    timeZone: 'string',
    accessibilityPreferences: AccessibilityPreferences,
    // ...other settings
  };
  </code></pre>
<h3>Feed Model</h3>
<pre><code>
  const Feed = {
    items: 'List[FeedItem]',
    page: 'int',
    size: 'int'
  };
  </code></pre>
<h3>Feed Item Model</h3>
<pre><code>
  const FeedItem = {
    type: 'FeedItemType',
    creationDate: 'string',
    author: User,
    content: 'FeedItemContent',
    comments: 'List[FeedItemComments]'
  };
  </code></pre>
<h3>Feed Item Content Model</h3>
<pre><code>
  const FeedItemContent = {
    title: 'StyledText',
    body: 'StyledText',
    media: 'Media',
    // ...other content properties
  };
  </code></pre>
<h3>Styled Text Model</h3>
<pre><code>
  const StyledText = {
    // Rich text, colors, links, mentions...
    // Styled text structure driven by server UI
  };
  </code></pre>
<p>These models will be utilized to store data related to the user, their settings, and the feed content, including individual feed items and associated comments. The <code>StyledText</code> The structure provides flexibility for rich text formatting, essential for a dynamic and engaging News Feed.</p>
</section>
<section>
<h2>API Design and Communication Options</h2>
<h3>Choosing the Right API Communication Protocol</h3>
<p>In the design of our News Feed&#8217;s API, selecting the appropriate communication protocol is crucial. The leading contenders include RESTful APIs, GraphQL, WebSockets, and Server-Side Events (SSE). Here&#8217;s a comparative overview:</p>
<table>
<thead>
<tr>
<th>Protocol</th>
<th>Pros</th>
<th>Cons</th>
<th>Suitability</th>
</tr>
</thead>
<tbody>
<tr>
<td>REST API</td>
<td>Simple, HTTP/2 compatible, easy load balancing</td>
<td>Longer latency, connection timeouts, and traffic overhead</td>
<td>Basic CRUD operations</td>
</tr>
<tr>
<td>GraphQL</td>
<td>Modern, fetch exactly what you need, type-safe</td>
<td>Can have longer latency if not optimized</td>
<td>Complex, interrelated data structures</td>
</tr>
<tr>
<td>WebSockets</td>
<td>Real-time, bidirectional, single TCP connection</td>
<td>Resource-intensive, can be overkill for simple operations</td>
<td>Real-time features</td>
</tr>
<tr>
<td>Server-Side Events</td>
<td>Efficient, HTTP/2 compatible, server-to-client only</td>
<td>Unidirectional, limited to text data</td>
<td>Real-time updates from server to client</td>
</tr>
</tbody>
</table>
<p>For our News Feed, we chose GraphQL due to its ability to handle complex, interrelated data with efficiency and precision. It allows the client to request precisely what is needed, reducing data overfetching and ensuring type safety. While GraphQL may introduce some latency due to its complexity, proper optimization can mitigate these concerns, making it an ideal choice for our application&#8217;s needs.</p>
<h3>API Endpoints</h3>
<p>Our API will consist of the following endpoints, designed to support the functionality of the NewsFeed:</p>
<h4>Get Feed</h4>
<pre><code>
  // Endpoint to get the feed
  GET /api/v1/gql/feed
  input = {
    size: int,
    page: int,
    post_types: List[PostTypes]
  }
  headers = {
    user_id // Authentication and personalization
  }
  </code></pre>
<h4>Get Feed Item</h4>
<pre><code>
  // Endpoint to get a specific feed item
  GET /api/v1/gql/feed-item
  input = {
    post_id: int
  }
  headers = {
    user_id // Authentication and personalization
  }
  </code></pre>
<h4>Create Post</h4>
<pre><code>
  // Endpoint to create a new post
  POST /api/v1/gql/create-feed-post
  input = {
    title: str,
    media: List[Media]
  }
  </code></pre>
<p>These endpoints facilitate the fetching of the feed, individual feed items, and the creation of new posts. The &#8216;Get Feed&#8217; endpoint is optimized for paginated access, whereas &#8216;Get Feed Item&#8217; allows retrieval of detailed data for a single item, essential for deep dives into specific content.</p>
</section>
<section>
<h2>Data Store Strategy: Choosing Non-Normalization</h2>
<p>When structuring our client-side data store, we&#8217;re presented with two predominant approaches: normalized and non-normalized (regular). A normalized data store is akin to a relational database where each data type has its own &#8216;table,&#8217; and references are made via IDs, reducing data duplication. However, for our NewsFeed scenario, a regular data store structure appears to be more fitting due to specific characteristics of the feed.</p>
<h3>Advantages of a Regular Data Store for NewsFeed</h3>
<p>The decision to opt for a regular data store stems from several considerations specific to the nature of a NewsFeed:</p>
<ul>
<li><strong>Minimal Data Duplication:</strong> Except for user and author information, our feed data contains minimal repetition, thereby reducing the need for normalization.</li>
<li><strong>Content Consumption:</strong> Since the feed primarily serves for content consumption with few updates, the benefits of a normalized store for data consistency and update facilitation are less critical.</li>
<li><strong>Simple Interactions:</strong> User interactions such as likes typically affect only a single post, negating the need for complex state management across different entities.</li>
</ul>
<h3>Example of a Regular Data Store Structure</h3>
<pre><code>
  const feedStore = {
    pagination: {
      size: 10,
      next_cursor: "encoded-cursor-string"
    },
    results: [
      {
        id: "123",
        author: {
          id: "456",
          name: "John Doe"
        },
        content: "Hello world",
        image: "https://www.example.com/feed-images.jpg",
        reactions: {
          likes: 20,
          haha: 15
        },
        created_time: "2020-05-10T09:46:23+0000"
      }
      // ...additional posts
    ]
  };
  </code></pre>
<p>The structure above represents a segment of our feed store, illustrating how data would be organized in a standard format. This setup streamlines data access and manipulation within the client application, particularly suited for the mostly static nature of our NewsFeed content.</p>
</section>
<section>
<h2>Performance Optimizations</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-613" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.55.33-AM.png" alt="" width="1252" height="860" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.55.33-AM.png 1252w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.55.33-AM-300x206.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.55.33-AM-1024x703.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.55.33-AM-768x528.png 768w" sizes="(max-width: 1252px) 100vw, 1252px" /></p>
<p>Our NewsFeed aims for a seamless user experience, necessitating a deep dive into performance optimization techniques. Here&#8217;s how we&#8217;re approaching some critical aspects:</p>
<h3>Server-Side vs. Client-Side Rendering (SSR vs CSR)</h3>
<p>We employ a hybrid rendering approach to ensure a fast initial page load with Server-Side Rendering (SSR) for &#8216;above-the-fold&#8217; content, which may include the first set of posts. Subsequent content, as part of the infinite scrolling feature, will be loaded using CSR for a smooth user experience.</p>
<h3>Infinite Scrolling and Pagination</h3>
<p>Our infinite scrolling implementation utilizes the Intersection Observer API for its performance benefits and precision over traditional window scroll events. For pagination, we have opted for a cursor-based strategy due to the dynamic nature of the News Feed, where offset-based pagination could result in stale or inaccurate data representation.</p>
<h3>Virtualization and Recycling Nodes</h3>
<p>Virtualization techniques recycle DOM nodes to handle long lists efficiently, ensuring smooth scrolling without sacrificing performance.</p>
<h3>Code Splitting and Lazy Loading</h3>
<p>We leverage code splitting and lazy loading to reduce the initial load time, progressively loading features and content as needed. This extends to image loading, where images are lazy-loaded and prioritized based on their placement &#8216;above the fold&#8217;.</p>
<h3>Loaders, Shimmers, and Feedback States</h3>
<p>Shimmer effects are used as content placeholders during load times, providing a graceful transition until the content is fully loaded. Success and error states are handled to provide immediate feedback to the user.</p>
<h3>Rich Text Handling</h3>
<p>Rich text elements like mentions, hashtags, and stylized text are dynamically rendered to enable interactive and engaging posts.</p>
<h3>Image Optimization</h3>
<p>Images are served through a microservice that provides the appropriate sizes, and the srcset attribute lets browsers choose the most suitable image. Compression techniques and modern formats like WebP are utilized for optimal delivery.</p>
<p>The following code snippet showcases how these optimizations could be reflected in our NewsFeed&#8217;s frontend architecture:</p>
<pre><code>
  // Pseudo-code for image lazy-loading with srcset
  &lt;img
    src="placeholder.jpg"
    data-srcset="image-320w.jpg 320w,
                 image-480w.jpg 480w,
                 image-800w.jpg 800w"
    data-sizes="(max-width: 320px) 280px,
                (max-width: 480px) 440px,
                800px"
    class="lazyload" /&gt;
  </code></pre>
<p>This pseudo-code outlines the approach for responsive image loading, where different-sized images are provided for different viewport widths. The actual images are loaded only when they&#8217;re near the viewport, optimizing resource loading and rendering times.</p>
</section>
<section>
<h2>Commitment to Security and Accessibility</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-614" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.57.53-AM.png" alt="" width="928" height="884" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.57.53-AM.png 928w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.57.53-AM-300x286.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-11.57.53-AM-768x732.png 768w" sizes="(max-width: 928px) 100vw, 928px" /></p>
<h3>Accessibility Considerations</h3>
<p>Our NewsFeed embraces the core principles of web accessibility, making sure it is usable by as many people as possible:</p>
<ul>
<li><strong>Cross-Device Compatibility:</strong> Through rigorous testing, we ensure that the News Feed performs seamlessly across various devices and screen sizes.</li>
<li><strong>REM Font Sizes:</strong> We use scalable units for font sizes to support users’ preferences in text size and enhance readability.</li>
<li><strong>Proper Contrast:</strong> We maintain high contrast ratios in compliance with WCAG guidelines to aid users with visual impairments.</li>
<li><strong>Keyboard Navigation:</strong> Our NewsFeed is fully navigable via keyboard, a fundamental accessibility feature.</li>
<li><strong>Semantic HTML:</strong> Semantic HTML elements enable screen readers and assistive technologies to interpret page content effectively.</li>
<li><strong>ARIA Roles:</strong> Attributes like <code>role="feed"</code> and <code>role="article"</code> Provide additional context to assistive technologies, delineating the structure of the NewsFeed content.</li>
</ul>
<h3>Security Measures</h3>
<p>We implement robust security protocols to protect our users and their data:</p>
<ul>
<li><strong>XSS Protection:</strong> Our system sanitizes input data to prevent Cross-Site Scripting attacks, ensuring that only secure content is rendered to the user.</li>
<li><strong>CORS Policy:</strong> Proper Cross-Origin Resource Sharing (CORS) settings are in place to restrict and control resources shared between different domains.</li>
<li><strong>HTTPS:</strong> Secure Hypertext Transfer Protocol (HTTPS) is enforced for all data in transit, safeguarding against interceptions and ensuring data integrity.</li>
</ul>
<p>These accessibility and security practices are ingrained in every step of our development process, from design to deployment, ensuring that our NewsFeed is enjoyable and engaging and respects all users&#8217; privacy and needs.</p>
</section>
<footer>
<h2>Conclusion</h2>
<p>From the initial clarifying questions to a meticulous requirement analysis, we dove deep into high-level architectural choices, API intricacies, and strategic optimizations. We balanced the technological prowess with a strong commitment to accessibility and security, ensuring that the NewsFeed caters to a diverse user base while safeguarding user interactions.</p>
<p>As we conclude, we emphasize the importance of creating a scalable frontend.</p>
</footer>


---

## 13. Design Pintrest

- Difficulty: 🔴 Hard
- Subtitle: Designing an efficient, secure, Pinterest-like platform with user accessibility in focus
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01.webp

### Content

<header>
<h1>Designing a Pinterest-Style Masonry Grid Layout &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-617" src="https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01.webp" alt="" width="1600" height="817" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01.webp 1600w, https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01-300x153.webp 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01-1024x523.webp 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01-768x392.webp 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/masonry-in-css-01-1536x784.webp 1536w" sizes="(max-width: 1600px) 100vw, 1600px" /></p>
<p>In this piece, we&#8217;ll outline the system design process for creating a Pinterest-like platform. Pinterest is known for its captivating masonry grid layout that showcases a plethora of images, or &#8216;pins&#8217;. We aim to conceive a user interface that supports infinite scrolling and dynamically organizes content, delivering an immersive browsing experience reminiscent of Pinterest&#8217;s signature style.</p>
<p>Fun fact: We also offer to create the grid as a coding question, which can be found <a href="/frontend-coding-questions/masonry-grid">here</a>.</p>
</header>
<section>
<h2>Introduction</h2>
<p>You have been tasked with engineering a masonry grid layout for a web application that mirrors Pinterest&#8217;s fundamental design elements. This layout is characterized by its ability to arrange items of varying height in an aesthetically pleasing, staggered grid, optimizing the use of space and providing visual diversity. Additionally, it must support an ever-changing, fast-moving feed through infinite scrolling and cater to desktop and mobile users, regardless of their authentication status.</p>
</section>
<section>
<h3>Clarifying Questions</h3>
<p>Before diving into the design, clarifying several aspects with the interviewer is crucial to ensure the alignment of expectations and functionality. Here are some questions that would guide the design process:</p>
<ul>
<li><strong>Core Features:</strong> What interactive features are expected to be included in the feed beyond the masonry grid layout?</li>
<li><strong>Content Ordering:</strong> How should the pins be sorted within the feed? Is there an algorithm or set of criteria for prioritizing them?</li>
<li><strong>Supported Items:</strong> Will the pins be limited to image content, or will other media types need to be accommodated in the future?</li>
<li><strong>Device Compatibility:</strong> What are the specific design considerations for mobile users, and how does that affect the layout and interaction?</li>
<li><strong>Feed Accessibility:</strong> Are different content or features available for logged-in versus logged-out users?</li>
<li><strong>Feed Dynamics:</strong> How frequently is new content added to the feed, and how does this affect the caching strategy and the user&#8217;s perception of the feed&#8217;s freshness?</li>
<li><strong>Offline Support:</strong> Is there a requirement for users to access the content when they are offline?</li>
</ul>
<p>Note: While caching strategies are pivotal in optimizing the user experience, detailed discussions on normalized caching, cache TTL, and eviction policies are outside the scope of this particular exploration.</p>
</section>
<section>
<h2>Design Requirements for a Pinterest-Style Layout</h2>
<h3>Functional Requirements</h3>
<p>To build a Pinterest-like interface, the following functional specifications are key:</p>
<ul>
<li><strong>Masonry Grid Layout:</strong> Implement a masonry grid layout for displaying images in an overlapping pattern that maximizes space and varies in size.</li>
<li><strong>Responsive Images:</strong> Adapt images to various viewport sizes, serving different image resolutions based on the user&#8217;s device.</li>
<li><strong>Infinite Scrolling:</strong> This feature enables a seamless flow of content, allowing users to scroll through an ever-expanding collection of pins continuously.</li>
</ul>
<h3>Non-Functional Requirements</h3>
<p>The non-functional aspects of our system are equally critical to ensure an optimal user experience:</p>
<ul>
<li><strong>Rendering:</strong> Utilize Server-Side Rendering (SSR) for the initial page load to improve SEO and ensure a quick first paint, followed by Client-Side Rendering (CSR) for dynamic interactions and content loading.</li>
<li><strong>Server Responsibilities:</strong> The server renders the HTML, but computational work, such as calculating the position of pins within the layout, is managed client-side.</li>
<li><strong>API Design and Infinite Scrolling:</strong> Decide between offset-based scrolling and cursor-based scrolling. Implement intersection observers with a threshold value to trigger additional content loading.</li>
<li><strong>Virtualization:</strong> Employ virtualization techniques to recycle DOM nodes, optimizing memory usage and performance.</li>
<li><strong>Dynamic Layout:</strong> To maintain the masonry layout, calculate the number of columns and the size of the page dynamically based on viewport dimensions.</li>
</ul>
<h3>Masonry Layout Options</h3>
<pre><code>
  .masonry-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
  }
  </code></pre>
<p>For the masonry layout, we consider several CSS-based approaches, including grid, column, and absolute positioning. The goal is to determine the shortest column height to order the pins efficiently.</p>
<h3>Image Optimizations</h3>
<p>Image optimization strategies will be crucial, involving responsive images, appropriate compression techniques, and lazy loading to balance image quality and performance.</p>
</section>
<section>
<h2>Handling Edge Cases in Masonry Layout Design</h2>
<p>In designing our masonry grid layout, we must anticipate and gracefully handle various edge cases that could affect performance and user experience. Below are strategies to mitigate potential issues:</p>
<h3>Caching Strategies</h3>
<p>Implementing an intelligent caching mechanism allows us to preserve and reuse data, minimize redundant network requests, and speed up load times. However, we must consider the trade-offs between caching duration and content freshness.</p>
<h3>Loading States and Image Rendering</h3>
<p>Placeholder shimmers will indicate loading states, providing a visually appealing way to maintain the user&#8217;s attention during image loading. For slower connections, images should load in a prioritized order, starting with the most visually critical ones to sustain engagement.</p>
<h3>Minimizing Reflows and Repaints</h3>
<p>Reflows and repaints are resource-intensive processes that can lead to sluggish performance. To mitigate this, we can:</p>
<ul>
<li>Utilize Web Workers for off-thread calculations of layout dimensions.</li>
<li>Batch DOM changes to minimize reflows.</li>
<li>Leverage CSS transforms, which do not trigger reflows, for visual changes.</li>
</ul>
<h3>Virtualized Lists and Scroll Performance</h3>
<p>Implementing virtualized lists enables the rendering of only the visible items in the viewport, significantly improving scroll performance and reducing memory usage.</p>
<h3>Debouncing and Throttling</h3>
<p>We&#8217;ll implement debouncing and throttling techniques to prevent performance bottlenecks caused by rapid successive actions, such as scrolling.</p>
<h3>Error States for Failed Images</h3>
<p>When images fail to load, we&#8217;ll handle this gracefully by:</p>
<ul>
<li>Ignoring failed images and possibly removing them from the layout to prevent broken experiences.</li>
<li>Retrying image loads with exponential backoff to give them a chance to succeed under better network conditions.</li>
<li>Displaying user-friendly error messages that communicate the issue without compromising the overall aesthetic.</li>
</ul>
<p>By proactively addressing these edge cases, we ensure a more resilient and responsive system that maintains a high-quality user experience even under less-than-ideal circumstances.</p>
</section>
<section>
<h2>High-Level Architecture Design for a Pinterest-Style Application</h2>
<p>The architecture of our Pinterest-style application is centered around a client-server model that supports a dynamic, interactive masonry layout of pins. This design facilitates the efficient fetching and storing of data and the rendering of the user interface for an engaging experience.</p>
<figure><figcaption><strong>Component Architecture Overview:</strong></figcaption><img loading="lazy" decoding="async" class="alignnone size-full wp-image-616" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-12.17.05-PM.png" alt="" width="1346" height="956" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-12.17.05-PM.png 1346w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-12.17.05-PM-300x213.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-12.17.05-PM-1024x727.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-12.17.05-PM-768x545.png 768w" sizes="(max-width: 1346px) 100vw, 1346px" /></figure>
<h3>Client Components</h3>
<p>At the client level, the architecture is composed of:</p>
<ul>
<li><strong>Homepage View:</strong> The main container for the user interface, serving as the entry point for the application.</li>
<li><strong>Masonry Component:</strong> A specialized component responsible for laying out the pins in the masonry style. It incorporates logic to handle varying image sizes and aspect ratios for a seamless grid presentation.</li>
<li><strong>Feed Items:</strong> Individual pin components, each with its image and metadata, ready to be positioned within the masonry grid.</li>
</ul>
<h3>Client Store</h3>
<p>As a mediator between the client and server, the client store manages the state of the application, caching pins, and handling the state transitions invoked by user actions:</p>
<ul>
<li>Stores the current set of pins and the pagination state for infinite scrolling.</li>
<li>Receives updates when new pages of pins are fetched, appending them to the existing state.</li>
</ul>
<h3>Server Responsibilities</h3>
<p>The server&#8217;s primary role is to manage the API endpoints that provide the pins:</p>
<ul>
<li>Processes requests for new pages of pins to support infinite scrolling.</li>
<li>Handles server-side rendering for the initial load, optimizing for SEO and performance.</li>
<li>Serves the API that the client interacts with to fetch and send data, abstracting the computational workload from the client.</li>
</ul>
<p>Through this architecture, we aim to deliver a high-performing, scalable, and maintainable system, allowing users to enjoy a fluid and responsive browsing experience, akin to the Pinterest platform they know and love.</p>
</section>
<section>
<h2>API Design: Request and Response</h2>
<p>Our application employs a modern API architecture to handle data retrieval and manipulation. Here&#8217;s a closer look at the API request and response patterns, accommodating the infinite scrolling feature of our masonry grid layout:</p>
<h3>API Request</h3>
<p>The GET request facilitates the fetching of pins, supporting both authenticated (logged-in with JWT) and unauthenticated (logged-out) users:</p>
<pre><code>
  GET /api/feed
  Authorization: Bearer <em>your-jwt-token</em>
  Content-Type: application/json

  {
    "cursor": "<em>cursorID</em>", // Identifier for the last fetched item
    "size": <em>20</em> // Number of items to fetch
  }
  </code></pre>
<h3>API Response</h3>
<p>The response includes metadata about the fetch operation, such as the number of items retrieved and the cursor for the next batch. It also contains the actual data for the pins:</p>
<pre><code>
  HTTP/1.1 200 OK
  Content-Type: application/json

  {
    "fetched": 20,
    "nextCursor": "<em>nextCursorID</em>",
    "data": [
      {
        "id": "<em>uuid</em>",
        "created": "<em>ISO8601-timestamp</em>",
        "alt_text": "<em>Descriptive text for image</em>",
        "images": {
          "75": {
            "width": 75,
            "height": 100,
            "url": "<em>image-url-75px.jpg</em>"
          },
          "150": {
            "width": 150,
            "height": 200,
            "url": "<em>image-url-150px.jpg</em>"
          }
          // Additional image sizes...
        },
        "metadata": {
          // Additional metadata...
        }
      }
      // Additional feed items...
    ]
  }
  </code></pre>
<p>This request-response pattern supports the client&#8217;s need for progressive image loading, which caters to slower connections and optimizes the user experience.</p>
</section>
<section>
<h2>Constructing a Masonry Grid for a Pinterest-Style Layout</h2>
<p>When constructing a masonry grid layout akin to Pinterest, our focus is on implementing a resource-efficient and visually engaging arrangement. This layout should support image content&#8217;s dynamic and diverse dimensions, ensuring an optimal browsing experience.</p>
<h3>Initial Content Loading</h3>
<p>For the initial page load, we employ Server-Side Rendering (SSR) to deliver a page with the necessary markup and image tags for the pins. This strategy benefits SEO and provides a fast First Contentful Paint. The serialized JSON data of the pins will be injected into the client store, eliminating the need for additional API calls post-load.</p>
<h3>Masonry Grid Implementation Options</h3>
<p>We have identified two primary approaches to implement the masonry grid:</p>
<h4>Column-Based Approach</h4>
<pre><code>
  &lt;div class="container"&gt;
    &lt;div class="column"&gt;
      &lt;div class="item"&gt;1&lt;/div&gt;
      &lt;div class="item"&gt;2&lt;/div&gt;
    &lt;/div&gt;
    &lt;div class="column"&gt;
      &lt;div class="item"&gt;3&lt;/div&gt;
      &lt;div class="item"&gt;4&lt;/div&gt;
    &lt;/div&gt;
    &lt;!-- More columns and items --&gt;
  &lt;/div&gt;
  </code></pre>
<p>This approach is straightforward to implement with CSS flex or grid, but it alters the DOM order to column-first, potentially impacting keyboard navigation for accessibility.</p>
<h4>Absolute Positioning Approach</h4>
<pre><code>
  &lt;div class="container"&gt;
    &lt;div class="item" style="transform: translate(0px, 0px);"&gt;1&lt;/div&gt;
    &lt;div class="item" style="transform: translate(80px, 0px);"&gt;2&lt;/div&gt;
    &lt;!-- More items with transformed positions --&gt;
  &lt;/div&gt;
  </code></pre>
<p>This approach maintains the DOM order and keyboard navigation flow. It is also more conducive to virtualization. The downside is the need for complex calculations to determine item positioning, which must be recalculated upon resize.</p>
<h3>Dynamic Content Placement</h3>
<p>We consider a height-balanced algorithm for content ordering that distributes pins across the shortest column, optimizing for visual balance. This algorithm can be implemented in JavaScript and executed on a secondary thread using web workers to prevent blocking the main thread.</p>
<h3>Performance and Optimization Techniques</h3>
<p>Key to the masonry layout&#8217;s performance is the handling of reflows and repaints. We aim to minimize these expensive operations through techniques such as:</p>
<ul>
<li>Using transforms for positioning instead of top/left properties to leverage hardware acceleration.</li>
<li>Debouncing window resize events to limit layout recalculations.</li>
<li>Batching DOM updates to avoid forced synchronous layouts.</li>
</ul>
<p>Here&#8217;s a simplified example of the height-balanced pin placement logic:</p>
<pre><code>const arrangeHeightBalanced = (pins) =&gt; {
    const pins = [
		{ height: 160, id: 1 },
		{ height: 70, id: 2 },
		{ height: 130, id: 3 },
		{ height: 160, id: 4 },
	];

	const NUM_COLS = 3;
	const GAP = 10;
	const COL_WIDTH = 70;

	function arrangeHeightBalanced(pins) {
		const columnHeights = Array(NUM_COLS).fill(0);
		// For each pin, augment with position data.
		return pins.map((pin) =&gt; {
			// Find the shortest column.
			let shortestCol = 0;
			for (let i = 1; i &amp; NUM_COLS; i++) {
			if (columnHeights[i] &amp; columnHeights[shortestCol]) {
				shortestCol = i;
			}

			// Calculate the `left` value of the current pin.
			const left = shortestCol * COL_WIDTH + Math.max(shortestCol, 0) * GAP;
			// Calculate the `top` value of the current pin.
			const top = GAP + columnHeights[shortestCol];
			// Update the column height.
			columnHeights[shortestCol] = top + pin.height;

			return {
				...pin,
				left,
				top,
				width: COL_WIDTH,
			};
		});
	}
}
  </code></pre>
<p>By strategically applying these techniques, our masonry grid will be performant across devices, offering an aesthetically pleasing and smooth user experience.</p>
</section>
<section>
<h2>Optimizing Images for a Pinterest-Style Masonry Grid</h2>
<p>Optimizing image delivery and rendering is paramount in a visually driven platform. We aim to provide a seamless experience for users, minimizing load times while maintaining high image quality. Below, we outline the strategies for image optimization:</p>
<h3>Preloading Off-Screen Images</h3>
<p>Images just outside the viewport are preloaded to ensure a smooth scrolling experience for users:</p>
<pre><code>
  &lt;link rel="preload" href="image-path.jpg" as="image"&gt;
  </code></pre>
<h3>Progressive Image Loading</h3>
<p>Starting with the smallest image size and progressively loading higher resolutions helps in enhancing perceived performance:</p>
<pre><code>
  &lt;img src="low-res.jpg" srcset="med-res.jpg 2x, high-res.jpg 3x" alt="descriptive text"&gt;
  </code></pre>
<h3>Using the `loading` Attribute</h3>
<p>The `loading` attribute of the `img` tag is leveraged to control the loading behavior of images:</p>
<pre><code>
  &lt;img src="image-path.jpg" loading="lazy" alt="descriptive text"&gt;
  </code></pre>
<h3>Responsive Image Delivery</h3>
<p>Responsive images are delivered using the `srcset` attribute, allowing the browser to select the most appropriate image size:</p>
<pre><code>
  &lt;img src="default.jpg" srcset="small.jpg 320w, medium.jpg 480w, large.jpg 800w" sizes="(max-width: 320px) 280px, (max-width: 480px) 440px, 800px" alt="descriptive text"&gt;
  </code></pre>
<h3>Styling for Unloaded Images</h3>
<p>To ensure the layout doesn&#8217;t jump when images load, we maintain aspect ratio using CSS:</p>
<pre><code>
  img {
    aspect-ratio: 4 / 3;
    width: 100%;
    object-fit: cover;
  }
  </code></pre>
<h3>Content Delivery Networks (CDN)</h3>
<p>A regional-based CDN strategy is used to reduce latency and improve load times for users worldwide.</p>
<p>These optimizations ensure that images are loaded efficiently and at the highest quality necessary, based on the user&#8217;s current context and device capabilities, enhancing the overall user experience.</p>
</section>
<section>
<h2>Addressing Edge Cases in Image Rendering</h2>
<p>Optimal image rendering on a visually driven platform is crucial for user retention, especially for users on slower connections. We tackle various edge cases to ensure the UI remains responsive and visually engaging:</p>
<h3>Paint Scheduling for Slower Connections</h3>
<p>We utilize paint scheduling to control when images are painted to the screen. The steps include:</p>
<ol>
<li>Loading data containing pins from the server.</li>
<li>Calculating the masonry layout.</li>
<li>Preloading images off the DOM using JavaScript <code>new Image()</code> and setting the <code>src</code> attribute.</li>
<li>Coordinating the painting of images to the screen once they are fully loaded, to maintain a smooth visual flow.</li>
</ol>
<h3>Painting Approaches</h3>
<p>We evaluate different painting approaches to find the optimal solution for our application:</p>
<ul>
<li><strong>Default Rendering:</strong> Rendering all the <code>img</code> tags as soon as they are loaded can result in a disjointed experience on slow connections.</li>
<li><strong>Sequential Load and Paint:</strong> Loading and painting images one after the other is inefficient and leads to a subpar user experience.</li>
<li><strong>Parallel Load, Single Paint:</strong> Loading images in parallel but painting them all at once can lead to unnecessary user wait times.</li>
<li><strong>Parallel Load, Ordered Paint:</strong> <em>This is the preferred approach.</em> Images are loaded in parallel but painted in the order they appear on the feed. This is achieved using a mechanism like React.Suspense ensures a smooth visual transition as images become ready to display.</li>
</ul>
<p>Through these strategies, we aim to enhance the images&#8217; loading and rendering process, providing users with a seamless browsing experience that is both efficient and visually pleasing, regardless of their connection speed.</p>
</section>
<section>
<h2>Optimization Strategies for a High-Performance Application</h2>
<p>For our masonry grid layout application, we prioritize performance and user experience through various network and rendering optimizations:</p>
<h3>Network Optimizations</h3>
<ul>
<li><strong>Caching:</strong> Implement an LRU (Least Recently Used) cache strategy for local storage to manage data efficiently, with a set limit to prevent overuse of client-side resources.</li>
<li><strong>Image Delivery:</strong> Use a CDN to serve images, prefer WebP format for better compression, and fall back to JPEG if necessary. Employ SVGs for icons and a microservice to deliver the right image size based on the client&#8217;s requirements.</li>
<li><strong>HTTP/2 Features:</strong> Leverage multiplexing to batch multiple requests and utilize compression headers to minimize the data transferred over the network.</li>
<li><strong>Data Transfer Optimization:</strong> Implement gzip or Brotli compression to reduce the bandwidth required for resource delivery.</li>
</ul>
<h3>Rendering Optimizations</h3>
<ul>
<li><strong>Code Efficiency:</strong> Use bundle splitting to load only the necessary code, employ lazy loading for off-screen images and non-critical code paths, and utilize tree shaking to eliminate dead code.</li>
<li><strong>Resource Prioritization:</strong> Focus on loading critical resources first and defer the rest, ensuring a quick Time To Interactive (TTI) and improving overall performance.</li>
<li><strong>Virtualization:</strong> Apply techniques to render only the items in the viewport, reducing the rendering load and memory consumption.</li>
<li><strong>User Interaction Optimization:</strong> Rate limit user-initiated actions using debounce and throttle techniques to reduce unnecessary processing and network requests.</li>
<li><strong>Styling and User Feedback:</strong> Implement CSS-in-JS for component-scoped styles and utilize loaders and success/error states to provide visual feedback to the user.</li>
<li><strong>Modern Practices:</strong> Minimize the use of polyfills by relying on modern web standards supported by the latest browsers, reducing the application&#8217;s overhead and bloat.</li>
</ul>
<p>These optimizations ensure the application loads quickly and remains interactive and responsive, providing an excellent user experience across a wide range of devices and network conditions.</p>
</section>
<section>
<h2>Ensuring Security, Accessibility, and Observability in Web Applications</h2>
<h3>Accessibility Considerations</h3>
<ul>
<li><strong>Semantic HTML:</strong> Use elements according to their intended purpose to ensure content structure is accessible to screen readers.</li>
<li><strong>ARIA Labels and Roles:</strong> Implement ARIA roles and properties to enhance the screen reader experience, for example, using <code>role="listbox"</code> for lists and <code>role="combobox"</code> for input fields with auto-complete functionality.</li>
<li><strong>Keyboard Navigation:</strong> Ensure all interactive elements are focusable and navigable using a keyboard, with proper <code>tabindex</code> management.</li>
</ul>
<h3>Security Measures</h3>
<ul>
<li><strong>Cross-Site Scripting (XSS) Protection:</strong> Sanitize user input to prevent the execution of malicious scripts. Most modern frameworks provide built-in XSS protection.</li>
<li><strong>Content Security Policy (CSP):</strong> Define a CSP to restrict resources to known safe sources and mitigate certain types of attacks, such as data injection attacks.</li>
<li><strong>Cross-Origin Resource Sharing (CORS):</strong> Configure CORS policies to control which cross-origin requests are permitted, preventing unwanted web pages from pulling resources or making API requests.</li>
</ul>
<h3>Observability and Monitoring</h3>
<ul>
<li><strong>Application Performance Monitoring:</strong> Utilize tools like Datadog or Sentry for real-time monitoring, error tracking, and operational visibility.</li>
<li><strong>Logging:</strong> Implement comprehensive logging with structured data to provide insights into application behavior and user interactions.</li>
<li><strong>Performance Metrics:</strong> Track key performance indicators such as load times, API response times, and user engagement to assess and improve the application continually.</li>
</ul>
<p>By integrating these security and accessibility practices, alongside robust observability systems, we can create a web application that is user-friendly and maintains the highest standards of security and performance monitoring.</p>
</section>


---

## 14. Rich Text Editor

- Difficulty: 🟠 Medium
- Subtitle: Enhancing Rich Text Editors: Debouncing and Caching for Optimal Performance.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.21.07-PM-1.png

### Content

<header>
<h1>Design WYSIWYG Rich Text Editor &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-620" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.21.07-PM.png" alt="" width="958" height="344" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.21.07-PM.png 958w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.21.07-PM-300x108.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.21.07-PM-768x276.png 768w" sizes="(max-width: 958px) 100vw, 958px" /></p>
<p>In this exploration, we are tasked with designing a WYSIWYG (What You See Is What You Get) text editor, a fundamental tool allowing users to edit and create content in a format that closely mirrors its appearance when published. This editor will provide both basic and advanced editing capabilities, catering to a wide range of user needs.</p>
<p>&nbsp;</p>
</header>
<section>
<h2>Clarifying Questions</h2>
<p>Before diving into the design, it&#8217;s essential to clarify several aspects to ensure the editor meets user expectations and technical feasibility. The following questions will guide our design process:</p>
<ul>
<li><strong>Supported Content Types:</strong> What range of content types (text, images, videos, GIFs, tables, etc.) should the editor support?</li>
<li><strong>Media Handling:</strong> How will the editor manage media uploads, including size limitations and storage?</li>
<li><strong>Collaborative Editing:</strong> Is collaborative editing required, and how will simultaneous changes be managed?</li>
<li><strong>Customizability:</strong> To what extent should the editor allow custom styles or plugins?</li>
<li><strong>Export Options:</strong> In which formats can users export their content?</li>
<li><strong>Mentions and Tags:</strong> Should the editor support user mentions and tags, and how are they integrated?</li>
<li><strong>Accessibility:</strong> What are the accessibility considerations to ensure the editor is usable by everyone?</li>
<li><strong>Performance:</strong> What performance benchmarks should the editor achieve, especially with large documents or rich media?</li>
<li><strong>Cross-Browser Compatibility:</strong> Which browsers and their versions must be supported?</li>
<li><strong>Mobile Experience:</strong> How will the editor adapt to mobile devices, and are there specific features or considerations for mobile users?</li>
</ul>
<p>&nbsp;</p>
</section>
<section>
<h2>Requirements</h2>
<h3>Functional Requirements</h3>
<p>The WYSIWYG text editor should offer a comprehensive set of features that enable users to create rich content effortlessly. Key functional requirements include:</p>
<ul>
<li><strong>Block Style Elements:</strong> Support for various block-style elements such as headings, block quotes, lists, figures, and pre-formatted text.</li>
<li><strong>Inline Style Elements:</strong> Capabilities to edit text inline with styles like bold, italic, underline, and text color adjustments.</li>
<li><strong>Advanced Content:</strong> Ability to insert and manage advanced content like images, videos, GIFs, tables, and hyperlinks.</li>
<li><strong>Interactivity:</strong> Features such as mentioning users with the &#8220;@&#8221; symbol, adding tags, and creating links.</li>
<li><strong>Editing Features:</strong> Standard editing features including undo/redo capabilities, text alignment, and bulleting.</li>
</ul>
<h3>Non-Functional Requirements</h3>
<p>To ensure a seamless and accessible user experience, the editor must also meet the following non-functional criteria:</p>
<ul>
<li><strong>Cross-Browser Compatibility:</strong> The editor should work consistently across major browsers without significant differences in functionality or appearance.</li>
<li><strong>Accessibility:</strong> Adherence to web accessibility standards to ensure the editor is usable by individuals with varying abilities.</li>
<li><strong>Performance:</strong> The editor should remain responsive and efficient, even with complex documents or on lower-end devices.</li>
<li><strong>Technical Implementation Options:</strong> Consideration of various implementation strategies, including:
<ul>
<li><em>Text Area Element:</em> Basic but limited to text-only content, suitable for simpler use cases.</li>
<li><em>Controlled Content Editable:</em> Utilizes the <code>contenteditable</code> attribute for rich text editing with good cross-browser support but requires customization for consistent behavior.</li>
<li><em>Manual DOM Elements:</em> Offers the highest level of customizability at the cost of reimplementing many native browser features.</li>
</ul>
</li>
</ul>
<p>Choosing the right technical approach will depend on the specific needs and priorities of the editor, balancing customizability with development complexity and user experience.</p>
<p>&nbsp;</p>
</section>
<section>
<h2>High-Level Architecture</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-619" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM.png" alt="" width="860" height="1264" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM.png 860w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM-204x300.png 204w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM-697x1024.png 697w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM-768x1129.png 768w" sizes="(max-width: 860px) 100vw, 860px" /></p>
</section>
<p>&nbsp;</p>
<p>The high-level architecture for a WYSIWYG rich text editor can be segmented into several key components, each responsible for distinct aspects of the editor’s functionality. The architecture diagram outlines the separation of concerns and depicts how user interactions are processed and rendered.</p>
<p><strong>Server and GraphQL (GQL) Layer</strong> The server forms the backbone of the rich text editor, interacting with the database and file storage systems to save and retrieve content. GraphQL sits as an intermediary between the server and client, providing a flexible API layer that allows the client to request exactly the data it needs. This can include not just the text content but also metadata, such as user permissions, versioning information, and linked multimedia resources.</p>
<p><strong>Model</strong> The Model represents the data structure and business logic of the editor. It stores the document state, including text, formatting attributes, and any embedded media. This state can be serialized for storage and transmitted to the server. The Model also exposes methods to manipulate the editor&#8217;s content programmatically, enabling operations like insertions, deletions, and formatting changes.</p>
<p><strong>Controller</strong> The Controller mediates interactions between the View and the Model. It handles user input, processes commands, and mediates the rendering of the content. The Controller receives events from the View, interprets them, and makes corresponding state changes to the Model. It ensures that the user&#8217;s intentions, as expressed through interactions with the View, are accurately reflected in the editor&#8217;s data model.</p>
<p><strong>Views</strong> The Views are the visual representation of the Model&#8217;s data. The Input Field View is the primary interface where users type and format their content. It listens for input events and requests the necessary updates from the Controller. The Popover View serves as an auxiliary interface for additional features like link editing or media insertion, providing a contextual UI that appears in response to specific user actions.</p>
<p><strong>Interactors</strong> Interactors (Field Interactor and Popover Interactor) are the conduits through which the Views communicate with the Controller. They listen for user actions, such as keystrokes, mouse clicks, or touch events, and translate them into operations on the Model via the Controller. The Interactors are also responsible for reflecting the state of the Model back onto the Views, ensuring the UI remains in sync with the underlying data.</p>
<p>&nbsp;</p>
<article>
<section>
<h2>Data Model</h2>
<p>The data model for the editor is a crucial aspect that dictates how text changes are processed and stored. Here is an interface that illustrates the structure and types of the editor&#8217;s properties, ensuring a controlled and predictable state.</p>
<pre><code>
interface MessageInputProps {
  // Interactions
  onChange?: (currentTextJSON: string) =&gt; void;
  onSelect?: (selectedObject: any) =&gt; void;
  onBlur?: (event: Event) =&gt; void;
  autoFocus: boolean;
  onFetchResults: (page: number, size: number, type: string) =&gt; void;

  // Styling
  placeholder: string;
  resultsRender: JSX.Element;
  styling: StyleObject;
  className: string;

  // Network-related
  debounceInterval: number;
  showEmptyResults: boolean;
  cacheTTL: number;
  cacheType: 'in network' | 'apollo' | 'local' | 'session' | 'none';
  networkTimeoutDuration: number; // in milliseconds
  networkRetries: int;
}
    </code></pre>
</section>
</article>
<section>
<h2>Implementation Options</h2>
<table>
<thead>
<tr>
<th>Option</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>Use text area input field</td>
<td>
<ul>
<li>Multiline support</li>
<li>Unlimited characters</li>
<li>Handles text input out of the box</li>
<li>Browser support</li>
</ul>
</td>
<td>
<ul>
<li>Does not support rich text content</li>
<li>Have to absolute position edited elements</li>
</ul>
</td>
</tr>
<tr>
<td>Use contentEditable</td>
<td>
<ul>
<li>Supported by most browsers</li>
<li>Support for native cursor</li>
<li>Native input events, key bindings</li>
<li>Accessibility friendly</li>
</ul>
</td>
<td>
<ul>
<li>Need to customize rendering per browser</li>
<li>Customized model required for state mapping</li>
<li>UI consistency across browsers</li>
<li>Complex manual build, cross-device issues</li>
</ul>
</td>
</tr>
<tr>
<td>External Library (Lexical/Draft.js)</td>
<td>
<ul>
<li>Battle-tested across platforms</li>
<li>Extensive API</li>
<li>Supports @mentions and hashtags</li>
<li>Rich text support</li>
<li>Accessibility friendly</li>
</ul>
</td>
<td>
<ul>
<li>Limited customization</li>
<li>Dependency on external code</li>
<li>Increased code size</li>
</ul>
</td>
</tr>
</tbody>
</table>
<h3>Why Option 3 is the Best Choice</h3>
<p>Considering the needs for a robust, feature-rich, and user-friendly WYSIWYG editor, Option 3, utilizing an external library like Lexical or Draft.js, emerges as the best choice. While this option may introduce a dependency on external code and potentially increase the overall code size, the advantages it offers far outweigh these drawbacks.</p>
<p>Lexical and Draft.js are battle-tested libraries that provide a wide array of features out-of-the-box, including rich text capabilities and support for modern web interactions like @mentions and hashtags. Furthermore, these libraries are designed with accessibility in mind, ensuring that the editor is usable for all individuals, regardless of their abilities.</p>
<p>The extensive APIs offered by these libraries simplify the implementation of complex editing features, while their compatibility across different platforms and browsers ensures a consistent user experience. Although customization might be somewhat limited compared to building a solution from scratch, the trade-off is a more reliable and maintainable codebase that leverages the collective knowledge and expertise of the developer community.</p>
</section>
<p>&nbsp;</p>
<article>
<h1>Optimizing a WYSIWYG Rich Text Editor</h1>
<section>
<h2>Debouncing User Input</h2>
<p>To enhance performance and reduce unnecessary load, user input can be debounced. This technique involves waiting for a certain amount of idle time before processing input, thereby limiting the rate at which events like keystrokes trigger updates in the editor state or re-rendering of the component.</p>
<p>Implementing debouncing ensures that the system is not overwhelmed by the high frequency of user actions, which is particularly beneficial when these actions lead to complex processing tasks or network requests, like fetching suggestions for @mentions or updating the live preview of the content.</p>
<pre><code>
function debounce(func, wait) {
  let timeout;

  return function executedFunction(...args) {
    const later = function() {
      clearTimeout(timeout);
      func(...args);
    };

    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
  };
};

// Usage with a function that updates the editor state
const debouncedUpdate = debounce(updateEditorState, 250);
    </code></pre>
</section>
<section>
<h2>Caching Strategy</h2>
<p>Caching is a crucial optimization strategy for a WYSIWYG editor. It allows us to store previously retrieved or computed data, such as user input, images, or document snapshots, so that future requests for the same data can be served faster.</p>
<p>The editor can implement a caching layer that stores the state of the editor or parts of it in memory. It can also persist data locally on the client&#8217;s machine using browser caching mechanisms like LocalStorage, IndexedDB, or Service Workers, which is particularly useful for offline capabilities and to quickly restore the state when the user returns to the editor.</p>
<pre><code>
// Example of a simple in-memory cache implementation
class EditorCache {
  constructor() {
    this.cache = {};
  }

  get(key) {
    return this.cache[key];
  }

  set(key, value) {
    this.cache[key] = value;
  }
}

const cache = new EditorCache();
// Store and retrieve the editor state
cache.set('editorState', editorState);
const cachedState = cache.get('editorState');
    </code></pre>
<p>The caching strategy also involves setting a Time To Live (TTL) for cached items and implementing an eviction policy, such as Least Recently Used (LRU), to manage memory efficiently.</p>
<p>&nbsp;</p>
</section>
</article>
<section>
<h2>Conclusion</h2>
<p>In crafting an efficient WYSIWYG rich text editor, the careful application of debouncing and caching strategies is essential. Debouncing smooths out the event-driven nature of user interactions, providing a performant and responsive editing experience without overloading the system with rapid-fire updates. Meanwhile, caching harnesses the ability to swiftly recall and reuse previously accessed data, accelerating load times and fostering a seamless user experience, even in offline scenarios.</p>
<p>These optimization techniques, when applied judiciously, ensure that the editor not only meets the functional requirements of modern web applications but does so with an eye towards scalability, resilience, and user satisfaction. The balance between real-time responsiveness and system performance is delicate, and with these strategies, we tip the scales in favor of an editor that is both powerful and a pleasure to use.</p>
</section>


---

## 15. Design mentions

- Difficulty: 🟠 Medium
- Subtitle: Explore efficient @mentions handling in rich text editors' nuanced design.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.26.51-PM.png

### Content

<h1>Design @mentions and #hashtags &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-624" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.26.51-PM.png" alt="" width="804" height="600" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.26.51-PM.png 804w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.26.51-PM-300x224.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.26.51-PM-768x573.png 768w" sizes="(max-width: 804px) 100vw, 804px" /></p>
<p>For this exercise, let&#8217;s construct an article structured around the task of building a system to support <code>@mentions</code> and <code>hashtags</code> within a WYSIWYG rich text editor, a common feature in modern social platforms and collaborative tools.</p>
<p>Please do note, @mentions and rich text editor share a lot of common features, please do check out rich text editor <a href="https://frontendlead.com/system-design/rich-text-editor">here</a>.</p>
<p><strong>Introduction</strong></p>
<p>In the dynamic landscape of web applications, the integration of <code>@mentions</code> and <code>hashtags</code> within text editors has evolved from a luxury to a near necessity. As developers, we are often tasked with creating systems that not only perform these functions but do so efficiently, accessibly, and across various devices and languages. This article will navigate through the construction of such a system, addressing the common functional and non-functional requirements, and highlighting optimizations and security measures necessary for a robust implementation.</p>
<p>Full Diagram can be found <a href="https://lucid.app/documents/view/f919934a-ed77-49f8-a6de-47bc82d05dc3">here</a>.</p>
<h2><strong>Clarifying Questions</strong></h2>
<ul>
<li>How should the system differentiate and prioritize <code>@mentions</code> vs. <code>hashtags</code>?</li>
<li>What user data should be displayed in <code>@mention</code> results?</li>
<li>At what user input threshold should the system begin querying for results?</li>
<li>Should the list of mentions or hashtags support infinite scrolling?</li>
<li>How frequently will the results be updated from the server?</li>
<li>Are there any preferences on the latency and load performance?</li>
</ul>
<h2><strong>Functional Requirements</strong></h2>
<ul>
<li>Support for rich text formatting, including bold, italics, and hyperlinks.</li>
<li>Seamless integration of <code>@mention</code> and <code>#hashtag</code> functionality within the text editor.</li>
<li>Displaying a popover list for both mentions and hashtags with real-time search results.</li>
<li>Navigational links in popovers that redirect to detailed user profiles or hashtag summaries.</li>
<li>Real-time updates to mention and hashtag lists based on the latest server data.</li>
</ul>
<h2><strong>Non-Functional Requirements</strong></h2>
<ul>
<li>Implement efficient caching strategies to minimize server hits and enhance user experience.</li>
<li>Decide between Server-Side Rendering (SSR) and Client-Side Rendering (CSR) based on initial load performance and SEO considerations.</li>
<li>Mobile responsiveness to ensure usability across various devices.</li>
<li>Pagination support, with a discussion on the merits of offset vs cursor-based approaches.</li>
<li>High performance with low latency, potentially leveraging debouncing and normalized caching.</li>
<li>Internationalization support for a global user base.</li>
<li>Accessibility considerations, ensuring compliance with ARIA standards and cross-browser compatibility.</li>
<li>Offline mode functionality, serving cached results when no network connection is available.</li>
<li>Observability measures to track and optimize system performance and user interactions.</li>
<li>Appropriate HTTP protocol selection to match the real-time or batched data requirements.</li>
</ul>
<h2><strong>Edgecases</strong></h2>
<p>Building a system to support <code>@mentions</code> and <code>hashtags</code> requires careful consideration of various edge cases to ensure a seamless user experience. Here are some potential edge cases and approaches for handling them:</p>
<h2><strong>Handling Deletions</strong></h2>
<p>When a user decides to remove an <code>@mention</code> or a <code>#hashtag</code>, the system should:</p>
<ul>
<li>Recognize the deletion in real time and remove any associated styling or interactive elements.</li>
<li>If part of a <code>mention</code> or <code>hashtag</code> is deleted, consider the entire entity as removed to avoid partial tags.</li>
<li>Update the list of mentions or hashtags accordingly if they are being tracked or counted.</li>
</ul>
<h2><strong>Handling Undos</strong></h2>
<p>Undo functionality is vital in text editing. For <code>@mentions</code> and <code>hashtags</code>:</p>
<ul>
<li>Implement a stack to keep track of user actions to allow a step-by-step undo process.</li>
<li>Ensure that undoing an action restores the previous state entirely, including text and associated metadata.</li>
</ul>
<h2><strong>Handling New Searches</strong></h2>
<p>When a user initiates a new search by typing <code>@</code> or <code>#</code>:</p>
<ul>
<li>Immediately trigger a debounce function to avoid overloading the server with requests during rapid typing.</li>
<li>Cancel any ongoing searches that are no longer relevant.</li>
<li>Display a loading state to inform the user that a search is in progress, if necessary.</li>
</ul>
<section>
<h2>High-Level Architecture</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-619" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM.png" alt="" width="860" height="1264" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM.png 860w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM-204x300.png 204w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM-697x1024.png 697w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-23-at-2.07.09-PM-768x1129.png 768w" sizes="(max-width: 860px) 100vw, 860px" /></p>
</section>
<p>&nbsp;</p>
<p>The high-level architecture for a WYSIWYG rich text editor can be segmented into several key components, each responsible for distinct aspects of the editor’s functionality. The architecture diagram outlines the separation of concerns and depicts how user interactions are processed and rendered.</p>
<p><strong>Server and GraphQL (GQL) Layer</strong> The server forms the backbone of the rich text editor, interacting with the database and file storage systems to save and retrieve content. GraphQL sits as an intermediary between the server and client, providing a flexible API layer that allows the client to request exactly the data it needs. This can include not just the text content but also metadata, such as user permissions, versioning information, and linked multimedia resources.</p>
<p><strong>Model</strong> The Model represents the data structure and business logic of the editor. It stores the document state, including text, formatting attributes, and any embedded media. This state can be serialized for storage and transmitted to the server. The Model also exposes methods to manipulate the editor&#8217;s content programmatically, enabling operations like insertions, deletions, and formatting changes.</p>
<p><strong>Controller</strong> The Controller mediates interactions between the View and the Model. It handles user input, processes commands, and mediates the rendering of the content. The Controller receives events from the View, interprets them, and makes corresponding state changes to the Model. It ensures that the user&#8217;s intentions, as expressed through interactions with the View, are accurately reflected in the editor&#8217;s data model.</p>
<p><strong>Views</strong> The Views are the visual representation of the Model&#8217;s data. The Input Field View is the primary interface where users type and format their content. It listens for input events and requests the necessary updates from the Controller. The Popover View serves as an auxiliary interface for additional features like link editing or media insertion, providing a contextual UI that appears in response to specific user actions.</p>
<p><strong>Interactors</strong> Interactors (Field Interactor and Popover Interactor) are the conduits through which the Views communicate with the Controller. They listen for user actions, such as keystrokes, mouse clicks, or touch events, and translate them into operations on the Model via the Controller. The Interactors are also responsible for reflecting the state of the Model back onto the Views, ensuring the UI remains in sync with the underlying data.</p>
<h2>API Design</h2>
<p>Our API design ensures seamless integration of @mentions and other dynamic content within a WYSIWYG rich text editor. Using GraphQL, we provide flexible and efficient querying capabilities.</p>
<h3>GraphQL API Endpoints</h3>
<ul>
<li><strong>Fetching Mentions:</strong>
<pre><code>query getMention($MentionInput) {
  id,
  type,
  title,
  url,
  photo,
  ... // additional metadata
}</code></pre>
</li>
<li><strong>Fetching Profile Data:</strong>
<pre><code>query getProfile($input) {
  name,
  photo
}</code></pre>
</li>
<li><strong>Fetching Room Data:</strong>
<pre><code>query getRoom($input) {
  name,
  photo
}</code></pre>
</li>
<li><strong>Creating Mentions with Content:</strong>
<pre><code>mutation createMessage($input) {
  text,
  metadata
}</code></pre>
</li>
</ul>
<p>The APIs are authenticated using JWT headers, ensuring security and personalization. Whether we incorporate a WYSIWYG editor or not, our API design caters to the creation and retrieval of content-rich mentions.</p>
<section>
<h2>Data Model</h2>
<p>The data model for the editor is a crucial aspect that dictates how text changes are processed and stored. Here is an interface that illustrates the structure and types of the editor&#8217;s properties, ensuring a controlled and predictable state.</p>
<pre><code>
interface MessageInputProps {
  // Interactions
  onChange?: (currentTextJSON: string) =&gt; void;
  onSelect?: (selectedObject: any) =&gt; void;
  onBlur?: (event: Event) =&gt; void;
  autoFocus: boolean;
  onFetchResults: (page: number, size: number, type: string) =&gt; void;

  // Styling
  placeholder: string;
  resultsRender: JSX.Element;
  styling: StyleObject;
  className: string;

  // Network-related
  debounceInterval: number;
  showEmptyResults: boolean;
  cacheTTL: number;
  cacheType: 'in network' | 'apollo' | 'local' | 'session' | 'none';
  networkTimeoutDuration: number; // in milliseconds
  networkRetries: int;
}
    </code></pre>
</section>
<section>
<h2>Implementation Options</h2>
<table>
<thead>
<tr>
<th>Option</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>Use text area input field</td>
<td>
<ul>
<li>Multiline support</li>
<li>Unlimited characters</li>
<li>Handles text input out of the box</li>
<li>Browser support</li>
</ul>
</td>
<td>
<ul>
<li>Does not support rich text content</li>
<li>Have to absolute position edited elements</li>
</ul>
</td>
</tr>
<tr>
<td>Use contentEditable</td>
<td>
<ul>
<li>Supported by most browsers</li>
<li>Support for native cursor</li>
<li>Native input events, key bindings</li>
<li>Accessibility friendly</li>
</ul>
</td>
<td>
<ul>
<li>Need to customize rendering per browser</li>
<li>Customized model required for state mapping</li>
<li>UI consistency across browsers</li>
<li>Complex manual build, cross-device issues</li>
</ul>
</td>
</tr>
<tr>
<td>External Library (Lexical/Draft.js)</td>
<td>
<ul>
<li>Battle-tested across platforms</li>
<li>Extensive API</li>
<li>Supports @mentions and hashtags</li>
<li>Rich text support</li>
<li>Accessibility friendly</li>
</ul>
</td>
<td>
<ul>
<li>Limited customization</li>
<li>Dependency on external code</li>
<li>Increased code size</li>
</ul>
</td>
</tr>
</tbody>
</table>
<h3>Why Option 3 is the Best Choice</h3>
<p>Considering the needs for a robust, feature-rich, and user-friendly WYSIWYG editor, Option 3, utilizing an external library like Lexical or Draft.js, emerges as the best choice. While this option may introduce a dependency on external code and potentially increase the overall code size, the advantages it offers far outweigh these drawbacks.</p>
<p>Lexical and Draft.js are battle-tested libraries that provide a wide array of features out-of-the-box, including rich text capabilities and support for modern web interactions like @mentions and hashtags. Furthermore, these libraries are designed with accessibility in mind, ensuring that the editor is usable for all individuals, regardless of their abilities.</p>
<p>The extensive APIs offered by these libraries simplify the implementation of complex editing features, while their compatibility across different platforms and browsers ensures a consistent user experience. Although customization might be somewhat limited compared to building a solution from scratch, the trade-off is a more reliable and maintainable codebase that leverages the collective knowledge and expertise of the developer community.</p>
</section>
<p>&nbsp;</p>
<h1>Optimizations</h1>
<section>
<h2>Debouncing User Input</h2>
<p>To enhance performance and reduce unnecessary load, user input can be debounced. This technique involves waiting for a certain amount of idle time before processing input, thereby limiting the rate at which events like keystrokes trigger updates in the editor state or re-rendering of the component.</p>
<p>Implementing debouncing ensures that the system is not overwhelmed by the high frequency of user actions, which is particularly beneficial when these actions lead to complex processing tasks or network requests, like fetching suggestions for @mentions or updating the live preview of the content.</p>
<pre><code>
function debounce(func, wait) {
  let timeout;

  return function executedFunction(...args) {
    const later = function() {
      clearTimeout(timeout);
      func(...args);
    };

    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
  };
};

// Usage with a function that updates the editor state
const debouncedUpdate = debounce(updateEditorState, 250);
    </code></pre>
</section>
<section>
<h2>Caching Strategy</h2>
<p>Caching is a crucial optimization strategy for a WYSIWYG editor. It allows us to store previously retrieved or computed data, such as user input, images, or document snapshots, so that future requests for the same data can be served faster.</p>
<p>The editor can implement a caching layer that stores the state of the editor or parts of it in memory. It can also persist data locally on the client&#8217;s machine using browser caching mechanisms like LocalStorage, IndexedDB, or Service Workers, which is particularly useful for offline capabilities and to quickly restore the state when the user returns to the editor.</p>
<pre><code>
// Example of a simple in-memory cache implementation
class EditorCache {
  constructor() {
    this.cache = {};
  }

  get(key) {
    return this.cache[key];
  }

  set(key, value) {
    this.cache[key] = value;
  }
}

const cache = new EditorCache();
// Store and retrieve the editor state
cache.set('editorState', editorState);
const cachedState = cache.get('editorState');
    </code></pre>
<p>The caching strategy also involves setting a Time To Live (TTL) for cached items and implementing an eviction policy, such as Least Recently Used (LRU), to manage memory efficiently.</p>
<p>&nbsp;</p>
</section>
<h2>Rendering @mentions</h2>
<p>Our rich text editor implements a sophisticated text rendering method that enhances plain text with dynamic features using metadata. The <code>renderText</code> function works in three distinct steps:</p>
<ol>
<li><strong>Read Text:</strong> The function begins by reading the provided text input, which is the base content without any formatting.</li>
<li><strong>Iterate Through Metadata:</strong> The next step is to iterate through the metadata array, applying the specified transformations to the text. For each piece of metadata, which contains offset and length, the function extracts the substring from the text and wraps it with an HTML element to apply the desired style or interaction. This could mean wrapping the text in a <code>&lt;strong&gt;</code> tag for bold styling, a <code>&lt;a&gt;</code> tag for links, or custom elements for mentions and hashtags.</li>
<li><strong>Return the Styled Characters:</strong> Finally, the function assembles the processed text fragments back into a single string, which represents the fully styled text ready to be displayed in the editor or on the webpage.</li>
</ol>
<pre><code>function renderText(text, metadata) {
  // Initial steps...
  // Styling and interaction application...
  // Return processed text...
}</code></pre>
<p>This method provides a seamless and interactive user experience, allowing for rich content creation within the editor.</p>
<article>
<h2>Edge Case Management for @mentions and #hashtags</h2>
<section>
<h3>Rendering Results Popover</h3>
<p>Ensuring the results popover for @mentions and #hashtags appears correctly involves two main positioning strategies:</p>
<ul>
<li><strong>Relative to Parent:</strong> This approach uses <code>position: absolute</code> on the results, which is simple and easy to implement. However, developers must be mindful of potential <code>z-index</code> issues.</li>
<li><strong>React Portals:</strong> Leveraging React Portals can help manage overflow and <code>z-index</code> issues by rendering the popover outside of the DOM hierarchy. This method requires careful manual calculations for positioning.</li>
</ul>
</section>
<section>
<h3>Network Optimization</h3>
<p>To handle network efficiency when users search for mentions or hashtags, a combination of debouncing and caching is essential.</p>
<ul>
<li><strong>Debounce Input:</strong> By implementing a debounce function, unnecessary API calls can be minimized, triggering requests only after a set idle time after the user has stopped typing.</li>
<li><strong>Caching with TTL:</strong> Utilizing caching mechanisms with Time To Live (TTL) settings helps to serve repeated requests swiftly without overloading the server.</li>
<li><strong>Normalized Data Store:</strong> A normalized data store can ensure efficient memory usage and remove data duplication by storing results based on unique identifiers.</li>
</ul>
</section>
<section>
<h3>User Interaction Handling</h3>
<p>Addressing user interactions such as deletions, undos, and new searches is critical for a seamless user experience.</p>
<ul>
<li><strong>Handling Deletions:</strong> When the user hits backspace, the editor must intelligently detect if it&#8217;s within the metadata range and update the UI accordingly.</li>
<li><strong>Handling Undos:</strong> Keeping a stack of user actions allows the editor to easily revert to previous states when the undo action is triggered.</li>
<li><strong>Handling New Searches:</strong> The editor must be able to handle new searches dynamically, showing relevant suggestions based on the latest input.</li>
</ul>
</section>
<footer>Exploring these edge cases ensures that our implementation of @mentions and #hashtags is robust, user-friendly, and efficient in terms of network and rendering performance.</footer>
<footer></footer>
</article>
<footer>
<h2></h2>
<h2>Conclusion</h2>
<p>Designing a rich text editor that supports @mentions and #hashtags is a nuanced task, which involves careful consideration of UI/UX design, network efficiency, and robust handling of user interactions. This article has delved into several edge cases and presented practical solutions for each, including the use of React Portals for UI placement, debouncing, and caching strategies for network optimization, and algorithmic approaches for dynamic content interaction. As we aim to provide a seamless and intuitive editing experience, these considerations are pivotal in building a feature-rich and performant application that meets the needs of modern web interactions.</p>
</footer>


---

## 16. Build ChatGPT (Frontend)

- Difficulty: 🔴 Hard
- Subtitle: Build the frontend architecture for ChatGPT.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48.png

### Content

<h1>Build ChatGPT &#8211; Frontend System Design Guide</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1825" src="https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48.png" alt="Design ChatGPT - Frontend System Design" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48.png 1920w, https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2025/06/FrontendLead-48-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<p>We’ll walk through the frontend system design for building a ChatGPT-style web application. Our goal is to design an interface that lets users enter prompts, stream responses word by word, maintains a conversation history, and optionally supports model switching (for example, toggling between GPT-3.5 and GPT-4). We’ll focus on building a frontend that’s fast, scalable, and production-ready, capable of serving millions of users with smooth, real-time experiences. You’ll see estimates for scale, functional requirements, and the key non-functional criteria that make for a robust, user-friendly AI chat app.</p>
<hr />
<h2>Requirements</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1815" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.01.19-AM.png" alt="Build GPT Requirements" width="450" height="435" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.01.19-AM.png 450w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.01.19-AM-300x290.png 300w" sizes="(max-width: 450px) 100vw, 450px" /></p>
<ol>
<li><strong>Prompt input:</strong> User enters a prompt.</li>
<li><strong>Streaming response:</strong> Chat response streams words word by word, similar to ChatGPT.</li>
<li><strong>Conversation history:</strong> Threads of past chats per user.</li>
<li><strong>Model switching (optional):</strong> Choose between GPT-3.5, GPT-4, etc.</li>
</ol>
<h2>Scalability Estimates</h2>
<table border="1" cellspacing="0" cellpadding="6">
<thead>
<tr>
<th>Metric</th>
<th>Estimate</th>
<th>Calculation</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr>
<td>Daily Active Users (DAUs)</td>
<td>10M</td>
<td>10 million users per day</td>
<td></td>
</tr>
<tr>
<td>Conversations per User</td>
<td>5</td>
<td>10M x 5 = 50M conversations/day</td>
<td></td>
</tr>
<tr>
<td>Messages per Conversation</td>
<td>4</td>
<td>50M x 4 = 200M messages/day</td>
<td></td>
</tr>
<tr>
<td>Average Message Size</td>
<td>100 bytes</td>
<td>200M x 100 bytes = 20GB/day</td>
<td>~7.3TB/year</td>
</tr>
<tr>
<td>Database Requirements</td>
<td>Scalable (NoSQL/Replica DBs)</td>
<td>&#8211;</td>
<td>Must handle read-heavy workloads, suggest using Redis for caching</td>
</tr>
</tbody>
</table>
<h2>Non-Functional Requirements</h2>
<ul>
<li>Real-time streaming (low latency)</li>
<li>High availability</li>
<li>Scalable backend</li>
<li>Secure data handling</li>
<li>Mobile-responsive UI</li>
<li>Rate limiting or usage limits</li>
<li>Fallback for slow networks/retry</li>
<li>Performance</li>
</ul>
<hr />
<h2>Frontend Architecture Overview</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1816" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.05.40-AM.png" alt="ChatGPT Frontend Architecture " width="1093" height="1056" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.05.40-AM.png 1093w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.05.40-AM-300x290.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.05.40-AM-1024x989.png 1024w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.05.40-AM-768x742.png 768w" sizes="(max-width: 1093px) 100vw, 1093px" /></p>
<p>Let’s break down how to architect a robust, scalable frontend for ChatGPT. The goal is to create a web app that feels instant, smooth, and reliable—even under massive user load. We want users to feel like they’re chatting with an assistant in real-time, with instant feedback, seamless navigation, and a persistent conversation history. To deliver this, we combine modern React design patterns, real-time data streaming, and a focus on security and performance.</p>
<p>At a high level, the system follows a modular approach. Each core responsibility—such as message input, chat history, and response streaming—lives in its own React component, making the app easier to maintain and extend. Data flow is predictable and managed using a central state store, usually implemented with React Context, Redux, or Zustand. All data fetching and mutation routes go through a dedicated Network Manager module, which keeps side effects outside the view layer. Let’s dive into each area in detail.</p>
<h3>Component Structure and Responsibilities</h3>
<p>The frontend is made up of composable React components that each handle a specific part of the UI or workflow. Here’s a breakdown of the major components and their responsibilities:</p>
<ul>
<li><strong>App:</strong> The root component. Handles top-level state, authentication, and initial data fetches. Renders child components for chat windows, navigation, and message input.
<pre><code>
&lt;App&gt;
  &lt;ChatWindow /&gt;
  &lt;MessageList /&gt;
  &lt;TypingIndicator /&gt;
  &lt;MessageInput /&gt;
  &lt;ChatWindows /&gt;
&lt;/App&gt;
    </code></pre>
</li>
<li><strong>ChatWindow:</strong> Displays the active conversation, including both user and assistant messages. Manages infinite scroll for older messages and updates as new responses stream in.</li>
<li><strong>MessageList:</strong> A virtualized list of all messages in the current chat. Designed for efficiency, it only renders what’s visible on screen, allowing for fast scrolling, even with thousands of messages.</li>
<li><strong>TypingIndicator:</strong> Animates as the assistant types out each response. Connects to the real-time streaming logic, allowing users to see responses appear word by word.</li>
<li><strong>MessageInput:</strong> Where users type their prompts. Handles keyboard shortcuts, input sanitization, and triggers message sends.</li>
<li><strong>SendMessageBtn:</strong> The action button to submit a new prompt. Integrates reCAPTCHA or similar anti-abuse checks to prevent bots or spam.</li>
<li><strong>ConvosContainer:</strong> Allows users to view all their past conversations. Includes features like infinite scroll, search, and quick switching between threads.</li>
</ul>
<h3>Network Layer and Data Management</h3>
<p>A Network Manager manages all API requests and streaming connections. This module abstracts away the details of HTTP requests and Server-Sent Events (SSE), so the rest of the app doesn’t have to worry about transport logic. It also centralizes error handling, retries, and analytics tracking, ensuring a consistent user experience.</p>
<ul>
<li><strong>Network Manager:</strong> Handles:
<ul>
<li>Fetching conversation lists and message history</li>
<li>Sending user prompts to the backend</li>
<li>Receiving streamed responses from the server</li>
<li>Managing auth headers and API tokens</li>
<li>Tracking performance, errors, and user analytics</li>
</ul>
</li>
</ul>
<p>State management is handled through a central store, using either React Context, Redux, or Zustand. This global state holds conversation threads, user metadata, loading and error states, and UI preferences. It enables any component to react to updates and keeps the UI in sync with the backend.</p>
<h3>Streaming Response Workflow</h3>
<p>A standout feature of ChatGPT is its real-time response streaming. Instead of waiting for a full reply, users see each word or token appear as soon as the backend model generates it. This is usually implemented with Server-Sent Events (SSE) or WebSockets.</p>
<ol>
<li>The user enters a prompt in <strong>MessageInput</strong> and clicks send.</li>
<li><strong>Network Manager</strong> sends the prompt to the backend.</li>
<li>The backend starts generating the response and pushes each token as it becomes available.</li>
<li>The frontend listens to the SSE stream, updating <strong>the MessageList</strong> in real-time as each new word arrives.</li>
<li>If the user switches threads or navigates away, the stream is paused or cancelled to save resources.</li>
</ol>
<p>This approach feels much faster to users and mirrors a real conversation. It also requires careful handling of partial messages, error states, and UI updates.</p>
<h3>Conversation History and Virtualization</h3>
<p>Users expect their conversation history to be instantly available, even across thousands of chats. The frontend stores a list of recent threads, including metadata such as timestamps and model version. When a user opens a thread, the app fetches only a window of messages, loading older messages on demand with infinite scroll. This keeps the initial page load light and fast, even for power users.</p>
<ul>
<li>Recent chats are shown using a <strong>ConvosContainer</strong> component, often with search and filter options.</li>
<li>Each chat is displayed in a <strong>ChatWindow</strong>, utilizing a virtualized <strong>MessageList</strong> to render large numbers of messages efficiently.</li>
<li>Intersection observers detect when to load more messages or prefetch upcoming ones.</li>
</ul>
<hr />
<h2>State and Data Flow</h2>
<p>A predictable data flow is crucial for reliability and maintainability. Here’s a typical flow:</p>
<ol>
<li>User action triggers a state update (e.g., sending a prompt or switching threads).</li>
<li>Network requests are fired through the Network Manager.</li>
<li>Response streams are received and update the global store.</li>
<li>UI components subscribe to store changes and update reactively.</li>
<li>All errors and loading states are surfaced in the UI so the user always knows what’s happening.</li>
</ol>
<p>This separation of concerns makes debugging easier and ensures that all network or side-effect logic stays out of the UI components.</p>
<h3>Performance, Prefetching, and Caching</h3>
<p>With high user volume and chatty interfaces, performance matters. Several strategies keep the app fast:</p>
<ul>
<li><strong>Virtualized lists:</strong> Both message lists and chat lists only render what’s visible. This keeps scrolling smoothly, even with thousands of messages.</li>
<li><strong>Prefetching:</strong> When a user hovers over or opens a conversation, the app preloads data in the background to enhance performance. This minimizes perceived latency.</li>
<li><strong>Intelligent caching:</strong> Frequently accessed data, like recent threads and user profiles, is cached in-memory or in local storage. Expiry policies and background refreshes ensure freshness without over-fetching.</li>
<li><strong>Bundle splitting and lazy loading:</strong> Load UI components and libraries only when needed. For example, advanced input editors or media handlers load on demand.</li>
<li><strong>Client-side error boundaries:</strong> Ensure that a crash in one component doesn’t take down the whole app. Surface-friendly error messages and allow users to recover.</li>
</ul>
<h3>Security and Input Sanitization</h3>
<p>Security is built in from the start. All user inputs are sanitized before rendering to prevent cross-site scripting (XSS) attacks. Because chat content might include HTML, code, or links, the frontend escapes all potentially dangerous characters. In React, this is typically handled automatically, but extra checks are used for any raw HTML.</p>
<ul>
<li><strong>Rate limiting:</strong> Prevents bots from spamming the chat endpoint. The <strong>SendMessageBtn</strong> disables rapidly after each send and re-enables after a short delay.</li>
<li><strong>reCAPTCHA integration:</strong> Used before sending the request to the backend to ensure it is human.</li>
<li><strong>Content sanitization:</strong> Every user message is cleaned before it’s sent and before it’s rendered.</li>
</ul>
<h3>Mobile Responsiveness and Accessibility</h3>
<p>The frontend is designed to be mobile-first. All layouts are adaptable to different screen sizes, featuring touch-friendly controls and responsive type sizes. Keyboard navigation, ARIA labels, and screen reader support make the app accessible to everyone. Core functions, such as entering a prompt, navigating threads, and viewing message history, are fully operable with the keyboard alone.</p>
<ul>
<li><strong>Accessible buttons and inputs:</strong> All interactive elements use proper roles and labels.</li>
<li><strong>Graceful error states:</strong> Users always get clear, actionable feedback if something goes wrong.</li>
<li><strong>Localizations:</strong> The app can support multiple languages and right-to-left layouts.</li>
</ul>
<h3>Extensible Input and Rich Content</h3>
<p>ChatGPT isn’t just plain text. Users may want to send images, code blocks, or rich-formatted messages. The frontend supports two types of editors:</p>
<table border="1" cellspacing="0" cellpadding="6">
<thead>
<tr>
<th>Component</th>
<th>Purpose</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr>
<td>Extranea</td>
<td>Handles plain text, supports emojis, auto-grows for multiline input, and is cross-browser compatible. Always sanitize input.</td>
<td>Safe by default. Used for basic chat UI.</td>
</tr>
<tr>
<td>ContentEditable</td>
<td>Enables rich content: code blocks, images, WYSIWYG editing, and custom embeds.</td>
<td>More complex, used for advanced or enterprise chat features.</td>
</tr>
</tbody>
</table>
<h2>Data Flow Summary</h2>
<p>The following steps summarize the complete frontend flow for a ChatGPT message exchange:</p>
<ol>
<li>The user opens the app and loads recent conversations. Only metadata is fetched initially.</li>
<li>The user selects or starts a conversation. The relevant messages are fetched and displayed using a virtualized list.</li>
<li>The user types a prompt and clicks send. The message is sanitized, rate-limited, and verified as human via reCAPTCHA.</li>
<li>The prompt is sent to the backend using the Network Manager. The UI immediately shows a pending message with a typing indicator.</li>
<li>The backend streams the response as tokens become available. The UI updates the chat window word by word, keeping the user engaged.</li>
<li>If the connection fails, the frontend retries the request or shows an error with a retry button.</li>
<li>Once complete, the message is saved to history, and the input field is reset for the following prompt.</li>
</ol>
<h3>Best Practices and Final Thoughts</h3>
<ul>
<li>Keep components modular and responsibilities clear. Avoid tightly coupled logic.</li>
<li>Always separate network effects from view logic using a dedicated manager or hooks.</li>
<li>Prefer optimistic UI updates where possible for instant feedback.</li>
<li>Utilize virtualization and prefetching to achieve scalable performance at any user scale.</li>
<li>Invest early in accessibility and mobile-friendliness. It pays off as usage grows.</li>
<li>Review all input and output handling for security and be proactive in sanitizing data.</li>
</ul>
<hr />
<h2>Data Model</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1817" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.15.08-AM.png" alt="ChatGPT Frontend Data Model - Frontend System Design" width="408" height="390" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.15.08-AM.png 408w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.15.08-AM-300x287.png 300w" sizes="(max-width: 408px) 100vw, 408px" /></p>
<p>The data model needs to be simple, fast to query, and easy to extend. At minimum, we need to support conversation threads, messages, and basic user info. Messages must support streaming, threading, and system metadata.</p>
<h3>Core Types</h3>
<pre><code>
// Preview of a conversation in the list
type ConversationPreview = {
  id: string;
  title: string;
  updated_at: string;
};

// Full conversation details
type FullConversation = ConversationPreview &amp; {
  model: string;           // e.g. "gpt-4"
  temperature: number;     // sampling parameter
  notes?: string;          // user notes (optional)
};

// Message object
type Message = {
  id: string;                   // unique identifier
  conversation_id: string;      // foreign key to Conversation
  user_id?: string;             // present for users
  ip_address?: string;          // for anonymous usage
  text: string;                 // message content
  gpt_response: boolean;        // true if generated by GPT
  parent_message_id?: string;   // for threaded replies
  created_at: string;           // ISO timestamp
  rating?: number;              // optional score (e.g. 1–5)
};</code><code></code></pre>
<hr />
<h2>API Endpoints</h2>
<ul>
<li><code>GET /conversations</code> – Returns a list of <code>ConversationPreview</code> for the user.</li>
<li><code>GET /conversations/{id}/messages</code> – Returns an array of <code>Message</code> for a conversation.</li>
<li><code>POST /conversations/{id}/messages</code> – Adds a new message (user prompt).</li>
</ul>
<h3>Message Streaming Format</h3>
<p>The backend streams message data as each token is generated. The frontend consumes these events in real time.</p>
<pre><code>
// Message event stream format
data: {
  "id": "...",
  "choices": [
    {
      "delta": {
        "content": "Hello "
      }
    }
  ]
}

data: {
  "choices": [
    {
      "delta": {
        "content": "world"
      }
    }
  ]
}

data: [DONE]
</code></pre>
<h3>Notes</h3>
<ul>
<li>Each message has an <code>id</code> for easy updates and threading.</li>
<li><code>gpt_response</code> flags AI-generated vs user messages.</li>
<li><code>parent_message_id</code> Supports reply threads and future group chat features.</li>
<li>Streaming allows the UI to update as each chunk arrives. <code>[DONE]</code> Signals completion.</li>
</ul>
<hr />
<h2>API Design</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1818" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.11-AM.png" alt="Design ChatGPT - Frontend System Design API Design" width="576" height="709" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.11-AM.png 576w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.11-AM-244x300.png 244w" sizes="(max-width: 576px) 100vw, 576px" /></p>
<p>The API should support standard CRUD operations for conversations and messages, as well as a real-time streaming endpoint for responses. For the chat streaming experience, using <strong>Server-Sent Events (SSE)</strong> is preferred. SSE allows the server to push each token or chunk as soon as it is ready, providing users with immediate feedback and a smoother user interface. Every API should use explicit, predictable request and response shapes. Authentication is handled via an auth token in the header.</p>
<h3>Endpoints</h3>
<table border="1" cellspacing="0" cellpadding="6">
<thead>
<tr>
<th>Action</th>
<th>Method &amp; Endpoint</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Create Conversation</td>
<td>POST /v1/conversation</td>
<td>Create a new chat thread. Returns <code>{ id }</code> for the new conversation.</td>
</tr>
<tr>
<td>Delete Conversation</td>
<td>DELETE /v1/conversation/{id}</td>
<td>Remove a chat thread for a user. Returns <code>{ success }</code>.</td>
</tr>
<tr>
<td>View Conversations</td>
<td>GET /v1/conversations?cursor=&#8230;&amp;limit=20</td>
<td>List recent conversations (paginated). Returns array of <code>ConversationPreview</code>.</td>
</tr>
<tr>
<td>View Conversation with Messages</td>
<td>GET /v1/conversation/{id}/messages?cursor=&#8230;&amp;limit=20</td>
<td>Fetch a full conversation and its messages. Returns <code>{ conversation, messages, nextCursor }</code>.</td>
</tr>
<tr>
<td>Send Message (Streaming)</td>
<td>POST /v1/conversation/{id}/message</td>
<td>Sends a user prompt and streams the response from the backend.<br />
<strong>Headers:</strong> <code>authToken, Idempotency-Key, Accept: text/event-stream</code><br />
<strong>Body:</strong> <code>{ text, timestamp }</code><br />
<strong>Response:</strong> Each token/chunk streamed as an SSE event.<br />
<strong>Example stream:</strong></p>
<pre><code>
data: {"id":"...","choices":[{"delta":{"content":"Hello "}}]}
data: {"choices":[{"delta":{"content":"world"}}]}
data: [DONE]
        </code></pre>
</td>
</tr>
<tr>
<td>Rate Message</td>
<td>POST /v1/conversation/{id}/message/rating</td>
<td>Send feedback or a rating for a message. Body: <code>{ score }</code>. Returns <code>{ success }</code>.</td>
</tr>
</tbody>
</table>
<h3>Notes on Streaming with SSE</h3>
<ul>
<li>For streaming chat responses, Server-Sent Events (SSE) is preferred over regular HTTP fetch. SSE allows the backend to send each chunk as soon as it&#8217;s ready, maintaining the strict order. The client receives and renders each piece immediately.</li>
<li>All message events follow a simple, predictable JSON structure, allowing the frontend to update the chat view in real-time.</li>
<li>Use an <code>Idempotency-Key</code> header on message POSTs to prevent accidental duplicate sends.</li>
<li>When the backend is done streaming, it sends a <code>data: [DONE]</code> signal to completion.</li>
<li>All endpoints require an <code>authToken</code> header for security.</li>
<li>Pagination is handled via <code>cursor</code>  <code>limit</code> Parameters for listing messages and conversations.</li>
</ul>
<h3>Example: Consuming SSE on the Frontend</h3>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1819" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.27-AM.png" alt="ChatGPT Streaming Response - Frontend System Design" width="805" height="731" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.27-AM.png 805w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.27-AM-300x272.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.18.27-AM-768x697.png 768w" sizes="(max-width: 805px) 100vw, 805px" /></p>
<pre><code>
// Set up SSE connection
const eventSource = new EventSource('/api/conversation/stream');

eventSource.onmessage = (event) =&gt; {
  const parsed = JSON.parse(event.data);
  if (parsed.choices) {
    updateLastMessage(parsed.choices[0].delta.content);
  } else if (event.data === "[DONE]") {
    eventSource.close();
  }
};
</code></pre>
<p>SSE ensures each token is delivered in strict sequence over TCP. This keeps the chat experience smooth and in order. For browsers or environments that don&#8217;t support SSE, consider a fallback to <code>fetch</code> with <code>ReadableStream</code> for token-wise updates.</p>
<hr />
<h2>Streaming Optimizations</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1820" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.21.43-AM.png" alt="Design ChatGPT - Frontend System Design Streaming Optimizations" width="678" height="541" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.21.43-AM.png 678w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.21.43-AM-300x239.png 300w" sizes="(max-width: 678px) 100vw, 678px" /></p>
<p>Smooth, real-time chat streaming is key for a great user experience. To keep the UI responsive and reduce unnecessary work, we need to optimize both the frontend and backend streaming pipelines.</p>
<h3>Frontend Streaming Strategies</h3>
<ul>
<li><strong>Avoid React re-renders per token.</strong> Instead of updating React state every token, use a ref or <code>innerHTML</code> to append tokens directly.</li>
<li><strong>Token buffering.</strong> Buffer 10–20 tokens, then update the DOM in one batch. This reduces rendering overhead, keeping scrolling smooth.</li>
<li><strong>Animation frame scheduling.</strong> Use <code>requestIdleCallback</code> or <code>requestAnimationFrame</code> to schedule DOM updates for best performance.</li>
<li><strong>Pause streaming in background tabs.</strong> Use <code>document.visibilityState</code> to detect when the tab is hidden and pause updates.</li>
</ul>
<h4>Sample Implementation</h4>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1821" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.21.40-AM.png" alt="ChatGPT - Frontend System Design UseEffect" width="413" height="474" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.21.40-AM.png 413w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.21.40-AM-261x300.png 261w" sizes="(max-width: 413px) 100vw, 413px" /></p>
<pre><code>
// In your chat container component
const [tokenBuffer, setTokenBuffer] = useState&lt;string[]&gt;([]);
const flushRef = useRef(false);

useEffect(() =&gt; {
  let animationFrameId: number;
  const flushTokens = () =&gt; {
    if (flushRef.current &amp;&amp; tokenBuffer.length &gt; 0) {
      const snapshot = [...tokenBuffer];
      setTokenBuffer([]); // clear buffer
      setRenderedMessage(prev =&gt; prev + snapshot.join(""));
      flushRef.current = false;
    }
    animationFrameId = requestAnimationFrame(flushTokens);
  };
  animationFrameId = requestAnimationFrame(flushTokens);
  return () =&gt; cancelAnimationFrame(animationFrameId);
}, [tokenBuffer]);

// In your SSE event listener:
eventSource.onmessage = (event) =&gt; {
  const newToken = event.data;
  flushRef.current = true;
  setTokenBuffer(prev =&gt; [...prev, newToken]);
};</code><code>
</code></pre>
<hr />
<h3>Backend Streaming Optimization</h3>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1823" src="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.24.42-AM.png" alt="Design ChatGPT - Frontend System Design Optimizations" width="700" height="471" srcset="https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.24.42-AM.png 700w, https://api.frontendlead.com/wp-content/uploads/2025/06/Screenshot-2025-06-13-at-9.24.42-AM-300x202.png 300w" sizes="(max-width: 700px) 100vw, 700px" /></p>
<ul>
<li><strong>Chunked transfer encoding.</strong> For Express/Node.js, use <code>res.write()</code> and <code>res.flush()</code> to stream tokens to the client as soon as they’re available.</li>
<li><strong>Token batching.</strong> Group tokens together (for example, send every 50 milliseconds) to reduce I/O overhead.</li>
<li><strong>Backpressure control.</strong> Monitor the client’s buffer size. If the client is slow, pause token generation (for WebSocket) or skip writes.</li>
</ul>
<h3>Latency Minimization</h3>
<ul>
<li><strong>Edge functions.</strong> Use platforms like Vercel or Cloudflare Workers to reduce time-to-first-byte (TTFB).</li>
<li><strong>Stream-start optimizations.</strong> Start emitting tokens as soon as the first token is ready. If model latency is high, pre-fill the first token (using a fake-typing fallback).</li>
</ul>
<p>&nbsp;</p>
<hr />
<h2>Handling User Edge Cases</h2>
<table border="1" cellspacing="0" cellpadding="6">
<thead>
<tr>
<th>Case</th>
<th>Strategy</th>
</tr>
</thead>
<tbody>
<tr>
<td>❌ User sends empty or spam input</td>
<td>Debounce and validate input. Reject if empty or too short.</td>
</tr>
<tr>
<td>❌ User sends multiple chats fast</td>
<td>Use <code>AbortController</code> to cancel prior requests before starting new ones.</td>
</tr>
<tr>
<td>🔄 User reloads tab</td>
<td>Persist the session in localStorage or the backend for seamless resumption.</td>
</tr>
<tr>
<td>🔁 Retry/Regenerate</td>
<td>Save prompt/metadata in a queue to allow retrying or regenerating failed messages.</td>
</tr>
<tr>
<td>📶 Network loss</td>
<td>Graceful SSE/WebSocket reconnection using <code>Last-Event-ID</code> or message ID to resume streaming without duplicates.</td>
</tr>
<tr>
<td>⏳ Token expired</td>
<td>Prompt user to re-authenticate and retry the last request automatically.</td>
</tr>
<tr>
<td>🚫 Abuse/spam</td>
<td>Add rate limits per IP address or user ID and block VPNs or proxies as needed.</td>
</tr>
</tbody>
</table>
<h3>Bonus UX Enhancements</h3>
<ul>
<li>Partial Markdown rendering: Highlight code blocks as they stream in.</li>
<li>Smart autoscroll: Only scroll to the bottom if the user is already there, avoid interrupting mid-scroll.</li>
<li>Typing placeholder: Show “GPT is typing&#8230;” animation for better user feedback.</li>
</ul>
<h3>Pro-Level Optimizations</h3>
<table border="1" cellspacing="0" cellpadding="6">
<thead>
<tr>
<th>Area</th>
<th>Suggestion</th>
</tr>
</thead>
<tbody>
<tr>
<td>Streaming Smoothness</td>
<td>Use <code>requestAnimationFrame</code> batching when appending many tokens to avoid layout thrashing.</td>
</tr>
<tr>
<td>Typing Indicator</td>
<td>Debounce display if the user types very fast. Hide onBlur or after a short timeout.</td>
</tr>
<tr>
<td>Retry Logic</td>
<td>On SSE disconnect, use the <code>Last-Event-ID</code> header to resume the stream without losing progress.</td>
</tr>
<tr>
<td>Client Memory</td>
<td>Clear out-of-view messages in the virtualized list. Optionally set a <code>maxRenderCount</code> for lower memory usage.</td>
</tr>
<tr>
<td>Analytics Hook</td>
<td>Add a hook on each token render or user interaction for tools like Mixpanel.</td>
</tr>
<tr>
<td>Mobile</td>
<td>Adjust the virtual list to prevent input field overlap when the mobile keyboard opens (a common issue).</td>
</tr>
</tbody>
</table>
<hr />
<h2>Conclusion</h2>
<p>Building a modern ChatGPT frontend is all about creating a fast, scalable, and user-friendly chat experience. We broke down the key requirements, from core architecture and data modeling to API design, streaming strategies, and user edge case handling. Each decision—from using SSE for real-time streams to virtualizing message lists and optimizing for mobile—directly impacts how users experience the app at scale.</p>
<p>The best frontend systems anticipate real-world usage patterns. They gracefully handle network hiccups, edge cases, and high user volume. By focusing on efficient rendering, robust input validation, and smooth streaming, you ensure the UI feels responsive at all times. Pro-level details like animation batching, session persistence, and Markdown support add polish that users notice.</p>
<p>With this system design, you’re set up to deliver a ChatGPT frontend that feels modern, reliable, and ready for millions of users. Focus on simplicity, clarity, and performance, and you’ll build an experience that stands out in the AI chat landscape.</p>


---

## 17. Design Airbnb

- Difficulty: 🟠 Medium
- Subtitle: Design a Airbnb like frontend for scale.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45.png

### Content

<h1>Design Airbnb &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1717" src="https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45.png" alt="Design Airbnb - Frontend System Design" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/06/FrontendLead-45-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<h2>Problem Statement</h2>
<blockquote><p>Build the frontend for a hotel booking website.</p>
<p>Requirements:</p>
<ul>
<li>Display a grid of hotels or houses available for booking</li>
<li>Each grid tile should show a slideshow of images (image carousel), the property title, and the price per night</li>
<li>The layout should be fully responsive and look good on both desktop and mobile devices</li>
<li>Users should be able to scroll within each property’s images to view a slideshow</li>
</ul>
<p>Describe your approach to component structure, implementing the image carousel, fetching data for hotels and images, and any optimizations you’d consider for performance and user experience.</p></blockquote>
<hr />
<h2>Clarifying Questions</h2>
<table>
<thead>
<tr>
<th>#</th>
<th>Question</th>
<th>Interviewer’s Answer</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Where is the hotel data coming from? Can you describe the API?</td>
<td>Please design the API.</td>
</tr>
<tr>
<td>2</td>
<td>How many images per property? Should we optimize for many or few?</td>
<td>You should design that for optimal performance.</td>
</tr>
<tr>
<td>3</td>
<td>Should the image carousel auto-play, or only allow manual scrolling?</td>
<td>Manual.</td>
</tr>
<tr>
<td>4</td>
<td>Any requirements for accessibility? (e.g., keyboard navigation, ARIA)</td>
<td>Yes, keep it accessible.</td>
</tr>
<tr>
<td>5</td>
<td>Should the grid use pagination, infinite scrolling, or show all at once?</td>
<td>Yes, pagination.</td>
</tr>
<tr>
<td>6</td>
<td>Should users be able to filter or sort hotel listings?</td>
<td>No need for filters right now.</td>
</tr>
<tr>
<td>7</td>
<td>Preferred technology stack or CSS framework?</td>
<td>Up to you, but let&#8217;s focus on React.</td>
</tr>
<tr>
<td>8</td>
<td>Any performance or scalability constraints?</td>
<td>Yes, please consider performance and scale.</td>
</tr>
<tr>
<td>9</td>
<td>Should we show loading or error states?</td>
<td>Graceful loading is always good.</td>
</tr>
<tr>
<td>10</td>
<td>Should we support localization/multi-currency for price display?</td>
<td>Yes, you can talk about localization.</td>
</tr>
<tr>
<td>11</td>
<td>Any offline support needed?</td>
<td>Out of scope.</td>
</tr>
</tbody>
</table>
<hr />
<h2>Requirements</h2>
<h3>Functional Requirements</h3>
<ul>
<li>Display a paginated, responsive grid of hotel/house listings</li>
<li>Each tile includes a manual image carousel, property title, and price per night</li>
<li>Images for each property should be viewable by scrolling/swiping within the tile</li>
<li>Data is fetched from an API you design</li>
<li>Site is accessible (keyboard navigation, ARIA labels, etc.)</li>
<li>Graceful loading states and error handling for data fetching</li>
<li>Price supports localization/multi-currency</li>
</ul>
<h3>Non-Functional Requirements</h3>
<ul>
<li>Fast load times and smooth scrolling, even with many properties</li>
<li>Scales to support large numbers of users and listings</li>
<li>Fully responsive design (works well on desktop, tablet, and mobile)</li>
<li>Designed with accessibility standards (WCAG) in mind</li>
<li>Good performance: optimized image loading, lazy loading for images/carousels</li>
<li>SEO-friendly markup where applicable</li>
<li>No offline support required</li>
</ul>
<h3>Napkin Math (Estimations)</h3>
<p>Assume a medium-sized site for initial design:</p>
<table>
<thead>
<tr>
<th>Metric</th>
<th>Estimate / Calculation</th>
</tr>
</thead>
<tbody>
<tr>
<td>Daily Active Users</td>
<td>100,000 users/day</td>
</tr>
<tr>
<td>Listings per Page</td>
<td>20 (typical grid pagination size)</td>
</tr>
<tr>
<td>Avg. Images/Listing</td>
<td>5</td>
</tr>
<tr>
<td>Total Daily Pageviews</td>
<td>500,000 pageviews/day (average five pages/user)</td>
</tr>
<tr>
<td>Images Loaded/Day</td>
<td>500,000 pages × 20 listings × 5 images = 50,000,000</td>
</tr>
<tr>
<td>Peak QPS</td>
<td>(500,000 ÷ 24 ÷ 3600) × 2 ≈ 12 requests/sec (per API)</td>
</tr>
</tbody>
</table>
<p><strong>API throughput:</strong> At peak, expect to serve up to ~12 grid pages per second (likely higher with bursts; design for 5x overhead, so aim for 60 QPS).</p>
<hr />
<h2>Architecture / Component Design</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1715" src="https://api.frontendlead.com/wp-content/uploads/2024/06/Screenshot-2025-05-19-at-8.40.50-AM.png" alt="Airbnb Frontend System Design Architecture" width="1268" height="1071" srcset="https://api.frontendlead.com/wp-content/uploads/2024/06/Screenshot-2025-05-19-at-8.40.50-AM.png 1268w, https://api.frontendlead.com/wp-content/uploads/2024/06/Screenshot-2025-05-19-at-8.40.50-AM-300x253.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/06/Screenshot-2025-05-19-at-8.40.50-AM-1024x865.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/06/Screenshot-2025-05-19-at-8.40.50-AM-768x649.png 768w" sizes="(max-width: 1268px) 100vw, 1268px" /></p>
<h3>User, Router, and Routing</h3>
<p>Everything starts when the user enters the app. At its core, <strong>React Router</strong> handles navigation between pages, such as the main bookings list and, in the future, more routes like a property details page or user account section. Right now, the router primarily directs users to the bookings grid. Suppose you need to support more routes down the line. In that case, React Router’s configuration can be easily extended by adding new route definitions, and the router will handle navigation between them without any significant architectural changes.</p>
<p>Routing like this keeps the UI fast and modern. Users can move between pages without waiting for full reloads, which feels much smoother and more like a native app.</p>
<hr />
<h3>SSR vs CSR (Server-Side Rendering vs Client-Side Rendering)</h3>
<p>For this hotel booking frontend, it’s essential to consider how and where our pages are rendered.</p>
<ul>
<li><strong>Server-Side Rendering (SSR):</strong> The HTML for each page is generated on the server and sent to the client. This means the first load is fast, SEO is better, and users see content more quickly, even before all JavaScript is loaded.</li>
<li><strong>Client-Side Rendering (CSR):</strong> The server sends a minimal HTML shell, and the browser downloads JavaScript, fetches data, and renders everything on the client. This can be great for fast, app-like navigation and complex interactions after the initial load.</li>
</ul>
<p>A standard, scalable approach is <strong>SSR for the initial page load</strong> (so users and search engines get content quickly), and <strong>CSR for all interactions</strong> (like clicking on a tile to view more images, paginating, or loading more listings).</p>
<p>Here’s a table comparing SSR and CSR for our use case:</p>
<table>
<thead>
<tr>
<th>Feature</th>
<th>SSR (Server-Side Rendering)</th>
<th>CSR (Client-Side Rendering)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Initial load speed</td>
<td>Fast, since the content is pre-rendered</td>
<td>Slower, must fetch and render on the client</td>
</tr>
<tr>
<td>SEO</td>
<td>Excellent, full HTML sent to the crawler</td>
<td>Poor, unless extra work for pre-render</td>
</tr>
<tr>
<td>Interactivity</td>
<td>Needs hydration, then fast</td>
<td>Very fast after JS loads</td>
</tr>
<tr>
<td>User experience</td>
<td>Content visible quickly</td>
<td>A blank or loading spinner at first</td>
</tr>
<tr>
<td>Complexity</td>
<td>Requires server setup (e.g., Next.js)</td>
<td>Simpler static hosting is possible</td>
</tr>
<tr>
<td>Best for&#8230;</td>
<td>Landing/search pages, listings</td>
<td>Deeply interactive UIs, dashboards</td>
</tr>
</tbody>
</table>
<p>For this project, SSR will make the booking grid fast and SEO-friendly, while CSR can handle all the snappy UI interactions after the first load.</p>
<hr />
<h3>State Management and Data Flow</h3>
<p>State management is a vast topic in frontend architecture, especially for an app like this. The right choice depends on how complex the state gets, how many places need to read or update it, and what kind of performance you need as you scale.</p>
<h4>Options for State Management</h4>
<ul>
<li><strong>useState</strong><br />
The simplest state hook in React is great for truly local state (like input fields or the current image index in a tile). It&#8217;s not ideal for global app data like the list of hotels or pagination since you’d have to “lift” state up multiple levels, which gets messy fast.</li>
<li><strong>useContext</strong><br />
React’s Context API lets you provide and consume state anywhere in the component tree. It’s solid for global, app-level states like hotel lists, pagination info, or loading status. It’s lightweight and doesn’t require external libraries, so keep your bundle size small and avoid unnecessary performance overhead. useContext is a strong choice for this project because we don’t have complex, deeply nested state or huge cross-component updates.</li>
<li><strong>Redux</strong><br />
Redux is super popular for large apps with many moving parts and strict state transition rules. It’s powerful, but it comes with a cost: extra boilerplate, a learning curve, and sometimes performance hits due to how Redux triggers updates across the app. Redux is overkill for a focused booking site like this and may slow things down if you’re not careful about structuring selectors and reducers.</li>
<li><strong>Zustand, Recoil, Jotai, etc.</strong><br />
There’s a wave of modern, minimal state management libraries that solve pain points in Redux and Context. Zustand, for example, gives you simple state containers with good performance and less boilerplate. If you ever outgrow Context or want fancier state control, these are worth exploring. For now, though, Context will keep things simple and readable.</li>
</ul>
<h4>Scoped State per Tile</h4>
<p>Beyond the global state, you often need to be “scoped” or local state for components like image slideshows or loading status per hotel card. For instance, if a user scrolls through images in one tile, you don’t want to re-render all tiles or blow away their position just because new data comes in. The solution is to use local state (with useState) inside each tile for things like the active image, loading animations, etc.</p>
<p>When the app fetches new data for a page, you also want to avoid blindly replacing everything and causing UI jumps. You can implement a diff check; if the incoming data for a hotel hasn’t changed, leave the tile alone. Only update those with new info (like price changes, new images, etc.). This is both a performance win and a better user experience.</p>
<h4>Why useContext for This Project?</h4>
<p>For this app, <strong>React Context</strong> strikes the right balance between simplicity, performance, and scalability:</p>
<ul>
<li>It keeps the global state in one place and is easily accessible across the app.</li>
<li>It avoids Redux’s overhead and complexity.</li>
<li>It works well with the View Model pattern, allowing you to separate business logic and data transformation from your UI components.</li>
<li>You can mix it with local state, especially for interactive components like carousels.</li>
</ul>
<table>
<thead>
<tr>
<th>Option</th>
<th>Pros</th>
<th>Cons</th>
<th>Best Use Case</th>
</tr>
</thead>
<tbody>
<tr>
<td>useState</td>
<td>Simple, built-in, great for local state</td>
<td>Not scalable for global state</td>
<td>Image index in a tile</td>
</tr>
<tr>
<td>useContext</td>
<td>Global state, minimal boilerplate</td>
<td>Unintended re-renders for large trees</td>
<td>Hotel list, pagination</td>
</tr>
<tr>
<td>Redux</td>
<td>Powerful, time-travel/debugging</td>
<td>Boilerplate, performance cost</td>
<td>Huge, complex apps</td>
</tr>
<tr>
<td>Zustand/etc.</td>
<td>Simple, fast, modern API</td>
<td>Less standard, another dependency</td>
<td>Growing apps, fine control</td>
</tr>
</tbody>
</table>
<p>Overall, go with <strong>useContext</strong> for the main store, and use <strong>local state</strong> for per-tile interactions. If the app grows into something more complex, migrating to a modern state lib is always an option, but starting simple is almost always the best move.</p>
<hr />
<h3>Bookings List Component Structure</h3>
<p>The <strong>BookingsListContainer</strong> is the hotel grid page&#8217;s main “container” component. It calls <code>useViewModel()</code> to get the current data. Inside, it renders a <strong>BookingsListContainerView</strong>, which maps over hotel data and renders a <strong>BookingsList</strong>.</p>
<p>Each hotel/house gets its <strong>BookingsCard</strong>, which shows the title, price, and image slideshow. The <strong>ImageSlideShow</strong> component handles scrolling/swiping through images within each tile, keeping things interactive and visually appealing.</p>
<p>The component structure looks like:</p>
<pre><code>
&lt;BookingsListContainer&gt;
  &lt;BookingsListContainerView&gt;
    &lt;BookingsList&gt;
      &lt;BookingsCard&gt;
        &lt;ImageSlideShow /&gt;
      &lt;/BookingsCard&gt;
    &lt;/BookingsList&gt;
  &lt;/BookingsListContainerView&gt;
&lt;/BookingsListContainer&gt;
</code></pre>
<p>The core of this UI is a series of reusable, focused components that build up the hotel grid in a predictable, scalable way. Each layer has a clear responsibility, and the structure makes testing, extending, and keeping your code clean easy.</p>
<hr />
<h4>BookingsListContainer</h4>
<p>This is the “smart” container at the top of the grid page. It handles data flow and passes everything down to child components. It calls <code>useViewModel()</code> to get the latest state (hotel list, loading status, pagination, etc.), and it might trigger data fetching when you hit a new page. BookingsListContainer doesn’t worry about layout details or how hotels are rendered; it handles the data and coordination.</p>
<h4>BookingsListContainerView</h4>
<p>This main “view” layer handles conditional rendering based on state. For example, depending on the situation, it can display a loading spinner, an error message, or the BookingsList itself. This keeps business logic and UI state (like loading or error states) out of your main grid component, making everything cleaner.</p>
<ul>
<li>Shows a loading indicator while data is being fetched</li>
<li>Renders an error message if there’s a fetch problem</li>
<li>Otherwise, renders the BookingsList with actual hotel data</li>
</ul>
<h4>BookingsList</h4>
<p>This component takes an array of hotel/property objects and maps over them to render a grid. You can easily style it with CSS Grid or Flexbox for a responsive layout. This component doesn’t know about pagination or API fetching, just how to lay out several hotel cards.</p>
<ul>
<li>Handles the visual grid</li>
<li>Keeps hotel tiles consistent in size and alignment</li>
<li>Renders one BookingsCard per hotel</li>
</ul>
<h4>BookingsCard</h4>
<p>The BookingsCard is responsible for each hotel’s tile. It receives props like the hotel title, price, and image array. All presentation logic for a single hotel goes here. This is also where you can integrate click handlers, hover states, or even “favorite” buttons in the future.</p>
<ul>
<li>Renders the title and price</li>
<li>Hosts the ImageSlideShow for the property</li>
<li>Handles any per-tile local state (like current image index)</li>
</ul>
<h4>ImageSlideShow</h4>
<p>This interactive piece lets users scroll or swipe through images for each hotel/house. It should be accessible (keyboard navigable, screen-reader friendly), touch-friendly for mobile, and lightweight so that you don’t load all images simultaneously unless needed (think lazy loading or prefetching the next/previous image).</p>
<ul>
<li>Accepts an array of image URLs</li>
<li>Handles manual navigation (left/right arrows, swipe, or scroll)</li>
<li>Maintains local state for the current image index</li>
<li>Optimizes image loading for performance</li>
</ul>
<h4>Component Relationship Table</h4>
<table>
<thead>
<tr>
<th>Component</th>
<th>Responsibility</th>
<th>Receives Data From</th>
<th>Passes Data To</th>
</tr>
</thead>
<tbody>
<tr>
<td>BookingsListContainer</td>
<td>Fetches/holds state, calls useViewModel</td>
<td>useViewModel</td>
<td>BookingsListContainerView</td>
</tr>
<tr>
<td>BookingsListContainerView</td>
<td>Handles loading/error/success display</td>
<td>BookingsListContainer</td>
<td>BookingsList</td>
</tr>
<tr>
<td>BookingsList</td>
<td>Maps hotels into a visual grid</td>
<td>BookingsListContainerView</td>
<td>BookingsCard</td>
</tr>
<tr>
<td>BookingsCard</td>
<td>Displays hotel info and image slideshow</td>
<td>BookingsList</td>
<td>ImageSlideShow</td>
</tr>
<tr>
<td>ImageSlideShow</td>
<td>Renders and manages a slideshow for property images</td>
<td>BookingsCard</td>
<td>(internal, manages itself)</td>
</tr>
</tbody>
</table>
<p>This approach separates data logic, state, and UI, making everything more maintainable. You can drop in new features, tweak layouts, or change the data flow without refactoring your entire app. If you need to add modals, tooltips, or even A/B test a new tile design, this structure makes those changes painless.</p>
<hr />
<h3>Networking and Data Fetching</h3>
<p>A <strong>Network Manager</strong> handles all API communication (fetching the hotel list, handling pagination, etc.). Instead of components making API calls directly, they go through the Network Manager, which can handle retries, caching, and logging out of the box.</p>
<p>The Network Manager talks to a <strong>blackbox server</strong> (the API backend you’ll design), grabs the latest hotel data, and pipes it into the Store/View Model for the UI.</p>
<hr />
<h3>Image Management and Caching</h3>
<p>A key performance area is image loading. The <strong>Img Manager</strong> is responsible for fetching and displaying images, so the UI isn’t bogged down by network latency. An Image Cache sits between the Img Manager and the network to provide fast image loads and reduce redundant network traffic. This caches recently viewed images in memory or IndexedDB, so images load instantly if a user scrolls back or reloads.</p>
<p>There’s also an <strong>image service</strong>, which you can use as the gateway to your image CDN or asset pipeline. The Img Manager requests images from the Image Service, which can handle transformations, resizing, and format negotiation.</p>
<p>A basic image flow:</p>
<ol>
<li>User scrolls to a new hotel tile.</li>
<li>Img Manager checks the image cache.</li>
<li>If cached, serve immediately. If not, fetch from the Image Service, then cache it.</li>
</ol>
<hr />
<h3>Component and Data Relationships (Table)</h3>
<p>Here’s a quick table summarizing how pieces talk to each other:</p>
<table>
<thead>
<tr>
<th>Layer/Component</th>
<th>Role</th>
<th>Talks To</th>
</tr>
</thead>
<tbody>
<tr>
<td>React Router</td>
<td>Handles navigation/routing</td>
<td>User, BookingsListContainer</td>
</tr>
<tr>
<td>BookingsListContainer</td>
<td>Entry point for the hotel list grid</td>
<td>View Model, UI components</td>
</tr>
<tr>
<td>View Model</td>
<td>Business logic/data transformation</td>
<td>Store, Network Manager, UI</td>
</tr>
<tr>
<td>Store (useContext)</td>
<td>Holds global app state</td>
<td>View Model</td>
</tr>
<tr>
<td>Network Manager</td>
<td>Handles API/data fetching</td>
<td>View Model, Server</td>
</tr>
<tr>
<td>Img Manager</td>
<td>Handles image fetch/display</td>
<td>Image Cache, Image Service</td>
</tr>
<tr>
<td>Image Cache</td>
<td>Speeds up repeat image loads</td>
<td>Img Manager</td>
</tr>
<tr>
<td>Image Service</td>
<td>Backend for image assets</td>
<td>Img Manager</td>
</tr>
<tr>
<td>BookingsCard, ImageSlideShow</td>
<td>UI for each hotel/property</td>
<td>BookingsListContainer</td>
</tr>
</tbody>
</table>
<hr />
<h3>Scalability and Extensibility</h3>
<p>This setup is designed for scale. Network and image logic are centralized so you can swap in more advanced caching, logging, or prefetching strategies later. The View Model means business logic doesn’t leak into the UI, keeping components easy to test and refactor.</p>
<p>If you want to add infinite scroll, filters, or favorites, expand the View Model and Store, and most of the UI can stay unchanged. Accessibility is also easier to enforce, since the ImageSlideShow and Cards can be built with semantic markup and ARIA attributes up front.</p>
<hr />
<h2>API Design</h2>
<p>The API will use <strong>RESTful design principles</strong> over <strong>HTTPS</strong> for our hotel booking app to ensure that all data sent between client and server is secure and standard. All endpoints return JSON. REST is familiar to front-end developers and works well with frameworks like React, so it’s a natural fit.</p>
<h3>Authentication &amp; Headers</h3>
<p>We require all API requests to include an <code>Authorization: Bearer &lt;token&gt;</code> header for authenticated endpoints. Public endpoints, such as hotel listings, can be accessed without authentication, but user-specific or booking actions would require a valid token. For localization and currency, clients can send a <code>Accept-Language</code> or <code>X-Currency</code> header.</p>
<ul>
<li><strong>Authorization:</strong> Bearer token for user auth (JWT or similar)</li>
<li><strong>Accept-Language:</strong> e.g., <code>en-US</code> for localization</li>
<li><strong>X-Currency:</strong> e.g., <code>USD</code>, <code>EUR</code></li>
</ul>
<h3>Pagination: Page-Based vs Cursor-Based</h3>
<p>There are two main styles for paginating API results:</p>
<ul>
<li><strong>Page-Based:</strong> Uses page numbers (<code>page=1&amp;pageSize=20</code>). Simple to use, easy to cache, but can be inconsistent if data changes rapidly. Suitable for user-facing grids and non-realtime data.</li>
<li><strong>Cursor-Based:</strong> Uses a cursor or token to fetch the next set (<code>cursor=abc123</code>). Handles real-time data well and prevents duplicates or missing data when listings change during pagination. More complex for basic UIs, but needed for feeds or chats.</li>
</ul>
<p>For our hotel listing, <strong>page-based pagination</strong> is enough because listings don’t change rapidly, and users expect to click through pages.</p>
<hr />
<h3>API Endpoint Design &amp; Client Data Model</h3>
<p>Here are the core endpoints, shown as TypeScript response types so you can see the shape of the server’s JSON output.</p>
<p>You can also use this for your client data model for your useContext.</p>
<pre><code>
// --- Shared Types ---

export type User = {
  id: string;
  name: string;
  avatarUrl?: string;
};

export type Hotel = {
  id: string;
  title: string;
  pricePerNight: number;
  currency: string;     // ISO code, e.g., "USD"
  images: string[];
  location: string;
  rating: number;
};

// --- API: Get Hotels (public endpoint) ---
// GET /api/hotels?page=1&amp;pageSize=20

// Request headers (for authenticated user, optional for this endpoint):
// Authorization: Bearer &lt;JWT&gt;
// Accept-Language: en-US
// X-Currency: USD

export type GetHotelsResponse = {
  hotels: Hotel[];
  page: number;
  pageSize: number;
  total: number;
};

// --- API: Get Hotel Details (public endpoint) ---
// GET /api/hotels/:id

// Request headers (optional):
// Authorization: Bearer &lt;JWT&gt;
// Accept-Language: en-US
// X-Currency: USD

export type Review = {
  user: User;
  comment: string;
  rating: number;
};

export type GetHotelDetailResponse = Hotel &amp; {
  description: string;
  amenities: string[];
  address: string;
  reviews: Review[];
};

// --- Error Response (all endpoints) ---
export type ErrorResponse = {
  error: string;
  message: string;
  status: number;
};
</code></pre>
<h3>Explanation</h3>
<ul>
<li><strong>GET /api/hotels: </strong>Returns a paginated list of hotels or houses. Each hotel object includes core fields and a set of image URLs for the slideshow. Pagination is done via <code>page</code> and <code>pageSize</code> query params. You can pass <code>Accept-Language</code> or <code>X-Currency</code> headers for localized/currency-aware pricing.</li>
<li><strong>GET /api/hotels/:id</strong>Returns detailed info for a single hotel. This expands the listing data and adds amenities, address, and reviews.</li>
<li><strong>Error responses: </strong>All errors return a JSON object with an error string, a human-readable message, and a status code.</li>
</ul>
<p>In production, you’ll also want to protect POST/PUT/DELETE endpoints with authentication. Hotel lists and details fetches can be public for our use case, but booking or user info would require a Bearer token.</p>
<hr />
<h2>Image Slider Design for Each Tile</h2>
<p>Each tile features an interactive image slider for a modern hotel grid that lets users scroll or swipe through property photos. This is a critical component for user experience and conversion, so it needs to be fast, touch-friendly, and visually smooth.</p>
<h3>Component Structure</h3>
<p>Here’s how the component tree looks for a single tile with an image slider:</p>
<pre><code>
&lt;BookingsCard&gt;
  &lt;ImageSlider images=[...] /&gt;
&lt;/BookingsCard&gt;
</code></pre>
<p><code>BookingsCard</code> handles the property’s details and hosts the <code>ImageSlider</code> component manages image navigation, touch events, and progressive image loading.</p>
<h3>Libraries vs Custom Implementation</h3>
<ul>
<li><strong>Using a library</strong>:<br />
There are many well-tested React image carousel libraries like <code>react-slick</code>, <code>swiper.js</code>, and <code>keen-slider</code>. These offer built-in touch, swipe, keyboard, and lazy-loading support.</p>
<ul>
<li><strong>Pros:</strong> Quick setup, polished UX, accessible, responsive out of the box, battle-tested for edge cases.</li>
<li><strong>Cons:</strong> Adds to bundle size, less flexibility for deep customization, sometimes overkill for basic sliders.</li>
</ul>
</li>
<li><strong>Custom build</strong>:<br />
You can build your slider with React, using React <code>useState</code> for the index, and CSS for transitions.</p>
<ul>
<li><strong>Pros:</strong> Minimal code, complete control, can be tiny for simple use cases.</li>
<li><strong>The cons:</strong> You must handle accessibility, swipe gestures, and performance optimizations yourself, which takes extra time and can introduce bugs.</li>
</ul>
</li>
</ul>
<p>For production, <strong>using a well-known library</strong> like <code>swiper.js</code> or It <code>react-slick</code> is usually the best bet, they’re optimized, accessible, and you avoid reinventing the wheel.</p>
<h3>Performance Best Practices</h3>
<ul>
<li><strong>Memoize the ImageSlider</strong>:<br />
Use <code>React.memo</code> or <code>useMemo</code> So the slider doesn’t re-render unless its props (the images) change. This is especially important in a grid where dozens of sliders are visible at once.</li>
<li><strong>Prevent unnecessary image fetches</strong>:<br />
Only fetch images that haven’t already been loaded. Use browser caching or a custom image cache to avoid redundant network requests.</li>
<li><strong>Lazy load images</strong>:<br />
By default, only load the first image. When a user clicks or swipes to the next image, fetch and render it just in time.</li>
<li><strong>Prefetch on desktop hover</strong>:<br />
If a user hovers over a desktop tile, start prefetching the next image or two in the background. This makes navigation instant when the user clicks next.</li>
<li><strong>Progressive image loading</strong>:<br />
Start with a low-res placeholder or blurred version, then swap in the full-res image when it finishes loading. Libraries like <code>react-lazyload</code> or native <code>&lt;img loading="lazy"&gt;</code> can help here.</li>
</ul>
<p>Using a battle-tested library and layering on bright lazy loading and caching gives you a smooth, responsive slider without hammering bandwidth or sacrificing UX.</p>
<hr />
<h2>Optimizations: Graceful Loading, Failures, and More</h2>
<p>For a hotel grid like this, the user experience is defined not just by fast loading, but by how gracefully the UI handles slow networks, image errors, and partial loads. Here’s how to design robust, resilient image and tile loading.</p>
<h3>Graceful Loading States</h3>
<ul>
<li><strong>Image Loading Indicators:</strong><br />
Show a spinner, skeleton, or blurred placeholder while an image loads. The <code>onLoad</code> event on the <code>&lt;img&gt;</code> lets you trigger the swap to the real image when it’s ready.</li>
<li><strong>Tile Placeholders:</strong><br />
While hotel data is being fetched, render card skeletons or shimmer placeholders. This prevents layout shift and keeps the grid visually stable as content comes in.</li>
<li><strong>Lazy Loading Tiles and Images:</strong><br />
Use <code>&lt;img loading="lazy"&gt;</code> Or intersection observers to load images only when a tile is about to scroll into view. React’s <code>lazy()</code> and <code>Suspense</code> Let you defer loading heavy components until needed.</li>
</ul>
<h3>Error Handling and Smart Retry Logic</h3>
<ul>
<li><strong>onError Handling:</strong><br />
If an image fails to load, show a fallback image, a “broken” icon, or a user-friendly message. Never leave a blank space or broken UI.</li>
<li><strong>Smart Retries:</strong><br />
Automatically retry loading failed images a few times with a delay, then fall back to a static error image. Use exponential backoff for retries to avoid hammering the server.</li>
<li><strong>Graceful Failures:</strong><br />
If a tile’s data can’t be fetched (due to network or server error), display a card-level error message with a “retry” button, not just a blank space.</li>
<li><strong>CDN Delivery:</strong><br />
Host images and static assets on a Content Delivery Network (CDN) for lower latency and higher availability. This means images still load quickly even if your main API is slow.</li>
</ul>
<h3>Other Key Optimizations</h3>
<ul>
<li><strong>Progressive Image Loading:</strong><br />
Load a tiny, blurred version first and fade in the high-res image for a smoother effect.</li>
<li><strong>Resource Preloading:</strong><br />
Use <code>&lt;link rel="preload"&gt;</code> for above-the-fold images and critical resources. On desktop, prefetch images on hover.</li>
<li><strong>Component Memoization:</strong><br />
Use <code>React.memo</code> and <code>useMemo</code> to prevent unnecessary re-renders, especially for image sliders and hotel cards that receive the same props.</li>
<li><strong>Minimize Layout Shift:</strong><br />
Always set explicit image width and height in Core Web Vitals to avoid Cumulative Layout Shift (CLS) penalties.</li>
<li><strong>Accessibility:</strong><br />
Make sure fallback images have <code>alt</code> text, and use ARIA labels for loading states so screen readers aren’t left out.</li>
<li><strong>Cache Control:</strong><br />
Set appropriate cache headers for API responses and images to reduce load times on repeat visits.</li>
</ul>
<p>With these optimizations in place, your frontend will stay fast, reliable, and smooth, even on slow networks or partial failures. Users will never see a broken experience, and your grid will always feel modern and responsive.</p>
<hr />
<h2>Accessibility and Security</h2>
<h3>Accessibility (a11y)</h3>
<ul>
<li>
    <strong>Keyboard Navigation:</strong><br />
    All interactive elements (image sliders, buttons, tiles) should be fully navigable with the keyboard. Use <code>tabIndex</code> for custom components and ensure focus styles are visible.
  </li>
<li>
    <strong>Screen Reader Support:</strong><br />
    Use semantic HTML and ARIA roles/labels to describe tiles, images, buttons, and loading states. Each hotel card should have descriptive <code>alt</code> text for images, and the slider controls should be announced as previous/next image buttons.
  </li>
<li>
    <strong>Color Contrast:</strong><br />
    Make sure text and controls meet minimum contrast ratios for readability, even in low-vision or high-contrast mode.
  </li>
<li>
    <strong>Accessible Loading/Error States:</strong><br />
    Loading spinners and error messages should be labeled with <code>aria-live</code> so screen readers announce changes in real time.
  </li>
<li>
    <strong>Touch and Pointer Support:</strong><br />
    Sliders and buttons should respond to both mouse and touch events, making the app usable on any device.
  </li>
</ul>
<h3>Security</h3>
<ul>
<li>
    <strong>XSS (Cross-Site Scripting) Protection:</strong><br />
    Never render raw HTML from user-generated content. Always sanitize or escape text. Use React’s default escaping for text content, and if you ever use <code>dangerouslySetInnerHTML</code>, sanitize first.
  </li>
<li>
    <strong>CORS (Cross-Origin Resource Sharing):</strong><br />
    Set up your backend API and CDN with appropriate CORS headers to restrict which domains can access your resources. Only allow trusted origins (your frontend domain).
  </li>
<li>
    <strong>HTTPS Everywhere:</strong><br />
    Serve your site and APIs over HTTPS to protect data in transit, including authentication tokens and personal info.
  </li>
<li>
    <strong>Authentication:</strong><br />
    Use secure tokens (like JWT) for user authentication. Store them in HTTP-only cookies or secure storage to prevent access from JavaScript.
  </li>
<li>
    <strong>Rate Limiting &#038; Abuse Prevention:</strong><br />
    Throttle API requests per user/IP to prevent brute force and abuse. Add backend validation on all inputs.
  </li>
<li>
    <strong>Content Security Policy (CSP):</strong><br />
    Use CSP headers to limit where scripts and resources can load from. This mitigates XSS risks even if something gets past your frontend.
  </li>
</ul>
<p>
By focusing on accessibility from the start and locking down security with best practices, you make your booking app usable for everyone and protect your users and data from common web threats.</p>


---

## 18. (Bonus) General System Design Fundamentals

- Difficulty: 🔴 Hard
- Subtitle: General System Design Fundamentals Guide
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35.png

### Content

<h1 data-start="169" data-end="207">General System Design Fundamentals &#8211; R.A.I.L.S Framework</h1>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1565" src="https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35.png" alt="Software Engineer System Design Interview Guide" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35.png 1920w, https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2025/05/FrontendLead-35-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<p class="" data-start="209" data-end="454">Although FrontendLead.com is built to help people prepare for <strong data-start="271" data-end="308">frontend system design interviews</strong> and everything related to frontend design, this article shifts gears. Here, we’ll focus specifically on <strong data-start="415" data-end="453">backend system design fundamentals</strong>.</p>
<p class="" data-start="456" data-end="481">Why, you might be asking?</p>
<p class="" data-start="483" data-end="785">Well, it’s not uncommon for frontend engineers to interview for <strong data-start="564" data-end="584">full-stack roles</strong>. And in full-stack interviews, expectations have changed. You&#8217;re not just going to be asked a frontend system design question anymore &#8211; chances are, you’ll be expected to reason about the backend too.</p>
<p class="" data-start="787" data-end="1018">While we already have several deep-dive articles on this platform covering <strong data-start="862" data-end="888">frontend system design</strong> prep, there has been a noticeable gap in covering backend fundamentals. That’s precisely what this guide aims to address.</p>
<p data-start="787" data-end="1018">If your interview is only for the frontend, please skip this article.</p>
<p class="" data-start="1020" data-end="1079">Here’s the table of contents we’ll cover:</p>
<ol data-start="1081" data-end="1415">
<li class="" data-start="1081" data-end="1111">
<p class="" data-start="1084" data-end="1111">System Design Foundations &#8211; R.A.I.L.S Framework Explained</p>
</li>
<li class="" data-start="1112" data-end="1144">
<p class="" data-start="1115" data-end="1144">Core System Design Concepts</p>
</li>
<li class="" data-start="1145" data-end="1159">
<p class="" data-start="1148" data-end="1159">Databases</p>
</li>
<li class="" data-start="1160" data-end="1172">
<p class="" data-start="1163" data-end="1172">Caching</p>
</li>
<li class="" data-start="1173" data-end="1201">
<p class="" data-start="1176" data-end="1201">Asynchronous Processing</p>
</li>
<li class="" data-start="1202" data-end="1237">
<p class="" data-start="1205" data-end="1237">Load Balancing and Scalability</p>
</li>
<li class="" data-start="1238" data-end="1271">
<p class="" data-start="1241" data-end="1271">Rate Limiting and Throttling</p>
</li>
<li class="" data-start="1272" data-end="1308">
<p class="" data-start="1275" data-end="1308">Fault Tolerance and Reliability</p>
</li>
<li class="" data-start="1309" data-end="1327">
<p class="" data-start="1312" data-end="1327">Observability</p>
</li>
<li class="" data-start="1328" data-end="1363">
<p class="" data-start="1332" data-end="1363">Infrastructure and Deployment</p>
</li>
<li class="" data-start="1364" data-end="1378">
<p class="" data-start="1368" data-end="1378">Security</p>
</li>
<li class="" data-start="1379" data-end="1415">
<p class="" data-start="1383" data-end="1415">Practice System Design Scenarios</p>
</li>
</ol>
<p data-start="1417" data-end="1442">We use the R.A.D.I.O framework for front-end interviews; however, it&#8217;s not 1:1 applicable for back-end interviews.</p>
<hr />
<h2 data-start="808" data-end="1016">R.A.I.L.S Framework</h2>
<p class="" data-start="808" data-end="1016">RAILS is a helpful mental model for structuring full-stack and backend interviews, but it’s not a strict checklist you need to follow in order. In interviews, the sections are fluid and often overlap.</p>
<p class="" data-start="1018" data-end="1280">If you&#8217;re designing a traffic-heavy system, you may start discussing scaling and bottlenecks before you lock down the interface. If you’re building a user-facing API, you might sketch out the contract first, then figure out how to support it at scale.</p>
<p class="" data-start="1282" data-end="1373">The framework is flexible; the goal is to make sure you cover all five areas thoughtfully:</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="1375" data-end="1941">
<thead data-start="1375" data-end="1419">
<tr data-start="1375" data-end="1419">
<th data-start="1375" data-end="1384" data-col-size="sm">Letter</th>
<th data-start="1384" data-end="1401" data-col-size="sm">What it Covers</th>
<th data-start="1401" data-end="1419" data-col-size="md">Why It Matters</th>
</tr>
</thead>
<tbody data-start="1465" data-end="1941">
<tr data-start="1465" data-end="1557">
<td data-start="1465" data-end="1474" data-col-size="sm"><strong data-start="1467" data-end="1472">R</strong></td>
<td data-start="1474" data-end="1489" data-col-size="sm">Requirements</td>
<td data-start="1489" data-end="1557" data-col-size="md">Clarifies what the system needs to do and under what constraints</td>
</tr>
<tr data-start="1558" data-end="1646">
<td data-start="1558" data-end="1567" data-col-size="sm"><strong data-start="1560" data-end="1565">A</strong></td>
<td data-start="1567" data-end="1582" data-col-size="sm">Architecture</td>
<td data-start="1582" data-end="1646" data-col-size="md">Helps you break the system into logical, scalable components</td>
</tr>
<tr data-start="1647" data-end="1738">
<td data-start="1647" data-end="1656" data-col-size="sm"><strong data-start="1649" data-end="1654">I</strong></td>
<td data-start="1656" data-end="1669" data-col-size="sm">Interfaces</td>
<td data-start="1669" data-end="1738" data-col-size="md">Defines how components talk to each other and external clients</td>
</tr>
<tr data-start="1739" data-end="1842">
<td data-start="1739" data-end="1748" data-col-size="sm"><strong data-start="1741" data-end="1746">L</strong></td>
<td data-start="1748" data-end="1776" data-col-size="sm">Latency, Load, and Limits</td>
<td data-start="1776" data-end="1842" data-col-size="md">Grounds your design in real-world performance, scale, and cost</td>
</tr>
<tr data-start="1843" data-end="1941">
<td data-start="1843" data-end="1852" data-col-size="sm"><strong data-start="1845" data-end="1850">S</strong></td>
<td data-start="1852" data-end="1874" data-col-size="sm">Storage and Scaling</td>
<td data-col-size="md" data-start="1874" data-end="1941">Ensures your data model and infrastructure can grow with demand</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="1943" data-end="2189">Use it as a checklist, not a script. You can start with R and A to set the foundation, but from there, let the conversation guide whether you go into load, scaling, or APIs next. Ensure you touch on all five areas by the time you&#8217;re done.</p>
<h3 class="" data-start="2815" data-end="2850">Keep These 3 Principles in Mind</h3>
<ol data-start="2852" data-end="3199">
<li class="" data-start="2852" data-end="2964">
<p class="" data-start="2855" data-end="2964"><strong data-start="2855" data-end="2893">Always clarify requirements first.</strong> Don’t jump into solutions without understanding scale and constraints.</p>
</li>
<li class="" data-start="2965" data-end="3092">
<p class="" data-start="2968" data-end="3092"><strong data-start="2968" data-end="3016">Don’t just name technologies, justify them.</strong> Saying “Redis” is fine, but explain <em data-start="3053" data-end="3058">why</em> it makes sense for your use case.</p>
</li>
<li class="" data-start="3093" data-end="3199">
<p class="" data-start="3096" data-end="3199"><strong data-start="3096" data-end="3121">Talk about tradeoffs.</strong> There’s rarely one perfect solution. Show that you’re aware of pros and cons.</p>
</li>
</ol>
<hr />
<h3 data-start="120" data-end="150">P: Problem and Requirements</h3>
<p class="" data-start="152" data-end="409">This is the first thing you should do in any backend or full-stack system design interview. Before discussing architecture or technology, you need to clearly define what you&#8217;re building, the constraints, and what the system needs to do.</p>
<h4 data-start="411" data-end="436">Why this step matters</h4>
<p class="" data-start="438" data-end="768">If you skip this, there&#8217;s a good chance you&#8217;ll build something that doesn’t solve the real problem or that can’t scale. It also gives the impression that you&#8217;re jumping into implementation without understanding the bigger picture. Starting with precise requirements shows thoughtfulness and helps anchor your design decisions later.</p>
<h4 data-start="770" data-end="787">What to Cover</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="789" data-end="1933">
<thead data-start="789" data-end="901">
<tr data-start="789" data-end="901">
<th data-start="789" data-end="816" data-col-size="sm">Area</th>
<th data-start="816" data-end="901" data-col-size="md">What to Ask or Do</th>
</tr>
</thead>
<tbody data-start="1016" data-end="1933">
<tr data-start="1016" data-end="1128">
<td data-start="1016" data-end="1043" data-col-size="sm">Core Use Case</td>
<td data-col-size="md" data-start="1043" data-end="1128">What is the system supposed to do? Summarize it in one sentence.</td>
</tr>
<tr data-start="1129" data-end="1245">
<td data-start="1129" data-end="1156" data-col-size="sm">Users and Actors</td>
<td data-col-size="md" data-start="1156" data-end="1245">Who is using the system? Are there admins, regular users, services, or third parties?</td>
</tr>
<tr data-start="1246" data-end="1361">
<td data-start="1246" data-end="1273" data-col-size="sm">Scale</td>
<td data-start="1273" data-end="1361" data-col-size="md">How many users, requests per second, or files per day are expected? Ask for numbers.</td>
</tr>
<tr data-start="1362" data-end="1474">
<td data-start="1362" data-end="1389" data-col-size="sm">Latency Expectations</td>
<td data-col-size="md" data-start="1389" data-end="1474">Is this a real-time system, or is some delay acceptable?</td>
</tr>
<tr data-start="1475" data-end="1591">
<td data-start="1475" data-end="1502" data-col-size="sm">Availability Requirements</td>
<td data-start="1502" data-end="1591" data-col-size="md">Is 24/7 uptime expected? Can parts of the system go down without breaking everything?</td>
</tr>
<tr data-start="1592" data-end="1704">
<td data-start="1592" data-end="1619" data-col-size="sm">Read vs Write Patterns</td>
<td data-col-size="md" data-start="1619" data-end="1704">Will this be a write-heavy system (like chat) or read-heavy (like a feed)?</td>
</tr>
<tr data-start="1705" data-end="1818">
<td data-start="1705" data-end="1732" data-col-size="sm">Security or Compliance</td>
<td data-start="1732" data-end="1818" data-col-size="md">Are we handling sensitive data like passwords, payments, or personal info?</td>
</tr>
<tr data-start="1819" data-end="1933">
<td data-start="1819" data-end="1849" data-col-size="sm">Non-Functional Requirements</td>
<td data-start="1849" data-end="1933" data-col-size="md">What’s expected regarding reliability, scalability, maintainability, and cost?</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 data-start="1935" data-end="1988">Walkthrough Example: Real-Time Facebook News Feed</h4>
<p class="" data-start="1990" data-end="2062">Prompt: <strong data-start="1998" data-end="2062">Design a Facebook-style news feed that updates in real time.</strong></p>
<p class="" data-start="2064" data-end="2104">You might start the interview like this:</p>
<p class="" data-start="2106" data-end="2317">Let me make sure I understand what we’re building. The goal is to allow users to see a real-time feed of posts from people or pages they follow. These posts might include text, images, and videos.</p>
<p class="" data-start="2319" data-end="2385">Before diving into architecture, I’d want to clarify a few things:</p>
<ul data-start="2387" data-end="3072">
<li class="" data-start="2387" data-end="2468">
<p class="" data-start="2389" data-end="2468">What’s the expected user base? Are we supporting millions or billions of users?</p>
</li>
<li class="" data-start="2469" data-end="2556">
<p class="" data-start="2471" data-end="2556">Are posts globally visible, or do we need privacy filters based on friends or groups?</p>
</li>
<li class="" data-start="2557" data-end="2636">
<p class="" data-start="2559" data-end="2636">Should the feed update in real time, or is it okay if there’s a slight delay?</p>
</li>
<li class="" data-start="2637" data-end="2717">
<p class="" data-start="2639" data-end="2717">Will the UI use infinite scroll with pagination, or should we preload content?</p>
</li>
<li class="" data-start="2718" data-end="2812">
<p class="" data-start="2720" data-end="2812">Should posts appear in strict reverse-chronological order, or does engagement rank them?</p>
</li>
<li class="" data-start="2813" data-end="2893">
<p class="" data-start="2815" data-end="2893">Do we need to support media uploads? If so, what’s the expected max file size?</p>
</li>
<li class="" data-start="2894" data-end="2988">
<p class="" data-start="2896" data-end="2988">Will the same post be shown to multiple users (fan-out), or is each feed fully personalized?</p>
</li>
<li class="" data-start="2989" data-end="3072">
<p class="" data-start="2991" data-end="3072">Are there any constraints around mobile performance or users on slow connections?</p>
</li>
</ul>
<h4 data-start="3074" data-end="3100">Tips for this step</h4>
<ul data-start="3102" data-end="3516">
<li class="" data-start="3102" data-end="3199">
<p class="" data-start="3104" data-end="3199">Always ask about scale. Designing for 1,000 users is not the same as designing for 100 million.</p>
</li>
<li class="" data-start="3200" data-end="3291">
<p class="" data-start="3202" data-end="3291">Clarify business logic. Don’t assume things like privacy settings or sharing rules &#8211; ask.</p>
</li>
<li class="" data-start="3292" data-end="3380">
<p class="" data-start="3294" data-end="3380">Write down your assumptions before moving forward. If you&#8217;re unsure, make it explicit.</p>
</li>
<li class="" data-start="3381" data-end="3516">
<p class="" data-start="3383" data-end="3516">Use numbers. Think out loud: “If each user posts 10 times a day, and we have 10 million users, that’s 100 million new posts per day.”</p>
</li>
</ul>
<hr />
<h3 data-start="96" data-end="114">A: Architecture</h3>
<p class="" data-start="116" data-end="474">Once the requirements are precise, the next step is to break the system into high-level components. This is where you start diagramming and explaining how the system works behind the scenes. You’re not expected to cover every technical detail yet, but you should show that you understand how to organize the system into clean, scalable, and maintainable parts.</p>
<p class="" data-start="476" data-end="675">This is usually the part of the interview where you start drawing boxes. You can verbally walk the interviewer through the architecture while referencing a shared doc or whiteboard if you&#8217;re remote.</p>
<h4 data-start="677" data-end="694">What to Cover</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="696" data-end="1450">
<thead data-start="696" data-end="728">
<tr data-start="696" data-end="728">
<th data-start="696" data-end="703" data-col-size="sm">Area</th>
<th data-start="703" data-end="728" data-col-size="lg">What to Think Through</th>
</tr>
</thead>
<tbody data-start="763" data-end="1450">
<tr data-start="763" data-end="878">
<td data-start="763" data-end="774" data-col-size="sm">Services</td>
<td data-start="774" data-end="878" data-col-size="lg">What services are involved? For example, post creation, feed generation, user service, and media service</td>
</tr>
<tr data-start="879" data-end="1012">
<td data-start="879" data-end="895" data-col-size="sm">Communication</td>
<td data-col-size="lg" data-start="895" data-end="1012">Are services communicating via REST, gRPC, or queues? When do you need synchronous vs asynchronous communication?</td>
</tr>
<tr data-start="1013" data-end="1125">
<td data-start="1013" data-end="1025" data-col-size="sm">Data Flow</td>
<td data-start="1025" data-end="1125" data-col-size="lg">What happens when a user creates a post? How does it reach their friends? How is the feed built?</td>
</tr>
<tr data-start="1126" data-end="1223">
<td data-start="1126" data-end="1136" data-col-size="sm">Caching</td>
<td data-col-size="lg" data-start="1136" data-end="1223">What data should be cached? Feed results? Post metadata? Where is the cache placed?</td>
</tr>
<tr data-start="1224" data-end="1323">
<td data-start="1224" data-end="1243" data-col-size="sm">External Systems</td>
<td data-col-size="lg" data-start="1243" data-end="1323">Are we using a CDN, media storage (like S3), analytics, or third-party auth?</td>
</tr>
<tr data-start="1324" data-end="1450">
<td data-start="1324" data-end="1345" data-col-size="sm">Client Integration</td>
<td data-start="1345" data-end="1450" data-col-size="lg">How does the frontend fetch the feed? Is it polling? Using GraphQL? WebSockets for real-time updates?</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 data-start="1452" data-end="1493">Example: Real-Time Facebook News Feed</h4>
<p class="" data-start="1495" data-end="1614">Let’s say you&#8217;re asked to design a Facebook-style feed. At a high level, you might break it down into these components:</p>
<ul data-start="1616" data-end="2323">
<li class="" data-start="1616" data-end="1674">
<p class="" data-start="1618" data-end="1674"><strong data-start="1618" data-end="1632">Client App</strong>: Sends a request to fetch the news feed</p>
</li>
<li class="" data-start="1675" data-end="1730">
<p class="" data-start="1677" data-end="1730"><strong data-start="1677" data-end="1692">API Gateway</strong>: Routes traffic to backend services</p>
</li>
<li class="" data-start="1731" data-end="1807">
<p class="" data-start="1733" data-end="1807"><strong data-start="1733" data-end="1749">Feed Service</strong>: Responsible for assembling and returning a user’s feed</p>
</li>
<li class="" data-start="1808" data-end="1871">
<p class="" data-start="1810" data-end="1871"><strong data-start="1810" data-end="1826">Post Service</strong>: Handles creation and storage of new posts</p>
</li>
<li class="" data-start="1872" data-end="1946">
<p class="" data-start="1874" data-end="1946"><strong data-start="1874" data-end="1896">User Graph Service</strong>: Tracks friendships and following relationships</p>
</li>
<li class="" data-start="1947" data-end="2011">
<p class="" data-start="1949" data-end="2011"><strong data-start="1949" data-end="1966">Media Service</strong>: Stores and serves images or video content</p>
</li>
<li class="" data-start="2012" data-end="2097">
<p class="" data-start="2014" data-end="2097"><strong data-start="2014" data-end="2050">Cache Layer (Redis or Memcached)</strong>: Stores hot feeds or user-specific timelines</p>
</li>
<li class="" data-start="2098" data-end="2165">
<p class="" data-start="2100" data-end="2165"><strong data-start="2100" data-end="2112">Database</strong>: Stores post data, user metadata, and feed indexes</p>
</li>
<li class="" data-start="2166" data-end="2258">
<p class="" data-start="2168" data-end="2258"><strong data-start="2168" data-end="2193">Queue + Worker System</strong>: For fan-out (e.g., distributing new posts to followers’ feeds)</p>
</li>
<li class="" data-start="2259" data-end="2323">
<p class="" data-start="2261" data-end="2323"><strong data-start="2261" data-end="2268">CDN</strong>: Delivers static assets like images and videos quickly</p>
</li>
</ul>
<p class="" data-start="2325" data-end="2363">The typical flow might look like this:</p>
<ol data-start="2365" data-end="3071">
<li class="" data-start="2365" data-end="2428">
<p class="" data-start="2368" data-end="2428">A user opens the app and triggers a request to <code data-start="2415" data-end="2426">GET /feed</code></p>
</li>
<li class="" data-start="2429" data-end="2516">
<p class="" data-start="2432" data-end="2516">The request goes to the <strong data-start="2456" data-end="2471">API Gateway</strong>, which forwards it to the <strong data-start="2498" data-end="2514">Feed Service</strong></p>
</li>
<li class="" data-start="2517" data-end="2586">
<p class="" data-start="2520" data-end="2586">The <strong data-start="2524" data-end="2540">Feed Service</strong> checks Redis to see if a recent feed exists</p>
</li>
<li class="" data-start="2587" data-end="2707">
<p class="" data-start="2590" data-end="2707">If not, it pulls data from the <strong data-start="2621" data-end="2637">Post Service</strong>, the <strong data-start="2643" data-end="2665">User Graph Service</strong>, and the <strong data-start="2675" data-end="2687">Database</strong> to build the feed</p>
</li>
<li class="" data-start="2708" data-end="2768">
<p class="" data-start="2711" data-end="2768">The resulting feed is cached and returned to the client</p>
</li>
<li class="" data-start="2769" data-end="2896">
<p class="" data-start="2772" data-end="2896">When a user creates a post, it goes through the <strong data-start="2820" data-end="2836">Post Service</strong>, which stores the data and sends a message to a <strong data-start="2885" data-end="2894">Queue</strong></p>
</li>
<li class="" data-start="2897" data-end="2988">
<p class="" data-start="2900" data-end="2988">A <strong data-start="2902" data-end="2912">Worker</strong> picks it up and fans out the post to all relevant followers&#8217; cached feeds</p>
</li>
<li class="" data-start="2989" data-end="3071">
<p class="" data-start="2992" data-end="3071">Media is uploaded separately to the <strong data-start="3028" data-end="3045">Media Service</strong> and delivered via <strong data-start="3064" data-end="3071">CDN</strong></p>
</li>
</ol>
<h4 data-start="3073" data-end="3095">Tips for This Step</h4>
<ul data-start="3097" data-end="3374">
<li class="" data-start="3097" data-end="3157">
<p class="" data-start="3099" data-end="3157">Use boxes and arrows to walk through the system visually</p>
</li>
<li class="" data-start="3158" data-end="3238">
<p class="" data-start="3160" data-end="3238">Focus on how components talk to each other, and what each is responsible for</p>
</li>
<li class="" data-start="3239" data-end="3293">
<p class="" data-start="3241" data-end="3293">Show a clear separation of concerns between services</p>
</li>
<li class="" data-start="3294" data-end="3374">
<p class="" data-start="3296" data-end="3374">Start simple, then layer in more complexity (e.g., real-time updates, failover)</p>
</li>
</ul>
<hr />
<h3 data-start="113" data-end="125">Data Flow</h3>
<p class="" data-start="127" data-end="374">After laying out the high-level architecture, you should next walk through what actually happens in the system. This means explaining how data flows from the client to the backend, through different services, and back to the user.</p>
<p class="" data-start="376" data-end="578">You don’t need to cover every edge case here, but you should clearly explain the core flow for the main use cases, in a news feed system, which includes post creation, feed generation, and feed delivery.</p>
<h4 data-start="580" data-end="597">What to Cover</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="599" data-end="1168">
<thead data-start="599" data-end="634">
<tr data-start="599" data-end="634">
<th data-start="599" data-end="610" data-col-size="sm">Scenario</th>
<th data-start="610" data-end="634" data-col-size="md">What to Walk Through</th>
</tr>
</thead>
<tbody data-start="672" data-end="1168">
<tr data-start="672" data-end="756">
<td data-start="672" data-end="688" data-col-size="sm">Post Creation</td>
<td data-start="688" data-end="756" data-col-size="md">How is a new post submitted, validated, stored, and distributed?</td>
</tr>
<tr data-start="757" data-end="855">
<td data-start="757" data-end="775" data-col-size="sm">Feed Generation</td>
<td data-start="775" data-end="855" data-col-size="md">How is the feed built for each user? When is it built — on write or on read?</td>
</tr>
<tr data-start="856" data-end="973">
<td data-start="856" data-end="876" data-col-size="sm">Real-Time Updates</td>
<td data-col-size="md" data-start="876" data-end="973">Are posts pushed to users using WebSockets, or do they refresh manually or poll periodically?</td>
</tr>
<tr data-start="974" data-end="1068">
<td data-start="974" data-end="989" data-col-size="sm">Media Upload</td>
<td data-start="989" data-end="1068" data-col-size="md">If a post has an image or video, how is it uploaded and linked to the post?</td>
</tr>
<tr data-start="1069" data-end="1168">
<td data-start="1069" data-end="1092" data-col-size="sm">Analytics or Metrics</td>
<td data-start="1092" data-end="1168" data-col-size="md">Are you logging views, clicks, or interactions? Where does that data go?</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 data-start="1170" data-end="1211">Example: Real-Time Facebook News Feed</h4>
<p class="" data-start="1213" data-end="1276">Let’s walk through what happens when a user creates a new post.</p>
<ol data-start="1278" data-end="2480">
<li class="" data-start="1278" data-end="1335">
<p class="" data-start="1281" data-end="1335">The user writes a post and hits &#8220;Publish&#8221; in the app</p>
</li>
<li class="" data-start="1336" data-end="1450">
<p class="" data-start="1339" data-end="1450">The frontend sends a <code data-start="1360" data-end="1372">POST /post</code> request to the backend, including text, metadata, and possibly a media link</p>
</li>
<li class="" data-start="1451" data-end="1522">
<p class="" data-start="1454" data-end="1522">The <strong data-start="1458" data-end="1474">Post Service</strong> validates and stores the post in the database</p>
</li>
<li class="" data-start="1523" data-end="1635">
<p class="" data-start="1526" data-end="1635">If the post includes media, it was likely uploaded separately using a presigned URL before the post request</p>
</li>
<li class="" data-start="1636" data-end="1744">
<p class="" data-start="1639" data-end="1744">The <strong data-start="1643" data-end="1659">Post Service</strong> sends a message to a <strong data-start="1681" data-end="1690">Queue</strong> (e.g., Kafka, SQS) indicating a new post was created</p>
</li>
<li class="" data-start="1745" data-end="2087">
<p class="" data-start="1748" data-end="1850">A <strong data-start="1750" data-end="1768">Fan-out Worker</strong> picks up the message and updates the feed entries for all followers of the user</p>
<ul data-start="1854" data-end="2087">
<li class="" data-start="1854" data-end="1978">
<p class="" data-start="1856" data-end="1978">If using a fan-out-on-write strategy, the system writes the new post ID to each follower’s feed in Redis or a feed table</p>
</li>
<li class="" data-start="1982" data-end="2087">
<p class="" data-start="1984" data-end="2087">If using fan-out-on-read, nothing is written yet — the post will be pulled during the following feed query</p>
</li>
</ul>
</li>
<li class="" data-start="2088" data-end="2412">
<p class="" data-start="2091" data-end="2203">When a follower opens the app and triggers a <code data-start="2136" data-end="2147">GET /feed</code> the <strong data-start="2153" data-end="2169">Feed Service</strong> fetches their personalized feed</p>
<ul data-start="2207" data-end="2412">
<li class="" data-start="2207" data-end="2249">
<p class="" data-start="2209" data-end="2249">It first checks Redis or another cache</p>
</li>
<li class="" data-start="2253" data-end="2339">
<p class="" data-start="2255" data-end="2339">If a cache miss, it queries the database or joins across tables to generate the feed.</p>
</li>
<li class="" data-start="2343" data-end="2412">
<p class="" data-start="2345" data-end="2412">It may also rank posts based on engagement, recency, or relevance</p>
</li>
</ul>
</li>
<li class="" data-start="2413" data-end="2480">
<p class="" data-start="2416" data-end="2480">The result is returned to the client, which renders it in the UI</p>
</li>
</ol>
<h4 data-start="2482" data-end="2513">Notes on Fan-out Strategies</h4>
<p class="" data-start="2515" data-end="2568">There are two main ways to handle distributing posts:</p>
<ul data-start="2570" data-end="2872">
<li class="" data-start="2570" data-end="2704">
<p class="" data-start="2572" data-end="2704"><strong data-start="2572" data-end="2592">Fan-out on write</strong>: You push the post to all followers&#8217; feeds as soon as it’s created. This gives fast reads but a heavy write load.</p>
</li>
<li class="" data-start="2705" data-end="2872">
<p class="" data-start="2707" data-end="2872"><strong data-start="2707" data-end="2726">Fan-out on read</strong>: You keep the posts in one place and fetch them dynamically when a user requests their feed. This keeps writes light but puts more load on reads.</p>
</li>
</ul>
<p class="" data-start="2874" data-end="2969">Your choice depends on the scale, read-to-write ratio, and personalization complexity.</p>
<hr />
<h3 data-start="129" data-end="145">I: Interfaces</h3>
<p class="" data-start="147" data-end="517">Now that you’ve mapped out how data flows through the system, the next step is to define the key interfaces. This includes the public-facing APIs that the client uses and internal service-to-service communication. You don’t need to write full API specs, but you should clearly describe the essential endpoints and how different components communicate.</p>
<h4 data-start="519" data-end="536">What to Cover</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="538" data-end="1115">
<thead data-start="538" data-end="563">
<tr data-start="538" data-end="563">
<th data-start="538" data-end="545" data-col-size="sm">Type</th>
<th data-start="545" data-end="563" data-col-size="md">What to Define</th>
</tr>
</thead>
<tbody data-start="590" data-end="1115">
<tr data-start="590" data-end="684">
<td data-start="590" data-end="606" data-col-size="sm">External APIs</td>
<td data-start="606" data-end="684" data-col-size="md">What does the frontend call? What does each endpoint do? What is returned?</td>
</tr>
<tr data-start="685" data-end="791">
<td data-start="685" data-end="701" data-col-size="sm">Internal APIs</td>
<td data-start="701" data-end="791" data-col-size="md">How do services talk to each other? What data gets passed? Is it synchronous or asynchronous?</td>
</tr>
<tr data-start="792" data-end="887">
<td data-start="792" data-end="810" data-col-size="sm">Auth Boundaries</td>
<td data-col-size="md" data-start="810" data-end="887">Which endpoints require authentication? Are there role-based permissions?</td>
</tr>
<tr data-start="888" data-end="1003">
<td data-start="888" data-end="905" data-col-size="sm">Media Handling</td>
<td data-start="905" data-end="1003" data-col-size="md">Is media uploaded directly to object storage? If so, how is that coordinated with the backend?</td>
</tr>
<tr data-start="1004" data-end="1115">
<td data-start="1004" data-end="1027" data-col-size="sm">Real-Time Interfaces</td>
<td data-start="1027" data-end="1115" data-col-size="md">If using WebSockets or long polling, what does the handshake or data push look like?</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 data-start="1117" data-end="1158">Example: Real-Time Facebook News Feed</h4>
<p class="" data-start="1160" data-end="1250">Here are some of the primary interfaces you might include for a basic version of this system.</p>
<h4 class="" data-start="1252" data-end="1270">External APIs</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="1272" data-end="1660">
<thead data-start="1272" data-end="1307">
<tr data-start="1272" data-end="1307">
<th data-start="1272" data-end="1283" data-col-size="sm">Endpoint</th>
<th data-start="1283" data-end="1292" data-col-size="sm">Method</th>
<th data-start="1292" data-end="1307" data-col-size="md">Description</th>
</tr>
</thead>
<tbody data-start="1344" data-end="1660">
<tr data-start="1344" data-end="1410">
<td data-start="1344" data-end="1354" data-col-size="sm"><code data-start="1346" data-end="1353">/feed</code></td>
<td data-start="1354" data-end="1360" data-col-size="sm">GET</td>
<td data-start="1360" data-end="1410" data-col-size="md">Returns a user’s news feed, possibly paginated</td>
</tr>
<tr data-start="1411" data-end="1489">
<td data-start="1411" data-end="1421" data-col-size="sm"><code data-start="1413" data-end="1420">/post</code></td>
<td data-start="1421" data-end="1428" data-col-size="sm">POST</td>
<td data-start="1428" data-end="1489" data-col-size="md">Creates a new post with text and optional media reference</td>
</tr>
<tr data-start="1490" data-end="1576">
<td data-start="1490" data-end="1506" data-col-size="sm"><code data-start="1492" data-end="1505">/upload-url</code></td>
<td data-col-size="sm" data-start="1506" data-end="1513">POST</td>
<td data-col-size="md" data-start="1513" data-end="1576">Returns a presigned URL to upload media directly to storage</td>
</tr>
<tr data-start="1577" data-end="1660">
<td data-start="1577" data-end="1592" data-col-size="sm"><code data-start="1579" data-end="1591">/media/:id</code></td>
<td data-col-size="sm" data-start="1592" data-end="1598">GET</td>
<td data-col-size="md" data-start="1598" data-end="1660">Streams or downloads the media file if the user has access</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="1662" data-end="1794">Depending on how auth is implemented, each of these endpoints would be authenticated using a session token, cookie, or bearer token.</p>
<h4 class="" data-start="1796" data-end="1820">Internal Interfaces</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="1822" data-end="2347">
<thead data-start="1822" data-end="1856">
<tr data-start="1822" data-end="1856">
<th data-start="1822" data-end="1832" data-col-size="sm">Service</th>
<th data-start="1832" data-end="1841" data-col-size="sm">Method</th>
<th data-start="1841" data-end="1856" data-col-size="md">Description</th>
</tr>
</thead>
<tbody data-start="1892" data-end="2347">
<tr data-start="1892" data-end="1991">
<td data-start="1892" data-end="1921" data-col-size="sm">Post Service → Feed Worker</td>
<td data-start="1921" data-end="1937" data-col-size="sm">Queue message</td>
<td data-col-size="md" data-start="1937" data-end="1991">Sends new post event to feed processor for fan-out</td>
</tr>
<tr data-start="1992" data-end="2082">
<td data-start="1992" data-end="2028" data-col-size="sm">Feed Service → User Graph Service</td>
<td data-start="2028" data-end="2042" data-col-size="sm">RPC or REST</td>
<td data-start="2042" data-end="2082" data-col-size="md">Fetches a list of followers or friends</td>
</tr>
<tr data-start="2083" data-end="2177">
<td data-start="2083" data-end="2113" data-col-size="sm">Feed Service → Post Service</td>
<td data-col-size="sm" data-start="2113" data-end="2129">Internal call</td>
<td data-col-size="md" data-start="2129" data-end="2177">Retrieves post details for a set of post IDs</td>
</tr>
<tr data-start="2178" data-end="2262">
<td data-start="2178" data-end="2207" data-col-size="sm">Feed Service → Cache Layer</td>
<td data-start="2207" data-end="2220" data-col-size="sm">Read/Write</td>
<td data-col-size="md" data-start="2220" data-end="2262">Gets or updates the user’s cached feed</td>
</tr>
<tr data-start="2263" data-end="2347">
<td data-start="2263" data-end="2285" data-col-size="sm">Media Service → CDN</td>
<td data-col-size="sm" data-start="2285" data-end="2291">N/A</td>
<td data-col-size="md" data-start="2291" data-end="2347">Serves media through an edge network for performance</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="2349" data-end="2436">You can also include real-time communication if the system pushes new posts to clients:</p>
<ul data-start="2438" data-end="2598">
<li class="" data-start="2438" data-end="2486">
<p class="" data-start="2440" data-end="2486">WebSocket connection is opened from the client</p>
</li>
<li class="" data-start="2487" data-end="2529">
<p class="" data-start="2489" data-end="2529">Server pushes new post IDs when relevant</p>
</li>
<li class="" data-start="2530" data-end="2598">
<p class="" data-start="2532" data-end="2598">Client fetches the full post via <code data-start="2565" data-end="2580">GET /post/:id</code> or batch endpoint</p>
</li>
</ul>
<h4 data-start="2600" data-end="2623">Tips for Interfaces</h4>
<ul data-start="2625" data-end="2931">
<li class="" data-start="2625" data-end="2667">
<p class="" data-start="2627" data-end="2667">Be clear about what’s public vs internal</p>
</li>
<li class="" data-start="2668" data-end="2740">
<p class="" data-start="2670" data-end="2740">Include pagination, filtering, or cursor-based navigation where needed</p>
</li>
<li class="" data-start="2741" data-end="2830">
<p class="" data-start="2743" data-end="2830">Talk about rate limiting, retries, and fallback behavior if an internal service is down</p>
</li>
<li class="" data-start="2831" data-end="2931">
<p class="" data-start="2833" data-end="2931">Explain auth rules: &#8220;Users can only access their feed and posts from users they follow.&#8221;</p>
</li>
</ul>
<hr />
<h3 data-start="103" data-end="134">L: Latency, Load, and Limits</h3>
<p class="" data-start="136" data-end="429">Once your system is architected and the interfaces are in place, you need to understand how much traffic you expect, how fast things need to be, and where bottlenecks might appear. This is where you do some quick math and discuss how your system holds up under real-world pressure.</p>
<p class="" data-start="431" data-end="586">You don’t need perfect numbers. What matters is showing that you can reason through scale, performance expectations, and where limits will start to appear.</p>
<h4 data-start="588" data-end="605">What to Cover</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="607" data-end="1189">
<thead data-start="607" data-end="645">
<tr data-start="607" data-end="645">
<th data-start="607" data-end="614" data-col-size="sm">Area</th>
<th data-start="614" data-end="645" data-col-size="md">What to Estimate or Discuss</th>
</tr>
</thead>
<tbody data-start="685" data-end="1189">
<tr data-start="685" data-end="767">
<td data-start="685" data-end="710" data-col-size="sm">Daily and Peak Traffic</td>
<td data-col-size="md" data-start="710" data-end="767">How many users? How many reads and writes per second?</td>
</tr>
<tr data-start="768" data-end="834">
<td data-start="768" data-end="780" data-col-size="sm">Data Size</td>
<td data-col-size="md" data-start="780" data-end="834">How much data is being created and stored per day?</td>
</tr>
<tr data-start="835" data-end="936">
<td data-start="835" data-end="858" data-col-size="sm">Latency Expectations</td>
<td data-col-size="md" data-start="858" data-end="936">How fast should the feed load? Is 100ms good enough? Is 1 second too slow?</td>
</tr>
<tr data-start="937" data-end="1006">
<td data-start="937" data-end="956" data-col-size="sm">Read/Write Ratio</td>
<td data-start="956" data-end="1006" data-col-size="md">Are there more reads than writes? By how much?</td>
</tr>
<tr data-start="1007" data-end="1090">
<td data-start="1007" data-end="1021" data-col-size="sm">Bottlenecks</td>
<td data-start="1021" data-end="1090" data-col-size="md">Where is the system likely to slow down or fail under heavy load?</td>
</tr>
<tr data-start="1091" data-end="1189">
<td data-start="1091" data-end="1108" data-col-size="sm">Cost Awareness</td>
<td data-start="1108" data-end="1189" data-col-size="md">Are there any high-cost operations or external services to be cautious about?</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 data-start="1191" data-end="1232">Example: Real-Time Facebook News Feed</h4>
<p class="" data-start="1234" data-end="1398">Let’s say you&#8217;re building a scaled-down version of Facebook’s feed for 10 million monthly active users. Here’s how you might talk through some quick load estimates.</p>
<h4 class="" data-start="1400" data-end="1427">Upload and Post Volume</h4>
<ul data-start="1429" data-end="1649">
<li class="" data-start="1429" data-end="1449">
<p class="" data-start="1431" data-end="1449">10 million users</p>
</li>
<li class="" data-start="1450" data-end="1507">
<p class="" data-start="1452" data-end="1507">20% post something each day → 2 million posts per day</p>
</li>
<li class="" data-start="1508" data-end="1573">
<p class="" data-start="1510" data-end="1573">Each post averages 1KB of metadata → ~2GB of metadata per day</p>
</li>
<li class="" data-start="1574" data-end="1649">
<p class="" data-start="1576" data-end="1649">Peak posting window might be 50,000 posts per hour → ~14 posts per second</p>
</li>
</ul>
<h4 class="" data-start="1651" data-end="1672">Feed Read Volume</h4>
<ul data-start="1674" data-end="1948">
<li class="" data-start="1674" data-end="1725">
<p class="" data-start="1676" data-end="1725">Let’s say each user opens the app 3 times a day</p>
</li>
<li class="" data-start="1726" data-end="1785">
<p class="" data-start="1728" data-end="1785">10 million users × 3 = 30 million feed requests per day</p>
</li>
<li class="" data-start="1786" data-end="1839">
<p class="" data-start="1788" data-end="1839">That’s about 350 feed reads per second on average</p>
</li>
<li class="" data-start="1840" data-end="1906">
<p class="" data-start="1842" data-end="1906">Realistically, traffic is spiky, so peak could be 3–5x average</p>
</li>
<li class="" data-start="1907" data-end="1948">
<p class="" data-start="1909" data-end="1948">Peak feed reads: up to 1,500 per second</p>
</li>
</ul>
<h4 class="" data-start="1950" data-end="1975">Latency Expectations</h4>
<ul data-start="1977" data-end="2217">
<li class="" data-start="1977" data-end="2051">
<p class="" data-start="1979" data-end="2051">Feed requests should respond in under 300ms for a good user experience</p>
</li>
<li class="" data-start="2052" data-end="2133">
<p class="" data-start="2054" data-end="2133">Media loads separately via CDN, which offloads that pressure from the backend</p>
</li>
<li class="" data-start="2134" data-end="2217">
<p class="" data-start="2136" data-end="2217">Writes (creating a post) can take slightly longer if asynchronous fan-out is used</p>
</li>
</ul>
<h4 class="" data-start="2219" data-end="2248">Bottlenecks to Watch For</h4>
<ul data-start="2250" data-end="2523">
<li class="" data-start="2250" data-end="2314">
<p class="" data-start="2252" data-end="2314">Fan-out worker queue might fall behind if post volume spikes</p>
</li>
<li class="" data-start="2315" data-end="2378">
<p class="" data-start="2317" data-end="2378">Feed cache misses could cause slower reads and more DB load</p>
</li>
<li class="" data-start="2379" data-end="2468">
<p class="" data-start="2381" data-end="2468">If the followers list is large, building personalized feeds on-the-fly could be expensive</p>
</li>
<li class="" data-start="2469" data-end="2523">
<p class="" data-start="2471" data-end="2523">Redis memory limits if you&#8217;re caching feeds per user</p>
</li>
</ul>
<h4 class="" data-start="2525" data-end="2544">Cost Awareness</h4>
<ul data-start="2546" data-end="2732">
<li class="" data-start="2546" data-end="2601">
<p class="" data-start="2548" data-end="2601">Storing full feeds for each user might grow quickly</p>
</li>
<li class="" data-start="2602" data-end="2652">
<p class="" data-start="2604" data-end="2652">Using a CDN for media reduces cost and latency</p>
</li>
<li class="" data-start="2653" data-end="2732">
<p class="" data-start="2655" data-end="2732">Long-term storage of posts and media may require lifecycle rules or archiving.</p>
</li>
</ul>
<p class="" data-start="2734" data-end="2954">This section shows the interviewer you’re not just designing systems in a vacuum. You’re thinking about the real-world numbers, performance expectations, and infrastructure pressure points that will matter in production.</p>
<hr />
<h3 data-start="128" data-end="153">S: Storage and Scaling</h3>
<p class="" data-start="155" data-end="435">Now that you’ve walked through architecture, data flow, interfaces, and performance, it’s time to talk about where the data lives and how your system scales as traffic grows. You discuss database choices, schema design, replication, sharding, and caching strategies here.</p>
<p class="" data-start="437" data-end="565">You don’t need to be overly detailed, but you should be thoughtful about how your data is stored, queried, and scaled over time.</p>
<h4 data-start="567" data-end="584">What to Cover</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="586" data-end="1198">
<thead data-start="586" data-end="618">
<tr data-start="586" data-end="618">
<th data-start="586" data-end="593" data-col-size="sm">Area</th>
<th data-start="593" data-end="618" data-col-size="md">What to Think Through</th>
</tr>
</thead>
<tbody data-start="653" data-end="1198">
<tr data-start="653" data-end="733">
<td data-start="653" data-end="667" data-col-size="sm">Data Models</td>
<td data-start="667" data-end="733" data-col-size="md">What does a post look like? A feed entry? A user relationship?</td>
</tr>
<tr data-start="734" data-end="793">
<td data-start="734" data-end="750" data-col-size="sm">Database Type</td>
<td data-start="750" data-end="793" data-col-size="md">Are you using SQL, NoSQL, or both? Why?</td>
</tr>
<tr data-start="794" data-end="872">
<td data-start="794" data-end="805" data-col-size="sm">Indexing</td>
<td data-start="805" data-end="872" data-col-size="md">What indexes will improve performance for your access patterns?</td>
</tr>
<tr data-start="873" data-end="952">
<td data-start="873" data-end="883" data-col-size="sm">Caching</td>
<td data-start="883" data-end="952" data-col-size="md">What gets cached, and where? Redis, Memcached, or something else?</td>
</tr>
<tr data-start="953" data-end="1027">
<td data-start="953" data-end="967" data-col-size="sm">Replication</td>
<td data-start="967" data-end="1027" data-col-size="md">Are you using read replicas? How do you handle failover?</td>
</tr>
<tr data-start="1028" data-end="1108">
<td data-start="1028" data-end="1039" data-col-size="sm">Sharding</td>
<td data-start="1039" data-end="1108" data-col-size="md">What’s your strategy for horizontal scaling as data volume grows?</td>
</tr>
<tr data-start="1109" data-end="1198">
<td data-start="1109" data-end="1120" data-col-size="sm">Archival</td>
<td data-start="1120" data-end="1198" data-col-size="md">Do you expire or archive old content to save cost and improve performance?</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 data-start="1200" data-end="1241">Example: Real-Time Facebook News Feed</h4>
<p class="" data-start="1243" data-end="1284">Let’s start with some of the core models.</p>
<h4 class="" data-start="1286" data-end="1301">Post Table</h4>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="1303" data-end="1846">
<thead data-start="1303" data-end="1370">
<tr data-start="1303" data-end="1370">
<th data-start="1303" data-end="1322" data-col-size="sm">Column</th>
<th data-start="1322" data-end="1336" data-col-size="sm">Type</th>
<th data-start="1336" data-end="1370" data-col-size="sm">Description</th>
</tr>
</thead>
<tbody data-start="1439" data-end="1846">
<tr data-start="1439" data-end="1506">
<td data-start="1439" data-end="1458" data-col-size="sm"><code data-start="1441" data-end="1445">id</code></td>
<td data-start="1458" data-end="1472" data-col-size="sm">UUID</td>
<td data-start="1472" data-end="1506" data-col-size="sm">Unique post ID</td>
</tr>
<tr data-start="1507" data-end="1574">
<td data-start="1507" data-end="1526" data-col-size="sm"><code data-start="1509" data-end="1520">author_id</code></td>
<td data-col-size="sm" data-start="1526" data-end="1540">UUID</td>
<td data-col-size="sm" data-start="1540" data-end="1574">ID of the user who posted</td>
</tr>
<tr data-start="1575" data-end="1642">
<td data-start="1575" data-end="1594" data-col-size="sm"><code data-start="1577" data-end="1586">content</code></td>
<td data-start="1594" data-end="1608" data-col-size="sm">Text</td>
<td data-start="1608" data-end="1642" data-col-size="sm">The post content</td>
</tr>
<tr data-start="1643" data-end="1710">
<td data-start="1643" data-end="1662" data-col-size="sm"><code data-start="1645" data-end="1657">created_at</code></td>
<td data-col-size="sm" data-start="1662" data-end="1676">Timestamp</td>
<td data-col-size="sm" data-start="1676" data-end="1710">When the post was created</td>
</tr>
<tr data-start="1711" data-end="1778">
<td data-start="1711" data-end="1730" data-col-size="sm"><code data-start="1713" data-end="1724">media_url</code></td>
<td data-start="1730" data-end="1744" data-col-size="sm">String</td>
<td data-start="1744" data-end="1778" data-col-size="sm">Optional media file path</td>
</tr>
<tr data-start="1779" data-end="1846">
<td data-start="1779" data-end="1798" data-col-size="sm"><code data-start="1781" data-end="1793">visibility</code></td>
<td data-start="1798" data-end="1812" data-col-size="sm">Enum/String</td>
<td data-start="1812" data-end="1846" data-col-size="sm">public, friends-only, private</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<h4 class="" data-start="1848" data-end="1865">Feed Storage</h4>
<p class="" data-start="1867" data-end="1893">You have two options here:</p>
<ol data-start="1895" data-end="2239">
<li class="" data-start="1895" data-end="2048">
<p class="" data-start="1898" data-end="2048"><strong data-start="1898" data-end="1918">Fan-out on write</strong><br data-start="1918" data-end="1921" />Store a separate feed per user with a list of post IDs. This speeds up reads but requires more writes during post creation.</p>
</li>
<li class="" data-start="2050" data-end="2239">
<p class="" data-start="2053" data-end="2239"><strong data-start="2053" data-end="2072">Fan-out on read</strong><br data-start="2072" data-end="2075" />Store posts in a single global table and build each feed on the fly when a user opens the app. This keeps writes light but increases read complexity and latency.</p>
</li>
</ol>
<p class="" data-start="2241" data-end="2397">In many systems, a hybrid approach is used. For example, you might fan out to a limited number of followers for real-time delivery and use on-demand fetch for the rest.</p>
<h4 class="" data-start="2399" data-end="2420">Database Choices</h4>
<ul data-start="2422" data-end="2777">
<li class="" data-start="2422" data-end="2476">
<p class="" data-start="2424" data-end="2476"><strong data-start="2424" data-end="2450">Post and feed metadata</strong>: PostgreSQL or DynamoDB</p>
</li>
<li class="" data-start="2477" data-end="2575">
<p class="" data-start="2479" data-end="2575"><strong data-start="2479" data-end="2501">User relationships</strong>: Graph database (like Neo4j) or key-value store, depending on complexity</p>
</li>
<li class="" data-start="2576" data-end="2630">
<p class="" data-start="2578" data-end="2630"><strong data-start="2578" data-end="2592">Feed cache</strong>: Redis with TTL to reduce read load</p>
</li>
<li class="" data-start="2631" data-end="2685">
<p class="" data-start="2633" data-end="2685"><strong data-start="2633" data-end="2650">Media storage</strong>: S3 or equivalent object storage</p>
</li>
<li class="" data-start="2686" data-end="2777">
<p class="" data-start="2688" data-end="2777"><strong data-start="2688" data-end="2701">Analytics</strong>: Stream data to a logging or analytics pipeline (e.g,. BigQuery, ClickHouse)</p>
</li>
</ul>
<h4 class="" data-start="2779" data-end="2800">Scaling Strategy</h4>
<ul data-start="2802" data-end="3183">
<li class="" data-start="2802" data-end="2872">
<p class="" data-start="2804" data-end="2872">Use horizontal partitioning (sharding) by user ID for large tables</p>
</li>
<li class="" data-start="2873" data-end="2927">
<p class="" data-start="2875" data-end="2927">Add read replicas to handle higher read throughput</p>
</li>
<li class="" data-start="2928" data-end="2987">
<p class="" data-start="2930" data-end="2987">Use the cache-aside pattern for hot feeds and post metadata</p>
</li>
<li class="" data-start="2988" data-end="3036">
<p class="" data-start="2990" data-end="3036">Apply S3 lifecycle rules to expire old media</p>
</li>
<li class="" data-start="3037" data-end="3091">
<p class="" data-start="3039" data-end="3091">Break services into microservices as traffic grows</p>
</li>
<li class="" data-start="3092" data-end="3183">
<p class="" data-start="3094" data-end="3183">Deploy workers in autoscaling groups or use serverless (e.g., AWS Lambda) for fan-out jobs</p>
</li>
</ul>
<p class="" data-start="3185" data-end="3405">At this point, you’ve covered everything the interviewer needs to see. You’ve shown that you can design a system that meets real-world requirements, scales under load, handles failure, and balances performance with cost.</p>
<p data-start="3185" data-end="3405">To summarize the foundations, here is a table below:</p>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
<td><b>How to Prepare (What You Need to Know)</b></td>
</tr>
<tr>
<td><b>Design Process</b></td>
<td><span style="font-weight: 400;">Requirement gathering, defining scope, functional vs non-functional requirements</span></td>
<td><span style="font-weight: 400;">Practice asking clarifying questions, identifying core features vs stretch goals, and defining success metrics. Be ready to break down vague prompts into concrete components.</span></td>
</tr>
<tr>
<td><b>API Contracts</b></td>
<td><span style="font-weight: 400;">API schema design, input/output validation, OpenAPI/Swagger</span></td>
<td><span style="font-weight: 400;">Know how to design clean RESTful APIs. Understand idempotency, versioning, request validation, and standard status codes. Be familiar with documenting APIs using Swagger/OpenAPI.</span></td>
</tr>
<tr>
<td><b>Estimations</b></td>
<td><span style="font-weight: 400;">QPS, storage size, bandwidth, latency SLAs</span></td>
<td><span style="font-weight: 400;">Learn back-of-the-envelope calculations: requests/day → QPS, data size per item → monthly/yearly storage. Understand how to estimate SLA targets and their impact on design.</span></td>
</tr>
<tr>
<td><b>Tradeoffs</b></td>
<td><span style="font-weight: 400;">Latency vs consistency, availability vs cost, speed vs durability</span></td>
<td><span style="font-weight: 400;">Explain and justify tradeoffs (e.g., when you&#8217;d favor availability over consistency). Study CAP theorem and when to denormalize or cache data to meet performance targets.</span></td>
</tr>
</tbody>
</table>
<hr />
<h2 class="" data-start="54" data-end="84">Core System Design Concepts</h2>
<p class="" data-start="86" data-end="395">Before exploring individual technologies or patterns, it’s essential to understand the fundamental concepts that apply to almost every system design problem. You&#8217;ll use these mental tools to reason through tradeoffs, understand bottlenecks, and make architecture decisions under constraints.</p>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">API Design</span></td>
<td><span style="font-weight: 400;">REST vs GraphQL vs gRPC, endpoint naming, versioning, idempotency, pagination</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Authentication</span></td>
<td><span style="font-weight: 400;">JWT, session-based, OAuth2, OpenID Connect, refresh tokens</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Authorization</span></td>
<td><span style="font-weight: 400;">RBAC (role-based), ABAC (attribute-based), permission hierarchies</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Hashing</span></td>
<td><span style="font-weight: 400;">Hash functions (SHA256, MD5), consistent hashing, hash maps, and deduplication</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Data Modeling</span></td>
<td><span style="font-weight: 400;">ER diagrams, normalization/denormalization, data ownership</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Indexing</span></td>
<td><span style="font-weight: 400;">B-tree, hash index, composite index, covering index, full-text search</span></td>
</tr>
</tbody>
</table>
<h3 class="" data-start="153" data-end="167">API Design</h3>
<p class="" data-start="169" data-end="465">Good API design is about creating consistent, scalable, and easy-to-use interfaces. In system design interviews, especially for full-stack roles, this is where you show that you know how to design APIs that hold up in production, evolve cleanly over time, and support real product needs.</p>
<p class="" data-start="467" data-end="623">You don’t need to write out exact specs, but you should be able to describe the key endpoints, how they behave, and why they’re structured the way they are.</p>
<h4 class="" data-start="625" data-end="653">REST vs GraphQL vs gRPC</h4>
<ul data-start="655" data-end="1112">
<li class="" data-start="655" data-end="790">
<p class="" data-start="657" data-end="790"><strong data-start="657" data-end="665">REST</strong> is the default choice for most public-facing APIs. It’s simple, stateless, and built on standard HTTP verbs and conventions.</p>
</li>
<li class="" data-start="791" data-end="951">
<p class="" data-start="793" data-end="951"><strong data-start="793" data-end="804">GraphQL</strong> is useful when clients need flexibility or want to reduce overfetching. Implementing and cache is more complex but powerful for UI-driven apps.</p>
</li>
<li class="" data-start="952" data-end="1112">
<p class="" data-start="954" data-end="1112"><strong data-start="954" data-end="962">gRPC</strong> is best for fast, efficient internal service-to-service communication. It uses binary encoding and strongly typed contracts but isn’t browser-native.</p>
</li>
</ul>
<p class="" data-start="1114" data-end="1307">Use REST when simplicity and clarity matter. Use gRPC for internal systems that prioritize speed and strict contracts. Use GraphQL when frontend flexibility is worth the tradeoff in complexity.</p>
<h4 class="" data-start="1309" data-end="1329">Endpoint Naming</h4>
<p class="" data-start="1331" data-end="1358">Follow RESTful conventions:</p>
<ul data-start="1360" data-end="1505">
<li class="" data-start="1360" data-end="1389">
<p class="" data-start="1362" data-end="1389"><code data-start="1362" data-end="1374">GET /users</code> → list users</p>
</li>
<li class="" data-start="1390" data-end="1425">
<p class="" data-start="1392" data-end="1425"><code data-start="1392" data-end="1408">GET /users/:id</code> → get one user</p>
</li>
<li class="" data-start="1426" data-end="1459">
<p class="" data-start="1428" data-end="1459"><code data-start="1428" data-end="1441">POST /posts</code> → create a post</p>
</li>
<li class="" data-start="1460" data-end="1505">
<p class="" data-start="1462" data-end="1505"><code data-start="1462" data-end="1487">GET /posts/:id/comments</code> → nested resource</p>
</li>
</ul>
<p class="" data-start="1507" data-end="1620">Use plural nouns. Keep everything lowercase. Avoid putting actions in the URL — let HTTP methods define behavior.</p>
<h4 class="" data-start="1622" data-end="1637">Versioning</h4>
<p class="" data-start="1639" data-end="1703">Always assume your API will change. Add versioning from day one.</p>
<ul data-start="1705" data-end="1808">
<li class="" data-start="1705" data-end="1750">
<p class="" data-start="1707" data-end="1750">Use path-based versioning like <code data-start="1738" data-end="1748">/v1/feed</code></p>
</li>
<li class="" data-start="1751" data-end="1808">
<p class="" data-start="1753" data-end="1808">Avoid breaking changes by introducing <code data-start="1791" data-end="1796">/v2</code> when needed</p>
</li>
</ul>
<p class="" data-start="1810" data-end="1958">You can also version through headers or query params, but URL versioning is the most straightforward. It keeps things explicit and avoids surprises.</p>
<h4 class="" data-start="1960" data-end="1976">Idempotency</h4>
<p class="" data-start="1978" data-end="2039">APIs should be safe to retry without unintended side effects.</p>
<ul data-start="2041" data-end="2199">
<li class="" data-start="2041" data-end="2130">
<p class="" data-start="2043" data-end="2130"><strong data-start="2043" data-end="2051">POST</strong> is usually not idempotent, but can be made idempotent using an idempotency key</p>
</li>
<li class="" data-start="2131" data-end="2199">
<p class="" data-start="2133" data-end="2199"><strong data-start="2133" data-end="2140">PUT</strong>, <strong data-start="2142" data-end="2151">PATCH</strong>, and <strong data-start="2157" data-end="2167">DELETE</strong> should be idempotent by default</p>
</li>
</ul>
<p class="" data-start="2201" data-end="2314">Idempotency is critical for things like payments, uploads, and any action that might get retried after a failure.</p>
<h4 class="" data-start="2316" data-end="2331">Pagination</h4>
<p class="" data-start="2333" data-end="2398">Always paginate list endpoints. Avoid returning massive payloads.</p>
<ul data-start="2400" data-end="2517">
<li class="" data-start="2400" data-end="2445">
<p class="" data-start="2402" data-end="2445">Use <code data-start="2406" data-end="2413">limit</code> and <code data-start="2418" data-end="2426">offset</code> for simple cases</p>
</li>
<li class="" data-start="2446" data-end="2517">
<p class="" data-start="2448" data-end="2517">Use cursor-based pagination for better performance and deep scrolling</p>
</li>
</ul>
<p class="" data-start="2519" data-end="2683">Cursor-based pagination scales better because it avoids large <code data-start="2581" data-end="2589">OFFSET</code> scans on the database. It’s essential when dealing with feeds, timelines, or logs.</p>
<h4 class="" data-start="2685" data-end="2712">Example: News Feed API</h4>
<p class="" data-start="2714" data-end="2772">For a Facebook-style feed, here’s a typical API structure:</p>
<ul data-start="2774" data-end="2998">
<li class="" data-start="2774" data-end="2833">
<p class="" data-start="2776" data-end="2833"><code data-start="2776" data-end="2811">GET /feed?limit=20&amp;after=post_123</code> → fetch a feed page</p>
</li>
<li class="" data-start="2834" data-end="2870">
<p class="" data-start="2836" data-end="2870"><code data-start="2836" data-end="2848">POST /post</code> → create a new post</p>
</li>
<li class="" data-start="2871" data-end="2905">
<p class="" data-start="2873" data-end="2905"><code data-start="2873" data-end="2888">GET /post/:id</code> → fetch a post</p>
</li>
<li class="" data-start="2906" data-end="2944">
<p class="" data-start="2908" data-end="2944"><code data-start="2908" data-end="2926">DELETE /post/:id</code> → delete a post</p>
</li>
<li class="" data-start="2945" data-end="2998">
<p class="" data-start="2947" data-end="2998"><code data-start="2947" data-end="2965">POST /upload-url</code> → get a presigned S3 upload link</p>
</li>
</ul>
<p class="" data-start="3000" data-end="3197">You might use REST for public APIs, and gRPC for internal services (e.g. feed service calling the user graph or media service). GraphQL is optional — useful for complex UIs, but harder to maintain.</p>
<h4 class="" data-start="3199" data-end="3230">What Interviewers Look For</h4>
<ul data-start="3232" data-end="3435">
<li class="" data-start="3232" data-end="3287">
<p class="" data-start="3234" data-end="3287">Are your APIs predictable, consistent, and versioned?</p>
</li>
<li class="" data-start="3288" data-end="3321">
<p class="" data-start="3290" data-end="3321">Can they handle retries safely?</p>
</li>
<li class="" data-start="3322" data-end="3377">
<p class="" data-start="3324" data-end="3377">Do you plan for large datasets and paginated results?</p>
</li>
<li class="" data-start="3378" data-end="3435">
<p class="" data-start="3380" data-end="3435">Do you understand when different API styles make sense?</p>
</li>
</ul>
<h3 class="" data-start="132" data-end="150">Authentication</h3>
<p class="" data-start="152" data-end="410">Authentication is how your system verifies who a user is. In full-stack and backend system design interviews, you must know how user identity is handled at the API layer, what tokens or credentials are exchanged, and how long sessions remain valid.</p>
<p class="" data-start="412" data-end="565">You don’t need to implement full auth flows, but you should understand the common patterns, when to use them, and what tradeoffs come with each approach.</p>
<h4 class="" data-start="567" data-end="593">JWT (JSON Web Tokens)</h4>
<p class="" data-start="595" data-end="815">JWTs are a stateless way to represent user identity. The server encodes user data into a signed token and sends it to the client. The client returns the token with every request, and the server verifies its signature.</p>
<p class="" data-start="817" data-end="827"><strong data-start="817" data-end="825">Pros</strong></p>
<ul data-start="828" data-end="940">
<li class="" data-start="828" data-end="904">
<p class="" data-start="830" data-end="904">Stateless and scalable (no need to store sessions in memory or database)</p>
</li>
<li class="" data-start="905" data-end="940">
<p class="" data-start="907" data-end="940">Suitable for APIs and microservices</p>
</li>
</ul>
<p class="" data-start="942" data-end="952"><strong data-start="942" data-end="950">Cons</strong></p>
<ul data-start="953" data-end="1104">
<li class="" data-start="953" data-end="1024">
<p class="" data-start="955" data-end="1024">Revocation is hard — once issued, tokens are valid until expiration</p>
</li>
<li class="" data-start="1025" data-end="1104">
<p class="" data-start="1027" data-end="1104">Tokens can get large and may contain sensitive data if not designed carefully</p>
</li>
</ul>
<p class="" data-start="1106" data-end="1191">Use JWTs when scalability matters; session invalidation isn’t a hard requirement.</p>
<h4 class="" data-start="1193" data-end="1226">Session-Based Authentication</h4>
<p class="" data-start="1228" data-end="1385">In session-based auth, the server creates a session and stores it (in memory, Redis, or DB). The client gets a session cookie and sends it with each request.</p>
<p class="" data-start="1387" data-end="1397"><strong data-start="1387" data-end="1395">Pros</strong></p>
<ul data-start="1398" data-end="1476">
<li class="" data-start="1398" data-end="1435">
<p class="" data-start="1400" data-end="1435">Easy to revoke or expire sessions</p>
</li>
<li class="" data-start="1436" data-end="1476">
<p class="" data-start="1438" data-end="1476">Works well with traditional web apps</p>
</li>
</ul>
<p class="" data-start="1478" data-end="1488"><strong data-start="1478" data-end="1486">Cons</strong></p>
<ul data-start="1489" data-end="1598">
<li class="" data-start="1489" data-end="1567">
<p class="" data-start="1491" data-end="1567">Doesn’t scale easily without sticky sessions or distributed session stores</p>
</li>
<li class="" data-start="1568" data-end="1598">
<p class="" data-start="1570" data-end="1598">Requires server-side storage</p>
</li>
</ul>
<p class="" data-start="1600" data-end="1692">Use session-based auth for monoliths, admin panels, or systems with strong revocation needs.</p>
<h4 class="" data-start="1694" data-end="1705">OAuth2</h4>
<p class="" data-start="1707" data-end="1867">OAuth2 is a protocol that lets users grant access to third-party apps without giving them passwords. It’s used to log in via Google, Facebook, and GitHub.</p>
<p class="" data-start="1869" data-end="1971">Your system acts as the <strong data-start="1893" data-end="1912">resource server</strong>, and the third party acts as the <strong data-start="1946" data-end="1970">authorization server</strong>.</p>
<p class="" data-start="1973" data-end="2007"><strong data-start="1973" data-end="2005">Grant types you should know:</strong></p>
<ul data-start="2008" data-end="2179">
<li class="" data-start="2008" data-end="2049">
<p class="" data-start="2010" data-end="2049">Authorization Code (used in web apps)</p>
</li>
<li class="" data-start="2050" data-end="2100">
<p class="" data-start="2052" data-end="2100">Client Credentials (for server-to-server APIs)</p>
</li>
<li class="" data-start="2101" data-end="2126">
<p class="" data-start="2103" data-end="2126">Password (deprecated)</p>
</li>
<li class="" data-start="2127" data-end="2179">
<p class="" data-start="2129" data-end="2179">Refresh Token Flow (to renew access without login)</p>
</li>
</ul>
<p class="" data-start="2181" data-end="2222">You should know when and why to use each.</p>
<h4 class="" data-start="2224" data-end="2243">OpenID Connect</h4>
<p class="" data-start="2245" data-end="2431">OpenID Connect is a layer on top of OAuth 2 that adds identity information. It allows &#8220;Login with Google&#8221; to return profile data like email and name, not just authorization tokens.</p>
<p class="" data-start="2433" data-end="2481">If you hear OIDC, think: OAuth2 + user identity.</p>
<h4 class="" data-start="2483" data-end="2502">Refresh Tokens</h4>
<p class="" data-start="2504" data-end="2670">Access tokens should expire quickly (e.g., 15 minutes). A <strong data-start="2561" data-end="2578">refresh token</strong> allows the client to request a new access token without requiring the user to log in again.</p>
<p class="" data-start="2672" data-end="2692"><strong data-start="2672" data-end="2690">Best practice:</strong></p>
<ul data-start="2693" data-end="2853">
<li class="" data-start="2693" data-end="2739">
<p class="" data-start="2695" data-end="2739">Access token in memory or an HTTP-only cookie</p>
</li>
<li class="" data-start="2740" data-end="2791">
<p class="" data-start="2742" data-end="2791">The refresh token is stored securely and rotated often</p>
</li>
<li class="" data-start="2792" data-end="2853">
<p class="" data-start="2794" data-end="2853">Always have a way to revoke refresh tokens (e.g., on logout)</p>
</li>
</ul>
<h4 class="" data-start="2855" data-end="2886">What Interviewers Look For</h4>
<ul data-start="2888" data-end="3176">
<li class="" data-start="2888" data-end="2966">
<p class="" data-start="2890" data-end="2966">Do you understand the difference between authentication and authorization?</p>
</li>
<li class="" data-start="2967" data-end="3041">
<p class="" data-start="2969" data-end="3041">Can you choose the right authentication strategy for different types of systems?</p>
</li>
<li class="" data-start="3042" data-end="3097">
<p class="" data-start="3044" data-end="3097">Do you know the tradeoffs between JWT and sessions?</p>
</li>
<li class="" data-start="3098" data-end="3176">
<p class="" data-start="3100" data-end="3176">Are you aware of security best practices like token expiration and rotation?</p>
</li>
</ul>
<hr />
<h3 class="" data-start="78" data-end="95">Authorization</h3>
<p class="" data-start="97" data-end="305">Once a user is authenticated, the next question is: what are they allowed to do? That’s where authorization comes in. It controls access to actions, resources, and data based on roles, attributes, or context.</p>
<p class="" data-start="307" data-end="483">In a system design interview, you should be able to explain how you would restrict access to specific endpoints or features, and how the system enforces those rules efficiently.</p>
<h4 class="" data-start="485" data-end="522">RBAC (Role-Based Access Control)</h4>
<p class="" data-start="524" data-end="667">RBAC is the most common authorization model. Users are assigned roles (like <code data-start="600" data-end="607">admin</code>, <code data-start="609" data-end="620">moderator</code>, <code data-start="622" data-end="630">member</code>), and roles are granted permissions.</p>
<p class="" data-start="669" data-end="683"><strong data-start="669" data-end="681">Example:</strong></p>
<ul data-start="684" data-end="760">
<li class="" data-start="684" data-end="718">
<p class="" data-start="686" data-end="718">An <code data-start="689" data-end="696">admin</code> can delete any post</p>
</li>
<li class="" data-start="719" data-end="760">
<p class="" data-start="721" data-end="760">A <code data-start="723" data-end="731">member</code> can only edit their own post</p>
</li>
</ul>
<p class="" data-start="762" data-end="772"><strong data-start="762" data-end="770">Pros</strong></p>
<ul data-start="773" data-end="830">
<li class="" data-start="773" data-end="799">
<p class="" data-start="775" data-end="799">Simple to reason about</p>
</li>
<li class="" data-start="800" data-end="830">
<p class="" data-start="802" data-end="830">Easy to audit and maintain</p>
</li>
</ul>
<p class="" data-start="832" data-end="842"><strong data-start="832" data-end="840">Cons</strong></p>
<ul data-start="843" data-end="908">
<li class="" data-start="843" data-end="908">
<p class="" data-start="845" data-end="908">Doesn’t work well for highly dynamic or contextual access rules</p>
</li>
</ul>
<p class="" data-start="910" data-end="991">Use RBAC when roles and permissions are well defined and don’t change frequently.</p>
<h4 class="" data-start="993" data-end="1035">ABAC (Attribute-Based Access Control)</h4>
<p class="" data-start="1037" data-end="1257">ABAC uses attributes — not just roles — to determine permissions. This includes user properties (like department, location), resource properties (like owner, visibility), and context (like time of day or request source).</p>
<p class="" data-start="1259" data-end="1273"><strong data-start="1259" data-end="1271">Example:</strong></p>
<ul data-start="1274" data-end="1406">
<li class="" data-start="1274" data-end="1342">
<p class="" data-start="1276" data-end="1342">A user can access a file if <code data-start="1304" data-end="1340">user.department == file.department</code></p>
</li>
<li class="" data-start="1343" data-end="1406">
<p class="" data-start="1345" data-end="1406">A student can only view assignments for their enrolled course</p>
</li>
</ul>
<p class="" data-start="1408" data-end="1418"><strong data-start="1408" data-end="1416">Pros</strong></p>
<ul data-start="1419" data-end="1523">
<li class="" data-start="1419" data-end="1463">
<p class="" data-start="1421" data-end="1463">More flexible and fine-grained than RBAC</p>
</li>
<li class="" data-start="1464" data-end="1523">
<p class="" data-start="1466" data-end="1523">Great for complex organizations or multi-tenant systems</p>
</li>
</ul>
<p class="" data-start="1525" data-end="1535"><strong data-start="1525" data-end="1533">Cons</strong></p>
<ul data-start="1536" data-end="1613">
<li class="" data-start="1536" data-end="1574">
<p class="" data-start="1538" data-end="1574">More complex to implement and test</p>
</li>
<li class="" data-start="1575" data-end="1613">
<p class="" data-start="1577" data-end="1613">Harder to audit without good tooling</p>
</li>
</ul>
<p class="" data-start="1615" data-end="1717">Use ABAC when access decisions depend on more than just a role — especially in enterprise or B2B apps.</p>
<h4 class="" data-start="1719" data-end="1746">Permission Hierarchies</h4>
<p class="" data-start="1748" data-end="1867">Sometimes, you need more control than RBAC or ABAC provides on their own. This is where permission hierarchies come in.</p>
<p class="" data-start="1869" data-end="1909">You might define permission levels like:</p>
<ul data-start="1911" data-end="1950">
<li class="" data-start="1911" data-end="1919">
<p class="" data-start="1913" data-end="1919"><code data-start="1913" data-end="1919">read</code></p>
</li>
<li class="" data-start="1920" data-end="1929">
<p class="" data-start="1922" data-end="1929"><code data-start="1922" data-end="1929">write</code></p>
</li>
<li class="" data-start="1930" data-end="1940">
<p class="" data-start="1932" data-end="1940"><code data-start="1932" data-end="1940">delete</code></p>
</li>
<li class="" data-start="1941" data-end="1950">
<p class="" data-start="1943" data-end="1950"><code data-start="1943" data-end="1950">admin</code></p>
</li>
</ul>
<p class="" data-start="1952" data-end="2035">Then assign these permissions per resource (e.g., per project, team, post).</p>
<p class="" data-start="2037" data-end="2202">This is common in collaboration platforms like Google Docs, GitHub, or Notion, where one user might have full access to one document and read-only access to another.</p>
<p class="" data-start="2204" data-end="2215"><strong data-start="2204" data-end="2213">Tips:</strong></p>
<ul data-start="2216" data-end="2406">
<li class="" data-start="2216" data-end="2306">
<p class="" data-start="2218" data-end="2306">Store permissions in a normalized table (e.g., <code data-start="2265" data-end="2274">user_id</code>, <code data-start="2276" data-end="2289">resource_id</code>, <code data-start="2291" data-end="2303">permission</code>)</p>
</li>
<li class="" data-start="2307" data-end="2349">
<p class="" data-start="2309" data-end="2349">Cache results for faster access checks</p>
</li>
<li class="" data-start="2350" data-end="2406">
<p class="" data-start="2352" data-end="2406">Deny by default — allow only what’s explicitly granted</p>
</li>
</ul>
<h4 class="" data-start="2408" data-end="2439">What Interviewers Look For</h4>
<ul data-start="2441" data-end="2706">
<li class="" data-start="2441" data-end="2505">
<p class="" data-start="2443" data-end="2505">Can you design a system that enforces secure access to data?</p>
</li>
<li class="" data-start="2506" data-end="2565">
<p class="" data-start="2508" data-end="2565">Do you understand the difference between RBAC and ABAC?</p>
</li>
<li class="" data-start="2566" data-end="2641">
<p class="" data-start="2568" data-end="2641">Can you scale permission checks across millions of users and resources?</p>
</li>
<li class="" data-start="2642" data-end="2706">
<p class="" data-start="2644" data-end="2706">Have you thought about revocation, caching, and audit logging?</p>
</li>
</ul>
<h3 class="" data-start="79" data-end="90">Hashing</h3>
<p class="" data-start="92" data-end="406">Hashing is a core concept in backend system design. It’s used everywhere — from securing data to distributing traffic across servers to speeding up lookups. In interviews, you should be able to explain what a hash function does, where it’s useful, and when it becomes critical to system performance or scalability.</p>
<h4 class="" data-start="408" data-end="441">Hash Functions (SHA256, MD5)</h4>
<p class="" data-start="443" data-end="621">A hash function takes input data and returns a fixed-size string (a hash) that represents it. Good hash functions are deterministic, fast, and produce evenly distributed outputs.</p>
<ul data-start="623" data-end="897">
<li class="" data-start="623" data-end="757">
<p class="" data-start="625" data-end="757"><strong data-start="625" data-end="635">SHA256</strong> is a secure, cryptographic hash function used for integrity checks, password storage (with salt), and digital signatures.</p>
</li>
<li class="" data-start="758" data-end="897">
<p class="" data-start="760" data-end="897"><strong data-start="760" data-end="767">MD5</strong> is outdated and not secure for cryptographic use, but may still be used for quick checksum comparisons in non-sensitive contexts.</p>
</li>
</ul>
<p class="" data-start="899" data-end="915"><strong data-start="899" data-end="913">Use cases:</strong></p>
<ul data-start="916" data-end="1038">
<li class="" data-start="916" data-end="956">
<p class="" data-start="918" data-end="956">Storing hashed passwords (with salt)</p>
</li>
<li class="" data-start="957" data-end="1014">
<p class="" data-start="959" data-end="1014">Detecting data tampering (e.g., comparing file hashes)</p>
</li>
<li class="" data-start="1015" data-end="1038">
<p class="" data-start="1017" data-end="1038">Content deduplication</p>
</li>
</ul>
<h4 class="" data-start="1040" data-end="1054">Hash Maps</h4>
<p class="" data-start="1056" data-end="1235">A hash map (or hash table) uses hashing to provide <strong data-start="1107" data-end="1115">O(1)</strong> average time complexity for lookups, inserts, and deletes. It’s often used in caching, indexing, and in-memory storage.</p>
<p class="" data-start="1237" data-end="1268"><strong data-start="1237" data-end="1266">Example in system design:</strong></p>
<ul data-start="1269" data-end="1381">
<li class="" data-start="1269" data-end="1303">
<p class="" data-start="1271" data-end="1303">Storing a session map in Redis</p>
</li>
<li class="" data-start="1304" data-end="1338">
<p class="" data-start="1306" data-end="1338">Caching database query results</p>
</li>
<li class="" data-start="1339" data-end="1381">
<p class="" data-start="1341" data-end="1381">Indexing user data by ID for fast access</p>
</li>
</ul>
<h4 class="" data-start="1383" data-end="1406">Consistent Hashing</h4>
<p class="" data-start="1408" data-end="1559">Consistent hashing is a technique for distributing load across servers (or shards) that minimizes remapping when nodes are added or removed.</p>
<p class="" data-start="1561" data-end="1705">Adding a new server can cause nearly all keys to be remapped without consistent hashing. With it, only a small number of keys change ownership.</p>
<p class="" data-start="1707" data-end="1723"><strong data-start="1707" data-end="1721">Use cases:</strong></p>
<ul data-start="1724" data-end="1881">
<li class="" data-start="1724" data-end="1763">
<p class="" data-start="1726" data-end="1763">Load balancers distribute traffic</p>
</li>
<li class="" data-start="1764" data-end="1818">
<p class="" data-start="1766" data-end="1818">Distributed caches (e.g. Memcached, Redis Cluster)</p>
</li>
<li class="" data-start="1819" data-end="1881">
<p class="" data-start="1821" data-end="1881">Partitioning data in distributed databases or message queues</p>
</li>
</ul>
<h4 class="" data-start="1883" data-end="1901">Deduplication</h4>
<p class="" data-start="1903" data-end="2055">Hashing is often used to detect duplicate content. If two files produce the same hash, they’re assumed to be identical (with a small risk of collision).</p>
<p class="" data-start="2057" data-end="2071"><strong data-start="2057" data-end="2069">Example:</strong></p>
<ul data-start="2072" data-end="2262">
<li class="" data-start="2072" data-end="2187">
<p class="" data-start="2074" data-end="2187">A file upload service might compute a hash of each file and skip storing it if an identical hash already exists.</p>
</li>
<li class="" data-start="2188" data-end="2262">
<p class="" data-start="2190" data-end="2262">Used in cloud storage systems to save space and prevent redundant writes</p>
</li>
</ul>
<h4 class="" data-start="2264" data-end="2295">What Interviewers Look For</h4>
<ul data-start="2297" data-end="2576">
<li class="" data-start="2297" data-end="2367">
<p class="" data-start="2299" data-end="2367">Do you know when to use cryptographic vs non-cryptographic hashes?</p>
</li>
<li class="" data-start="2368" data-end="2432">
<p class="" data-start="2370" data-end="2432">Can you explain how consistent hashing improves scalability?</p>
</li>
<li class="" data-start="2433" data-end="2501">
<p class="" data-start="2435" data-end="2501">Do you understand how hash-based structures enable fast lookups?</p>
</li>
<li class="" data-start="2502" data-end="2576">
<p class="" data-start="2504" data-end="2576">Can you reason about edge cases like collisions and uneven distribution?</p>
</li>
</ul>
<h3 class="" data-start="81" data-end="98">Data Modeling</h3>
<p class="" data-start="100" data-end="388">Data modeling is about structuring your data to reflect real-world relationships and support the queries your system needs to run efficiently. In system design interviews, you should be able to sketch out core entities, their relationships, and how you plan to store and access them.</p>
<p class="" data-start="390" data-end="541">You don’t need to draw a complete ER diagram, but you should be able to explain your schema design choices and justify when you’d normalize or denormalize.</p>
<h4 class="" data-start="543" data-end="590">ER Diagrams (Entity-Relationship Diagrams)</h4>
<p class="" data-start="592" data-end="765">ER diagrams visually represent your data structure. They show entities (like <code data-start="669" data-end="675">User</code>, <code data-start="677" data-end="683">Post</code>, <code data-start="685" data-end="694">Comment</code>) and the relationships between them (one-to-many, many-to-many, etc.).</p>
<p class="" data-start="767" data-end="788"><strong data-start="767" data-end="786">Why it matters:</strong></p>
<ul data-start="789" data-end="958">
<li class="" data-start="789" data-end="853">
<p class="" data-start="791" data-end="853">Helps organize your thoughts when breaking down complex data</p>
</li>
<li class="" data-start="854" data-end="899">
<p class="" data-start="856" data-end="899">Clarifies how foreign keys and joins work</p>
</li>
<li class="" data-start="900" data-end="958">
<p class="" data-start="902" data-end="958">Useful for communication with teammates and interviewers</p>
</li>
</ul>
<p class="" data-start="960" data-end="974"><strong data-start="960" data-end="972">Example:</strong></p>
<ul data-start="975" data-end="1084">
<li class="" data-start="975" data-end="1004">
<p class="" data-start="977" data-end="1004">A <code data-start="979" data-end="985">User</code> has many <code data-start="995" data-end="1002">Posts</code></p>
</li>
<li class="" data-start="1005" data-end="1037">
<p class="" data-start="1007" data-end="1037">A <code data-start="1009" data-end="1015">Post</code> has many <code data-start="1025" data-end="1035">Comments</code></p>
</li>
<li class="" data-start="1038" data-end="1084">
<p class="" data-start="1040" data-end="1084">A <code data-start="1042" data-end="1051">Comment</code> belongs to a <code data-start="1065" data-end="1071">User</code> and a <code data-start="1078" data-end="1084">Post</code></p>
</li>
</ul>
<h4 class="" data-start="1086" data-end="1104">Normalization</h4>
<p class="" data-start="1106" data-end="1293">Normalization is the process of organizing data to reduce redundancy. Common standard forms eliminate duplicate fields, split data into related tables, and use foreign keys to connect them.</p>
<p class="" data-start="1295" data-end="1306"><strong data-start="1295" data-end="1304">Pros:</strong></p>
<ul data-start="1307" data-end="1424">
<li class="" data-start="1307" data-end="1349">
<p class="" data-start="1309" data-end="1349">Easier to update — one place to change</p>
</li>
<li class="" data-start="1350" data-end="1393">
<p class="" data-start="1352" data-end="1393">Avoids inconsistent or conflicting data</p>
</li>
<li class="" data-start="1394" data-end="1424">
<p class="" data-start="1396" data-end="1424">Reduces overall storage size</p>
</li>
</ul>
<p class="" data-start="1426" data-end="1437"><strong data-start="1426" data-end="1435">Cons:</strong></p>
<ul data-start="1438" data-end="1509">
<li class="" data-start="1438" data-end="1470">
<p class="" data-start="1440" data-end="1470">Requires more joins to query</p>
</li>
<li class="" data-start="1471" data-end="1509">
<p class="" data-start="1473" data-end="1509">Can be slower for read-heavy systems</p>
</li>
</ul>
<p class="" data-start="1511" data-end="1600">Use normalization when writing; consistency and integrity matter more than reading performance.</p>
<h4 class="" data-start="1602" data-end="1622">Denormalization</h4>
<p class="" data-start="1624" data-end="1802">Denormalization is when you deliberately duplicate data to reduce the number of joins and speed up reads. It’s common in analytics systems, feeds, dashboards, and caching layers.</p>
<p class="" data-start="1804" data-end="1815"><strong data-start="1804" data-end="1813">Pros:</strong></p>
<ul data-start="1816" data-end="1877">
<li class="" data-start="1816" data-end="1832">
<p class="" data-start="1818" data-end="1832">Faster reads</p>
</li>
<li class="" data-start="1833" data-end="1877">
<p class="" data-start="1835" data-end="1877">Fewer joins, better performance under load</p>
</li>
</ul>
<p class="" data-start="1879" data-end="1890"><strong data-start="1879" data-end="1888">Cons:</strong></p>
<ul data-start="1891" data-end="1951">
<li class="" data-start="1891" data-end="1919">
<p class="" data-start="1893" data-end="1919">Data can get out of sync</p>
</li>
<li class="" data-start="1920" data-end="1951">
<p class="" data-start="1922" data-end="1951">Harder to update consistently</p>
</li>
</ul>
<p class="" data-start="1953" data-end="2056">Use denormalization when the system is read-heavy and stale data is acceptable for performance reasons.</p>
<h4 class="" data-start="2058" data-end="2077">Data Ownership</h4>
<p class="" data-start="2079" data-end="2280">In microservice architectures, each service should own its data. That means the schema, database, and write access are fully controlled by the service. Other services are read via APIs, not direct queries.</p>
<p class="" data-start="2282" data-end="2303"><strong data-start="2282" data-end="2301">Why it matters:</strong></p>
<ul data-start="2304" data-end="2422">
<li class="" data-start="2304" data-end="2348">
<p class="" data-start="2306" data-end="2348">Prevents tight coupling between services</p>
</li>
<li class="" data-start="2349" data-end="2380">
<p class="" data-start="2351" data-end="2380">Makes data boundaries clear</p>
</li>
<li class="" data-start="2381" data-end="2422">
<p class="" data-start="2383" data-end="2422">Simplifies ownership and responsibility</p>
</li>
</ul>
<p class="" data-start="2424" data-end="2573">For example, the User Service owns the <code data-start="2463" data-end="2470">users</code> table. The Post Service might have a <code data-start="2508" data-end="2517">user_id</code> foreign key, but it never directly queries the User DB.</p>
<h4 class="" data-start="2575" data-end="2606">What Interviewers Look For</h4>
<ul data-start="2608" data-end="2860">
<li class="" data-start="2608" data-end="2671">
<p class="" data-start="2610" data-end="2671">Can you model real-world problems with clean relationships?</p>
</li>
<li class="" data-start="2672" data-end="2733">
<p class="" data-start="2674" data-end="2733">Do you know when to use normalization vs denormalization?</p>
</li>
<li class="" data-start="2734" data-end="2804">
<p class="" data-start="2736" data-end="2804">Can you give some reasons for data duplication, tradeoffs, and performance?</p>
</li>
<li class="" data-start="2805" data-end="2860">
<p class="" data-start="2807" data-end="2860">Do you keep service boundaries and ownership in mind?</p>
</li>
</ul>
<h3 class="" data-start="75" data-end="87">Indexing</h3>
<p class="" data-start="89" data-end="340">Indexing is how databases speed up queries. Without indexes, every query becomes a full table scan, which doesn&#8217;t scale. In system design interviews, you’re expected to know how indexing works and how to apply it to improve performance.</p>
<p class="" data-start="342" data-end="483">You don’t need to dive into database internals, but you should be able to explain which index type is appropriate based on the query pattern.</p>
<h4 class="" data-start="485" data-end="502">B-tree Index</h4>
<p class="" data-start="504" data-end="671">B-tree (balanced tree) indexes are the default index type in most relational databases (like PostgreSQL and MySQL). They work well for range queries and sorted access.</p>
<p class="" data-start="673" data-end="689"><strong data-start="673" data-end="687">Use cases:</strong></p>
<ul data-start="690" data-end="818">
<li class="" data-start="690" data-end="729">
<p class="" data-start="692" data-end="729">Searching for values within a range</p>
</li>
<li class="" data-start="730" data-end="755">
<p class="" data-start="732" data-end="755">Sorting by date or ID</p>
</li>
<li class="" data-start="756" data-end="818">
<p class="" data-start="758" data-end="818">WHERE conditions like <code data-start="780" data-end="790">age &gt; 30</code> or <code data-start="794" data-end="818">created_at BETWEEN ...</code></p>
</li>
</ul>
<h4 class="" data-start="820" data-end="835">Hash Index</h4>
<p class="" data-start="837" data-end="980">Hash indexes use a hash function to map keys directly to a location. They’re fast for exact matches but don’t support range queries or sorting.</p>
<p class="" data-start="982" data-end="998"><strong data-start="982" data-end="996">Use cases:</strong></p>
<ul data-start="999" data-end="1101">
<li class="" data-start="999" data-end="1066">
<p class="" data-start="1001" data-end="1066">Fast lookups with <code data-start="1019" data-end="1022">=</code> (e.g. <code data-start="1029" data-end="1063">WHERE email = 'user@example.com'</code>)</p>
</li>
<li class="" data-start="1067" data-end="1101">
<p class="" data-start="1069" data-end="1101">Not useful for <code data-start="1084" data-end="1087">&gt;</code> or <code data-start="1091" data-end="1101">ORDER BY</code></p>
</li>
</ul>
<p class="" data-start="1103" data-end="1206"><strong data-start="1103" data-end="1112">Note:</strong> Many relational DBs don’t use hash indexes by default because B-trees offer more flexibility.</p>
<h4 class="" data-start="1208" data-end="1228">Composite Index</h4>
<p class="" data-start="1230" data-end="1385">A composite index (also called a multi-column index) is created on more than one column. It helps when you often query or sort by multiple fields together.</p>
<p class="" data-start="1387" data-end="1401"><strong data-start="1387" data-end="1399">Example:</strong></p>
<ul data-start="1402" data-end="1508">
<li class="" data-start="1402" data-end="1438">
<p class="" data-start="1404" data-end="1438">Index on <code data-start="1413" data-end="1436">(user_id, created_at)</code></p>
</li>
<li class="" data-start="1439" data-end="1508">
<p class="" data-start="1441" data-end="1508">Speeds up queries like <code data-start="1464" data-end="1508">WHERE user_id = ? ORDER BY created_at DESC</code></p>
</li>
</ul>
<p class="" data-start="1510" data-end="1659"><strong data-start="1510" data-end="1524">Important:</strong> The order of columns in a composite index matters. An index on <code data-start="1588" data-end="1596">(a, b)</code> can help with queries on <code data-start="1622" data-end="1625">a</code> or <code data-start="1629" data-end="1636">a + b</code>, but not on <code data-start="1649" data-end="1652">b</code> alone.</p>
<h4 class="" data-start="1661" data-end="1680">Covering Index</h4>
<p class="" data-start="1682" data-end="1819">A covering index includes all the columns a query needs, so the database doesn’t need to access the table at all (no “table lookup”).</p>
<p class="" data-start="1821" data-end="1835"><strong data-start="1821" data-end="1833">Example:</strong></p>
<ul data-start="1836" data-end="1980">
<li class="" data-start="1836" data-end="1893">
<p class="" data-start="1838" data-end="1893">You query <code data-start="1848" data-end="1891">SELECT title FROM posts WHERE user_id = ?</code></p>
</li>
<li class="" data-start="1894" data-end="1980">
<p class="" data-start="1896" data-end="1980">If you have an index on <code data-start="1920" data-end="1938">(user_id, title)</code>, the query is fully served from the index</p>
</li>
</ul>
<p class="" data-start="1982" data-end="1997"><strong data-start="1982" data-end="1995">Benefits:</strong></p>
<ul data-start="1998" data-end="2035">
<li class="" data-start="1998" data-end="2016">
<p class="" data-start="2000" data-end="2016">Faster queries</p>
</li>
<li class="" data-start="2017" data-end="2035">
<p class="" data-start="2019" data-end="2035">Fewer disk reads</p>
</li>
</ul>
<p class="" data-start="2037" data-end="2115">Use covering indexes for high-traffic queries that always use the same fields.</p>
<h4 class="" data-start="2117" data-end="2138">Full-Text Search</h4>
<p class="" data-start="2140" data-end="2257">Full-text indexes are specialized for searching within large bodies of text, like articles or user-generated content.</p>
<p class="" data-start="2259" data-end="2275"><strong data-start="2259" data-end="2273">Use cases:</strong></p>
<ul data-start="2276" data-end="2379">
<li class="" data-start="2276" data-end="2313">
<p class="" data-start="2278" data-end="2313">Searching the post content by keyword</p>
</li>
<li class="" data-start="2314" data-end="2348">
<p class="" data-start="2316" data-end="2348">Autocomplete or fuzzy matching</p>
</li>
<li class="" data-start="2349" data-end="2379">
<p class="" data-start="2351" data-end="2379">Ranking results by relevance</p>
</li>
</ul>
<p class="" data-start="2381" data-end="2465">Most databases support this through extensions or separate tools like Elasticsearch.</p>
<h4 class="" data-start="2467" data-end="2498">What Interviewers Look For</h4>
<ul data-start="2500" data-end="2741">
<li class="" data-start="2500" data-end="2555">
<p class="" data-start="2502" data-end="2555">Can you match index types to common query patterns?</p>
</li>
<li class="" data-start="2556" data-end="2624">
<p class="" data-start="2558" data-end="2624">Do you know the tradeoffs between speed, memory, and write cost?</p>
</li>
<li class="" data-start="2625" data-end="2687">
<p class="" data-start="2627" data-end="2687">Can you give a reason for index maintenance and write overhead?</p>
</li>
<li class="" data-start="2688" data-end="2741">
<p class="" data-start="2690" data-end="2741">Do you think ahead about scaling read-heavy tables?</p>
</li>
</ul>
<hr />
<h3><b style="font-size: 16px;"><br />
Databases</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Database Types</span></td>
<td><span style="font-weight: 400;">Relational (Postgres, MySQL), NoSQL (MongoDB, Cassandra, DynamoDB), Time Series (InfluxDB)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Transactions</span></td>
<td><span style="font-weight: 400;">ACID, two-phase commit, optimistic vs pessimistic locking</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Schema Design</span></td>
<td><span style="font-weight: 400;">Normalization levels, handling large tables, surrogate vs natural keys</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Scaling Techniques</span></td>
<td><span style="font-weight: 400;">Sharding (horizontal), replication (read-replicas), federation</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Consistency Models</span></td>
<td><span style="font-weight: 400;">Strong vs eventual, causal, quorum-based consistency</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Read/Write Optimization</span></td>
<td><span style="font-weight: 400;">Read replicas, write-ahead logs (WAL), and batching</span></td>
</tr>
</tbody>
</table>
<h3 class="" data-start="121" data-end="178">Kafka vs. Traditional Database for Event Streaming</h3>
<p><strong data-start="0" data-end="16">Apache Kafka</strong> is a <strong data-start="22" data-end="62">distributed event streaming platform</strong> that builds <strong data-start="77" data-end="132">real-time data pipelines and streaming applications</strong>. Initially developed by LinkedIn, it is now open-source and part of the Apache Software Foundation.</p>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="180" data-end="1902">
<thead data-start="180" data-end="352">
<tr data-start="180" data-end="352">
<th data-start="180" data-end="213" data-col-size="sm">Feature</th>
<th data-start="213" data-end="289" data-col-size="md"><strong data-start="215" data-end="224">Kafka</strong></th>
<th data-start="289" data-end="352" data-col-size="md"><strong data-start="291" data-end="315">Traditional DB Table</strong></th>
</tr>
</thead>
<tbody data-start="526" data-end="1902">
<tr data-start="526" data-end="697">
<td data-start="526" data-end="558" data-col-size="sm"><strong data-start="528" data-end="542">Throughput</strong></td>
<td data-start="558" data-end="633" data-col-size="md">High (millions of messages/sec)</td>
<td data-col-size="md" data-start="633" data-end="697">Low/Moderate (concurrent writes can bottleneck)</td>
</tr>
<tr data-start="698" data-end="869">
<td data-start="698" data-end="730" data-col-size="sm"><strong data-start="700" data-end="723">Real-time Streaming</strong></td>
<td data-start="730" data-end="805" data-col-size="md">Built for real-time pub/sub pipelines</td>
<td data-col-size="md" data-start="805" data-end="869">Not built for real-time; polling adds latency</td>
</tr>
<tr data-start="870" data-end="1041">
<td data-start="870" data-end="902" data-col-size="sm"><strong data-start="872" data-end="886">Decoupling</strong></td>
<td data-start="902" data-end="977" data-col-size="md">Multiple consumers can read the same data independently</td>
<td data-col-size="md" data-start="977" data-end="1041">Hard to decouple producers/consumers cleanly</td>
</tr>
<tr data-start="1042" data-end="1213">
<td data-start="1042" data-end="1074" data-col-size="sm"><strong data-start="1044" data-end="1059">Scalability</strong></td>
<td data-start="1074" data-end="1149" data-col-size="md">Horizontally scalable (partitions across brokers)</td>
<td data-col-size="md" data-start="1149" data-end="1213">Scaling write-heavy DB tables is hard</td>
</tr>
<tr data-start="1214" data-end="1385">
<td data-start="1214" data-end="1246" data-col-size="sm"><strong data-start="1216" data-end="1230">Durability</strong></td>
<td data-col-size="md" data-start="1246" data-end="1321">Data stored for configurable retention (even forever)</td>
<td data-col-size="md" data-start="1321" data-end="1385">Data often updated/deleted; hard to reprocess</td>
</tr>
<tr data-start="1386" data-end="1557">
<td data-start="1386" data-end="1418" data-col-size="sm"><strong data-start="1388" data-end="1411">Reprocessing Events</strong></td>
<td data-start="1418" data-end="1493" data-col-size="md">Easy — consumers can rewind and reconsume data</td>
<td data-col-size="md" data-start="1493" data-end="1557">Hard — must write complex logic to &#8220;replay&#8221; DB rows</td>
</tr>
<tr data-start="1558" data-end="1730">
<td data-start="1558" data-end="1590" data-col-size="sm"><strong data-start="1560" data-end="1583">Ordering Guarantees</strong></td>
<td data-col-size="md" data-start="1590" data-end="1666">Guaranteed within a partition</td>
<td data-col-size="md" data-start="1666" data-end="1730">No natural event ordering unless manually managed</td>
</tr>
<tr data-start="1731" data-end="1902">
<td data-start="1731" data-end="1763" data-col-size="sm"><strong data-start="1733" data-end="1758">Backpressure Handling</strong></td>
<td data-col-size="md" data-start="1763" data-end="1838">Consumers can lag behind producers without data loss</td>
<td data-col-size="md" data-start="1838" data-end="1902">Lagging consumers</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 class="" data-start="1909" data-end="1938">TL;DR: Use Kafka When…</h3>
<ul data-start="1940" data-end="2271">
<li class="" data-start="1940" data-end="2030">
<p class="" data-start="1942" data-end="2030">You need <strong data-start="1951" data-end="1996">real-time, high-throughput data pipelines</strong> (e.g. log processing, analytics).</p>
</li>
<li class="" data-start="2031" data-end="2112">
<p class="" data-start="2033" data-end="2112">You want <strong data-start="2042" data-end="2062">multiple systems</strong> to consume the same stream of data independently.</p>
</li>
<li class="" data-start="2113" data-end="2193">
<p class="" data-start="2115" data-end="2193">You need <strong data-start="2124" data-end="2153">reliable message delivery</strong> and want to <strong data-start="2166" data-end="2186">reprocess events</strong> later.</p>
</li>
<li class="" data-start="2194" data-end="2271">
<p class="" data-start="2196" data-end="2271">You need <strong data-start="2205" data-end="2235">event-driven architectures</strong> or <strong data-start="2239" data-end="2270">microservices communication</strong>.</p>
</li>
</ul>
<h3><b>Caching</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Caching Layers</span></td>
<td><span style="font-weight: 400;">Client-side, CDN (Cloudflare), reverse proxy (Varnish), backend (Redis)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Cache Invalidation</span></td>
<td><span style="font-weight: 400;">TTL, write-through, write-back, cache busting</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Eviction Policies</span></td>
<td><span style="font-weight: 400;">LRU, LFU, FIFO</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Data Freshness</span></td>
<td><span style="font-weight: 400;">Stale-while-revalidate, background refresh</span></td>
</tr>
</tbody>
</table>
<p class="" data-start="183" data-end="382">Effective caching is critical for building fast, scalable, and resilient systems. Choosing the right caching layer depends on the type of content, the access patterns, and the freshness requirements.</p>
<h3 class="" data-start="389" data-end="423">CDN (Content Delivery Network)</h3>
<p class="" data-start="425" data-end="505"><strong data-start="425" data-end="437">Best for</strong>: Static assets like images, CSS, JavaScript, fonts, and HTML files.</p>
<p class="" data-start="507" data-end="669"><strong data-start="507" data-end="523">How it works</strong>: CDNs replicate content across geographically distributed edge servers. When a user requests a file, the CDN serves it from the nearest location.</p>
<p class="" data-start="671" data-end="692"><strong data-start="671" data-end="691">Common use cases</strong>:</p>
<ul data-start="693" data-end="791">
<li class="" data-start="693" data-end="725">
<p class="" data-start="695" data-end="725">Website assets (JS/CSS/images)</p>
</li>
<li class="" data-start="726" data-end="765">
<p class="" data-start="728" data-end="765">Static HTML pages for marketing sites</p>
</li>
<li class="" data-start="766" data-end="791">
<p class="" data-start="768" data-end="791">Video streaming content</p>
</li>
</ul>
<p class="" data-start="793" data-end="853"><strong data-start="793" data-end="805">Examples</strong>: Cloudflare CDN, AWS CloudFront, Akamai, Fastly</p>
<p class="" data-start="855" data-end="868"><strong data-start="855" data-end="867">Benefits</strong>:</p>
<ul data-start="869" data-end="963">
<li class="" data-start="869" data-end="924">
<p class="" data-start="871" data-end="924">Reduces latency by serving content closer to the user</p>
</li>
<li class="" data-start="925" data-end="963">
<p class="" data-start="927" data-end="963">Decreases the load on your origin server</p>
</li>
</ul>
<p class="" data-start="965" data-end="988"><strong data-start="965" data-end="987">Cache invalidation</strong>:</p>
<ul data-start="989" data-end="1156">
<li class="" data-start="989" data-end="1059">
<p class="" data-start="991" data-end="1059">Typically handled via <code data-start="1013" data-end="1028">Cache-Control</code>, <code data-start="1030" data-end="1036">ETag</code>, and <code data-start="1042" data-end="1051">Expires</code> headers</p>
</li>
<li class="" data-start="1060" data-end="1156">
<p class="" data-start="1062" data-end="1156">Manual invalidation supported via purge APIs or cache-busting URLs (e.g., <code data-start="1136" data-end="1155">filename.12345.js</code>)</p>
</li>
</ul>
<h3 class="" data-start="1163" data-end="1205">Cloudflare (or Similar Edge Platforms)</h3>
<p class="" data-start="1207" data-end="1249"><strong data-start="1207" data-end="1219">Best for</strong>: CDN + security + edge logic.</p>
<p class="" data-start="1251" data-end="1490">Cloudflare can act as a CDN and a smart reverse proxy with additional features like DDoS protection, WAF (Web Application Firewall), and DNS. Using Cloudflare Workers or Page Rules, you can also cache dynamic API responses at the edge.</p>
<p class="" data-start="1492" data-end="1506"><strong data-start="1492" data-end="1505">Use cases</strong>:</p>
<ul data-start="1507" data-end="1637">
<li class="" data-start="1507" data-end="1559">
<p class="" data-start="1509" data-end="1559">Protecting and accelerating a frontend application</p>
</li>
<li class="" data-start="1560" data-end="1599">
<p class="" data-start="1562" data-end="1599">Caching GraphQL or REST API responses</p>
</li>
<li class="" data-start="1600" data-end="1637">
<p class="" data-start="1602" data-end="1637">Edge-based A/B testing or redirects</p>
</li>
</ul>
<p class="" data-start="1639" data-end="1662"><strong data-start="1639" data-end="1661">Cache invalidation</strong>:</p>
<ul data-start="1663" data-end="1759">
<li class="" data-start="1663" data-end="1700">
<p class="" data-start="1665" data-end="1700">Edge caching can be purged manually</p>
</li>
<li class="" data-start="1701" data-end="1759">
<p class="" data-start="1703" data-end="1759">TTLs and <code data-start="1712" data-end="1727">Cache-Control</code> headers apply similarly to CDNs</p>
</li>
</ul>
<h3 class="" data-start="1766" data-end="1806">Reverse Proxy (e.g., NGINX, Varnish)</h3>
<p class="" data-start="1808" data-end="1883"><strong data-start="1808" data-end="1820">Best for</strong>: Caching full or partial HTTP responses near your application.</p>
<p class="" data-start="1885" data-end="2026">A reverse proxy sits between the client and your app. It can serve cached versions of dynamic content, reducing the load on backend services.</p>
<p class="" data-start="2028" data-end="2042"><strong data-start="2028" data-end="2041">Use cases</strong>:</p>
<ul data-start="2043" data-end="2214">
<li class="" data-start="2043" data-end="2107">
<p class="" data-start="2045" data-end="2107">Caching expensive dynamic pages (e.g., rendered blog articles)</p>
</li>
<li class="" data-start="2108" data-end="2153">
<p class="" data-start="2110" data-end="2153">Handling surge traffic to popular endpoints</p>
</li>
<li class="" data-start="2154" data-end="2214">
<p class="" data-start="2156" data-end="2214">Internal caching layer in monoliths or service mesh setups</p>
</li>
</ul>
<p class="" data-start="2216" data-end="2239"><strong data-start="2216" data-end="2238">Cache invalidation</strong>:</p>
<ul data-start="2240" data-end="2355">
<li class="" data-start="2240" data-end="2266">
<p class="" data-start="2242" data-end="2266">Based on URL and headers</p>
</li>
<li class="" data-start="2267" data-end="2317">
<p class="" data-start="2269" data-end="2317">Often uses custom logic or cache purging scripts</p>
</li>
<li class="" data-start="2318" data-end="2355">
<p class="" data-start="2320" data-end="2355">TTLs can be configured per endpoint</p>
</li>
</ul>
<h3 class="" data-start="2362" data-end="2371">Redis</h3>
<p class="" data-start="2373" data-end="2460"><strong data-start="2373" data-end="2385">Best for</strong>: In-memory caching of computed data, user sessions, and ephemeral storage.</p>
<p class="" data-start="2462" data-end="2630">Redis is an in-memory data store that supports various data structures (strings, hashes, sets, etc.). It’s highly performant and can persist data to disk if configured.</p>
<p class="" data-start="2632" data-end="2646"><strong data-start="2632" data-end="2645">Use cases</strong>:</p>
<ul data-start="2647" data-end="2768">
<li class="" data-start="2647" data-end="2679">
<p class="" data-start="2649" data-end="2679">Caching database query results</p>
</li>
<li class="" data-start="2680" data-end="2707">
<p class="" data-start="2682" data-end="2707">Storing user session data</p>
</li>
<li class="" data-start="2708" data-end="2732">
<p class="" data-start="2710" data-end="2732">Rate limiting counters</p>
</li>
<li class="" data-start="2733" data-end="2768">
<p class="" data-start="2735" data-end="2768">Storing ephemeral tokens or flags</p>
</li>
</ul>
<p class="" data-start="2770" data-end="2792"><strong data-start="2770" data-end="2791">Eviction policies</strong>:</p>
<ul data-start="2793" data-end="2922">
<li class="" data-start="2793" data-end="2871">
<p class="" data-start="2795" data-end="2871">LRU (Least Recently Used), LFU (Least Frequently Used), TTL-based, or manual</p>
</li>
<li class="" data-start="2872" data-end="2922">
<p class="" data-start="2874" data-end="2922">You can set expiry per key (<code data-start="2902" data-end="2910">EXPIRE</code> or <code data-start="2914" data-end="2921">SETEX</code>)</p>
</li>
</ul>
<p class="" data-start="2924" data-end="2947"><strong data-start="2924" data-end="2946">Cache invalidation</strong>:</p>
<ul data-start="2948" data-end="3014">
<li class="" data-start="2948" data-end="2979">
<p class="" data-start="2950" data-end="2979">Manual deletion (e.g., <code data-start="2973" data-end="2978">DEL</code>)</p>
</li>
<li class="" data-start="2980" data-end="3014">
<p class="" data-start="2982" data-end="3014">Automatic expiration after a TTL</p>
</li>
</ul>
<h3 class="" data-start="3021" data-end="3034">Memcached</h3>
<p class="" data-start="3036" data-end="3108"><strong data-start="3036" data-end="3048">Best for</strong>: Lightweight, simple key-value caching with no persistence.</p>
<p class="" data-start="3110" data-end="3302">Memcached is a fast, in-memory cache ideal for use cases where persistence and advanced data types are unnecessary. In some scenarios, it&#8217;s simpler and faster than Redis but less feature-rich.</p>
<p class="" data-start="3304" data-end="3318"><strong data-start="3304" data-end="3317">Use cases</strong>:</p>
<ul data-start="3319" data-end="3442">
<li class="" data-start="3319" data-end="3369">
<p class="" data-start="3321" data-end="3369">Caching small, frequently accessed query results</p>
</li>
<li class="" data-start="3370" data-end="3404">
<p class="" data-start="3372" data-end="3404">Transient data for API responses</p>
</li>
<li class="" data-start="3405" data-end="3442">
<p class="" data-start="3407" data-end="3442">Session caching (in stateless apps)</p>
</li>
</ul>
<p class="" data-start="3444" data-end="3466"><strong data-start="3444" data-end="3465">Eviction policies</strong>:</p>
<ul data-start="3467" data-end="3496">
<li class="" data-start="3467" data-end="3477">
<p class="" data-start="3469" data-end="3477">LRU only</p>
</li>
<li class="" data-start="3478" data-end="3496">
<p class="" data-start="3480" data-end="3496">TTL-based expiry</p>
</li>
</ul>
<p class="" data-start="3498" data-end="3514"><strong data-start="3498" data-end="3513">Limitations</strong>:</p>
<ul data-start="3515" data-end="3602">
<li class="" data-start="3515" data-end="3531">
<p class="" data-start="3517" data-end="3531">No persistence</p>
</li>
<li class="" data-start="3532" data-end="3560">
<p class="" data-start="3534" data-end="3560">No complex data structures</p>
</li>
<li class="" data-start="3561" data-end="3602">
<p class="" data-start="3563" data-end="3602">No replication or clustering (natively)</p>
</li>
</ul>
<h3 class="" data-start="3609" data-end="3650">Cache Invalidation and Data Freshness</h3>
<p class="" data-start="3652" data-end="3756">One of the most complex problems in caching is invalidation &#8211; knowing <strong data-start="3717" data-end="3755">when to update or evict stale data</strong>.</p>
<p class="" data-start="3758" data-end="3777"><strong data-start="3758" data-end="3776">Key strategies</strong>:</p>
<ol data-start="3778" data-end="4168">
<li class="" data-start="3778" data-end="3851">
<p class="" data-start="3781" data-end="3851"><strong data-start="3781" data-end="3803">Time-to-Live (TTL)</strong>: Set a fixed expiration time on cached content.</p>
</li>
<li class="" data-start="3852" data-end="3923">
<p class="" data-start="3855" data-end="3923"><span style="box-sizing: border-box; margin: 0px; padding: 0px;"><strong>Write-through caching</strong>: Data is written together in the cache and the DB.</span></p>
</li>
<li class="" data-start="3924" data-end="4006">
<p class="" data-start="3927" data-end="4006"><strong data-start="3927" data-end="3951">Write-behind caching</strong>: Cache is updated first; DB is updated asynchronously.</p>
</li>
<li class="" data-start="4007" data-end="4083">
<p class="" data-start="4010" data-end="4083"><strong data-start="4010" data-end="4033">Manual invalidation</strong>: Cache is explicitly cleared when updates happen.</p>
</li>
<li class="" data-start="4084" data-end="4168">
<p class="" data-start="4087" data-end="4168"><strong data-start="4087" data-end="4104">Cache busting</strong>: Use versioned keys or URLs to force new content to be fetched.</p>
</li>
</ol>
<p class="" data-start="4170" data-end="4189"><strong data-start="4170" data-end="4188">Considerations</strong>:</p>
<ul data-start="4190" data-end="4395">
<li class="" data-start="4190" data-end="4240">
<p class="" data-start="4192" data-end="4240"><strong data-start="4192" data-end="4212">Strong freshness</strong>: Use low TTL or no caching.</p>
</li>
<li class="" data-start="4241" data-end="4306">
<p class="" data-start="4243" data-end="4306"><strong data-start="4243" data-end="4267">Eventual consistency</strong>: Use higher TTLs and accept staleness.</p>
</li>
<li class="" data-start="4307" data-end="4395">
<p class="" data-start="4309" data-end="4395"><strong data-start="4309" data-end="4330">Real-time systems</strong>: Combine pub/sub (e.g., Redis Streams) to trigger invalidations.</p>
</li>
</ul>
<h3 class="" data-start="4402" data-end="4413">Summary</h3>
<div class="_tableContainer_16hzy_1">
<div class="_tableWrapper_16hzy_14 group flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="4415" data-end="5196">
<thead data-start="4415" data-end="4524">
<tr data-start="4415" data-end="4524">
<th data-start="4415" data-end="4429" data-col-size="sm">Tool</th>
<th data-start="4429" data-end="4468" data-col-size="sm">Best For</th>
<th data-start="4468" data-end="4482" data-col-size="sm">Persistent?</th>
<th data-start="4482" data-end="4493" data-col-size="sm">Eviction</th>
<th data-start="4493" data-end="4524" data-col-size="sm">Supports Complex Structures</th>
</tr>
</thead>
<tbody data-start="4635" data-end="5196">
<tr data-start="4635" data-end="4745">
<td data-start="4635" data-end="4649" data-col-size="sm">CDN</td>
<td data-col-size="sm" data-start="4649" data-end="4689">Static files, global distribution</td>
<td data-col-size="sm" data-start="4689" data-end="4703">No</td>
<td data-col-size="sm" data-start="4703" data-end="4714">TTL</td>
<td data-col-size="sm" data-start="4714" data-end="4745">No</td>
</tr>
<tr data-start="4746" data-end="4855">
<td data-start="4746" data-end="4760" data-col-size="sm">Cloudflare</td>
<td data-start="4760" data-end="4800" data-col-size="sm">Edge caching + security + APIs</td>
<td data-col-size="sm" data-start="4800" data-end="4814">No</td>
<td data-col-size="sm" data-start="4814" data-end="4825">TTL</td>
<td data-col-size="sm" data-start="4825" data-end="4855">No (but Workers add logic)</td>
</tr>
<tr data-start="4856" data-end="4969">
<td data-start="4856" data-end="4872" data-col-size="sm">Reverse Proxy</td>
<td data-col-size="sm" data-start="4872" data-end="4911">Full-page or route caching</td>
<td data-col-size="sm" data-start="4911" data-end="4925">Optional</td>
<td data-col-size="sm" data-start="4925" data-end="4938">TTL/manual</td>
<td data-col-size="sm" data-start="4938" data-end="4969">No</td>
</tr>
<tr data-start="4970" data-end="5085">
<td data-start="4970" data-end="4984" data-col-size="sm">Redis</td>
<td data-col-size="sm" data-start="4984" data-end="5024">Fast app-level caching, sessions</td>
<td data-col-size="sm" data-start="5024" data-end="5038">Optional</td>
<td data-col-size="sm" data-start="5038" data-end="5055">LRU/TTL/custom</td>
<td data-col-size="sm" data-start="5055" data-end="5085">Yes</td>
</tr>
<tr data-start="5086" data-end="5196">
<td data-start="5086" data-end="5100" data-col-size="sm">Memcached</td>
<td data-col-size="sm" data-start="5100" data-end="5140">Lightweight key-value caching</td>
<td data-col-size="sm" data-start="5140" data-end="5154">No</td>
<td data-col-size="sm" data-start="5154" data-end="5165">LRU/TTL</td>
<td data-col-size="sm" data-start="5165" data-end="5196">No</td>
</tr>
</tbody>
</table>
<div class="sticky end-(--thread-content-margin) h-0 self-end select-none">
<div class="absolute end-0 flex items-end"></div>
</div>
</div>
</div>
<p class="" data-start="5198" data-end="5396">Each caching layer serves a distinct purpose. In modern systems, they are often <strong data-start="5278" data-end="5295">used together</strong>, layered strategically to maximize speed, reduce backend load, and ensure acceptable data freshness.</p>
<h3><b>Asynchronous Processing</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Message Queues</span></td>
<td><span style="font-weight: 400;">Kafka, RabbitMQ, SQS, Pub/Sub</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Queue Patterns</span></td>
<td><span style="font-weight: 400;">Fan-out, fan-in, publish-subscribe, dead-letter queues</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Async Processing</span></td>
<td><span style="font-weight: 400;">Worker pools, retry queues, exponential backoff</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Scheduled Jobs</span></td>
<td><span style="font-weight: 400;">Cron jobs, delay queues, distributed schedulers (Quartz, Celery)</span></td>
</tr>
</tbody>
</table>
<h3><b>Load Balancing &amp; Scalability</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Load Balancers</span></td>
<td><span style="font-weight: 400;">Layer 4 (TCP), Layer 7 (HTTP), HAProxy, NGINX, AWS ALB/ELB</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Load Balancing Algorithms</span></td>
<td><span style="font-weight: 400;">Round-robin, least connections, weighted routing</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Sticky Sessions</span></td>
<td><span style="font-weight: 400;">Session affinity, IP hash</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Autoscaling</span></td>
<td><span style="font-weight: 400;">CPU/memory-based, scheduled scaling, predictive scaling</span></td>
</tr>
</tbody>
</table>
<h3><b>Rate Limiting &amp; Throttling</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Algorithms</span></td>
<td><span style="font-weight: 400;">Token bucket, leaky bucket, fixed window, sliding window</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Implementation</span></td>
<td><span style="font-weight: 400;">Redis-based rate limiter, API gateway-level throttling</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Scope</span></td>
<td><span style="font-weight: 400;">Per-user, per-IP, per-endpoint</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Abuse Prevention</span></td>
<td><span style="font-weight: 400;">Blacklisting, rate-based blocking, CAPTCHA triggers</span></td>
</tr>
</tbody>
</table>
<h3><b>Fault Tolerance &amp; Reliability</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Retry Mechanisms</span></td>
<td><span style="font-weight: 400;">Retry queues, exponential backoff, jitter</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Circuit Breakers</span></td>
<td><span style="font-weight: 400;">Open/half-open/closed states, fallback handling</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Graceful Degradation</span></td>
<td><span style="font-weight: 400;">Fallback UIs, feature toggles, read-only mode</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Redundancy</span></td>
<td><span style="font-weight: 400;">Multi-region, active-active vs active-passive deployments</span></td>
</tr>
</tbody>
</table>
<h3><b>Observability</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Monitoring</span></td>
<td><span style="font-weight: 400;">Prometheus, Grafana, DataDog</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Logging</span></td>
<td><span style="font-weight: 400;">Structured logs, ELK stack (Elasticsearch, Logstash, Kibana)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Tracing</span></td>
<td><span style="font-weight: 400;">OpenTelemetry, Jaeger, Zipkin</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Health Checks</span></td>
<td><span style="font-weight: 400;">Liveness and readiness probes, alerting systems</span></td>
</tr>
</tbody>
</table>
<h3><b>Infrastructure &amp; Deployment</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Containerization</span></td>
<td><span style="font-weight: 400;">Docker, container lifecycle, image optimization</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Orchestration</span></td>
<td><span style="font-weight: 400;">Kubernetes basics (pods, deployments, services, autoscalers)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">CI/CD</span></td>
<td><span style="font-weight: 400;">GitHub Actions, Jenkins, ArgoCD, blue-green &amp; canary deployments</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Environment Config</span></td>
<td><span style="font-weight: 400;">12-factor apps, secrets management, dotenv, Vault</span></td>
</tr>
</tbody>
</table>
<h3><b>Security</b></h3>
<table>
<tbody>
<tr>
<td><b>Topic</b></td>
<td><b>Subtopics</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Transport Security</span></td>
<td><span style="font-weight: 400;">HTTPS, TLS, mutual TLS (mTLS)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Data Security</span></td>
<td><span style="font-weight: 400;">Encryption at rest/in transit, KMS (Key Management Services)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">App Security</span></td>
<td><span style="font-weight: 400;">Input validation, rate limiting, CSRF/XSS/SQL injection protection</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Authentication/Token Handling</span></td>
<td><span style="font-weight: 400;">Secure token storage, rotation, session hijack protection</span></td>
</tr>
</tbody>
</table>
<h3><b>Practice System Design Scenarios</b></h3>
<table>
<tbody>
<tr>
<td><b>Problem Type</b></td>
<td><b>Example Use Case</b></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Real-time system</span></td>
<td><span style="font-weight: 400;">Chat app (WebSockets vs polling)</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Rate limiting</span></td>
<td><span style="font-weight: 400;">Token bucket algorithm in Redis</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">File uploads</span></td>
<td><span style="font-weight: 400;">Presigned URLs, virus scanning pipeline</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Notification system</span></td>
<td><span style="font-weight: 400;">Push/SMS/email delivery with retries</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">AI Inference API</span></td>
<td><span style="font-weight: 400;">Streamed output, compute resource throttling</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">Feed system</span></td>
<td><span style="font-weight: 400;">User feed with fan-out vs fan-in architecture</span></td>
</tr>
<tr>
<td><span style="font-weight: 400;">URL shortener</span></td>
<td><span style="font-weight: 400;">ID generation, redirect routing, analytics</span></td>
</tr>
</tbody>
</table>


---

## 19. SSR vs CSR

- Difficulty: 🟢 Easy
- Subtitle: Uncover the trade-offs between SSR and CSR in web apps.

### Content

<h1>Server Side Rendering vs Client Side Rendering</h1>
<p>Server-side rendering (SSR) and client-side rendering (CSR) are two different approaches to rendering web applications, and they each have their own set of advantages and disadvantages. Below, I&#8217;ll outline the pros and cons of both Server-side rendering and Client-side rendering in the context of React.</p>
<h3>Server-side Rendering (SSR):</h3>
<h4>Pros:</h4>
<ol>
<li>Initial Page Load: SSR sends a fully rendered page to the client, which means that the user can see content sooner because the server generates the HTML on the initial request.</li>
<li>SEO-Friendly: Search engines can easily crawl and index the content because the page is delivered with all the necessary markup. This is particularly important for content-heavy applications.</li>
<li>Performance for Low-Powered Devices: SSR can perform better on low-powered devices or slow network connections because the server sends pre-rendered HTML.</li>
<li>Graceful Degradation: If JavaScript fails on the client-side, SSR provides a fallback mechanism, ensuring that the user still sees content.</li>
</ol>
<h4>Cons:</h4>
<ol>
<li>Server Load: SSR can put a higher load on the server because it&#8217;s responsible for rendering the page for each request.</li>
<li>Complexity: Implementing SSR can be more complex, especially if you have a complex application that relies heavily on client-side interactivity.</li>
<li>Slower Interactivity: While the initial page load may be faster, subsequent interactions may be slower because the client has to make additional requests to the server.</li>
</ol>
<h3>Client-side Rendering (CSR):</h3>
<h4>Pros:</h4>
<ol>
<li>Faster Interactivity: Once the initial JavaScript bundle is loaded, subsequent interactions can be very fast because the client can update the DOM without needing to go back to the server.</li>
<li>Reduced Server Load: The server is primarily responsible for sending the initial JavaScript bundle and data. After that, the client handles rendering.</li>
<li>Rich Client Interactions: CSR is great for applications that rely heavily on client-side interactions, as it provides a more dynamic and interactive experience.</li>
</ol>
<h4>Cons:</h4>
<ol>
<li>Slower Initial Page Load: The initial load time can be slower because the client needs to fetch the JavaScript bundle and then render the page on the client-side.</li>
<li>SEO Challenges: Search engines may have a harder time crawling and indexing content because the initial HTML is often minimal and the actual content is populated by JavaScript.</li>
<li>Limited Performance on Low-Powered Devices: CSR can be less performant on low-powered devices or slow network connections, as they have to do more work on the client-side.</li>
<li>Potential for Flicker: In some cases, there can be a noticeable flicker or delay as the client-side JavaScript renders the page.</li>
</ol>
<h3>Summary:</h3>
<p>Choosing between SSR and CSR depends on the specific requirements of your application. If you have a content-heavy site that requires good SEO, SSR might be the better choice. However, for highly interactive applications where speed of interaction is crucial, CSR may be more suitable. In many cases, a hybrid approach (like Next.js with its ability to do both SSR and CSR) can provide the best of both worlds.</p>


---

## 20. Security

- Difficulty: 🟢 Easy
- Subtitle: Elevate web app security with essential frontend security best practices.

### Content

<h1>Frontend security &#8211; Frontend System Design Guide</h1>
<p>Frontend security is crucial for protecting web applications from various types of attacks and vulnerabilities. Here are some of the main frontend security features and practices to consider:</p>
<h3><strong>Cross-Site Scripting (XSS) Protection:</strong></h3>
<ul>
<li class="ql-indent-1">Content Security Policy (CSP): Implement CSP headers to restrict the sources from which resources can be loaded, preventing XSS attacks by disallowing the execution of malicious scripts.</li>
<li class="ql-indent-1">Input Validation and Sanitization: Validate and sanitize user inputs to ensure they do not contain malicious scripts.</li>
<li class="ql-indent-1">Escape Characters: Encode special characters in user-generated content to prevent them from being interpreted as executable code.</li>
</ul>
<h3><strong>Cross-Site Request Forgery (CSRF) Protection:</strong></h3>
<ul>
<li class="ql-indent-1">CSRF Tokens: Implement anti-CSRF tokens to ensure that requests originate from legitimate and authenticated users.</li>
<li class="ql-indent-1">Same-Site Cookies: Use the <code>SameSite</code> attribute to prevent cookies from being sent in cross-origin requests, which can help mitigate CSRF attacks.</li>
</ul>
<h3><strong>Clickjacking Protection:</strong></h3>
<ul>
<li class="ql-indent-1">X-Frame-Options Header: Set the X-Frame-Options header to deny or allow specific domains to embed your site in an iframe, preventing clickjacking attacks.</li>
</ul>
<h3><strong>Secure Communications:</strong></h3>
<ul>
<li class="ql-indent-1">HTTPS: Ensure that your site uses HTTPS to encrypt data in transit and protect against eavesdropping and man-in-the-middle attacks.</li>
</ul>
<h3><strong>Input Validation and Sanitization:</strong></h3>
<ul>
<li class="ql-indent-1">Client-Side Validation: Implement validation on the client-side to catch and reject invalid or malicious input before it&#8217;s sent to the server.</li>
<li class="ql-indent-1">Server-Side Validation: Always validate input on the server-side as well, as client-side validation can be bypassed.</li>
</ul>
<h3><strong>Authentication and Authorization:</strong></h3>
<ul>
<li class="ql-indent-1">Strong Password Policies: Enforce strong password requirements to protect user accounts.</li>
<li class="ql-indent-1">Multi-Factor Authentication (MFA): Implement MFA to add an extra layer of security for user authentication.</li>
<li class="ql-indent-1">Role-Based Access Control (RBAC): Use RBAC to ensure that users only have access to the resources and functionalities they are authorized to use.</li>
</ul>
<h3><strong>Session Management:</strong></h3>
<ul>
<li class="ql-indent-1">Session Timeout: Set session timeouts to automatically log out inactive users and prevent session hijacking.</li>
<li class="ql-indent-1">Session Tokens: Use secure, random session tokens and regenerate them after a successful login.</li>
</ul>
<h3><strong>Content Security:</strong></h3>
<ul>
<li class="ql-indent-1">Content-Type Headers: Properly set Content-Type headers to prevent browsers from interpreting content in unexpected ways.</li>
<li class="ql-indent-1">File Upload Security: If your application allows file uploads, validate file types and implement proper security measures to prevent malicious uploads.</li>
</ul>
<h3><strong>Error Handling:</strong></h3>
<ul>
<li class="ql-indent-1">Custom Error Messages: Avoid revealing sensitive information in error messages. Provide generic error messages to users and log detailed error information for developers.</li>
<li class="ql-indent-1">404 Handling: Customize error pages to avoid leaking information about the underlying technology stack.</li>
</ul>
<h3><strong>Dependency Scanning:</strong></h3>
<ul>
<li class="ql-indent-1">Regularly Update Dependencies: Keep frontend libraries and frameworks up-to-date to patch security vulnerabilities.</li>
<li class="ql-indent-1">Dependency Scanning Tools: Use tools that scan your project&#8217;s dependencies for known vulnerabilities.</li>
</ul>
<h3><strong>Content Security Policies (CSP):</strong></h3>
<ul>
<li class="ql-indent-1">Strict Mode: Consider implementing CSP in strict mode to limit which resources can be loaded by your application.</li>
</ul>
<p>Remember that security is an ongoing process. Regularly updating and patching your frontend code, staying informed about emerging threats, and conducting security audits are essential practices to maintain a secure frontend.</p>


---

## 21. XSS vs CORS

- Difficulty: 🟢 Easy
- Subtitle: Explore XSS attacks and CORS policies for secure web applications.

### Content

<h1>XSS (Cross-Site Scripting) and CORS (Cross-Origin Resource Sharing)</h1>
<p>Both are security mechanisms, but they address different types of security concerns in web applications.</p>
<h3>XSS (Cross-Site Scripting):</h3>
<p>XSS is a vulnerability that occurs when an attacker injects malicious scripts into a web page viewed by other users. These scripts can then be executed in the context of the victim&#8217;s browser, potentially leading to the theft of sensitive information or the manipulation of web content.</p>
<h4>Types of XSS:</h4>
<ol>
<li>Stored XSS: The malicious script is permanently stored on a website&#8217;s server and served to users when they visit a particular page.</li>
<li>Reflected XSS: The malicious script is embedded in a URL and executed when the victim clicks on a malicious link.</li>
<li>DOM-based XSS: The vulnerability arises within the Document Object Model (DOM) of a web page, often as a result of manipulating JavaScript code that interacts with the DOM.</li>
</ol>
<h4>Prevention of XSS:</h4>
<ol>
<li>Input Validation and Sanitization: Validate and sanitize user inputs to ensure they do not contain malicious scripts.</li>
<li>Content Security Policy (CSP): Implement CSP headers to restrict the sources from which resources can be loaded, preventing the execution of malicious scripts.</li>
<li>Escape Characters: Encode special characters in user-generated content to prevent them from being interpreted as executable code.</li>
</ol>
<h3>CORS (Cross-Origin Resource Sharing):</h3>
<p>CORS is a security feature implemented by web browsers that controls which resources (e.g., fonts, scripts, or images) a web page can request from another domain. It&#8217;s designed to prevent a web page from making requests to a different domain without explicit permission.</p>
<h4>Key Aspects of CORS:</h4>
<ol>
<li>Same-Origin Policy (SOP): By default, web browsers follow the same-origin policy, which means that a web page can only request resources from the same domain, port, and protocol.</li>
<li>Cross-Origin Requests: When a web page attempts to make a request to a different domain (cross-origin), the browser enforces CORS policies to determine whether the request is allowed.</li>
</ol>
<h4>CORS Headers:</h4>
<ul>
<li>Access-Control-Allow-Origin: Specifies which domains are allowed to access a resource.</li>
<li>Access-Control-Allow-Methods: Specifies which HTTP methods are allowed when making a request.</li>
<li>Access-Control-Allow-Headers: Specifies which headers can be included in the request.</li>
</ul>
<h4>CORS Pre-flight Requests:</h4>
<p>For certain types of requests (e.g., those with custom headers or using certain methods like <code>PUT</code> or <code>DELETE</code>), the browser sends a pre-flight request (an HTTP <code>OPTIONS</code> request) to the server to check if the actual request is permitted.</p>
<h4>CORS vs XSS:</h4>
<ul>
<li>XSS is a vulnerability that attackers exploit to inject malicious scripts into web pages, potentially compromising user data or executing unwanted actions.</li>
<li>CORS is a security feature implemented by web browsers to control which resources a web page can request from a different domain, preventing unauthorized cross-origin requests.</li>
</ul>
<p>In summary, XSS is an attack vector, while CORS is a security feature that helps prevent unauthorized cross-origin requests. Both are important considerations for building secure web applications.</p>
<h2>Preventing XSS (Cross-Site Scripting)</h2>
<p>Preventing XSS (Cross-Site Scripting) involves implementing various security measures to ensure that user inputs are properly sanitized and that malicious scripts cannot be executed on a web page. Here are some key strategies with examples:</p>
<h3><strong>Input Validation and Sanitization:</strong></h3>
<p>Validate and sanitize user inputs to ensure they do not contain malicious scripts. This can be done both on the client side and server side.</p>
<p>Example (Client-side Validation):</p>
<pre class="ql-syntax" spellcheck="false">// Client-side validation using regular expressions 
function validateInput(input) { const regex = /^[a-zA-Z0-9\s]+$/; // Allow letters, numbers, and spaces return regex.test(input); } const userInput = document.getElementById('user-input').value; if (!validateInput(userInput)) { alert('Invalid input. Please enter alphanumeric characters only.'); } 
</pre>
<p>Example (Server-side Validation in Node.js):</p>
<pre class="ql-syntax" spellcheck="false">// Server-side validation using Express.js 
app.post('/submitForm', (req, res) =&gt; { const userInput = req.body.userInput; const regex = /^[a-zA-Z0-9\s]+$/; if (!regex.test(userInput)) { return res.status(400).send('Invalid input. Please enter alphanumeric characters only.'); } // Process the valid input // ... }); 
</pre>
<h3><strong>Content Security Policy (CSP):</strong></h3>
<p>Implement CSP headers to restrict the sources from which resources can be loaded, preventing the execution of malicious scripts.</p>
<p>Example (Setting CSP Headers in HTTP Response):</p>
<pre class="ql-syntax" spellcheck="false">j// Express.js middleware to set CSP header 
app.use((req, res, next) =&gt; { res.setHeader('Content-Security-Policy', "default-src 'self'; script-src 'self' cdn.example.com"); next(); }); 
</pre>
<h3><strong>Escape Characters:</strong></h3>
<p>Encode special characters in user-generated content to prevent them from being interpreted as executable code.</p>
<p>Example (Using a Library like DOMPurify):</p>
<pre class="ql-syntax" spellcheck="false">const userInput = '&lt;img src="x" onerror="alert(\'XSS Attack!\')"&gt;'; 
const sanitizedHTML = DOMPurify.sanitize(userInput); // Render the sanitized HTML in the document document.getElementById('output').innerHTML = sanitizedHTML; 
</pre>
<h3><strong>Use Frameworks with Built-in XSS Protection:</strong></h3>
<p>Some modern web frameworks (e.g., React, Angular) have built-in features that help prevent XSS attacks. For instance, React uses JSX to escape potentially dangerous content by default.</p>
<p>Example (React JSX):</p>
<pre class="ql-syntax" spellcheck="false">const userInput = '&lt;img src="x" onerror="alert(\'XSS Attack!\')"&gt;'; const output = &lt;div&gt;{userInput}&lt;/div&gt;; // User input is escaped by JSX 
</pre>
<h3><strong>Avoid Using </strong><code><strong>eval()</strong></code><strong>:</strong></h3>
<p>Avoid using <code>eval()</code> to execute arbitrary code, as it can potentially execute malicious scripts.</p>
<p>Example (Avoiding <code>eval()</code>):</p>
<pre class="ql-syntax" spellcheck="false">const userInput = 'alert(\'XSS Attack!\')'; // Bad practice - Avoid using eval() eval(userInput); 
</pre>
<h3><strong>Secure Headers:</strong></h3>
<p>Set HTTP headers to enhance security. For example, using the <code>X-Content-Type-Options</code> header to prevent MIME-sniffing.</p>
<p>Example (Setting HTTP Headers):</p>
<pre class="ql-syntax" spellcheck="false">// Express.js middleware to set secure headers 
app.use((req, res, next) =&gt; { res.setHeader('X-Content-Type-Options', 'nosniff'); next(); }); 
</pre>
<p>These are just some examples of how to prevent XSS attacks. It&#8217;s important to incorporate a combination of these strategies based on your application&#8217;s requirements and technology stack. Additionally, keeping up with best practices and security updates in the web development community is crucial for maintaining a secure application.</p>


---

## 22. Image Caching Strategies

- Difficulty: 🟢 Easy
- Subtitle: Master image caching for improved web speed and user satisfaction.

### Content

<p>Caching strategies for loading images on the web are essential for optimizing website performance and user experience. Here are some common caching strategies:</p>
<h3>1. <strong>Browser Caching:</strong></h3>
<ul>
<li>Leverage the browser&#8217;s built-in caching mechanism. When a user visits a website, the browser stores images in its cache. On subsequent visits, if the image hasn&#8217;t changed, the browser can load it from the cache instead of making a new request to the server.</li>
<li>Set appropriate HTTP caching headers (<code>Cache-Control</code>, <code>Expires</code>, <code>ETag</code>, <code>Last-Modified</code>) to control how long the browser should cache the images. This can be configured on the server.</li>
</ul>
<h3>2. <strong>Content Delivery Networks (CDNs):</strong></h3>
<ul>
<li>Use a Content Delivery Network to distribute images to servers located closer to users. CDNs cache images across multiple edge servers worldwide, reducing the distance and time it takes for images to reach users.</li>
</ul>
<h3>3. <strong>Lazy Loading:</strong></h3>
<ul>
<li>Lazy loading delays the loading of offscreen images until the user scrolls down to them. This can significantly improve initial page load times. There are native browser features like <code>loading="lazy"</code> or JavaScript libraries (e.g., <code>Intersection Observer</code>) that enable lazy loading.</li>
</ul>
<h3>4. <strong>Responsive Images:</strong></h3>
<ul>
<li>Provide multiple image sizes and resolutions (using <code>srcset</code> and <code>sizes</code> attributes) to serve the most appropriate image based on the user&#8217;s device and screen size. This helps in delivering smaller images to smaller screens.</li>
</ul>
<h3>5. <strong>Image Sprites:</strong></h3>
<ul>
<li>Combine multiple small images into a single larger image (sprite). This reduces the number of HTTP requests required to load multiple images.</li>
</ul>
<h3>6. <strong>Data URIs:</strong></h3>
<ul>
<li>Convert small images into data URIs and embed them directly into the HTML or CSS. This can reduce the number of HTTP requests. However, it&#8217;s suitable only for very small images due to increased HTML/CSS file size.</li>
</ul>
<h3>7. <strong>HTTP/2 or HTTP/3:</strong></h3>
<ul>
<li>If your server and client support HTTP/2 or HTTP/3, take advantage of multiplexing, which allows multiple resources (including images) to be requested over a single connection, reducing latency.</li>
</ul>
<h3>8. <strong>Image Format Optimization:</strong></h3>
<ul>
<li>Choose appropriate image formats (e.g., JPEG, PNG, WebP) based on the type of image and its use case. Use image compression tools to reduce file sizes without compromising quality.</li>
</ul>
<h3>9. <strong>Cache-Control Headers:</strong></h3>
<ul>
<li>Set Cache-Control headers on the server to specify caching policies for images. For example, you can set a long cache duration for static images that don&#8217;t change frequently.</li>
</ul>
<h3>10. <strong>Versioning or Hashing:</strong></h3>
<ul>
<li>Append a version number or hash to the image URL. When the image changes, the URL changes, ensuring the browser requests the updated version.</li>
</ul>
<h3>11. <strong>Service Workers:</strong></h3>
<ul>
<li>Use service workers to implement more advanced caching strategies, like offline caching or dynamic caching based on user behavior.</li>
</ul>
<h3>12. <strong>CDN Edge Caching:</strong></h3>
<ul>
<li>CDNs often provide edge caching, which caches images at the edge servers. This can further reduce the load on your origin server.</li>
</ul>
<p>Remember to analyze the specific needs of your application and user base to determine which combination of caching strategies will be most effective. Additionally, regularly monitor and measure the impact of your caching strategies to ensure they continue to provide optimal performance.</p>


---

## 23. Broadcast Channels

- Difficulty: 🟢 Easy
- Subtitle: BroadcastChannel: Streamline communication between your web app's tabs and windows.

### Content

<h1>Broadcast Channels Explained</h1>
<p><code>BroadcastChannel</code> is a Web API that provides a simple way for different windows or tabs from the same origin to communicate with each other. It allows you to send messages between different browsing contexts, such as different tabs or windows of the same browser.</p>
<p>Here&#8217;s how it works:</p>
<ol>
<li>Creation of a Channel:</li>
</ol>
<ul>
<li class="ql-indent-1">You create a <code>BroadcastChannel</code> object by specifying a channel name. This name acts as an identifier for the communication channel.</li>
</ul>
<ol>
<li>Sending Messages:</li>
</ol>
<ul>
<li class="ql-indent-1">You can send messages using the <code>postMessage()</code> method of the <code>BroadcastChannel</code> object. This allows you to send data to all connected channels.</li>
</ul>
<ol>
<li>Receiving Messages:</li>
</ol>
<ul>
<li class="ql-indent-1">Each channel that has the same name can listen for messages using the <code>onmessage</code> event handler.</li>
</ul>
<h3>Example Usage:</h3>
<p>Let&#8217;s say you have two tabs open in your browser, and you want to enable communication between them using a <code>BroadcastChannel</code>.</p>
<p>Tab 1 (Sender):</p>
<pre class="ql-syntax" spellcheck="false">const channel = new BroadcastChannel('myChannel'); document.querySelector('button').addEventListener('click', () =&gt; { const message = document.querySelector('input').value; channel.postMessage(message); }); 
</pre>
<p>In this example, we create a new <code>BroadcastChannel</code> named &#8216;myChannel&#8217;. When the button is clicked, it sends the value of an input field as a message through the channel.</p>
<p>Tab 2 (Receiver):</p>
<pre class="ql-syntax" spellcheck="false">const channel = new BroadcastChannel('myChannel'); channel.onmessage = function(event) { const message = event.data; console.log('Received message:', message); }; 
</pre>
<p>In this example, we create a <code>BroadcastChannel</code> with the same name (&#8216;myChannel&#8217;). We then listen for messages using the <code>onmessage</code> event handler. When a message is received, we extract the data from the event and log it to the console.</p>
<p>How it Works:</p>
<ol>
<li>When Tab 1 sends a message using <code>channel.postMessage(message)</code>, Tab 2 receives it through <code>channel.onmessage</code>.</li>
<li>Both tabs use the same channel name (&#8216;myChannel&#8217;) to establish a connection.</li>
<li>Any message sent through the channel is received by all listening channels with the same name.</li>
</ol>
<p>Important Considerations:</p>
<ul>
<li>The communicating tabs need to be from the same origin (i.e., same protocol, domain, and port) due to same-origin policy restrictions.</li>
<li>Messages sent through a <code>BroadcastChannel</code> are serialized, so they should be JSON-serializable data.</li>
<li>Channels persist as long as at least one script holds a reference to them. When all references are released, the channel is closed.</li>
</ul>
<p><code>BroadcastChannel</code> is useful for scenarios where you need real-time communication between different browsing contexts within your web application, such as multiplayer games, collaborative tools, or any situation where you want to sync data across multiple windows or tabs.</p>


---

## 24. IndexedDB

- Difficulty: 🟢 Easy
- Subtitle: Harness IndexedDB for robust data storage and offline web apps.

### Content

<h1>Unlocking the Power of IndexedDB: A Guide to Client-Side Storage</h1>
<p>IndexedDB is a low-level, client-side storage API provided by modern web browsers. It allows web applications to store significant amounts of structured data in a user&#8217;s browser and retrieve it later, even when the user is offline.</p>
<p>Here are some key characteristics and features of IndexedDB:</p>
<h3>1. <strong>Structured Data Storage:</strong></h3>
<ul>
<li>IndexedDB is an object-oriented database. It allows you to store data in structured records using key-value pairs, similar to tables in a traditional relational database.</li>
</ul>
<h3>2. <strong>Asynchronous API:</strong></h3>
<ul>
<li>IndexedDB operations are asynchronous, meaning that you initiate an operation and provide a callback function that will be called when the operation completes.</li>
</ul>
<h3>3. <strong>High Storage Capacity:</strong></h3>
<ul>
<li>IndexedDB can handle large amounts of data, often more than traditional client-side storage options like cookies or localStorage.</li>
</ul>
<h3>4. <strong>No Same-Origin Policy Restrictions:</strong></h3>
<ul>
<li>Unlike many other web APIs, IndexedDB does not enforce the same-origin policy, meaning that you can access data stored in IndexedDB from multiple origins (domains).</li>
</ul>
<h3>5. <strong>Transaction-Based:</strong></h3>
<ul>
<li>All interactions with an IndexedDB are done within transactions. A transaction is a way of grouping operations together to ensure atomicity and consistency.</li>
</ul>
<h3>6. <strong>Supports Indexing:</strong></h3>
<ul>
<li>You can create indexes on properties of objects in an IndexedDB database, which allows for efficient querying and retrieval of data.</li>
</ul>
<h3>7. <strong>Offline Access:</strong></h3>
<ul>
<li>IndexedDB is particularly useful for building offline web applications. It allows you to cache data on the client-side so that users can still interact with the app even without an internet connection.</li>
</ul>
<h3>8. <strong>Security and Privacy:</strong></h3>
<ul>
<li>Data stored in IndexedDB is specific to the origin (protocol, domain, and port) of the web page. This helps maintain privacy and security.</li>
</ul>
<h3>9. <strong>Browser Support:</strong></h3>
<ul>
<li>IndexedDB is supported by most modern browsers, including Chrome, Firefox, Edge, Safari, and others.</li>
</ul>
<h3>Use Cases:</h3>
<p>IndexedDB is well-suited for scenarios where you need to:</p>
<ul>
<li>Store large amounts of structured data on the client-side.</li>
<li>Build offline-capable web applications.</li>
<li>Cache resources for improved performance.</li>
<li>Implement more complex client-side data management.</li>
</ul>
<h3>Limitations:</h3>
<ul>
<li>IndexedDB has a steeper learning curve compared to simpler storage mechanisms like localStorage.</li>
<li>It requires careful management of asynchronous operations and transactions.</li>
<li>Older browsers or browsers with limited support may not fully support IndexedDB.</li>
</ul>
<p>Overall, IndexedDB is a powerful tool for client-side data storage and retrieval, providing web developers with the means to build sophisticated web applications that can function effectively both online and offline.</p>


---

## 25. Core Web Vitals

- Difficulty: 🟢 Easy
- Subtitle: Mastering Core Web Vitals for Superior Web Performance and SEO

### Content

<h1>Optimizing for Excellence: A Deep Dive into Core Web Vitals</h1>
<p>Core Web Vitals are a set of user-centered performance metrics introduced by Google to help web developers and site owners measure and improve the user experience on their websites. They focus on aspects of web performance that directly impact user perception and satisfaction. As of my last training data in September 2021, there are three core web vitals:</p>
<h3>1. <strong>Largest Contentful Paint (LCP):</strong></h3>
<ul>
<li>Definition: LCP measures the perceived loading performance of a web page. It specifically looks at the time it takes for the largest visible element (usually an image, video, or block-level element) to fully render on the page.</li>
<li>Ideal Benchmark: To provide a good user experience, LCP should occur within the first 2.5 seconds of the page starting to load.</li>
<li>Improvement Tips:</li>
<li class="ql-indent-1">Optimize and prioritize the loading of large elements like images and videos.</li>
<li class="ql-indent-1">Use efficient image formats.</li>
<li class="ql-indent-1">Minimize render-blocking resources.</li>
</ul>
<h3>2. <strong>First Input Delay (FID):</strong></h3>
<ul>
<li>Definition: FID measures the responsiveness of a web page. It gauges the time between a user&#8217;s first interaction (like clicking a button or link) and the browser&#8217;s response to that interaction.</li>
<li>Ideal Benchmark: To provide a good user experience, FID should be less than 100 milliseconds.</li>
<li>Improvement Tips:</li>
<li class="ql-indent-1">Minimize JavaScript execution time.</li>
<li class="ql-indent-1">Avoid long tasks that might block the main thread.</li>
<li class="ql-indent-1">Optimize third-party scripts and resources.</li>
</ul>
<h3>3. <strong>Cumulative Layout Shift (CLS):</strong></h3>
<ul>
<li>Definition: CLS measures the visual stability of a web page. It quantifies how much the content of a page shifts around during loading. This can be caused by elements loading asynchronously or dynamically, potentially leading to a frustrating user experience.</li>
<li>Ideal Benchmark: To provide a good user experience, CLS should have a score of less than 0.1.</li>
<li>Improvement Tips:</li>
<li class="ql-indent-1">Provide dimensions for media elements like images and videos to prevent layout shifts.</li>
<li class="ql-indent-1">Avoid inserting new content above existing content unless in direct response to a user action.</li>
</ul>
<h3>How to Measure Core Web Vitals:</h3>
<p>You can measure Core Web Vitals using various tools provided by Google:</p>
<ol>
<li>Google PageSpeed Insights: This tool provides a score for both mobile and desktop experiences, along with detailed suggestions for improvement.</li>
<li>Google Search Console: It offers reports on how your site&#8217;s pages are performing in terms of Core Web Vitals.</li>
<li>Chrome DevTools: You can use the Lighthouse panel in DevTools to run audits on any web page.</li>
</ol>
<h3>Importance of Core Web Vitals:</h3>
<ul>
<li>SEO Ranking Factor: Google considers Core Web Vitals as a factor in its search ranking algorithm. Sites that provide a better user experience are more likely to rank higher in search results.</li>
<li>User Experience: Good Core Web Vitals scores lead to faster, more responsive, and more visually stable web pages, resulting in improved user satisfaction.</li>
<li>Reduced Bounce Rates: Users are less likely to leave a page if it loads quickly and responds promptly to their interactions.</li>
</ul>
<p>Remember that the web landscape is always evolving, and it&#8217;s important to stay updated with the latest recommendations and guidelines from Google to ensure your website provides the best user experience possible.</p>


---

## 26. Web Accessibility

- Difficulty: 🟢 Easy
- Subtitle: Make your website universally accessible with key web accessibility practices.

### Content

<h1>Web Accessibility Best Practices</h1>
<p>Accessibility in web development ensures that websites are usable by people with various disabilities. This encompasses a broad range of practices, from keyboard navigation and semantic HTML to ARIA roles and responsive design. The goal is to make the web inclusive for everyone, regardless of their physical or cognitive abilities.</p>
<h2>Semantic HTML and ARIA</h2>
<p>Utilizing semantic HTML elements such as <code>&lt;nav&gt;</code>, <code>&lt;main&gt;</code>, and <code>&lt;article&gt;</code> clarifies the structure and meaning of content, making it easier for assistive technologies to interpret. ARIA roles and attributes further enhance the accessibility of dynamic content and custom UI components.</p>
<table>
<caption>Key Semantic Elements and Their Purposes</caption>
<thead>
<tr>
<th>Element</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td>&lt;nav&gt;</td>
<td>Navigation links</td>
</tr>
<tr>
<td>&lt;main&gt;</td>
<td>Main content of a document</td>
</tr>
<tr>
<td>&lt;article&gt;</td>
<td>A self-contained composition</td>
</tr>
</tbody>
</table>
<h2>Enhancing Accessibility with Alt Text and Keyboard Navigation</h2>
<p>Providing descriptive alt text for images ensures that users who cannot see them still understand their content. Equally important is enabling keyboard navigation for all interactive elements, allowing users without mouse capabilities to fully interact with the site.</p>
<h2>Ensuring Visibility with Focus Styles and Skip Links</h2>
<p>Clear focus styles and &#8220;skip to content&#8221; links significantly improve the experience for keyboard users, making navigation more intuitive and less cumbersome.</p>
<h2>Form Accessibility and Error Handling</h2>
<p>Proper labeling of form elements, along with clear and descriptive error messages, ensures that forms are accessible and user-friendly.</p>
<h2>Color Contrast and Media Accessibility</h2>
<p>Maintaining high contrast between text and backgrounds enhances readability, while providing captions and transcripts for media ensures inclusivity for users with hearing impairments.</p>
<h2>Responsive Design and Testing</h2>
<p>A responsive design adapts to various devices and screen sizes, ensuring accessibility across all platforms. Regular testing with screen readers and accessibility tools is crucial to identify and address potential barriers.</p>
<table>
<caption>Tools for Accessibility Testing</caption>
<thead>
<tr>
<th>Tool</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Screen Readers</td>
<td>Software that reads out webpage content for visually impaired users</td>
</tr>
<tr>
<td>Browser Extensions</td>
<td>Extensions that highlight accessibility issues on web pages</td>
</tr>
</tbody>
</table>


---

## 27. ARIA roles

- Difficulty: 🟢 Easy
- Subtitle: Use ARIA roles and attributes to make websites more accessible.

### Content

<article>
<h1>Empowering Web Accessibility with ARIA: Roles and Attributes Explained</h1>
<p>ARIA roles are used to provide additional information to assistive technologies (such as screen readers) about the purpose and behavior of elements on a web page. This helps users with disabilities, particularly those who may not be able to interact with a page using a traditional mouse or visual interface.</p>
<h3>role=&#8221;button&#8221;</h3>
<ul>
<li>Purpose: Indicates that an element functions as a button.</li>
<li>Accessibility Benefit: Screen readers will announce the element as a button, allowing users to understand that it&#8217;s interactive and can be activated.</li>
</ul>
<h3>role=&#8221;link&#8221;:</h3>
<ul>
<li>Purpose: Indicates that an element functions as a hyperlink.</li>
<li>Accessibility Benefit: Screen readers will announce the element as a link, letting users know that it leads to another page or resource.</li>
</ul>
<h3>role=&#8221;heading&#8221;:</h3>
<ul>
<li>Purpose: Specifies the heading level of an element.</li>
<li>Accessibility Benefit: Screen readers use headings to create a hierarchical structure for the content, aiding users in understanding the organization and flow of the page.</li>
</ul>
<h3>role=&#8221;navigation&#8221;:</h3>
<ul>
<li>Purpose: Denotes a navigation region within a page.</li>
<li>Accessibility Benefit: Screen readers can identify navigation sections, helping users quickly locate menus or links to different parts of the website.</li>
</ul>
<h3>role=&#8221;checkbox&#8221;:</h3>
<ul>
<li>Purpose: Represents a checkbox input.</li>
<li>Accessibility Benefit: Screen readers will recognize the element as a checkbox, allowing users to interact with it and understand its state (checked or unchecked).</li>
</ul>
<h3>role=&#8221;menu&#8221; and role=&#8221;menuitem&#8221;:</h3>
<ul>
<li>Purpose: Defines a menu and its individual items.</li>
<li>Accessibility Benefit: Screen readers will identify menus and their items, making it easier for users to navigate and select options.</li>
</ul>
<h3>role=&#8221;alert&#8221;:</h3>
<ul>
<li>Purpose: Indicates that an element contains important and time-sensitive information.</li>
<li>Accessibility Benefit: Screen readers will announce alerts, ensuring that users are immediately aware of critical messages or notifications.</li>
</ul>
<h3>How ARIA Attributes Enhance Accessibility:</h3>
<ul>
<li><code>aria-label</code> and <code>aria-labelledby</code>: Provide an accessible name for an element, ensuring that assistive technologies can convey the purpose or label of the element to the user.</li>
<li><code>aria-describedby</code>: Points to additional information that describes the element, giving users more context or instructions.</li>
<li><code>aria-hidden</code>: Determines whether an element should be hidden from assistive technologies, allowing developers to manage what is presented to users with disabilities.</li>
<li><code>aria-disabled</code>: Indicates that an element is not interactive and cannot be activated, ensuring that users understand when an element is not usable.</li>
<li><code>aria-haspopup</code> and <code>aria-expanded</code>: Indicate the presence of a popup menu and its current state (open or closed), providing users with information about interactive elements.</li>
<li><code>aria-live</code>: Specifies that an element will be automatically updated with live information, making dynamic content accessible to users.</li>
<li><code>aria-pressed</code>: Indicates the current state of a toggle button (e.g., pressed or not pressed), helping users understand the current setting.</li>
</ul>
<h3>ARIA Roles:</h3>
<ol>
<li><code>role="button"</code>:
<ul>
<li>Indicates that an element functions as a button.</li>
</ul>
<pre><code>&lt;div role="button" tabindex="0"&gt;Click me&lt;/div&gt;</code></pre>
</li>
<li><code>role="link"</code>:
<ul>
<li>Indicates that an element functions as a hyperlink.</li>
</ul>
<pre><code>&lt;div role="link" tabindex="0"&gt;Visit our homepage&lt;/div&gt;</code></pre>
</li>
<li><code>role="heading"</code>:
<ul>
<li>Specifies the heading level of an element.</li>
</ul>
<pre><code>&lt;div role="heading" aria-level="2"&gt;Subheading&lt;/div&gt;</code></pre>
</li>
<li><code>role="navigation"</code>:
<ul>
<li>Denotes a navigation region within a page.</li>
</ul>
<pre><code>&lt;nav role="navigation"&gt; &lt;ul&gt; &lt;li&gt;&lt;a href="#"&gt;Home&lt;/a&gt;&lt;/li&gt; &lt;li&gt;&lt;a href="#"&gt;About&lt;/a&gt;&lt;/li&gt; &lt;li&gt;&lt;a href="#"&gt;Contact&lt;/a&gt;&lt;/li&gt; &lt;/ul&gt; &lt;/nav&gt;</code></pre>
</li>
<li><code>role="checkbox"</code>:
<ul>
<li>Represents a checkbox input.</li>
</ul>
<pre><code>&lt;div role="checkbox" aria-checked="true" tabindex="0"&gt;Checked&lt;/div&gt;</code></pre>
</li>
<li><code>role="menu"</code> and <code>role="menuitem"</code>:
<ul>
<li>Defines a menu and its individual items.</li>
</ul>
<pre><code>&lt;div role="menu"&gt; &lt;div role="menuitem" tabindex="0"&gt;Option 1&lt;/div&gt; &lt;div role="menuitem" tabindex="0"&gt;Option 2&lt;/div&gt; &lt;/div&gt;</code></pre>
</li>
<li><code>role="alert"</code>:
<ul>
<li>Indicates that an element contains important and time-sensitive information.</li>
</ul>
<pre><code>&lt;div role="alert"&gt;Error: Please enter a valid email address&lt;/div&gt;</code></pre>
</li>
</ol>
<h3>ARIA Attributes:</h3>
<ol>
<li><code>aria-label</code> and <code>aria-labelledby</code>:
<ul>
<li>Provides an accessible name for an element.</li>
</ul>
<pre><code>&lt;button aria-label="Close"&gt;X&lt;/button&gt;
&lt;div id="section-heading"&gt;Section Title&lt;/div&gt;
&lt;section aria-labelledby="section-heading"&gt;
  &lt;!-- Section content --&gt;
&lt;/section&gt;</code></pre>
</li>
<li><code>aria-describedby</code>:
<ul>
<li>Points to additional information that describes the element.</li>
</ul>
<pre><code>&lt;input type="text" aria-describedby="help-text"&gt;
&lt;div id="help-text"&gt;Please enter your username&lt;/div&gt;</code></pre>
</li>
<li><code>aria-hidden</code>:
<ul>
<li>Indicates whether an element should be hidden from assistive technologies.</li>
</ul>
<pre><code>&lt;div aria-hidden="true"&gt;Hidden content&lt;/div&gt;</code></pre>
</li>
<li><code>aria-disabled</code>:
<ul>
<li>Indicates that an element is not interactive and cannot be activated.</li>
</ul>
<pre><code>&lt;button aria-disabled="true"&gt;Disabled Button&lt;/button&gt;</code></pre>
</li>
<li><code>aria-haspopup</code> and <code>aria-expanded</code>:
<ul>
<li>Indicates that an element has a popup menu and whether it is expanded.</li>
</ul>
<pre><code>&lt;button aria-haspopup="true" aria-expanded="false"&gt;Show Menu&lt;/button&gt;</code></pre>
</li>
<li><code>aria-live</code>:
<ul>
<li>Specifies that an element will be automatically updated<br />
with live information.</li>
</ul>
<pre><code>&lt;div aria-live="polite"&gt;New message received&lt;/div&gt;</code></pre>
</li>
<li><code>aria-pressed</code>:
<ul>
<li>Indicates the current state of a toggle button (e.g., pressed or not pressed).</li>
</ul>
<pre><code>&lt;button aria-pressed="false"&gt;Toggle&lt;/button&gt;</code></pre>
</li>
</ol>
<p>These are just a few examples of how ARIA roles and attributes can be used to enhance the accessibility of web content. It&#8217;s important to choose the appropriate roles and attributes based on the functionality and purpose of your elements. Always refer to the ARIA specification and consider testing with assistive technologies to ensure your content is properly accessible.</p>
</article>


---

## 28. Network Requests

- Difficulty: 🟢 Easy
- Subtitle: Choose the right data fetching strategy for optimal web performance.

### Content

<article>
<h1>Navigating Data Fetching Strategies: Network Only, Cache, and Hybrid Approaches</h1>
<p>Choosing the right data fetching strategy is crucial for the performance and user experience of any web application. This article discusses three common strategies: Network Only, Network and Cache, and Cache Only, along with their advantages and disadvantages.</p>
<h2>Network Only</h2>
<h3>Pros:</h3>
<ul>
<li><strong>Fresh Data:</strong> Ensures access to the most up-to-date information directly from the server, ideal for real-time data needs.</li>
</ul>
<h3>Cons:</h3>
<ul>
<li><strong>Latency:</strong> Can result in delays due to slow network connections or high server load.</li>
<li><strong>Potential for Failure:</strong> Relies entirely on network availability; any disruption means no data is received.</li>
</ul>
<h2>Network and Cache</h2>
<h3>Pros:</h3>
<ul>
<li><strong>Balanced Approach:</strong> Offers a compromise between speed (cache) and freshness (network).</li>
<li><strong>Improved Performance:</strong> Immediate response from cache with background updates for fresh data.</li>
</ul>
<h3>Cons:</h3>
<ul>
<li><strong>Potential for Stale Data:</strong> The cache might serve outdated information until the next network update.</li>
<li><strong>Complex Caching Logic:</strong> Requires careful management of cache validity and synchronization.</li>
</ul>
<h2>Cache Only</h2>
<h3>Pros:</h3>
<ul>
<li><strong>Instantaneous Response:</strong> Delivers immediate data retrieval if available in the cache.</li>
</ul>
<h3>Cons:</h3>
<ul>
<li><strong>Risk of Stale Data:</strong> There&#8217;s a high chance of serving outdated information if the cache isn&#8217;t regularly refreshed.</li>
<li><strong>Dependence on Cache:</strong> Excessive reliance on cached data can prevent accessing fresh data from the network.</li>
</ul>
<h2>Summary</h2>
<p>The choice of data fetching strategy should be tailored to the specific needs of your application. <strong>Network Only</strong> is best for applications requiring real-time data. <strong>Network and Cache</strong> offers a balanced solution suitable for most use cases. <strong>Cache Only</strong> is ideal for applications where data doesn&#8217;t change frequently and speed is paramount.</p>
</article>


---

## 29. Web Protocols Cheat Sheet

- Difficulty: 🟠 Medium
- Subtitle: Compare Polling, HTTP, WebSockets, and SSE for optimal web communication.
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.23-PM.png

### Content

<article>
<h1>Web Protocols Cheat Sheet &#8211; Frontend System Design</h1>
<p><img loading="lazy" decoding="async" class="alignnone wp-image-1434 size-full " style="max-width: 200px;" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.15.59-PM.png" alt="" width="698" height="1338" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.15.59-PM.png 698w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.15.59-PM-157x300.png 157w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.15.59-PM-534x1024.png 534w" sizes="(max-width: 698px) 100vw, 698px" /></p>
<p>HTTP/1.x and HTTP/2 represent two major versions of the Hypertext Transfer Protocol used for the World Wide Web. HTTP/1.x, with its final iteration being HTTP/1.1, has been the backbone of the web for decades. Its simplicity and text-based nature characterize it, making it easy to use and understand. Each request-response cycle in HTTP/1.x typically opens a new TCP connection, leading to a straightforward but potentially inefficient process, especially when loading complex web pages with many elements.</p>
<p>HTTP/2, on the other hand, introduced several key improvements to enhance web performance and efficiency. One of the most significant changes is the introduction of multiplexing, allowing multiple requests and responses to be sent asynchronously over a single TCP connection, reducing latency and improving page load times. HTTP/2 also incorporates header compression to reduce overhead and introduces server push, which allows servers to send resources proactively. Despite these advancements, HTTP/2 maintains high-level compatibility with HTTP/1.x, ensuring that applications built on the older versions can be upgraded without drastic changes.</p>
<table border="1">
<thead>
<tr>
<th>Feature</th>
<th>HTTP/1.x Pros</th>
<th>HTTP/2 Pros</th>
</tr>
</thead>
<tbody>
<tr>
<td>Connection Management</td>
<td>Simple; each request/response pair uses a separate TCP connection.</td>
<td>Multiple requests and responses can be multiplexed over a single TCP connection, reducing overhead.</td>
</tr>
<tr>
<td>Performance</td>
<td>Well-understood behavior and widespread support across web infrastructure.</td>
<td>Significantly improved performance through header compression, prioritization of requests, and server push capabilities.</td>
</tr>
<tr>
<td>Resource Loading</td>
<td>Sequential loading can be simpler for developers to manage and predict.</td>
<td>Concurrent loading of resources reduces page load times and improves user experience.</td>
</tr>
<tr>
<td>Protocol Overhead</td>
<td>HTTP/1.x&#8217;s textual nature can be more readable and easier to debug manually.</td>
<td>Binary framing layer reduces overhead and improves parsing efficiency.</td>
</tr>
<tr>
<td>Scalability</td>
<td>More straightforward to implement on small-scale or less complex websites.</td>
<td>Better suited for complex applications and high-traffic websites due to efficient use of resources.</td>
</tr>
<tr>
<td>Compatibility and Adoption</td>
<td>Universal support across all web browsers and servers.</td>
<td>It requires modern web infrastructure and browsers but is widely supported in current environments.</td>
</tr>
</tbody>
</table>
<h2>Polling</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1439" style="max-width: 200px;" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM.png" alt="" width="1148" height="1188" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM.png 1148w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-290x300.png 290w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-990x1024.png 990w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-768x795.png 768w" sizes="(max-width: 1148px) 100vw, 1148px" /></p>
<p>Polling, a technique used in computer networks to periodically check the state or presence of new data by making repeated requests to a server, is revered for its implementation simplicity. It&#8217;s straightforward to set up, making it a go-to choice for many developers when real-time data updates are not critical. Polling facilitates easy load balancing, distributing requests across multiple servers to enhance scalability. Additionally, it&#8217;s compatible with modern protocols like HTTP/2, which can optimize its performance through features like multiplexing.</p>
<p>However, polling is not without its drawbacks. It can lead to inefficient use of resources, particularly if new data is infrequent, as servers must process requests even when there&#8217;s nothing new to return. This can also result in increased server load, affecting overall performance, and generate significant network traffic, leading to bandwidth overuse. Moreover, the inherent nature of polling means data is not updated in real time, which can result in noticeable delays in data freshness, potentially impacting user experience in applications where timely data is crucial.</p>
<table border="1">
<thead>
<tr>
<th>Feature</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>Implementation Simplicity</td>
<td>Polling is straightforward to implement, involving periodic requests to the server.</td>
<td>Can lead to inefficient resource use if new data is infrequent.</td>
</tr>
<tr>
<td>Load Balancing</td>
<td>Distributing requests across multiple servers is relatively simple, enhancing scalability.</td>
<td>Server resources may be underutilized during off-peak times.</td>
</tr>
<tr>
<td>Protocol Compatibility</td>
<td>Works well with HTTP/2, leveraging its performance optimizations and multiplexing capabilities.</td>
<td>Without careful implementation, can negate HTTP/2 benefits due to frequent connections.</td>
</tr>
<tr>
<td>Data Freshness</td>
<td>Periodic updates ensure data is regularly refreshed.</td>
<td>May experience delays in receiving real-time data due to fixed interval polling.</td>
</tr>
<tr>
<td>Server Load</td>
<td>Server load can be predicted and managed based on known polling intervals.</td>
<td>Constant polling can lead to unnecessary server load, impacting performance.</td>
</tr>
<tr>
<td>Network Traffic</td>
<td>Simple to monitor and predict network traffic patterns.</td>
<td>Generates significant overhead, especially when there&#8217;s no new data to retrieve.</td>
</tr>
</tbody>
</table>
<h2>Long Polling</h2>
<p>While inheriting many advantages of traditional polling, such as ease of implementation and compatibility with existing web infrastructures, this approach offers a more efficient data retrieval method. Adopting a model that allows the server to hold a request open until new data is available can reduce the overall number of requests, potentially decreasing unnecessary network traffic and improving the freshness of the data presented to the user.</p>
<p>However, this method is not without its drawbacks. Similar to traditional polling, it can still suffer from issues like long latency in data updates, which may not be ideal for applications requiring real-time responsiveness. Connection timeouts and the risk of increased traffic overhead during peak times or in scenarios with numerous concurrent connections also pose significant challenges. Thus, while this method can offer improvements in certain areas over traditional polling, careful consideration and management are required to mitigate its limitations, especially in high-demand environments.</p>
<table border="1">
<thead>
<tr>
<th>Aspect</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>Implementation Ease</td>
<td>Shares the simplicity of setup and debugging with traditional polling.</td>
<td>Additional logic may be required to handle long polling connections and responses.</td>
</tr>
<tr>
<td>Infrastructure Compatibility</td>
<td>Utilizes existing infrastructure without needing significant changes.</td>
<td>Limited by the capabilities and scalability of the current infrastructure.</td>
</tr>
<tr>
<td>Data Freshness</td>
<td>Improves over traditional polling by reducing the wait time for new data.</td>
<td>Still subject to delays, not suitable for real-time applications needing instant updates.</td>
</tr>
<tr>
<td>Resource Efficiency</td>
<td>Can be optimized to reduce unnecessary network load compared to constant polling.</td>
<td>Potential for increased server and network load during peak usage or with many clients.</td>
</tr>
<tr>
<td>User Experience</td>
<td>Can improve user experience by providing more timely updates.</td>
<td>Long wait times for updates can still negatively impact user engagement.</td>
</tr>
<tr>
<td>Scalability</td>
<td>More scalable than traditional polling in moderate use cases.</td>
<td>Scalability challenges can arise with a high number of concurrent long polling requests.</td>
</tr>
</tbody>
</table>
<h2>WebSockets</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1440" style="max-width: 200px;" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.23-PM.png" alt="" width="802" height="1200" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.23-PM.png 802w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.23-PM-201x300.png 201w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.23-PM-684x1024.png 684w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.23-PM-768x1149.png 768w" sizes="(max-width: 802px) 100vw, 802px" /></p>
<table border="1">
<thead>
<tr>
<th>Aspect</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>Communication Type</td>
<td>Duplex communication allows for real-time, bidirectional data exchange between client and server.</td>
<td></td>
</tr>
<tr>
<td>Performance</td>
<td>High-speed communication channel, ideal for low-latency applications.</td>
<td>Continuous connections can increase resource consumption on both the client and server sides.</td>
</tr>
<tr>
<td>Connection Efficiency</td>
<td>Utilizes a single TCP connection, reducing the overhead of multiple HTTP connections.</td>
<td>Managing a single, persistent connection can be complex, especially in distributed systems.</td>
</tr>
<tr>
<td>Scalability</td>
<td></td>
<td>Challenges in efficiently load-balancing WebSocket connections can affect scalability.</td>
</tr>
<tr>
<td>Compatibility</td>
<td>Supported by most modern web browsers, facilitating widespread use.</td>
<td>Some firewalls, proxies, and older network infrastructure may face compatibility issues.</td>
</tr>
<tr>
<td>Protocol Overhead</td>
<td>Lower protocol overhead compared to HTTP polling, enhancing efficiency.</td>
<td>Initial handshake and setup can introduce some overhead and complexity.</td>
</tr>
</tbody>
</table>
<h2>Server-Sent Events (SSE)</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1441" style="max-width: 200px;" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.38-PM.png" alt="" width="962" height="1186" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.38-PM.png 962w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.38-PM-243x300.png 243w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.38-PM-831x1024.png 831w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.19.38-PM-768x947.png 768w" sizes="(max-width: 962px) 100vw, 962px" /></p>
<p>Server-sent events (SSE) offer a streamlined method for servers to push updates to web clients, harnessing the capabilities of HTTP/2 for improved efficiency and performance. Using gzipping and multiplexing, inherent to HTTP/2, enables SSE to deliver updates with reduced bandwidth usage and better connection management. This approach is particularly resource-efficient as it transmits only necessary text-based updates, making it an ideal choice for applications that require server-initiated messages, such as live news feeds or stock tickers.</p>
<p>However, the primary limitation of SSE lies in its unidirectional nature, allowing data to flow solely from server to client. This makes it less suited for applications that require a two-way exchange of information, such as interactive games or chat applications. Furthermore, its focus on text data may restrict its use in scenarios that demand the transmission of binary data or complex data structures. Despite these constraints, SSE&#8217;s ease of integration with</p>
<table border="1">
<thead>
<tr>
<th>Aspect</th>
<th>Pros</th>
<th>Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>Protocol Advantages</td>
<td>Benefits from HTTP/2 improvements like gzipping for reduced size and multiplexing for better connection efficiency.</td>
<td></td>
</tr>
<tr>
<td>Resource Utilization</td>
<td>Sends only necessary updates as text, optimizing bandwidth and server resources.</td>
<td></td>
</tr>
<tr>
<td>Scalability</td>
<td>Compatible with standard load balancing strategies, enhancing scalability.</td>
<td></td>
</tr>
<tr>
<td>Communication Direction</td>
<td></td>
<td>Limited to server-to-client communication, not supporting client-initiated data streams.</td>
</tr>
<tr>
<td>Data Flexibility</td>
<td></td>
<td>Primarily supports text-based data, which may not be ideal for binary or more complex data needs.</td>
</tr>
<tr>
<td>Integration Simplicity</td>
<td>More straightforward to implement on top of the existing HTTP infrastructure without significant changes.</td>
<td></td>
</tr>
<tr>
<td>Real-Time Capability</td>
<td>Provides near real-time updates to clients, enhancing user experience for live data feeds.</td>
<td>May experience latency issues in high-volume or high-traffic scenarios.</td>
</tr>
</tbody>
</table>
<h2>REST API</h2>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1442" style="max-width: 200px;" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-1.png" alt="" width="1148" height="1188" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-1.png 1148w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-1-290x300.png 290w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-1-990x1024.png 990w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2025-01-01-at-1.18.40-PM-1-768x795.png 768w" sizes="(max-width: 1148px) 100vw, 1148px" /></p>
<div>
<p>REST APIs have long been the standard for web services, prized for their simplicity, standardization, and compatibility with web technologies like HTTP/2. They excel in scenarios where the API&#8217;s structure and data requirements are relatively stable and predictable, offering straightforward scalability through load balancing. However, their stateless nature can introduce latency in dynamic environments, and the granularity of data retrieval may result in traffic inefficiencies.</p>
<p>On the other hand, GraphQL represents a modern approach to API design, emphasizing flexibility and efficiency in data retrieval. By allowing clients to specify precisely what data they need, GraphQL can significantly reduce over-fetching, making it an attractive choice for dynamic, data-driven applications. Its type system and caching capabilities further enhance performance and reliability. However, the complexity of queries and potential verbosity pose challenges, particularly regarding traffic overhead and server processing demands.</p>
</div>
<table border="1">
<thead>
<tr>
<th>Aspect</th>
<th>GraphQL Pros</th>
<th>GraphQL Cons</th>
</tr>
</thead>
<tbody>
<tr>
<td>API Design</td>
<td>Enables clients to request what they need, reducing overfetching precisely.</td>
<td></td>
</tr>
<tr>
<td>Type Safety</td>
<td>The strongly typed nature of GraphQL enhances API safety and reduces client-side errors.</td>
<td></td>
</tr>
<tr>
<td>Caching</td>
<td>Advanced caching capabilities at the client level improve application performance.</td>
<td></td>
</tr>
<tr>
<td>Latency</td>
<td></td>
<td>Depending on the server&#8217;s processing capabilities, complex queries can result in latency.</td>
</tr>
<tr>
<td>Connection Reliability</td>
<td></td>
<td>Connection timeouts may occur, similar to REST APIs.</td>
</tr>
<tr>
<td>Verbosity</td>
<td></td>
<td>Verbose queries can lead to increased traffic, especially with nested structures.</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
</article>


---

## 30. Image Optimizations Strategies

- Difficulty: 🟢 Easy
- Subtitle: Elevate web speed with progressive, lazy loading, and dynamic image sizing.

### Content

<h1>Comprehensive Image Optimization Strategies for Web</h1>
<p>Images are the lifeblood of web content, but they can also be a double-edged sword. When used improperly, they can significantly slow down web page load times and compromise user experience. In this comprehensive guide, we will explore various image optimization strategies to help you strike the perfect balance between visual appeal and performance. We will delve deeper into the following techniques:</p>
<ol>
<li>Progressive Image Loading</li>
<li>Using the <code>srcset</code> Attribute</li>
<li>Lazy Loading</li>
<li>Utilizing Microservices for Dynamic Image Sizing</li>
</ol>
<h2>Progressive Image Loading</h2>
<p>Progressive image loading is a technique that revolutionizes the way images are displayed on web pages. Instead of loading the entire image at once, browsers gradually refine a low-resolution version, progressively enhancing the image&#8217;s quality as more data becomes available.</p>
<h3>Why It Matters:</h3>
<p>Traditional image loading can cause a &#8220;loading lag&#8221; that frustrates users. Progressive loading provides a more responsive and engaging experience, as users can see a preliminary version of the image while the high-resolution version loads in the background.</p>
<h3>Implementation:</h3>
<pre class="ql-syntax" spellcheck="false">&lt;img src="thumbnail.jpg" alt="High-Resolution Image" loading="lazy"&gt; 
</pre>
<p>The <code>loading="lazy"</code> attribute tells the browser to load the image lazily, contributing to the page&#8217;s perceived loading speed.</p>
<h2>Using the <code>srcset</code> Attribute</h2>
<p>The <code>srcset</code> attribute is an HTML attribute used in <code>&lt;img&gt;</code> tags to provide multiple sources for an image. It allows the browser to choose the most appropriate source based on the user&#8217;s device capabilities, such as screen resolution and size, to optimize image loading and display.</p>
<p>Here&#8217;s how the <code>srcset</code> attribute works:</p>
<ol>
<li>Providing Multiple Sources: You specify multiple image sources within the <code>srcset</code> attribute. Each source is defined as a URL followed by a space and the descriptor, which indicates the image&#8217;s characteristics.</li>
</ol>
<pre class="ql-syntax" spellcheck="false">&lt;img src="default.jpg" alt="Default Image" srcset="small.jpg 300w, medium.jpg 600w, large.jpg 1024w"&gt; 
</pre>
<ol>
<li>In this example, we have three image sources: <code>small.jpg</code>, <code>medium.jpg</code>, and <code>large.jpg</code>. Each is followed by a descriptor indicating the image&#8217;s width (<code>w</code> stands for width). For instance, <code>300w</code> means the image&#8217;s width is 300 pixels.</li>
<li>Browser Decision: When the browser loads the page, it evaluates the user&#8217;s device characteristics, such as screen width and resolution.</li>
<li>Choosing the Best Source: Based on these characteristics, the browser selects the most appropriate source from the list in the <code>srcset</code>. It aims to choose an image that closely matches the device&#8217;s capabilities to minimize loading times and data usage.</li>
<li>Loading the Chosen Image: The browser then loads and displays the chosen image. If the chosen image isn&#8217;t available or supported, it falls back to the <code>src</code> attribute&#8217;s value (in this case, &#8220;default.jpg&#8221;).</li>
</ol>
<p>Benefits of <code>srcset</code>:</p>
<ul>
<li>Responsive Images: <code>srcset</code> enables responsive web design by serving different images for different devices, ensuring images look sharp on high-resolution screens without wasting bandwidth on larger images for smaller screens.</li>
<li>Improved Performance: By serving appropriately sized images, you reduce page loading times and save data usage, especially on mobile devices with limited bandwidth.</li>
<li>Better User Experience: Users get images that match their device&#8217;s capabilities, resulting in a visually pleasing and optimized browsing experience.</li>
<li>Accessibility: You can provide images with different sizes to accommodate users with visual impairments or those using screen readers.</li>
</ul>
<p>It&#8217;s important to note that while <code>srcset</code> helps optimize image loading, you should also include the <code>alt</code> attribute for accessibility and ensure that your images are appropriately compressed and optimized for the web. Additionally, you may use the <code>sizes</code> attribute to provide additional information to the browser about how the image should be displayed on different screen sizes.</p>
<p>&nbsp;</p>
<h2>Lazy Loading</h2>
<p>Lazy loading is a technique that defers the loading of non-essential images until they enter the user&#8217;s viewport. This reduces the initial page load time, especially for images placed below the fold.</p>
<h3>Why It Matters:</h3>
<p>For content-heavy web pages, lazy loading can be a game-changer. It prioritizes the loading of images that users are likely to see immediately, improving the initial page load experience.</p>
<h3>Implementation:</h3>
<pre class="ql-syntax" spellcheck="false">&lt;img src="placeholder.jpg" data-src="image-to-lazy-load.jpg" alt="Lazy Loaded Image" loading="lazy"&gt; 
</pre>
<p>Using <code>loading="lazy"</code>, you instruct the browser to load the image only when it&#8217;s about to become visible, enhancing both page speed and user experience.</p>
<h2>Utilizing Microservices for Dynamic Image Sizing</h2>
<p>Microservices architecture offers an innovative way to optimize image delivery. By leveraging microservices, you can dynamically fetch images of the required size based on the user&#8217;s device characteristics.</p>
<h3>Why It Matters:</h3>
<p>This approach minimizes image storage requirements and optimizes bandwidth usage. Users receive images tailored to their devices, ensuring efficient image delivery.</p>
<h3>Implementation:</h3>
<p>Imagine a microservice that receives a request for an image along with desired dimensions. It fetches and serves the appropriately sized image, eliminating the need to store multiple image versions.</p>
<pre class="ql-syntax" spellcheck="false">// Microservice logic (simplified) 
app.get('/images/:imageName', (req, res) =&gt; { 
    const imageName = req.params.imageName; 
    const desiredWidth = req.query.width; 
    const desiredHeight = req.query.height; 
    // Logic to fetch and resize the image // 
    ... 
    // Serve the resized image 
    res.sendFile(resizedImagePath);
}); 
</pre>
<p>By using this technique, you ensure optimal bandwidth utilization and provide users with images tailored to their specific devices.</p>
<h2>Conclusion</h2>
<p>Effective image optimization is crucial for web performance, user experience, and accessibility. Employing techniques like progressive loading, <code>srcset</code> attributes, lazy loading, and microservices for dynamic sizing can significantly enhance your web application&#8217;s speed and responsiveness. The key is to find the right balance between image quality and performance to create a seamless and enjoyable browsing experience for your users.</p>


---

## 31. Apollo Cache

- Difficulty: 🟢 Easy
- Subtitle: Boost GraphQL app performance with Apollo Client's advanced caching techniques.

### Content

<article>
<h1>Apollo Client Caching Explained</h1>
<p>Apollo Client, known for its powerful GraphQL handling, incorporates an advanced caching system to boost application performance by minimizing unnecessary network requests. Below are key features and techniques for client-side caching with Apollo:</p>
<section>
<h2>InMemoryCache</h2>
<p>The default caching solution, <strong>InMemoryCache</strong>, stores normalized data in memory to eliminate redundancy and enhance lookup speeds.</p>
</section>
<section>
<h2>Normalized Cache</h2>
<p>By breaking down query results into individual objects and storing them flatly by unique identifiers, <strong>Normalized Cache</strong> ensures efficiency in data updating and retrieval.</p>
</section>
<section>
<h2>Cache Redirects</h2>
<p><strong>Cache Redirects</strong> guide Apollo&#8217;s cache to fetch data for certain queries from already cached information, even if stored under different queries.</p>
</section>
<section>
<h2>Field Policies</h2>
<p>Custom logic for cache operations at the field level can be defined through <strong>Field Policies</strong>, allowing for tailored caching strategies, pagination, and more.</p>
</section>
<section>
<h2>Cache Eviction and Garbage Collection</h2>
<p>Tools for <strong>Cache Eviction</strong> and <strong>Garbage Collection</strong> aid in maintaining an optimal cache size by purging unused or stale data.</p>
</section>
<section>
<h2>Persisted Cache</h2>
<p>With <strong>Persisted Cache</strong>, data can be stored in local storage or other mediums, enabling quick data retrieval even after application restarts.</p>
</section>
<section>
<h2>Optimistic UI</h2>
<p>The <strong>Optimistic UI</strong> feature allows for instant UI updates with hypothetical responses, later corrected by actual server data, fostering a seamless user experience.</p>
</section>
<section>
<h2>Fetch Policies</h2>
<p>Diverse <strong>Fetch Policies</strong> like <em>cache-first</em>, <em>cache-and-network</em>, and <em>network-only</em> dictate the interplay between cache and network requests, providing flexibility in data fetching strategies.</p>
</section>
<p>Utilizing these caching capabilities of Apollo Client can significantly improve the efficiency and responsiveness of applications built on GraphQL.</p>
</article>


---

## 32. Normalization

- Difficulty: 🟢 Easy
- Subtitle: Discover how normalized caching transforms data efficiency in web apps.

### Content

<article>
<h1>Understanding Normalized vs. Non-Normalized Cache</h1>
<p>In a blogging application, caching plays a crucial role in performance and efficiency. Let&#8217;s explore the concepts of normalized and non-normalized cache using blog posts and their authors as an example.</p>
<section>
<h2>Data from Server</h2>
<p>Consider this sample data structure fetched from the server, featuring two posts by the same author, &#8220;Alice&#8221;:</p>
<pre><code>{
  "posts": [
    {
      "id": "1",
      "title": "My First Post",
      "author": {
        "id": "a1",
        "name": "Alice"
      }
    },
    {
      "id": "2",
      "title": "Another Day, Another Post",
      "author": {
        "id": "a1",
        "name": "Alice"
      }
    }
  ]
}</code></pre>
</section>
<section>
<h2>Non-Normalized Cache</h2>
<p>In a non-normalized cache, data is stored as received, without any alteration. Here&#8217;s how it might look:</p>
<pre><code>{
  "posts": [
    {
      "id": "1",
      "title": "My First Post",
      "author": {
        "id": "a1",
        "name": "Alice"
      }
    },
    {
      "id": "2",
      "title": "Another Day, Another Post",
      "author": {
        "id": "a1",
        "name": "Alice"
      }
    }
  ]
}</code></pre>
<p>This approach leads to redundancy and inefficiency, particularly when updating shared data like the author&#8217;s name.</p>
</section>
<section>
<h2>Normalized Cache</h2>
<p>A normalized cache, on the other hand, structures data by unique identifiers, as shown below:</p>
<pre><code>{
  "Post": {
    "1": {
      "id": "1",
      "title": "My First Post",
      "authorId": "a1"
    },
    "2": {
      "id": "2",
      "title": "Another Day, Another Post",
      "authorId": "a1"
    }
  },
  "Author": {
    "a1": {
      "id": "a1",
      "name": "Alice"
    }
  }
}</code></pre>
<p>This method ensures data integrity, avoids redundancy, and is more space-efficient. Relationships are maintained through references like &#8220;authorId.&#8221;</p>
</section>
<p>While normalized caching adds a layer of complexity, particularly in reconstructing data relationships, it offers significant benefits in large-scale applications. Tools like Apollo Client greatly simplify managing these challenges.</p>
</article>


---

## 33. Design E-Commerce Platform

- Difficulty: 🟠 Medium
- Subtitle: Design a scalable, secure e-commerce platform with top-notch features.

### Content

<article>
<h1>Design E-Commerce Platform (Frontend System Design)</h1>
<p>This walkthrough focuses on the frontend architecture for a modern e-commerce product that supports discovery, conversion, and post-purchase workflows at scale.</p>
<h2>Core Requirements</h2>
<ul>
<li>Browse categories, search products, and apply filters/sorting.</li>
<li>Product detail pages with variants, media gallery, and recommendations.</li>
<li>Cart, checkout, address, payment, and order confirmation flows.</li>
<li>Order history, tracking, returns, and cancellation support.</li>
</ul>
<h2>Non-Functional Priorities</h2>
<ul>
<li>Fast first load and low interaction latency on mobile networks.</li>
<li>High availability during sales spikes.</li>
<li>Secure handling of checkout and personal data.</li>
<li>Resilient UX with retry/fallback behavior.</li>
</ul>
<h2>Frontend Architecture</h2>
<ul>
<li><strong>Presentation Layer:</strong> Page shells for Home, Listing, PDP, Cart, Checkout, and Account.</li>
<li><strong>Domain Modules:</strong> Catalog, Search, Pricing, Cart, Checkout, Orders, User.</li>
<li><strong>State Strategy:</strong> Local UI state + domain store for cart/session + server state cache.</li>
<li><strong>Network Layer:</strong> Typed API clients, request cancellation, retries for safe idempotent calls.</li>
</ul>
<h2>Data Flow Highlights</h2>
<ul>
<li>Listing page uses paginated queries with filter state encoded in URL.</li>
<li>PDP prefetches adjacent recommendation blocks and inventory status.</li>
<li>Cart uses optimistic updates with server reconciliation.</li>
<li>Checkout flow is step-based and persists progress in session storage.</li>
</ul>
<h2>Performance Plan</h2>
<ul>
<li>Code-split checkout and account modules.</li>
<li>Use image CDN transforms and lazy media loading.</li>
<li>Cache catalog/search responses with short TTL and SWR strategy.</li>
<li>Virtualize long product lists and defer non-critical widgets.</li>
</ul>
<h2>Security and Trust</h2>
<ul>
<li>Token handling with secure cookies and CSRF protection.</li>
<li>Input validation for addresses, coupons, and payment metadata.</li>
<li>Strong CSP and XSS-safe rendering for user-generated content.</li>
</ul>
<h2>Interview Talking Points</h2>
<ul>
<li>How to maintain UX when inventory/pricing changes mid-checkout.</li>
<li>How to degrade gracefully when recommendation/search services fail.</li>
<li>How to keep cart consistency across tabs/devices.</li>
</ul>
</article>

---

## 34. Design Netflix

- Difficulty: 🔴 Hard

### Content

<article>
<h1>Design Netflix (Frontend System Design)</h1>
<p>This topic covers the frontend system design for a streaming platform optimized for discovery, playback quality, and cross-device continuity.</p>
<h2>Core Requirements</h2>
<ul>
<li>Home feed with rows by genre, language, and personalized ranking.</li>
<li>Title details with cast, episodes, trailers, and related content.</li>
<li>Low-latency playback initiation with resume support.</li>
<li>Watchlist management and continue-watching synchronization.</li>
</ul>
<h2>Non-Functional Priorities</h2>
<ul>
<li>Perceived instant navigation across feed and detail pages.</li>
<li>Reliable playback startup and adaptive behavior on weak networks.</li>
<li>Consistent experience across TV, web, tablet, and mobile.</li>
<li>Resilience under peak-time traffic.</li>
</ul>
<h2>Frontend Architecture</h2>
<ul>
<li><strong>Shell + Route Segments:</strong> lightweight app shell with lazy route chunks.</li>
<li><strong>Modules:</strong> Home feed, Search, Details, Player, Watchlist, Profile.</li>
<li><strong>State:</strong> Session/profile state, playback state, and cached feed blocks.</li>
<li><strong>Playback Adapter:</strong> abstraction over player engine, telemetry, and QoE events.</li>
</ul>
<h2>Feed and Playback Strategy</h2>
<ul>
<li>Fetch hero + first rows first; defer lower-priority rails.</li>
<li>Prefetch details/trailer metadata for hovered or focused items.</li>
<li>Start playback with minimal manifest bootstrap, then hydrate extra metadata.</li>
<li>Persist progress with debounced heartbeat updates.</li>
</ul>
<h2>Performance and Reliability</h2>
<ul>
<li>Skeleton UIs for rails and detail blocks.</li>
<li>Image optimization with responsive sizes and progressive loading.</li>
<li>Retry policy for metadata calls; fallback rails on personalization failure.</li>
<li>Client-side caching for recently viewed titles and continue-watching list.</li>
</ul>
<h2>Accessibility and UX Quality</h2>
<ul>
<li>Keyboard-first navigation model for TV-like experiences.</li>
<li>Screen-reader labels for playback controls and timeline landmarks.</li>
<li>Clear error states for geo/device/content restrictions.</li>
</ul>
<h2>Interview Talking Points</h2>
<ul>
<li>Balancing personalization freshness vs caching efficiency.</li>
<li>Designing for instant-feeling playback while keeping startup robust.</li>
<li>Handling cross-device progress consistency and eventual consistency tradeoffs.</li>
</ul>
</article>

---

## 35. Design A Scalable Frontend Architecture

- Difficulty: 🟢 Easy

### Content

<article>
<h1>Design a Scalable Frontend Architecture</h1>
<p>This section outlines a practical architecture blueprint for frontend systems that must scale across teams, products, and traffic growth.</p>
<h2>Scalability Goals</h2>
<ul>
<li>Support many contributors without merge-gridlock and regressions.</li>
<li>Enable reusable foundations while allowing domain autonomy.</li>
<li>Maintain performance budgets as features and bundles grow.</li>
<li>Keep release velocity high with strong guardrails.</li>
</ul>
<h2>Architectural Building Blocks</h2>
<ul>
<li><strong>Layering:</strong> App shell, domain features, shared UI, shared utilities.</li>
<li><strong>Contracts:</strong> typed API boundaries and stable component interfaces.</li>
<li><strong>State Model:</strong> separate server state, domain state, and transient UI state.</li>
<li><strong>Observability:</strong> standardized logging, tracing markers, and UX metrics.</li>
</ul>
<h2>Team and Code Organization</h2>
<ul>
<li>Domain-oriented folders/modules aligned with ownership.</li>
<li>Design system package for consistent primitives and tokens.</li>
<li>Shared linting, testing, and CI policies across all feature modules.</li>
<li>ADR-driven decision tracking for major architecture choices.</li>
</ul>
<h2>Performance and Delivery Strategy</h2>
<ul>
<li>Route-level code splitting with progressive hydration where appropriate.</li>
<li>Asset budgets enforced in CI with regression thresholds.</li>
<li>Caching strategy per data class (critical, warm, optional).</li>
<li>Canary releases and feature flags for controlled rollouts.</li>
</ul>
<h2>Reliability and Quality Guardrails</h2>
<ul>
<li>Error boundaries per domain route.</li>
<li>Contract tests for API adapters and serialization boundaries.</li>
<li>Accessibility checks as part of PR validation.</li>
<li>Incident-ready dashboards tied to user journeys.</li>
</ul>
<h2>Evolution Plan</h2>
<ul>
<li>Start with modular monolith frontend.</li>
<li>Extract independently deployable slices only when team/product scale demands it.</li>
<li>Protect shared platform interfaces before scaling deployment complexity.</li>
</ul>
<h2>Interview Talking Points</h2>
<ul>
<li>When to centralize vs federate shared concerns.</li>
<li>How to prevent architecture entropy over time.</li>
<li>How to scale teams without sacrificing UX consistency.</li>
</ul>
</article>
