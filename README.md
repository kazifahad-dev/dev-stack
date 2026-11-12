<h1 align="center">🧱 Dev Stack</h1>
<p align="center"><b>Build Your Ideal Development Stack</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/React_18-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" />
  <img src="https://img.shields.io/badge/Tailwind_CSS_v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
</p>

<p align="center">
  <a href="https://dev-stack-five-silk.vercel.app/"><b>🌐 Live Demo</b></a>
</p>

**Dev Stack** is a responsive **React + TypeScript** web app that helps developers explore frontend, backend, database, and tooling technologies, compare them side by side, and assemble a personal "stack" for their next project, all in a clean, gradient-themed UI built from a Figma design.

## 📸 Screenshot

![Dev Stack Screenshot](./screenshot.png)

## 🔗 Links

- 🌐 **Live Demo:** [https://dev-stack-five-silk.vercel.app/](https://dev-stack-five-silk.vercel.app/)
- 💻 **Source Code:** [github.com/kazifahad-dev/YOUR_REPO_NAME](https://github.com/kazifahad-dev/YOUR_REPO_NAME)

## 🛠️ Technologies Used

| Technology | Purpose |
| --- | --- |
| **React 18 + TypeScript** | Component-based UI with static typing |
| **Vite** | Fast dev server and build tool |
| **Tailwind CSS v4** | Utility-first styling |
| **react-toastify** | Toast notifications for stack actions |
| **JSON** | Local data source for the technology catalog, loaded via `fetch()` |

### 💡 Why These Technologies?

- **React 18**: The UI is built from reusable pieces (cards, navbar, sidebar), and React's state keeps the cards and the "Your Stack" sidebar in sync automatically.
- **TypeScript**: Static typing for the technology data and component props catches mistakes early and makes the code easier to maintain.
- **Vite**: Instant startup and fast hot reload during development, with a lightweight production build.
- **Tailwind CSS v4**: Makes it quick to turn the Figma design into a consistent, responsive layout directly in the markup.
- **react-toastify**: Gives clear, non-blocking feedback (such as the duplicate warning) with very little code.
- **JSON + `fetch()`**: Keeps the catalog separate from the UI, so technologies can be added or edited without touching any component.

## ✨ Features

1. **Build-your-own stack**: Browse 15 curated technologies as cards (icon, category, rating, difficulty, badge) and click **Add to Stack** to collect the ones you want. Duplicate additions are blocked with a warning toast, and an added card gets a pink border/button and its button flips to **✓ Added to Stack**.
2. **Live "Your Stack" sidebar**: A sticky panel that shows the running count of selected technologies, lets you remove any single item, or clear everything at once with **Remove All**, with an empty-state message when nothing is selected yet.
3. **Polished, theme-able UI**: A single shared gradient (orange → pink → violet), defined once as CSS variables in `src/index.css`, powers the logo, hero headline and primary buttons, so the whole app can be re-themed by editing three color values. The layout is fully responsive (1 column on mobile, 2 on tablet, 3 on desktop) with a sticky, mobile-friendly navbar.

## 📦 Dependencies

- `react` and `react-dom` (v18)
- `typescript`
- `vite`
- `tailwindcss` (v4)
- `react-toastify`

> The exact versions are listed in [`package.json`](./package.json).

## 🚀 Getting Started

**Prerequisites:** [Node.js](https://nodejs.org/) (v18 or later) and npm.

```bash
# 1. Clone the repository
git clone https://github.com/kazifahad-dev/YOUR_REPO_NAME.git

# 2. Go to the project folder
cd YOUR_REPO_NAME

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev
```

Open the local URL shown in your terminal (usually `http://localhost:5173`).

To create a production build:

```bash
npm run build
npm run preview
```

## 🧗 Challenges I Faced

- **Keeping the cards and the sidebar in sync**: Both depend on the same list of selected technologies, so the list lives in one place in the parent component and is passed down with props and callbacks.
- **Preventing duplicate entries**: The stack is checked before adding, and a warning toast is shown instead of adding the same technology twice.
- **Loading the catalog from JSON**: The data is fetched once when the app loads using `useEffect` and `fetch()`.
- **One theme in many places**: The gradient is defined once as CSS variables, so the logo, headline and buttons always match and re-theming is simple.
- **Responsive layout**: A card grid, a sticky sidebar and a sticky navbar had to work on every screen size (1, 2 and 3 columns across breakpoints).

## 🎯 Problems This Project Solves

- **Choice overload**: A curated set of technologies in one place, with rating, difficulty and category visible at a glance.
- **Planning a stack**: Build and adjust a personal stack visually by adding, removing or clearing items instantly.
- **Quick comparison**: Cards with the same structure make it easy to compare technologies side by side.

## 🧠 React Concepts Used

**1. What is JSX, and why is it used in React?**
JSX (JavaScript XML) is a syntax extension for JavaScript that lets you write HTML-like code directly inside your JavaScript files. It keeps the UI structure and the logic together in one component and makes the code easier to read.

**2. What is the difference between props and state?**
Props are passed into a component from the outside by its parent and are read-only. State is data managed inside the component itself and can change over time.

**3. What does the `useState` hook do, and where did you use it in this project?**
`useState` is a built-in React function that lets you add state variables to functional components. In this project it stores the list of technologies the user has added to their stack.

**4. What does the `useEffect` hook do, and why did you need it to load the JSON data?**
`useEffect` lets you synchronize a component with external systems or perform "side effects", such as fetching data, modifying the DOM manually, setting up timers or subscribing to external services, after the component renders. Here it fetches the technology catalog from the JSON file once when the app loads.

**5. Why does every item in a `.map()` list need a unique `key` prop?**
React needs a unique `key` for each item in a mapped list so its reconciliation algorithm (the Virtual DOM) can track which items have changed, been added or been removed between renders.

**6. What is conditional rendering? Show one place you used it.**
Conditional rendering means rendering different UI elements or components based on specific conditions or state, just like `if` statements or ternary operators in standard JavaScript. In this project, the "Your Stack" sidebar shows an empty-state message when nothing has been selected yet, and the list of technologies once something is added.

**7. How do you pass data from a parent component to a child component, and how does a child send something back to the parent?**
A parent passes data to a child through props. The child sends data back by calling a callback function that the parent passes down as a prop, for example when a card's **Add to Stack** button is clicked.

---

<p align="center">Built with ❤️ by <a href="https://github.com/kazifahad-dev">Kazi Fahad</a></p>
