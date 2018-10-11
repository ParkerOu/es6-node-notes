# Start project
```sh
npm init -y
```
- **-y** skip the interactive questions

# Install webpack (on current project)
```sh
npm i webpack webpack-cli --save-dev
```
- **i** It's **install** alias
- **--save-dev** save the package for development purpose. This would also create a new value in your package.json
- [**webpack**](https://www.npmjs.com/package/webpack) is the actual JS library that contains webpack bundling functionality
- [**webpack-cli**](https://www.npmjs.com/package/webpack-cli) is the Command Line Interface that communicates to the Webpack Compiler/Bundler)

# Basic Setup
### 1. Create src directory & create index.js
```
  webpack-demo
  |- package-lock.json
  |- package.json
+ |- /src
+   |- index.js
```
```js
console.log('hello js')
```
### 2. Setup package.json
- remove "test" and add "start", "build"
```
  ...
  "devDependencies": {},
  "scripts": {
+    "start": "webpack --mode development",
+    "build": "webpack --mode production"
  },
  ...
```
### 3. Testing 
```sh
npm run dev
``` 
- new folder **dist** appear
- dist means **distribution**
```
webpack-demo
+ |- /dist
+   |- main.js
```
See content in main.js, and you'll find a lot of stuff here.
- **Development mode** is optimized for speed and does nothing more than providing an un-minified bundle.
#### Try production mode
```sh
npm run build
```
Now it's a minified bundle.
- **Production mode** enables all sorts of optimizations out of the box. Including minification, scope hoisting, tree-shaking and more.