## 开发日志
### 安装依赖
`npm install pnpm -g`
`pnpm init`
`pnpm install vue typescript -D`

### 引用提升
typescript/vue的一些依赖放到了.pnpm下面, 需要创建.npmrc进行引用提升
`shamefully-hoist = true`
node_modules下会多出一些依赖

### 初始化ts文件
调用node_modules/.bin/tsc
`pnpm tsc --init`
配置tsconfig.json

### 搭建monorepo 
在本仓库下管理多个仓库
在一个项目下管理多个项目
新建pnpm-workspace.yaml
在包目录下依次执行pnpm init
三个包想要互相调用, 需要将三个包安装到全局
使用第三方模块的方式进行引用
`pnpm install @simon/components -w`
`pnpm install @simon/theme-chalk -w`