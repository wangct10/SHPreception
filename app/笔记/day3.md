1：完成一级分类动态添加背景颜色
第一种解决方案：采用样式完成
第二种解决方案：通过JS完成

2：通过JS控制二三级商品分类的显示与隐藏
最开始的时候，是通过CSS样式display：block|name显示与隐藏二三级商品分类

3:演示卡顿现象
正常：事件触发非常频繁，而且每一次触发，回调函数都要去执行（如果时间很短，而回调函数内部有计算，那么很可能出现浏览器卡顿）
  比如changeIndex（index）事件
      // index:鼠标移动上某一个分类的元素的索引值
      //正常情况（用户慢慢的操作）：鼠标进入，每一个一级分类h3，都会触发鼠标进入事件
      //非正常情况（用户操作很快）：本身全部的一级分类都应该触发鼠标进入事件，但是经过测试，只有部分h3触发了
      // 就是由于用户行为过快，导致浏览器反应不过来，如果当前回调函数中有一些大量业务，有可能会出现卡顿现象

节流：在规定的间隔时间范围内不会重复触发回调，只有大于这个时间间隔才会触发回调，把频繁触发变为少量触发
（相当于技能cd刷新)
答：下载引入lodash
_.throttle


防抖：前面的所有的触发都被取消，最后一次执行在规定时间之后才会触发，也就是说如果连续快速的触发，只会执行
（相当于打断回城）
答：下载引入lodash
_.debounce


4：完成三级联动节流的操作

5：三级联动组件的路由跳转与传递参数
三级联动用户可以点击的：一级分类、二级分类、三级分类，当你点击的时候
Home模块跳转到search模块，一级会把用户选中的产品（产品的名字、产品的ID）在路由跳转的时候，进行传递。

路由跳转：
声明式导航：router-link
编程式导航：push|replace

三级联动：如果使用声明式导航router-link，可以实现路由的跳转与传递参数。
但是需要注意，会出现卡顿现象

router-link：可以一个组件，当服务器的数据返回之后，循环出很多的router-link组件【创建组件实例】1000+，
创建组件实例的时候，一瞬间创建1000+很好内存的，因此出现了卡顿现象


6：完成三级联动路由跳转与传递参数
this.$router.push({name:"search",query:{categoryName:'xxx',2id:'xx'}})