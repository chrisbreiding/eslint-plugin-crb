# CRB ESLint Plugin

## Installation

```
npm install --save-dev eslint-plugin-crb
```

Requires ESLint 10+ and Node.js 20.19+.

## Usage

Import one or more of the presets into your `eslint.config.js` depending on the nature of the package:

```js
// eslint.config.js
const crb = require('eslint-plugin-crb')

/** @type {import('eslint').Linter.Config[]} */
module.exports = [
  crb.configs.general,
  {
    files: ['test/**'],
    ...crb.configs.tests,
  },
  {
    files: ['**/*.{jsx,tsx}'],
    ...crb.configs.react,
  },
]
```

## Presets

### general

The majority of the rules concerning JavaScript. Should usually be used at the root of the package.

### tests

Test-specific configuration and rules. Should be used within the `test` directory.

### react

React and JSX-specific configuration and rules.

## Dependencies

Due to a limitation in how ESLint plugins work, your package needs to install the ESLint plugins that this plugin depends on:

If using the `tests` preset:

```bash
npm install --save-dev eslint-plugin-mocha
```

If using the `react` preset:

```bash
npm install --save-dev @babel/eslint-parser eslint-plugin-react
```

## License

This project is licensed under the terms of the [MIT license](/LICENSE.md).
