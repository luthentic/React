<p align="center">
  <img src = "https://media.licdn.com/dms/image/C511BAQF8F2Wry9GTXQ/company-background_10000/0/1584269093982/reactofficial_cover?e=2147483647&v=beta&t=TMIox6sTR3227DIw-2U1I_gk7cqj7xktbb2OkKNfvo4" width=900 height=300>
</p>


## 🚩 Table of Contents

- [Vite](#vite)


--- 

run _npx create-react-app my-app_ it automatically installs the latest version of Create React App.

If you've previously installed create-react-app globally via _npm install -g create-react-app_


## Vite

### What's Vite:
Vite.js is a build tool that is designed to be fast and lightweight. It uses native ES modules and a native development server to provide a fast and seamless development experience. Vite. js also supports code splitting and hot reloading.

### Why Vite:
**The Problems:**

- Before native ES modules were available in browsers, developers used bundling tools (like webpack, Rollup, and Parcel) to concatenate and process source modules into browser-compatible files.
- Bundling allowed modular development but had performance limitations.
- As applications grew more complex, the amount of JavaScript increased significantly.
- Large-scale projects with thousands of modules faced performance bottlenecks.
- Dev servers took too long to start, and even with Hot Module Replacement (HMR), file edits had delays.
- In a bundler-based build setup, the dev server must eagerly crawl and build the entire application before serving it. This process can be time-consuming.

**Vite’s Approach:**

- Native ES modules support in browsers.
- JavaScript tools written in compile-to-native languages.

**Dependencies:**

- Dependencies consist mostly of plain JavaScript code that doesn’t change frequently during development.
- Some large dependencies (like component libraries with many modules) can be resource-intensive to process.
- Dependencies may be shipped in different module formats (e.g., ESM or CommonJS).
  
**Vite’s Approach:**

- Vite addresses these issues by leveraging new advancements in the ecosystem.
- It takes advantage of native ES modules (ESM) in the browser.
- Vite pre-bundles dependencies using esbuild, which is written in Go.
- This pre-bundling process is significantly faster (10-100x) than traditional JavaScript-based bundlers like webpack or Rollup.

### two major parts:

- A dev server that provides rich feature enhancements over native ES modules, for example extremely fast Hot Module Replacement (HMR).
- A build command that bundles your code with Rollup, pre-configured to output highly optimized static assets for production.


