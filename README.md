## 使用vite创建vue2项目

参考：[Vite 创建 vue2 项目](https://blog.csdn.net/qq_46264882/article/details/123225030)


### 1. 创建`vite`项目
按照个人喜好使用`vite`或`npm`创建均可
```shell
yarn create vite
```
### 2.输入项目名并选择框架
  项目名随意，但框架要选`vanilla`
  ![20220726144636.png](https://wujun-pic-bed.oss-cn-chengdu.aliyuncs.com/img/20220726144636.png)

  之后选择要用`javascript`还是`typescript`

 ![20220726144840.png](https://wujun-pic-bed.oss-cn-chengdu.aliyuncs.com/img/20220726144840.png)

### 3.进入项目并安装`vue2`插件
  参考：[github:vite-plugin-vue2](https://github.com/underfin/vite-plugin-vue2)
  ```shell
  $ cd vite-vue2

  $ yarn install

  $ yarn add vite-plugin-vue2 -D
  ```



### 4.安装`vue-template-compiler`

不安装这个模块启动的时候会报`Error: Cannot find module 'vue-template-compiler'`的错误

```shell
yarn add vue-template-compiler -D
```



### 5.项目根目录创建`vite.config.js`文件

  ```javascript
  // vite.config.js
  import { createVuePlugin } from 'vite-plugin-vue2'
  
  export default {
    plugins: [
      createVuePlugin(/* options */)
    ],
  }
  ```



 ### 6.安装`vue2.x`
 直接运行`yarn add vue`安装的是最新版本的vue(3.x),所以这里安装要带上具体版本号 
 ```shell
 $ yarn add vue@2.7.7 -S
 ```

### 7.修改项目目录结构
  1. 项目结构如下
  ```shell
    ├── index.html
    ├── package.json
    ├── public
    │   └── vite.svg
    ├── src
    │   ├── App.vue
    │   └── main.js
    ├── vite.config.js
    └── yarn.lock
  ```
  2. 修改`main.js`

  ```javascript
  // main.js
import Vue from "vue";
import App from "./App.vue"

new Vue({
  el: "#app",
  render: (h) => h(App)
}).$mount();
  ```

3. `src`目录下创建并修改`App.vue`

```vue
   <template>
     <div>
       {{message}}
     </div>
   </template>
   
   <script>
     export default {
       data() {
         return {
           message: 'Hello world!'
         }
       },
     }
   </script>
   
   <style lang="scss" scoped>
   </style>
```



### 8.项目启动

```shell
$ yarn dev
或
$ yarn vite
```





### 9.使用vuex及vue-router

待续
