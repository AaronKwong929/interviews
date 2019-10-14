# 总时长20分钟的视频面

## 自我介绍

## 为什么学前端（契机），怎么学的前端，学了多久前端

## 正则表达式有用过吗？怎么使用正则表达式判断手机号的准确性

回答了：/^d{11}%/

正解（？）看下面

``` JS
let re = /^1(3|5|7|8)\d{9}$/
console.log(re.test( `13123456789` ));
```

## vue是用脚手架写的吗

### 回答是，可以多加一句说自己可以脱离脚手架写vue spa页面

## vue的父子组件怎么通信

回答：v-on v-emit vuex eventBus props

（eventBus给自己挖了一坑）

父组件使用子组件标签 v-bind:xxx="~~~"  (:xxx = "~~~")

子组件通过props: ["xxx": "12345"] 然后调用12345

父组件引用子组件时候加上 ref="xxx", this.$refs.xxx.数据/方法

子组件 this.$parent.数据/方法

### 非父子组件

空的js文件并暴露

``` JS
let abc = new Vue();
export default abc;
```

在父子组件引入该文件，xx.$emit('1234', xxxxxx);

xx.$on('1234', callback)

## （追问）eventBus在什么情况下适用 

## 低频，少组件通信下使用

其实就是emit on

``` JS
// main.js
Vue.prototype.$eventBus = new Vue()
// component a
this.$eventBus.$emit('key','data-1232131232132131232');

B组件中接收A组件的数据

this.$eventBus.$on('key',function(params){ console.log(params); });
```

## 平时用什么工具来调试项目

回答： vue DevTools，chrome的开发者后台

## （追问）说到了开发者后台，说一下平时你注意哪几个地方（指 F12 里的 elements, console, network

回答：elements，console，network，performance

## （追问2）为什么要看 performance，network里你又看什么

回答：performance是看项目加载速度想办法优化的时候去看的，看网页加载的问题，network里看前后端交互的信息返回，前端有无发出正确信息，后端是否有相应正确的信息

## cookie头部有什么属性

回答：expires（回答不出来了）

|属性|描述|
|-----|-----|
|name|Cookie的名称，Cookie一旦创建，名称便不可更改|
|value|Cookie的值，如果值为Unicode字符，需要为字符编码。如果为二进制数据，则需要使用BASE64编码|
|maxAge|Cookie失效的时间，单位秒。如果为整数，则该Cookie在maxAge秒后失效。如果为负数，该Cookie为临时Cookie，关闭浏览器即失效，浏览器也不会以任何形式保存该Cookie。如果为0，表示删除该Cookie。默认为-1。|
|secure|该Cookie是否仅被使用安全协议传输。安全协议。安全协议有HTTPS，SSL等，在网络上传输数据之前先将数据加密。默认为false。|
|path|Cookie的使用路径。如果设置为“/sessionWeb/”，则只有contextPath为“/sessionWeb”的程序可以访问该Cookie。如果设置为“/”，则本域名下contextPath都可以访问该Cookie。注意最后一个字符必须为“/”。|
|domain|可以访问该Cookie的域名。如果设置为“.google.com”，则所有以“google.com”结尾的域名都可以访问该Cookie。注意第一个字符必须为“.”。|
|comment|该Cookie的用处说明，浏览器显示Cookie信息的时候显示该说明。|
|version|Cookie使用的版本号。0表示遵循Netscape的Cookie规范，1表示遵循W3C的RFC 2109规范|

## 为什么会做这个项目

回答：总共做了三个版本的这个项目，（说了每个项目的区别），第三个版本的特点（上线，前后端分离），前端学习的尝试，毕业设计样稿

## 项目后端koa用了什么插件

回答：koa-bodyParser（处理post请求的数据）, koa-router...（一时记不清）

### 其实还有 koa-static（处理前端打包过来的dist（静态资源））, koa2-cors（在跨域部分提及了）

## koa-router 有什么用

回答：注册路由

### 如果所有路由都写在一个中间件里，路由要写在switch语句中，可读性↓，可维护性↓，项目变大时会很复杂，而且这样只能写 get/post，使用 koa-router 解决这个问题

## 做这个项目你有遇到什么难题，你是怎么解决的

回答：评论区，楼中楼，前端分页器的逻辑思维，开发/生产时产生的跨域问题

### 评论区楼中楼分页器可以改至项目体积优化

## （追问）项目需要跨域吗？你是怎么解决跨域问题的

回答：

前端部署在8080，后端部署在3000端口，交互产生了跨域

开发环境下：vue-cli3 vue.config.js 里的 devServer下加一个proxy，代理接口转发

生产环境下：使用了koa2-cors

## （追问2）项目体积优化怎么做到的

回答：本来加载速度巨慢，打开上线版本需要10秒的加载时间，后面发现是前端引入的js文件太大了(highlight.js)，后面使用cdn源引入这些文件，将项目打包体积压到100k不到

## （追问3）说到了cdn引入，你用了哪一家的cdn源

回答说想不起来

### [bootcdn](https://www.bootcdn.cn/)

## 你简历里的项目地址是个ip地址，为什么

回答：写简历的时候域名备案还没过，现在已经过了，正常域名访问了

## （追问）项目是怎么上线的，用了哪家的云

回答：腾讯云

## （结束）你有什么问题要提出来吗

回答：如果我能入职，你希望我能在前面的几个月能做什么？

