# Vue 3 + TypeScript + Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

Learn more about the recommended Project Setup and IDE Support in the [Vue Docs TypeScript Guide](https://vuejs.org/guide/typescript/overview.html#project-setup).

## Eslint + Prettier 세팅

Eslint가 Prettier rule까지 체크하여 코드 스타일링을 지키지 않아도 에러로 처리됩니다.
format on save 기능과 함께 이용하면 유용합니다.

## Vite 설치

npm을 기준으로 설명

```bash
npm create vite@latest my-vue-app -- --template vue-ts
```

## 디펜던시 설치

`eslint` 9 버전과 호환성 이슈가 있기 떄문에, 8 버전을 기준으로 다른 디펜던시를 설치합니다.

```bash
npm install --save-dev eslint-plugin-vue eslint@^8 eslint-plugin-prettier eslint-config-prettier prettier @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

## ESLint 설정

`.eslintrc`를 아래와 같이 작성합니다.

```json
{
  "root": true,
  "env": {
    "node": true
  },
  "plugins": ["@typescript-eslint"],
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:vue/vue3-recommended",
    "plugin:prettier/recommended"
  ],
  "parser": "vue-eslint-parser",
  "parserOptions": {
    "parser": "@typescript-eslint/parser",
    "sourceType": "module"
  }
}
```

## Prettier 설정

굳이 하지 않아도 되지만, 원래 사용하던 prettier 설정이 있다면 `.prettierrc`를 따로 적는다.

```json
{
  "trailingComma": "all"
}
```

## format on save 설정

VS Code 설정의 `setting.json`을 열고 아래 속성을 추가하면, 저장할 때 마다 lint됩니다.

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

## npm script 추가하여 CLI Linting

CAVEAT: 일부 prettier 룰이 잘 적용되지 않음

```json
  "scripts": {
    "dev": "vite",
    "build": "vue-tsc -b && vite build",
    "preview": "vite preview",
    "lint:fix": "eslint --ext .js,.vue,.ts src --fix"
  },
```
