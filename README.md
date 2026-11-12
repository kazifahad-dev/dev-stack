# 🧱 Dev Stack — Build Your Ideal Development Stack

🌐 **Live Demo:** https://dev-stack-five-silk.vercel.app/

Dev Stack is a responsive React + TypeScript web app that helps developers explore frontend, backend, database, and tooling technologies, compare them side by side, and assemble a personal "stack" for their next project, all in a clean, gradient-themed UI built from a Figma design.

## 📸 Screenshot

![Dev Stack Screenshot](./public/Screenshot%202026-11-12%20175835.png)
![Dev Stack Screenshot](./public/Screenshot%202026-11-12%20175847.png)

## 🛠️ Technologies Used

1. **React 18 + TypeScript** — component-based UI with static typing
2. **Vite** — fast dev server and build tool
3. **Tailwind CSS v4** — utility-first styling
4. **react-toastify** — toast notifications for stack actions
5. **JSON** — local data source for the technology catalog, loaded via `fetch()`

### Why These Technologies?

- **React 18:** Reusable components keep the cards and the "Your Stack" sidebar in sync through state.
- **TypeScript:** Static typing catches mistakes early and makes the code easier to maintain.
- **Vite:** Very fast startup and hot reload during development.
- **Tailwind CSS v4:** Quickly turns the Figma design into a consistent, responsive layout.
- **react-toastify:** Clear, non-blocking feedback (like the duplicate warning) with very little code.
- **JSON + fetch():** Keeps the catalog separate from the UI, so technologies can be added without changing any component.

## ✨ Features

1. **Build-your-own stack:** Browse 15 curated technologies as cards (icon, category, rating, difficulty, badge) and click **Add to Stack** to collect the ones you want. Duplicate additions are blocked with a warning toast, and an added card gets a pink border/button and its button flips to **✓ Added to Stack**.
2. **Live "Your Stack" sidebar:** A sticky panel that shows the running count of selected technologies, lets you remove any single item, or clear everything at once with **Remove All**, with an empty-state message when nothing is selected yet.
3. **Polished, theme-able UI:** A single shared gradient (orange → pink → violet), defined once as CSS variables in `src/index.css`, powers the logo, hero headline and primary buttons, so the whole app can be re-themed by editing three color values. The layout is fully responsive (1 column on mobile, 2 on tablet, 3 on desktop) with a sticky, mobile-friendly navbar.

## 📦 Dependencies

- react and react-dom (v18)
- typescript
- vite
- tailwindcss (v4)
- react-toastify

## 🚀 How to Run Locally

1. Clone the repository:
   `git clone https://github.com/kazifahad-dev/dev-stack`
2. Go to the project folder:
   `cd YOUR_REPO_NAME`
3. Install dependencies:
   `npm install`
4. Start the development server:
   `npm run dev`
5. Open the local URL shown in the terminal (usually `http://localhost:5173`).

## 🧗 Challenges I Faced

- **Keeping the cards and the sidebar in sync:** Both depend on the same list of selected technologies, so the list lives in the parent component and is passed down with props and callbacks.
- **Preventing duplicate entries:** The stack is checked before adding, and a warning toast is shown instead of adding the same technology twice.
- **Loading the catalog from JSON:** The data is fetched once when the app loads using `useEffect` and `fetch()`.
- **One theme in many places:** The gradient is defined once as CSS variables, so the logo, headline and buttons always match.
- **Responsive layout:** A card grid, a sticky sidebar and a sticky navbar had to work on every screen size.

## 🎯 Problems This Project Solves

- **Choice overload:** A curated set of technologies in one place, with rating, difficulty and category visible at a glance.
- **Planning a stack:** Build and adjust a personal stack instantly by adding, removing or clearing items.
- **Quick comparison:** Cards with the same structure make it easy to compare technologies side by side.

## 🧠 React Questions & Answers

**1. What is JSX, and why is it used in React?**
JSX (JavaScript XML) is a syntax extension for JavaScript that lets you write HTML-like code directly inside your JavaScript files. It keeps the UI structure and logic together and makes the code easier to read.

**2. What is the difference between props and state?**
Props are passed into a component from the outside by its parent and are read-only. State is data managed inside the component itself and can change over time.

**3. What does the useState hook do, and where did you use it in this project?**
useState is a built-in React function that lets you add state variables to functional components. In this project it stores the list of technologies the user has added to their stack.

**4. What does the useEffect hook do, and why did you need it to load the JSON data?**
useEffect lets you synchronize a component with external systems or perform "side effects", such as fetching data, modifying the DOM manually, setting up timers or subscribing to external services, after the component renders. Here it fetches the technology catalog from the JSON file once when the app loads.

**5. Why does every item in a .map() list need a unique key prop?**
React needs a unique key for each item in a mapped list so its reconciliation algorithm (the Virtual DOM) can track which items have changed, been added or been removed between renders.

**6. What is conditional rendering? Show one place you used it.**
Conditional rendering means rendering different UI elements or components based on specific conditions or state, just like if statements or ternary operators in standard JavaScript. In this project, the "Your Stack" sidebar shows an empty-state message when nothing has been selected yet, and the list of technologies once something is added.

**7. How do you pass data from a parent component to a child component, and how does a child send something back to the parent?**
A parent passes data to a child through props. The child sends data back by calling a callback function that the parent passes down as a prop, for example when a card's **Add to Stack** button is clicked.