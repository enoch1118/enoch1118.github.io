---
layout: posts
title: “React Native 의 eslint prettier 적용방법”
categories:
  - react-native
---

[React Native 에 ESLint 적용하기. how to use eslint for react-native | by lama. | lamaground | Medium](https://medium.com/lamaground/react-native-%EC%97%90-eslint-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0-3a8aeee4dc53)

여기에 잘나와있다.

`npm install --save-dev eslint-config-airbnb eslint-plugin-import eslint-plugin-react eslint-plugin-jsx-a11y`

`eslint --init`

`npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettie`

> eslintrc

```
module.exports = {
extends: [
"airbnb",
"prettier",
"prettier/react",
"plugin:prettier/recommended",
"eslint-config-prettier"
],
parser: "babel-eslint",
rules: {
"import/no-unresolved": "off",
"react/jsx-filename-extension": [
1,
{
extensions: [".js", ".jsx"]
}
],
"prettier/prettier": [
"error",
{
trailingComma: "es5",
singleQuote: true,
printWidth: 100
}
]
},
plugins: ["prettier"]
};
```

> vscode setting.json

```
{
  "prettier.eslintIntegration": true,
  "editor.formatOnSave": true,
  "editor.tabSize": 2
}
```

> .prettierrc

```
{
  "singleQuote": true,
  "semi": true,
  "useTabs": false,
  "tabWidth": 2,
  "trailingComma": "all",
  "printWidth": 80
}
```
