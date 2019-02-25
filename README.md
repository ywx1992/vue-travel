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

6. swiper
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
    
7. icons
  
  盒子模型的内容区域其实包括content+padding，即padding box，虽然正常情况下元素只在content内排布，但是当内容溢出到padding也是允许的，故overflow:hidden对此不做影响。
  
  利用这个特性，我们可以使用div的padding为图片占位，防止图片加载出现抖动现象：
  
    ```
    <div class="wrapper">
          <img class="swiper-img" src="http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg"/>
    </div>
    ```
  给wrapper添加如下css特性：
  
      ```
      overflow: hidden
      width: 100%
      height: 0
      padding-bottom: 27.0%
      background: #eee
      ```
  这样，在图片未加载时由灰色背景的div占位，图片加载后能正常显示，不会因为height为0且overflow为hidden而隐藏图片。

  
8. 解决text-overflow: ellipsis失效问题
   - 在 flex 项中设置 min-width: 0;

9. 使用axios发送ajax请求
   - npm install axios -S
   
   模拟数据/static/mock
   
   代理转发 index.js
   ```
    proxyTable: {
      '/api': {
        target: 'http://localhost:8080',
        pathRewrite: {
          '^/api': '/static/mock'
        }
      }
    },
    ```

10. 
  ```
  li {
      border-bottom: 1px solid #ddd;
      margin-bottom: -1px;
  }
  ```

11. better-scroll

```npm install better-scroll -S

  import BScroll from 'better-scroll
  
  this.scroll = new BScroll(this.$refs.wrapper)
```

12. 兄弟组件之间的联动





