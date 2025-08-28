1. Tell me about yourself (shortened):
   I’m a Senior Full Stack Engineer with 12+ years of experience building .com websites using HTML5, CSS3, JavaScript, React.js, and Redux.
   For the last 2 years at United Airlines, I’ve been on the React migration team converting .NET pages to React using our in-house ATMOS library. I delivered several security and account management features like Forgot Password, MileagePlus sign-in, Miles-Pooling, TSA Precheck, Known Traveler Number (KTN), and WCAG accessibility updates. Redux-Saga handled our async flows for data fetching and API calls.
   Key initiatives included Miles-Pooling (rewards sharing), TSA Precheck integration, Under18 account restrictions, and enhanced account security.
   Previously:
   • Visa Inc. – Migrated MBDA modules (Application Mgmt, Portfolio Mgmt, Billing, Analytics) for Wells Fargo, Bank of America.
   • Capital Group – Built Highcharts data visualizations in React, integrated with AEM, and created Creative Workbench for article publishing.
   • Cerner – Developed medical examination forms.
   • Office Depot – Built Black Friday reporting tools.
   • Satinos Technologies – Developed a tax portal and school website for Vignan Schools.

2. Core React Hooks
   • useState, useEffect – For state management and side effects (data fetching, DOM updates).
   • useRef – For accessing DOM elements and storing mutable values without re-rendering.
   • useContext – For global state and theme/config sharing without prop drilling.
   • useMemo, useCallback – For performance optimization, memoizing expensive calculations and stable callbacks.

Custom Hooks
• Built custom hooks to handle reusable logic like API calls with error/loading states, form validations, and managing authentication flows.
Advanced Scenarios
• Combined hooks with Redux-Saga for async workflows like fetching user profiles, Miles-Pooling transactions, TSA Precheck data.
• Used hooks to trigger accessibility improvements (e.g., focusing error elements for WCAG compliance).
• Integrated hooks with Highcharts for data visualizations at Capital Group.

3. simplest JavaScript code for sum(3,4,5):
   function sum(...nums) {
   return nums.reduce((total, num) => total + num, 0);
   }
   console.log(sum(3, 4, 5)); // Output: 12

4. custom hook for sorting: A custom hook for sorting is a reusable function in React that uses hooks like useState and useMemo to manage sorting logic (key, order) and return the sorted data plus functions to control sorting. It keeps components clean and the logic reusable.

5. useMemo vs useCallback
   • useMemo: Caches the result of an expensive calculation so it only recomputes when dependencies change. Example: sorting a big list or computing derived data.
   • useCallback: Caches the function itself so React doesn’t create a new function on every render. Example: passing a stable callback to child components to prevent unnecessary re-renders.
   Both help with performance optimization by reducing re-renders and recomputations.

6. Purpose of useMemo?
   useMemo → Caches values to avoid recalculating expensive results on every render.
   const sorted = useMemo(() => sortData(data), [data]);
   • useCallback → Caches functions so they aren’t recreated on every render, preventing child re-renders.
   • const handleClick = useCallback(() => doSomething(id), [id]);
   Both help with performance optimization:
   • useMemo → Memoize results
   • useCallback → Memoize functions

   ***

7. united airlines what is your role
   I am a core UI Developer with 10+ years of experience building .com websites for different organizations using HTML5, CSS3, JavaScript, React.js, and Redux.
   In the past 2 years, I worked on the React migration team, where I converted the .net pages to react on united.com.
   Frontend is React, and used ATMOS (Own library) components used company wide.

used middleware such as redux-saga to handle asynchronous tasks such as API calls, data fetching, and impure actions in a more organized and efficient way.

Worked on Security features for users where they can manage there account like Forgot password, Forgot MileagePlus number, security questions, Sign-in features, Miles-Pooling, United Club pass, Recent Activity, dashboard updates and KTN(Known Traveler Number), Accessibility guidelines features on united.com.

The new initiative worked on Miles-Pooling( points you get after traveling), TSA Precheck, Account security and management features, and Under18.

2. React standalone components
   Reusable, isolated pieces of UI that don’t depend on global state. Props in/out, no hidden side effects.

3. Redux vs Zustand
   Redux → predictable, boilerplate heavy, great for large apps.
   Zustand → lightweight, minimal API, easier setup, simpler for smaller/mid apps.

4. Can we mix Redux with Zustand?
   Yes. You can use Redux for global/shared state and Zustand for local/feature-specific state.

5. Values between micro frontends
   Shared via event bus, custom DOM events, or shared storage (localStorage/sessionStorage/Context APIs exposed).

6. State management in micro frontends
   Decentralized. Each microfrontend manages its own state. For shared state, use cross-frontend store (Redux, Zustand) or message bus.

7. Tools for microfrontend
   Webpack Module Federation, Single-SPA, Nx, Bit, Lerna.

8. Microfrontend architecture in React
   Each team builds independently deployable React apps, stitched together using Module Federation or a container shell.

9. Publishing npm library
   Build reusable components → bundle with Rollup/Webpack → version and publish to npm (public or private registry).

10. Service impact during migration
    Need backward compatibility. Old services must support both old (.NET) and new (React) clients until migration is complete.

11. Architecting .NET component to React
    Break monolith UI into React components. Mirror business logic in APIs, keep UI logic in React.

12. .NET component equivalent in React
    .NET user controls map to React components. Shared libraries map to npm packages.

13. Rendering mechanism .NET vs React
    .NET (Razor/WebForms) → server-side rendering.
    React → client-side rendering (with option for SSR using Next.js).

14. Why choose React?
    Component-based, fast virtual DOM, strong ecosystem, reusable, easier scaling compared to tightly coupled server-side rendering.

15. Migrating .NET → React: evaluating components
    Identify reusable UI patterns, decouple business logic into APIs, convert UI to React functional components.

16. Best practice for token storage
    Short-lived access token in memory, refresh token in httpOnly cookie. Avoid localStorage for security.

17. Where it’s stored?
    Access token → memory (Redux/Zustand).
    Refresh token → secure httpOnly cookie.

18. PKCE flow
    PKCE = Proof Key for Code Exchange. Adds code verifier + challenge to OAuth for securing SPA/public clients.

19. OAuth flow library used?
    oidc-client-ts, react-oauth2-pkce, or Auth0 SDKs.

20. Difference between .NET vs React architecture
    .NET → monolithic, server-rendered, tightly coupled UI + backend.
    React → client-side, component-driven, API-first, decoupled from backend.

=======================================

Technical interview: ventleytech/capgemini/comcast

1. current project explain?
2. In RTL what is act?
   act() ensures all React updates (state, effects) are flushed before making assertions. It wraps test code so you don’t get warnings about async updates.

3. Which testing libraries did you use?
   Jest for test runner, React Testing Library for component testing, Enzyme for legacy, Cypress/Playwright for end-to-end.

4. i18n? how did you implement in frontend?
   Used react-i18next. Wrapped app in I18nextProvider, created translation JSON files per locale, switched language dynamically using the hook useTranslation.

5. What is the build tool you used for United?
   Webpack 5 with Module Federation for microfrontends. Also used Babel + ESLint integrated into the build.

6. How did you add validation to input fields in React?
   Two approaches:

Controlled components with custom validation logic.

Libraries like Formik + Yup or react-hook-form for schema-based validation.

7. Authentication mechanism did you use in United?
   OAuth2 with PKCE. Access token stored in memory, refresh token in secure httpOnly cookie. Used oidc-client-ts for flow handling.

=================

## Interview Questions & Answers (Short)

### 1. Introduce yourself? Total years of experience?

I’m a Full Stack UI Developer with **12+ years of experience**, skilled in React, Angular, JavaScript, TypeScript, Node.js, and AWS-based microservices.

---

### 2. JavaScript is synchronous or asynchronous?

JavaScript is **synchronous by default**, but supports **asynchronous behavior** using callbacks, Promises, and `async/await`.

---

### 3. What is asynchronous call? How to make async call?

An asynchronous call runs in the background without blocking the main thread.  
You can make one using:

- `setTimeout`
- `fetch` (returns a Promise)
- `async/await`

---

### 4. Callback?

A **callback** is a function passed into another function as an argument, to be executed later after an operation completes.

---

### 5. Callback hell?

Occurs when callbacks are nested within callbacks, making code messy and unreadable.  
**Solution**: Use Promises or `async/await` for cleaner, linear flow.

---

### 6. call, apply, bind? Where did you use?

Used to control the `this` context inside functions.

- `call()`: Calls a function with a specified `this` and arguments.
- `apply()`: Like `call`, but takes arguments as an array.
- `bind()`: Returns a new function with bound `this`.

**Used `bind`** in React class components to bind event handlers.
call() — For function borrowing, apply() — When args are in an array, 3. bind() — To fix this in advance

## Interview Questions & Answers (Part 2)

### 7. Coding Question

```js
const test = [[1, 2, 3], [4, 5, [5, false, 6, [5, 8, null]]], [6]];

function flattenArray(arr) {
  const result = [];

  function helper(subArr) {
    for (let item of subArr) {
      if (Array.isArray(item)) {
        helper(item);
      } else {
        result.push(item);
      }
    }
  }

  helper(test);
  console.log(result);
}
```

## Interview Questions & Answers (8–15)

### 8. React: Functional or Class — which have you used?

I’ve primarily used **functional components** with hooks in recent projects. I’ve also worked with **class components** in legacy codebases.

---

### 9. State management — how did you achieve it?

- For local state: `useState`, `useReducer`
- For shared/global state: Redux Toolkit, Context API
- For async/server state: React Query
- Also used Zustand in a lightweight scenario

---

### 10. Have you worked on class components?

Yes. I’ve used class components in earlier projects and worked with lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

---

### 11. Lifecycle Methods Using Hooks (equivalent to Class)

```js
// componentDidMount
useEffect(() => {
  // code to run on mount
}, []);

// componentDidUpdate
useEffect(() => {
  // code to run on update
}, [dependency]);

// componentWillUnmount
useEffect(() => {
  return () => {
    // cleanup code
  };
}, []);
```

## Interview Questions & Answers (12–15)

### 12. Hooks — have you worked with them? Which?

Yes. I’ve worked with the following hooks:

- `useState` – for managing local state
- `useEffect` – for side effects and lifecycle behavior
- `useContext` – for accessing shared context
- `useRef` – for referencing DOM elements or storing mutable values
- `useReducer` – for complex state logic
- `useMemo` – to memoize expensive computations
- `useCallback` – to memoize functions

---

### 13. useMemo vs useCallback — Difference?

| Hook          | Purpose                                | Returns  |
| ------------- | -------------------------------------- | -------- |
| `useMemo`     | Caches the **result** of a computation | Value    |
| `useCallback` | Caches the **function** itself         | Function |

- Use `useMemo` to avoid re-calculating expensive values unless dependencies change.
- Use `useCallback` to avoid recreating functions on each render, especially when passing them to child components.

---

### 14. How to pass data from child to parent?

You pass a callback from parent to child. The child calls that function with the data:

```js
// Parent
const handleData = (value) => setState(value);
<Child onSendData={handleData} />;

// Child
props.onSendData("data from child");
```

### 15. Other than Redux and Context — how to manage state?

Here are alternative ways to manage state in React:

- **Zustand** – A small, fast, and scalable global state management library without boilerplate.
- **Jotai** – Atomic state model. Each piece of state is an individual unit (atom) that can be shared.
- **Recoil** – Provides fine-grained state control using atoms/selectors. Good for complex global state needs.
- **React Query (TanStack Query)** – Manages **server state** like API data: caching, fetching, updating.
- **useReducer + Context** – Combine both to create a basic global state system without external libs.

<!-- const test = [[1, 2, 3], [4, 5, [5, false, 6, [5, 8, null]]], [6]]
//convert array to single array without flat method

const flattAray = (arr) => {
const result = [];

    for (const item of arr) {
        if (Array.isArray(item)) {
            result.push(...flattAray(item));
        } else {
            result.push(item);
        }
    }

    return result;

}
console.log(flattAray(test)); -->

---

## 1. Introduce Yourself?

I'm a Full Stack UI Developer with 12+ years of experience building scalable, accessible, and performant web apps. My stack includes React, Angular, Node.js, TypeScript, Redux, GraphQL, and AWS services.

## 2. Did You Work on Agile Methodology?

Yes. Participated in daily stand-ups, sprint planning, backlog grooming, retrospectives. Worked closely with product owners and QA in 2-week sprint cycles.

## 3. How Did You Mentor Peers?

Conducted onboarding sessions, paired programming, architecture walkthroughs, and regular knowledge-sharing meetings. Reviewed code and helped improve code quality and best practices.

## 4. Code Review?

Yes. Focused on readability, performance, security, modularity, and adherence to project standards. Used GitHub/Bitbucket for PR reviews and comments.

## 5. BFF (Backend for Frontend)?

Yes. Created custom Node.js/GraphQL layers to aggregate and shape data for specific frontend needs, improving performance and reducing client-side logic.

## 6. MFA (Multi-Factor Authentication)?

Implemented MFA using Auth0 and AWS Cognito. Supported SMS, email OTP, and authenticator apps for secure logins.

## 7. BFS (Breadth First Search)?

Algorithm to traverse nodes level by level. Use a queue for implementation. Common in trees, graphs, pathfinding problems.

## 8. Coding Question – JSON

Use `fetch("https://dummyjson.com/products")` in React or Node.js to retrieve products and display them using `.map()` or render in table/grid.

## 9. Performance Improvement in React.js?

Used `React.memo`, `useMemo`, `useCallback`, lazy loading, dynamic imports, code splitting, image optimization, and limiting re-renders by lifting state wisely.

## 10. Redux? Which One Did You Work On?

Worked on both classic Redux with `redux-thunk` and modern `Redux Toolkit` (RTK). Prefer RTK for its cleaner syntax, built-in immer, and easier boilerplate reduction.

## React.js Component: Product Table from API

### ✅ Requirements:

- API: `https://dummyjson.com/products`
- Display: `title`, `brand`, `rating`
- Sort: by `title` in ascending order
- Feature: Add delete button per row

---

### 📦 Dependencies:

- React (`useState`, `useEffect`)

---

### 🧠 Logic:

1. Fetch product data on mount using `useEffect`.
2. Sort the products by `title` (A-Z) using `localeCompare`.
3. Store the result in local state (`products`).
4. Render data in a `<table>`.
5. Add a **Delete** button that filters out the product from local state.

---

### 💻 Code:

```jsx
import React, { useEffect, useState } from 'react';

function ProductTable() {
  const [products, setProducts] = useState([]);

  useEffect(() => {
    fetch('https://dummyjson.com/products')
      .then(res => res.json())
      .then(data => {
        const sorted = [...data.products].sort((a, b) =>
          a.title.localeCompare(b.title)
        );
        setProducts(sorted);
      });
  }, []);

  const handleDelete = (id) => {
    setProducts(prev => prev.filter(product => product.id !== id));
  };

  return (
    <div>
      <h2>Product Table</h2>
      <table border="1" cellPadding="10">
        <thead>
          <tr>
            <th>Title (A-Z)</th>
            <th>Brand</th>
            <th>Rating</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          {products.map(({ id, title, brand, rating }) => (
            <tr key={id}>
              <td>{title}</td>
              <td>{brand}</td>
              <td>{rating}</td>
              <td>
                <button onClick={() => handleDelete(id)}>Delete</button>
              </td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}

export default ProductTable;

<!--


import React, { useState, useEffect } from 'react';

export function App(props) {
const [data, setData] = useState([]);
const onSortClick = () => {
setData([...data.sort((a, b) => a.title.localeCompare(b.title))]);
};
const onDeleteClick =() =
useEffect(() => {
fetch('https://dummyjson.com/products').then(res => res.json()).then((res) => setData(res.products))
}, []);

return (
<div className='App'>
<h1>Hello React.</h1>
<h2>Start editing to see some magic happen!</h2>
<table>
<thead>
<tr>
<th onClick={onSortClick}>Title</th>
<th>Brand</th>
<th>Rating</th>
</tr>
</thead>
<tbody>
{data?.map(item => {
return <tr key={item.id}>
<td>{item.title}</td>
<td>{item.brand}</td>
<td>{item.rating}</td>
<td><button onClick={() => onDelecteClick(item.id)}>Delete</button></td>
</tr>
})}
</tbody>
</table>
</div>
);
}

// Log to console
console.log('Hello console')
```

-->

---

## React Interview Questions

---

### 1. What are Hooks?

Hooks let you use React features like state and lifecycle methods inside functional components.

Common Hooks:

- `useState` – Local state
- `useEffect` – Side effects (e.g., data fetching)
- `useRef` – Mutable values & DOM refs
- `useMemo` / `useCallback` – Memoization and function identity
- `useContext` – Access values from context

---

### 2. User Authentication Mechanism?

Typical frontend auth flow:

- Use **JWT** stored in `httpOnly` cookies or `localStorage`
- After login, store the token and use it in the `Authorization` header for API requests
- Protect routes via guards (`PrivateRoute`) or conditional rendering
- For MFA: an extra step after login, usually OTP input

---

### 3. What is the full form of TSX?

**TSX** stands for **TypeScript with JSX**.  
It's a TypeScript file that contains JSX syntax.

---

### 4. Have you worked with React and TypeScript?

Yes. Used in multiple projects:

- Type-safe props and state interfaces
- Utility types (`Partial`, `Record`, `Pick`)
- Better IntelliSense and compile-time safety
- Typed Redux setup using `TypedUseSelectorHook`, action interfaces, etc.

---

### 5. What is `react-scripts`?

Part of **Create React App**.

It provides:

- Preconfigured Webpack setup
- Babel config
- Dev server
- Build scripts

You get a working React setup out of the box.

---

### 6. Have you used Redux?

Yes. Worked with:

- **Redux Toolkit** (`createSlice`, `configureStore`, `createAsyncThunk`)
- Middleware: `redux-thunk`, `redux-saga`
- Selectors using `reselect`
- Connected components using `useSelector` and `useDispatch`

---

### 7. Global State Management? Have you used `useContext`?

Yes.

- For lightweight/global state: used **Context API** with `useContext`
- For complex/async-heavy state: prefer Redux or Zustand

Example use cases: user session, feature flags, theme

---

### 8. How do you pass data between components?

**Parent to Child:** via props

```tsx
<ChildComponent title="Dashboard" />
```

Child to Parent: via callback functions

```tsx
<ChildComponent onUpdate={handleUpdate} />
```

### 9. What is Context API?

Used to share state/data across the component tree without prop drilling.

#### Steps:

- Create context with `createContext()`
- Wrap components in `Context.Provider`
- Consume with `useContext(SomeContext)`

Great for:

- Themes
- Current user info
- Settings

<!-- coding question: currency conversion:

import React, { useState } from "react";
import "./style.css";

const RATES = {
USD: { EUR: 0.86, INR: 86 },
EUR: { USD: 1.16, INR: 93 },
INR: { USD: 0.0125, EUR: 0.0107 }
};

export default function App() {
const [fromCurrency, setFromCurrency] = useState("USD");
const [toCurrency, setToCurrency] = useState("INR");
const [fromAmount, setFromAmount] = useState(1);
const [toAmount, setToAmount] = useState(RATES["USD"]["INR"] \* 1);
const [editing, setEditing] = useState("from");

const handleFromAmount = (e) => {
const val = e.target.value;
setFromAmount(val);
setToAmount((val \* RATES[fromCurrency][toCurrency]).toFixed(2));
setEditing("from");
}

const handleToAmount = (e) => {
const val = e.target.value;
setToAmount(val);
setFromAmount((val / RATES[fromCurrency][toCurrency]).toFixed(2));
setEditing("to");
}

const handleFromCurrency = (e) => {
const newFrom = e.target.value;
setFromCurrency(newFrom);
const rate = RATES[newFrom][toCurrency];
if (editing === "from") {
setToAmount((fromAmount \* rate).toFixed(2));
} else {
setFromAmount((toAmount / rate).toFixed(2));
}
}

const handleToCurrency = (e) => {
const newTo = e.target.value;
setToCurrency(newTo);
const rate = RATES[fromCurrency][newTo];
if (editing === "from") {
setToAmount((fromAmount \* rate).toFixed(2));
} else {
setFromAmount((toAmount / rate).toFixed(2));
}
}

return (
<div>
<h2>Simple Currency Converter</h2>
<div className="amount-from">
<input
          type="number"
          value={fromAmount}
          onChange={handleFromAmount}
        />
<select value={fromCurrency} onChange={handleFromCurrency}>
{Object.keys(RATES).map((c) => (
<option value={c} key={c}>
{c}
</option>
))}
</select>
</div>
<div className="amount-to">
<input
          type="number"
          value={toAmount}
          onChange={handleToAmount}
        />
<select value={toCurrency} onChange={handleToCurrency}>
{Object.keys(RATES).map((c) => (
<option value={c} key={c}>
{c}
</option>
))}
</select>
</div>
</div>
);
}

---

How can you Optimize Performance in React application?

1. Memoization with useMemo and useCallback: Use this hooks to memoize values and, reducing unnecessary recalculations.
2. Optimizing Renders with React.Fragment: Use it to avoid unnecessary wrapper elements that could cause additional DOM nodes.
3. Lazy loading with React.lazy: Use it to load components lazily, reducing the intial bundle size and imporving intial loading performance.
4. Code splitting: Employ code splitting to divide your application into smaller chunks that are loaded on demand, improving initial load times.
5. Optimizing Images and Assets: Compress and optimize images, use responsive images and leverage lazy loading for images to reduce network and rendering overhead.

What are the popular hooks in react and explain it's usage?

useState: Manages state in functional components.
useEffect: Manages side effects in functional components.
useContext: Consumes context in functional components.
useReducer: Manage state with a reducer function, For More complex state management.
useRef: Accesses DOM elements or stores mutable values.
useCallback: performance improvement usecase
useMemo: performance improvement usecase.

```

``` -->

## 1. Tell me about your current project

I’m working on United.com’s React migration project. We’re converting legacy .NET modules to React with a strong focus on accessibility, performance, and security. I lead the UI side—building components using React 18, Redux-Saga, and integrating them with backend services over REST and xAPI. We also embed the frontend into AEM containers for CMS-driven rendering.

## 2. Which hooks did you work on?

I use `useState`, `useEffect`, `useRef`, `useCallback`, `useMemo`, and `useContext` regularly. For example, I use `useMemo` for memoizing heavy computations and `useCallback` for preventing unnecessary re-renders in child components. I also write custom hooks when logic needs to be reused across components.

## 3. Authentication and Authorization—how did you handle it?

For frontend auth, I used tokens (usually JWTs) stored in memory or HTTP-only cookies. Based on user roles returned from the backend, I conditionally render routes and UI elements. On login, we fetch user details and permissions, store them in Redux, and use them for access control in the UI.

## 4. Redux?

Yes, I’ve used both classic Redux and Redux Toolkit. In my current project, we use Redux-Saga for handling async flows like API calls, and selectors for memoization. I organize state using slices and modular patterns, especially in larger applications.

## 5. Which version of React.js?

I’m currently using React 18. I’ve worked with features like automatic batching, concurrent rendering (with Suspense), and improved SSR support. Most projects I’ve led used React 16+ initially, and we've migrated to 18 over time.

## 6. Error boundaries?

Yes, I use class-based components as error boundaries. It helps catch rendering errors in child components without crashing the whole app. I wrap key parts of the UI (like dynamic dashboards or user forms) with error boundaries and log errors using Sentry.

## 7. React with Java—how did you deal?

The React frontend interacts with Java-based backend via REST APIs. We use Axios/fetch to call APIs, handle tokens for auth, and parse JSON responses. I work closely with backend teams to align on contracts and test integration flows using Postman or Swagger before wiring up the UI.

## 8. Virtual DOM vs Real DOM—what's the difference?

The virtual DOM is a lightweight JS copy of the real DOM. React uses it to figure out the minimal changes needed and applies them efficiently to the real DOM. This diffing and batching reduces direct manipulation, making rendering faster and more optimized.

## 9. Internationalization (i18n)?

I’ve used libraries like `react-i18next` for i18n. We create translation JSON files for each language and load them dynamically. I also handled RTL (right-to-left) support and fallback languages. The AEM setup helped manage language content for global sites.

## 10. Route protection in React application?

I use wrapper components or higher-order components that check auth state before rendering routes. For example, a `<PrivateRoute>` checks if the user is authenticated (from Redux or Context), and redirects to login if not. Same goes for role-based routes.

## 11. Multi-step form with persistent data (even on navigation away)?

I manage multi-step form state in Redux or Context. To persist it across sessions or page reloads, I use `localStorage` or `sessionStorage`. Each step updates a slice of the global state, and on submission, we compile and send the complete payload to the backend.

## 12. How to make an API call in frontend?

Typically with Axios or fetch. I structure API calls in service files. In Redux-Saga, I use generator functions to make async calls and dispatch actions based on success or failure. I also show loading spinners and handle error states gracefully.

## 13. Context API?

I’ve used it when the state doesn't require Redux-level complexity—like theme toggles, language switchers, or user session data. I define a context provider and use `useContext` hook to access state in child components.

## 14. How did you integrate frontend and backend process?

We define API contracts first (REST or GraphQL). I use Postman to test them. Once confirmed, I write services in the frontend using Axios, manage state via Redux, and ensure type consistency using TypeScript. I also handle error cases and retry logic for robustness.

## 15. Authentication in backend—how did you implement?

In backend projects with Node or Java, I’ve implemented JWT-based auth. On login, the backend validates credentials, signs a token, and sends it to the frontend. Backend middleware checks for token validity on each request, along with role/permission validation for sensitive endpoints.

## 16. What is a Higher-Order Component (HOC) in React?

A Higher-Order Component (HOC) is a function that takes a component and returns a new component with additional functionality.

Think of it as a pattern for reusing component logic without duplicating code.

### Example:

```jsx
const withLoader = (WrappedComponent) => {
  return function WithLoaderComponent({ isLoading, ...props }) {
    if (isLoading) {
      return <div>Loading...</div>;
    }
    return <WrappedComponent {...props} />;
  };
};

// Usage
const UserListWithLoader = withLoader(UserList);
```

In the example above, `withLoader` is a HOC that wraps any component and adds a loading UI based on props.

## When I used HOC:

At United, I used HOCs to wrap protected routes with auth checks and also to inject layout or common behaviors like error handling, logging, or feature toggling into reusable modules.

## Key Notes:

- HOCs don’t modify the original component—they return a new one.
- **Common use cases**: authentication, layout wrappers, logging, performance monitoring.
- They follow the pattern:
  ```js
  const EnhancedComponent = hoc(WrappedComponent);
  ```

## 17. What are Custom Hooks in React?

Custom Hooks are JavaScript functions that start with `use` and let you reuse stateful logic across multiple components.

They help avoid duplication and keep components clean by abstracting common logic.

---

## Example: `useWindowWidth`

```jsx
import { useState, useEffect } from "react";

function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener("resize", handleResize);

    return () => window.removeEventListener("resize", handleResize);
  }, []);

  return width;
}

// Usage in a component
function Dashboard() {
  const width = useWindowWidth();

  return <div>Current width: {width}px</div>;
}
```

## When I used Custom Hooks:

At United and Visa, I created several custom hooks to manage:

- **Debounced search input** (`useDebounce`)
- **Tracking scroll position** (`useScrollPosition`)
- **Form validation logic** (`useFormState`)
- **Media query handling for responsive behavior** (`useMediaQuery`)
- **Fetch abstraction** (`useApi` with loading/error/state management)

These hooks helped isolate logic, reduce duplication, and made components much more maintainable.

---

## Key Notes:

- Custom hooks can call other hooks inside them.
- Great for reusing logic without repeating it in every component.
- Should always start with the word `use` to follow React rules.

## What is Routing in React?

Routing in React is handled using `react-router-dom`. It maps URLs to components and enables navigation in single-page apps.

### Example:

- `/login` → Login page
- `/dashboard` → Dashboard component

### Key Hooks & Components:

- `Routes`, `Route` – for defining routes
- `useNavigate()` – for navigation in code
- `useParams()` – to access URL params
- `Navigate` – to redirect

### When I used it:

At United and Capital Group, I used routing to manage public/private routes, nested layouts, and dynamic route parameters. Also implemented lazy-loaded routes and route guards using a custom `PrivateRoute` wrapper.

================

## 1. Tell me about your current project

I’m working on United.com’s React migration project. We’re converting legacy .NET modules to React with a strong focus on accessibility, performance, and security. I lead the UI side—building components using React 18, Redux-Saga, and integrating them with backend services over REST and xAPI. We also embed the frontend into AEM containers for CMS-driven rendering.

## 2. Which hooks did you work on?

I use `useState`, `useEffect`, `useRef`, `useCallback`, `useMemo`, and `useContext` regularly. For example, I use `useMemo` for memoizing heavy computations and `useCallback` for preventing unnecessary re-renders in child components. I also write custom hooks when logic needs to be reused across components.

## 3. Authentication and Authorization—how did you handle it?

For frontend auth, I used tokens (usually JWTs) stored in memory or HTTP-only cookies. Based on user roles returned from the backend, I conditionally render routes and UI elements. On login, we fetch user details and permissions, store them in Redux, and use them for access control in the UI.

## 4. Redux?

Yes, I’ve used both classic Redux and Redux Toolkit. In my current project, we use Redux-Saga for handling async flows like API calls, and selectors for memoization. I organize state using slices and modular patterns, especially in larger applications.

## 5. Which version of React.js?

I’m currently using React 18. I’ve worked with features like automatic batching, concurrent rendering (with Suspense), and improved SSR support. Most projects I’ve led used React 16+ initially, and we've migrated to 18 over time.

## 6. Error boundaries?

Yes, I use class-based components as error boundaries. It helps catch rendering errors in child components without crashing the whole app. I wrap key parts of the UI (like dynamic dashboards or user forms) with error boundaries and log errors using Sentry.

## 7. React with Java—how did you deal?

The React frontend interacts with Java-based backend via REST APIs. We use Axios/fetch to call APIs, handle tokens for auth, and parse JSON responses. I work closely with backend teams to align on contracts and test integration flows using Postman or Swagger before wiring up the UI.

## 8. Virtual DOM vs Real DOM—what's the difference?

The virtual DOM is a lightweight JS copy of the real DOM. React uses it to figure out the minimal changes needed and applies them efficiently to the real DOM. This diffing and batching reduces direct manipulation, making rendering faster and more optimized.

## 9. Internationalization (i18n)?

I’ve used libraries like `react-i18next` for i18n. We create translation JSON files for each language and load them dynamically. I also handled RTL (right-to-left) support and fallback languages. The AEM setup helped manage language content for global sites.

## 10. Route protection in React application?

I use wrapper components or higher-order components that check auth state before rendering routes. For example, a `<PrivateRoute>` checks if the user is authenticated (from Redux or Context), and redirects to login if not. Same goes for role-based routes.

## 11. Multi-step form with persistent data (even on navigation away)?

I manage multi-step form state in Redux or Context. To persist it across sessions or page reloads, I use `localStorage` or `sessionStorage`. Each step updates a slice of the global state, and on submission, we compile and send the complete payload to the backend.

## 12. How to make an API call in frontend?

Typically with Axios or fetch. I structure API calls in service files. In Redux-Saga, I use generator functions to make async calls and dispatch actions based on success or failure. I also show loading spinners and handle error states gracefully.

## 13. Context API?

I’ve used it when the state doesn't require Redux-level complexity—like theme toggles, language switchers, or user session data. I define a context provider and use `useContext` hook to access state in child components.

## 14. How did you integrate frontend and backend process?

We define API contracts first (REST or GraphQL). I use Postman to test them. Once confirmed, I write services in the frontend using Axios, manage state via Redux, and ensure type consistency using TypeScript. I also handle error cases and retry logic for robustness.

## 15. Authentication in backend—how did you implement?

In backend projects with Node or Java, I’ve implemented JWT-based auth. On login, the backend validates credentials, signs a token, and sends it to the frontend. Backend middleware checks for token validity on each request, along with role/permission validation for sensitive endpoints.

## 16. What is a Higher-Order Component (HOC) in React?

A Higher-Order Component (HOC) is a function that takes a component and returns a new component with additional functionality.

Think of it as a pattern for reusing component logic without duplicating code.

### Example:

```jsx
const withLoader = (WrappedComponent) => {
  return function WithLoaderComponent({ isLoading, ...props }) {
    if (isLoading) {
      return <div>Loading...</div>;
    }
    return <WrappedComponent {...props} />;
  };
};

// Usage
const UserListWithLoader = withLoader(UserList);
```

In the example above, `withLoader` is a HOC that wraps any component and adds a loading UI based on props.

## When I used HOC:

At United, I used HOCs to wrap protected routes with auth checks and also to inject layout or common behaviors like error handling, logging, or feature toggling into reusable modules.

## Key Notes:

- HOCs don’t modify the original component—they return a new one.
- **Common use cases**: authentication, layout wrappers, logging, performance monitoring.
- They follow the pattern:
  ```js
  const EnhancedComponent = hoc(WrappedComponent);
  ```

## 17. What are Custom Hooks in React?

Custom Hooks are JavaScript functions that start with `use` and let you reuse stateful logic across multiple components.

They help avoid duplication and keep components clean by abstracting common logic.

---

## Example: `useWindowWidth`

```jsx
import { useState, useEffect } from "react";

function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener("resize", handleResize);

    return () => window.removeEventListener("resize", handleResize);
  }, []);

  return width;
}

// Usage in a component
function Dashboard() {
  const width = useWindowWidth();

  return <div>Current width: {width}px</div>;
}
```

## When I used Custom Hooks:

At United and Visa, I created several custom hooks to manage:

- **Debounced search input** (`useDebounce`)
- **Tracking scroll position** (`useScrollPosition`)
- **Form validation logic** (`useFormState`)
- **Media query handling for responsive behavior** (`useMediaQuery`)
- **Fetch abstraction** (`useApi` with loading/error/state management)

These hooks helped isolate logic, reduce duplication, and made components much more maintainable.

---

## Key Notes:

- Custom hooks can call other hooks inside them.
- Great for reusing logic without repeating it in every component.
- Should always start with the word `use` to follow React rules.

## What is Routing in React?

Routing in React is handled using `react-router-dom`. It maps URLs to components and enables navigation in single-page apps.

### Example:

- `/login` → Login page
- `/dashboard` → Dashboard component

### Key Hooks & Components:

- `Routes`, `Route` – for defining routes
- `useNavigate()` – for navigation in code
- `useParams()` – to access URL params
- `Navigate` – to redirect

### When I used it:

At United and Capital Group, I used routing to manage public/private routes, nested layouts, and dynamic route parameters. Also implemented lazy-loaded routes and route guards using a custom `PrivateRoute` wrapper.

=======

## Infosys 1hr:30 min Interview

# Interview Q&A (Short .md Format)

## 1. Introduction

Full-stack UI developer with 12+ years' experience in React, Angular, Node.js, AWS, and UI architecture.

## 2. What backend services did you work on?

Node.js with NestJS, Express.js, GraphQL APIs, AWS Lambda, API Gateway, DynamoDB.

## 3. Which Frontend technologies did you work?

React.js, Angular 16, TypeScript, Redux, RxJS, HTML5, CSS3, Sass, Highcharts, AG Grid.

## 4. Hardcoding in Frontend and Backend? Why?

Avoid it. Makes updates error-prone and unscalable. Prefer configs, enums, or DB-driven values.

## 5. Tables Structure in Backend?

Normalized with clear entities: user, role, permissions. Use foreign keys and mapping tables.

## 6. Delayed screen feedback by client?

Track all screen specs via JIRA/Confluence. Use wireframes, versioning, and document changes.

## 7. UX suggestions for React apps?

Keep components modular, reusable. Minimize load time. Use skeletons/loaders. Align on design tokens.

## 8. How to handle UX?

Collaborate early with UX team. Validate flows with user feedback. Focus on accessibility and performance.

## 9. Low-Level Design (LLD)?

Break down components, APIs, service classes, DB schema, validations, and interface contracts.

## 10. UI Architecture of React App?

Feature-based folder structure, centralized state (Redux/Context), reusable components, code splitting.

## 11. React.js Architecture?

Component-based. Props for data flow. Hooks for state/effects. Virtual DOM for efficient rendering.

## 12. Libraries in React.js?

Redux Toolkit, Axios, React Router, Formik, Yup, Zod, Lodash, React Query, AG Grid.

## 13. UI Components in React?

Button, Input, Modal, Table, Dropdown, Tooltip, Toast, Accordion, Tabs—abstracted and reused.

## 14. Hooks in React?

useState, useEffect, useMemo, useCallback, useRef, useContext, custom hooks.

## 15. Rendering?

React re-renders based on state/prop changes. Use memoization to avoid unnecessary re-renders.

## 16. jQuery to JS Conversion Time?

Depends on project size. Typically a few days to weeks. Focus on event handling and DOM updates.

## 17. JS vs jQuery: Which is faster?

Vanilla JS is faster. jQuery adds overhead but simplifies cross-browser scripting.

## 18. JS vs jQuery?

JS is native, modern, and powerful. jQuery is easier for beginners, but outdated for modern apps.

## 19. Accessing Camera: HTML or JS?

Both. HTML provides `<video>` tag, JavaScript uses `navigator.mediaDevices.getUserMedia()`.

## 20. Unit Test Cases?

Jest, React Testing Library for frontend. Write tests for components, reducers, and utility functions.

## 21. AWS Cloud?

Worked with S3, Lambda, API Gateway, DynamoDB, CloudWatch, IAM, Cognito.

## 22. CI/CD Cloud?

Used GitHub Actions, Bitbucket Pipelines, and AWS CodePipeline for automated build/test/deploy.

## 23. Why no problem with private variables?

They enforce encapsulation. Outside access is restricted to getter/setter only.

## 24. Private Variable Drawback?

Can’t access directly—need accessor methods. Can slow development if overused.

## 25. Public Method?

Used to safely expose internal state or trigger actions—maintains abstraction.

## 26. How to achieve encapsulation?

Make variables private. Provide public methods to access/update them.

## 27. How we achieve security?

Use encapsulation, authentication, authorization, validation, HTTPS, and secure APIs.

## 28. Setter Method for Bank Balance?

```java
public void setBalance(double balance) {
  this.balance = balance;
}
```

## 29. Purpose of Encapsulation

Encapsulation hides internal state and logic, exposing only what’s necessary through methods. It protects data integrity and makes the codebase easier to maintain.

## 30. Model Class in Setter/Getter

A model class defines private fields and provides public getters/setters to access or modify them. This enforces controlled access to data.

## 31. Model in Java

A model is a simple Java class representing a data entity (e.g., User, Product). It holds fields and provides getters/setters.

## 32. POJO

POJO (Plain Old Java Object) is a lightweight Java class with private variables, constructors, and getter/setter methods, with no extra framework dependencies.

## 33. How to Implement Encapsulation

Declare class variables `private`, use `public` getter/setter methods to access and update them.

## 34. Encapsulation?

A core OOP concept where the internal state of an object is shielded from direct access, reducing complexity and increasing security.

## 35. Virtual DOM vs Real DOM

- **Virtual DOM**: Lightweight JS representation of UI. Fast updates.
- **Real DOM**: Actual browser-rendered structure. Slower updates.
  Virtual DOM is more efficient for UI re-renders.

## 36. WhatsApp/Instagram 25MB Status Upload

Client compresses media before uploading. Reduces upload time and storage requirements on the server.

## 37. VDOM vs Real DOM: Storage

Real DOM needs more memory since it's an actual UI node tree. VDOM is just JS objects, so it's lighter in terms of memory.

## 38. How to Add Permissions (Push) in UI

Store user permissions in app state. Conditionally show/hide actions like push/create using permission flags.

## 39. Core Level Permissions in UI

Set access control at component or route level. Use wrappers or guards to restrict rendering or navigation based on user role/permissions.

## 40. Push, Create Resource, Create User → Permissions

Define permission keys (e.g., `canPush`, `canCreateUser`). Check these flags in UI logic before rendering actions.

## 41. Permissions in Hardcoding?

Avoid hardcoding permissions. Use role-permission mappings from backend or config files to manage access dynamically.

## 42. Database Hardcoding?

Hardcoding DB logic is fragile. Prefer normalized tables and parameterized queries or stored procedures for flexibility and security.

## 43. Role Management DB Tables

- `users`
- `roles`
- `permissions`
- `user_roles`
- `role_permissions`
  This structure supports flexible, scalable access control.

## 44. Ecommerce App Redux

Redux manages global state: cart, user auth, product list. Helps in predictable state transitions and syncing UI with server responses.

## 45. State Management

State can be managed using Redux, Context API, Zustand, etc. Centralizes state for consistency and better debugging.

## 46. Can We AJAX Synchronous?

Yes, but discouraged. Synchronous calls block the main thread, freeze UI. Always prefer async with Promises or `async/await`.

## 47. AJAX Call?

AJAX is used to fetch or send data to the server without reloading the page. Common tools: `fetch()`, `axios`, or `XMLHttpRequest`.

## 48. useState in JavaScript?

`useState` is React’s way to declare reactive state inside functional components. In vanilla JS, closures or IIFEs can somewhat mimic state behavior.

## 49. Scope of Layers in the Application

Divide code into layers:

- **Presentation Layer** (UI)
- **Business Logic Layer** (validation, processing)
- **Service Layer** (API calls)
- **Data Layer** (DB interaction)
  Keeps code modular and easier to manage.

## 50. z-index?

CSS property to control stacking order. Higher `z-index` brings an element visually on top of lower-indexed elements.

## 51. Normalization: Better Table Structure?

Yes. Normalization reduces data redundancy, improves consistency, and maintains referential integrity across tables.

🔧 Suggested Normalized Structure:
users
id firstname lastname age mobile is_active is_prime

addresses
id user_id address1 address2 city state pincode country

======
Technical quesitons:

# Interview Q&A

### 1. Introduce yourself?

Hi, I'm Vijay, a Senior Full Stack Engineer with over 12 years of experience in building scalable web applications. My core expertise lies in frontend development with React.js, TypeScript, and Redux Toolkit, and on the backend, I work extensively with Node.js, Express, and GraphQL.

I've worked with cloud-native solutions on AWS, including Lambda, API Gateway, and DynamoDB, and I'm well-versed in building micro frontends and designing reusable UI libraries. I’ve also contributed to improving performance, accessibility (WCAG 2.0), and observability in production apps. Most recently, I’ve been focusing on real-time dashboards and enterprise-scale UI architecture.

---

### 2. Folder structure?

I use a feature-based folder structure:

src/
├── features/ // domain modules (auth, dashboard)
├── components/ // shared UI
├── hooks/ // reusable hooks
├── utils/ // helper functions
├── types/ // global interfaces/types

Keeps the code modular and scalable.

## 3. Redux?

Redux is a state management tool. I use Redux Toolkit to manage app-wide state, with `createSlice`, `useSelector`, and `useDispatch`. For async tasks, I use Thunk or Redux Saga.

---

## 4. Difference Between Interface vs Type?

### Q: What’s the difference between `interface` and `type` in TypeScript?

**A:**

| Feature               | `interface`                     | `type`                                      |
| --------------------- | ------------------------------- | ------------------------------------------- |
| Purpose               | Defines shape of an object      | Alias for any type (primitive, union, etc.) |
| Extensibility         | Can be extended via `extends`   | Can be extended using intersections (`&`)   |
| Merging               | Supports declaration merging    | Does **not** support merging                |
| Usage with Primitives | ❌ Not for primitives or unions | ✅ Works with primitives, unions, tuples    |
| Readability           | Preferred for object shapes     | Better for complex or computed types        |

---

- **interface:** Best for objects and class contracts, supports declaration merging.
- **type:** Used for unions, primitives, tuples, and intersection types.

**Example:**

```ts
interface A {
  name: string;
}
type B = { age: number };
```

## 5. WCAG 2.0 guidelines?

WCAG ensures accessibility. It follows the POUR principles:

- **Perceivable:** alt text, captions
- **Operable:** keyboard navigation, focus indicators
- **Understandable:** clear labels
- **Robust:** screen reader support

I use semantic HTML, ARIA attributes, and tools like axe or Lighthouse.

---

## 6. How do you do a code review?

**Answer:**

I review code focusing on:

- ✅ Functionality – Does it meet requirements and handle edge cases?
- ✅ Readability – Clear variable names, modular functions, consistent formatting.
- ✅ Performance – Avoid unnecessary re-renders, loops, or memory leaks.
- ✅ Security – Prevent XSS, SQL injection, and avoid exposing secrets.
- ✅ Best Practices – Follow project standards (e.g., React patterns, REST/GraphQL conventions).
- ✅ Tests – Check for unit/integration tests and critical path coverage.

I leave constructive comments, suggest improvements with examples, and encourage collaboration rather than criticism.

## 7. What is your deployment process?

**Answer:**

I follow a CI/CD-driven deployment process:

- ✅ Code pushed to Git → triggers CI pipeline (GitHub Actions, Jenkins).
- 🧪 Linting, unit tests, and build are run automatically.
- 📦 Artifacts or Docker images are generated and stored (e.g., ECR/S3).
- 🚀 Deployment to dev/stage/prod via:
  - Serverless Framework for Lambda
  - ECS or EC2 for containerized apps
  - S3 + CloudFront for frontend
- 📊 Post-deployment: Monitor with CloudWatch, enable rollback if issues occur.

I ensure infrastructure is defined as code and approvals are in place for prod releases.

---

## 8. What is your role? Developer or Lead?

**Answer:**

I primarily work as a Senior Full Stack Developer, but I often take on lead responsibilities like:

- Reviewing code and mentoring juniors
- Designing technical architecture
- Collaborating with backend/devops teams
- Leading sprint planning and estimations
- Driving best practices for performance, accessibility, and testing

So while my title is developer, I act as a tech lead in many areas of the project.

---

## 9. When there are data issues, how do backend and frontend teams coordinate?

**Short Answer:**

We first identify the issue through logs, API responses, or UI errors. Then:

- 🔍 Frontend shares request payloads, expected vs actual data.
- 🔄 Backend checks API logic, DB queries, or transformation issues.
- 🧪 We reproduce it together (via Postman or dev console).
- 📋 Use tools like Swagger, logging, or versioned contracts to validate.
- ✅ Once fixed, frontend verifies and updates UI handling if needed.

We use Slack/JIRA for async communication and daily standups or debug sessions to collaborate quickly.

---

## 10. What is the difference between any and unknown in TypeScript?

**Short Answer:**

- `any`: Disables type checking. You can assign and use it freely — unsafe.
- `unknown`: Like `any`, but type-safe — you must check its type before using it.

**Example:**

```ts
let a: any = "Hello";
a.toUpperCase(); // ✅ No error, even if 'a' was a number — risky!

let b: unknown = "Hello";
b.toUpperCase(); // ❌ Error: You must check the type first

if (typeof b === "string") {
  b.toUpperCase(); // ✅ Safe
}
```

**Rule of thumb:**
Use `unknown` when you're unsure about the type and want to enforce safety. Avoid `any` unless absolutely necessary.

---

## 11. Have you used React Hooks?

**Answer:**

Yes, I use React Hooks extensively in all my React projects.

- `useState` for managing local state
- `useEffect` for side effects (API calls, subscriptions)
- `useContext` for global state or theming
- `useRef` for DOM access or persisting values
- `useMemo` and `useCallback` for performance optimization
- `useReducer` for complex state logic
- Custom hooks for reusable logic (e.g., `useFetch`, `useDebounce`)

Hooks help me write cleaner, functional, and reusable components.

---

## 12. What is a Custom Hook in React?

A custom hook is a reusable function that uses React hooks like `useState` or `useEffect` to share logic between components.

- 🔁 It helps avoid code duplication and keeps components clean.
- 📛 Custom hooks always start with `use`, like `useFetch` or `useForm`.

## 13. How to improve performance in React apps?

**Short Answer:**

- 🧠 Use `React.memo`, `useMemo`, `useCallback` to avoid unnecessary re-renders
- 💤 Lazy load components with `React.lazy` and `Suspense`
- 🧹 Clean up effects in `useEffect`
- 📦 Code splitting and dynamic imports
- 🎯 Use virtualization (e.g., `react-window`) for large lists
- 🚫 Avoid prop drilling – use Context or Redux
- 📉 Minimize unnecessary state and DOM updates

---

## 14. What are Cross-Browser Compatibility Issues?

**Short Answer:**

Cross-browser compatibility issues occur when a website or app behaves differently or breaks across different browsers (like Chrome, Firefox, Safari, Edge) due to differences in how browsers interpret HTML, CSS, or JavaScript.

Common issues include:

- CSS styles not rendering the same
- JavaScript APIs not supported or behaving inconsistently
- Layout and positioning differences
- Feature support variations (e.g., flexbox, grid)

We fix these by using vendor prefixes, polyfills, testing on multiple browsers, and writing standards-compliant code.

---

## 15. What is Webpack?

Webpack is a module bundler for JavaScript applications. It takes your code and assets (JS, CSS, images), bundles them into optimized files for the browser, and handles things like code splitting, tree shaking, and hot module replacement to improve performance and developer experience.

---

## 16. Which tools do you use for accessibility testing?

**Short Answer:**

I use tools like:

- axe DevTools (browser extension) for automated accessibility checks
- Lighthouse (built into Chrome DevTools) for accessibility score reports
- Wave extension for visual accessibility feedback
- NVDA or VoiceOver screen readers for manual testing
- Keyboard-only navigation to ensure operability

These help catch issues and ensure compliance with WCAG guidelines.

---

## 17. What is your team size?

**Short Answer:**

I typically work in teams of 5 to 10 engineers, including frontend, backend, QA, and DevOps. Sometimes larger cross-functional teams up to 15, depending on project scale.

I collaborate closely with product managers, designers, and stakeholders to deliver features smoothly.

## 18. Have you worked on the production environment?

**Short Answer:**

Yes, I regularly work in production environments. I’m involved in:

- Deployments using CI/CD pipelines
- Monitoring app health with tools like CloudWatch and Sentry
- Troubleshooting live issues and applying hotfixes
- Ensuring performance and uptime through observability and alerts

I understand the importance of careful releases and rollback strategies to minimize user impact.

---

## 19. What is the input for Webpack?

**Short Answer:**

The input for Webpack is the entry point — typically a JavaScript file (like `src/index.js` or `src/index.tsx`) that serves as the root of your application. Webpack starts bundling from this entry file, following all imports and dependencies to create the final bundle.

---

## 20. How to enable CORS with Webpack?

You enable CORS during development by configuring `webpack-dev-server` to proxy API requests and set headers:

```js
devServer: {
  proxy: { '/api': 'http://localhost:5000' },
  headers: { 'Access-Control-Allow-Origin': '*' },
}
```

For production, CORS must be handled on the backend server.

=========================================================
coding question:

/\*

- Click `Run` to execute the snippet below!
- [[1,9,3] , [5,4,8] ,[2,7,6]]
-
- "ALL ASC" - [[1,2,3] , [4,5,6] ,[7,8,9]]
- "BLOCK ASC" - [[1,3,9] , [4,5,8] ,[2,6,7]]
  \*. "ALL DESC" - [[9,8,7] , [6,5,4] ,[3,2,1]]
- "Block DESC" - [[9,3,1] , [8,5,4] ,[7,6,7]]
  \*/

const input = [[1,9,3] , [5,4,8] ,[2,7,6]];

// Sort each sub-array ascending
const allAsc = input.map(arr => [...arr].sort((a, b) => a - b));
console.log("ALL ASC:", allAsc);

// Sort each sub-array descending
const allDesc = input.map(arr => [...arr].sort((a, b) => b - a));
console.log("ALL DESC:", allDesc);

// Sort main array by first item ascending
const blockAsc = [...input].sort((a, b) => a[0] - b[0]);
console.log("BLOCK ASC:", blockAsc);

// Sort main array by first item descending
const blockDesc = [...input].sort((a, b) => b[0] - a[0]);
console.log("BLOCK DESC:", blockDesc);

Output:

ALL ASC: [ [ 1, 3, 9 ], [ 4, 5, 8 ], [ 2, 6, 7 ] ]
ALL DESC: [ [ 9, 3, 1 ], [ 8, 5, 4 ], [ 7, 6, 2 ] ]
BLOCK ASC: [ [ 1, 9, 3 ], [ 2, 7, 6 ], [ 5, 4, 8 ] ]
BLOCK DESC: [ [ 5, 4, 8 ], [ 2, 7, 6 ], [ 1, 9, 3 ] ]

====

## 45 minutes interview with Persistent

## 1. Tell me about yourself

I am a **Senior Full Stack Engineer** with 12+ years of experience building .com websites for various organizations using **HTML5**, **CSS3**, **JavaScript**, **React.js**, and **Redux**.

For the past 2 years, I’ve been part of the **React migration team** at United Airlines, where we converted .NET pages to React on united.com.  
The frontend uses **React** with in-house **ATMOS** component libraries used company-wide.

I worked on several user-facing **security features**, including:

- Forgot password / Forgot MileagePlus number
- Security questions and sign-in features
- Miles-Pooling
- United Club pass management
- Recent Activity and dashboard updates
- KTN (Known Traveler Number)
- Accessibility (WCAG) improvements

To handle asynchronous flows, I used **Redux-Saga** for API calls, data fetching, and impure actions.

**Recent initiatives** include:

- **Miles-Pooling** (travel rewards point sharing)
- **TSA Precheck integration**
- **Under18 account restrictions**
- **Account security and management** updates

**Previous experience:**

- **Visa Inc. – Accelerator Team**  
  Remediated MBDA modules like Application Management, Portfolio Management, Analytics, Recurring Billing, and Virtual Terminal for clients like Wells Fargo and Bank of America.

- **Capital Group – DAVIS Project**  
  Built data visualizations using **Highcharts** in React and integrated with **AEM**.  
  Also worked on **Creative Workbench**, a writing tool for publishing articles.

- **Cerner Corporation**  
  Developed forms for **medical examinations**.

- **Office Depot**  
  Worked on **Black Friday reporting** tools.

- **Satinos Technologies**  
  Built a **tax portal** and **school website** (Schoomin) for **Vignan Schools**.

---

## 2. HTML

### Q: What is a Web Worker? Why would you use it?

**A:** A **Web Worker** allows JavaScript to run in a **background thread**, separate from the main UI thread.

This is useful for handling **heavy computations or blocking logic**—such as image processing, long loops, or polling APIs—**without freezing the UI**.  
It keeps the page responsive and improves user experience when doing non-UI intensive work in the background.

## 🚀 2. HTML Page Optimization – What are the best practices?

**Q: How do you optimize an HTML page for performance?**

**A: Key strategies:**

- Minify HTML, CSS, JS
- Defer non-critical JS with `defer` or `async`
- Lazy-load images (`loading="lazy"`) and use compressed formats like WebP
- Use semantic HTML for better rendering and accessibility
- Reduce HTTP requests (combine files, use sprites/icons)
- Preload key resources with `<link rel="preload">`
- Use caching headers and versioning for assets
- Avoid inline styles/scripts unless necessary
- Optimize critical rendering path: inline critical CSS, defer the rest
- Use a CDN for static assets
- Compress responses (gzip, Brotli)

---

**Q: What's the difference between `async` and `defer`?**

- **`async`**: Loads and executes the script _as soon as it’s available_. Doesn’t wait for HTML parsing.
- **`defer`**: Loads script in parallel, but executes _after_ HTML is parsed. Safer for DOM-dependent scripts.

---

## 🧩 3. Semantic Elements in HTML

**Q: What are semantic elements in HTML and why are they important?**

**A:** Semantic elements clearly describe their meaning to both the browser and developer. This improves:

- Accessibility (screen readers)
- SEO (search engines prioritize semantic structure)
- Maintainability (code clarity)

**Examples:**

- `<header>`, `<footer>`
- `<main>`, `<section>`, `<article>`
- `<nav>`, `<aside>`
- `<figure>`, `<figcaption>`

---

**Q: What's the difference between `<section>` and `<div>`?**

- `<section>` is semantic—it represents a standalone block of related content with a heading.
- `<div>` is purely structural—no inherent meaning.

---

**Q: When should you use `<article>` vs `<section>`?**

- Use `<article>` for independent, self-contained content (blog post, comment, news article).
- Use `<section>` to group related content under a heading that forms part of a larger document.

## 3. CSS

### Q: What is Responsive Web Design?

**A:** Responsive Web Design (RWD) is a design approach where the layout and elements of a web page adapt fluidly to different screen sizes and devices.  
It uses techniques like **flexible grids**, **media queries**, and **relative units** (%, `em`, `rem`, `vw`, `vh`) to ensure content looks good on desktops, tablets, and phones.

---

### Q: What are the different `position` values in CSS?

**A:** The `position` property determines how an element is placed in the document. Key values include:

- `static` – default, element follows normal document flow
- `relative` – positioned relative to its normal position
- `absolute` – positioned relative to the nearest positioned ancestor
- `fixed` – positioned relative to the viewport, stays in place during scroll
- `sticky` – toggles between `relative` and `fixed` depending on scroll position

---

### Q: What is `z-index` in CSS?

**A:** `z-index` controls the **stacking order** of positioned elements (those with `position` other than `static`).  
Higher `z-index` values appear in front of lower ones. It only works on **positioned** elements.

Example:

```css
.element {
  position: absolute;
  z-index: 10;
}
```

### Q: What's Flex?

**A:** Flexbox (`display: flex`) is a CSS layout model that makes it easier to align and distribute space among elements inside a container.

Key concepts:

- **Main axis** (horizontal by default) and **cross axis** (vertical)
- Automatically adjusts item sizes based on available space
- Helps with both **horizontal and vertical alignment**

**Common properties:**

**On the container:**

- `display: flex`
- `flex-direction`: row | column
- `justify-content`: flex-start | center | space-between | space-around
- `align-items`: stretch | center | flex-start | flex-end

**On the children:**

- `flex`: shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`
- `align-self`: overrides container’s `align-items` for individual items

**Example:**

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### Q: What are Media Types in CSS?

**A:** Media types specify the type of device or medium a stylesheet is targeting. They allow developers to apply styles conditionally based on how the content is being accessed.

**Common media types:**

- `screen` – for computer screens, tablets, smartphones
- `print` – for printed documents or print preview
- `speech` – for screen readers (used in accessibility)
  Media types are often combined with media features (like width, resolution) using media queries to create responsive designs.
  **Example:**

```css
@media screen and (max-width: 768px) {
  body {
    font-size: 16px;
  }
}
```

### Q: What’s the difference between SCSS and CSS?

| Feature          | CSS                            | SCSS (Sassy CSS)               |
| ---------------- | ------------------------------ | ------------------------------ |
| Variables        | Not supported (in classic CSS) | Supported using `$variable`    |
| Nesting          | Not supported                  | Fully supported                |
| Mixins/Functions | Not available                  | Supported for reuse            |
| Code Reusability | Limited                        | High                           |
| Syntax           | Plain styling rules            | CSS-compatible with extensions |
| Compilation      | No compilation needed          | Must be compiled to CSS        |

**Summary:**  
SCSS is a preprocessor that extends CSS by adding powerful features like variables, nesting, mixins, and functions. It helps write cleaner, more maintainable styles—especially in large or component-based codebases.

## 4. JavaScript

## Closure

A **closure** occurs when an **inner function** retains access to variables defined in its **outer function**, even after the outer function has finished executing.

In simpler terms:

> If any inner function holds on to outer function's data, that's a closure.

---

### Example:

```html
<script>
  function fun_one() {
    var x = 10;
    var y = 20;
    return () => {
      console.log(x);
      console.log(y);
    };
  }

  console.dir(fun_one());
  // Output in console:
  // 0: Closure (fun_one) { x: 10, y: 20 }
</script>
```

## What is the Event Loop?

The **Event Loop** is the mechanism in JavaScript that enables **non-blocking, asynchronous behavior**, even though JavaScript runs in a **single thread**.

It coordinates execution between:

- **Call Stack** – where functions are executed
- **Web APIs** – like `setTimeout`, `fetch`, DOM events, etc.
- **Callback Queue** – holds messages (callbacks) ready to be pushed onto the call stack
- **Microtask Queue** – used for promises and other microtasks

---

### How It Works:

1. JavaScript runs the first line and puts functions on the **call stack**.
2. When an async operation (like `setTimeout`) is called, it's handed off to the **Web API** environment.
3. Once the operation completes, its callback is pushed into the **callback queue**.
4. The **event loop** checks if the call stack is empty.
5. If empty, it moves the next function from the queue into the call stack and executes it.

---

### Example:

```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

Promise.resolve().then(() => {
  console.log("Promise");
});

console.log("End");
```

### Summary

The **Event Loop** allows JavaScript to handle **asynchronous tasks** without blocking the **main thread**.  
This ensures the UI stays responsive and code execution remains efficient, even when handling time-consuming operations like API calls, timers, or user events.

---

### Q: Output of `isNaN('1')`

````js
isNaN('1'); // returns false

### Why?

The string `'1'` is **coerced into a number** before the `isNaN` check.
Since `Number('1')` results in the valid number `1`, it is **not** NaN.

So:

```js
isNaN('1')   // → false
isNaN('abc') // → true
````

### Output for the following code:

```js
x = 23;
let x;

function anotherRandomFunc() {
  message = "Hello"; // bad pratice
}

anotherRandomFunc();
```

### Summary

The code will throw a **ReferenceError** at `x = 23;` due to the **Temporal Dead Zone (TDZ)**.

If the TDZ error did not occur, calling `anotherRandomFunc()` would create a global variable `message`.

## Temporal Dead Zone (TDZ)

The **Temporal Dead Zone** is the time between entering a scope and the moment a variable declared with `let` or `const` is initialized.  
Accessing the variable during this period results in a **ReferenceError**.

Example:

```js
console.log(a); // ReferenceError: Cannot access 'a' before initialization
let a = 10;
```

TDZ helps catch errors by preventing access to variables before their declaration.

---

## Higher-Order Functions (HOFs) in JavaScript

A **Higher-Order Function** is a function that either:

- Takes one or more functions as arguments, or
- Returns a function as its result

They allow functions to be composed, reused, and abstracted.

**Common examples:**

- `Array.prototype.map`
- `Array.prototype.filter`
- `Array.prototype.reduce`
- `setTimeout`

### Q: What’s a Generator Function? (`function* genFunc(){}`)

A **Generator Function** is a special kind of function in JavaScript that can **pause** and **resume** its execution.

- Defined using the `function*` syntax (note the asterisk `*`)
- Uses the `yield` keyword to pause execution and send values out
- Calling a generator returns an **iterator** object with a `.next()` method
- Each `.next()` call resumes execution until the next `yield` or return

---

### Example:

```js
function* genFunc() {
  yield 1;
  yield 2;
  return 3;
}

const gen = genFunc();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: true }
```

### Use Cases

- Lazy evaluation (generate values on demand)
- Implementing iterators
- Managing asynchronous flows (with `async`/`await`)
- State machines

### Difference Between Promises and Observables in JavaScript

| Feature        | Promises                                      | Observables                                               |
| -------------- | --------------------------------------------- | --------------------------------------------------------- |
| Values emitted | Single value (resolved or rejected)           | Multiple values over time                                 |
| Lazy?          | Yes                                           | Yes                                                       |
| Cancelable?    | No                                            | Yes                                                       |
| Operators      | Limited (`then`, `catch`, `finally`)          | Rich set of operators (`map`, `filter`, `debounce`, etc.) |
| Execution      | Starts immediately when created               | Execution starts on subscription                          |
| Use cases      | Single async operations (e.g., HTTP requests) | Streams, events, real-time data, user input               |

---

**Summary:**

- Use **Promises** for one-time async operations that resolve or reject once.
- Use **Observables** (e.g., with RxJS) for handling streams of data over time, allowing cancellation and complex operations.

## 5. NodeJS

### Types of Subjects in RxJS

In RxJS, a **Subject** is both an **Observable** and an **Observer**. It can multicast to many observers.

There are several types of Subjects:

- **Subject**  
  The basic form. Starts empty and emits values to subscribers from the point of subscription onward.

- **BehaviorSubject**  
  Requires an initial value and **emits the latest value** to new subscribers immediately upon subscription.

- **ReplaySubject**  
  Records a specified number of previous emissions and replays them to new subscribers.

- **AsyncSubject**  
  Emits only the **last value** (and only when the Observable completes).

---

### Summary:

| Subject Type    | Emits to New Subscribers                        |
| --------------- | ----------------------------------------------- |
| Subject         | Values emitted after subscription               |
| BehaviorSubject | Most recent value immediately upon subscription |
| ReplaySubject   | Specified number of previous values             |
| AsyncSubject    | Last value only after completion                |

## Pros and Cons of Node.js

### Pros

- **Fast and efficient**  
  Built on Chrome’s V8 engine, Node.js executes JavaScript very quickly.

- **Non-blocking, event-driven architecture**  
  Handles many concurrent connections with minimal overhead.

- **Single language (JavaScript) for frontend and backend**  
  Simplifies development and allows code reuse.

- **Large ecosystem**  
  Vast npm repository with thousands of libraries and tools.

- **Scalable**  
  Suitable for microservices and real-time applications (chat, streaming).

- **Active community and corporate support**  
  Constant improvements and plenty of learning resources.

---

### Cons

- **Single-threaded limitations**  
  CPU-intensive tasks can block the event loop and degrade performance.

- **Callback hell** (less common now with async/await)  
  Complex asynchronous code can become hard to manage.

- **Maturity**  
  Some libraries and tools are less mature compared to older backend platforms.

- **Not ideal for heavy computation**  
  Better suited for I/O-bound applications rather than CPU-bound.

- **API instability**  
  Some APIs have changed frequently in early versions (less so now).

---

**Summary:**  
Node.js excels at building fast, scalable I/O-heavy applications but requires care when handling CPU-intensive workloads.

## Streams in Node.js

**Streams** are objects that let you read data from a source or write data to a destination **in chunks**, rather than all at once.  
This makes streams efficient for handling large files, network communications, or any I/O operation.

---

### Types of Streams

- **Readable**: streams you can read data from (e.g., `fs.createReadStream`)
- **Writable**: streams you can write data to (e.g., `fs.createWriteStream`)
- **Duplex**: streams that are both readable and writable (e.g., TCP sockets)
- **Transform**: duplex streams that can modify or transform the data as it is written and read (e.g., compression)

---

### Benefits

- Handle large data efficiently without buffering entire content in memory
- Support **backpressure** to control the flow of data
- Allow piping data from one stream to another, simplifying data processing

---

### Example

```js
const fs = require("fs");

const readable = fs.createReadStream("input.txt");
const writable = fs.createWriteStream("output.txt");

readable.pipe(writable);
```

This reads `input.txt` chunk by chunk and writes it to `output.txt` without loading the entire file into memory.

---

### Summary

Streams are core to Node.js for efficient I/O operations, enabling scalable and performant applications.

## `fork()` Function in Node.js

The `fork()` function is a special case of `child_process.spawn()` used to create a new Node.js process. It is mainly used to run another JavaScript file as a separate process.

---

### Key Features

- Creates a new Node.js instance with its own event loop and memory.
- Enables inter-process communication (IPC) between parent and child using messaging.
- Useful for CPU-intensive tasks or running separate modules without blocking the main process.

---

### Usage Example

```js
const { fork } = require("child_process");

const child = fork("child.js");

child.on("message", (msg) => {
  console.log("Message from child:", msg);
});

child.send({ hello: "world" });
```

## Security Implementation in Node.js

### Key Practices

- **Input Validation & Sanitization**  
  Prevent injection attacks (SQL, NoSQL, command injection) by validating and sanitizing all user inputs.

- **Use HTTPS**  
  Always serve over HTTPS to encrypt data in transit.

- **Manage Secrets Safely**  
  Store API keys, tokens, and passwords securely using environment variables or secret management tools.

- **Authentication & Authorization**  
  Implement robust auth using JWT, OAuth, or sessions. Limit access based on roles and permissions.

- **Avoid Vulnerable Dependencies**  
  Regularly audit and update npm packages. Use tools like `npm audit` or `Snyk`.

- **Prevent Cross-Site Scripting (XSS)**  
  Escape user-generated content before rendering on client.

- **Prevent Cross-Site Request Forgery (CSRF)**  
  Use CSRF tokens to validate requests.

- **Secure Headers**  
  Use modules like `helmet` to set HTTP headers (Content Security Policy, X-Frame-Options, etc.).

- **Rate Limiting and Throttling**  
  Protect APIs from brute force or denial-of-service attacks.

- **Error Handling**  
  Avoid leaking sensitive info in error messages.

---

### Tools & Libraries

- `helmet` — sets security-related HTTP headers
- `express-validator` — input validation
- `bcrypt` — secure password hashing
- `jsonwebtoken` — JWT auth
- `cors` — enable and configure CORS securely

---

### Summary

Security in Node.js requires a multi-layered approach: validate inputs, protect data in transit, manage dependencies, enforce strict auth, and configure secure headers.

## Clustering in Node.js

Node.js runs on a single thread by default, which limits CPU core utilization.  
**Clustering** allows you to create multiple child processes (workers) that share the same server port and run in parallel, leveraging multi-core systems.

---

### How Clustering Works

- The main process (master) spawns multiple worker processes.
- Each worker runs its own event loop and handles incoming requests.
- Workers share the same server port, allowing load distribution.
- If a worker crashes, the master can restart it for resilience.

---

### Basic Example

```js
const cluster = require("cluster");
const http = require("http");
const numCPUs = require("os").cpus().length;

if (cluster.isMaster) {
  console.log(`Master ${process.pid} is running`);

  // Fork workers
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on("exit", (worker, code, signal) => {
    console.log(`Worker ${worker.process.pid} died. Restarting...`);
    cluster.fork();
  });
} else {
  // Workers can share the TCP connection
  http
    .createServer((req, res) => {
      res.writeHead(200);
      res.end(`Hello from worker ${process.pid}`);
    })
    .listen(8000);

  console.log(`Worker ${process.pid} started`);
}
```

### Benefits

- Improves performance by utilizing all CPU cores.
- Increases application reliability through worker restarts.
- Enables horizontal scaling on a single machine.

---

### Summary

Clustering is a simple way to scale Node.js applications vertically by forking worker processes that handle requests concurrently.

## 6. Angular

### Dependency Injection (DI) in Angular

Dependency Injection (DI) is a design pattern Angular uses to supply components or services with the dependencies they need.

Instead of creating dependencies inside a class, Angular injects them from an external source, making the code more modular, testable, and maintainable.

---

### How DI Works in Angular

- Angular has an **injector** that maintains a container of dependencies (services).
- Components declare dependencies in their constructor.
- Angular resolves and provides those dependencies automatically at runtime.

---

### Example

```ts
import { Injectable } from "@angular/core";

@Injectable({
  providedIn: "root",
})
export class ApiService {
  getData() {
    return "data";
  }
}

@Component({
  selector: "app-example",
  template: "{{ data }}",
})
export class ExampleComponent {
  data: string;

  constructor(private apiService: ApiService) {
    this.data = this.apiService.getData();
  }
}
```

Here, `ApiService` is injected into `ExampleComponent` via the constructor.

---

### Benefits of DI

- Promotes loose coupling between classes
- Easier unit testing by injecting mocks/stubs
- Centralizes dependency management
- Enables reusable and maintainable code

---

### Providers

- Services are registered with **providers** in modules, components, or via `providedIn: 'root'`.
- Providers define how and where dependencies are created.

---

### Summary

Angular’s DI system simplifies the management of service instances, improves testability, and promotes clean, modular architecture.

## Eager vs Lazy Loading

### Eager Loading

- Loads all components, modules, or resources **upfront** when the application starts.
- Ensures everything is available immediately but can increase initial load time.
- Common in small apps or for critical modules that must be ready instantly.

### Lazy Loading

- Loads components or modules **on demand**, only when needed.
- Reduces initial load time and improves performance, especially for large apps.
- Often used with route-based code splitting in frameworks like Angular or React.

---

### Summary

- **Eager Loading** prioritizes availability at startup, possibly at the cost of slower initial loads.
- **Lazy Loading** optimizes load time by deferring non-essential resources until required, improving user experience.

## Types of Route Guards in Angular

Route guards control navigation and access to routes in an Angular application.

### 1. CanActivate

- Checks if a route can be **activated**.
- Used to prevent unauthorized access to routes.

### 2. CanActivateChild

- Checks if **child routes** of a route can be activated.
- Useful when protecting a group of child routes.

### 3. CanDeactivate

- Checks if a route can be **exited** or deactivated.
- Commonly used to warn users about unsaved changes before leaving a page.

### 4. Resolve

- Pre-fetches data **before** activating the route.
- Ensures components have necessary data when they load.

### 5. CanLoad

- Prevents **lazy-loaded modules** from loading unless certain conditions are met.
- Useful for blocking access to entire feature modules.

---

### Summary

Angular’s route guards help manage access control, data loading, and user flow, improving security and user experience.

### What is `CanLoad` used for?

`CanLoad` is a route guard in Angular that prevents **lazy-loaded modules** from being loaded unless certain conditions are met.

---

### Key points:

- Runs **before** the module is loaded.
- Stops unauthorized users from downloading entire feature modules.
- Useful for improving app performance and security by blocking access early.

---

### Example use case:

Prevent loading an admin module unless the user has admin privileges.

```ts
export class AuthGuard implements CanLoad {
  constructor(private authService: AuthService, private router: Router) {}

  canLoad(route: Route): boolean {
    if (this.authService.isAdmin()) {
      return true;
    } else {
      this.router.navigate(["/not-authorized"]);
      return false;
    }
  }
}
```

### What do Providers mean in the context of Angular services?

In Angular, **providers** tell the dependency injection system **how to create and deliver a service** instance.

---

### Key points:

- A provider defines **where** and **how** Angular should create an instance of a service.
- Services need to be registered with providers to be injectable.
- Providers can be registered at different levels:
  - **Root level** (application-wide singleton)
  - **Module level** (scoped to a module)
  - **Component level** (scoped to component and its children)

---

### Common ways to register providers:

- Using `providedIn` metadata in `@Injectable` decorator:
  ```ts
  @Injectable({
    providedIn: "root",
  })
  export class MyService {}
  ```
  This makes the service available app-wide as a singleton.

---

### Adding `providers` array in an NgModule or component:

```ts
@NgModule({
  providers: [MyService],
})
export class SomeModule {}
```

### Summary

Providers configure Angular’s Dependency Injection (DI) system to know **how** and **where** to create service instances,  
controlling their **scope** (application-wide, module-level, or component-level) and **lifecycle**.

## HTTP Interceptors in Angular

### What is an HTTP Interceptor?

An **HTTP Interceptor** is a special service in Angular that sits between your application and the backend.  
It lets you **intercept, modify, or log** outgoing HTTP requests and incoming responses.

---

### Common Use Cases

- Add authentication tokens (e.g., JWT) to headers
- Log or handle errors globally
- Show and hide loading indicators
- Modify requests or responses
- Retry failed requests

---

### Example: Adding an Authorization Header

```ts
@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  constructor(private authService: AuthService) {}

  intercept(
    req: HttpRequest<any>,
    next: HttpHandler
  ): Observable<HttpEvent<any>> {
    const token = this.authService.getToken();

    const cloned = req.clone({
      setHeaders: {
        Authorization: `Bearer ${token}`,
      },
    });

    return next.handle(cloned);
  }
}
```

### Summary

HTTP Interceptors in Angular are powerful for centralizing cross-cutting concerns like authentication, error handling, and logging, making your HTTP code cleaner and more maintainable.

## 7. React

### What is Redux?

**Redux** is a predictable state management library used in JavaScript applications, commonly with React.

It centralizes the application state into a **single store**, making state changes predictable and easier to debug.

---

### Core Concepts

- **Store**: The single source of truth that holds the app state.
- **Action**: A plain JavaScript object that describes what happened.
- **Reducer**: A pure function that takes the current state and an action, and returns the new state.
- **Dispatch**: Sends an action to the store to trigger a state change.
- **Selector**: Extracts specific data from the store.

---

### Example Flow

1. Component dispatches an action
2. Redux passes the action to the reducer
3. Reducer returns a new state
4. UI re-renders with the updated state

---

### Benefits

- Predictable state updates
- Centralized debugging (e.g. with Redux DevTools)
- Easier testing and maintenance
- Works well for medium to large applications

---

### Summary

Redux helps manage and centralize state in large React apps by enforcing a unidirectional data flow and clear separation between data and UI logic.

### What is Immutability?

**Immutability** means that an object’s state **cannot be changed after it’s created**.  
Instead of modifying the original object or array, you create and return a **new copy** with the updated values.

---

### Why It Matters in React/Redux

- Ensures **predictable state updates**
- Makes **time-travel debugging** possible
- Avoids unintended side effects
- Helps React detect changes (via shallow comparison)

---

### Example (Wrong: Mutating)

```js
const state = { count: 1 };
state.count = 2; // ❌ mutation
```

### Summary

Immutability is a key principle in React and Redux that ensures state changes are **predictable**, **traceable**, and **efficient**.

### What are React Hooks?

React Hooks are built-in functions that let you use state and other React features in functional components—without writing a class.

**Common hooks:**

- `useState` – manage local state
- `useEffect` – handle side effects
- `useContext` – access context
- `useRef` – reference DOM or store mutable values
- `useMemo`, `useCallback` – performance optimizations

**Rules:** Only call hooks at the top level, inside function components or custom hooks.

### What is React Router?

**React Router** is a standard library for routing in React.  
It enables navigation between different components (pages) in a single-page application (SPA) without reloading the page.

---

### Key Features

- Declarative routing using components like `<Route>`, `<Link>`, and `<Navigate>`
- Nested routes for complex layouts
- Dynamic route matching (e.g., `/users/:id`)
- Programmatic navigation using `useNavigate()`
- Route protection with wrappers or conditions

---

### Basic Example

```jsx
import { BrowserRouter, Routes, Route, Link } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link> | <Link to="/about">About</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

### Summary

React Router enables client-side routing in React apps—keeping the UI in sync with the URL without full page reloads.

## 8. AEM

### AEM Design Patterns

AEM (Adobe Experience Manager) design patterns are reusable best practices and structures for building scalable, maintainable AEM applications.

---

### Common AEM Design Patterns

- **Component-Based Architecture**  
  Build modular, reusable components that encapsulate both content and logic.

- **Sling Models**  
  Use Sling Models to map Sling resources to Java objects, making backend logic cleaner and easier to maintain.

- **HTL (Sightly) Templates**  
  Use HTL for secure, HTML-centric templating that separates markup from business logic.

- **Use of Client Libraries**  
  Manage CSS and JavaScript dependencies via clientlibs to optimize delivery and caching.

- **Dispatcher Caching**  
  Configure dispatcher caching rules to improve performance and scalability.

- **Content Fragment and Experience Fragment**  
  Leverage fragments to reuse content across pages and channels.

- **Event Handling with Observers**  
  Use event handlers and observers for asynchronous processing and decoupling.

- **Service Layer Design**  
  Implement service layers to encapsulate business logic, separate from component code.

---

### Summary

Following AEM design patterns leads to modular, maintainable, and performant AEM projects by leveraging componentization, proper templating, caching, and clean backend logic.

## AEM Connectors

**AEM Connectors** are integrations between Adobe Experience Manager and other Adobe or third-party systems to extend AEM’s capabilities and enable seamless workflows.

---

### Common AEM Connectors

- **Adobe Marketing Cloud**  
  Integrates AEM with Adobe Analytics, Adobe Target, and Adobe Campaign for unified marketing automation and personalization.

- **Adobe Asset Link**  
  Connects AEM Assets with Adobe Creative Cloud apps (Photoshop, Illustrator) to streamline asset management and editing.

- **Adobe Commerce (Magento)**  
  Syncs content between AEM and Magento to deliver rich shopping experiences with CMS-managed content.

- **Salesforce Connector**  
  Integrates AEM with Salesforce CRM for personalized customer experiences using CRM data.

- **Social Media Connectors**  
  Enable publishing and syndication of content to platforms like Facebook, Twitter, and LinkedIn.

- **DAM Connectors**  
  Sync third-party Digital Asset Management (DAM) systems with AEM Assets.

---

### Benefits of AEM Connectors

- Streamline workflows between marketing, creative, commerce, and sales teams
- Enable personalized, data-driven experiences
- Reduce manual data synchronization
- Enhance asset management and delivery

---

### Summary

AEM Connectors enable powerful integrations that extend AEM’s core features, making it a central hub for digital experience management.

## OSGi Lifecycle

OSGi (Open Services Gateway initiative) defines a dynamic module system for Java that manages the lifecycle of bundles (modules) at runtime.

---

### OSGi Bundle Lifecycle States

1. **Installed**  
   The bundle has been successfully installed but is not yet resolved.

2. **Resolved**  
   All dependencies are resolved; the bundle is ready to be started.

3. **Starting**  
   The bundle is in the process of starting. Its `BundleActivator.start()` method is called.

4. **Active**  
   The bundle is running and its services are available.

5. **Stopping**  
   The bundle is stopping. Its `BundleActivator.stop()` method is called.

6. **Uninstalled**  
   The bundle has been removed and is no longer available.

---

### Lifecycle Transitions

- Install → Resolve → Start → Active
- Active → Stop → Resolved
- Resolved → Uninstall → Uninstalled

---

### Summary

The OSGi lifecycle allows modular Java applications like AEM to dynamically install, start, stop, update, and uninstall components without restarting the entire system.

## Advantages of OSGi

- **Modularity**  
  Enables breaking applications into reusable, loosely coupled bundles (modules).

- **Dynamic Updates**  
  Supports installing, updating, and uninstalling bundles at runtime without restarting the application.

- **Versioning**  
  Allows multiple versions of the same bundle or library to coexist.

- **Service-Oriented**  
  Promotes service registration and discovery, enabling dynamic binding between components.

- **Improved Maintainability**  
  Smaller, focused bundles are easier to develop, test, and maintain.

- **Resource Isolation**  
  Bundles have their own classloaders, preventing class conflicts.

- **Scalability**  
  Suitable for large, complex applications that require modular architecture.

- **Used in Enterprise Platforms**  
  Foundation for systems like Adobe Experience Manager (AEM) and Eclipse.

---

### Summary

OSGi provides a flexible, modular framework that enhances application maintainability, scalability, and dynamic behavior.

====

1. Introduce yourself?

I am a core UI Developer with 12+ years of experience building .com websites for different organizations using HTML5, CSS3, JavaScript, Angular 18, React.js, and Redux.

In the past 2 years, I worked on the React migration team, where I converted the .NET pages to React on united.com.
Frontend is React, and used ATMOS (own library) components used company-wide.

Worked on security features for users where they can manage their account like Forgot Password, Forgot MileagePlus number,
security questions, Sign-in features, Miles-Pooling, United Club pass, Recent Activity, dashboard updates and
KTN (Known Traveler Number), Accessibility guidelines features on united.com.

Used middleware such as redux-saga to handle asynchronous tasks such as API calls, data fetching, and impure actions in a more organized and efficient way.

The new initiatives I worked on include Miles-Pooling (points you get after traveling), TSA Precheck, Account security and management features, and Under18.

Previously worked with the Accelerator team for Visa Inc. remediation of MBDA modules like Application Management, Account Management, Portfolio Management, Analytics, Recurring billing, Virtual Terminal, etc. for bank users like Wells Fargo, Bank of America, etc.

2. Explain the use of useCallback and useMemo for performance optimization in React.

In React, useCallback and useMemo are performance optimization hooks introduced in React 16.8.
They help prevent unnecessary re-renders and recalculations by memoizing functions and values.

useCallback – Memoizes Functions
Purpose: Prevents unnecessary re-creation of functions on re-renders.

When to use:
You're passing a function as a prop to child components (especially memoized ones).

The function would otherwise be re-created on every render, causing unnecessary re-renders.

example:
const handleClick = useCallback(() => {
console.log("Clicked!");
}, []); // only re-created if dependencies change

useMemo – Memoizes Computed Values
Purpose: Avoids recomputing expensive calculations on every render.

When to use:
You're doing heavy computations or transformations.

You want to avoid recalculating values unless dependencies change.

Example:
jsx

const sortedItems = useMemo(() => {
return items.sort((a, b) => a.value - b.value);
}, [items]); // recompute only when items change

3. Provide more details on the authentication approach using AWS services like API Gateway and S3.

"In AWS, I typically use Cognito User Pools for user authentication.
The frontend authenticates with Cognito and gets JWT tokens. These tokens are passed to API Gateway, which validates them before
routing requests to backend services like Lambda. For S3 access, I use pre-signed URLs generated by the backend, so the frontend
can securely upload or download files without directly exposing S3 credentials.
This ensures secure, scalable, and decoupled authentication across the application.

4. Elaborate on the implementation of column resizing in tables using data table libraries.

Implementing column resizing in data tables using libraries (like AG Grid, Material UI DataGrid, React Table, etc.)
generally involves enabling built-in features or customizing handlers for resizing logic.

1.  AG Grid – Built-in Column Resizing
    🔧 Configuration:
    AG Grid has native support for column resizing out of the box.

<AgGridReact
columnDefs={[
{ field: 'name', resizable: true },
{ field: 'age', resizable: true }
]}
defaultColDef={{ resizable: true }}
rowData={rowData}
/>

2. Material UI (MUI) DataGrid
   🔧 Column Resizing (Pro/Premium):
   MUI DataGrid Pro supports column resizing by enabling the prop:

jsx
Copy
Edit
<DataGrid
  columns={columns}
  rows={rows}
  disableColumnResize={false}
/>

3. React Table (Headless Table Library)
   🔧 Manual Column Resizing:
   React Table doesn’t include UI, but provides hooks to build column resizing behavior.

Example setup using useResizeColumns plugin:
tsx

const tableInstance = useTable(
{
columns,
data,
},
useResizeColumns,
useFlexLayout // for flexible layouting
);
Then in your column header component:

jsx
Copy
Edit

<div {...header.getResizerProps()} className="resizer" />
🛠️ Customization:
Full control over how the resizing UI looks.
Supports minWidth, maxWidth, and persistence via local storage.

4. PrimeReact Table (DataTable)
   🔧 Enable Resizing:
   jsx

<DataTable value={data} resizableColumns columnResizeMode="fit">
  <Column field="name" header="Name" />
  <Column field="age" header="Age" />
</DataTable>

🛠️ Modes:
"fit": Adjust other columns accordingly.
"expand": Increase table width on resize.

5. Provide more information on the features and capabilities of AWS Amplify.

1. 🔐 Authentication
   Cognito-based user authentication out-of-the-box.

Prebuilt UI components for sign-up, sign-in, multi-factor auth (MFA), social login (Google, Facebook, Amazon, Apple).

Supports OAuth2 and OpenID Connect.

Fine-grained access control using Cognito User Pools and Identity Pools.

2. 📦 API (GraphQL + REST)
   Auto-generates backend APIs via:

GraphQL (AppSync) – with real-time subscriptions.

REST APIs using API Gateway + Lambda.

Works with custom resolvers and existing APIs.

Strong integration with DynamoDB and other data sources.

Offers auto-generated queries/mutations for GraphQL.

3. 💾 Data Storage
   Supports both:

NoSQL via Amazon DynamoDB.

File/object storage via Amazon S3.

Built-in support for public/private/protected access levels.

S3 uploads/downloads integrated with Cognito identity-based roles.

4. 🧠 AI/ML Integration
   Connects with AWS AI/ML services:

Rekognition (image & video analysis),

Polly (text-to-speech),

Comprehend (NLP),

Translate, Lex, and more.

Easily accessible via Amplify CLI or JS/React Native libraries.

5. 🌐 Hosting & Deployment
   Fully managed static site hosting for React, Angular, Vue, Next.js, Gatsby, etc.

Supports CI/CD pipelines from GitHub, GitLab, Bitbucket, or AWS CodeCommit.

Instant rollbacks, custom domains, password protection.

6. Explain the process of resolving CORS issues by enabling CORS policies in the backend API.

What is a CORS Issue?
CORS is a security mechanism implemented by browsers to restrict cross-origin HTTP requests initiated by scripts in a web page.

A CORS issue occurs when your frontend (e.g., running at http://localhost:3000) tries to access an API at a different origin (e.g., https://api.example.com) and the server doesn’t explicitly allow it.

Solution: Enable CORS on the Backend API
You need to configure your backend to send the correct CORS headers in the response, especially:

Access-Control-Allow-Origin

Access-Control-Allow-Methods

Access-Control-Allow-Headers

Access-Control-Allow-Credentials (if using cookies/auth headers)

7. Explain the react.js architecture you followed?

React.js Architecture I Followed
The architecture I typically follow is a modular, scalable, and component-driven architecture, aligned with best practices for enterprise-grade applications.

🔧 1. Project Structure
less
Copy
Edit
src/
│
├── assets/ // Static assets like images, fonts, styles
├── components/ // Reusable shared UI components (Buttons, Modals, Inputs)
├── features/ // Feature-specific folders (e.g., auth, dashboard, profile)
│ └── FeatureName/
│ ├── components/ // Feature-specific components
│ ├── hooks/ // Custom React hooks
│ ├── services/ // API calls, GraphQL queries/mutations
│ └── FeatureName.tsx
├── hooks/ // Global custom hooks
├── contexts/ // Context API for global state (theme, auth)
├── store/ // Redux or Zustand store (if applicable)
├── utils/ // Utility functions, constants, validators
├── routes/ // Route configurations and protected routes
├── api/ // API clients (Axios, GraphQL client)
├── App.tsx // Main App component
└── main.tsx / index.tsx // Entry point

🧩 2. Component-Based Design
Follow atomic design principles:

Atoms (buttons, inputs)

Molecules (forms, cards)

Organisms (pages, sections)

Promotes reusability and testability.

⚛️ 3. State Management
Local state via useState, useReducer.

Context API for global but lightweight state (theme, language).

Redux (with Redux Toolkit) or Zustand for large-scale apps.

Redux Saga or Thunk for async logic.

🔗 4. API Layer
Abstracted API calls using Axios or GraphQL client.

Centralized error handling and token injection via interceptors.

Services organized by feature (e.g., authService.ts, userService.ts).

🧠 5. Hooks & Custom Logic
Use of custom hooks like useAuth, useFetch, useDebounce, useFormValidation.

Keeps logic reusable and clean across components.

🛣️ 6. Routing
React Router v6+ with:

Lazy loading via React.lazy and Suspense.

Protected routes using wrapper components.

Nested and dynamic routes.

🧪 7. Testing
Unit testing with Jest and React Testing Library.

Component-level tests for UI logic.

Integration tests for critical flows.

💅 8. Styling
Tailwind CSS or CSS Modules for scoped styles.

Sometimes use Styled Components for dynamic styling.

Follows BEM or utility-first methodology depending on project.

🌍 9. Internationalization (i18n)
Integrated react-i18next for multilingual support.

Language context and switcher built at the layout level.

🔐 10. Authentication & Authorization
Token-based auth using JWT.

Auth state persisted via localStorage or cookies.

Role-based UI rendering and route protection.

8. How the code review process done in your company?

9. 2 coding questions: javascript and react.js?

10. what are Lifecycle methods?

React component lifecycle has three categories – Mounting, Updating and Unmounting.
Mounting – Birth of your component
Update – Growth of your component
Unmount – Death of your component

React Component LifeCycle Hooks

        1. constructor
        2. componentWillMount()
        3. render()
        4. componentDidMount()
        5. componentWillReceiveProps()
        6. shouldComponentUpdate()

        // component kill methods

        7. componentWillUpdate()
        8. componentDidUpdate()
        9. componentWillUnmount()

===

1. Tell me about your exprience with react.js and node.js?

I have extensive experience with both React.js and Node.js, and have used them together to build full-stack applications across several enterprise projects.

🔷 React.js Experience (Frontend)
I’ve been working with React for over 6 years, using it to build complex, modular, and scalable UI applications. Some highlights include:

At Visa, I built accessibility-first modules like Application Management using React + Redux-Saga, ensuring compliance with WCAG and VGAR.

At United Airlines, I led part of the React migration effort for key modules like My Account, TSA Precheck, and Miles Pooling.
I implemented feature-rich, responsive components and managed state with Redux.

At Capital Group, I built data visualizations from scratch using React + Highcharts, and embedded them in AEM for advisor-facing platforms.

I follow best practices around component architecture, state management, lazy loading, memoization, and testing with Jest and React Testing Library.

I’ve also worked on responsive design, performance optimization, custom hooks, and integration with tools like Google Analytics and Quantum Metric.

🔷 Node.js Experience (Backend/API Layer)
On the backend, I’ve used Node.js with Express to build REST APIs, microservices, and middleware layers:

I’ve written Node.js services to support React apps, handling tasks like user authentication, data aggregation, and CRUD operations.

Integrated APIs with AWS services like S3, CloudWatch, and Lambda.

For authentication, I’ve implemented middleware using JWT and integrated with Cognito when using Amplify.

I’m comfortable with API versioning, error handling, request validation, and logging using tools like Winston or Morgan.

In many projects, I’ve worked as a full-stack developer, so I’m very comfortable architecting solutions that bridge both React and Node, ensuring a clean separation of concerns, and aligning with business and product needs.

2. how many years of experience do you have on node.js? 4 to 5 years of experience with Node.js

3. have you use Jira and confluence?

Yes, I’ve used both Jira and Confluence extensively across multiple projects.

I use Jira daily for managing sprints, tracking user stories, bugs, and tasks in Agile environments.
I’m comfortable creating custom filters, dashboards, and working with different workflows.

I use Confluence for documenting features, technical designs, release notes, and onboarding guides.
At Visa and United Airlines, I regularly maintained module-level documentation and supported cross-team collaboration using shared Confluence spaces.

4. Are you familiar with Testing?

es, I’m familiar with both unit and end-to-end testing.

I’ve written unit tests using Jest and React Testing Library for React components — covering props, state, and rendering logic.

For backend testing in Node.js, I’ve used Mocha, Chai, and Supertest to validate API endpoints and middleware.

I’ve also worked with E2E testing tools like Cypress and Protractor in projects requiring full workflow validation.

In my past roles, especially at Visa and United Airlines, I followed Test-Driven Development (TDD) in some modules and collaborated with QA teams using Jira to triage and verify bugs.

I make testing a core part of my development cycle to ensure code reliability and catch regressions early.

5. Have you worked on Data Visulization?

Yes, I’ve worked extensively on data visualization.

At Capital Group, I built interactive data visualizations from scratch using React and Highcharts for modules like Asset Mix, Credit Quality, and Income Objective.
These charts were embedded into AEM-based advisor websites and designed to be dynamic, responsive, and WCAG-compliant.

I’ve also customized tooltips, legends, and interactivity, and ensured performance even with large datasets.
In other projects, I’ve used Chart.js and D3.js when specific chart types or animations were required.

6. Have you built apps from scratch? which project? explain

Yes, I’ve built several applications from scratch. One example is the Davis data visualization app at Capital Group.

I was responsible for gathering requirements, setting up the project architecture with React, building reusable chart components using Highcharts, integrating APIs, handling accessibility (WCAG), and deploying the app on AWS (S3 + CloudFront). I also handled embedding the charts into AEM pages and coordinated with design and QA teams throughout the release cycle.

Another example is at Visa, where I built internal tools like Application Management and Release Management modules from the ground up using React, Redux-Saga, and AWS services. I set up the full frontend workflow — including routing, API integration, state management, and accessibility compliance.

7. which version control tools did you work on?

I’ve worked with several version control tools, primarily:

Git – My main tool for source control in all recent projects. I’ve used it with platforms like GitHub, Bitbucket, and GitLab for branching, pull requests, and code reviews.

SVN – I used it in earlier projects before transitioning fully to Git.

I follow best practices like feature branching, commit hygiene, rebasing when needed, and tagging for releases.
I’ve also helped teams establish branching strategies (like GitFlow) and integrated version control into CI/CD pipelines.

8. how to implement security in Frontend application?

To implement security in a frontend application, I follow several best practices:

Authentication & Authorization:

Use token-based auth (like JWT) securely stored in HTTP-only cookies or in-memory.

Enforce role-based UI rendering — show/hide features based on user roles.

Input Validation & Sanitization:

Sanitize all user inputs to prevent XSS (Cross-Site Scripting).

Use libraries like DOMPurify when rendering dynamic HTML.

Secure API Communication:

Always use HTTPS.

Avoid storing tokens in localStorage (use session or cookies).

Sign requests or use OAuth/Cognito for secure access.

Error Handling:

Avoid exposing stack traces or sensitive data in frontend errors or console logs.

Content Security Policies (CSP):

Work with backend teams to set headers that protect against script injection.

Prevent Clickjacking:

Use X-Frame-Options: DENY or equivalent headers.

Package Audits:

Regularly audit third-party libraries with tools like npm audit.

9. Have you worked on Greenfield (from scratch) or brownfield?

Yes, I’ve worked on both greenfield and brownfield projects.

In greenfield projects, like the Davis visualization app at Capital Group, I built the app entirely from scratch — setting up the React architecture, chart components, API integration, accessibility, and deployment on AWS. I also defined folder structure, code standards, and reusable components.

In brownfield projects, like at United Airlines, I worked on migrating legacy .NET modules to React. This involved integrating with existing systems, refactoring old code, improving accessibility, and modernizing the UI while ensuring backward compatibility.

I’m comfortable starting clean or enhancing existing systems based on the project needs.

10. are you individual contributor?

Yes, I primarily work as an individual contributor focusing on delivering high-quality frontend features and components.
For example, at United Airlines, I worked independently on the React migration of modules like Forgot Password and United Club Pass, ensuring accessibility compliance and smooth integration with backend services.
While I collaborate closely with product owners and cross-functional teams, I take ownership of my assigned tasks from development to deployment.

11. Which project did you work on node.js?

I worked on several projects involving Node.js. At Office Depot, I used Node.js alongside React to build business applications that followed W3C standards.
I was responsible for designing scalable web interfaces and integrating RESTful APIs developed in Node.js.
Additionally, my experience includes using Node Package Manager (NPM) for managing dependencies and building frontend packages.

12. For backend which technologies have you worked on?

In my backend experience, I have worked primarily with Node.js to build scalable APIs and server-side logic. For example, at Office Depot, I used Node.js alongside React to create web applications and handle backend service calls.

Additionally, I have experience working with Java-based technologies such as SpringBoot and J2EE, which I used in some enterprise applications to develop RESTful services and business logic.

I’m also familiar with API integration, database interactions, and tools related to backend development such as IBM Websphere and CI/CD pipelines for deployment and testing automation.

13. Have you worked on CI/CD pipeline deployment?

Yes, I have experience working with CI/CD pipelines to automate build, test, and deployment processes. For instance, at Capital Group and other projects, I collaborated with DevOps teams to integrate frontend and backend code deployments into CI/CD workflows.

I’m familiar with tools like Jenkins, GitHub Actions, and automated testing frameworks such as Karma and Jasmine for ensuring code quality during the pipeline. This helped us achieve faster release cycles and more reliable production deployments.

====
Infosys Interview - 30 minutes

1. How to handle performance in react app in your company?

1. Memoization with useMemo and useCallback: Use this hooks to memoize values and, reducing unnecessary recalculations.
1. Optimizing Renders with React.Fragment: Use it to avoid unnecessary wrapper elements that could cause additional DOM nodes.
1. Lazy loading with React.lazy: Use it to load components lazily, reducing the intial bundle size and imporving intial loading performance.
1. Code splitting: Employ code splitting to divide your application into smaller chunks that are loaded on demand, improving initial load times.
1. Optimizing Images and Assets: Compress and optimize images, use responsive images and leverage lazy loading for images to reduce network and rendering overhead.

1. Find and filter.

find and filter are array methods used to search and extract elements:

find() returns the first element in the array that matches a condition.
→ Example: arr.find(item => item.id === 1);

filter() returns all elements that match the condition in a new array.
→ Example: arr.filter(item => item.active);

3. getServerSideProps and then getInitialProps.

getServerSideProps is server-only per request.

getInitialProps runs on both client and server, depending on the navigation.

4. In parent component, I have multiple child components. I am trying to update one of the child components. It is re-rendering everything.
   So whatever the components we have under parent, also parent, everything is getting re-rendered. So what could be the reason for that? How you can fix that?

When a parent re-renders, all child components re-render by default.
This happens if state or props change, or if functions/objects are re-created on each render.

To fix it:

Use React.memo for child components.

Use useCallback / useMemo to prevent unnecessary prop changes.

Keep state local to the component that needs it.

5. Like I have a component, okay, like, say, a checkbox, the initial value is false, okay? When I try to check the checkbox, okay, it shows me false.
   Ideally, I should get true. It shows me false. So what could be the reason how you can fix it?

Problem Breakdown
You're saying:

Checkbox has an initial value of false.

When you click to check the checkbox, it should update to true.

But it's still showing false.

This likely means the checkbox is not updating the state properly, or it's not controlled correctly.

Fix Strategy
Ensure your checkbox is controlled: use checked={state} and onChange={handler}.

Use e.target.checked to set the state.

6. So that's the value I have it in array. I want only the value 1. So remaining things will be skipped and the output will be 1. Only 1. With the help of... Number 1.
   So it will be like inside array, we will have 2 1s. Okay. So how you can do that? I think we can use like the key property.

react.js, next.js, node.js

// Online Javascript Editor for free
// Write, Edit and Run your Javascript code using JS Online Compiler

// interview with infosys

// Output: Interview With Infosys

function toCamelCase(str){
return str.toLowerCase().split(' ').map(word => word.charAt(0).toUpperCase() + word.slice(1)).join(' ');
}

console.log(toCamelCase('inetrview with infosys'));

// Inetrview With Infosys

# === Code Execution Successful ===

can you tell the output:

const obj1 : {
const a = 1;
const b= funtion;
}

const c = b();

obj1().b;
c();

==========================

1. Can you quickly introduce yourself and your skills?

I am a core UI Developer with 12+ years of experience building .com websites for different organizations using HTML5, CSS3, JavaScript, Angular 18, React.js, and Redux.
In the past 2 years, I worked on the React migration team, where I converted the .net pages to react on united.com.
Frontend is React, and used ATMOS (Own library) components used company wide.

Worked on Security features for users where they can manage there account like Forgot password, Forgot MileagePlus number,
security questions, Sign-in features, Miles-Pooling, United Club pass, Recent Activity, dashboard updates and
KTN(Known Traveler Number), Accessibility guidelines features on united.com.

used middleware such as redux-saga to handle asynchronous tasks such as API calls, data fetching, and impure actions in a more organized and efficient way.

The new initiative worked on Miles-Pooling( points you get after traveling), TSA Precheck, Account security and management features, and Under18.

Previously worked with Accelerator team for Visa Inc. remediation of MBDA modules like Application Management, Account Management, Portfolio Management, Analytics, Recurring billing, Virtual Terminal, etc for bank users like Wells Fargo, Bank of America, etc

==============================

2. what is the architecture you followed in united ?

At United Airlines, I was part of the React migration team, where we modernized legacy .NET pages into React apps on united.com. We used a micro frontend architecture with company-wide ATMOS component libraries to ensure consistency.

I focused on account security and user management features—like Forgot Password, MileagePlus recovery, Sign-In, Miles-Pooling, KTN, TSA PreCheck, United Club Pass, and Under18 account handling—while adhering to accessibility (WCAG) guidelines.

For state management and async flows, we used Redux with redux-saga to handle API calls and side effects in a scalable way.

On the backend, we integrated with microservices via REST and GraphQL APIs. Middleware services were deployed using Node.js, and AWS components like Lambda, API Gateway, and DynamoDB supported event-driven workflows.

The overall architecture supported modular, scalable, and secure development with strong CI/CD and observability practices.

3. why did you choose react.js?

We chose React.js for its component-based architecture, which made it easy to build reusable, scalable UIs.
It worked well with our ATMOS design system and micro frontend approach.
React also offered great performance and strong ecosystem support with tools like Redux and redux-saga for managing complex state and async tasks.

4. did you work on production related bugs?

Yes, I actively worked on production-related bugs. This included triaging issues reported by users or monitoring tools,
reproducing them in lower environments, and providing quick yet stable fixes. I used tools like Chrome DevTools, Postman, and
application logs (via CloudWatch or console logs) to debug issues. After identifying the root cause, I would implement fixes,
test thoroughly, and push changes through the CI/CD pipeline to production with minimal downtime.
I also updated Confluence documentation and communicated changes with QA and product teams to ensure smooth releases.

5. What is a State?

In React, state is a built-in object used to store data that can change over time and impact how a component renders.

When the state changes, React automatically re-renders the component to reflect the new data.

For example, in a user profile component, the user’s name, login status, or input fields can be part of the state.

Why Do We Need State?

We need state in React to:

Track dynamic data: such as form inputs, API responses, UI toggles (like modals or dropdowns), etc.

Enable interactivity: like incrementing a counter, switching tabs, or filtering data.

Trigger re-renders: When state changes, React automatically re-renders the component to reflect the new data in the UI.

6. What is HTTP and HTTPS protocol?

HTTP (HyperText Transfer Protocol) is a protocol used for transferring data between a web browser (client) and a web server.
It is the foundation of any data exchange on the web and operates over port 80 by default.

It's stateless – each request is independent.

It transfers data in plain text, which is not secure.

What is HTTPS?
HTTPS (HyperText Transfer Protocol Secure) is the secure version of HTTP.
It uses SSL/TLS encryption to secure the communication between the browser and the server. It operates over port 443.

Encrypts data to protect it from hackers.

Ensures data integrity and authentication (via SSL certificates).

Used for secure transactions, like banking, logins, and e-commerce.

7. What is autodeploy.com/admin URL?

The URL autodeploy.com/admin likely refers to an internal deployment admin dashboard or portal used by your team or organization to:

Trigger deployments

Monitor pipeline statuses

Manage environments (Dev, QA, Staging, Production)

Rollback or restart builds

Review deployment logs and artifacts

This kind of admin interface is commonly seen in custom CI/CD solutions or tools like Jenkins, TeamCity, GitLab CI, or AWS CodePipeline.

8. how does the data flows into reactJS?

In React, data flows in one direction — this is called unidirectional data flow.

From Parent to Child (via Props)
Props (short for properties) are used to pass data from parent components to child components.

Props are read-only in the child component.

jsx

function Parent() {
return <Child name="Vijay" />;
}

function Child(props) {
return <p>Hello, {props.name}</p>;
}

9. Can you draw the architecture of your application?

Typical Architecture of United.com (or any major airline booking site)

User (Customer)
│
▼
[Web Client / Mobile App]
(React/Angular/Next.js frontend)
│
▼
[Content Delivery Network (CDN)]
(e.g., Akamai, Cloudflare)
│
▼
[Web Server / Application Server]
(Load Balanced, Auto-scaled)
│
▼
[API Gateway / Backend Services]
├── Flight Search Service (queries availability, fares)
├── Booking & Reservation Service
├── User Profile & Authentication Service
├── Payment Gateway Integration
├── Loyalty / Mileage Program Service
└── Customer Support & Chatbot Service
│
▼
[Database Layer]
├── Relational DB (Bookings, Users, Flights)
├── NoSQL DB (Sessions, Caching)
└── Analytics DB (User behavior, logs)
│
▼
[Third-Party Integrations]
├── Global Distribution Systems (GDS) like Sabre, Amadeus
├── Payment Processors (Stripe, Visa, Mastercard)
├── Identity Verification Providers
└── External APIs (Weather, Flight Status)

Explanation:
User: Browses the site or app.

Web Client: Frontend running React or similar SPA framework to provide smooth interactive experience.

CDN: Delivers static assets fast worldwide.

Web Server: Handles dynamic requests and serves frontend.

API Gateway: Routes to microservices handling specific business logic.

Backend Services: Core flight search, booking, user management, and payment.

Database: Stores all persistent data securely.

Third-Party Integrations: Connects to global flight inventories and payment providers.

10. can you walk me through how your united.com app works?

11. What is MVC architecture? what is View?

MVC stands for Model-View-Controller, a widely used software design pattern for organizing code, especially in web and desktop applications.
It separates an application into three main components to promote organized, reusable, and maintainable code.

Components of MVC:
Model

Represents the data and the business logic of the application.

It directly manages the data, rules, and logic (e.g., database records, validation).

When data changes, the Model notifies the View to update accordingly.

View

The user interface (UI) or presentation layer.

It displays data from the Model to the user.

It listens to Model changes and updates the UI accordingly.

Controller

Acts as an intermediary between Model and View.

Handles user input (like clicks, typing) and commands Model to update or retrieve data.

Selects which View to display based on interactions.

What is the View in MVC?
The View is what the user sees and interacts with — the layout, buttons, text, images, forms, etc.

It renders the data it receives from the Model into a user-friendly interface.

In web apps, Views are often HTML/CSS templates or frontend components.

Views don’t handle business logic — their job is just to present data and capture user interactions to send to the Controller.

Simple Analogy
Imagine an app for booking flights:

Model: Flight data, user info, booking records.

View: The booking form, flight search results page, confirmation page.

Controller: Handles clicking “Search Flights,” tells Model to find flights, and tells View to display the results.

12. Is React MVC architecture?

No, React is not strictly an MVC (Model-View-Controller) framework.

React focuses only on the View layer of an application.

It’s a UI library used to build user interfaces by breaking them into reusable components.

If you need full MVC-like structure, you can combine React with other libraries for state management (like Redux for the Model)
and routing/controllers (like React Router).

13. suppose 100 lines of code how does change happen?

In React, when there’s a change—like user input or new data—state or props get updated.

React then creates a virtual DOM, compares it with the previous virtual DOM (this process is called reconciliation), and
calculates the minimal set of changes needed.

Only those specific parts of the real DOM are updated, which makes the UI efficient and fast, even if the codebase is large,
like 100 lines or more.

14. What is DOM?

DOM stands for Document Object Model. It’s a programming interface that represents the structure of an HTML or XML document as a tree
of objects. Each element, attribute, and piece of text in the document becomes a node in this tree,
which can be accessed and manipulated using JavaScript to dynamically update the webpage.

15. What is parent?

A parent is a component or element that contains one or more child components or elements within it.
In React, the parent component can pass data and functions down to its child components via props.

16. what is child?

A child is a component or element that is nested inside a parent component.
It can receive data and functions from the parent through props and can also communicate back through callbacks or events.

17. How state works in redux? example?

In Redux, the entire app state is stored in a single store. To change state, you dispatch actions describing what happened.
Reducers receive these actions and return a new state based on the action type. This makes state predictable and easy to manage.

18. What kind of state react supports?

In Redux, the entire app state is stored in a single store.
To change state, you dispatch actions describing what happened.
Reducers receive these actions and return a new state based on the action type.
This makes state predictable and easy to manage.

19. username, password where does the data go?

When a user enters their username and password, the data is sent securely from the frontend to the backend via an API call,
usually over HTTPS to protect it in transit. On the backend, the credentials are validated against stored data, often in a database.
Passwords are never stored in plain text—they are hashed and salted before saving.
If authentication succeeds, the backend typically returns a token or session ID for the frontend to manage user sessions securely.

20. have you used Azure, AWS for deployment of the code?

Yes, I have experience deploying applications on AWS.

We used services like ECS Fargate for container deployment, Lambda for serverless functions, API Gateway for managing APIs, and S3 for storage.
CI/CD pipelines were set up using GitLab and AWS CodePipeline for automated, reliable deployments.

I have less direct experience with Azure but am familiar with its core services and concepts."

21. why did you use redux-saga? purpose? what side effects did you handle?

We used redux-saga to handle side effects like asynchronous API calls, data fetching, and other impure actions in a more organized and testable way.
Redux-saga uses generator functions, which made managing complex async flows—like user authentication, account security updates,
and Miles-Pooling operations—simpler and easier to maintain.
It helped us keep the Redux store pure and the UI responsive."

22. open a notepad and tell me what is parent and child? with example?

Parent and Child:

A parent component is a component that contains or renders other components.

A child component is a component nested inside the parent.

The parent can pass data to the child via props, and the child can communicate back through callbacks.

Example:

jsx
Copy
Edit
// Parent Component
function Parent() {
const message = "Hello from Parent";

return <Child text={message} />;
}

// Child Component
function Child(props) {
return <h1>{props.text}</h1>;
}
In this example, Parent is the parent component that passes the message to the Child component as a prop named text.

23. why is react.js unidirectional?

React is unidirectional because data flows in one direction—from parent to child via props.
This makes the app more predictable and easier to debug, as each component clearly knows where its data is coming from.

24. did you work on backend also?

Yes, I’ve worked on the backend as well. I’ve used Node.js and NestJS to build RESTful and GraphQL APIs, handled authentication logic,
and integrated with AWS services like Lambda, API Gateway, and DynamoDB.
I’ve also worked on business logic for features like Miles-Pooling, TSA PreCheck, and account security.

25. have you used cloud deployments like AWS, azure?

Yes, I’ve used AWS for cloud deployments. I’ve deployed microservices using ECS Fargate, used Lambda for serverless functions,
API Gateway for routing, and S3 for static content. I’ve also set up CI/CD with GitLab and AWS CodePipeline.
I’m familiar with Azure concepts but have mainly worked hands-on with AWS.

26. redux architecture how to did you implement in your previous company?

In my previous project at United Airlines, we implemented Redux to manage global state across the React app.
We used redux for state management, redux-saga for handling async tasks like API calls, and react-redux for connecting components to the store.
Each feature had its own actions, reducers, and sagas to keep things modular.
This made the app scalable and helped us manage complex flows like user sign-in, Miles-Pooling, and security features more cleanly."

27. how do you deploy your code ? which application?

We deployed our code using the internal deployment tool autodeploy.com/admin.
It allowed us to promote builds across environments like Dev, QA, and Pre-Prod with a few clicks.
The React frontend and Node.js backend were built through GitLab CI/CD pipelines, and the deployment tool handled version tagging,
environment selection, and automated rollouts.
This made our deployment process streamlined and consistent across all stages.

====
technical interview questions

---

1. tell me about yourself?

2. which version of react.js are using? v16.8, react 18, v19 dec 5th, 2024

3. what is async await?

In JavaScript, async and await are used to handle asynchronous operations in a more readable and manageable way, replacing traditional callback-based approaches.

Explanation
async function: Declares that a function returns a Promise, allowing you to use await inside it.

await keyword: Pauses execution until a Promise resolves, making asynchronous code look more like synchronous code.

Key Benefits
Makes asynchronous code easier to read.

Helps avoid callback hell.

Improves error handling with try-catch.

4.  what is synchronous vs asychronous?

Synchronous Code
Executes line by line, meaning each operation must finish before the next one starts.

Blocking: If one task takes a long time, everything after it waits.

Asynchronous Code
Executes without waiting for a previous task to complete.

Non-blocking: Tasks can run independently, allowing multiple operations to happen simultaneously.

Often uses callbacks, Promises, or async/await.

5. how to call multiple api calls simunatenously?

You can call multiple API requests simultaneously using Promise.all, Promise.allSettled, or async/await with parallel execution.

Using Promise.all (Best for Successful Responses)

✅ Executes all requests in parallel ❌ Fails completely if one request errors out

Using Promise.allSettled (Handles Errors Gracefully)

✅ All requests execute, even if some fail ✅ Provides individual success/failure reports

Using async/await with Parallel Execution
✅ Parallel execution without Promise.all ✅ More control over individual responses

Which One Should You Use?
Use Promise.all when all API calls must succeed together.

Use Promise.allSettled when you want results even if some APIs fail.

Use async/await for a more manual approach with better readability.

6. what is controlled and uncontrolled components?

Use controlled components for most cases where React state should manage inputs.

Use uncontrolled components if you need direct DOM access or lightweight components.

7. what is Debouncing ?

Debouncing is a technique used to improve performance by limiting the rate at which a function executes.
It ensures that a function (typically event handlers like input changes, scrolling, or resizing) only runs after a specified delay, preventing unnecessary executions.

8. What is useEffect hook?
   The useEffect hook in React is a powerful tool used for managing side effects in functional components.
   It allows you to run logic after the component renders, handling things like data fetching, subscriptions, or updating the DOM.

How Does useEffect Work?
It executes after the component renders.

Can run once, on updates, or on cleanup—depending on dependencies.

Helps avoid unnecessary logic inside the main component body.

9. did you work on custom hooks?
   A custom hook in React is a reusable function that encapsulates logic using other React hooks (useState, useEffect, etc.).
   It allows you to extract common behavior from components and keep them clean and maintainable.

Common Use Cases for Custom Hooks
API calls (useFetch)

Local storage management (useLocalStorage)

Form validation

Handling authentication

Debouncing functions

10. how to make api call without useEffect?

You can make API calls in React without using useEffect by triggering them inside event handlers, functions, or lifecycle methods in class components.

11. What is promise.All() and race?

Both Promise.all and Promise.race are useful methods for handling multiple promises in JavaScript, but they behave differently.

Promise.all (Waits for All Promises to Resolve)
Promise.race (Returns the First Settled Promise)

12. How do you integrate 2 API in front end with useEffect?

Use Promise.all inside one useEffect → When both APIs need to be fetched together.

Use multiple useEffect hooks → When API calls are independent.

13. How Do Uncontrolled Components Work?

The value of an input field is stored directly in the DOM.

React does not track state updates for the input field.

You access the current value when needed, usually via useRef.

14. redux architecture?

Redux is a state management library for JavaScript applications, commonly used with React.
It follows a predictable, unidirectional data flow, making state management more manageable, especially for large applications.

Redux Data Flow
Redux follows a structured flow to ensure predictable state updates:

1️⃣ Action → Describes what happens (e.g., "ADD_ITEM").
2️⃣ Reducer → Handles the action and updates state.
3️⃣ Store → Holds the global application state.
4️⃣ View (React Component) → Receives state data and dispatches actions.

15. what is == vs ===

== and === are comparison operators, but they behave differently in terms of type coercion.

Which One Should You Use?

Use === (strict equality) in most cases to avoid unexpected behavior.

Use == only when intentional type conversion is required.

16. can you explain your implementation
    // write code for 1 text field, enter the data.
    // display table product id, name, description
    //top of table display text field and search button - click on search need to show table with hardcode data.

17. have you worked as a LEAD?

"Yes, I’ve worked as a lead on multiple React projects.
I was responsible for guiding the team on best practices, making architectural decisions, and ensuring scalable and maintainable code.
I also mentored junior developers and conducted code reviews to maintain high coding standards.
My role involved close collaboration with stakeholders to align development with business goals."

18. what is return and commit in JSX?

return is essential in JSX—it defines the UI a component renders.

commit is part of React’s internal lifecycle—it happens when React applies changes to the DOM.

Developers rarely interact with "commit" directly, but useEffect runs after React commits updates.

19. What is map()? and reduce()?

Use map() when transforming each item (e.g., formatting names, adjusting values).

Use reduce() when combining data into a single result (e.g., summing prices, merging arrays).

20. what is the output of map()?

The output of map() is always a new array with transformed elements based on the function provided.

✅ The original array remains unchanged ✅ The new array contains modified elements

Key Takeaways
map() always returns a new array (original array stays untouched).

The number of elements remains the same, unless explicitly modified.

Works well for transforming data (e.g., formatting, extracting values, modifying structures).

===
30 minute interview

Senior React.js Developer Interview Question and Answers.

1. Tell me about yourself?

I am a core UI Developer with 12+ years of experience building .com websites for different organizations using HTML5, CSS3, JavaScript, Angular 18, React.js, and Redux.
In the past 2 years, I worked on the React migration team, where I converted the .net pages to react on united.com.
Frontend is React, and used ATMOS (Own library) components used company wide.

Worked on Security features for users where they can manage there account like Forgot password, Forgot MileagePlus number,
security questions, Sign-in features, Miles-Pooling, United Club pass, Recent Activity, dashboard updates and
KTN(Known Traveler Number), Accessibility guidelines features on united.com.

used middleware such as redux-saga to handle asynchronous tasks such as API calls, data fetching, and impure actions in a more organized and efficient way.

The new initiative worked on Miles-Pooling( points you get after traveling), TSA Precheck, Account security and management features, and Under18.

Previously worked with Accelerator team for Visa Inc. remediation of MBDA modules like Application Management, Account Management, Portfolio Management, Analytics, Recurring billing, Virtual Terminal, etc for bank users like Wells Fargo, Bank of America, etc

Capital Group worked on DAVIS Project. Davis stands for Data visualization where we build different highcharts using react and integrate into the AEM., the backend is Java. Previously I worked on Creative Workbench, a writing tool where articles are published on capital group websites.

At Cerner Corporation worked on the medical examination forms.

In Office Depot worked on black Friday reporting.

Satinos Technologies created a tax portal and a schoomin website for the Vignan schools.

2. React Hooks: Hooks are functions that enable functional components to manage state and lifecycle features, providing a more concise and expressive way to handle component logic.

3. What are the popular hooks in react and explain it's usage?

useState: Manages state in functional components.
useEffect: Manages side effects in functional components.
useContext: Consumes context in functional components.
useReducer: Manage state with a reducer function, For More complex state management.
useRef: Accesses DOM elements or stores mutable values.
useCallback: performance improvement usecase
useMemo: performance improvement usecase.

4. How can you Optimize Performance in React application?
1. Memoization with useMemo and useCallback: Use this hooks to memoize values and, reducing unnecessary recalculations.
1. Optimizing Renders with React.Fragment: Use it to avoid unnecessary wrapper elements that could cause additional DOM nodes.
1. Lazy loading with React.lazy: Use it to load components lazily, reducing the intial bundle size and imporving intial loading performance.
1. Code splitting: Employ code splitting to divide your application into smaller chunks that are loaded on demand, improving initial load times.
1. Optimizing Images and Assets: Compress and optimize images, use responsive images and leverage lazy loading for images to reduce network and rendering overhead.

1. Difference between virtual DOM and real DOM?
   Suppose line of code is changed , processing is done on particular line. It will process the whole code in real DOM. Virtual DOM is faster.

1. Redux is a predictable state container for JavaScript applications.
   It helps to you write applications, run in different environments and easy to test.
   And simply we called as Redux is a state management tool.
   Components in redux
   Actions -->Input Parameters Ex: Deposit and Withdraw money from ATM
   Store --> Main Server
   Reducers --> Business Logic
   Dispatch --> Request
   Subscribe --> Response
   State --> Store Component Data

1. What is state management in react application? 3rd party module, with redux.
   Redux? We have redux thux, redux saga.
   What is redux thunx, redux saga? Inorder to manipulate the store Actions(request, response).
   Redux thunx is an outdated library.
   Saga is Advanced library.

Why Saga? In sagas debouncing is available by default.

8. Explain React lifecycle methods?

React component lifecycle has three categories – Mounting, Updating and Unmounting.
Mounting – Birth of your component
Update – Growth of your component
Unmount – Death of your component

React Component LifeCycle Hooks

        1. constructor
        2. componentWillMount()
        3. render()
        4. componentDidMount()
        5. componentWillReceiveProps()
        6. shouldComponentUpdate()

        // component kill methods

        7. componentWillUpdate()
        8. componentDidUpdate()
        9. componentWillUnmount()

Recently Added LifeCycle Hooks

Context API, useEffect, useState --- Newly added version by version

Explanation:

# Constructor()

        constructor will execute at booting time of component --constructor will execute only once
        Define state in constructor

# componentWillMount()

        componentWillMount() will execute after constructor
        componentWillMount() will execute only once
        in general we will do the initial modifications in state
        in general we will set global parameters like width, height

# render()

        after componentWillMount() automatically render() function will execute
        render() is mandatory lifecycle hook(main lifecycle hook)
        in general, we will place presentation logic in render()
        when ever change detected in state or props automatically this lifecycle hooks will execute

# componentDidMount()

        after render function immediately componentDidMount() life cycle hook will execute
        in general we will make asynchronous calls in ComponentWillMount()
        this is recommended state to change the state of component

# componentWillReceiveProps()

        when component will receive props from redux

# shouldComponentUpdate()

        if we want to update the state return "true" else "false"

# UNSAFE_componentWillUpdate()

        death method --> perform cleanup operations

# componentDidUpdate()

        if we integrate any third party UI elements
        plugin logic will write here

# componentWillUnmount()

        Before killing the component componentWillUnmount is executed.
        death method --> perform cleanup operations

9. Call() -- if we want to create second memory location will interact with 1st memory location.

Apply – if we want to pass array instead of independent parameter

Bind() - merge memory location 1 and memory location 2 -->merge 2 memory locations-->new memory location.

What is the USE? Call function advanced function APPLY, call and apply advanced version is bind().
Purpose is same. Call, bind, apply –used to access 2 objects in different memory location

10. What is the current ES version? ES6 -2015, ES9, JS24

11. What are different positions in CSS ?
    The position property specifies the type of positioning method used for an element.

There are five different position values:

static: HTML elements are positioned static by default.

relative: An element with position: relative; is positioned relative to its normal position.

fixed: An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled.
The top, right, bottom, and left properties are used to position the element.

absolute: An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).

sticky: An element with position: sticky; is positioned based on the user's scroll position.

12. What is shallow copy and deep copy?

A shallow copy creates a new object with references to the same memory locations as the original object for nested properties.
This means changes to nested objects in the copy will affect the original object.

javascript example:
const originalObject = { a: 1, b: { c: 2 } };
const shallowCopy = { ...originalObject };

shallowCopy.b.c = 3;
console.log(originalObject.b.c); // Output: 3

Deep Copy
A deep copy creates a new object with new memory locations for all nested properties, ensuring changes to the copy don't affect the original object.

JavaScript Example:

javascript
const originalObject = { a: 1, b: { c: 2 } };
const deepCopy = JSON.parse(JSON.stringify(originalObject));

deepCopy.b.c = 3;
console.log(originalObject.b.c); // Output: 2

===
Interview Question and answers

1. Tell me about yourself.

2. Which version of react? v16.8

3. How to optimize performance in react ?

4. Memoization with useMemo and useCallback: Use this hooks to memoize values and, reducing unnecessary recalculations.
5. Optimizing Renders with React.Fragment: Use it to avoid unnecessary wrapper elements that could cause additional DOM nodes.
6. Lazy loading with React.lazy: Use it to load components lazily, reducing the intial bundle size and imporving intial loading performance.
7. Code splitting: Employ code splitting to divide your application into smaller chunks that are loaded on demand, improving initial load times.
8. Optimizing Images and Assets: Compress and optimize images, use responsive images and leverage lazy loading for images to reduce network and rendering overhead.

9. What is difference between Promise.all() and race?

Promise.all() waits for all promises to settle (either resolve or reject), and resolves with an array of all resolved values or rejects as soon as one promise rejects.

Promise.race() resolves or rejects as soon as the first promise settles (either resolves or rejects).

5. difference between useMemo and useCallback?

Key Differences:

    useMemo: Memoizes the result of a computation (value). It helps with performance optimization by avoiding recalculating expensive values.

    useCallback: Memoizes the function itself, ensuring the function reference remains the same between renders unless its dependencies change.
    It's mostly useful when passing functions as props to avoid unnecessary re-renders in child components.

6. Have you used async/await? use?

async: Declares a function that will always return a Promise.

await: Pauses the execution of the async function until the Promise resolves or rejects.

7. What are hooks in react? use?

useState: Manages state in functional components.
useEffect: Manages side effects in functional components.
useContext: Consumes context in functional components.
useReducer: Manage state with a reducer function, For More complex state management.
useRef: Accesses DOM elements or stores mutable values.
useCallback: performance improvement usecase
useMemo: performance improvement usecase.

8. did you work on custom hooks?

Custom Hooks in React are JavaScript functions that allow you to reuse stateful logic across multiple components.
They enable you to extract and share common logic without repeating code, promoting code reusability and separaration concerns.

c1, c2, c3, c4, c5--> one custom hooks --> state
Advantages:
Code Reusability: Custom hooks allow you to reuse stateful logic without duplicating code.
Separation of Concerns: They help spearate the logic from the component's structure, making the code more modular and easier to maintain.
Cleaner Code: By Moving common logic into custom hooks, components become cleaner and more focused on their core responsibilites.

9. Can we useHelp() hook instead of custom hook?

If useHelp() is a custom hook you've created or imported, then yes, you can use it just like any other hook.

Custom hooks don't replace built-in hooks; they are for organizing reusable logic. You can still use built-in hooks inside your custom hooks if needed.

10. what is callback?

Passing "one function" to "another function" as an argument called as "CallBack"

11. what is callback hell?

Callback hell" refers to a situation in programming where multiple asynchronous operations are handled using nested callback functions,
creating a complex and difficult-to-read code structure, often resembling a pyramid shape;
to avoid it, use techniques like Promises and the async/await syntax to manage asynchronous operations in a more linear fashion,
making your code cleaner and easier to maintain.

12. have you worked on NodeJS?

Node.js is commonly used for backend development, APIs, real-time applications (like chat apps), and more.
It leverages non-blocking, event-driven architecture, making it ideal for I/O-heavy tasks like handling HTTP requests, reading files, and querying databases.

I can help with many aspects of Node.js development, including:

    Creating web servers using frameworks like Express.js.

    Working with databases (like MongoDB, MySQL, PostgreSQL) through libraries like mongoose or sequelize.

    Building APIs (RESTful APIs, GraphQL, etc.).

    Managing asynchronous operations (with callbacks, promises, and async/await).

    Implementing middleware for routing and error handling.

    Integrating third-party services (like payment gateways, email services, etc.).

    Optimizing performance (using clustering, worker threads, etc.).

    Deploying Node.js applications (on cloud platforms like AWS, Heroku, etc.).

13. difference between fetch and axios module?

fetch is a built-in JavaScript API that returns a Promise. It is native to the browser and doesn't require installing any additional libraries.

axios is a third-party library that also returns a Promise. It needs to be installed via npm or yarn (e.g., npm install axios).

Fetch Example:

fetch('https://api.example.com/data')
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));

Axios Example:

axios.get('https://api.example.com/data')
.then(response => console.log(response.data))
.catch(error => console.error('Error:', error));

14. call api in react syntax?

axios.get('https://api.example.com/data')
.then(response => console.log(response.data))
.catch(error => console.error('Error:', error));

15. what is hoisting? explain with example?

console.log(a); // Uncaught ReferenceError: a is not defined
let a;

console.log(a); // Uncaught ReferenceError: a is not defined
let a = 10;

Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their respective scopes during the compilation phase, before the code is executed.
This means that regardless of where variables and functions are declared in the code, they are treated as if they are declared at the beginning of their scope.

example:
console.log(x); //output: undefined
var x = 5;
console.log(x); //output: 5

the declaration of x is hoisted to the top, but not its initialization. That's why the first `console.log outputs undefined.

let and const declarations are hoisted but not initialized. This leads to a "temporal dead zone" where accessing the variable before its declaration results in a ReferenceError.

console.log(y);
// throws ReferenceError: Cannot access 'y' before "initialization"
let y = 10;

16. What is promise?

- Promises Establishes the communication between "producer" and "consumer".

       - Promises also called as "special javascript objects".

       - we will create Promises by using "Promise" class constructor.

       - Promises have 3 states

           1) success  (resolve)

           2) error    (reject)

           3) pending

       - we will consume promises by using "then()"

/_
let promise1 = new Promise((resolve,reject)=>{
resolve("tomorrow i will discuss async & await keywords");
});
promise1.then((posRes)=>{
console.log(posRes);
},(errRes)=>{
console.log(errRes);
}); //tomorrow i will discuss async & await keywords
_/

17. What is synchronous and asynchronous calls?

Synchronous calls block the program until the current task finishes. Everything happens in sequence.

Asynchronous calls allow the program to continue executing while waiting for a task to complete, preventing it from freezing or being blocked.

18. What operations did you perform in NodeJS?

    HTTP Server: Set up basic web servers to handle requests and responses.

    REST APIs: Created APIs for handling CRUD operations using Express.

    File Operations: Used the fs module to read, write, and manipulate files.

    Database Integration: Worked with databases (e.g., MongoDB) using libraries like Mongoose.

    Event-driven: Utilized the EventEmitter for event-driven programming.

    Asynchronous Programming: Managed asynchronous operations using Promises and async/await.

    Middleware: Built custom middleware in Express for additional functionality (e.g., logging, authentication).

Node.js offers a robust environment for developing scalable, event-driven applications and handling backend services, APIs, and tasks efficiently.

19. callback hell resolve?

Callback Hell can be mitigated by:

    Modularizing code: Break down tasks into smaller functions.

    Using Promises: Chain asynchronous operations and handle errors in a clean way.

    Using Async/Await: Write asynchronous code that looks synchronous, improving readability.

    Using Libraries like Async.js: Manage complex flows in a more elegant and concise way.

    Using Event Emitters: For managing more complex workflows that involve multiple events.

The async/await approach is generally the most modern and readable method, and it resolves the deep nesting of callbacks effectively, improving code quality and maintainability.

20. What is a closure in JavaScript?

    - if any inner function holding the outer function data, then such scenario called as closure.

21. can we write application in redux instead of redux-saga?

Yes, you can write applications using Redux without using Redux-Saga. Redux itself is a state management library,
while Redux-Saga is a middleware used for handling side effects (like async actions such as fetching data from an API, interacting with external services, etc.).

22. what is difference redux, redux-thunk, redux-saga?

Redux is for managing the state of your application.

Redux-Thunk is a simple middleware for managing simple async logic like API calls or timeouts.

Redux-Saga is a middleware that handles complex side effects using generator functions, making it ideal for handling advanced async logic
(e.g., canceling tasks, running multiple tasks in parallel, and managing retries).

23. explain how redux architecture works? example?

Redux Data Flow

    User Interaction or Events trigger an action.

    The action is sent to the store using the dispatch function.

    The store forwards the action to the appropriate reducer.

    The reducer computes a new state based on the action.

    The store updates the state with the new value.

    The updated state can be accessed by React components or any part of the app.

This process follows the unidirectional data flow in Redux, where actions trigger state updates, and the components re-render based on the updated state.

24. what is react 19 features?

The New Additional Hooks in React 19:-

1. useFormStatus
   -Tracks form submission status dynamically.
   -Eliminates manual state tracking for pending operations.

2. useActionState
   -Combines form actions and states into one seamless hook.

- Perfect for server-side rendered applications.

3. useOptimistic
   -Supports optimistic Ul updates for async operations.

- Makes rollbacks smooth if operations fail.

4. use
   -Brings promises and async context handling directly into components.
   -Enhances Suspense for better async rendering.

5. what is useRef() hook?

The useRef hook is used to access and interact with DOM elements directly and to persist mutable values across renders without causing re-renders.

26. useLayoutEffect? useLayoutEffect fires before the browser repaints the screen. You can measure layout here.

useLayoutEffect: Synchornous Side effects.

27. what is synchronous vs asynchronous call?

Synchronous Call:

    A synchronous call means that the code is executed in a sequential, blocking manner.
    The program executes each statement one after another, waiting for the previous one to finish before moving on to the next.

    In other words, each operation must complete before the next one begins.

Asynchronous Call:

    An asynchronous call allows certain tasks to run in the background while the program continues executing other code.
    It doesn't block the rest of the program, and the operation may complete at a later time.

    Common asynchronous operations include fetching data from an API, setTimeout, Promises, or async/await syntax.

React

performance opt

Javascript

Redux
