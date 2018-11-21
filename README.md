记录一些工作上和看见的BUG。 

1.vue-awesome-swiper   上下轮播轮播距离无限叠加。需要设置高度，配置里 height : window.innerHeight。https://segmentfault.com/q/1010000011692769

2.safari上点击失效

3.华为手机自带浏览器flex失效

5.iview modal的显示隐藏问题

iview 提供了全局关闭对话框 this.$Modal.remove()
但是这个方式只能用this.$Modal.confirm在modal里生成元素才能使用
直接在modal里放元素的话只能通过其他方式如vuex 改变v-model来控制显示隐藏
转载：https://www.jianshu.com/p/09d922e388b8   iview的一些坑

6.百度地图
API LocalResult 类表示LocalSearch的检索结果 其中province属性返回值 在直辖市（北京，天津） 点击获取地址时返回省会是区县地址

7.echarts wordCloud 词云显示不全标签丢失
 sizeRange 配置字符的范围（array），series设置这个属性就完美解决








