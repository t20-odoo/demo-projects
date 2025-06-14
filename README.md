# Complete React, Next.js & TypeScript Projects Course 2025

_Hands-on React: 25+ Projects Featuring Next.js, TypeScript, Prisma, Zod, Shadcn, Axios, Router 6, Query 5, Redux Toolkit_

## Section 1: Introduction

#### 1. Main Course Repository

<https://github.com/john-smilga/react-course-v3>

#### 2. What is React?

<https://react.dev/>

_React:_ The library for web and native user interfaces

#### 3. Goals

_Theory_: Understand the main buidling blocks and know where to find useful info

_Practice_: Apply the knowledge by building bunch of cool projects

#### 4. Structure

- Tutorial
  - Get familiar with all of the major building blocks
- Projects
  - After each new topic, build one or few cool projects
- Redux
  - Learn the most popular state management library

#### 5. Requirements

- _HTML & CSS_: Familiar with common elements - div, section, navbar. Understand primary styling principles
- _JavaScript_: Arrow functions, array methods, spread operator, rest operator, destructuring etc.
- _Youtube channel_: Coding Addict
- _Playlist_: JacaScript Nuggets

#### 6. Discord Channel

Join the Discord Channel - <https://discord.com/invite/GhUxjr66xz>

---

## Section 2: Dev Environment

#### 11. VS Code

Visual Studio Code - <https://code.visualstudio.com/>

vs-code-setup-2022 - <https://github.com/t20-odoo/vs-code-setup-2022>

#### 13. Node.js

Node.js - <https://nodejs.org/en>

_Node.js® is a free, open-source, cross-platform JavaScript runtime environment that lets developers create servers, web apps, command line tools and scripts._

`node --version`

_NPM_: Node Package Manager

`npm install packageName`

#### 14. Create-React-App

Create React App - <https://create-react-app.dev/>

`npx create-react-app my-app` or `npx create-react-app@latest my-app`

`npm start` - Starts the development server.

`npm run build`- Bundles the app into static files for production.

---

## Section 3: React Fundamentals

#### 15. Intro

<https://github.com/t20-odoo/react-course-v3/blob/main/01-fundamentals/README.md>

#### 16. Github Repository

<https://github.com/john-smilga/react-course-v3>

#### 17. Folder Structure

_node_modules_: Contains all dependencies required by the app. Main dependencies also listed in package.json

_public_: Contains static assets including index.html (page template)

- index.html
  - title
  - fonts
  - css
  - favicon
  - id="root" - our entire app

_src_: In simplest form it's the brain of our app. This is where we will do all of our work. src/index.js is the JavaScript entry point.

_.gitignore_: Specifies which files source control (Git) should ignore

_package.json_: Every Node.js project has a package.json and it contains info about our project, for example list of dependencies and scripts

_package-lock.json_: A snapshot of the entire dependency tree

_README.md_: The markdown file where you can share more info about the project for example build instructions and summary

#### 18. Remove Boilerplate

- remove src folder
- create src folder
  - create index.js inside src

#### 19. First Component

```js
function Greeting() {
  return <h2>My First Component</h2>;
}

// arrow function also works

const Greeting = () => {
  return <h2>My First Component</h2>;
};
```

- starts with capital letter
- must return JSX (html)
- always close tag

#### 20. Extensions and Settings

- Auto Rename Tag
- Highlight Matching Tag
  - customize in settings.json
- Prettier
  - format on save
  - format on paste
  - Default Formatter (Prettier - Code formatter)

settings.json

```json
  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "prettier.singleQuote": true,
  "prettier.semi": false,
```

- Emmet

settings.json

```json
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
```

- ES7 Snippets
  - rafce (arrow func with export)
  - rfce (regular func with export )
  - same as the file name
  - react auto import
    - uncheck
    - React Snippets › Settings: Import React On Top

#### 21. Create Element Function

- capital letter
- must return something
- JSX syntax (return html)
  - to make our lives easier
  - calling function under the hood

```js
const Greeting = () => {
  return React.createElement("h2", {}, "hello world");
};
```

#### 22. JSX Rules

- return single element (one parent element)
  - semantics section/article
  - Fragment - let's us group elements without adding extra nodes

```js
return <React.Fragment>...rest of the return</React.Fragment>;

// shorthand

return <>...rest of the return</>;
```

- camelCase property naming convention

```js
return (
  <div tabIndex={1}>
    <button onClick={myFunction}>click me</button>
    <label htmlFor='name'>Name</label>
    <input readOnly={true} id='name' />
  </div>
)
// in html
<div tabindex="1">
    <button onclick="myFunction()">click me</button>
    <label for='name'>Name</label>
    <input readonly id='name' />
</div>
```

- className instead of class

```js
return <div className="someValue">hello</div>;
```

- close every element

```js
return <img />;
// or
return <input />;
```

- formatting
  - opening tag in the same line as return or ()

```js
function Greeting() {
  return (
    <>
      <div className="someValue">
        <h3>hello people</h3>
        <ul>
          <li>
            <a href="#">hello world</a>
          </li>
        </ul>
      </div>
      <h2>hello world</h2>
      <input type="text" name="" id="" />
    </>
  );
}
```

#### 23. Nest Components

```js
function Greeting() {
  return (
    <div>
      <Person />
      <Message />
    </div>
  );
}

const Person = () => <h2>john doe</h2>;
const Message = () => {
  return <p>this is my message</p>;
};
```

#### 24. React Developer Tools

<https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi>

#### 25. BookList

#### 26. CSS

- create index.css in src

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  background: #f1f5f8;
  color: #222;
}
```

- import file and add classes

```css
import './index.css';
```

#### 27. Local Images (public folder)

#### 28. JSX - CSS

- style prop
- {} in JSX means going back to JS Land
- value is an object with key/value pairs - capitalized and with ''

```js
const Author = () => (
  <h4 style={{ color: "#617d98", fontSize: "0.75rem", marginTop: "0.5rem" }}>
    Jordan Moore
  </h4>
);
```

#### 29. JSX - Javascript

#### 30. Props - Basic Setup

#### 31. Props - Somewhat Dynamic Setup

#### 32. Props - Multiple Approaches

#### 33. Children Prop

#### 34. Simple List

#### 35. Proper List

#### 36. Key Prop

#### 37. Object as a Prop

#### 38. Event Basics

#### 39. Form Submission

#### 40. Form Submission - Button Example

#### 41. Anonymous Function (arrow)

#### 42. Components Feature

#### 43. Prop Drilling

#### 44. Complex Example - Intro

#### 45. Complex Example - Bug

#### 46. Complex Example - Fix

#### 47. ES6 Modules

#### 48. Local Images (src folder)

#### 49. Numbers Challenge

#### 50. Title Challenge

#### 51. Build Folder

#### 52. Deployment

<https://www.netlify.com/>

---

## Section 4: Backroads Application

?????

---

## Section 5: VITE

#### 74. VITE - Intro

_Vite_ - <https://vite.dev/>: (French word for "quick", pronounced /vit/, like "veet") is a build tool that aims to provide a faster and leaner development experience for modern web projects.

#### 75. VITE - Install / Setup

- need to use .jsx extension
- index.html in the source instead of public
- assets still in public
- instead of index.js, need to use main.jsx
- to spin up dev server - `npm run dev`
- rest the same - imports/exports, deployment, assets, etc...

`npm create vite@latest` or `npm create vite@latest my-react-app -- --template react`

---

## Section 6: React Hooks and Advanced Topics

?????
