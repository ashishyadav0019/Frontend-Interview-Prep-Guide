# Pragmatic UI Problems Catalog

- Source file: `pragmaticUI.json`
- Dataset key: `data.problems.nodes`
- Total items: **100**

## Table of Contents

- [1. Flatten I](#1-flatten-i)
- [2. Histogram](#2-histogram)
- [3. Filtering Matching JSON](#3-filtering-matching-json)
- [4. Improve a function](#4-improve-a-function)
- [5. Throttle](#5-throttle)
- [6. Total Salaries](#6-total-salaries)
- [7. ClassNames](#7-classnames)
- [8. Array Methods](#8-array-methods)
- [9. Build Promise](#9-build-promise)
- [10. Find Corresponding Node](#10-find-corresponding-node)
- [11. Create DOM](#11-create-dom)
- [12. Phone Number Parser](#12-phone-number-parser)
- [13. Deep Clone](#13-deep-clone)
- [14. Event Emitter](#14-event-emitter)
- [15. Event Target](#15-event-target)
- [16. Traverse DOM](#16-traverse-dom)
- [17. Flatten II](#17-flatten-ii)
- [18. Intersection Observer](#18-intersection-observer)
- [19. Memoize I](#19-memoize-i)
- [20. Masonry Grid](#20-masonry-grid)
- [21. Navigation](#21-navigation)
- [22. Next Right Sibling](#22-next-right-sibling)
- [23. Node Store](#23-node-store)
- [24. Parser for Rich Text Editor](#24-parser-for-rich-text-editor)
- [25. Promisify Any Function](#25-promisify-any-function)
- [26. Skill Endorsements](#26-skill-endorsements)
- [27. Testing Framework](#27-testing-framework)
- [28. Text Highlighter](#28-text-highlighter)
- [29. Throttle II](#29-throttle-ii)
- [30. Tic Tac Toe](#30-tic-tac-toe)
- [31. Top K Words](#31-top-k-words)
- [32. Image Slider](#32-image-slider)
- [33. Virtual DOM I](#33-virtual-dom-i)
- [34. Virtual DOM II](#34-virtual-dom-ii)
- [35. Virtual DOM III](#35-virtual-dom-iii)
- [36. API Confirmation](#36-api-confirmation)
- [37. API Search and Render Image](#37-api-search-and-render-image)
- [38. Asynchronous Request Queue](#38-asynchronous-request-queue)
- [39. Auto Suggest Search List](#39-auto-suggest-search-list)
- [40. Autocomplete Search List](#40-autocomplete-search-list)
- [41. ClearAllIntervals()](#41-clearallintervals)
- [42. ClearAllTimeouts()](#42-clearalltimeouts)
- [43. Compose Function](#43-compose-function)
- [44. Curry Function](#44-curry-function)
- [45. Custom “this” Methods](#45-custom-this-methods)
- [46. Debounce II](#46-debounce-ii)
- [47. Debounce III](#47-debounce-iii)
- [48. Deep Equals](#48-deep-equals)
- [49. Event Emitter II](#49-event-emitter-ii)
- [50. Event Logger I](#50-event-logger-i)
- [51. Event Logger II](#51-event-logger-ii)
- [52. File Navigation](#52-file-navigation)
- [53. Gym Sessions](#53-gym-sessions)
- [54. Flatten III](#54-flatten-iii)
- [55. Flatten IV](#55-flatten-iv)
- [56. Flatten V](#56-flatten-v)
- [57. Flatten VI](#57-flatten-vi)
- [58. Flatten VII](#58-flatten-vii)
- [59. Flatten XI](#59-flatten-xi)
- [60. getElementsByClassName](#60-getelementsbyclassname)
- [61. Hierarchical Checkbox](#61-hierarchical-checkbox)
- [62. Tabs](#62-tabs)
- [63. Infinite Scrolling News Feed](#63-infinite-scrolling-news-feed)
- [64. K MostText Nodes](#64-k-mosttext-nodes)
- [65. Memoize II](#65-memoize-ii)
- [66. Promise Methods](#66-promise-methods)
- [67. querySelectorAll](#67-queryselectorall)
- [68. Rate Limiter](#68-rate-limiter)
- [69. Animate Element To The Right](#69-animate-element-to-the-right)
- [70. RxJS Observable](#70-rxjs-observable)
- [71. Set Interval with Linear Delay](#71-set-interval-with-linear-delay)
- [72. Stream](#72-stream)
- [73. String Repeater](#73-string-repeater)
- [74. Debounce I](#74-debounce-i)
- [75. To-do App](#75-to-do-app)
- [76. Transactions List](#76-transactions-list)
- [77. Trending Stocks](#77-trending-stocks)
- [78. Reorder Array With New Indexes](#78-reorder-array-with-new-indexes)
- [79. Merge Identical API Calls](#79-merge-identical-api-calls)
- [80. Fake Timer](#80-fake-timer)
- [81. GetTextBetweenNodes](#81-gettextbetweennodes)
- [82. First Bad Version](#82-first-bad-version)
- [83. Roman Numeral To Int](#83-roman-numeral-to-int)
- [84. Math.sqrtRoot](#84-mathsqrtroot)
- [85. FeatureFlag](#85-featureflag)
- [86. API Retry](#86-api-retry)
- [87. JSON.stringify](#87-jsonstringify)
- [88. Node Store II](#88-node-store-ii)
- [89. Build Airbnb](#89-build-airbnb)
- [90. Nested Comments I](#90-nested-comments-i)
- [91. Nested Comments II](#91-nested-comments-ii)
- [92. Accordion](#92-accordion)
- [93. Progress Bar](#93-progress-bar)
- [94. Star Rating System](#94-star-rating-system)
- [95. Emoji Selector](#95-emoji-selector)
- [96. Connect Four](#96-connect-four)
- [97. Data List](#97-data-list)
- [98. Signup Form](#98-signup-form)
- [99. Authentication Code](#99-authentication-code)
- [100. Build ChatGPT](#100-build-chatgpt)

---

## 1. Flatten I

- Source Number: 1
- Slug: `flatten-arrays-recursively-and-iteratively`
- Date: `2024-02-26T02:39:16`
- Difficulty: Easy
- Premium: No
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/UV9Lp-3uwwg?si=sIkEur5qGudwyPgh
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Robinhood, Zillow, Airbnb, OpenAI, Microsoft, Netflix
- Category: Array
- Type: Coding

### Content

<p>Write a function to flatten a multi-dimensional array into a single-level array. Provide both recursive and iterative solutions.</p>
<p>The problem involves transforming an array that contains nested arrays of various levels into a single-level array. For example, given an input like <code>[[1, 2, [3]], 4]</code>, the expected output would be <code>[1, 2, 3, 4]</code>. This challenge must be addressed in two distinct manners:</p>
<ul>
<li><strong>Recursive Approach:</strong> This method leverages the concept of recursion, where a function calls itself. When the function encounters an element that is an array, it calls itself with this nested array, accumulating all the elements into a single, flattened array. This approach elegantly navigates through the layers of nested arrays, extracting and combining elements into one cohesive structure.</li>
<li><strong>Iterative Approach:</strong> Differing from recursion, the iterative solution utilizes a stack to manage and process the elements. This method iteratively examines each element, and when an array is encountered, its elements are added to the stack to be processed. This continues until all elements are flattened into a single array, ensuring efficient handling without the overhead of recursive function calls.</li>
</ul>
<p><strong>Example:</strong> Let&#8217;s illustrate the problem and solutions with a concrete example.</p>
<pre><code>Input: [[1, 2, [3, [4, 5]]], 6]

Recursive Output: [1, 2, 3, 4, 5, 6]
Iterative Output: [1, 2, 3, 4, 5, 6]</code></pre>
<p>This task not only tests your understanding of array manipulation but also evaluates your ability to implement solutions using different programming paradigms. Whether you opt for the elegance of recursion or the control of iteration, mastering this challenge will sharpen your problem-solving skills and prepare you for frontend interviews.</p>
<p>As you embark on solving this problem, consider the implications of each approach, including the ease of implementation, efficiency, and potential limitations such as stack overflow in recursion for deeply nested arrays. Good luck!</p>


---

## 2. Histogram

- Source Number: 2
- Slug: `histogram`
- Date: `2024-03-16T17:16:17`
- Difficulty: Medium
- Premium: No
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/jSzkUAe4YBc
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Netflix
- Category: App Design
- Type: Vanilla

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-299" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-05-15-at-6.38.31-PM-300x118.png" alt="" width="300" height="118" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-05-15-at-6.38.31-PM-300x118.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-05-15-at-6.38.31-PM.png 527w" sizes="(max-width: 300px) 100vw, 300px" /></p>
<p>You are given an array of numbers. Your task is to write a function <code>buildHistogram()</code> that generates a histogram based on the occurrences of each unique number in the array. The histogram should visually represent the frequency of each number with vertical bars, displaying the count on the left axis.</p>
<p>This challenge involves:</p>
<ul>
<li>Counting the occurrences of each unique number in the given array.</li>
<li>Building a histogram where each bar represents the frequency of a unique number.</li>
<li>Displaying the frequency on the left axis of the histogram.</li>
</ul>
<p><strong>Example:</strong></p>
<pre><code>Input: [2, 4, 5, 2, 3, 4]
Histogram:
4 |      ##
3 |     ####
2 |    ######
1 |   ########
    ---------
     2  3  4  5
</code></pre>
<p>Your implementation should dynamically generate the histogram based on the input array, accommodating arrays with varying lengths and ranges of numbers. Consider the visualization aspect of the histogram, ensuring that the bars are proportional and accurately reflect the data&#8217;s distribution.</p>


---

## 3. Filtering Matching JSON

- Source Number: 3
- Slug: `filtering-matching-json`
- Date: `2024-03-07T16:21:53`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/8xOAFXTriUk
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Robinhood, Apple
- Category: JSON
- Type: Coding

### Content

<p>You are presented with a task involving a dataset represented as an array of objects, where each object delineates a person&#8217;s attributes, such as name, company, position, and level. Additionally, there is a match object specifying criteria to identify matches based on specific attributes. Your challenge is to develop a function, <code>findMatches</code>, which filters the dataset to return only the objects that meet all the criteria outlined in the match object.</p>
<p>The core objective is to write a program that, given the dataset and the match object, produces an array containing only the objects that satisfy all the criteria in the match object. For instance:</p>
<p><strong>Input:</strong></p>
<pre><code>data: [
  { name: 'John', company: 'Google', position: 'Software Engineer', level: 'Entry' },
  { name: 'Ann', company: 'Waymo', position: 'Product Manager', level: 'Entry' }
]
match: { position: 'Product Manager', level: 'Entry' }
</code></pre>
<p><strong>Output:</strong></p>
<pre><code>[
  { name: 'Ann', company: 'Waymo', position: 'Product Manager', level: 'Entry' }
]
</code></pre>
<p>This exercise tests your ability to manipulate complex data structures and implement effective filtering algorithms, essential skills in data handling and software development. It involves traversing arrays, understanding object properties, and applying logical operations to achieve the desired outcome.</p>


---

## 4. Improve a function

- Source Number: 4
- Slug: `improve-a-function`
- Date: `2024-03-14T16:02:57`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/VClupMy84gU
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Array
- Type: Coding

### Content

<article>Develop a function <code>excludeItems</code> tasked with filtering an array of items by removing those that meet specific exclusion criteria. This function plays a pivotal role in data processing, enabling the refinement of datasets based on dynamic conditions.</p>
<h3>Function Input</h3>
<ul>
<li><strong>items</strong> (Array of Objects): A collection of items, each represented as an object with various properties such as <em>color</em>, <em>type</em>, and <em>age</em>.</li>
<li><strong>excludes</strong> (Array of Objects): Criteria for exclusion, with each criterion as an object containing properties <em>k</em> (the property name to consider for exclusion) and <em>v</em> (the value of that property leading to exclusion).</li>
</ul>
<h3>Function Output</h3>
<p>Returns a filtered array comprising items that do not align with the specified exclusion criteria.</p>
<h3>Example</h3>
<p>Consider the following <em>items</em> array and <em>excludes</em> criteria:</p>
<pre><code>const items = [
  { color: 'red', type: 'tv', age: 18 },
  { color: 'silver', type: 'phone', age: 20 },
  { color: 'blue', type: 'book', age: 17 }
];

const excludes = [
  { k: 'color', v: 'blue' },
  { k: 'type', v: 'phone' }
];
</code></pre>
<p>Executing <code>excludeItems(items, excludes)</code> should yield:</p>
<pre><code>[{ color: 'red', type: 'tv', age: 18 }]</code></pre>
<p>This output represents the items array after the exclusion of items with a <em>color</em> of &#8216;blue&#8217; and <em>type</em> of &#8216;phone&#8217;, based on the specified criteria.</p>
<h3>Objective</h3>
<p>The goal is to implement a versatile function capable of sifting through an array of objects and excluding those that meet certain key-value criteria, thus refining the dataset for subsequent processing or analysis.</p>
</article>


---

## 5. Throttle

- Source Number: 5
- Slug: `throttle`
- Date: `2024-03-09T00:15:44`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/xf58_woO1oc
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Robinhood, Zillow, Airbnb, OpenAI, Microsoft, Netflix, Apple, LinkedIn, Stripe, ClickUp, PayPal, Snap, Vimeo, Adobe, TikTok
- Category: Javascript
- Type: Coding

### Content

<p>In this challenge, you are tasked with creating a <code>throttle</code> function, a fundamental concept in optimizing web applications by controlling the rate at which a function is executed. This mechanism is particularly beneficial for handling events that fire at a high frequency, such as scrolling or resizing, ensuring that the event handler doesn&#8217;t get called more often than is necessary for a smooth user experience.</p>
<h3>Function Requirements:</h3>
<p>The <code>throttle</code> function should accept a callback function and a delay time in milliseconds as parameters. It must return a new function, called <code>throttler</code>, that, when invoked, ensures the callback function is executed at most once in the specified delay period.</p>
<h3>Behavioral Specifications:</h3>
<ul>
<li>The <code>throttler</code> function calculates the time elapsed since the last callback execution and decides whether to execute the callback immediately or after the remaining delay.</li>
<li>If the elapsed time is less than the specified delay, the <code>throttler</code> function postpones the callback execution until the full delay period has passed since the last execution.</li>
<li>The <code>throttler</code> function also provides a <code>cancel</code> method to cancel any scheduled callback execution, enhancing control over the throttling behavior.</li>
</ul>
<h3>Technical Approach:</h3>
<p>Implement the <code>throttle</code> function using closure to maintain the state between invocations, such as the last call time and any pending timer. This approach ensures that the callback is not executed more frequently than the specified delay, regardless of how often the <code>throttler</code> function is called.</p>
<p>By integrating the <code>throttle</code> function into your application, you can significantly improve performance and user experience by reducing the frequency of heavy computations or DOM manipulations in response to rapid, high-frequency events.</p>


---

## 6. Total Salaries

- Source Number: 6
- Slug: `total-salaries`
- Date: `2024-03-08T20:51:10`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Google
- Category: JSON
- Type: Coding

### Content

<p>You are tasked with implementing a function named <code>calculateTotalSalaries</code> that will navigate through a company&#8217;s hierarchical structure to calculate the cumulative sum of salaries for all employees. The company&#8217;s structure is depicted as a nested object, where each node can either be a department containing further sub-departments or an array of employees. Each employee is represented by an object containing their name and salary.</p>
<p>The main challenge lies in efficiently traversing this nested structure, which may vary in depth and complexity across different companies, to aggregate all the salary values. This problem not only tests your ability to work with nested data structures but also assesses your recursive thinking and problem-solving skills.</p>
<p><strong>Input:</strong> A nested object representing the company&#8217;s structure, where each department can contain sub-departments or an array of employees with their respective salaries.</p>
<p><strong>Output:</strong> A single integer value representing the total sum of salaries of all employees across the entire company.</p>
<p><strong>Example:</strong></p>
<pre><code>const company = {
  sales: [
    { name: "John", salary: 1000 },
    { name: "Alice", salary: 1600 }
  ],
  development: {
    sites: [
      { name: "Peter", salary: 2000 },
      { name: "Alex", salary: 1800 }
    ],
    internals: [
      { name: "Jack", salary: 1300 }
    ]
  }
};
const totalSalaries = calculateTotalSalaries(company);
console.log(totalSalaries); // Output: 7700
</code></pre>
<p>In this example, the function <code>calculateTotalSalaries</code> navigates through each department and sub-department, summing up the salaries of &#8220;John&#8221;, &#8220;Alice&#8221;, &#8220;Peter&#8221;, &#8220;Alex&#8221;, and &#8220;Jack&#8221;, resulting in a total of 7700.</p>
<p>This problem encapsulates a real-world scenario where understanding and manipulating nested data structures are crucial. It provides a foundation for more complex data processing tasks that are common in software development, especially in handling hierarchical data.</p>


---

## 7. ClassNames

- Source Number: 7
- Slug: `classnames`
- Date: `2024-03-15T21:28:11`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Array
- Type: Coding

### Content

<p>The <code>classnames</code> utility function is a powerful tool in frontend development, used to dynamically construct a string of CSS class names based on certain conditions. This function simplifies the process of conditionally adding classes to HTML elements, making the code more readable and maintainable.</p>
<p>Your task is to implement the <code>classnames</code> function in JavaScript. This function should accept any number of arguments, where each argument can be a class name or a condition that determines whether a class name should be included. The function should process these arguments and return a single string containing all class names that meet their respective conditions, separated by spaces.</p>
<p><strong>Example:</strong></p>
<pre><code>
// If isActive is true and isError is false, 
// buttonClasses should be: 'btn btn-active'
const buttonClasses = classnames(
    'btn',
    isActive &amp; &amp; 'btn-active',
    isError &amp;&amp; 'btn-error'
);

</code></pre>
<p>This example demonstrates how the <code>classnames</code> function allows for flexible and conditional class name assignment based on the <code>isActive</code> and <code>isError</code> conditions. Implementing this function will enhance your ability to manage dynamic styling in your web applications.</p>


---

## 8. Array Methods

- Source Number: 8
- Slug: `custom-javascript-array-methods-mymap-myfilter-myreduce`
- Date: `2024-03-12T00:13:31`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Amazon, Robinhood, Zillow, Netflix, LinkedIn, Stripe, Snap, Vimeo
- Category: Array
- Type: Coding

### Content

<p>JavaScript arrays come with a set of powerful built-in methods like <code>map()</code>, <code>filter()</code>, and <code>reduce()</code> that are essential for manipulating array elements. The task is to recreate these methods, named <code>myMap()</code>, <code>myFilter()</code>, and <code>myReduce()</code>, by adding them to the <code>Array.prototype</code>. These custom methods should mimic the functionality of their native counterparts, enabling similar operations on arrays without using the built-in methods.</p>
<p>Here is a brief overview of what each method should accomplish:</p>
<ul>
<li><strong>myMap(callback):</strong> This method should create a new array populated with the results of calling a provided function on every element in the calling array.</li>
<li><strong>myFilter(callback):</strong> It should create a new array with all elements that pass the test implemented by the provided function.</li>
<li><strong>myReduce(callback, initialValue):</strong> This method applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value, starting from <code>initialValue</code> if provided.</li>
</ul>
<p>These custom methods are not only a great way to understand how JavaScript&#8217;s built-in array methods work under the hood but also serve as an excellent exercise in enhancing one&#8217;s ability to extend native JavaScript objects in a meaningful way.</p>


---

## 9. Build Promise

- Source Number: 9
- Slug: `build-custom-promise-javascript`
- Date: `2024-02-19T21:03:30`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/w9plxTCGAVE
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google, Robinhood, Zillow, Netflix
- Category: Javascript
- Type: Coding

### Content

<p class="mt-3">You are tasked with implementing a custom Promise class in JavaScript, mimicking the behavior of the native Promise. This includes handling asynchronous operations, chaining methods, and error management.</p>
<p class="mt-3">Your implementation should support the basic promise methods: <code>then</code>, <code>catch</code>, and the constructor should take an executor function with <code>resolve</code> and <code>reject</code> parameters.</p>
<p>Here&#8217;s an example of how your custom Promise might be used:</p>
<pre><code>const promise = new MyPromise((resolve, reject) =&gt; {
  setTimeout(() =&gt; resolve("Success!"), 1000);
});
promise.then(value =&gt; console.log(value));</code></pre>
<p>Please make sure to include a method called <code>getState()</code> that returns the STATE to pass all unit tests.</p>


---

## 10. Find Corresponding Node

- Source Number: 10
- Slug: `find-corresponding-node`
- Date: `2024-03-07T00:34:02`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/ElHeF2zY570
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Array
- Type: Coding

### Content

<p>Given two identical-structure DOM trees with differing text content, and a specified node in the first tree, your task is to implement a function to identify and return the corresponding node from the second tree. This problem tests your understanding of tree traversal and comparison techniques, making it essential for those interested in data structures and algorithms.</p>
<p><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-68" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-06-at-4.29.55-PM-300x213.png" alt="" width="300" height="213" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-06-at-4.29.55-PM-300x213.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-06-at-4.29.55-PM.png 540w" sizes="(max-width: 300px) 100vw, 300px" /></p>


---

## 11. Create DOM

- Source Number: 11
- Slug: `create-dom`
- Date: `2024-03-12T16:49:03`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p>You are tasked to build a <code>createDom</code> function, which is designed to dynamically create Document Object Model (DOM) elements or a tree of elements based on a structured definition provided by a root object. This root object might represent a simple text node or a more elaborate construct with nested elements, each potentially endowed with its own attributes and children.</p>
<p>The <code>createDom</code> function aims to facilitate the programmatic construction of DOM elements for the dynamic generation of web content. It is capable of:</p>
<ul>
<li>Creating simple text nodes by enclosing them within a paragraph element when the root is a string.</li>
<li>Generating complex elements as defined by an object, which specifies the type of element (tag name), attributes (like class, id, etc.), and children (which can be additional elements or text).</li>
</ul>
<p><strong>Example Usage:</strong></p>
<pre><code>
// Define a complex structure for the DOM
const root = {
    type: 'div',
    attributes: { class: 'container' },
    children: [
        { type: 'h1', children: ['Title'] },
        { type: 'p', children: ['This is a paragraph.'] }
    ]
};

// Utilize createDom to construct the DOM based on the defined structure
const dom = createDom(root);

// Append the newly created DOM to the document body or another DOM element
document.body.appendChild(dom);
</code></pre>
<p>This approach empowers developers to dynamically generate and update web page content programmatically, based on data or user interactions, enhancing the flexibility and interactivity of web applications.</p>


---

## 12. Phone Number Parser

- Source Number: 12
- Slug: `build-phone-number-parser`
- Date: `2024-03-10T18:13:33`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Stripe
- Category: Javascript
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1271" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-04-17-at-9.31.01-AM.png" alt="" width="449" height="176" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-04-17-at-9.31.01-AM.png 449w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-04-17-at-9.31.01-AM-300x118.png 300w" sizes="(max-width: 449px) 100vw, 449px" /></p>
<p>You are tasked with developing a phone number parser component using React, focusing on dynamically formatting and validating user inputs. This parser transcends mere data format assurance; it enhances user experience and data integrity in web applications that necessitate phone number inputs.</p>
<h3>Core Functionality</h3>
<p>The parser will feature a <code>Form</code> component for user input. As users type, the input field will automatically format the numbers into a readable format (e.g., <code>(123) 456-7890</code>), providing immediate feedback crucial for usability and allowing users to correct mistakes in real-time.</p>
<h3>Validation and Error Handling</h3>
<p>In addition to formatting, the parser will incorporate validation logic to confirm inputs adhere to a standard 10-digit phone number format, crucial for backend processing and frontend consistency, thus mitigating the risk of invalid data submissions.</p>
<h3>User Interactions</h3>
<p>The component will adeptly manage various user interactions. For example, when a user attempts to copy the phone number, only the digits (excluding formatting characters) will be copied to the clipboard, ensuring phone numbers are usable in diverse contexts without necessitating additional formatting.</p>
<h3>Technical Approach</h3>
<p>React&#8217;s <code>useState</code> and <code>useEffect</code> hooks will be employed for state management and side effects, respectively. Functions like <code>cleanNumber</code> will strip out non-numeric characters for consistent storage, while <code>formatPhoneNumber</code> will enhance displayed value readability.</p>
<h3>Validation Workflow</h3>
<p>The <code>validateInput</code> function will encapsulate validation logic, checking for completeness and format correctness, thus maintaining form integrity and guiding user inputs.</p>


---

## 13. Deep Clone

- Source Number: 13
- Slug: `javascript-deep-clone-frontend-interview-question`
- Date: `2024-03-10T18:32:59`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Coding

### Content

<p>Implement a function <code>deepClone</code> that takes an object as input and returns a deep copy of it. Unlike a shallow copy, which only copies the outermost layer, a deep copy replicates every level of nested objects. This means that changes made to the nested objects in the cloned object do not affect the original object.</p>
<p>This function is crucial in scenarios where you need to manipulate data while preserving the original structure for future use. Deep cloning is a common requirement in frontend development, especially in state management, where immutability is a key concept.</p>
<p>Consider the following object as an example:</p>
<pre><code>const source = {
    a: 10,
    b: 20,
    c: {
        d: 30,
        e: ['a', 'b', 1],
        f: {
            g: 1
        }
    }
}</code></pre>
<p>Your task is to create a <code>deepClone</code> function that accurately duplicates this structure, including all nested objects and arrays. Changes to any level of the cloned object should not impact the original object.</p>
<p>Here&#8217;s a basic usage example where changes to the cloned object do not affect the original:</p>
<pre><code>const obj = { role: 'foo' };
const clonedObj = deepClone(obj);
clonedObj.role = 'bar';
console.log(obj.role); // Output: 'foo'
console.log(clonedObj.role); // Output: 'bar'</code></pre>
<p>The challenge involves understanding and applying recursion for objects within objects, ensuring each level is appropriately cloned.</p>
<p>This problem tests your ability to work with references in JavaScript, a fundamental concept in ensuring data integrity and preventing unintended side effects in your applications.</p>


---

## 14. Event Emitter

- Source Number: 14
- Slug: `javascript-event-emitter-guide`
- Date: `2024-03-12T15:07:17`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>In modern application development, the asynchronous event-driven architecture plays a crucial role, especially in handling operations where the response time is uncertain. This architecture allows for a decoupled system where objects (emitters) can emit events at any time, and function objects (listeners) respond to these events as they are triggered.</p>
<p>The challenge here is to implement an <code>EventEmitter</code> class that encapsulates this behavior. The class should provide mechanisms to:</p>
<ul>
<li><strong>Emit events:</strong> Trigger an event by name, executing all callbacks subscribed to this event.</li>
<li><strong>Subscribe to events:</strong> Allow functions to listen for specific events and respond when those events are emitted. Each subscription should provide a way to release (unsubscribe) itself to avoid memory leaks and unintended behavior.</li>
</ul>
<p>The <code>EventEmitter</code> class should work as follows:</p>
<pre><code>class EventEmitter {
  constructor() {
    this.events = {};
  }

  subscribe(eventName, callback) {
    // Logic to add a listener for the event
  }

  emit(eventName, ...args) {
    // Logic to trigger an event and call all subscribed listeners
  }
}</code></pre>
<p>With this setup, you can create an instance of <code>EventEmitter</code>, subscribe functions to listen for named events, and emit those events at any point in your application. This approach is fundamental in creating non-blocking, asynchronous flows and is at the heart of many JavaScript frameworks and libraries.</p>
<p>This task will test your ability to work with higher-order functions, callbacks, and the principles of event-driven programming. Implementing the <code>EventEmitter</code> class will deepen your understanding of these concepts, which are pivotal in modern JavaScript development.</p>


---

## 15. Event Target

- Source Number: 15
- Slug: `eventtarget`
- Date: `2024-03-12T15:02:41`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>You are tasked with building an <code>EventTarget</code> class in JavaScript, structured to efficiently handle events. This class is fundamental for registering event listeners, removing these listeners, and dispatching events to the registered listeners.</p>
<p>The <code>EventTarget</code> class should encapsulate three primary methods:</p>
<ul>
<li><strong>addEventListener(name, callback):</strong> Utilized to register event listeners. Whenever an event with the specified name is dispatched, the corresponding callback functions are invoked. This method should prevent the addition of duplicate callback functions for the same event.</li>
<li><strong>removeEventListener(name, callback):</strong> Employed to deregister a previously added event listener. If the specified callback is located within the event&#8217;s callback list, it should be removed. Should the callback list become empty as a result, the event should be completely removed from the class&#8217;s registry.</li>
<li><strong>dispatchEvent(name):</strong> Used to trigger events. It executes all callback functions associated with the provided event name.</li>
</ul>
<p><strong>Example Usage:</strong></p>
<pre><code>const et = new EventTarget();
et.addEventListener('click', () => console.log('Clicked!'));
et.dispatchEvent('click'); // Output: "Clicked!"
et.removeEventListener('click', () => console.log('Clicked!'));
et.dispatchEvent('click'); // No output, as the listener has been removed.</code></pre>
<p>This <code>EventTarget</code> implementation offers a streamlined and adaptable approach to managing events within event-driven programming paradigms, allowing for the dynamic addition and removal of event handlers and the capability to programmatically initiate events.</p>


---

## 16. Traverse DOM

- Source Number: 16
- Slug: `traverse-dom`
- Date: `2024-03-15T19:15:46`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Amazon
- Category: DOM API
- Type: Coding

### Content

<p>Given a root node of a DOM tree, write a function to traverse the tree level by level and return an array of nodes in the order they are visited. This task simulates a breadth-first search (BFS) traversal of the Document Object Model (DOM), which is particularly useful for various web development tasks, such as manipulating or querying a webpage&#8217;s structure.</p>
<p>The function should take a single argument: the root node of the DOM tree to be traversed. It should return an array containing the nodes in the order they were visited during the traversal. The DOM tree can be visualized as a hierarchical structure of nodes, where each node represents an element in the webpage, and its children represent the nested elements within it.</p>
<p><strong>Example:</strong></p>
<pre><code>
Input: Root node of a DOM tree representing the following HTML structure:
&lt;div&gt;
  &lt;p&gt;Paragraph 1&lt;/p&gt;
  &lt;div&gt;
    &lt;p&gt;Paragraph 2&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;

Output: [div, p (Paragraph 1), div, p (Paragraph 2)]
</code></pre>
<p>This example illustrates a simple case where the function starts at the root <code>&lt;div&gt;</code> node, adds it to the results array, and then proceeds to its children, adding them to the array in the order they appear, level by level. The process continues until all nodes in the tree have been visited and added to the results array.</p>
<p>Your task is to implement this traversal function, ensuring that it accurately reflects the breadth-first search approach and correctly captures the structure of the DOM tree.</p>


---

## 17. Flatten II

- Source Number: 17
- Slug: `flatten-array-with-depth`
- Date: `2024-03-09T18:45:52`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Array
- Type: Coding

### Content

<article>
<h2>Flatten with Depth</h2>
<p>Implement a function to flatten a multi-level nested array up to a specified depth. The function should accept two arguments: the array to be flattened (<code>arr</code>) and the depth of flattening (<code>depth</code>). This challenge should be tackled using both recursive and iterative approaches to offer different strategies for achieving the same outcome.</p>
<h3>Recursive Solution:</h3>
<p>The recursive approach involves a function that calls itself to flatten each level of nested arrays until the specified depth is reached. If the current item is an array and the depth has not been exceeded, the function recursively flattens this item and concatenates the result. If the item is not an array or the depth has been exceeded, it is added directly to the result. This approach elegantly handles nested arrays by leveraging the call stack, but it&#8217;s essential to manage the depth to avoid excessive recursion that can lead to a stack overflow.</p>
<h3>Iterative Solution:</h3>
<p>The iterative approach uses a stack to manage the array items. Each item from the input array is processed: if it&#8217;s an array and the depth allows, its items are added to the stack to be processed; otherwise, the item is added to the results. This method iteratively deconstructs the nested arrays without recursion, making it robust for deeply nested structures but potentially more complex to implement and understand.</p>
<h3>Example Usage:</h3>
<p>Consider an array <code>[1, [2, [3, [4, 5]]], 6]</code> with a depth of 2. The expected output would be <code>[1, 2, 3, [4, 5], 6]</code>, flattening the array up to two levels deep but leaving any further nesting intact.</p>
<p>This problem tests your ability to manipulate arrays, handle recursion, and implement iterative solutions, all crucial skills for a frontend developer.</p>
</article>


---

## 18. Intersection Observer

- Source Number: 18
- Slug: `intersection-observer`
- Date: `2024-03-15T23:56:44`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/VCkOoDk4a80?si=qhc3jCsMK3b6vgf2
- Study Plan: 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Vanilla

### Content

<p>You are tasked with implementing an <strong>Intersection Observer</strong>, a utility commonly used in frontend development to detect when an element enters or exits the viewport. Your goal is to create a class that can observe multiple elements on a webpage and trigger a callback function when these elements intersect or stop intersecting with the viewport.</p>
<p>The Intersection Observer you will create should be capable of handling multiple elements simultaneously, monitoring their presence within the viewport. This feature is crucial for implementing lazy loading of images, infinite scrolling, and animations based on scroll position, enhancing user experience and performance.</p>
<p>To illustrate, consider a webpage with multiple sections that become visible only as the user scrolls. Your Intersection Observer should be able to detect when each section comes into view and trigger a specified callback function, allowing for dynamic content loading or animations.</p>
<p>Here is a basic example of how your Intersection Observer might be initialized and used:</p>
<pre><code>const observer = new MyIntersectionObserver((entries) =&gt; {
  entries.forEach(entry =&gt; {
    if (entry.isIntersecting) {
      console.log(entry.target, 'has entered the viewport');
    } else {
      console.log(entry.target, 'has exited the viewport');
    }
  });
});

// Assuming `section1` and `section2` are DOM elements you wish to observe
observer.observe(section1);
observer.observe(section2);
</code></pre>
<p>This implementation should efficiently manage and track the elements, ensuring that the callback function is invoked appropriately as elements enter and leave the viewport. Consider the implications of scroll events, element visibility, and the efficient use of resources in your solution.</p>


---

## 19. Memoize I

- Source Number: 19
- Slug: `memoize-i`
- Date: `2024-03-14T15:16:28`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Create a function <code>memoize</code> that enhances the efficiency of function calls by caching the results. Given a callback function and an optional resolver function, <code>memoize</code> should return a new function that remembers the results of previous invocations with specific arguments, thereby avoiding redundant calculations for the same inputs.</p>
<p>The returned function, <code>memoizedFn</code>, should operate as follows:</p>
<ul>
<li>It checks if the result for a given set of arguments is already stored in a cache. If so, it returns the cached result instead of executing the callback again.</li>
<li>If the result for the given arguments is not in the cache, <code>memoizedFn</code> calls the original callback with those arguments, stores the result in the cache, and then returns the result.</li>
<li>The cache should be a <code>Map</code> object where keys represent argument combinations, and values are the callback results for those arguments.</li>
</ul>
<p>Additionally, <code>memoizedFn</code> includes methods for cache management:</p>
<ul>
<li><code>has</code>: Checks if a result for a specific set of arguments is already cached.</li>
<li><code>delete</code>: Removes the cached result for a specific set of arguments.</li>
<li><code>clear</code>: Clears the entire cache.</li>
</ul>
<p>The optional <code>resolver</code> function, if provided, generates a custom key for caching based on the arguments passed to <code>memoizedFn</code>. If not provided, the key is generated by stringifying the arguments.</p>
<p>This memoization technique is particularly useful for optimizing performance in applications with heavy computational functions or expensive database queries that are frequently called with the same arguments.</p>


---

## 20. Masonry Grid

- Source Number: 20
- Slug: `masonry-grid`
- Date: `2024-03-16T22:32:07`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: App Design
- Type: Vanilla

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-388" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.42.59-PM-300x195.png" alt="" width="300" height="195" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.42.59-PM-300x195.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.42.59-PM-768x499.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.42.59-PM.png 776w" sizes="(max-width: 300px) 100vw, 300px" /></p>
<p>Create a dynamic Masonry layout using Vanilla JavaScript, which organizes a series of items into a grid layout that optimizes space by fitting elements in the optimal position based on available vertical space. This layout should resemble the way stones are laid in a masonry wall, where each item is placed in the shortest column available at the time of placement, creating a staggered effect rather than a uniform grid.</p>
<p>Your task is to implement a function that positions each item within a container to achieve the Masonry layout effect. Each item has its own content and height, and the layout should consist of a specified number of columns with a fixed gap between items. The items should be arranged such that they fill up the shortest column available, ensuring that the layout is balanced and the overall height of the grid is minimized.</p>
<p>The implementation should include the following:</p>
<ul>
<li>A function to create a new DOM element for each item, setting its class, text content, width, and height.</li>
<li>A function to calculate the position of each item and append it to the container, ensuring items are placed in the shortest column to achieve the Masonry effect.</li>
<li>Consideration for the number of columns and the gap between items, dynamically adjusting the layout based on the container&#8217;s width.</li>
</ul>
<p><strong>Example:</strong></p>
<pre><code>const items = [
    { content: 'Item 1', height: 150 },
    { content: 'Item 2', height: 100 },
    { content: 'Item 3', height: 120 },
    // more items...
];

// Expected to create a Masonry layout with the given items inside a container with an id of 'masonry'.
</code></pre>
<p>This task assesses your ability to manipulate the DOM using Vanilla JavaScript, handle dynamic layout calculations, and apply creative problem-solving to achieve complex layout patterns without external libraries.</p>


---

## 21. Navigation

- Source Number: 21
- Slug: `navigation`
- Date: `2024-03-16T23:10:03`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google
- Category: App Design
- Type: Vanilla

### Content

<p>The given problem involves understanding and explaining a JavaScript function that dynamically generates a navigation menu based on a nested data structure. The data, represented in a JavaScript array of objects, outlines a hierarchical structure of navigation items, where each item can have a name and potentially a list of child items, denoting sub-navigation menus.</p>
<p>The primary challenge is to traverse this nested data structure and create an HTML navigation menu that reflects the hierarchical relationships. This involves creating <code>&lt;ul&gt;</code> elements for each level of the hierarchy, <code>&lt;li&gt;</code> elements for each navigation item, and nesting them appropriately according to their parent-child relationships in the data.</p>
<p>The JavaScript function <code>renderNav</code> takes this navigation data as input and renders the corresponding HTML structure within a specified context, which by default is <code>document.body</code>. The function uses recursion to handle nested data, allowing it to generate menus at any depth.</p>
<p>For example, given a simplified version of the navigation data:</p>
<pre><code>[
  {
    "name": "Home",
    "children": [
      {
        "name": "About",
        "children": [
          {"name": "Team", "children": []},
          {"name": "History", "children": []}
        ]
      }
    ]
  },
  {"name": "Services", "children": []}
]</code></pre>
<p>The function would produce an HTML structure similar to:</p>
<pre><code>&lt;ul&gt;
  &lt;li&gt;Home
    &lt;ul&gt;
      &lt;li&gt;About
        &lt;ul&gt;
          &lt;li&gt;Team&lt;/li&gt;
          &lt;li&gt;History&lt;/li&gt;
        &lt;/ul&gt;
      &lt;/li&gt;
    &lt;/ul&gt;
  &lt;/li&gt;
  &lt;li&gt;Services&lt;/li&gt;
&lt;/ul&gt;</code></pre>
<p>This task evaluates your ability to work with DOM manipulation, recursion, and data structures in JavaScript, which are essential skills for frontend development.</p>


---

## 22. Next Right Sibling

- Source Number: 22
- Slug: `next-right-sibling`
- Date: `2024-03-14T16:28:45`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/46KnJk8eZDQ
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Microsoft
- Category: DOM API
- Type: Coding

### Content

<article><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-195" src="https://api.frontendlead.com/wp-content/uploads/2024/03/I8ncH1ncdGaBXV3nwPH061w1MmdqNR9p_1169x546_1597852405395-300x140.png" alt="" width="300" height="140" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/I8ncH1ncdGaBXV3nwPH061w1MmdqNR9p_1169x546_1597852405395-300x140.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/I8ncH1ncdGaBXV3nwPH061w1MmdqNR9p_1169x546_1597852405395-1024x478.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/I8ncH1ncdGaBXV3nwPH061w1MmdqNR9p_1169x546_1597852405395-768x359.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/I8ncH1ncdGaBXV3nwPH061w1MmdqNR9p_1169x546_1597852405395.png 1169w" sizes="(max-width: 300px) 100vw, 300px" />You are tasked with creating a function <code>findNextRightSibling</code> that identifies the next right sibling of a given node within a tree structure, resembling the DOM tree. This function should traverse the tree in a breadth-first manner, using a queue to keep track of the nodes.The function <code>findNextRightSibling</code> takes two arguments:</p>
<ul>
<li><code>root</code>: The root node of the tree from which the search begins.</li>
<li><code>target</code>: The node for which you want to find the next right sibling.</li>
</ul>
<p>The goal is to find and return the node that is the immediate right sibling of the <code>target</code> node. If the <code>target</code> node is the last child of its parent or does not have any right siblings, the function should return <code>null</code>.</p>
<p>This functionality is crucial for applications that need to understand or manipulate hierarchical structures similar to the DOM, where knowing a node&#8217;s relationship to its siblings can influence layout, styling, or interactivity.</p>
</article>


---

## 23. Node Store

- Source Number: 23
- Slug: `node-store`
- Date: `2024-03-14T23:33:05`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/oNYXqbwaQHI
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Array
- Type: Coding

### Content

<p>Create a class called <code>NodeStore</code> that allows you to store values associated with DOM nodes. The class should provide the following methods:</p>
<ul>
<li><strong>set(node, value):</strong> Sets the value for a given DOM node.</li>
<li><strong>get(node):</strong> Retrieves the value associated with a given DOM node.</li>
<li><strong>has(node):</strong> Checks if a given DOM node exists in the store.</li>
</ul>
<p>Remember, we will be storing DOM nodes, so each retrieval might have the same node item, so we want keys to be unique.</p>
<p><strong>Example:</strong></p>
<pre><code>const node1 = document.createElement('p');
const node2 = document.createElement('p');
const store = new NodeStore();
store.set(node1, 1);
store.set(node2, 2);
console.log(store.get(node1)); // Expected output: 1
console.log(store.get(node2)); // Expected output: 2</code></pre>
<p>This task tests your understanding of JavaScript classes, DOM manipulation, and associative arrays or objects. It&#8217;s a practical scenario for frontend developers who need to manage state or metadata associated with specific DOM elements dynamically.</p>


---

## 24. Parser for Rich Text Editor

- Source Number: 24
- Slug: `parser-for-rich-text-editor`
- Date: `2024-03-15T16:16:31`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/watch?v=o89VYBvOAmo
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Google
- Category: Algorithmic
- Type: Coding

### Content

<p>Given a string and an array representing styles, the task is to render HTML similar to the output of a rich text editor.</p>
<p>The input consists of a string and a style array. Each element in the style array is another array that contains three items: the start index, the end index, and the HTML tag to be applied. The goal is to apply these styles to the specified ranges within the string and generate the corresponding HTML output.</p>
<p><strong>Example:</strong></p>
<pre><code>Input: 'Hello, world', [[0, 2, 'i'], [4, 9, 'b'], [7, 10, 'u']]

Output: '&lt;i&gt;Hel&lt;/i&gt;l&lt;b&gt;o, w&lt;u&gt;orl&lt;/u&gt;&lt;/b&gt;&lt;u&gt;d&lt;/u&gt;'</code></pre>
<p>This example demonstrates overlapping style ranges where the <code>&lt;u&gt;</code> tag is applied both within and outside the <code>&lt;b&gt;</code> tag&#8217;s range, showing the complexity of nesting and ordering HTML tags based on the input style ranges.</p>
<p>The challenge lies in correctly applying the styles, especially when the style ranges overlap, ensuring that the HTML tags are nested and ordered properly according to their positions in the input string.</p>


---

## 25. Promisify Any Function

- Source Number: 25
- Slug: `promisify-any-function`
- Date: `2024-03-13T15:11:53`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<section>Your task is to implement the <code>promisify</code> function. This function should:</p>
<ul>
<li>Accept a callback-based function as its only argument.</li>
<li>Return a new function that, when called, returns a Promise.</li>
<li>Ensure that if the original function calls the callback with an error, the returned Promise is rejected with that error.</li>
<li>Resolve the returned Promise with the result if the original function completes successfully.</li>
</ul>
<p>This transformation will allow developers to invoke legacy callback-based functions in a more modern, cleaner, and more intuitive way, improving code readability and error handling.</p>
</section>


---

## 26. Skill Endorsements

- Source Number: 26
- Slug: `aggregate-skill-endorsements-javascript-guide`
- Date: `2024-03-08T22:47:21`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: LinkedIn
- Category: JSON
- Type: Coding

### Content

<p>You are given an array of skill endorsements, where each endorsement is represented by an object that includes a skill and the user who endorsed it. Your task is to write a function, <code>aggregateSkillEndorsements</code>, that processes this array and produces a summary for each skill.</p>
<p>This summary should include the skill name, an array of users who have endorsed the skill, and the total count of endorsements the skill has received. The primary challenge lies in efficiently aggregating this information from a potentially large and unorganized list of endorsements.</p>
<p><strong>Input:</strong> An array of endorsement objects, where each object has <code>skill</code> and <code>user</code> properties.</p>
<p><strong>Output:</strong> An array of objects, each representing a skill summary that contains the skill name, an array of unique users who endorsed it, and the total count of endorsements for that skill.</p>
<p><strong>Example:</strong></p>
<pre><code>const endorsements = [
  { skill: 'css', user: 'Bill' },
  { skill: 'javascript', user: 'Chad' },
  { skill: 'javascript', user: 'Bill' },
  { skill: 'css', user: 'Sue' },
  { skill: 'javascript', user: 'Sue' },
  { skill: 'html', user: 'Sue' }
];

const skillSummaries = aggregateSkillEndorsements(endorsements);

// Output:
// [
//   { skill: 'javascript', users: ['Chad', 'Bill', 'Sue'], count: 3 },
//   { skill: 'css', users: ['Bill', 'Sue'], count: 2 },
//   { skill: 'html', users: ['Sue'], count: 1 }
// ]
</code></pre>
<p>The function must efficiently traverse the endorsements array, grouping endorsements by skill while keeping track of the unique users and total count for each skill. This task tests your ability to manipulate and aggregate data from complex data structures, a common requirement in software development.</p>


---

## 27. Testing Framework

- Source Number: 27
- Slug: `testing-framework`
- Date: `2024-03-14T14:44:06`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: App Design
- Type: Coding

### Content

<p>Implement a simple testing framework for frontend code that allows you to define test suites and test cases, and provides assertion methods for validating expected outcomes. Write the necessary functions and classes to achieve this.</p>
<p>The framework should enable the definition of a <code>describe</code> function for test suites, an <code>it</code> function for test cases within those suites, and an <code>expect</code> function for making assertions within those test cases. The framework should support the following functionalities:</p>
<ul>
<li>Grouping related test cases using the <code>describe</code> function.</li>
<li>Defining individual test cases with the <code>it</code> function that describes the specific test.</li>
<li>Making assertions within test cases using the <code>expect</code> function and assertion methods like <code>toExist</code>, <code>toBe</code>, and <code>toBeType</code>.</li>
</ul>
<p>For example:</p>
<pre><code>describe('Hello world', () =&gt; {
  it('input exists', () =&gt; {
    let input = null;
    expect(input).toExist();
  });
});</code></pre>
<p>This should produce an output like:</p>
<pre><code>beginning test suite Hello world
beginning test case input exists
failed running test suite Hello world on test case input exists with error message expected value to exist but got null</code></pre>
<p>Another example:</p>
<pre><code>describe('Hello world', () =&gt; {
  it('input is as expected', () =&gt; {
    let input = 'foo';
    let expected = 'fooo';
    expect(input).toBe(expected);
  });
});</code></pre>
<p>Should result in:</p>
<pre><code>beginning test suite Hello world
beginning test case input is as expected
failed running test suite Hello world on test case input is as expected with error message expected "foo" to be "fooo"</code></pre>
<p>And:</p>
<pre><code>describe('Hello world', () =&gt; {
  it('input is as expected', () =&gt; {
    let input = 'foo';
    let expected = 'string';
    expect(input).toBeType(expected);
  });
});</code></pre>
<p>Would output:</p>
<pre><code>beginning test suite Hello world
beginning test case input is as expected
failed running test suite Hello world on test case input is as expected with error message expected "foo" to be of type "string" but got "object"</code></pre>
<p>This framework aims to provide a lightweight and straightforward way for developers to write and organize tests, ensuring the reliability and correctness of their frontend code.</p>


---

## 28. Text Highlighter

- Source Number: 28
- Slug: `text-highlighter`
- Date: `2024-03-15T15:34:58`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/3Isrio8vIP8
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Google
- Category: DOM API
- Type: Coding

### Content

<p>Given an HTML element and a specific word to look for, the task is to write a function that highlights the occurrences of that word within the text content of the element. The function should encapsulate the found word with a <code>span</code> element having a specified background color to visually emphasize the highlighted text.</p>
<p>Consider the following HTML structure as an input example:</p>
<pre><code>&lt;div id="hello"&gt; I have some text 
  &lt;p&gt;Which has some subtext &lt;a href="#"&gt;that has a link&lt;/a&gt;&lt;/p&gt; 
  &lt;p&gt;And a sibling&lt;/p&gt; 
  Finally some random text
&lt;/div&gt;</code></pre>
<p>The objective is to highlight a word, for instance, &#8220;Finally&#8221;, within the <code>div</code> element with the id <code>hello</code>. The word &#8220;Finally&#8221; should be wrapped in a <code>span</code> element with a background color, for example, red, to visually differentiate it from the rest of the text.</p>
<p>This challenge requires manipulating the DOM to dynamically change the HTML content based on the text search criteria. The solution should ensure that only text content is affected without altering the inherent structure of the HTML or affecting nested elements such as <code>&lt;p&gt;</code> and <code>&lt;a&gt;</code>.</p>


---

## 29. Throttle II

- Source Number: 29
- Slug: `throttle-ii`
- Date: `2024-03-12T01:08:34`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Google, Zillow, Microsoft, Snap
- Category: Array
- Type: Coding

### Content

<p>This problem extends the concept of throttling function executions, introducing an improved version of the <code>throttle()</code> function. The enhanced <code>throttle()</code> function now accepts an additional third parameter: an options object. This object includes two boolean properties: <code>leading</code> and <code>trailing</code>. The <code>leading</code> property decides if the throttled function should be invoked at the start or after a delay, while the <code>trailing</code> property controls whether the function should be called after the delay concludes or right away.</p>
<p>The primary objective is to design a throttling function that can limit the execution rate of a given function. Unlike the basic implementation from the previous problem, this version grants more control over the throttled function&#8217;s behavior, allowing for a more tailored functionality.</p>
<p>To illustrate, consider the following examples which demonstrate how the options object influences the throttling:</p>
<ul>
<li>With <code>{ leading: true, trailing: false }</code>, the function will execute immediately on the first call, then ignore all calls during the wait time.</li>
<li>With <code>{ leading: false, trailing: true }</code>, the function will ignore the initial call, then execute at the end of the wait time, applying the last arguments passed during the wait.</li>
<li>When both are true or both are false, the function&#8217;s behavior adjusts accordingly, offering various execution strategies that can be customized as needed.</li>
</ul>
<p>To verify the correctness of your <code>throttle()</code> function, a test function named <code>run()</code> is provided. It simulates function calls, capturing their timing, and utilizes <code>setTimeout()</code> to manage execution based on the specified delay and options. The outcome is an array of strings that represent the executed function calls and their respective timings.</p>
<p>Given this setup, your task is to implement the improved <code>throttle()</code> function. Ensure that it adheres to the specified behavior, taking into account the leading and trailing options, and that it functions accurately even in the complex browser environment where <code>setTimeout()</code> and <code>clearTimeout()</code> might not always be precise.</p>


---

## 30. Tic Tac Toe

- Source Number: 30
- Slug: `tic-tac-toe`
- Date: `2024-03-16T21:41:03`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Atlassian
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-370" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-2.44.10-PM.png" alt="" width="200" height="216" /></p>
<p>You are tasked with building a Tic-Tac-Toe game in React. The game allows two players to take turns marking squares on a 3&#215;3 grid. The objective is to be the first player to place three of their marks in a horizontal, vertical, or diagonal row to win the game. Implement the game logic, handle player turns, and declare a winner appropriately.</p>
<p>Input Examples:</p>
<ul>
<li>Player X clicks on square 0: <code>['X', null, null, null, null, null, null, null, null]</code></li>
<li>Player O clicks on square 4: <code>['X', null, null, null, 'O', null, null, null, null]</code></li>
<li>Player X wins: <code>['X', null, null, null, 'O', null, 'X', null, null]</code></li>
</ul>
<p>Expected Output Examples:</p>
<ul>
<li>Display <strong>&#8220;Next Player: X&#8221;</strong> when it&#8217;s Player X&#8217;s turn.</li>
<li>Display <strong>&#8220;Next Player: O&#8221;</strong> when it&#8217;s Player O&#8217;s turn.</li>
<li>Display <strong>&#8220;Winner: X&#8221;</strong> when Player X wins.</li>
</ul>
<p>This game requires understanding React state management to track the game board and current player, implementing game logic to determine the winner, and rendering the UI based on the game&#8217;s state.</p>


---

## 31. Top K Words

- Source Number: 31
- Slug: `top-k-words`
- Date: `2024-03-14T15:47:34`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Algorithmic
- Type: Coding

### Content

<p>Write a function <code>topKWords(log, k)</code> that analyzes a given log file content and identifies the top K most frequently occurring words within it. The function should return an array containing these top K words, sorted by their frequency of occurrence in descending order.</p>
<p>For instance, given a log:</p>
<pre><code>
May 12, 2023: User1 logged in.
May 13, 2023: User2 logged in.
May 13, 2023: User1 performed an action.
May 14, 2023: User3 logged in.
May 15, 2023: User2 performed an action.
May 15, 2023: User1 logged out.
</code></pre>
<p>And a value of K = 3, the function <code>topKWords(log, 3)</code> should return:</p>
<pre><code>['User1', 'logged', 'May']</code></pre>
<p>This output represents the top 3 most frequently occurring words in the log, which are &#8216;User1&#8217;, &#8216;logged&#8217;, and &#8216;May&#8217; in this example.</p>
<p>The function should process the log content to count word occurrences, then sort and return the most frequent words up to the specified limit of K.</p>


---

## 32. Image Slider

- Source Number: 32
- Slug: `image-slider`
- Date: `2024-03-16T21:50:42`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-376" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.02.18-PM-300x147.png" alt="" width="300" height="147" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.02.18-PM-300x147.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.02.18-PM.png 644w" sizes="(max-width: 300px) 100vw, 300px" /></p>
<p>Create a simple image slider component in React to display a set of product images fetched from an API. The slider should enable users to navigate through the images using &#8220;Next&#8221; and &#8220;Previous&#8221; buttons, allowing for smooth transitions between them.</p>
<p><strong>Input Examples:</strong></p>
<ul>
<li>Initial render with fetched product images.</li>
<li>Clicking the &#8220;Next&#8221; button to move to the next image.</li>
<li>Clicking the &#8220;Previous&#8221; button to move to the previous image.</li>
</ul>
<p><strong>Expected Output Examples:</strong></p>
<ul>
<li>Display a set of product images in a slider format.</li>
<li>Transition smoothly to the next image when clicking &#8220;Next&#8221;.</li>
<li>Transition smoothly to the previous image when clicking &#8220;Previous&#8221;.</li>
</ul>
<p>The implementation should handle fetching product images from an external API, managing the current image index, and enabling smooth transitions between images within the React application.</p>


---

## 33. Virtual DOM I

- Source Number: 33
- Slug: `virtual-dom-i`
- Date: `2024-03-14T23:46:38`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/lE0CE2N3oUg
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p>Explore the concept of serializing and deserializing a DOM tree using JSON, similar to how React represents elements and their properties. This approach offers an alternative to traditional HTML string serialization, providing a structured and easily manipulable format for representing the DOM structure.</p>
<p>Consider the following example of a DOM tree:</p>
<pre><code>&lt;div id="root"&gt;
   &lt;h1&gt;
     this is
   &lt;/h1&gt;
   &lt;p class="paragraph"&gt;
     a
     &lt;button&gt;
       button
     &lt;/button&gt;
     from
     &lt;a href="https://frontendlead.com"&gt;
       &lt;b&gt;frontendlead&lt;/b&gt;
       .com
     &lt;/a&gt;
   &lt;/p&gt;
&lt;/div&gt;</code></pre>
<p>The object representation of this DOM tree might look like:</p>
<pre><code>{
  type: 'div',
  props: {
    children: [{
      type: 'h1',
      props: {
        children: ' this is '
      }
    }, {
      type: 'p',
      props: {
        className: 'paragraph',
        children: [' a ', {
          type: 'button',
          props: {
            children: ' button '
          }
        }, ' from ', {
          type: 'a',
          props: {
            href: 'https://frontendlead.com',
            children: [{
              type: 'b',
              props: {
                children: 'frontendlead'
              }
            }, '.com']
          }
        }]
      }
    }]
  }
}</code></pre>
<p>Your task is to implement two functions:</p>
<ul>
<li><strong>virtualize():</strong> Converts a real DOM tree into its JSON representation.</li>
<li><strong>render():</strong> Recreates the real DOM tree from its JSON representation.</li>
</ul>
<p>Focus on basic HTML tags and properties, excluding complex functionalities like event handlers and custom components. The ability to handle text nodes, single or multiple children, and camelCased properties in your implementation is essential.</p>
<p>This challenge not only tests your understanding of DOM manipulation and JavaScript object handling but also offers insight into virtual DOM concepts used in frameworks like React.</p>


---

## 34. Virtual DOM II

- Source Number: 34
- Slug: `virtual-dom-ii`
- Date: `2024-03-15T00:02:11`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/5DIxFGFG1e4
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p>Building on the concept of Virtual DOM introduced in Virtual DOM I, this challenge involves transforming a virtualized JSON representation of a DOM tree back into a valid DOM structure. The process should accurately recreate the DOM elements, including their attributes and nested structure, from the virtual representation.</p>
<p>Given a virtual DOM representation like:</p>
<pre><code>{
  "type": "div",
  "props": {
    "children": [{
      "type": "h1",
      "props": {
        "children": "this is"
      }
    }, {
      "type": "p",
      "props": {
        "className": "paragraph",
        "children": ["a ", {
          "type": "button",
          "props": {
            "children": "button"
          }
        }, " from", {
          "type": "a",
          "props": {
            "href": "https://frontendlead.com",
            "children": [{
              "type": "b",
              "props": {
                "children": "frontendlead"
              }
            }, ".com"]
          }
        }]
      }
    }]
  }
}</code></pre>
<p>Your task is to implement a function <code>render()</code> that takes this object literal representation of a DOM tree and recreates the corresponding real DOM tree, as shown below:</p>
<pre><code>&lt;div id="root"&gt;
   &lt;h1&gt;
     this is
   &lt;/h1&gt;
   &lt;p class="paragraph"&gt;
     a
     &lt;button&gt;
       button
     &lt;/button&gt;
     from
     &lt;a href="https://frontendlead.com"&gt;
       &lt;b&gt;frontendlead&lt;/b&gt;
       .com
     &lt;/a&gt;
   &lt;/p&gt;
&lt;/div&gt;</code></pre>
<p>The function should support basic HTML tags and properties, including the handling of text nodes, single or multiple children, and camelCased properties like <code>className</code>.</p>
<p>This challenge tests your understanding of DOM manipulation, recursion, and the concept of a virtual DOM, highlighting the algorithmic approach to rendering web interfaces.</p>


---

## 35. Virtual DOM III

- Source Number: 35
- Slug: `virtual-dom-iii`
- Date: `2024-03-15T00:27:23`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/pIpYNP_lIv0
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p>Build a JSX-like compiler that transforms a given string representing HTML code into a JavaScript object representation. The compiler should parse the HTML-like string and extract the tag name, attributes (if any), and children content. Consider the following input string:</p>
<pre><code>&lt;a&gt;frontendlead.com&lt;/a&gt;</code></pre>
<p>The expected output for the above input should be:</p>
<pre><code>{
 "openingElement": {
  "name": "a"
 },
 "closingElement": {
  "name": "a"
 },
 "props": {
  "children": [
   "frontendlead.com"
  ]
 }
}</code></pre>
<p>The compiler must handle various cases, including strings with extra spaces, and ensure proper tag formatting. For instance, the following examples should be successfully parsed:</p>
<ul>
<li><code>&lt;a&gt;bfe.dev&lt;/a&gt;</code></li>
<li><code>&lt; a &gt; bfe.dev &lt; / a &gt;</code></li>
</ul>
<p>However, certain inputs should trigger parsing errors, such as:</p>
<ul>
<li>Incorrect tag formats like <code>'2a&gt;bfe.dev&lt;/a&gt;'</code> or <code>'&lt;a&gt;&lt;/b&gt;'</code></li>
<li>Strings that do not strictly follow the tag structure, e.g., <code>'&lt;a&gt;&gt;&lt;/a&gt;'</code>, <code>'&lt;a&gt;&lt;a&gt;'</code></li>
<li>Unmatched opening and closing tags or misplaced characters within tags</li>
</ul>
<p>This challenge aims to assess your ability to parse and transform string data, manage errors, and construct object representations, which are essential skills in front-end development and working with virtual DOM concepts.</p>


---

## 36. API Confirmation

- Source Number: 36
- Slug: `api-confirmation`
- Date: `2024-03-15T17:50:10`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/jVk5KQvCgQc?si=DudfjRtqvFcxHaMg
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google
- Category: Javascript
- Type: Coding

### Content

<p>You are provided with an array of API URLs, where the position of each URL in the array indicates the priority of its respective API. The task involves fetching these APIs concurrently and obtaining the result from the highest-priority API that returns a successful response. Should all the API calls result in failure, it&#8217;s essential to manage the rejection appropriately.</p>
<p>Consider the following example of API URLs:</p>
<ul>
<li><code>https://api.example.com/api1</code></li>
<li><code>https://api.example.com/api2</code></li>
<li><code>https://api.example.com/api3</code></li>
</ul>
<p>The objective is to execute these API requests in parallel and secure the result from the API with the highest priority (earliest in the array) that successfully responds. In scenarios where every API call is unsuccessful, the system must adeptly handle the collective failure.</p>


---

## 37. API Search and Render Image

- Source Number: 37
- Slug: `api-search-and-render-image`
- Date: `2024-03-16T22:24:43`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-02-at-5.10.24-PM-300x290.png" alt="" width="300" height="290" class="alignnone size-medium wp-image-383" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-02-at-5.10.24-PM-300x290.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-10-02-at-5.10.24-PM.png 532w" sizes="(max-width: 300px) 100vw, 300px" /></p>
<p>Develop a basic React user interface that accomplishes the following tasks:</p>
<ul>
<li>Fetches data from an external API.</li>
<li>Renders a header image using the first item from the API&#8217;s response.</li>
<li>Displays a list of results, each with a title and a button.</li>
<li>Includes a search input field to filter through the list items based on the title.</li>
<li>Allows users to update the main header image by clicking a button associated with each list item.</li>
</ul>
<p>This UI challenge focuses on implementing core React functionalities, including state management with <code>useState</code>, side effects with <code>useEffect</code>, componentization, and event handling. Styling is not a primary concern for this task, but the functionality to filter results and update the main image based on user interaction is crucial.</p>
<p><strong>Example Interaction:</strong></p>
<pre><code>1. Upon loading, the UI fetches data from the API and displays the first image as the main header image.
2. A list of titles is displayed below the header image, each with a corresponding "Click Me" button.
3. The user can type in the search field to filter the list of titles.
4. Clicking on a "Click Me" button next to a title updates the header image to that of the clicked item's image.</code></pre>
<p>This task assesses your ability to handle data fetching, state management, and dynamic rendering in React, which are essential skills for frontend development.</p>


---

## 38. Asynchronous Request Queue

- Source Number: 38
- Slug: `asynchronous-request-queue`
- Date: `2024-03-15T18:00:22`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/wOmQoeiZlQw?si=YHlqvUvege5x-FXe
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google, Robinhood
- Category: Javascript
- Type: Coding

### Content

<p>You are tasked with creating an asynchronous request queue in JavaScript. The primary objective is to ensure that each request in the queue is executed sequentially, adhering to the order in which they were added to the queue. The execution of a subsequent request should commence only after the completion of the preceding one. Your challenge involves developing a function named <code>requestQueue</code>, which accepts an array of request promises as input and returns a promise that resolves to an array containing the results of these requests, maintaining the sequence of their execution.</p>
<p>Consider the following example of requests:</p>
<pre><code>const requests = [ 
  fetch('https://api.example.com/data/1'), 
  fetch('https://api.example.com/data/2'), 
  fetch('https://api.example.com/data/3') 
];
</code></pre>
<p>The expected output should be an array containing the results of the requests, in the order they were executed:</p>
<pre><code>[
  // Result of the first request
  { /* data for request 1 */ },
  // Result of the second request
  { /* data for request 2 */ },
  // Result of the third request
  { /* data for request 3 */ }
]
</code></pre>
<p>The <code>requestQueue</code> function is crucial for scenarios where the order of request execution and completion is paramount, ensuring that each request is given due consideration in a sequential manner.</p>


---

## 39. Auto Suggest Search List

- Source Number: 39
- Slug: `auto-complete-search`
- Date: `2024-03-16T17:50:13`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: App Design
- Type: Vanilla

### Content

<article>
<section>
<p>Implement an autocomplete feature that enhances user experience by suggesting possible completions for a search term as it is being typed into an HTML input field. This functionality should dynamically filter and display a list of suggestions based on the current input value, offering keyboard navigation to select from the filtered results.</p>
</section>
<section>
<h2>Task Overview</h2>
<p>Your task is to write a JavaScript function that integrates with an HTML input field, monitoring the user&#8217;s input. As the user types, the function should interact with a predefined endpoint (simulated by an object in this case) that returns a list of potential matches. These matches should then be displayed as a list of suggestions beneath the input field, updating in real time with each keystroke to reflect the current query.</p>
</section>
<section>
<h2>Features and Behavior</h2>
<ul>
<li>The autocomplete should dynamically filter search results to include only items matching the current input, disregarding case sensitivity.</li>
<li>The displayed results should update as the user types, with each keystroke refining the list of suggestions.</li>
<li>Keyboard navigation (e.g., using the arrow keys) should allow the user to browse through the list of suggestions and select a result to fill in the search field.</li>
<li>Each suggestion in the list should be selectable, and clicking on a suggestion or pressing &#8216;Enter&#8217; when highlighted should populate the input field with that value.</li>
</ul>
</section>
<section>
<h2>Example</h2>
<p>Consider an input field where a user starts typing &#8220;Al&#8221;. The autocomplete feature should filter the list of names to show only those that contain &#8220;Al&#8221;, such as &#8220;Alex&#8221; and &#8220;Aleksandra&#8221;, beneath the input field as selectable suggestions.</p>
</section>
</article>


---

## 40. Autocomplete Search List

- Source Number: 40
- Slug: `autocomplete-search-list`
- Date: `2024-03-16T19:55:52`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: N/A
- Category: App Design
- Type: Vanilla

### Content

<p><img loading="lazy" decoding="async" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-08-20-at-5.38.01-PM-283x300.png" alt="" width="283" height="300" class="alignnone size-medium wp-image-340" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-08-20-at-5.38.01-PM-283x300.png 283w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screen-Shot-2023-08-20-at-5.38.01-PM.png 477w" sizes="(max-width: 283px) 100vw, 283px" /></p>
<p>Develop an autocomplete search suggestion feature that dynamically displays search suggestions to users as they type in a search query. This feature fetches search results from an API endpoint and displays them as suggestions in real-time. Selected results are displayed separately, enhancing user experience and interaction.</p>
<p>The functionality is akin to what you might find in popular search engines, where suggestions appear as you type, based on the current input. This not only makes the search process more efficient but also provides users with a glimpse of what information is available even before they complete typing their query.</p>
<p><strong>Input Examples:</strong></p>
<ul>
<li>User types: &#8220;ph&#8221; <br />Expected Output: Display a list of search suggestions related to &#8220;phone.&#8221;</li>
<li>User types: &#8220;lap&#8221; <br />Expected Output: Display a list of search suggestions related to &#8220;laptop.&#8221;</li>
<li>User types: &#8220;app&#8221; <br />Expected Output: Display a list of search suggestions related to &#8220;apparel.&#8221;</li>
</ul>
<p>This task involves handling user input in real-time, querying an API for search results based on this input, and then displaying these results as clickable suggestions. When a user selects a suggestion, it should be displayed separately to indicate selection.</p>
<p>Please use <code>https://dummyjson.com/products/search?q=yourkeyword</code> endpoint to fetch results</p>
<p>The completion of this feature involves understanding and handling asynchronous operations, DOM manipulation, and event handling in JavaScript. It is a practical and commonly implemented feature in many web applications, making it an essential skill for frontend developers.</p>


---

## 41. ClearAllIntervals()

- Source Number: 41
- Slug: `clearallintervals`
- Date: `2024-03-15T16:56:24`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Imagine you&#8217;re working with JavaScript&#8217;s <code>window.setInterval()</code> function, which is commonly used to schedule tasks for future execution. Your challenge is to not only utilize <code>setInterval</code> effectively but also to create a function named <code>clearAllIntervals()</code>. This function should be capable of clearing all active interval timers, proving especially useful for cleaning up pending tasks before a page transition.</p>
<p>Consider the scenario where multiple functions are scheduled to execute after a delay, as illustrated in the example below:</p>
<pre><code>setInterval(func1, 10000); 
setInterval(func2, 10000); 
setInterval(func3, 10000); // All three functions are scheduled for execution after a 10-second delay</code></pre>
<p>The task is to implement the <code>clearAllIntervals()</code> function such that calling it cancels all previously scheduled tasks:</p>
<pre><code>clearAllIntervals(); // Cancels all scheduled tasks</code></pre>
<p>This challenge tests your ability to manipulate and work with timers in a frontend environment effectively. You are required to maintain the interface of <code>window.setInterval</code> and <code>window.clearInterval</code> but are allowed to augment their underlying logic to incorporate the functionality of <code>clearAllIntervals()</code>.</p>
<p>This task not only assesses your proficiency with JavaScript timers but also your capacity to design clean and efficient solutions for managing asynchronous tasks in web applications.</p>


---

## 42. ClearAllTimeouts()

- Source Number: 42
- Slug: `clearalltimeouts`
- Date: `2024-03-15T16:46:25`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Imagine you&#8217;re tasked with scheduling tasks for future execution in a frontend environment, utilizing the <code>window.setTimeout()</code> function. Your challenge doesn&#8217;t stop there; you must also create a function named <code>clearAllTimeout()</code>. This function should be capable of clearing all active timers, ensuring a clean slate of pending tasks, particularly useful during page transitions.</p>
<p>Consider the scenario where you&#8217;ve scheduled multiple functions for execution after a 10-second delay:</p>
<pre><code>setTimeout(func1, 10000);
setTimeout(func2, 10000);
setTimeout(func3, 10000); // All three functions are set to execute after 10 seconds.</code></pre>
<p>The requirement is to halt all these scheduled tasks with a single call to <code>clearAllTimeout()</code>:</p>
<pre><code>clearAllTimeout(); // This call should cancel all previously scheduled tasks.</code></pre>
<p>Your solution must adhere to the existing interface of <code>window.setTimeout</code> and <code>window.clearTimeout</code>, but you are encouraged to redefine their underlying implementations. This exercise will test your ability to manipulate timers efficiently in a frontend development context, showcasing your skills in managing asynchronous tasks.</p>
<p>Through this challenge, you&#8217;ll demonstrate not only your proficiency in using JavaScript timers but also your innovative approach to enhancing and controlling their behavior to suit specific application needs.</p>


---

## 43. Compose Function

- Source Number: 43
- Slug: `compose-function`
- Date: `2024-03-12T15:23:58`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Algorithmic
- Type: Coding

### Content

<p>You are tasked with implementing a <code>compose</code> function that combines multiple single-argument functions into a single function. This composite function should apply the given functions in sequence to an initial value, transforming it step by step.</p>
<p>Given three functions <code>a</code>, <code>b</code>, and <code>c</code>, each performing a distinct mathematical operation on an input value, your <code>compose</code> function should enable these functions to be applied in the order they are provided.</p>
<p><strong>Example:</strong></p>
<ul>
<li>Function <code>a</code>: Multiplies the input by 4.</li>
<li>Function <code>b</code>: Adds 4 to the input.</li>
<li>Function <code>c</code>: Subtracts 1 from the input.</li>
</ul>
<p>Starting with an initial value of 5, the <code>compose</code> function should return the final result after sequentially applying these functions. Therefore, <code>compose(a, b, c)(5)</code> should yield 23, following these steps:</p>
<ol>
<li>Apply <code>a</code> to 5: <code>a(5) = 5 * 4 = 20</code></li>
<li>Apply <code>b</code> to 20: <code>b(20) = 20 + 4 = 24</code></li>
<li>Apply <code>c</code> to 24: <code>c(24) = 24 - 1 = 23</code></li>
</ol>
<p>This example illustrates the transformation process, demonstrating how each function modifies the value passed through the composition.</p>
<p>Your implementation should allow for any number of functions to be composed, providing a flexible and powerful tool for function chaining and value transformation.</p>


---

## 44. Curry Function

- Source Number: 44
- Slug: `curry-function`
- Date: `2024-03-12T15:10:48`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Coding

### Content

<p>The goal is to implement a <code>curry</code> function in JavaScript that allows a function to be called with arguments one at a time until all arguments have been provided, after which the original function is executed with all of the accumulated arguments. This technique is particularly useful in functional programming where functions are treated as first-class citizens and can be composed or chained together.</p>
<p>The <code>curry</code> function takes a callback as an argument and returns a new function. This new function can be called multiple times, each with a single argument, until no arguments are provided, at which point the original callback function is executed with all of the previously provided arguments.</p>
<p>Usage Example:</p>
<pre><code>const curriedSum = curry((a, b, c) => a + b + c);
console.log(curriedSum(1)(2)(3)()); // Outputs: 6</code></pre>
<p>This example defines a <code>curriedSum</code> function that adds three numbers together. The <code>curry</code> function enables <code>curriedSum</code> to be called with one argument at a time, and finally, an empty call triggers the execution of the sum operation with all the provided arguments.</p>
<p>This approach offers flexibility in how functions receive their arguments, enabling more dynamic and functional programming patterns.</p>


---

## 45. Custom “this” Methods

- Source Number: 45
- Slug: `this-methods`
- Date: `2024-03-12T01:24:51`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Robinhood, Zillow, Airbnb, OpenAI, Microsoft, Netflix, Apple, LinkedIn, Stripe, ClickUp, PayPal, Snap, Vimeo, Adobe, TikTok, Atlassian
- Category: Array
- Type: Coding

### Content

<p>You are tasked with creating custom implementations of three essential methods found in the Function prototype: <code>myCall</code>, <code>myApply</code>, and <code>myBind</code>. These methods are designed to emulate the functionality of JavaScript&#8217;s native <code>Function.prototype.call</code>, <code>Function.prototype.apply</code>, and <code>Function.prototype.bind</code> methods, respectively. This challenge provides a deep dive into handling function context (`this`) and arguments in JavaScript, which is crucial for function execution and object-oriented programming.</p>
<p>The <code>myCall</code> method should enable a function to be invoked with a specified `this` context and individual arguments, mirroring the behavior of <code>Function.prototype.call</code>. The <code>myApply</code> method, on the other hand, should allow a function to be called with an array of arguments, akin to <code>Function.prototype.apply</code>. Finally, the <code>myBind</code> method is expected to return a new function that, when called at a later time, will have its `this` context and initial arguments preset, resembling <code>Function.prototype.bind</code>.</p>
<p>Implementing these custom methods not only showcases the flexibility and dynamism of JavaScript but also serves as a valuable exercise in understanding the core mechanics of function execution and context binding. By crafting <code>myCall</code>, <code>myApply</code>, and <code>myBind</code> from the ground up, you will gain a deeper insight into these fundamental aspects of JavaScript and enhance your problem-solving skills for various programming challenges.</p>


---

## 46. Debounce II

- Source Number: 46
- Slug: `debounce-ii`
- Date: `2024-03-12T00:22:04`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google
- Category: Javascript
- Type: Coding

### Content

<p>Implement a JavaScript utility called <code>debounce</code> that enhances the control over function executions in response to rapid or repeated triggers. This utility should accept two parameters: a target function (<code>func</code>) and a wait time in milliseconds (<code>wait</code>). The <code>debounce</code> function returns a new, debounced version of the target function that ensures it is only executed after the specified wait time has elapsed since its last invocation.</p>
<p>If the debounced function is called again before the wait time has expired, the countdown is reset, delaying the function&#8217;s execution until the wait time passes without any further invocations. This behavior is crucial in scenarios such as handling rapid user inputs, window resizing, or scroll events, where controlling the rate of function execution can significantly enhance performance and user experience.</p>
<p>In addition to the basic debouncing behavior, the returned function includes two methods for added flexibility:</p>
<ul>
<li><strong>cancel():</strong> Cancels any scheduled execution of the debounced function, effectively resetting the debounce mechanism.</li>
<li><strong>flush():</strong> Immediately invokes the debounced function if there is a scheduled execution pending, bypassing the wait time.</li>
</ul>
<p>This advanced debouncing mechanism, with its <code>cancel</code> and <code>flush</code> capabilities, provides a powerful tool for optimizing dynamic function execution in response to user actions or system events.</p>


---

## 47. Debounce III

- Source Number: 47
- Slug: `debounce-iii`
- Date: `2024-03-12T00:52:18`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google, Microsoft
- Category: Javascript
- Type: Coding

### Content

<p>The goal is to implement an advanced version of the <code>debounce()</code> function in JavaScript, which introduces an <code>options</code> parameter. This parameter contains two properties: <code>leading</code> and <code>trailing</code>, both of which are boolean flags.</p>
<p>The <code>leading</code> flag determines if the debounced function should execute immediately on the first call. When <code>true</code>, the function triggers right away; otherwise, it waits for the specified delay. The <code>trailing</code> flag, on the other hand, controls the execution of the function after the delay. If <code>true</code>, the function executes after the delay; if <code>false</code>, it does not.</p>
<p>By default, the debounce function behaves traditionally, with <code>{leading: false, trailing: true}</code>. This task involves creating a debounce mechanism that adapts to these options, providing flexibility in function execution timing. This adaptation is crucial for optimizing event handling and response strategies in various scenarios.</p>
<p><strong>Example:</strong> Consider a sequence of function calls with corresponding delays. The enhanced debounced function should execute these calls based on the configured <code>leading</code> and <code>trailing</code> options, potentially reducing the number of invocations for efficiency.</p>
<p>Note: In testing environments, especially browsers, the accuracy of <code>setTimeout()</code> and <code>clearTimeout()</code> might not be reliable. Thus, alternative implementations should be considered for evaluating the debounced function&#8217;s behavior.</p>


---

## 48. Deep Equals

- Source Number: 48
- Slug: `deep-equals-comparison`
- Date: `2024-03-12T00:00:47`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/PUmNzgIhdPA
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Array
- Type: Coding

### Content

<p>Implement a <code>deepEquals</code> function capable of comparing two inputs, which can vary widely in type and structure, including null, undefined, objects, arrays, NaN, and primitives (such as numbers, strings, and booleans). The function should accurately determine whether the two inputs are deeply equal, meaning they are structurally identical and contain the same values at every level of nesting.</p>
<p>The challenge lies in handling the nuanced differences between JavaScript data types and their comparisons. For instance:</p>
<ul>
<li>Comparing <code>NaN</code> values, which by default are not equal to themselves.</li>
<li>Distinguishing between different types of falsy values, such as <code>null</code> and <code>undefined</code>.</li>
<li>Ensuring that arrays and objects are compared recursively, delving into each element or property to verify equality.</li>
<li>Correctly handling primitive data types, ensuring strict equality.</li>
</ul>
<p>Examples of expected behavior:</p>
<pre><code>deepEquals(NaN, NaN) // true
deepEquals([1, 2, [3]], [1, 2, [3]]) // true
deepEquals({ a: 1, b: { c: 2 } }, { a: 1, b: { c: 2 } }) // true
deepEquals(null, undefined) // false
deepEquals([1, 2, 3], { 0: 1, 1: 2, 2: 3 }) // false</code></pre>
<p>This function is not only a powerful tool for JavaScript developers to accurately compare complex structures but also serves as an excellent exercise in understanding JavaScript&#8217;s type coercion and equality comparisons.</p>


---

## 49. Event Emitter II

- Source Number: 49
- Slug: `advanced-event-emitter-implementation-javascript`
- Date: `2024-03-12T01:21:40`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Coding

### Content

<p>Implement an <code>EventEmitter</code> class in JavaScript that allows for subscribing to events, emitting events, and unsubscribing from events. This problem is categorized as medium difficulty and is commonly encountered in interviews for companies like Meta. Understanding event handling and the observer pattern is crucial for frontend developers, making this challenge both relevant and instructive.</p>
<p>The <code>EventEmitter</code> class should have the following functionalities:</p>
<ul>
<li><strong>on(name, callback):</strong> Registers an event listener for the specified event <code>name</code>. This method should return an object with an <code>off</code> method, which when called, removes the listener.</li>
<li><strong>emit(name, &#8230;args):</strong> Triggers the specified event <code>name</code> and calls all the registered callbacks with the provided arguments.</li>
</ul>
<p>Your implementation should allow for the dynamic addition and removal of event listeners, ensuring that event callbacks are executed in the order they were added. The <code>emit</code> method should return <code>true</code> if the event has listeners and was successfully emitted, or <code>false</code> otherwise.</p>
<p>Example usage:</p>
<pre><code>const emitter = new EventEmitter();
var sum = 0;
function addTwoNumbers(a, b) {
  sum = a + b;
}
const sub = emitter.on('foo', addTwoNumbers);
emitter.emit('foo', 2, 5); // Triggers addTwoNumbers, expecting sum = 7
console.log(sum); // Output: 7

sub.off(); // Unsubscribe the addTwoNumbers listener from 'foo' event
emitter.emit('foo', -3, 9); // Since addTwoNumbers is unsubscribed, sum remains unchanged
console.log(sum); // Output: 7</code></pre>
<p>This task assesses your ability to work with classes, callbacks, and advanced JavaScript concepts such as closures and the observer pattern. Successfully implementing an <code>EventEmitter</code> demonstrates a deep understanding of event-driven programming, a key aspect of many JavaScript applications.</p>


---

## 50. Event Logger I

- Source Number: 50
- Slug: `event-logger-i`
- Date: `2024-03-15T18:16:57`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Robinhood
- Category: Javascript
- Type: Coding

### Content

<p>You are tasked with developing a part of an Event Logger system, specifically focusing on the feature that sends requests and logs events with a configurable delay. The goal is to simulate the behavior of sending requests to a server and logging the events, including the time elapsed since the initialization of the logger. The system should allow for a delay in logging to mimic network latency or processing time, and it should also provide functionality to abort a logging request.</p>
<p>The requirements for this part of the Event Logger system are as follows:</p>
<ul>
<li>Initialize a start time that serves as a reference point for calculating the elapsed time for each event logged.</li>
<li>Provide a function to set a delay for the logging of events, simulating network latency or processing time.</li>
<li>Include a function to reset the delay to zero, effectively removing any simulated latency.</li>
<li>Implement a function to send logging requests. Each request should log the event with the specified delay, and include the elapsed time since the logger&#8217;s initialization.</li>
<li>Equip each logging request with the capability to be aborted, in which case the event should be logged immediately with an &#8220;[ABORTED]&#8221; tag.</li>
</ul>
<p>Example usage:</p>
<pre><code>// Initialize the logger
_initializeStartTime();

// Set a simulated delay of 500ms for logging events
_setFetchResponseDelay(500);

// Send a logging request
const logRequest = sendRequest({ event: 'UserLogin', details: 'User logged in successfully' });

// Optionally, the logging request can be aborted
// logRequest.abort();
</code></pre>
<p>The expected output should include the logged events with their respective elapsed times and indicate whether they were aborted.</p>


---

## 51. Event Logger II

- Source Number: 51
- Slug: `event-logger-ii`
- Date: `2024-03-15T19:02:45`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Robinhood
- Category: Javascript
- Type: Vanilla

### Content

<p>In this continuation of the Event Logger series, your task is to enhance the Event Logger system by integrating it with a user interface that generates events based on user interactions. Specifically, you&#8217;ll work with a grid of colored squares. Each time a square is clicked, an event should be logged, capturing essential details such as the event name, timestamp, and the color of the clicked square.</p>
<p>The core functionality should be encapsulated within an <code>EventLogger</code> class. This class is responsible for batching events and sending them off at specified intervals, rather than sending each event immediately. This approach is crucial for optimizing performance and reducing network load, especially in scenarios with frequent user interactions.</p>
<p>The requirements for &#8220;Event Logger II&#8221; include:</p>
<ul>
<li>Implement an <code>EventLogger</code> class that batches events and sends them at defined intervals.</li>
<li>Each square in the provided grid should be clickable, with each click generating a loggable event.</li>
<li>The logged event should include details such as the event name (e.g., &#8220;click&#8221;), the timestamp of the interaction, and the color of the square that was clicked.</li>
<li>The <code>EventLogger</code> should temporarily store events in a queue and only send them once the batch interval has elapsed, ensuring that events are sent in batches rather than individually.</li>
</ul>
<p>Example HTML structure for the grid of squares:</p>
<pre><code>&lt;div id="grid"&gt;
  &lt;div class="square" style="background-color: #ff5000;"&gt;&lt;/div&gt;
  &lt;!-- Additional squares follow --&gt;
&lt;/div&gt;
</code></pre>
<p>Through &#8220;Event Logger II,&#8221; you&#8217;ll demonstrate the ability to handle user-generated events in a performant manner, leveraging batch processing to efficiently log and send event data.</p>


---

## 52. File Navigation

- Source Number: 52
- Slug: `file-navigation-react`
- Date: `2024-03-16T21:29:20`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Atlassian
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-2.34.32-PM-262x300.png" alt="" width="262" height="300" class="alignnone size-medium wp-image-363" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-2.34.32-PM-262x300.png 262w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-2.34.32-PM.png 632w" sizes="(max-width: 262px) 100vw, 262px" /></p>
<p>In this React-based problem, we are tasked with managing a nested directory structure where each directory can be either opened to reveal its subdirectories or closed to hide them. Additionally, users must be able to add new files to any directory within this structure.</p>
<p>The core functionalities required for this application include:</p>
<ul>
<li>Being able to toggle a directory&#8217;s state between open and closed, thereby controlling the visibility of its subdirectories.</li>
<li>Adding new files to directories. Each new file should be displayed in the directory&#8217;s list of files once added.</li>
</ul>
<p>To illustrate, consider the following scenarios:</p>
<table>
<thead>
<tr>
<th>Action</th>
<th>Expected Outcome</th>
</tr>
</thead>
<tbody>
<tr>
<td>Closing a directory</td>
<td>Its subdirectories should be hidden.</td>
</tr>
<tr>
<td>Opening a directory</td>
<td>Its subdirectories should be revealed.</td>
</tr>
<tr>
<td>Adding a new file to a directory</td>
<td>The file should appear in the directory&#8217;s list of files.</td>
</tr>
</tbody>
</table>
<p>This challenge involves a combination of state management, event handling, and dynamic rendering in React, making it a comprehensive task for testing one&#8217;s understanding of React fundamentals, especially in the context of handling complex, nested structures.</p>


---

## 53. Gym Sessions

- Source Number: 53
- Slug: `gym-sessions`
- Date: `2024-03-08T23:27:06`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: JSON
- Type: Coding

### Content

<p>You are tasked with developing a function capable of selecting and filtering gym session data based on specific options. Each session is detailed within an array of objects, highlighting the user, duration of the exercise, and the equipment utilized. A crucial feature of this function is its ability to consolidate sessions by the same user, thereby amalgamating their total exercise duration and equipment used.</p>
<p><strong>Input:</strong></p>
<ul>
<li><code>sessions</code>: An array of session objects, each containing <code>user</code>, <code>duration</code>, and <code>equipment</code> properties.</li>
<li><code>options</code>: An object hosting filtering and merging preferences.</li>
</ul>
<p><strong>Output:</strong></p>
<p>An array of session objects tailored according to the specified options, inclusive of user-merged data if indicated.</p>
<p><strong>Example:</strong></p>
<pre><code>const input = [
  { user: 'User1', duration: 30, equipment: ['treadmill'] },
  { user: 'User2', duration: 45, equipment: ['bike', 'dumbbell'] },
  // additional session objects
];
const options = { merge: true, equipment: ['bike'] };
const selectedSessions = selectData(input, options);
console.log(selectedSessions);
// Output might resemble:
// [
// { user: 'User2', duration: 45, equipment: ['bike', 'dumbbell'] }
// ]
</code></pre>
<p>This function not only demands adeptness in data filtering based on criteria but also challenges you to thoughtfully combine data from multiple entries pertaining to the same individual, ensuring a seamless and informative summary of gym sessions.</p>


---

## 54. Flatten III

- Source Number: 54
- Slug: `flatten-nested-objects-with-prefixes-javascript`
- Date: `2024-03-08T20:40:17`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Robinhood, Stripe, Snap
- Category: Objects
- Type: Coding

### Content

<h2>Flatten with Prefix</h2>
<p>You are tasked with creating a function, <code>flattenWithPrefix</code>, that flattens a nested object. The challenge lies in ensuring that as the object is flattened, the keys in the resulting object are prefixed with their parent keys, joined by periods (&#8216;.&#8217;). This means that for every level of nesting within the original object, its key is concatenated with its parent key(s), creating a clear hierarchical representation of the original nested structure in the flattened object.</p>
<p>This problem presents a common scenario in data manipulation, where nested structures need to be simplified for easier processing or storage, while still retaining a trace of their original hierarchical organization. Such a function can be particularly useful when dealing with configurations, translations, or any data that is naturally hierarchical but needs to be flattened for practical reasons.</p>
<p><strong>Example Usage:</strong></p>
<pre><code>Input: { a: { b: { c: 1 }, d: 2 } }
Output: { "a.b.c": 1, "a.d": 2 }

Input: { x: { y: 10, z: { w: 20 } } }
Output: { "x.y": 10, "x.z.w": 20 }
</code></pre>
<p>In these examples, notice how each key in the output object is a string that represents the path to the corresponding value in the input object. The function essentially transforms the nested object into a &#8216;flat&#8217; object where each key-value pair is accessible at the top level, with keys indicating the original nested structure.</p>
<p>Your implementation of <code>flattenWithPrefix</code> should work for objects of arbitrary depth and complexity, handling all the quirks of object iteration in JavaScript, such as inherited properties. The focus is not just on achieving the task but on writing clean, efficient, and maintainable code that could be integrated into larger codebases.</p>


---

## 55. Flatten IV

- Source Number: 55
- Slug: `flatten-nested-objects`
- Date: `2024-03-10T23:40:24`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/uOtTZqTtOMI
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Netflix, LinkedIn, ClickUp, TikTok
- Category: Objects
- Type: Coding

### Content

<p>Write a function to flatten a multi-dimensional object into a single-level object. The function should take an object as input and return a new object where all nested objects are flattened, retaining their key-value pairs at the top level. Each key in the output object should be unique, and the corresponding value should reflect the nested structure of the input object. This task involves recursively exploring each property within the object and aggregating all properties at the root level. Consider the following examples to better understand the expected behavior:</p>
<ul>
<li><strong>Input:</strong> <code>{ a: 1, b: { c: 2, d: 3, e: { f: null } }, g: 4, h: undefined }</code><br />
    <strong>Output:</strong> <code>{ a: 1, c: 2, d: 3, f: null, g: 4, h: undefined }</code></li>
<li><strong>Input:</strong> <code>{ a: { b: { c: 1 }, d: { e: 2, f: 3 } } }</code><br />
    <strong>Output:</strong> <code>{ c: 1, e: 2, f: 3 }</code></li>
<li><strong>Input:</strong> <code>{ a: { b: { c: { d: { e: 1 } } } } }</code><br />
    <strong>Output:</strong> <code>{ e: 1 }</code></li>
</ul>
<p>The function must ensure that if a key has a value of <code>null</code> or <code>undefined</code>, it should still be included in the output object. This challenge tests your ability to manipulate object properties and recursively process nested structures, which is a common task in handling JSON data and configuring component states in frontend development.</p>


---

## 56. Flatten V

- Source Number: 56
- Slug: `flatten-nested-objects-2`
- Date: `2024-03-10T23:53:38`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Microsoft, Netflix, LinkedIn, Snap
- Category: Objects
- Type: Coding

### Content

<p>Developing a frontend application often involves dealing with complex data structures, particularly when displaying hierarchical lists of items where each item can potentially have children, forming a nested structure. However, for certain UI components or data processing tasks, a flat list representation of these items, preserving their inherent relationships, is more desirable.</p>
<p>Your challenge is to implement a function that accepts a nested structure of items as input and returns a flattened array of objects. Each object in the output array should represent an item from the nested structure, stripped of its nesting but retaining the original order of items.</p>
<p>Consider the following input examples to understand the expected behavior:</p>
<ul>
<li><strong>Input Example 1:</strong></li>
</ul>
<pre><code>const input1 = [
  {
    "value": "value0",
    "children": []
  },
  // ... other items ...
];</code></pre>
<ul>
<li><strong>Expected Output for Example 1:</strong></li>
</ul>
<pre><code>const output1 = [
  { "value": "value0" },
  // ... other items ...
];</code></pre>
<ul>
<li><strong>Input Example 2:</strong></li>
</ul>
<pre><code>const input2 = [
  {
    "value": "value1",
    "children": [
      {
        "value": "value2",
        "children": [
          {
            "value": "value3",
            "children": []
          }
        ]
      },
      {
        "value": "value4",
        "children": []
      }
    ]
  },
  // ... other items ...
];</code></pre>
<ul>
<li><strong>Expected Output for Example 2:</strong></li>
</ul>
<pre><code>const output2 = [
  { "value": "value1" },
  { "value": "value2" },
  { "value": "value3" },
  { "value": "value4" },
  // ... other items ...
];</code></pre>
<p>This task assesses your ability to manipulate complex data structures and simplify them for practical usage in frontend applications. Successfully implementing this function will enhance your skills in data manipulation, recursion (if applicable), and algorithmic thinking.</p>


---

## 57. Flatten VI

- Source Number: 57
- Slug: `flatten-vi`
- Date: `2024-03-11T16:33:02`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Atlassian
- Category: Array
- Type: Coding

### Content

<p>Given a nested JSON structure, the task is to create two utility functions and one primary function to efficiently process and flatten the structure asynchronously. The functions to be implemented are:</p>
<ol>
<li><strong>getBatch:</strong> This function asynchronously retrieves an item from the input array based on a specified index. It returns a Promise that resolves to the item, facilitating asynchronous item processing. This is particularly useful for handling large datasets without impeding the execution flow.</li>
<li><strong>getValueList:</strong> An asynchronous function that utilizes <code>getBatch</code> to fetch items within a specified range (fromIndex to toIndex). It aims to flatten these items into a single-level array of values while preserving the original order found in the nested structure.</li>
</ol>
<p>The primary challenge lies in the efficient management of asynchronous operations coupled with the maintenance of the correct order of values in the flattened structure.</p>
<p><strong>Example Use Case:</strong> Consider the following input structure, which represents a simplified hierarchical data model akin to a file system or a comment thread, where each item can contain children:</p>
<pre><code>[
  {
    "value": "value0",
    "children": []
  },
  {
    "value": "value1",
    "children": [
      {
        "value": "value2",
        "children": [
          {
            "value": "value3",
            "children": []
          }
        ]
      },
      {
        "value": "value4",
        "children": []
      }
    ]
  },
  {
    "value": "value5",
    "children": []
  },
  {
    "value": "value6",
    "children": []
  }
]</code></pre>
<p>The objective is to flatten this structure into a single-level array of values [<code>"value0", "value1", "value2", "value3", "value4", "value5", "value6"</code>], using asynchronous functions to fetch and process the data efficiently.</p>


---

## 58. Flatten VII

- Source Number: 58
- Slug: `flatten-vii`
- Date: `2024-03-11T17:09:14`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/Kt7V9-ls-38
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Airbnb, Netflix, Apple, Vimeo, Adobe
- Category: Array
- Type: Coding

### Content

<p>Write a function named <code>flatten</code> that is capable of taking an input which may be an arbitrarily nested object or array, and return a flattened version of it. In the flattened output, all elements from nested arrays should be in a single-level array, and all nested object properties should be brought to the top level of a single object.</p>
<p>The challenge involves creating a versatile function that can handle various types of nested structures, including combinations of arrays and objects, without losing any data in the process. The function should be able to distinguish between objects and arrays and treat them accordingly, ensuring that arrays are merged into a single array and object properties are collated into a single object.</p>
<p>Consider the following examples to understand the expected behavior of the function:</p>
<ul>
<li>Given an array like <code>[1, [2, 3], [[4, 5], 6]]</code>, the function should produce <code>[1, 2, 3, 4, 5, 6]</code>.</li>
<li>For an object such as <code>{ a: 1, b: { c: 2, d: { e: 3 } } }</code>, the expected output is <code>{ a: 1, c: 2, e: 3 }</code>.</li>
<li>When the input is a mix of arrays and objects like <code>[1, { a: 2, b: [3, 4] }, [5, { c: 6 }]]</code>, the function should return <code>[1, 2, 3, 4, 5, 6]</code>.</li>
<li>For deeply nested arrays such as <code>[[[[[[[[[[1]]]]]]]]]]</code>, the output should simply be <code>[1]</code>.</li>
<li>When the input is <code>null</code>, the function should return <code>null</code>.</li>
</ul>
<p>Your task is to implement the <code>flatten</code> function in such a way that it fulfills the above requirements, providing a simple and efficient solution to the problem of dealing with complex, nested data structures. This is a common challenge that developers face, making it a valuable exercise for enhancing your problem-solving skills and understanding of data manipulation.</p>


---

## 59. Flatten XI

- Source Number: 59
- Slug: `flatten-xi`
- Date: `2024-03-14T15:36:27`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Google
- Category: Algorithmic
- Type: Coding

### Content

<p>Write a function <code>flattenWithPrefix(obj, prefix)</code> that flattens a nested object into a single-level object. Each key in the resulting object should be a concatenation of the keys from the nested object, prefixed with the specified prefix. The function should handle arbitrary levels of nesting.</p>
<p>For example, given the input object:</p>
<pre><code>const input = { a: { b: { c: 1 }, d: 2 } };</code></pre>
<p>The expected output, with each key flattened and prefixed, would be:</p>
<pre><code>{ 'a.b.c': 1, 'a.d': 2 }</code></pre>
<p>The function should be able to traverse through the nested object, concatenating each key with its parent key(s) and the given prefix, to create a new, flattened object structure where each key represents the &#8220;path&#8221; to its value within the original nested object.</p>


---

## 60. getElementsByClassName

- Source Number: 60
- Slug: `getelementsbyclassname`
- Date: `2024-03-15T23:23:30`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38.png
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1613" src="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38.png" alt="Learn document.getElementsByClassname() HTML method" width="1920" height="1080" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38.png 1920w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38-300x169.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38-1024x576.png 1024w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38-768x432.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/FrontendLead-38-1536x864.png 1536w" sizes="(max-width: 1920px) 100vw, 1920px" /></p>
<p>Implement a function <code>getElementsByClassName</code> that mimics the behavior of the native DOM method <code>document.getElementsByClassName</code>. The function should search through a DOM tree starting from a specified root element and collect all elements that have the specified class name.</p>
<p>The function <code>getElementsByClassName(className, root)</code> takes two parameters: <code>className</code>, which is the name of the class to search for, and <code>root</code>, which is the root element of the DOM subtree in which to begin the search. If the root element is not provided, the search should not proceed.</p>
<p>The function should return an array of DOM elements that match the specified class name. If no elements are found, the function should return an empty array. The search should include the root element and should be performed depth-first, ensuring that all descendants of the root are considered.</p>
<p><strong>Example:</strong></p>
<pre><code>
// Assuming an HTML structure like:
// &lt;div class="container"&gt;
//   &lt;div class="item active"&gt;&lt;/div&gt;
//   &lt;div class="item"&gt;&lt;/div&gt;
//   &lt;div class="list"&gt;
//     &lt;div class="item active"&gt;&lt;/div&gt;
//   &lt;/div&gt;
// &lt;/div&gt;

const rootElement = document.querySelector('.container');
const itemsWithActiveClass = getElementsByClassName('active', rootElement);

// itemsWithActiveClass should contain the two '.item.active' divs
</code></pre>
<p>This task requires traversing the DOM tree and applying conditional logic to select elements based on their class name, which is a common requirement in many frontend development tasks. Implementing this function will deepen your understanding of DOM manipulation and element selection.</p>


---

## 61. Hierarchical Checkbox

- Source Number: 61
- Slug: `hierarchical-checkbox`
- Date: `2024-03-16T21:01:07`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Google
- Category: App Design
- Type: Vanilla

### Content

<p>Implement a JavaScript solution to manage checkboxes in a hierarchical structure, ensuring the following functionality:</p>
<ul>
<li>When a parent checkbox is checked, all its child checkboxes should also be checked.</li>
<li>When a parent checkbox is unchecked, all its child checkboxes should be unchecked.</li>
<li>If some, but not all, child checkboxes are checked, the parent checkbox should be in an indeterminate state.</li>
</ul>
<p>This problem presents a common scenario in user interfaces where options are nested within categories and subcategories, requiring a coherent and intuitive interaction pattern. The hierarchical structure of checkboxes can represent various real-world scenarios such as selecting features in a product, permissions in a software application, or categories in a content management system.</p>
<p>For example, consider the following HTML structure:</p>
<pre><code>&lt;h1&gt;Indeterminate Checkboxes&lt;/h1&gt;
&lt;ul&gt;
    &lt;li&gt;
        &lt;input type="checkbox" name="tall" id="tall"&gt;
        &lt;label for="tall"&gt;Tall Things&lt;/label&gt;
        &lt;ul&gt;
            &lt;li&gt;
                &lt;input type="checkbox" name="tall-1" id="tall-1"&gt;
                &lt;label for="tall-1"&gt;Buildings&lt;/label&gt;
            &lt;/li&gt;
            &lt;li&gt;
                &lt;input type="checkbox" name="tall-2" id="tall-2"&gt;
                &lt;label for="tall-2"&gt;Giants&lt;/label&gt;
                &lt;ul&gt;
                    &lt;li&gt;
                        &lt;input type="checkbox" name="tall-2-1" id="tall-2-1"&gt;
                        &lt;label for="tall-2-1"&gt;Andre&lt;/label&gt;
                    &lt;/li&gt;
                    &lt;li&gt;
                        &lt;input type="checkbox" name="tall-2-2" id="tall-2-2"&gt;
                        &lt;label for="tall-2-2"&gt;Paul Bunyan&lt;/label&gt;
                    &lt;/li&gt;
                &lt;/ul&gt;
            &lt;/li&gt;
            ...
        &lt;/ul&gt;
    &lt;/li&gt;
    ...
&lt;/ul&gt;</code></pre>
<p>In this structure, selecting &#8220;Tall Things&#8221; should automatically select &#8220;Buildings,&#8221; &#8220;Giants,&#8221; and all nested options under &#8220;Giants.&#8221; Conversely, deselecting any child option should update the parent&#8217;s state to reflect that not all children are selected, thus showing the parent in an indeterminate state.</p>
<p>This challenge requires a thoughtful approach to event handling and DOM traversal, ensuring that the state of each checkbox is accurately reflected throughout the hierarchy. As you work through this problem, consider the implications of each interaction, aiming for a solution that is both efficient and intuitive for the user.</p>


---

## 62. Tabs

- Source Number: 62
- Slug: `tabs`
- Date: `2024-03-16T22:15:34`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Airbnb
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-380" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.18.45-PM-300x261.png" alt="" width="300" height="261" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.18.45-PM-300x261.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-3.18.45-PM.png 596w" sizes="(max-width: 300px) 100vw, 300px" /></p>
<p>The objective is to develop a tabbed UI component that allows users to interactively switch between different tabs. Each tab should display specific content associated with it, and only the content of the active tab should be visible at any time. The component should be styled and functional, providing an intuitive user experience.</p>
<p>Each tab&#8217;s visibility is controlled by React state, allowing for dynamic rendering of tab content based on user interaction.</p>


---

## 63. Infinite Scrolling News Feed

- Source Number: 63
- Slug: `build-infinite-scrolling-newsfeed`
- Date: `2024-03-16T20:33:19`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Vanilla

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-medium wp-image-348" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-1.49.33-PM-300x208.png" alt="" width="300" height="208" srcset="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-1.49.33-PM-300x208.png 300w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-1.49.33-PM-768x534.png 768w, https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-1.49.33-PM.png 924w" sizes="(max-width: 300px) 100vw, 300px" /></p>
<p>You have been tasked with creating a Facebook-like newsfeed that displays user-generated content with infinite scrolling. The application should fetch user data from a mock API endpoint and display it in a feed. As users scroll down the feed, more content should be dynamically loaded, ensuring a seamless user experience.</p>
<p>Endpoint: https://dummyjson.com/users?limit=10&amp;skip=1</p>
<p><strong>Functional Requirements:</strong></p>
<ul>
<li>The feed should initially load a set number of posts.</li>
<li>As the user scrolls to the bottom of the feed, more posts should be loaded dynamically.</li>
<li>The application should handle cases where no more data is available to load.</li>
</ul>
<p><strong>Input/Output Examples:</strong></p>
<ul>
<li><strong>Input:</strong> Initial load of the page<br />
<strong>Expected Output:</strong> Displays the first set of user-generated content along with a loader element.</li>
<li><strong>Input:</strong> Scroll to the bottom of the feed<br />
<strong>Expected Output:</strong> Removes the loader element and appends more user-generated content to the feed.</li>
<li><strong>Input:</strong> Scroll to the bottom of the feed again<br />
<strong>Expected Output:</strong> Continues appending additional user-generated content to the feed.</li>
</ul>


---

## 64. K MostText Nodes

- Source Number: 64
- Slug: `k-most-text-nodes`
- Date: `2024-03-14T23:21:10`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Google
- Category: DOM API
- Type: Coding

### Content

<p>Given a DOM tree representing a webpage and a limit (K), write a function to find the K most frequently appeared text nodes in the webpage. A text node is considered as a string of non-empty characters that are not equal to &#8216;↵&#8217;. Ignore other node types (e.g., element nodes) while counting the frequency. Return an array containing the K most frequent text nodes in descending order of their frequencies.</p>
<p><strong>Example:</strong></p>
<p>Consider the following webpage HTML:</p>
<pre><code>&lt;div id="root"&gt;
  &lt;p&gt;This is a paragraph.&lt;/p&gt;
  &lt;div&gt;
    &lt;span&gt;This is some text.&lt;/span&gt;
    &lt;p&gt;Another paragraph here.&lt;/p&gt;
  &lt;/div&gt;
  &lt;p&gt;This is another paragraph.&lt;/p&gt;
&lt;/div&gt;</code></pre>
<p>Input:</p>
<ul>
<li>tree = DOM tree of the webpage</li>
<li>limit = 3</li>
</ul>
<p>The function <code>findKFrequentWordsInTree(tree, limit)</code> should analyze the text nodes within the given DOM tree and return the K (3 in this example) most frequently occurring text nodes.</p>
<p>The expected output for this example, assuming the function correctly identifies and counts the frequency of text nodes, might be an array like <code>['This', 'is', 'a']</code>, reflecting the most common text nodes within the specified limit.</p>
<p>This task tests your ability to traverse and process DOM trees, count frequency of specific nodes, and return a sorted list of these nodes based on their frequency, which are essential skills for manipulating web page content dynamically.</p>


---

## 65. Memoize II

- Source Number: 65
- Slug: `memoize-ii`
- Date: `2024-03-14T15:24:58`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Enhance the <code>memoize</code> function by implementing a more sophisticated caching mechanism using a Trie data structure. This approach optimizes memory usage by storing each argument of the memoized function as a node within a Trie, rather than concatenating arguments into a single string key.</p>
<p>The updated <code>memoize</code> function should work as follows:</p>
<ul>
<li>It accepts a function <code>func</code> and returns a new function that caches the results of <code>func</code> based on its arguments.</li>
<li>The cache is represented by a Trie structure, where each node corresponds to an argument of the memoized function.</li>
<li>If the memoized function is called with a set of arguments that has been previously used, the function retrieves the result from the Trie cache instead of executing <code>func</code> again.</li>
<li>If the set of arguments is new, the memoized function executes <code>func</code>, stores the result in the Trie cache, and returns the result.</li>
</ul>
<p>This approach minimizes memory consumption by avoiding the need to store serialized representations of arguments. Instead, the Trie structure efficiently represents the hierarchical relationship between arguments, making it an ideal choice for caching function results.</p>
<p>The implementation includes two helper classes, <code>TrieNode</code> and <code>Trie</code>, which provide the necessary structure and methods for the Trie cache, such as <code>set</code>, <code>has</code>, and <code>get</code>, similar to the Map object.</p>


---

## 66. Promise Methods

- Source Number: 66
- Slug: `promise-methods`
- Date: `2024-03-14T15:06:25`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, LinkedIn, ClickUp
- Category: Javascript
- Type: Coding

### Content

<p>Extend the Promise object in JavaScript by implementing custom methods that mimic the functionality of existing Promise methods. Specifically, you are required to create the following methods:</p>
<ul>
<li><code>Promise.myRace</code>: This method should mimic the behavior of <code>Promise.race</code>, returning a promise that resolves or rejects as soon as one of the promises in the input array does, reflecting that promise&#8217;s outcome.</li>
<li><code>Promise.myAny</code>: Similar to <code>Promise.any</code>, this method should return a promise that resolves as soon as any one of the input promises resolves, with the value of the resolved promise. If all input promises are rejected, it should reject with an aggregate error.</li>
<li><code>Promise.myAll</code>: This method should emulate <code>Promise.all</code>, returning a promise that resolves when all of the input promises have resolved, with an array of the results, or rejects as soon as one of the input promises rejects.</li>
<li><code>Promise.myAllSettled</code>: Inspired by <code>Promise.allSettled</code>, this method should return a promise that resolves after all input promises have settled (resolved or rejected), with an array of objects that each describe the outcome of each promise.</li>
</ul>
<p>For example, using <code>Promise.myRace</code>, you can race multiple promises against each other and act upon the first to settle, whether it resolves or rejects:</p>
<pre><code>Promise.myRace([Promise.resolve('First'), Promise.reject('Second'), Promise.resolve('Third')])
  .then(value =&gt; console.log(value))
  .catch(error =&gt; console.error(error));
// Expected output: "First"
</code></pre>
<p>Implementing these methods will give you deeper insights into the workings of promises in JavaScript, enhancing your understanding of asynchronous programming patterns.</p>


---

## 67. querySelectorAll

- Source Number: 67
- Slug: `build-your-own-queryselectorall-javascript-guide`
- Date: `2024-03-10T17:22:45`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Coding

### Content

<p>The <code>querySelectorAll</code> method is an essential tool in web development, enabling developers to select elements from the DOM (Document Object Model) that match specific CSS selectors. This method simplifies the process of manipulating HTML documents by allowing for the selection of elements based on class names, IDs, attributes, and more, mirroring the flexibility of CSS.</p>
<p>In this exercise, we aim to create a simplified version of <code>querySelectorAll</code>. This custom function, <code>querySelectorAll</code>, will be designed to traverse the DOM tree and collect elements that match a given CSS selector. The function will begin its search from a specified node (defaulting to the document&#8217;s root) and explore child nodes recursively to find matches.</p>
<h3>Function Signature</h3>
<p>Our simplified <code>querySelectorAll</code> function has the following signature:</p>
<pre><code>function querySelectorAll(selector, node = document)</code></pre>
<ul>
<li><code>selector</code>: A string representing the CSS selector to match against.</li>
<li><code>node</code>: The root node from where the search should start. It defaults to the document if not provided.</li>
</ul>
<h3>Implementation Details</h3>
<p>The function works by recursively traversing the DOM tree from the given node, checking each node against the provided CSS selector. If a node matches the selector, it is added to an array of elements. This array is eventually returned, containing all elements that matched the selector.</p>
<p>Here&#8217;s a step-by-step breakdown of the function&#8217;s logic:</p>
<ol>
<li>Initialize an empty array <code>elements</code> to store the matching elements.</li>
<li>Define a <code>traverse</code> function that will recursively explore each node in the DOM tree.
<ul>
<li>If the current node matches the provided CSS selector (using the <code>matches</code> method), it is added to the <code>elements</code> array.</li>
<li>The <code>traverse</code> function is then called on each child node of the current node, allowing the function to search deeper into the DOM tree.</li>
</ul>
</li>
<li>The <code>traverse</code> function is initially called with the starting node, kicking off the recursive search.</li>
<li>Once the entire tree has been explored, the <code>elements</code> array, now potentially populated with matching elements, is returned.</li>
</ol>
<h3>Usage Examples</h3>
<p>The custom <code>querySelectorAll</code> function can be used in various scenarios, similar to the native method. Here are some examples:</p>
<ul>
<li>To select all paragraph (<code>&lt;p&gt;</code>) elements within the document:
<pre><code>const paragraphs = querySelectorAll('p');</code></pre>
</li>
<li>To find all <code>&lt;div&gt;</code> elements within a specific container:
<pre><code>const container = document.getElementById('container');
const divsInContainer = querySelectorAll('div', container);</code></pre>
</li>
<li>To locate elements with a specific class within a container:
<pre><code>const elementsWithClass = querySelectorAll('.my-class', container);</code></pre>
</li>
</ul>
<h3>Limitations and Considerations</h3>
<p>While our simplified <code>querySelectorAll</code> function demonstrates the core concept of DOM traversal and element selection, it is not as optimized or feature-rich as the native implementation. The actual <code>querySelectorAll</code> method provided by browsers supports a wide range of CSS selectors and includes optimizations for performance. Therefore, our function serves as an educational tool to understand the underlying principles rather than a replacement for the native method.</p>
<p>By building and understanding this simplified version of <code>querySelectorAll</code>, developers can gain insights into how DOM traversal works and how elements are programmatically selected and manipulated in web development.</p>


---

## 68. Rate Limiter

- Source Number: 68
- Slug: `rate-limiter`
- Date: `2024-03-15T17:41:45`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Google
- Category: Algorithmic
- Type: Coding

### Content

<p>You are tasked with safeguarding a web service or an API endpoint from potential abuse, such as denial-of-service (DOS) attacks, by implementing a rate limiter. Build a function called <code>isAllowed</code> within a <code>RateLimiter</code> class. This function should deny any request from a unique client that exceeds the threshold of 100 requests within the last second.</p>
<p>Consider the following examples to understand the functionality of the <code>isAllowed</code> function:</p>
<ul>
<li>If Client A has initiated 99 requests in the preceding second and makes another request, <code>isAllowed</code> should <strong>Allow</strong> this request.</li>
<li>If Client B has sent 101 requests within the same timeframe, <code>isAllowed</code> should <strong>Deny</strong> any subsequent requests from Client B.</li>
<li>If Client C has made 50 requests in the past second, the next request from Client C should also be <strong>Allowed</strong> by <code>isAllowed</code>.</li>
</ul>
<p>This rate limiting mechanism serves as a defensive measure against excessive usage or attacks, ensuring that the web service remains available and performs optimally for all users.</p>


---

## 69. Animate Element To The Right

- Source Number: 69
- Slug: `request-animation-frame`
- Date: `2024-03-15T16:01:25`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/Ko9J4T8MY-M
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Write a function that animates an HTML element to move towards the right by a specified distance over a given duration. The function should utilize the <code>requestAnimationFrame</code> method to ensure smooth animation.</p>
<p><strong>Example:</strong></p>
<p>Input:</p>
<ul>
<li><code>elementID</code>: &#8216;hello&#8217;</li>
<li><code>distance</code>: 400</li>
<li><code>duration</code>: 1000</li>
</ul>
<p>Expected Output:</p>
<p>The element with the ID &#8216;hello&#8217; should gradually move 400 pixels to the right over a duration of 1000 milliseconds.</p>


---

## 70. RxJS Observable

- Source Number: 70
- Slug: `javascript-observables-reactive-programming-guide`
- Date: `2024-03-12T15:32:38`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<article>Observables are pivotal in modern application development, especially in asynchronous event-driven architectures. They allow subscribing to a stream of values and receiving notifications for new values, errors, and completion events. This functionality is essential for managing asynchronous data flows and handling events in a decoupled manner.</p>
<section>
<h2>Objective</h2>
<p>Your task is to implement a basic <code>Observable</code> class in JavaScript. This class should enable the subscription to a stream of values, supporting multiple subscribers and effectively handling errors and completion events.</p>
</section>
<section>
<h2>Requirements</h2>
<ul>
<li>The class must support multiple subscribers.</li>
<li>It should handle errors and completion events, delivering these notifications exactly once.</li>
<li>Subsequent <code>next</code>, <code>error</code>, or <code>complete</code> calls after an error/complete event should be ignored.</li>
<li>The <code>subscribe</code> function should accept either an object with <code>next</code>, <code>error</code>, and <code>complete</code> methods or a function treated as the <code>next</code> method.</li>
<li>The <code>subscribe</code> function returns a Subscription object, allowing unsubscribing from the Observable.</li>
</ul>
</section>
<section>
<h2>Example Usage</h2>
<p>Consider the following observer object, indicating its purpose through <code>next</code>, <code>error</code>, and <code>complete</code> callbacks:</p>
<pre><code>const observer = {
  next: (value) =&gt; { console.log('Received a value:', value); },
  error: (error) =&gt; { console.log('Encountered an error:', error); },
  complete: () =&gt; { console.log('No more values to receive.'); }
};</code></pre>
<p>This Observer can be associated with an Observable, which dispatches values, errors, or completion signals to the attached Observer:</p>
<pre><code>const observable = new Observable((subscriber) =&gt; {
  subscriber.next(1);
  subscriber.next(2);
  setTimeout(() =&gt; {
    subscriber.next(3);
    subscriber.next(4);
    subscriber.complete();
  }, 100);
});</code></pre>
<p>Attaching the observer to the observable and handling the subscription allows for receiving values and notifications as defined:</p>
<pre><code>const subscription = observable.subscribe(observer);
// Logs:
// Received a value: 1
// Received a value: 2
// (after delay) Received a value: 3
// Received a value: 4
// No more values to receive.</code></pre>
</section>
<section>
<h2>Follow-Up Problems</h2>
<p>This Observable and Observer implementation introduces various intriguing follow-up problems and patterns to explore, further expanding on reactive programming concepts.</p>
</section>
</article>


---

## 71. Set Interval with Linear Delay

- Source Number: 71
- Slug: `set-interval-with-linear-delay`
- Date: `2024-03-15T17:04:47`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p>The task at hand involves creating a custom function named <code>mySetInterval(func, delay, period)</code> that diverges from the traditional <code>window.setInterval</code> behavior. Instead of executing the provided function <code>func</code> at regular intervals, this function should execute <code>func</code> with increasing delays following a linear pattern. The delay before each subsequent execution is calculated using the formula <code>delay + period * count</code>, where <code>count</code> is the number of times the function has been called.</p>
<p>To illustrate, consider the following example:</p>
<pre><code>let prev = Date.now();
const func = () =&gt; {
  const now = Date.now();
  console.log('Time elapsed:', now - prev, 'ms');
  prev = now;
};

const id = mySetInterval(func, 100, 200);

// Output:
// Time elapsed: 100ms
// Time elapsed: 400ms (100 + 200 * 1)
// Time elapsed: 900ms (100 + 200 * 2)
// Time elapsed: 1600ms (100 + 200 * 3)
// ...
</code></pre>
<p>This functionality allows for scheduling tasks with increasing intervals, which can be particularly useful in scenarios where the intensity of task execution needs to decrease over time.</p>
<p>Additionally, a function named <code>myClearInterval(id)</code> should be provided to stop the scheduled execution. This function should take an identifier returned by <code>mySetInterval</code> and cancel the scheduled task.</p>
<p>The challenge lies not only in implementing the increasing delay logic but also in ensuring that the <code>mySetInterval</code> and <code>myClearInterval</code> functions can be used similarly to their native JavaScript counterparts, providing a seamless interface for scheduling and canceling tasks with dynamic intervals.</p>


---

## 72. Stream

- Source Number: 72
- Slug: `stream-subscription-service`
- Date: `2024-03-10T17:46:01`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: N/A
- Category: Javascript
- Type: Coding

### Content

<p>You are tasked with building a simple stream subscription system in JavaScript, encapsulated within a Stream class. This class should enable users to subscribe to the stream and receive updates whenever new data is pushed into it, allowing for real-time data processing and manipulation.</p>
<p>The Stream class should be designed with the following functionalities:</p>
<ul>
<li><strong>Subscriptions:</strong> Users can subscribe to the stream by providing a callback function. This function should be invoked with the new data as its argument whenever the stream is updated.</li>
<li><strong>Data Pushing:</strong> The class should provide a method to push new data into the stream. Upon pushing new data, all subscribed callback functions should be executed with the newly pushed data, enabling subscribers to react to updates in real-time.</li>
</ul>
<p>Here&#8217;s a simple usage example demonstrating both subscription and data pushing:</p>
<pre><code>
// Creating a new instance of the Stream class
const myStream = new Stream();

// Subscribing to the stream with a callback function
myStream.subscribe(data => console.log(`Received data: ${data}`));

// Pushing new data into the stream, triggering subscribed callbacks
myStream.push('Hello, world!');
// Output: "Received data: Hello, world!"
</code></pre>
<p>This implementation facilitates a versatile mechanism for handling real-time data streams, allowing multiple consumers to process and react to new data as it becomes available. Whether for handling event streams, processing live data feeds, or implementing observer patterns, the Stream class provides a foundational structure for these scenarios.</p>
<p>As you delve into building this stream subscription system, consider the aspects of data flow, subscriber management, and the efficiency of data dissemination among multiple subscribers.</p>


---

## 73. String Repeater

- Source Number: 73
- Slug: `string-repeater`
- Date: `2024-03-14T16:18:02`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Apple
- Category: Array
- Type: Coding

### Content

<article>
<p>Write a function named <code>myRepeat</code> that extends the String prototype. This function should allow a string to be repeated a specified number of times, enhancing the native capabilities of string manipulation in JavaScript.</p>
<h3>Input</h3>
<ul>
<li><strong>String:</strong> The string to be repeated.</li>
<li><strong>Integer (times):</strong> The number of times the string should be repeated.</li>
</ul>
<h3>Output</h3>
<p>A new string that concatenates the original string the specified number of times.</p>
<h3>Example</h3>
<p><strong>Input:</strong> <code>"hello world ".myRepeat(2)</code></p>
<p><strong>Output:</strong> <code>"hello world hello world "</code></p>
<p>The function <code>myRepeat</code> takes an integer <code>times</code> as an argument and returns a new string that repeats the original string <code>times</code> number of times. This custom method does not modify the original string but instead returns a new string with the repeated content, demonstrating an extension of the String prototype&#8217;s functionality in JavaScript.</p>
</article>


---

## 74. Debounce I

- Source Number: 74
- Slug: `debounce-i`
- Date: `2024-03-09T17:37:30`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: https://www.youtube.com/embed/6uB4a7igDP4
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Robinhood, Zillow, Airbnb, OpenAI, Microsoft, Netflix, Apple, LinkedIn, Stripe, ClickUp, PayPal, Snap, Vimeo, Adobe, TikTok
- Category: Javascript
- Type: Coding

### Content

<p>You are tasked with implementing a <code>debounce</code> function in JavaScript, an essential technique in improving the performance of web applications by limiting the rate at which a function is executed. This function is particularly useful in scenarios where some code should not run until after a certain amount of time has elapsed since the last time it was invoked, such as during window resizing, scrolling, or real-time form validation.</p>
<h3>Functionality Requirements:</h3>
<p>The <code>debounce</code> function should accept a callback function, a delay in milliseconds, and an optional boolean parameter <code>immediate</code>. It returns a new function that, when invoked repeatedly, will only execute the callback after the specified delay has passed since the last invocation. If the <code>immediate</code> parameter is set to <code>true</code>, the callback should be executed immediately on the first call, but subsequent calls should be debounced until there is a pause in invocation for at least the delay period.</p>
<h3>Behavioral Specifications:</h3>
<ul>
<li>If <code>immediate</code> is <code>false</code> (default), the callback is executed after the delay period if no subsequent calls are made within that delay.</li>
<li>If <code>immediate</code> is <code>true</code>, the callback is executed immediately on the first call, but subsequent calls are debounced until the delay period has elapsed without any new calls.</li>
</ul>
<h3>Technical Considerations:</h3>
<p>Use a timer to track the delay period and ensure that the callback function&#8217;s execution is postponed until the delay passes without any new invocation of the returned function. Carefully manage the timer to handle immediate execution logic and reset the timer as needed to ensure correct function behavior.</p>
<p>This implementation of the <code>debounce</code> function will enhance your application&#8217;s responsiveness and efficiency by preventing code from executing too frequently under rapid event firing, such as typing in a search input or resizing a window.</p>


---

## 75. To-do App

- Source Number: 75
- Slug: `todo-app`
- Date: `2024-03-16T18:59:11`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 2 weeks, 1 month, 3 months, 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Robinhood, Zillow, Airbnb, OpenAI, Microsoft, Netflix, Apple, LinkedIn, Stripe, ClickUp, PayPal, Snap, Vimeo, Adobe, TikTok, Atlassian
- Category: App Design
- Type: Vanilla

### Content

<p>You&#8217;ve been tasked with building a basic ToDo app using HTML, CSS, and JavaScript. The goal of this project is to create a functional todo list that allows users to add, remove, complete, and update tasks. This exercise focuses on enhancing your skills with DOM manipulation, event handling, and dynamic content generation in Vanilla JavaScript.</p>
<p>The application&#8217;s UI is already set up with HTML and CSS. Your main task is to implement the JavaScript functionality to bring the ToDo app to life. Here are the key features your app should support:</p>
<ul>
<li><strong>Adding a ToDo Item:</strong> Users should be able to type in a task and add it to the list by submitting the form. The new task should appear at the top of the list.</li>
<li><strong>Removing a ToDo Item:</strong> Each task should have an associated &#8216;Delete&#8217; button. Clicking this button should remove the task from the list.</li>
<li><strong>Completing a ToDo Item:</strong> Each task should also have a &#8216;Complete&#8217; button. When clicked, the task should be visually marked as completed (e.g., strikethrough text).</li>
<li><strong>Updating a ToDo Item:</strong> Tasks should be editable. An &#8216;Update&#8217; button should toggle the task between an editable state and a view state. Users can change the task text and save the changes.</li>
</ul>
<p><strong>Example:</strong> Below is a visual and functional description of the app&#8217;s intended behavior.</p>
<pre><code>&lt;!-- Initial State --&gt;
&lt;div id="container"&gt;
  &lt;div class="wrapper"&gt;
    &lt;h1&gt;ToDo App&lt;/h1&gt;
    &lt;form action="#" class="addtodo-form"&gt;
      &lt;input class="input-todo" type="text" placeholder="Write your todo..."&gt;
      &lt;input type="submit" value="Add Todo"&gt;
    &lt;/form&gt;
    &lt;br/&gt;&lt;br/&gt;
    &lt;h2&gt;Items to be done&lt;/h2&gt;
    &lt;br/&gt;----&lt;br/&gt;
    &lt;ul&gt;
      &lt;div class="no-todos"&gt;No Todos Available Yet&lt;/div&gt;
    &lt;/ul&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- After Adding a New Task 'Task 1' --&gt;
&lt;ul&gt;
  &lt;li&gt;
    &lt;div class="text"&gt;Task 1&lt;/div&gt;
    &lt;input class="hidden" type="text" value="Task 1"&gt;
    &lt;div class="buttons"&gt;
        &lt;button class="update green"&gt;Update&lt;/button&gt;
        &lt;button class="delete"&gt;X&lt;/button&gt;
        &lt;button class="done"&gt;Complete&lt;/button&gt;
    &lt;/div&gt;
  &lt;/li&gt;
  &lt;div class="no-todos hidden"&gt;No Todos Available Yet&lt;/div&gt;
&lt;/ul&gt;
</code></pre>
<p>This project is an excellent opportunity to practice and showcase your ability to work with core web technologies and implement basic but crucial functionalities that are common in many web applications.</p>


---

## 76. Transactions List

- Source Number: 76
- Slug: `transactions-list`
- Date: `2024-03-16T23:04:10`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Stripe
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-403" src="https://api.frontendlead.com/wp-content/uploads/2024/03/Screenshot-2024-03-16-at-4.33.20-PM.png" alt="" width="234" height="294" /></p>
<p>You are provided with a React application designed to manage and display a list of customer transactions. The primary functionalities of this application include:</p>
<ul>
<li><strong>Rendering the Transaction List:</strong> Displaying an initial list of transactions to the user, each containing an ID, the customer&#8217;s name, and the transaction amount.</li>
<li><strong>Filtering Transactions:</strong> Allowing users to filter the transaction list by customer name through a text input field. The list updates in real-time based on the user&#8217;s input, showing transactions that match the entered name (case-insensitively).</li>
<li><strong>Highlighting Top Customer&#8217;s Transactions:</strong> Identifying the customer with the highest total transaction amount across all their transactions. The application highlights transactions associated with this top customer in the list, making them easily distinguishable.</li>
</ul>
<p>These features aim to enhance user experience by providing a clear and interactive way to manage and understand transaction data. Users can easily locate transactions for specific customers, and quickly identify which customer has the highest total transaction amount, thanks to the visual highlights applied to their transactions.</p>
<p><strong>Implementation Example:</strong></p>
<pre><code>
const transactions = [
  { id: "t_101", customer: "Alice Anderson", amount: 84 },
  { id: "t_102", customer: "Bob Brown", amount: 30 },
  // Additional transactions...
];

function TransactionsList({ transactions }) {
  // Component logic...
  return (
    &lt;div&gt;
      &lt;input type="text" onChange={/* Filter logic */} /&gt;
      &lt;ul&gt;
        {transactions.map(transaction =&gt; (
          &lt;li key={transaction.id}&gt;
            &lt;span style={{ backgroundColor: /* Highlighting logic */ }}&gt;
              {transaction.customer}
            &lt;/span&gt;
            : {transaction.amount}
          &lt;/li&gt;
        ))}
      &lt;/ul&gt;
    &lt;/div&gt;
  );
}
</code></pre>
<p>This code snippet illustrates the basic structure and functionality of the React application, highlighting the key areas of rendering, filtering, and visual distinction of transactions. The actual logic for filtering and highlighting will depend on the user input and the aggregated transaction amounts per customer.</p>


---

## 77. Trending Stocks

- Source Number: 77
- Slug: `trending-stocks`
- Date: `2024-03-08T18:00:04`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook, Amazon, Google, Microsoft, Netflix, Apple
- Category: JSON
- Type: Coding

### Content

<p>You are tasked with creating a function that retrieves information about trending stocks based on their market capitalization and prices. The goal is to identify the top <code>n</code> trending stocks, where <code>n</code> is a specified number, and return details about these stocks in a structured format. The function should return an array of objects, each encapsulating the symbol, name, market capitalization, and current price of these trending stocks.</p>
<p>The challenge involves fetching data from three different APIs: one for stock symbols and names, another for market capitalizations, and the last one for current stock prices. The process is to first fetch the symbols and market caps, sort the stocks by market cap in descending order, pick the top <code>n</code> stocks, and then fetch their current prices. Finally, the information is aggregated into a single array of objects that contain all the necessary details for each selected stock.</p>
<h3>Example:</h3>
<p>Consider you want to find the top 2 trending stocks. The function will sort all available stocks based on their market capitalization and return the details for the top 2.</p>
<pre><code>Input: n = 2

Output:
[
  { "symbol": "MMM", "name": "3M Company", "market-cap": 138721055226, "price": 1001.52 },
  { "symbol": "ABT", "name": "Abbott Laboratories", "market-cap": 102121042306, "price": 1001.52 }
]
</code></pre>
<p>The function encapsulates a complex process of asynchronous API calls, data sorting, and aggregation, presenting a streamlined solution to the user. This task not only tests your proficiency with asynchronous JavaScript operations but also your ability to work with external data sources and transform data to fit specific requirements.</p>
<p>This challenge serves as an excellent real-world scenario for frontend developers, especially for those interested in financial technologies or stock market applications, providing both a technical challenge and an insight into financial data manipulation.</p>


---

## 78. Reorder Array With New Indexes

- Source Number: 78
- Slug: `reorder-array-with-new-indexes`
- Date: `2024-03-18T21:36:31`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Array
- Type: Coding

### Content

<p>Given an array of items and a corresponding array of new index positions, write a function to reorder the items array according to the new index positions provided. Your function should mutate the original items array to reflect the new order.</p>
<p>This challenge tests your understanding of array manipulation and sorting algorithms. It&#8217;s a common task in frontend development, especially when dealing with dynamic user interfaces where elements might need reordering based on user actions or other criteria.</p>
<p><strong>Example:</strong></p>
<pre><code>Input: items = ["a", "b", "c", "d", "e"], newOrder = [3, 0, 4, 1, 2]
Output: items becomes ["b", "d", "e", "a", "c"]</code></pre>
<p>The function should take two arguments:</p>
<ul>
<li><code>items</code>: An array of elements that need to be reordered.</li>
<li><code>newOrder</code>: An array of integers representing the new index positions for each corresponding element in the <code>items</code> array.</li>
</ul>
<p>The goal is to mutate the <code>items</code> array such that each element is moved to its new index as specified by the <code>newOrder</code> array. Ensure your solution accounts for the possibility of various data types within the <code>items</code> array and handles edge cases gracefully.</p>


---

## 79. Merge Identical API Calls

- Source Number: 79
- Slug: `merge-identical-api-calls`
- Date: `2024-03-18T21:44:16`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Implement a function that enhances a given API call function by merging identical calls and caching their responses to optimize network usage. This approach should prevent multiple identical requests from being sent to the server simultaneously, reducing unnecessary network traffic and load on the server.</p>
<p>The function, <code>createGetAPIWithMerging</code>, takes an API call function <code>getAPI</code> as an argument and returns a new function. This new function behaves like <code>getAPI</code> but with added capabilities:</p>
<ul>
<li>Merging identical API calls made within a short timeframe.</li>
<li>Caching the responses of these calls to serve future identical requests without contacting the server.</li>
<li>Limiting the cache size to maintain only the most recent responses, thus managing memory usage effectively.</li>
</ul>
<p><strong>Usage Example:</strong></p>
<pre><code>const mergedGetAPI = createGetAPIWithMerging(getAPI);
const response1 = await mergedGetAPI('/data', { params: { id: 123 } });
const response2 = await mergedGetAPI('/data', { params: { id: 123 } });  // This call will be merged with the first one if made within 1 second.
</code></pre>
<p>Here, <code>getAPI</code> is the original function for making GET requests. <code>createGetAPIWithMerging</code> enhances it by caching and merging, ensuring that if multiple identical requests are made in rapid succession, only one will be sent to the server, and its response will be used for all of them.</p>
<p>The cache is automatically managed to contain only a limited number of recent responses and to expire entries after a short period, ensuring the data&#8217;s freshness and limiting memory usage.</p>


---

## 80. Fake Timer

- Source Number: 80
- Slug: `build-fake-timer`
- Date: `2024-03-18T21:50:07`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Javascript
- Type: Coding

### Content

<p>Create a <code>FakeTimer</code> class that can be used to replace the native JavaScript timing functions (<code>setTimeout</code>, <code>clearTimeout</code>, and <code>Date.now</code>) with a controllable fake version. This allows for the simulation and testing of time-dependent code without the need for actual time to elapse, making it ideal for tests and simulations where precise timing control is required.</p>
<p>The <code>FakeTimer</code> class should provide the following functionalities:</p>
<ul>
<li><strong>Install:</strong> Replace the native timing functions with fake ones that queue callbacks instead of executing them after a real delay.</li>
<li><strong>Uninstall:</strong> Restore the original timing functions to their native implementations.</li>
<li><strong>Tick:</strong> Manually advance the fake timer, executing any callbacks that should be triggered up to the current simulated time.</li>
</ul>
<p><strong>Usage Example:</strong></p>
<pre><code>const timer = new FakeTimer();
timer.install();
// Schedule a timeout
const id = setTimeout(() => console.log('Timeout called'), 100);
// Advance the fake timer
timer.tick();
// 'Timeout called' is logged to the console
timer.uninstall();  // Restore original functions</code></pre>
<p>This feature is particularly useful in unit testing, where real-time waiting is impractical. It allows for precise control over the execution timing of callbacks, enabling more deterministic and faster tests.</p>


---

## 81. GetTextBetweenNodes

- Source Number: 81
- Slug: `get-text-between-nodes`
- Date: `2024-03-18T21:57:53`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: DOM API
- Type: Coding

### Content

<p>Create a function <code>getTextBetweenTwoNodes</code> that retrieves all the text content found in the DOM between two specified nodes, <code>node1</code> and <code>node2</code>. The function should traverse the DOM tree, collecting text from text nodes that are located between these two nodes, and return an array of these text snippets.</p>
<p>The function should consider a depth-first search approach to navigate through the DOM elements, ensuring that all text nodes between the two specified nodes are included. It&#8217;s important to handle various edge cases, such as when the nodes are nested at different levels or when there&#8217;s no direct sibling relationship between them.</p>
<p><strong>Function Signature:</strong></p>
<pre><code>function getTextBetweenTwoNodes(node1: Node, node2: Node): string[]</code></pre>
<p><strong>Example Usage:</strong></p>
<pre><code>const node1 = document.getElementById('start');
const node2 = document.getElementById('end');
const textsBetween = getTextBetweenTwoNodes(node1, node2);
console.log(textsBetween);  // Output: Array of text snippets between node1 and node2</code></pre>
<p>This utility can be particularly useful for web scraping, automated testing, or any scenario where understanding the text content between two DOM elements is required.</p>


---

## 82. First Bad Version

- Source Number: 82
- Slug: `first-bad-version`
- Date: `2024-03-18T22:21:33`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Algorithmic
- Type: Coding

### Content

<p>Suppose you have <code>n</code> versions of a product, and you want to find the first version that introduced a bug, causing all the following versions to also be bad. Given a function <code>isBad</code> that takes a version number and returns <code>true</code> if the version is bad and <code>false</code> otherwise, implement a function <code>firstBadVersion</code> that utilizes a binary search algorithm to efficiently find and return the first bad version.</p>
<p>Your function should minimize the number of calls to the <code>isBad</code> function. Implement <code>firstBadVersion</code> such that it returns a closure which accepts a single integer parameter <code>version</code>, representing the total number of versions, and returns the first bad version number, or <code>-1</code> if no bad version is found.</p>
<p><strong>Function Signature:</strong></p>
<pre><code>function firstBadVersion(isBad: (version: number) => boolean): (version: number) => number</code></pre>
<p><strong>Example Usage:</strong></p>
<pre><code>const isBad = (version) => version >= 4;
const findFirstBad = firstBadVersion(isBad);
console.log(findFirstBad(5));  // Output: 4</code></pre>
<p>This problem tests your ability to apply binary search in a practical scenario, optimizing for efficiency in terms of time complexity and minimizing the use of resources such as network or database calls.</p>


---

## 83. Roman Numeral To Int

- Source Number: 83
- Slug: `roman-numeral-to-int`
- Date: `2024-03-18T22:30:16`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Algorithmic
- Type: Coding

### Content

<p>Implement a function <code>romanToInteger</code> that converts a Roman numeral string to an integer. Roman numerals are represented by seven different symbols: <code>I</code>, <code>V</code>, <code>X</code>, <code>L</code>, <code>C</code>, <code>D</code> and <code>M</code>.</p>
<p>The rules for Roman numeral conversion are as follows:</p>
<ul>
<li><code>I</code> can be placed before <code>V</code> (5) and <code>X</code> (10) to make 4 and 9.</li>
<li><code>X</code> can be placed before <code>L</code> (50) and <code>C</code> (100) to make 40 and 90.</li>
<li><code>C</code> can be placed before <code>D</code> (500) and <code>M</code> (1000) to make 400 and 900.</li>
</ul>
<p><strong>Function Signature:</strong></p>
<pre><code>function romanToInteger(str: string): number</code></pre>
<p><strong>Example Usage:</strong></p>
<pre><code>const result = romanToInteger("MCMXCIV");
console.log(result);  // Output: 1994</code></pre>
<p>Your solution should handle strings representing Roman numerals in the range from 1 to 3999. The input string is guaranteed to be a valid Roman numeral up to 3999.</p>


---

## 84. Math.sqrtRoot

- Source Number: 84
- Slug: `math-sqrtroot`
- Date: `2024-03-18T22:35:40`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Algorithmic
- Type: Coding

### Content

<p>Create a function <code>mySqrt</code> that computes and returns the square root of a given number <code>x</code>. The function should return the integer part of the square root, similar to how the built-in <code>Math.sqrt</code> function works, but without using it directly. Your implementation should use a binary search algorithm to efficiently find the square root.</p>
<p>Additionally, your function should handle edge cases such as negative numbers, non-numeric inputs, and <code>NaN</code> by returning <code>NaN</code>.</p>
<p><strong>Function Signature:</strong></p>
<pre><code>function mySqrt(x: number): number</code></pre>
<p><strong>Example Usage:</strong></p>
<pre><code>console.log(mySqrt(4));  // Output: 2
console.log(mySqrt(8));  // Output: 2 (since the square root of 8 is approximately 2.82842..., and the function returns the integer part)</code></pre>
<p>The input <code>x</code> is guaranteed to be a non-negative number. The function should aim for an efficient solution, ideally with a time complexity of O(log n).</p>


---

## 85. FeatureFlag

- Source Number: 85
- Slug: `build-feature-flag`
- Date: `2024-03-18T22:51:43`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Atlassian
- Category: Javascript
- Type: Coding

### Content

<p>Create a <code>FeatureFlag</code> class that manages feature flags in a web application. Feature flags are a powerful technique in software development, allowing developers to enable or disable certain features dynamically, often used for testing new features, A/B testing, or enabling features for specific users or environments.</p>
<p>The <code>FeatureFlag</code> class should provide the functionality to check if specific features are enabled or disabled based on stored flags. It should also include a method to retrieve feature flags from local storage, simulating the fetching of feature configurations from a persistent storage or a remote configuration service.</p>
<p><strong>Class Requirements:</strong></p>
<ul>
<li>A constructor that initializes the feature flags.</li>
<li>A private method <code>_fetchFeatures</code> that simulates fetching feature flags from local storage and populates the <code>features</code> object.</li>
<li>A method <code>isEnabled</code> that accepts an array of feature names and returns an array of objects indicating the enabled status of each feature.</li>
<li>An optional method <code>useFeatureFlag</code> similar to <code>isEnabled</code>, demonstrating alternative naming or functionality as desired.</li>
</ul>
<p><strong>Example Usage:</strong></p>
<pre><code>const featureFlag = new FeatureFlag();
console.log(featureFlag.isEnabled(['feature', 'feature2']));
// Output: [{feature: true}, {feature2: false}]</code></pre>
<p>The class should handle cases where local storage might not be accessible due to browser restrictions or privacy settings, defaulting to an empty configuration in such cases.</p>


---

## 86. API Retry

- Source Number: 86
- Slug: `api-retry`
- Date: `2024-03-18T23:01:26`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Atlassian
- Category: Javascript
- Type: Coding

### Content

<p>Implement an asynchronous function <code>retryApiCall</code> that attempts to call a given API function and retries a specified number of times if the call fails or does not return a successful response (status code 200). The function should wait for a given interval between retries.</p>
<p>The function should accept the following parameters:</p>
<ul>
<li><code>apiFunction</code>: A function that makes the API call and returns a promise.</li>
<li><code>maxRetries</code>: The maximum number of retries allowed.</li>
<li><code>retryInterval</code>: The interval (in milliseconds) to wait between retries.</li>
</ul>
<p><strong>Function Signature:</strong></p>
<pre><code>async function retryApiCall(apiFunction: () => Promise<any>, maxRetries: number, retryInterval: number): Promise<any></code></pre>
<p><strong>Example Usage:</strong></p>
<pre><code>const fetchData = async () => {
    // Simulated API call
    return fetch('https://example.com/data');
};

retryApiCall(fetchData, 3, 1000)
    .then(response => console.log('Data:', response))
    .catch(error => console.error('Failed to fetch data:', error));</code></pre>
<p>Ensure that the function correctly handles retries, waiting the specified interval between attempts, and throws an error if the maximum number of retries is reached without a successful response.</p>


---

## 87. JSON.stringify

- Source Number: 87
- Slug: `build-your-own-json-stringify`
- Date: `2024-03-20T01:00:37`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: N/A
- Company: Snap
- Category: Algorithmic
- Type: Coding

### Content

<p>In this challenge, your task is to create a custom implementation of the <code>JSON.stringify()</code> method, which we&#8217;ll call <code>myStringify</code>. The <code>JSON.stringify()</code> method in JavaScript is used to convert JavaScript objects or values to a JSON string. However, for the sake of this exercise, you&#8217;ll be building your own version to deepen your understanding of how data serialization works in JavaScript.</p>
<p>Your function should be able to handle the following data types:</p>
<ul>
<li>Primitive types: Number, String, Boolean, null</li>
<li>Complex types: Objects, Arrays</li>
</ul>
<p>Note that unlike the native <code>JSON.stringify()</code>, your function does not need to worry about circular references, functions, or symbols.</p>
<p>Here are some examples to illustrate what your function should do:</p>
<pre><code>
Input: ['foo', 'bar']
Output: '["foo", "bar"]'

Input: { name: 'John', age: 30, isEmployed: true }
Output: '{"name": "John", "age": 30, "isEmployed": true}'

Input: 42
Output: '42'

Input: 'Hello, world!'
Output: '"Hello, world!"'

Input: true
Output: 'true'

Input: null
Output: 'null'
</code></pre>
<p>Your implementation should correctly convert arrays and objects to their string representations, ensuring to wrap string values in double quotes and separate object properties with commas. Pay close attention to handling edge cases, such as empty objects or arrays.</p>


---

## 88. Node Store II

- Source Number: 88
- Slug: `node-store-es5-compatible`
- Date: `2025-04-24T16:19:14`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: Facebook
- Category: Array
- Type: Coding

### Content

<p>Create a class called <code>NodeStore</code> that allows you to store values associated with DOM nodes. The class should provide the following methods:</p>
<ul>
<li><strong>set(node, value):</strong> Sets the value for a given DOM node.</li>
<li><strong>get(node):</strong> Retrieves the value associated with a given DOM node.</li>
<li><strong>has(node):</strong> Checks if a given DOM node exists in the store.</li>
</ul>
<p><strong>Important:</strong> You cannot use <code>Map</code> or <code>WeakMap</code> in this problem.<br />
Your solution should work in older JavaScript environments (like ES5), where such features are unavailable.<br />
Hint: DOM nodes are mutable JavaScript objects. Can you use that to your advantage?</p>
<p><strong>Example:</strong></p>
<pre><code>const node1 = document.createElement('p');
const node2 = document.createElement('p');
const store = new NodeStore();
store.set(node1, 1);
store.set(node2, 2);
console.log(store.get(node1)); // Expected output: 1
console.log(store.get(node2)); // Expected output: 2
</code></pre>
<p>This task tests your understanding of JavaScript classes, DOM manipulation, object property behavior, and memory-efficient design. It&#8217;s a practical scenario for frontend developers managing metadata tied to specific DOM elements.</p>


---

## 89. Build Airbnb

- Source Number: 89
- Slug: `build-airbnb-react-question`
- Date: `2025-05-26T20:16:58`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.15.56-PM.png
- Company: Airbnb, OpenAI, Netflix, LinkedIn
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1739" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.15.56-PM.png" alt="Build Airbnb" width="1092" height="940" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.15.56-PM.png 1092w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.15.56-PM-300x258.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.15.56-PM-1024x881.png 1024w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.15.56-PM-768x661.png 768w" sizes="(max-width: 1092px) 100vw, 1092px" /></p>
<p>Design and implement a React component that displays a list of products in a responsive Airbnb-style grid. The product data should be fetched from a remote API and displayed as individual cards. Your component must support <strong>infinite scroll</strong>: as the user scrolls down, new products should be fetched and appended to the grid seamlessly. The grid must remain responsive, and each card should clearly show the product’s image, title, and a short description.</p>
<h3>API Details</h3>
<p>You will use the following API endpoint to fetch products:</p>
<pre><code>GET https://fakestoreapi.com/products?limit=&lt;limit&gt;&amp;page=&lt;page&gt;</code></pre>
<ul>
<li><code>limit</code> (number): The number of products to fetch per request.</li>
<li><code>page</code> (number): The page number for pagination (starting from 1).</li>
</ul>
<p>Each product in the response is an object with at least these properties:</p>
<ul>
<li><code>id</code> (number): Unique identifier.</li>
<li><code>title</code> (string): Product name.</li>
<li><code>description</code> (string): Product description.</li>
<li><code>image</code> (string): URL to the product image.</li>
</ul>
<h3>Requirements</h3>
<ul>
<li>Implement a functional React component using hooks (<code>useState</code>, <code>useEffect</code>, <code>useRef</code>).</li>
<li>Fetch the product data from the API in a paginated manner, appending new products to the list as the user scrolls.</li>
<li>Implement <strong>infinite scrolling</strong> using the Intersection Observer API: when the user scrolls to the bottom, automatically fetch the next page of products.</li>
<li>Render the products in a CSS grid layout that is responsive and visually similar to Airbnb listings (cards with images and details).</li>
<li>Handle loading states: display a loading indicator when fetching more products.</li>
<li>Do <strong>not</strong> refetch the same page twice; ensure products load incrementally as the user continues to scroll.</li>
<li>The component should not break if the API returns fewer products than requested (i.e., handle end-of-list scenarios gracefully).</li>
<li>Do <strong>not</strong> mutate the original data or make unnecessary API requests.</li>
</ul>
<h3>Input</h3>
<pre><code>
// No input props. The component manages its own state and fetches data as needed.
</code></pre>
<h3>Output</h3>
<pre><code>
// Renders a responsive grid of product cards. As the user scrolls, more cards are loaded and appended to the grid.
</code></pre>
<h3>Example</h3>
<pre><code>
The user lands on the page. The first set of products is fetched from the API and displayed in a grid.
As the user scrolls to the bottom, the next set of products is automatically fetched and added to the grid.
Each product card displays:
  - An image (from <code>image</code>) - The product title - A short description (first 100 characters of <code>description</code>) Loading indicators appear while more products are being fetched. </code></pre>
<h3>Explanation</h3>
<pre><code>
- Infinite scroll should feel seamless: there are no "Load More" buttons.
- If the API returns no products, or the user scrolls past all available products, the loading indicator should disappear or display an end-of-list message.
- The solution must efficiently manage state and avoid memory leaks by properly cleaning up the Intersection Observer.
</code></pre>


---

## 90. Nested Comments I

- Source Number: 90
- Slug: `react-nested-components`
- Date: `2025-05-26T20:23:58`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.19.58-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1746" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.19.58-PM.png" alt="" width="927" height="303" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.19.58-PM.png 927w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.19.58-PM-300x98.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.19.58-PM-768x251.png 768w" sizes="(max-width: 927px) 100vw, 927px" /></p>
<p>You are given a flat array of posts and comments. Each item in the array represents either a top-level post or a comment on a post (or another comment). Each object has the following properties:</p>
<ul>
<li><code>id</code> (number): A unique identifier for the post or comment.</li>
<li><code>text</code> (string): The content of the post or comment.</li>
<li><code>replyTo</code> (number, optional): The <code>id</code> of the post or comment that this comment is replying to. If absent, the item is a top-level post.</li>
</ul>
<p>Your task is to convert this flat array into a nested tree structure that represents the parent-child relationships between posts and comments, and render this structure recursively in React as an indented list.</p>
<h3>Requirements</h3>
<ul>
<li>Write a function that transforms the flat array of posts and comments into a tree, where each comment object includes a <code>replies</code> array containing its direct children.</li>
<li>Implement a React component that recursively renders the tree, so each comment displays its nested replies as indented child lists.</li>
<li>Handle any depth of nesting—comments can reply to posts, or to other comments, indefinitely.</li>
<li>The input array may contain posts and comments in any order.</li>
<li>Do <b>not</b> mutate the original input array.</li>
</ul>
<h3>Input</h3>
<pre><code>
posts: Array&lt;{
  id: number,
  text: string,
  replyTo?: number
}&gt;
</code></pre>
<h3>Output</h3>
<pre><code>
Array&lt;{
  id: number,
  text: string,
  replyTo?: number,
  replies: Array&lt;...&gt;
}&gt;
</code></pre>
<h3>Example</h3>
<pre><code>
Input:
[
  { id: 1, text: "This is a post 1" },
  { id: 2, replyTo: 1, text: "This is a comment, child to post 1" },
  { id: 3, replyTo: 2, text: "This is a comment, child to comment 2" },
  { id: 4, replyTo: 1, text: "This is a comment, child to post 1" },
  { id: 5, text: "This is a post 2" }
]

Output (tree structure):
[
  {
    id: 1,
    text: "This is a post 1",
    replies: [
      {
        id: 2,
        replyTo: 1,
        text: "This is a comment, child to post 1",
        replies: [
          {
            id: 3,
            replyTo: 2,
            text: "This is a comment, child to comment 2",
            replies: []
          }
        ]
      },
      {
        id: 4,
        replyTo: 1,
        text: "This is a comment, child to post 1",
        replies: []
      }
    ]
  },
  {
    id: 5,
    text: "This is a post 2",
    replies: []
  }
]

Explanation:
- Posts and comments are arranged in a tree structure, where each comment is nested under its parent based on the <code>replyTo</code> field. - Comments can be nested to any depth. - Only items without a <code>replyTo</code> field appear at the top level of the result. </code></pre>


---

## 91. Nested Comments II

- Source Number: 91
- Slug: `react-nested-components-ii`
- Date: `2025-05-26T20:30:48`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.27.23-PM.png
- Company: N/A
- Category: Array
- Type: Coding

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1750" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.27.23-PM.png" alt="Nested Comments II" width="304" height="99" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.27.23-PM.png 304w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.27.23-PM-300x98.png 300w" sizes="(max-width: 304px) 100vw, 304px" /></p>
<h2>Problem Statement</h2>
<p>You are given a data structure representing a list of posts and their nested replies. Each post is represented as an object with the following properties:</p>
<ul>
<li><code>id</code> (number): A unique identifier for the post or comment.</li>
<li><code>text</code> (string): The content of the post or comment.</li>
<li><code>replyTo</code> (number, optional): The <code>id</code> of the post or comment this is replying to.</li>
<li><code>replies</code> (array): An array of child comments (can be empty).</li>
</ul>
<p>Your task is to write a React function that <b>flattens this nested tree</b> into a single-level list (array), including only the posts and comments up to a specified depth <code>maxLevel</code>. If <code>maxLevel = 1</code>, return the top-level posts and their direct replies. If <code>maxLevel = 2</code>, include one more level of replies, and so on. Replies deeper than <code>maxLevel</code> should not be included in the flattened result.</p>
<h3>Requirements</h3>
<ul>
<li>Write a recursive function that accepts the nested array and <code>maxLevel</code> and returns a flat array of nodes up to the required depth.</li>
<li>Render the resulting flat array as a list in React.</li>
<li>Do <b>not</b> mutate the original data.</li>
<li>The input data may have any level of nesting, and nodes may appear in any order.</li>
</ul>
<h3>Input</h3>
<pre><code>posts: Array&lt;Post&gt;
maxLevel: number
</code></pre>
<h3>Output</h3>
<pre><code>Array&lt;Post&gt; // flattened to the required depth
</code></pre>
<h3>Example</h3>
<pre><code>Input:
posts = [
  {
    "id": 1,
    "text": "This is a post 1",
    "replies": [
      {
        "id": 2,
        "replyTo": 1,
        "text": "This is a comment, child to post 1",
        "replies": [
          {
            "id": 3,
            "replyTo": 2,
            "text": "This is a comment, child to comment 2",
            "replies": []
          }
        ]
      },
      {
        "id": 4,
        "replyTo": 1,
        "text": "This is a comment, child to post 1",
        "replies": []
      }
    ]
  },
  {
    "id": 5,
    "text": "This is a post 2",
    "replies": []
  }
]
maxLevel = 1

Output:
[
  { id: 1, text: "This is a post 1" },
  { id: 2, replyTo: 1, text: "This is a comment, child to post 1" },
  { id: 4, replyTo: 1, text: "This is a comment, child to post 1" },
  { id: 5, text: "This is a post 2" }
]

Explanation:
- Level 0: Post 1 and Post 2 are included.
- Level 1: Direct replies to Post 1 (id 2, id 4) are included.
- Level 2: id 3 is a reply to id 2, but since maxLevel = 1, it is not included.
</code></pre>


---

## 92. Accordion

- Source Number: 92
- Slug: `react-accordian-frontend-interview`
- Date: `2025-05-26T20:40:40`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.37.42-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1760" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.37.42-PM.png" alt="Build a simple accordion in React" width="623" height="321" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.37.42-PM.png 623w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.37.42-PM-300x155.png 300w" sizes="(max-width: 623px) 100vw, 623px" /></p>
<p>Implement an <strong>Accordion</strong> component in React. An accordion is a vertically stacked set of expandable items. Each item has a title and can be toggled to show or hide its content. You are given an array of accordion items, each with a unique <code>id</code>, a <code>title</code>, a <code>collapsed</code> boolean, and a <code>content</code> function returning a React node.</p>
<h3>Requirements</h3>
<ul>
<li>Render all accordion items in a vertical list.</li>
<li>Match the UI above</li>
<li>Each accordion item shows its <code>title</code> and a &#8220;Show&#8221; or &#8220;Hide&#8221; button depending on its collapsed state.</li>
<li>Clicking the button toggles the visibility (<code>collapsed</code>) of that item&#8217;s content only.</li>
<li>Render the item&#8217;s <code>content()</code> inside the expanded region when not collapsed. When collapsed, the content should not be visible but should remain mounted.</li>
<li>The list can have any number of items, and all items are independently expandable/collapsible.</li>
<li>Each item must have appropriate ARIA roles and properties for accessibility (e.g., <code>aria-expanded</code>, <code>aria-controls</code>, <code>role="region"</code>, etc).</li>
<li>Do <b>not</b> use max-height transitions or animations (simple toggle only).</li>
<li>Do <b>not</b> mutate the original data array.</li>
</ul>
<h3>Input</h3>
<pre><code>
accordionItems: Array&lt;{
  id: string,
  title: string,
  collapsed: boolean,
  content: () =&gt; React.ReactNode
}&gt;
</code></pre>
<h3>Output</h3>
<pre><code>
// Renders an accessible accordion UI. Each item displays its title, a toggle button, and content that is conditionally visible based on collapsed state.
</code></pre>
<h3>Example</h3>
<pre><code>
Given:
accordionItems = [
  {
    title: 'Accordion Item 1',
    id: 'accordion-item-1',
    collapsed: true,
    content: () =&gt; &lt;p&gt;Accordion Item 1 Content&lt;/p&gt;
  },
  {
    title: 'Accordion Item 2',
    id: 'accordion-item-2',
    collapsed: true,
    content: () =&gt; &lt;p&gt;Accordion Item 2 Content&lt;/p&gt;
  }
]</code></pre>
<p>&#8211; The page displays two vertically stacked items, each with a title and a button labeled &#8220;Show&#8221;.<br />
&#8211; Clicking &#8220;Show&#8221; on &#8220;Accordion Item 1&#8221; expands the first item, changes the button label to &#8220;Hide&#8221;, and reveals its content below the title.<br />
&#8211; Clicking &#8220;Hide&#8221; collapses the item again.<br />
&#8211; Each item is controlled</p>
<pre><code>
</code></pre>


---

## 93. Progress Bar

- Source Number: 93
- Slug: `progress-bar-react-interview-question`
- Date: `2025-05-26T20:45:23`
- Difficulty: Easy
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.47.14-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1765" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.47.14-PM.png" alt="React Progress Bar Frontend Interview Question" width="415" height="133" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.47.14-PM.png 415w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.47.14-PM-300x96.png 300w" sizes="(max-width: 415px) 100vw, 415px" /></p>
<p>Create a <strong>progress/loading bar</strong> component in React. The component should visually indicate progress based on a percentage (0-100), support both controlled and automatic modes, and be accessible. The progress bar must be animated and show progress updates smoothly.</p>
<h3>Requirements</h3>
<ul>
<li>The progress bar must be implemented as a reusable React functional component.</li>
<li>It should accept a <code>value</code> prop (number, 0-100) to set progress percentage, and an optional <code>auto</code> boolean prop.</li>
<li>If <code>auto</code> is true, the bar should automatically animate from 0% to 100% over 5 seconds, then reset.</li>
<li>When the <code>value</code> prop changes, the bar should update smoothly using CSS transitions.</li>
<li>The component must include an accessible <code>role="progressbar"</code>, <code>aria-valuenow</code>, <code>aria-valuemin</code>, and <code>aria-valuemax</code>.</li>
<li>The progress percentage (e.g., “50%”) should be displayed as text above or inside the bar for visual feedback.</li>
<li>Use React state and effects appropriately; do not mutate props or data directly.</li>
<li>Do not use any third-party UI libraries.</li>
</ul>
<h3>Input</h3>
<pre><code>
ProgressBar props:
- value: number (between 0 and 100)
- auto?: boolean (default: false)
</code></pre>
<h3>Output</h3>
<pre><code>
// Renders a horizontal progress/loading bar that visually fills up to the specified percentage.
</code></pre>
<h3>Example</h3>
<pre><code>
&lt;ProgressBar value={50} /&gt;
// Renders a bar that is half-filled, displaying "50%" as text.

&lt;ProgressBar auto /&gt;
// Bar animates smoothly from 0% to 100% over 5 seconds, then resets and loops.
</code></pre>
<h3>Accessibility Requirements</h3>
<pre><code>
- The progress bar must use <code>role="progressbar"</code>. - Set <code>aria-valuenow</code> to the current percentage, <code>aria-valuemin="0"</code>, and <code>aria-valuemax="100"</code>. - The progress percentage should be visible as text for screen readers and sighted users. </code></pre>
<h3>Explanation</h3>
<pre><code>
- In controlled mode (<code>value</code> prop), the progress bar should respond to changes in <code>value</code> with a smooth width transition. - In auto mode (<code>auto</code> prop), the component manages its own state, filling from 0 to 100 over 5 seconds, then resetting. - Use CSS for the bar's appearance and transitions. - Bar must be responsive and visually clear at all percentages. </code></pre>


---

## 94. Star Rating System

- Source Number: 94
- Slug: `star-rating-component-react`
- Date: `2025-05-26T20:54:19`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.55.57-PM-1.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<h2><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1772" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.55.57-PM-1.png" alt="Star Rating System React Component" width="441" height="167" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.55.57-PM-1.png 441w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-1.55.57-PM-1-300x114.png 300w" sizes="(max-width: 441px) 100vw, 441px" /></h2>
<p>Build a reusable <strong>Star Rating</strong> React component that lets users select a rating between 1 and 5 stars. Use the provided SVG for rendering each star. The component must support mouse, touch, and keyboard interactions for accessibility, and visually indicate the current rating (and hover state).</p>
<h3>Requirements</h3>
<ul>
<li>The component should display 5 clickable stars in a horizontal row.</li>
<li>Render each star using the provided SVG. Change its color or fill when selected or hovered.</li>
<li>Allow users to set their rating by clicking (or tapping) a star. All stars up to and including the selected one become filled.</li>
<li>Display the current rating as a number (e.g., &#8220;3/5&#8221;) next to the stars.</li>
<li>Support keyboard navigation: left/right arrow keys move the highlight, Enter/Space selects the rating.</li>
<li>Support resetting to zero by clicking the current selected star again or pressing Escape.</li>
<li>Add proper ARIA roles and properties (<code>role="radiogroup"</code> for the container, <code>role="radio"</code> and <code>aria-checked</code> for each star).</li>
<li>Do not use any third-party UI or icon libraries.</li>
</ul>
<h3>Input</h3>
<pre><code>
No input props required. All state is managed internally.
</code></pre>
<h3>Output</h3>
<pre><code>
// Renders a 5-star rating UI. Users can set their rating (0-5) via mouse, keyboard, or touch.
</code></pre>
<h3>Provided SVG</h3>
<pre><code>
const StarSVG = ({ filled }) =&gt; (
  &lt;svg width="32" height="32" viewBox="0 0 20 20" fill={filled ? "#fbbf24" : "none"} stroke="#fbbf24" strokeWidth="1.5"&gt;
    &lt;polygon points="10,2 12.59,7.95 19,8.66 14,13.14 15.18,19.02 10,16 4.82,19.02 6,13.14 1,8.66 7.41,7.95" /&gt;
  &lt;/svg&gt;
);
</code></pre>
<h3>Example</h3>
<pre><code>
- The UI shows five stars and a text "3/5" when the user clicks the third star.
- Hovering on a star highlights all stars up to that star (without selecting).
- Arrow keys move the hover/focus state; Enter/Space selects; Escape clears.
- Clicking the same star twice clears the selection (sets to zero).
</code></pre>
<h3>Accessibility Requirements</h3>
<pre><code>
- Use <code>role="radiogroup"</code> on the container. - Each star uses <code>role="radio"</code> and <code>aria-checked</code>. - Manage <code>tabIndex</code> for keyboard navigation. - Show current rating visually and as <code>aria-label</code>. </code></pre>
<h3>Explanation</h3>
<pre><code>
- Users should be able to select a rating, clear it, and visually see their selection.
- The component must be accessible for screen readers and keyboard users.
- Visual feedback must be clear for both selected and hovered stars.
</code></pre>


---

## 95. Emoji Selector

- Source Number: 95
- Slug: `react-emoji-selector`
- Date: `2025-05-26T21:01:47`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 3 months, 6 months
- Featured Image: N/A
- Company: N/A
- Category: App Design
- Type: React

### Content

<h2><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1776" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.03.09-PM.png" alt="Emoji Selector React" width="602" height="199" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.03.09-PM.png 602w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.03.09-PM-300x99.png 300w" sizes="(max-width: 602px) 100vw, 602px" /></h2>
<p>Implement a Facebook-style <strong>Emoji Reaction Selector</strong> in React. The selector should display a row of emoji buttons representing different reactions (e.g., Like, Love, Haha, Wow, Sad, Angry). When the user hovers over an emoji, it animates to grow larger above the rest. Clicking an emoji selects it and visually marks it as the chosen reaction.</p>
<h3>Requirements</h3>
<ul>
<li>Display a horizontal row of emoji buttons, each rendered with a custom SVG.</li>
<li>When a user hovers over an emoji, smoothly animate it to become larger and float slightly above the row; other emojis remain at their normal size.</li>
<li>On mouse leave, the emoji shrinks back to its normal size and position.</li>
<li>Clicking an emoji selects it as the user&#8217;s reaction. The selected emoji remains visually highlighted until a new one is chosen.</li>
<li>Keyboard navigation: Left/right arrows move focus between emojis, Enter/Space selects.</li>
<li>Apply <code>role="radiogroup"</code> to the container and <code>role="radio"</code>, <code>aria-checked</code> to each emoji for accessibility.</li>
<li>All state is managed internally; do not require external props.</li>
<li>Do not use third-party icon libraries; use only the provided SVGs.</li>
</ul>
<h3>Provided Emoji SVGs</h3>
<pre><code>
// Like
const LikeSVG = ({ size }) =&gt; (
  &lt;svg width={size} height={size} viewBox="0 0 32 32" fill="#3578e5"&gt;
    &lt;path d="M28 16c0-6-6-12-12-12S4 10 4 16c0 6 6 12 12 12s12-6 12-12z"/&gt;
    &lt;path d="M16 22l6-8h-4V8h-4v6h-4z" fill="#fff"/&gt;
  &lt;/svg&gt;
);

// Love
const LoveSVG = ({ size }) =&gt; (
  &lt;svg width={size} height={size} viewBox="0 0 32 32"&gt;
    &lt;path d="M16 29s-13-8.35-13-16A7 7 0 0 1 16 8a7 7 0 0 1 13 5c0 7.65-13 16-13 16z" fill="#f55376"/&gt;
  &lt;/svg&gt;
);

// Haha
const HahaSVG = ({ size }) =&gt; (
  &lt;svg width={size} height={size} viewBox="0 0 32 32"&gt;
    &lt;circle cx="16" cy="16" r="15" fill="#fbc02d"/&gt;
    &lt;ellipse cx="11" cy="13" rx="2" ry="3" fill="#6d4c41"/&gt;
    &lt;ellipse cx="21" cy="13" rx="2" ry="3" fill="#6d4c41"/&gt;
    &lt;path d="M10 20c2 2 10 2 12 0" stroke="#6d4c41" strokeWidth="2" fill="none"/&gt;
    &lt;ellipse cx="16" cy="22" rx="4" ry="2" fill="#fff"/&gt;
  &lt;/svg&gt;
);

// Wow
const WowSVG = ({ size }) =&gt; (
  &lt;svg width={size} height={size} viewBox="0 0 32 32"&gt;
    &lt;circle cx="16" cy="16" r="15" fill="#fbc02d"/&gt;
    &lt;ellipse cx="11" cy="14" rx="2" ry="2.5" fill="#6d4c41"/&gt;
    &lt;ellipse cx="21" cy="14" rx="2" ry="2.5" fill="#6d4c41"/&gt;
    &lt;ellipse cx="16" cy="21" rx="3" ry="4" fill="#fff"/&gt;
    &lt;ellipse cx="16" cy="22" rx="1" ry="2" fill="#6d4c41"/&gt;
  &lt;/svg&gt;
);

// Sad
const SadSVG = ({ size }) =&gt; (
  &lt;svg width={size} height={size} viewBox="0 0 32 32"&gt;
    &lt;circle cx="16" cy="16" r="15" fill="#fbc02d"/&gt;
    &lt;ellipse cx="11" cy="14" rx="2" ry="2" fill="#6d4c41"/&gt;
    &lt;ellipse cx="21" cy="14" rx="2" ry="2" fill="#6d4c41"/&gt;
    &lt;path d="M12 23c2-2 6-2 8 0" stroke="#6d4c41" strokeWidth="2" fill="none"/&gt;
  &lt;/svg&gt;
);

// Angry
const AngrySVG = ({ size }) =&gt; (
  &lt;svg width={size} height={size} viewBox="0 0 32 32"&gt;
    &lt;circle cx="16" cy="16" r="15" fill="#eb5a46"/&gt;
    &lt;ellipse cx="11" cy="14" rx="2" ry="2" fill="#6d4c41"/&gt;
    &lt;ellipse cx="21" cy="14" rx="2" ry="2" fill="#6d4c41"/&gt;
    &lt;path d="M12 22c2 1 6 1 8 0" stroke="#6d4c41" strokeWidth="2" fill="none"/&gt;
    &lt;path d="M10 12l2-2m8 2l-2-2" stroke="#6d4c41" strokeWidth="2"/&gt;
  &lt;/svg&gt;
);
</code></pre>
<h3>Example</h3>
<pre><code>
- On hover, the hovered emoji smoothly grows larger and floats above others.
- When clicked, the emoji becomes the selected reaction (remains highlighted).
- Keyboard users can navigate and select emojis; the UI remains accessible.
</code></pre>
<h3>Accessibility Requirements</h3>
<pre><code>
- Use <code>role="radiogroup"</code> on the container. - Each emoji uses <code>role="radio"</code>, <code>aria-checked</code>, and proper <code>tabIndex</code>. - Keyboard navigation: left/right arrows, Enter/Space to select. </code></pre>
<h3>Explanation</h3>
<pre><code>
- The component must visually and interactively match Facebook’s emoji selector for reactions.
- Animations and accessibility are required for a production-ready UI.
</code></pre>


---

## 96. Connect Four

- Source Number: 96
- Slug: `react-connect-four`
- Date: `2025-05-26T21:11:00`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.16.32-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1781" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.16.32-PM.png" alt="Connect Four React" width="561" height="591" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.16.32-PM.png 561w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.16.32-PM-285x300.png 285w" sizes="(max-width: 561px) 100vw, 561px" /></p>
<p>Build a playable <strong>Connect Four</strong> game as a React component. Connect Four is a two-player game where players alternate dropping colored discs into a 7-column, 6-row vertically suspended grid. The discs fall straight down, occupying the lowest available cell within the chosen column. The first player to form a horizontal, vertical, or diagonal line of four of their own discs wins the game.</p>
<h3>Requirements</h3>
<ul>
<li>Render a 7&#215;6 grid representing the Connect Four board.</li>
<li>Two players take turns (Player 1: Red, Player 2: Yellow).</li>
<li>Clicking on a column drops the current player&#8217;s disc into the lowest empty cell in that column.</li>
<li>After each move, check for a win: four consecutive discs in any direction (horizontal, vertical, or diagonal).</li>
<li>When a player wins, display a message and highlight the winning line. No further moves should be allowed.</li>
<li>If the board fills up without a winner, display a draw message.</li>
<li>Include a &#8220;Restart&#8221; button to reset the board and start a new game.</li>
<li>All state must be managed internally.</li>
<li>Do not use any third-party libraries for game logic or UI.</li>
</ul>
<h3>Input</h3>
<pre><code>
No input props. The component manages its own state.
</code></pre>
<h3>Output</h3>
<pre><code>
// Renders a playable Connect Four game UI in React.
</code></pre>
<h3>Example</h3>
<pre><code>
- The UI displays a 7x6 grid.
- Clicking on a column places a red or yellow disc, alternating turns.
- If a player gets four in a row (any direction), a message "Player X wins!" is shown and the four discs are highlighted.
- If the board is filled with no winner, "Draw!" is shown.
- A "Restart" button resets the board and the game.
</code></pre>
<h3>Accessibility Requirements</h3>
<pre><code>
- Each cell must be accessible and labeled for screen readers (e.g., "Row 3, Column 4, empty", "Row 3, Column 4, Red disc").
- The grid should be navigable via keyboard (optional but recommended for extra credit).
- Visual focus and selection states should be clear.
</code></pre>
<h3>Explanation</h3>
<pre><code>
- State should be represented as a 2D array: board[row][col].
- On each move, update state and check for a win or draw.
- Highlight the four-in-a-row when a player wins.
- The UI should be visually clear and intuitive to play.
</code></pre>


---

## 97. Data List

- Source Number: 97
- Slug: `data-list`
- Date: `2025-05-26T21:30:12`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.35.28-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1786" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.35.28-PM.png" alt="Data list React Interview" width="804" height="443" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.35.28-PM.png 804w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.35.28-PM-300x165.png 300w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.35.28-PM-768x423.png 768w" sizes="(max-width: 804px) 100vw, 804px" /></p>
<p>Your task is to update the DataTable so that each column can optionally display a filter input directly within its header. These filter inputs let users narrow down visible rows by entering specific criteria for each column. Filters can be combined—only rows that satisfy <strong>all</strong> active filter conditions should be displayed.</p>
<h3>Filtering Rules</h3>
<ul>
<li><strong>String columns</strong>: Show a text input. Rows should be included if their value for that column contains the entered text (case-insensitive).</li>
<li><strong>Numeric columns</strong>: Show two number inputs labeled &#8220;Min&#8221; and &#8220;Max.&#8221; Rows should be included only if their value falls within the entered range. If either min or max is left blank or invalid, ignore that boundary.</li>
<li>If a filter field is empty or invalid, do not apply that filter to the data.</li>
<li>All filters are cumulative—rows must match every active filter to be shown.</li>
</ul>
<h3>Component Flexibility</h3>
<ul>
<li>The DataTable should remain fully reusable. You must not hardcode any data or filter logic—configuration must come from the <code>columns</code> array and <code>data</code> props.</li>
<li>Filtering must work in combination with sorting and pagination; users should be able to filter, sort, and page through data at the same time.</li>
<li>The filter inputs should be visually integrated into the table header and styled for clarity and usability.</li>
</ul>
<h3>Examples</h3>
<pre><code>
- Typing "alex" into the "Name" filter should instantly show only users whose names contain "alex" (e.g., "Alexander Hall").
- Entering Min = 30 and Max = 40 in the "Age" filter should only show users whose ages are between 30 and 40.
- Combining filters (e.g., Name="an", Age Min=35) narrows results to users matching both conditions.
</code></pre>
<h3>Accessibility</h3>
<ul>
<li>All filter inputs and controls must be keyboard accessible and have clear labels or placeholders.</li>
</ul>
<h3>Design Goal</h3>
<p>Your solution should deliver a fast, intuitive, and visually appealing experience for exploring tabular data. Think about how real-world productivity apps handle table filtering—aim for that level of polish!</p>


---

## 98. Signup Form

- Source Number: 98
- Slug: `react-signup-form`
- Date: `2025-05-26T21:39:52`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.41.01-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1791" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.41.01-PM.png" alt="Email Form React Component" width="551" height="427" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.41.01-PM.png 551w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.41.01-PM-300x232.png 300w" sizes="(max-width: 551px) 100vw, 551px" /></p>
<p>Build a modern sign-up form as a React component. The form should collect the user&#8217;s email address and password, and include robust email validation. When the user submits the form, validate the inputs and provide clear feedback if any field is invalid. If all validations pass, display a success message instead of the form.</p>
<h3>Requirements</h3>
<ul>
<li>Render a sign-up form with the following fields:
<ul>
<li>Email address (required, must be a valid email format)</li>
<li>Password (required, at least 8 characters)</li>
</ul>
</li>
<li>Validate the email using a standard regular expression (use the most popular regex from Google for email validation)</li>
<li>Display real-time error messages below each field as the user types</li>
<li>Disable the submit button until both fields are valid</li>
<li>On successful submit, display a &#8220;Sign up successful!&#8221; message instead of the form</li>
<li>Do not use any third-party form libraries</li>
</ul>
<h3>Accessibility</h3>
<ul>
<li>Each input must be labeled and accessible by keyboard and screen reader</li>
<li>Errors must be associated with the corresponding input</li>
</ul>
<h3>Example</h3>
<pre><code>
- Typing an invalid email immediately shows an error message.
- Typing a short password (less than 8 chars) shows a password error.
- The submit button remains disabled until both fields are valid.
- Upon successful submission, "Sign up successful!" is shown.
</code></pre>


---

## 99. Authentication Code

- Source Number: 99
- Slug: `authentication-code-component-react`
- Date: `2025-05-26T21:46:25`
- Difficulty: Medium
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.46.45-PM.png
- Company: N/A
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1795" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.46.45-PM.png" alt="authentication code component react" width="481" height="339" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.46.45-PM.png 481w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.46.45-PM-300x211.png 300w" sizes="(max-width: 481px) 100vw, 481px" /></p>
<p>Design a React component that allows the user to enter a 6-digit authentication code (OTP) typically sent via email or SMS. The component should render 6 separate input boxes, each accepting only a single digit (0-9). As the user types, focus should automatically advance to the next input, and backspace should move focus to the previous box. Validate that all 6 digits are filled before enabling the &#8220;Verify&#8221; button. Display a clear error message if the code is incomplete or contains any non-digit character.</p>
<h3>Requirements</h3>
<ul>
<li>Render 6 input boxes in a row; each box accepts only one digit (0-9).</li>
<li>As the user types, focus moves automatically to the next input. Backspace moves to the previous input.</li>
<li>Allow the user to paste the full 6-digit code into any input; it should populate all boxes in order.</li>
<li>The &#8220;Verify&#8221; button is disabled unless all 6 digits are filled (and valid digits).</li>
<li>On submit, display a success message if valid, or a clear error if not.</li>
<li>Component must be fully keyboard accessible and screen reader friendly.</li>
</ul>
<h3>Example</h3>
<pre><code>
- User can type or paste "123456" and see each digit appear in a separate box.
- Typing "abc" or a special character is ignored.
- Clicking "Verify" with less than 6 digits shows an error.
</code></pre>


---

## 100. Build ChatGPT

- Source Number: 100
- Slug: `build-gpt-react`
- Date: `2025-05-26T21:52:52`
- Difficulty: Hard
- Premium: Yes
- Coming Soon: No
- Subtitle: N/A
- Video Link: N/A
- Study Plan: 6 months
- Featured Image: https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.54.27-PM.png
- Company: OpenAI
- Category: App Design
- Type: React

### Content

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-1804" src="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.55.29-PM.png" alt="Build Chat GPT React Component" width="608" height="413" srcset="https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.55.29-PM.png 608w, https://api.frontendlead.com/wp-content/uploads/2025/05/Screenshot-2025-05-26-at-2.55.29-PM-300x204.png 300w" sizes="(max-width: 608px) 100vw, 608px" /></p>
<p>Build a fully interactive ChatGPT-like chat UI in React that streams AI assistant responses word-by-word or character-by-character, just like the real ChatGPT experience. The chat should support multi-line messages, animated streaming for GPT responses, and a clean user interface for both user and AI messages. As the AI &#8220;types,&#8221; each word (or character) should appear in sequence with a short delay, mimicking the streaming effect of modern AI chatbots.</p>
<h3>Requirements</h3>
<ul>
<li>Allow the user to submit multi-line chat messages.</li>
<li>User messages should appear immediately in the chat log, right-aligned and styled differently from AI responses.</li>
<li>AI (GPT) responses should be &#8220;streamed&#8221; into the chat: reveal the response text word-by-word or character-by-character with a delay for each word/character.</li>
<li>The AI message should support multi-line responses (render <code>\n</code> as new lines).</li>
<li>Show a loading indicator (&#8220;GPT is typing&#8230;&#8221;) while the assistant response is being streamed.</li>
<li>The chat log should auto-scroll to the newest message.</li>
<li>UI must be accessible: screen reader-friendly, labeled, and keyboard-navigable.</li>
<li>No third-party UI frameworks for the chat/animation—use plain React and CSS.</li>
</ul>
<h3>Example</h3>
<pre><code>
- User types: "Tell me a joke" and presses Send.
- Their message instantly appears on the right.
- GPT "types" its reply word by word with a fade-in animation.
- Loading indicator shows while GPT is streaming.
</code></pre>

