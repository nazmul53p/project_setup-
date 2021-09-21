

<!-- PROJECT Title -->
<br />
<p align="center">
  <h3 align="center"><a href="https://github.com/nazmul53p/project_setup-">Project Setup</a></h3>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [How to run](#how-to-run)
- [Editor Setup](#editor-setup)
  - [Plugins](#plugins)
  - [Settings](#settings)
  - [Set Line Breaks](#set-line-breaks)
- [Linting Setup](#linting-setup)
  - [Install Dev Dependencies](#install-dev-dependencies)
  - [Create Linting Configuration file manually](#create-linting-configuration-file-manually)
- [Contact](#contact)

<!-- HOW TO RUN -->

## How to run

Please follow the below instructions to run this project in your computer:

1. Create the project
    ```sh
    npx create-react-app ./ --template typescript
    ```
    
Or

1. Clone this repository
   ```sh
   git clone https://github.com/nazmul53p/project_setup-
   ```
2. Checkout to branch "lesson-3"
   ```sh
   git checkout lesson-3
   ```
3. Run
   ```sh
   yarn
   ```
4. Your app should be available in http://localhost:5500

<!-- Editor Setup -->

## Editor Setup

You can use any editor but as I personally prefer VS Code. I will give some instructions about how I prefer VS code to be setup for React applications with Typescript.

### Plugins

You need to install the below plugins:

- ESLint by Dirk Baeumer
- Prettier - Code formatter by Prettier
- Dracula Official Theme (optional)

### Settings

Follow the below settings for VS Code -

1. Create a new folder called ".vscode" inside the project root folder
2. Create a new file called "settings.json" inside that folder.
3. Paste the below json in the newly created settings.json file and save the file.

```json
{
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "[javascript]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "[javascriptreact]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "[typescript]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "[typescriptreact]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "javascript.validate.enable": false, //disable all built-in syntax checking
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true,
        "source.fixAll.tslint": true,
        "source.organizeImports": true
    },
    "eslint.alwaysShowStatus": true,
    // emmet
    "emmet.triggerExpansionOnTab": true,
    "emmet.includeLanguages": {
        "typescript": "typescriptreact",
    }
}
```

If you followed all previous steps, the theme should change and your editor should be ready.

### Set Line Breaks

Make sure in your VS Code Editor, "LF" is selected as line feed instead of CRLF (Carriage return and line feed). To do that, just click LF/CRLF in bottom right corner of editor, click it and change it to "LF". If you dont do that, you will get errors in my setup.

<img src="public/line-feed.jpg" alt="Line Feed" width="700">

## Linting Setup

In order to lint and format your React project automatically according to popular airbnb style guide, I recommend you to follow the instructions below.

### Install Dev Dependencies

```sh
yarn add -D eslint-plugin-import eslint-plugin-jest eslint-plugin-json eslint-plugin-react @typescript-eslint/eslint-plugin prettier prettier-eslint eslint-config-prettier eslint-plugin-prettier@3.4.0
```

or You can also add a new script in the scripts section like below to install everything with a single command:

```json
    "lint": "yarn add -D eslint-plugin-import eslint-plugin-jest eslint-plugin-json eslint-plugin-react @typescript-eslint/eslint-plugin prettier prettier-eslint eslint-config-prettier eslint-plugin-prettier@3.4.0"
```

and then simply run the below command in the terminal -

```sh
yarn lint #or 'npm run lint'
```

### Create Linting Configuration file manually

Create a `.eslintrc.js` file in the project root and enter the below contents:

```js
module.exports = {
  root: true,
  extends: [
    "eslint:recommended",
    "plugin:prettier/recommended",
    "plugin:react/recommended", // Uses the recommended rules from @eslint-plugin-react
    "plugin:@typescript-eslint/eslint-recommended", // Uses the recommended rules from the @typescript-eslint/eslint-plugin
    "plugin:@typescript-eslint/recommended", // Uses the recommended rules from the @typescript-eslint/eslint-plugin
  ],
  parser: "@typescript-eslint/parser", // Specifies the ESLint parser
  env: {
    browser: true,
    es6: true,
    jest: true,
    node: true,
  },
  parserOptions: {
    ecmaVersion: 2020, // Allows for the parsing of modern ECMAScript features
    sourceType: "module", // Allows for the use of imports
    ecmaFeatures: {
      jsx: true, // Allows for the parsing of JSX
      arrowFunctions: true,
    },
  },
  plugins: ["react", "@typescript-eslint", "prettier"],
  settings: {
    react: {
      version: "detect", // Tells eslint-plugin-react to automatically detect the version of React to use
    },
    "import/resolver": {
      node: {
        extensions: [".js", ".jsx", ".ts", ".tsx"],
        paths: ["./src"],
      },
    },
  },
  rules: {
    // Existing rules
    "comma-dangle": "off", // https://eslint.org/docs/rules/comma-dangle
    "function-paren-newline": "off", // https://eslint.org/docs/rules/function-paren-newline
    "global-require": "off", // https://eslint.org/docs/rules/global-require
    "import/no-dynamic-require": "off", // https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-dynamic-require.md
    "no-inner-declarations": "off", // https://eslint.org/docs/rules/no-inner-declarations
    // New rules
    "class-methods-use-this": "off",
    "import/extensions": "off",
    "import/prefer-default-export": "off",
    "@typescript-eslint/explicit-function-return-type": "off",
    "@typescript-eslint/no-var-requires": "off",
  },
};
```

Create a `.prettierrc` file in the project root and enter the below contents:

```
{
    "semi": true,
    "printWidth": 140,
    "tabWidth": 2,
    "singleQuote": true,
    "bracketSpacing": true,
    "jsxBracketSameLine": false,
    "useTabs": false,
    "arrowParens": "avoid",
    "jsxSingleQuote": true,
    "trailingComma": "all"
}

```

Create a `.prettierignore` file in the project root and enter the below contents:

```
**/node_modules
**/dist
**/package.json
**/yarn.lock
**/package-lock.json
**/.eslintrc.js
**/tsconfig.json
```
<!-- CONTACT -->

## Contact

Nazmul Haque - [nazmul2018s@gmail.com](mailto:nazmul2018s@gmail.com)

Project Link: [https://github.com/nazmul53p/project_setup-](https://github.com/nazmul53p/project_setup-)
