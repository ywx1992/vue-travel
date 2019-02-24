# vue-travel

> A Vue.js project

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

1. 引入样式初始化文件 reset.css

2. 引入1px边框文件 border.css

3. 安装fastclick,解决移动端300ms延迟  
   - npm install fastclick -S
  
4. iconfont `https://www.iconfont.cn/`
   - 引入iconfont.css

5. npm install less less-loader -D
   - 定义变量variables
   - 组件style中引入 `import '~styles/variables.css'`

6. header 
   - 创建分支index-swiper,在分支上开发
   - 轮播图插件 `https://github.com/surmon-china/vue-awesome-swiper`
    `npm install vue-awesome-swiper@2.6.7 -S`
    
    scoped看起来很好用，当时在Vue项目中，当我们引入第三方组件库时(如使用vue-awesome-swiper实现移动端轮播)，需要在局部组件中修改第三方组件库样式，而又不想去除scoped属性造成组件之间的样式覆盖。这时我们可以通过特殊的方式穿透scoped
    
    1、stylus的样式穿透 使用 >>>
       
    `.wrapper >>> .swiper-pagination-bullet-active
     background: #fff`
     
    2、sass和less的样式穿透 使用 /deep/
    
    外层 /deep/ 第三方组件 {
        样式
    }
    
    `.wrapper /deep/ .swiper-pagination-bullet-active{
      background: #fff;
    }`
    
    由于scoped看起来很美好，但是含有很多的坑，所以，不推荐不使用scoped属性，而通过在外层dom上添加唯一的class来区分不同组件
    
