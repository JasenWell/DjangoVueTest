# DjangoVueTest
 django,vue
 
 1.进入node.js官网下载相应安装包：https://nodejs.org/en/  LTS版本最好
 cmd命令行下 node -v  来判断是否安装成功
 在安装node的时候，npm包管理器会自动安装，我们在命令输出 npm -v 看看是否安装成功
 安装vue-cli脚手架：
 npm install -g vue-cli 或者使用国内的淘宝镜像 npm install -g cnpm --registry=https://registry.npm.taobao.org     后执行 cnpm i -g vue-cli
 
 npm install webpack -g 安装webpack  //https://blog.csdn.net/qq_33036599/article/details/75666058  -g表示全局安装
 
 
 进入项目目录创建项目 
 vue-init webpack frontend
 
 cd frontend 进入vue项目目录，安装依赖
 npm install --registry=https://registry.npm.taobao.org
 npm i element-ui -S
 
 npm run build 打包  //https://blog.csdn.net/liuyukuan/article/details/70477095   新增文件需要重新构建
 配置templates模块路径 指向vue
 配置静态文件路径 指向vue
 
 运行
 
 
 https://element.eleme.cn/#/zh-CN/component/layout  element-ui学习
 https://blog.csdn.net/csdn_yudong/article/details/85250412  后台管理
 https://www.cnblogs.com/wdlhao/p/8075646.html
 https://segmentfault.com/a/1190000016377881
 
 
 https://www.cnblogs.com/donghuang/p/10042812.html npm run build打包优化
 
 
 vue 浏览器兼容
 在 vue cli2 项目中使用Vuex时，ie浏览器会出现“Vuex requires a Promise polyfill in this browser”的错误提示，这是因为使用了ES6 Promise,而IE浏览器不支持，解决方案如下：
1. 安装babel-polyfill 执行以下命令，重启服务器：
npm install --save babel-polyfill

2.在main.js引入
import 'babel-polyfill'

3.在webpack.base.conf.js中配置:
entry: {
    app: ['babel-polyfill','./src/main.js']
},
vue-cli3下 解决浏览器兼容性问题

1. 安装babel-polyfill依赖
 npm i babel-polyfill --save-dev

2.在src同级目录下新建vue.config.js文件配置如下

module.exports = {
    configureWebpack: {
        devServer: {
            proxy: {
                //名字可以自定义，这里我用的是api/
                '/api/': {
                    target: 'https://www.163.com', //设置你调用的接口域名和端口号 别忘了加http
                    ws: true, // 是否代理websockets
                    changeOrigin: true, //这里设置是否跨域
                    pathRewrite: {
                        '^/api/': 'https://www.163.com'
                    }
                }
            }
        }
    },
    chainWebpack: config => {
    // 其他配置
    config.entry('main').add('babel-polyfill') // main是入口js文件
    // 其他配置
   }
}


链接：https://www.jianshu.com/p/e4f27a499209

 
 bootstrap
 
 https://blog.csdn.net/pengyufight/article/details/94400561 bootstrap框架
 https://www.jianshu.com/p/b501695c1308
 https://blog.csdn.net/u011220960/article/details/81189547
 https://www.cnblogs.com/derek1184405959/p/9060981.html
 https://blog.csdn.net/ITBigGod/article/details/79670538