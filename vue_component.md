https://www.jianshu.com/p/c7dc624ae6c7

Vue-router
是Vue.js官方的路由插件，它和vue.js是深度集成的，适合用于构建单页面应用。vue的单页面应用是基于路由和组件的，路由用于设定访问路径，并将路径和组件映射起来。

安装：npm install vue-router --save

通过以上步骤，我们已经安装好了vue-router，但是在vue-cli中我们如何使用呢？

首先，我们需要在main.js文件中导入并注册vue-router:

//ES6语法导入

import VueRouter from 'vue-router'

//注册

Vue.use(VueRouter)

然后便是实例化：

const router = new VueRouter({

mode: 'history',

routes:[

  {path: '/', component:DemoHome},

  {path: '/about', component:DemoAbout},

  {path: '/contact', component:DemoContact}

]

})

path: 是路由的路径。

component: 是该路由需要渲染的组件。

Element-ui
Element，一套为开发者、设计师和产品经理准备的基于 Vue 2.0 的桌面端组件库

安装：npm i element-ui -S

在main.js中引入和注册

引入：

import ElementUI from 'element-ui';

import 'element-ui/lib/theme-chalk/index.css';

注册：

Vue.use(ElementUI);

Vuex
Vuex 是一个专为 Vue.js 应用程序开发的状态管理模式。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。

安装：

npm install vuex --save

在main.js中引入和注册

引入：

import Vuex from 'vuex‘

注册：

Vue.use(Vuex)

VueAwesomeSwiper
轮播图插件，可以同时支持Vue.js（1.X ~ 2.X），兼顾PC和移动端，随着vue的广泛使用，其中插件swiper也算是使用的比较频繁的插件。

安装：

npm install vue-awesome-swiper --save

在main.js中引入和注册

引入：

import VueAwesomeSwiper from 'vue-awesome-swiper'

注册：

Vue.use(VueAwesomeSwiper)

Echarts
实现数据界面可视化

安装：

npm install echarts --save

在main.js中配置：

import echarts from 'echarts' //引入echarts

Vue.prototype.$echarts = echarts //引入组件

jQuery
安装：npm install jquey

在main.js中引入：

import $ from 'jquery'

这是jquery不是全局的，如果要使用在每一个模块中需要import 。比较麻烦，下面是设置jquery为全局的方法：

修改webpack.base.conf.js(在build文件下)两个地方：

var webpack=require('webpack');

在module.exports的里面加入

plugins: [

    new webpack.optimize.CommonsChunkPlugin('common.js'),

    new webpack.ProvidePlugin({

        jQuery: "jquery",

        $: "jquery"

    })

]

bootstrap
想要在vue中引入bootstrap，引入的时候需要按照如下的步骤进行。

1、引入jquery(上一步骤即可)

2、引入bootstrap

安装：

npm install bootstrap --save-dev

把bootstrap库的js和css放到assets文件夹下，在webpack.base.conf.js的module.exports = {}中的resolve中增加

'bootstrap':resolve('src/assets/bootstrap'),

在main.js中引入：

import 'bootstrap/js/bootstrap.js'

import 'bootstrap/css/bootstrap.css'

axios
安装：npm install axios --save-dev

在main.js中引入注册：

引入：

importaxiosfrom'axios'

注册：

Vue.prototype.$http= axios

