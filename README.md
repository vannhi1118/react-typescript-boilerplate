# react-typescript-boilerplate

A simple boilerplate for my personal react project

1. **Initialize the app**

   `npm init -y`

2. **Install Typescript**

   `npm i --save-dev typescript ts-loader`

3. **Create tsconfig.json**

   `touch tsconfig.json`

   [Full config reference](https://www.typescriptlang.org/tsconfig)

4. **Install basic packages**

   `npm i --save-dev webpack babel-loader @babel/preset-react @babel/core babel-preset-react html-webpack-plugin webpack-dev-server css-loader style-loader @babel/plugin-proposal-class-properties webpack-cli`

- babel: transpile ES6 codes to older versions to make it compatible older browsers
- webpack: bundles all files into 1
- webpack-dev-server: use webpack with a dev server to provide live reloading
- react-dom: “Serves as the entry point to the DOM and server renderers for React”
- mini-css-extract-plugin: extracts styles to a separate file which otherwise remain in index.html

5. **Create webpack.config.js**

- Setting a `NODE_ENV` var is the typical way of setting a dev/prod mode. See later how to set it in your script.
- `HtmlWebpackPlugin` generates index.html from a template which we are going to create shortly
- `MiniCssExtractPlugin` extracts styles to a separate file which otherwise remain in index. html
- `mode` tells webpack if your build is for development or production. In production mode webpack minifies the bundle.
- `entry` is a module to execute first after your app is loaded on a client. That's a bootstrap that will launch your application.
- `output` sets the target dir to put compiled files to
- `module.rules` describes how to load (import) different files to a bundle
  - `test: /\.(ts|tsx)$/` item loads TS files with `ts-loader`
  - `test: /\.css$/` item loads CSS files
- `devtool` sets the config for source maps
- `plugins` contains all plugins with their settings

6.  **Add scripts to package.json**

- `open`: open browser automatically after being compiled
- `config`: start the server with default webpack config file

7. **Install React**

   `npm i react react-dom`

   `npm i --save-dev @types/react @types/react-dom `

- `@types/*` is for packages that support Typescript

8. **Setup ESLint **

- Install packages

  `npm i --save-dev @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-react --dev`

- Create `.eslintrc.js`

9. **Setup Prettier**

- Install packages

  `yarn add prettier eslint-config-prettier eslint-plugin-prettier --dev`

- Create `.prettierrc.js`
- Update `.eslintrc.js` file

  - `'prettier/@typescript-eslint'`: Uses eslint-config-prettier to disable ESLint rules from @typescript-eslint/eslint-plugin that would conflict with prettier
  - `'plugin:prettier/recommended'`: Enables eslint-plugin-prettier and displays prettier errors as ESLint errors. Make sure this is always the last configuration in the extends array.

10. **Create initial files**

- `index.html`
- `index.tsx`
  - The id should be similar to the id of the element in `index.html` file
