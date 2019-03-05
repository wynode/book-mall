### 网上书城
#### 一、前言
跟着网上买的课程，一个多月零零散散的时间，终于是把这个项目完成了。这也是自己第一个用完整框架技术栈搭建的项目，对比之前自己在Sublime里手写每一行代码的刀耕火种的日子，用框架实在是舒服很多。代价也是明显的，你需要去适应另一种编码方式，常常也是右边Sublime，左边搜索引擎。


你可以通过[这个网址](mall.wynode.com)（mall.wynode.com）访问到我的项目（PC端和移动端均可）。
#### 二、项目截图
PC端
![PC端](https://github.com/wynode/book-mall/blob/master/static/mall.gif)
移动端
<img src="https://github.com/wynode/book-mall/blob/master/static/mall2.png" width="50%" height="50%">
#### 三、技术栈
前端：vue2 + vuex + vue-router + axios + webpack + ES6
服务端：nodejs + express + mongoose
数据库： mongodb
#### 四、实现功能
- 登录
- 加入购物车
- 购物车操作
- 配送地址操作
- 订单确认
- 订单ID生成
#### 五、使用
跟大多数node项目一样
``` javascript
git clone https://github.com/wynode/book-mall.git
cd book-mall
cnpm install
node server/bin/www
cnpm start
```
在根目录
#### 六、总结
1、整个项目写下来，感觉对vue全家桶的理解能算是入门了。状态管理的vuex，路由的vue-router，http客户端的axios加上vue本身的components和computed等等特性的使用，对于常规的建站甚至是大型的单页面项目已经是足够了。
如果说与react和angular相比孰优孰劣我是没有资格去评判的，其他两种中我所接触了解的angular还停留在angular2上面（其控制器的实现真的是用冗长来形容），而现在angular已经做到了5.x,有了很大的变革，但由于没有向下兼容，加上迭代更新速度太快，所以流失的用户是相当多。而react还在我的下一个学习目标中，所以vue暂时在我心中算最好的前端框架吧。

2、更重要的是前后分离的概念在我的心中更加的明确。开发阶段如果不是只有我一个人写，完全可以一个人写前端，一个写后端，最后上线方面，服务端的代码和前端代码的分开部署，互不干扰，让我体会到一个完整的项目应该有的样子。



