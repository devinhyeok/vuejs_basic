# vuejs_basic

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

## gh-pages 배포하는법

### 1. 터미널을 통해 gh-pages 설치
```
npm i gh-pages
```

### 2. vue.config.js 수정
#### npm으로 프로젝트 생성시
```
const { defineConfig } = require('@vue/cli-service')
module.exports = defineConfig({
  transpileDependencies: true,
  publicPath: process.env.NODE_ENV === 'production' ? '/vuejs_basic' : '/', // 추가
})
```
#### vite로 프로젝트 생성시
```
export default defineConfig({
  base: '/vue3-learn/', // 추가
  plugins: [vue()],
  resolve: {
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    }
  }
})
```

### 3. pacakage.json에 "depoly", "predeploy" 추가
```
"scripts": {
  "serve": "vue-cli-service serve",
  "build": "vue-cli-service build",
  "lint": "vue-cli-service lint",
  "deploy": "gh-pages -d dist", // 추가
  "predeploy": "npm run build" // 추가
},
"homepage": "https://devinhyeok.github.io/vuejs_basic/" // 추가
```

### 4. 터미널을 통해 빌드
```
npm run deploy
```
