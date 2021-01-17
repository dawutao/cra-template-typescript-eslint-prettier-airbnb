# TypeScript-ESLint-Prettier-Airbnb Create React App Template

This project is forked from the official TypeScript template for [Create React App](https://github.com/facebook/create-react-app). It includes a basic setup with Prettier and [eslint-config-airbnb-typescript](https://www.npmjs.com/package/eslint-config-airbnb-typescript).

To use this template simply run:

```shell
npx create-react-app my-app --template typescript-eslint-prettier-airbnb
```

## Features

### ESLint with Airbnb Configuration

This template extends Create React App's ESLint configuration by adding Airbnb TypeScript style rules.

### Prettier

Prettier is setup along with ESLint to work seamlessly.

### VS Code Format on Save

The template contains a `.vscode/setting.json` file that enables format on save by fixing any ESLint (and Prettier) errors automatically.

**Note:** As with the original Create React App TypeScript template, VS Code might not detect your project's TypeScript version, which may show errors in the IDE. To allow VS Code to detect the workspace TypeScript version open any TS file, then on the lower right-hand corner of VS Code click on the TypeScript version number (e.g. 4.1.2) and click on `Select TypeScript version --> Use Workspace Version`.

### Lint Script

Added to `package.json` there is a lint script that type-checks your code with TypeScript and then automatically fixes ESLint errors.

```bash
npm run lint
```

It simply runs `tsc --noEmit && eslint --ext .js,.jsx,.ts,.tsx src --fix` under the hood.

### Default .eslintrc.js

This project comes with a default `.eslintrc.js` enforcing Prettier and Airbnb's TypeScript rules with minimal setup so you can extend it with your own rules and plugins.

```js
// .eslintrc.js

module.exports = {
    root: true,
    parser: '@typescript-eslint/parser',
    plugins: ['react', '@typescript-eslint', 'prettier'],
    extends: [
        'airbnb-typescript',
        'airbnb/hooks',
        'eslint:recommended',
        'plugin:react/recommended',
        'plugin:@typescript-eslint/recommended',
        'prettier',
        'prettier/react',
        'prettier/@typescript-eslint',
    ],
    env: {
        browser: true,
        jasmine: true,
        jest: true,
        node: true,
    },
    // Airbnb's ESLint config requires this
    parserOptions: {
        project: './tsconfig.json',
    },
    // Your own custom rules, for example:
    rules: {
        // Include .prettierrc.js rules
        'prettier/prettier': ['error', {}, { usePrettierrc: true }],
        // We will use TypeScript's types for component props instead
        'react/prop-types': 'off',
        // We don't want unused vars
        '@typescript-eslint/no-unused-vars': ['error'],
    },
};
```
