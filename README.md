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

7.echarts使用词云必须先安装依赖 并且在main添加
import 'echarts-wordcloud/dist/echarts-wordcloud.min.js'
import 'echarts-wordcloud/dist/echarts-wordcloud.js'

8.echarts wordCloud 词云显示不全标签丢失
 sizeRange 配置字符的范围（array），series设置这个属性就完美解决
 
9.iview级联BUG 当选择第三级的时候不能退回选择相关的第二级

10 element upload上传图片时 展示不了已上传的图片的列表
需要在 :file-list 存入(上传的文件列表, 例如: [{name: 'food.jpg', url: 'https://xxx.cdn.com/xxx.jpg'}]）;
然而使用before-upload 中返回的file里没有url的值 ，改为:on-change 里面可返回 url值再保存进入file-list便可展示已上传的文件或者图片

11 element 事件不能传递 $event 如一些组件中的change click等 （不懂是不是全部都是？）

12 element upload 会报错Cannot set property 'status' of null 这是什么鸡掰回事？

13 富文本上传需要encodeURI编码

14 Clipboard.js 在安卓的UC浏览器和QQ浏览器下不能复制 IOS所有浏览器都没问题， 安卓的UC浏览器和QQ浏览器会有问题，百度浏览器是没有问题。

15 iview select组件 添加配置 label-in-value	 再用on-change监听时会返回两次 一次返回选择的值 第二次返回空

16 新项目main.js中 import引入CSS文件报错  
报错问题是在index中 文件引入路径错误
原本index中引入错误路径 <script src="./src/main.js"></script> 
正确引入  <script src="main.js"></script>
https://www.webpackjs.com/guides/getting-started/#创建一个-bundle-文件  问题解答

17 微信网页 js 动态设置 document.title失效  https://www.jianshu.com/p/ce0e829b1bc2

18 iview Tooltip  提示组件放在最顶部，每次移入显示的提示窗口位置会有误差 还未找到什么样式有干扰

19 echarts 文字标题 title 文字align属性失效  title -> textStyle -> align  文字不能居中偏右偏左

20 echarts pie的移入让移入的块状高亮 
myChart.dispatchAction({ //高亮
   type: 'highlight',
   name: xxx,
 }) 
 但是移入使目标高亮一瞬间立马就消失高亮状态 加上移出目光也添加高亮才解决 并且移入移出都要重新setOption 
   myChart.on('mouseover', (res)=> {
      myChart.setOption(option, true);
       myChart.dispatchAction({
           type: 'highlight',
           name: res.name
       })
   });   
    myChart.on('mouseout', (res)=> {
      myChart.setOption(option, true);
       myChart.dispatchAction({
           type: 'highlight',
           name: res.name
       })
   });   

21.





