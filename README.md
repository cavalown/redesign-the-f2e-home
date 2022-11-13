# Redesign The-F2E-4th Home Page

## UI/UX
[UI/UX：Weily Huang](https://www.figma.com/file/wzATDupkAO6HklzhFoAXuK/REDESIGN-F2E?node-id=0%3A1)
## Introduction
Redesign "[2022 The F2E 4th](https://2022.thef2e.com/)" home page.

Here's [Mission Description](https://2022.thef2e.com/news/week1).




## Setup
```
$ npm install
```

### Compiles and hot-reloads for development
```
$ npm run serve
```

### Compiles and minifies for production
```
$ npm run build
```

## Technologies
Node.js v12.22.9
Vue Cli
Vue 3

## Directors
./src
├── App.vue 
├── assets
│   └── images 靜態圖片
├── components 元件components
│   ├── Navbar.vue 
│   └── homeComponents
├── main.js
├── router
│   └── index.js 只有使用home
├── store
│   └── index.js 沒有用到
├── style
│   ├── _mixin.scss pad & phone
│   ├── all.scss
│   └── reset.scss
└── views
    └── Home.vue

## Third Party Services
GSAP

