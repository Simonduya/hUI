## 开发日志
## vue3组件库monorepo环境搭建
### 安装依赖

`npm install pnpm -g`
`pnpm init`
`pnpm install vue typescript -D`

### 引用提升

typescript/vue 的一些依赖放到了.pnpm 下面, 需要创建.npmrc 进行引用提升
`shamefully-hoist = true`
node_modules 下会多出一些依赖

### 初始化 ts 文件

调用 node_modules/.bin/tsc
`pnpm tsc --init`
配置 tsconfig.json

### 搭建 monorepo

在本仓库下管理多个仓库
在一个项目下管理多个项目
新建 pnpm-workspace.yaml
在包目录下依次执行 pnpm init
三个包想要互相调用, 需要将三个包安装到全局
使用第三方模块的方式进行引用
`pnpm install @simon/components -w`
`pnpm install @simon/theme-chalk -w`

## 初始化 play 文件

`pnpm create vite play --template vue-ts`

### 添加全局的类型限制

vue-shim.d.ts

### 运行代码

在 play 文件下执行 npm run dev (vite)
但是希望在根目录下执行代码
配置外层的 package.json
`  "scripts": {
    "dev": "pnpm -C play dev"
  },`

## 通过JS实现BEM规范
packages/utils/create.ts

## 实现icon组件
components/icon
配置props属性处理
使用插件定义组件的名字 `pnpm install unplugin-vue-define-options -D -w`, 
在play/vite.config.ts中引入该包`import DefineOptions from 'unplugin-vue-define-options/vite'
`