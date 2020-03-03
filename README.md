# travel

> A Vue.js project

##### 项目名称：去哪儿旅游网App

##### 项目开发环境：WebStrom+ES6+stylus+node.js+vue2.5+webpack+npm

项目描述：本项目是参考去哪儿网进行开发布局，实现了根据不同城市选择不同景点的功能，本项目一共包括三个页面，App首页，城市选择页面和景点详情页面。

项目细节：首页实现了多区域轮播的功能以及多区域列表的循环展示，在城市选择页面，我们实现了城市展示、城市搜索以及城市右侧区块与城市动画联动的效果，在景点详情页面，实现了公用的画廊组件，渐隐渐显的Header组件以及递归展示的列表组件。

项目功能实现：
1.利用Axios进行Ajax数据的获取；
2.使用vue-router来做多页面之间的路由；
3.使用Vuex来做多个页面之间的数据共享；
4.使用better-scroll，vue-awesome-swiper等插件来实现页面的渲染；
5.使用stylus编写前端的样式；
6.使用了递归组件实现了组件调用自身组件的效果。

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
