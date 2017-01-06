# vue-basic
## 运行实例

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```
## 详细教程

### 全局安装vue + webpack + vue-cli

```
npm install -g vue       //全局安装vue
npm install -g webpack   //全局安装webpack
npm install -g vue-cli   //全局安装vue-cli

```

### 生成项目目录


```
vue init webpack projectName        //生成项目名为projectName的模板
```
- 进入新生成的目录&安装依赖  
- **运行安装时特别注意：可以不用安装==eslint,mocha==等等依赖，因为大家都懂的原因特别慢，而且在编写代码时容易出现错误，让人摸不着头脑，所以建议初学不安装**

- **如下图**

![安装图](http://www.omwteam.com/public/md/vue-install.png)

```

cd projectName                   // 进入新生成的目录  
// 注意运行安装命令式需要一次输入目录名称，描述，作者，eslint,mocha等
// 不用安装 eslint及后面的依赖 请选择 N
npm install                         // 安装依赖

npm run dev  // 运行开发即可自动打开浏览显示初始页面，热更新

npm run build // 运行构建生成生产环境可发布的代码
```
运行成功如下图

![vue-welcome](http://www.omwteam.com/public/md/vue-welcome.png)

---
---

### 使用基本路由用


- 安装路由
```
npm install vue-router
```


### 配置路由

在main.js里面


```
import Vue from 'vue'
import VueRouter from 'vue-router'
import App from './App'

Vue.use(VueRouter);

const routes = [
  { path: '/',  redirect: '/index'},// 首页默认重定向至Index路由
  
  { path: '/test', component: resolve => require(['./components/test.vue'], resolve) }

  { path: '/index', component: resolve => require(['./components/index.vue'], resolve) }
 
];

const router = new VueRouter({
  routes // （缩写）相当于 routes: routes,
});

// 4. 创建和挂载根实例。
// 记得要通过 router 配置参数注入路由，
// 从而让整个应用都有路由功能
const app = new Vue({
  router,
  render: h => h(App)
}).$mount('#app');
```
### vue应用的基本目录

- ==pages== 是我自己增加的目录用来存储路由视图

```
例如 一个应用有首页，搜索页面，列表详情页就对应着有三个路由
首页   =>  index 路由
搜索页 => search 路由
列表页 => list 路由
所以pages文件夹里面对应着三个文件为index.vue,search.vue,list.vue
```
- ==components== 是组件库文件夹

```
例如 假如首页需要三个组件分别为轮播swipe组件，搜索栏组件，listView组件
那么我就需要在components里面增加三个组件

如果是大型项目就需要每个路由对应着一个组件文件夹 
index路由对应在components里面增加一个index文件夹专门用来存储Index路由里面的组件

```
- 基本结构图

![基本结构图](http://www.omwteam.com/public/md/vue-app.png)

- 路由组件图
![路由组件图](http://www.omwteam.com/public/md/vue-router.png)

- 效果图

![酷我效果图](http://www.omwteam.com/public/md/kw.png)

- 谢谢大家

![装逼结束](http://www.omwteam.com/public/md/zb.png)



For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
