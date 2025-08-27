
React is a n Algorithm and React-DOM is a Support system for the React and React's Algo modify the UI in which React-DOM helps to do that.
ReactDOM (for web) and React Native (for mobile) are the **platform-specific renderers** that take the React "tree" and update the actual environment (browser DOM, native UI, etc.).

- Components=> Reusable and Independent Bits of code that returns HTML it server the same purpose of JS Functions, but work in isolation.
- HTML, CSS & JS ~ JSX {JS+XML} => But browser doesn't understand the shit in JSX so it needs a Transpilier (Babel) which converts JSX (XML-in-JS) into plain JavaScript.
- Babel is inspired from template literals of JS to write more ease usage of variables inside the XML or anywhere we used to write in React APPS.

### **Doubt/Confusion-Resolved*:**
- the order of elements even of the same type of components are repeated the React Consider it as the different element.
- But the List of Items used and transformed into the elements, means the List can be changed/modified so **React can't Trust on the current items in list** so having unique id for every element using/mentioning items of array like using map() in return part will makes React clarity of each Item is unique.
- npm -> used to bought the pacakages into the project. npx ->executing the npm modules/pacakages.
- Difference between the package.json and package-lock-.json
	1) **package.json**: Think of it as the **manifest / blueprint** of your project.
	- Created when you run `npm init` or a React starter like `create-vite`.
	- It contains:
	    - **Project metadata** → name, version, description.
	    - **Scripts** → commands like `npm start`, `npm run build`.
	    - **Dependencies** → libraries your project needs (e.g., React, Lodash).
	    - **DevDependencies** → tools needed only for development (e.g., ESLint, Babel).
		👉 It’s **human-readable** and tells _what your project needs_, not the full detail of _how it’s installed_.
	- Notice `"react": "^18.3.1"` → the **caret (^)** means it allows compatible versions (`>=18.3.1 <19.0.0`).
	1) **package-lock.json**: This is the **snapshot / lockfile** generated automatically when you run `npm install`.
		- It records the **exact versions** of every installed package, including nested ones.
		- Ensures **consistent installs across machines** (your machine vs your friend’s vs production).
		- Without it → you may both have slightly different versions (because of semver `^` / `~` rules).
		- With it → same versions everywhere, no “works on my machine” problem.
		👉 It’s **machine-generated**, not meant for manual edits.  
- 
### Important Points
- When we control the UI Elements like input using the state in the component is called Controlled Component.
- Bundlers solved **DX (Developer Experience)** + **Browser compatibility** + **Performance**.
- **DX**:
	1) - Hot Module Replacement (HMR) → Live reload when coding.
	2) Polyfills for old browsers.
	3) Handling non-JS assets (images, CSS, fonts). 
- **Performance**:
	1) By bundling the Long CSS, JS & assests Files easily in single bundle which avoids too many Network calls. 
- CRA uses webpack as Bundler to bundle the code's of all files into single file of javascript.
- This process ensure broad Browser Compatibility. But, downfalls the performance during the development{This issue spotlight when development of the application grows larger}.
- Reasons: Debugging Complexity, Mostly relied on Polyfills for browser Compatibility.
- Vite uses esbuild + native ESM during dev = startup in <1s, HMR almost instant.
- Config Hell: CRA hides Webpack config. To customize, devs had to `eject` (messy, irreversible).  
Vite gives **simple plugin system** and easy config.
- ```shell

```