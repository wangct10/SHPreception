复习：
1)完成商品分类的三级列表路由跳转一级路由传参（合并参数）
2）完成search模块中对于typeNav使用（过渡动画的）
3）关于typeNav请求次数进行优化
4）swiper插件：
swiper插件：经常制作轮播图（移动端|pc端也可以使用）
使用步骤：
第一步:引入相应依赖包（swiper.js|swiper.css）
第二步：页面中的结构务必要有
第三步：初始化swiper实例，给轮播图添加动态效果
5）mock数据：通过mockjs模块实现的

1：最完美的解决方案，解决轮播图问题：
watch+nextTick：数据监听，监听数据已有变化
$nextTick:在下次DOM更新循环结束之后执行延迟回调，在修改数据之后立即使用这个方法，获取更新后的DOM，可以保证页面中的结构一定是有的，经常和很多插件一起使用【都需要DOM存在了】。

2:开发floor组件
切记：仓库中的state的数据格式，别瞎写，胡写，乱写，数据格式取决于服务器返回的数据
2.1：getFloorList这个action在哪里触发，是需要在Home路由组件当中发的，不能在Floor组件内部发action，因为我们需要v-for遍历floor组件
2.2:v-for也可以在自定义标签当中使用
2.3:组件通信的方式有哪些?
props：用于父子组件通信
自定义事件：@on @emit 可以实现子给父的通信
全局事件总线bus：全能
pubsub-js：vue当中几乎不用，全能
插槽
vuex

3:把首页当中轮播图拆分一个共用全局组件
切记：以后在开发项目的时候，如果看到某一个组件在很多地方都使用，把它设为全局组件，。
在main.js注册一次，可以在任意地方使用，共有的组件|非路由组建放到components

4:search模块开发？
1：先静态页面+静态组件拆分出来
2：发请求（API）
3：vuex（三连环）
4：组件获取仓库，动态展示数据


