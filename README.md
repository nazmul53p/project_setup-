

<!-- PROJECT Title -->
<br />
<p align="center">
  <h3 align="center"><a href="https://github.com/nazmul53p/project_setup-">Project Setup (React with Typescript)</a></h3>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [How to create project](#how-to-create-project)
- [Editor Setup](#editor-setup)
  - [Plugins](#plugins)
  - [Settings](#settings)
  - [Set Line Breaks](#set-line-breaks)
- [Linting Setup](#linting-setup)
  - [Install Dev Dependencies](#install-dev-dependencies)
  - [Create Linting Configuration file manually](#create-linting-configuration-file-manually)
- [Contact](#contact)

<!-- HOW TO RUN -->

## How to create project (React with Typescript)

Please follow the below instructions to run this project in your computer:

1. Create the project
    ```sh
    npx create-react-app ./ --template typescript
    ```
<!-- Editor Setup -->

## Editor Setup

You can use any editor but as I personally prefer VS Code. I will give some instructions about how I prefer VS code to be setup for React applications with Typescript.

### Plugins

You need to install the below plugins:
- ESLint by Dirk Baeumer
- Prettier - Code formatter by Prettier

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

## Linting Setup

In order to lint and format your React project automatically according to popular airbnb style guide, I recommend you to follow the instructions below.

### Install Dev Dependencies
```
https://www.npmjs.com/package/eslint-config-airbnb-typescript-prettier

yarn add -D eslint-config-airbnb-typescript-prettier eslint-config-prettier eslint-plugin-prettier prettier prettier-eslint
```
or
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

Create a `.eslintrc.json` file in the project root and enter the below contents:

```json
{
    "extends": [
        "airbnb-typescript-prettier"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
      "ecmaVersion": 8
    },
    "env": {
      "browser": true,
      "node": true,
      "es6": true,
      "jest": true
    },
    "rules": {
      "@typescript-eslint/explicit-module-boundary-types": "off",
      "react/react-in-jsx-scope": 0,
      "react-hooks/rules-of-hooks": "error",
      "no-console": 0,
      "react/state-in-constructor": 0,
      "indent": 0,
      "linebreak-style": 0,
      "react/prop-types": 0,
      "jsx-a11y/click-events-have-key-events": 0,
      "react/jsx-filename-extension": [
        1,
        {
          "extensions": [".js", ".jsx", ".ts", ".tsx"]
        }
      ],
      "prettier/prettier": [
        "error",
        {
          "trailingComma": "es5",
          "singleQuote": true,
          "printWidth": 100,
          "tabWidth": 4,
          "semi": true,
          "endOfLine": "auto"
        }
      ]
    },
    "settings": {
      "import/resolver": {
        "node": {
          "paths": ["src"],
          "extensions": [".js", ".jsx", ".ts", ".tsx"]
        }
      }
    },

    "plugins": ["react", "react-hooks", "@typescript-eslint", "prettier"]
  }
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
