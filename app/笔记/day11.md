1）登陆过后首页用户信息的展示
URL：/api/user/userAddress/auth/findUserAddressList  method：get
1.1当用户注册完成，用户登录【用户名+密码】向服务器发请求（组件派发action：userLogin），
登陆成功获取到token，仓储与仓库中（非持久化，刷新就没），路由跳转到home主页
1.2因此再首页当中（mounted）派发action（getUserInfo）获取用户信息，一级动态展示header组件内容。
1.3一刷新home首页，获取不到用户信息（token：vuex非持久化存储）
1.4持久化存储
1.5存在问题
 1.多个组件展示用户信息需要在每一个组件的mounted中发出this.$store.dispatch('getUserInfo') 不行
 2.用户已经登陆了，就不应该再回登录页

 2)退出登录

 3）导航守卫
 导航：表示路由正在发生改变，进行路由跳转
 守卫：你把它当‘紫禁城守卫’
 全局守卫：你的项目中，只要发生路由变化，守卫就能监听到
 举例子：紫禁城【皇帝，太后，妃子】，紫禁城大门守卫全要排查
 路由独享守卫：
 举例子：紫禁城【皇帝、太后、妃子】，是相应的【皇帝、太后、妃子】路上守卫
 组件内守卫：我要去皇帝的屋子
 举例子：老师已经到皇帝屋子外面了（进入了）守卫
 比如：用户已经登录，用户不应该还能去login页面

 4）整个项目、游客（UUID）与用户（token），后台老师以token为大

 5）同意登录的帐号？
 1862254545556 qqq
老师的帐号：（能获取地址信息）
 13700000000  111111

 6）获取交易页面用户信息？
 用户登录了才可以获取用户地址信息，不登录没办法获取到的

