1. MVC和MVVM

   MVC中，M：model，V：view，C：controller，主要逻辑集中在view，controller层很薄，只起到路由的作用。

   MVVM中，M：model，V：view，VM：view-model，将数据双向绑定的思想作为核心，因此在View和Model之间没有联系，通过view-model进行交互。

2. data为什么要用方法而不是对象

   因为Vue是单页面应用，各个组件都有data，如果data使用对象，是引用类型的值，如果一个组件中改变了data，其他组件中的data也改变了，因此要用方法来创建独立的作用域，防止组件之间相互引用。

3. VUE双向绑定的原理

   利用Object.defineProperty()这个方法重新定义了对象获取属性值(get)和设置属性值(set)的操作来实现的。

4. Computed和watch的区别

   a) computed支持缓存，只有依赖数据发生变化，才会重新进行计算，而watch不支持缓存，数据变，直接会触发相应的操作。

   b) computed不支持异步，当computed内有异步操作时无效，无法监听数据的变化，而watch支持异步。

   c)computed属性值会默认走缓存，计算属性是基于它们的响应式依赖进行缓存的，也就是基于data中声明过或者父组件传递的props中得数据通过计算得到的值；而watch监听的函数接收两个参数，第一个参数是最新的值，第二个参数是输入之前的值。

   d) 如果一个属性是由其它属性计算而来的，这个属性依赖其它属性，是一个多对一或者一对一，一般用computed，热当一个属性发生变化时，需要执行对应的操作，一对多一般用watch。

   e)如果computed属性属性值是函数，那么默认会走get方法；函数的返回值就是属性的属性值；在computed中的属性都有一个get方法和set方法，当数据变化时，调用set方法，而watch监听数据必须是data中声明过或者父组件传递过来的props中的数据，当数据变化时，触发其他操作，函数有两个参数。

5. Slot插槽

   可以获取组件里的内容，应用场景：自定义组件使用，比如定义button按钮。

6. 生命周期：

   a)     beforeCreate：初始化之前

   b)     created： 初始化完成（不能获取dom,一般用于获取ajax数据）

   c)     beforeMount:beforeMount挂载之前

   d)     Mounted：挂载完成之后

   e)     Updated:数据更新之后。

   f)     beforeDestoy:接触绑定之前（页面离开）

   g)     destroyed：解除绑定之后（页面离开）

7. 如何知道页面是离开还是刷新？

8. 移动端布局及适配方式？

   Viewport，rem，百分比布局，媒体查询

9. fetch,ajax,axios区别？

10. hash和history模式的区别？

    hash模式：路由地址带#号，适合做后台管理系统

    history模式：路由地址不带#号，适合做前端宣传界面，但是history模式有个问题就是刷新页面会出现404错误，解决方法需要配置服务器

11. vuex?

    Vuex是一个专为vue.js应用程序开发的状态管理模式，将数据分发给各个组件，异步数据流，统一封装接口。(state,mutations,actions,getters,modules)

12. Better-scroll解决滚动场景需求的插件，(借鉴了iscroll)，实现了下拉刷新，上拉加载

