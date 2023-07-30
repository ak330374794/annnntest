# react-test

#### 介绍
react 学习  
1.react是什么？  
react用于构建用户界面的JavaScript库  
react是一个将数据渲染为HTML视图的开源JavaScript库
2.谁开发的？  
facebook开发，开源  
3.为什么要学？  
提高开发效率  
4.react特点  
采用**组件化**模式，**声明式编码**，提高开发效率及组件复用率。  
react native中可以使用react进行**移动端开发**。  
使用**虚拟DOM**+优秀的**Diff算法**，减少与真实DOM交互。  
5.学习react需要掌握的JavaScript基础  
判断this指向、class类、es6+、npm包管理、原型和原型链、数组常用方法、模块化  

React入门  
react中文网：https://react.docschina.org/




#### 软件架构
软件架构说明

目录结构
这里罗列了 Umi 项目中约定(或推荐)的目录结构，在项目开发中，请遵照这个目录结构组织代码。

├── config  
│   └── config.ts  
├── dist  
├── mock  
│   └── app.ts｜tsx  
├── src  
│   ├── .umi  
│   ├── .umi-production  
│   ├── layouts  
│   │   ├── BasicLayout.tsx  
│   │   ├── index.less  
│   ├── models  
│   │   ├── global.ts  
│   │   └── index.ts  
│   ├── pages  
│   │   ├── index.less  
│   │   └── index.tsx  
│   ├── utils // 推荐目录  
│   │   └── index.ts  
│   ├── services // 推荐目录  
│   │   └── api.ts  
│   ├── app.(ts|tsx)  
│   ├── global.ts  
│   ├── global.(css|less|sass|scss)  
│   ├── overrides.(css|less|sass|scss)  
│   ├── favicon.(ico|gif|png|jpg|jpeg|svg|avif|webp)  
│   └── loading.(tsx|jsx)  
├── node_modules  
│   └── .cache  
│       ├── bundler-webpack  
│       ├── mfsu  
│       └── mfsu-deps  
├── .env  
├── plugin.ts  
├── .umirc.ts // 与 config/config 文件 2 选一  
├── package.json  
├── tsconfig.json  
└── typings.d.ts  

.env 环境变量配置
PORT=8888
COMPRESS=none

.umirc.ts
与 config/config.ts 文件功能相同，2 选 1 。.umirc.ts 文件优先级较高  
// package.json
```json
{
    "scripts": {
        "dev": "umi dev",
        "dev:pre": "cross-env UMI_ENV=pre umi dev"
    }
}
```
#配置路由  
在配置文件中通过 routes 进行配置，格式为路由信息的数组。

比如：
```ts
// .umirc.ts
export default {
    routes: [
        { path: '/', component: 'index' },
        { path: '/user', component: 'user' },
    ],
}
```
#插件
使用插件
在普通的 Umi 应用中，默认 不附带任何插件 ，如需使用 Max 的功能（如 数据流、antd 等），需要手动安装插件并开启他们：

pnpm add -D @umijs/plugins
如开启 antd 插件：
```ts
// .umirc.ts
export default {
    plugins: ['@umijs/plugins/dist/antd'],
    antd: {}
}
```
#代理  
```js
export default {
  proxy: {
    '/api': {
      'target': 'http://jsonplaceholder.typicode.com/',
      'changeOrigin': true,
      'pathRewrite': { '^/api' : '' },
    },
  },
}
```

#### 安装教程

1. node  v16+，pnpm  v7.3+
2. pnpm dlx create-umi@latest
3. pnpm i
4. 启动项目：pnpm dev

