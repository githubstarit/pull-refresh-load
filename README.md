# pull-refresh-load
轻量级下拉刷新/上拉加载

# 简介
之前做下拉刷新和上拉加载，尝试了很多方式，也包括iscroll框架等。发现总有不如意的地方。比如使用iscroll框架，会发现在旧的android设备下，数据量大的情况会出现很多问题，比如卡、闪白等等。
总结了下，不能自己通过touch事件来模拟滚动条，因为在旧设备和大数据量的情况下回出现兼容问题。而且类似iscroll的框架太重，就为了下拉刷新和上来加载就自己模拟滚动，不是很好。
总结了下就自己简单封装一个。

# 使用方式

* 依赖Zepto或者jquery库
* 在html中引入 css/pull.css和js/pull.js
* 通过new Pull(options)来初始化Pull组件


# options配置参数
* scroller ： 滚动区域的dom
* scrollArea ： 滚动容器的dom
* pullDown ：下拉刷新监听  pullDown函数格式  function(pull){}
* pullUp ： 上拉加载监听   pullDown函数格式  function(pull){}

# 方法
* refresh(state) : 用于刷新滚动区域和上下拉条的状态, state参数格式如下
```
{
  lockUp: false, // 上拉锁定
  lockDown: false, // 下拉锁定
  hasNext: false // 是否还有下一条
}
```
