# eslint-config-volvocars
A shared eslint-prettier config package


[![NPM](https://img.shields.io/npm/v/eslint-config-volvocars)](https://www.npmjs.com/package/eslint-config-volvocars) ![npm downloads](https://img.shields.io/npm/dt/eslint-config-volvocars) ![license](https://img.shields.io/npm/l/eslint-config-volvocars)


## Dev Setup

### Install package + peer dependencies:

```
npx install-peerdeps --dev eslint-config-volvocars
```

### Configure eslint

 create `.eslintrc` file with the following:

```json
{
  "extends": ["volvocars"]
}
```

**NOTE:** your project must include `.tsconfig.json` file. If it doesn't, you can easily initialize it by running:

```
yarn tsc --init
```

## To Override Default Config

Add your custom ESLint or Prettier rules directly in `.eslintrc` file under `"rules"` (for ESLint) or `"prettier/prettier"` (for Prettier):

```json
{
  "extends": ["volvocars"],
  "rules": {
    "@typescript-eslint/ban-ts-comment": "off",
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5"
      }
    ]
  }
}
```

### add .prettierrc file with the following:
**NOTE:** Goal here is to create an NPM package so prettier config is added directly into the eslint config without making a separate
 `.prettierrc` file. But this might cause an issue with text editor extensions (ex. prettier-vscode) as they read directly from .prettierrc file. Simplest solution is to add .prettierrc file with the same configuration from .eslintrc:

```json
{
  "semi": true,
  "tabWidth": 2,
  "printWidth": 100,
  "singleQuote": true,
  "trailingComma": "all",
  "jsxBracketSameLine": true
}
```