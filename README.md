# 前言
根据慕课网实战课程——[Vue2.0实战带你开发去哪儿APP](https://coding.imooc.com/class/203.html)开发出来的微型项目，通过这个项目，进一步巩固自己的Vue实践能力。在这之前，还用大白话整理一篇关于[Vue基础知识的整理](https://github.com/CruxF/Vue-base/issues/1)，真的是大白话啊，因此描述的不会是很官方和标准，可能也有些是理解错了（轻点喷....），唯一的亮点就是看一遍真的就能get到Vue大部分的知识了，在这里看完一遍并且理解的话，马上撸一遍[Vue.js的官方文档](https://cn.vuejs.org/)，你会受益匪浅的！

### 多页应用和单页应用的区别
- 多页应用：它是页面跳转时返回一个HTML文件。所具备的优点是：首屏时间快，SEO效果好；缺点是：页面之间切换慢。
- 单页应用：它是页面跳转时利用JavaScript渲染出一个页面。所具备的优点是：页面切换时间短；缺点是：首屏时间稍慢，SEO效果差，因为搜素引擎只识别HTML页面的内容，但是不识别JavaScript渲染出来的页面。

### 如何全局使用一个CSS文件
这个CSS样式是所有组件公用的，使用的方式是在main.js中导入，比如：<br>
`import './assets/styles/reset.css'`

### 使用stylus编写样式代码
使用stylus语法编写样式代码能够很好进行代码管理和提高开发速度，首先我们需要利用npm下载相关的依赖包，下载方式如下：<br>
`npm install stylus --save`<br>
`npm install stylus-loader --save`<br>
下载好之后我们就可以使用它了，使用方式可以来看看相关的[中文文档](http://www.zhangxinxu.com/jq/stylus/)

### 项目单位的运算方式
拿首页头部来说，设计稿的尺寸为736x86，即设计稿头部区域高为86px（物理像素）。由于设计师给的是2倍的设计稿，于是CSS样式中这个头部区域的高得为43px（逻辑像素）。在这个项目开发中，是使用rem这个单位，因为rem是相对于根元素的字体大小的单位，该怎么理解呢？比如在全局样式reset.css中，我们设置了html的font-size为50px，则1rem=50px。那么此时逻辑像素为43px转化为rem单位值为多少呢？下面来看一看运算过程：<br>
由1rem=50px  ==>  50x?=43  ==>  ?=0.86  ==>  则此时的43px=0.86rem<br>

更多的移动端知识请转到这里————[移动端基础知识整理](https://github.com/CruxF/IMOOC/issues/4)<br>

### 提高项目的维护性
我们可以将一些经常通用的属性值放在一个样式表中，然后组件导入，直接传变量值就好了，这样就能实现修改一处而改变多处。<br>


### vue-cli项目中文件路径的别名
在项目开发之中，可能我们会写很多又长又臭的路径名，这是十分不优雅且麻烦的。比如这样的：`import '../../../assets/styles/iconfont.css'`，还有这样的：`@import '../../../assets/styles/variables.styl'`，那么在vue-cli项目中我们就可以使用一些别名来代替，比如能这么写：`import '@/assets/styles/iconfont.css'`，还能这么写：`@import '~@/assets/styles/variables.styl'`，需要注意的是在导入一个css文件到另一个css文件中，@符号前面要加个波浪线，此时这里的@代表的是整个src目录。<br>

我们还能自己来定义各种文件名的别名，修改地址是build——>webpack.base.conf.js，具体改动地方看下面的代码：
```
resolve: {
  extensions: ['.js', '.vue', '.json'],
  alias: {
    'vue$': 'vue/dist/vue.esm.js',
    '@': resolve('src'),
    'styles':resolve('src/assets/styles'),
  }
},
```
然后我们就能把一开始的导入文件地址这么写：`import 'styles/iconfont.css'`，还有这么写的：`@import '~/styles/variables.styl'`。这样修改之后导入文件路径的书写是不是方便了很多？不过需要注意的是修改了webpack.base.conf.js文件记得重新npm run dev运行项目。<br>

### 使用稳定版本的vue-awesome-swiper插件
这是一个移动端轮播插件，使用步骤为：

- 下载相关jar包`npm install vue-awesome-swiper@2.6.7 --save`
- 使用方式以及相关配置，请到[官方网站](https://github.com/surmon-china/vue-awesome-swiper)进行查看



### 有用的网站
1、能够定制和收藏属于自己的icon网站，[传送门](http://www.iconfont.cn/home/index?spm=a313x.7781069.1998910419.2)在此。我们可以在每次开发一个项目的时候都在里面收集一些icon，并为这些icon创建一个相应的仓库。<br>

**使用方式** <br>
icon新建一个项目，在官方图标库中找到相应的icon，加入购物车，再选择购物车添加到创建的项目之中，然后下载到本地。我们需要的是把iconfont.css、iconfont.eot、iconfont.svg、iconfont.ttf和iconfont.woff文件添加加到我们的开发项目中，唯一需要注意的是我们需要在iconfont.css更改下调用文件的路径，如果iconfont.eot、iconfont.svg、iconfont.ttf和iconfont.woff这些文件的位置法伤变化的话。<br>

iconfont.css是全局样式，如何去使用前面有提到。在项目中是这么来使用的，首先在相应的区域添加一个iconfont的类，然后来那个区域使用在iconfont官网复制下来的代码，下面请看案例：<br>
`<span class="iconfont">&#xe624;</span>`



# 项目下载和运行

```
下载：git clone git@github.com:CruxF/Travel.git
```
