# Install Babel
```sh
npm install @babel/core babel-loader @babel/preset-env --save-dev
```
- [**@babel/core**](https://www.npmjs.com/package/@babel/core) Babel compiler core.
- [**babel-loader**](https://www.npmjs.com/package/babel-loader) allows transpiling JavaScript files using Babel and webpack.
- [**@babel/preset-env**](https://www.npmjs.com/package/@babel/preset-env) preset for each environment.

# Setup Babel
### In the root of your project folder, create a .babelrc file.
```
  webpack-demo
  ...
  |- package.json
+ |- .babelrc
```
## Setup .babelrc
```
{
  "presets": ["@babel/preset-env"]
}
```
## Setup webpack.config.js
#### Add module
```js
module.exports = {
  ...
  devServer: {
    port: 3000,
    contentBase: path.resolve(__dirname, 'dist')
  },
+ module: {
+   rules: [
+     {
+       test: /\.js$/,
+       exclude: /node_modules/,
+       use: {
+         loader: "babel-loader"
+       }
+     }
+   ]
+ }
};
```
- For every file with a .js extension Webpack pipes the code through babel-loader for transforming ES6 down to ES5.
## Test
```sh
npm run server
```
- If the setting correct, we won't see error messages.