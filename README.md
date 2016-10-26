# JavaScript---skiller
##JavaScript获取各种浏览器可见窗口大小

###基础语法

* 网页可见区域宽：document.body.clientWidth
* 网页可见区域高：document.body.clientHeight

* 网页可见区域宽：document.body.offsetWidth（包括边线宽）
* 网页可见区域高：document.body.offsetHeight（包括边线高）

* 网页正文全文宽：document.body.scrollWidth
* 网页正文全文高：document.body.scrollHeight

* 网页被卷去的高：document.body.scrollTop
* 网页被卷去的左：document.body.scrollLeft

* 网页正文部分上：window.screenTop
* 网页正文部分左：window.screenLeft

* 屏幕分辨率的高：window.screen.height
* 屏幕分辨率的宽：windwo.screen.width

* 屏幕可用工作区高度：window.screen.availHeight
* 屏幕可用工作区宽度：windwo.screen.availWidht

###HTML精准定位

* scrollHeight:获取对象的滚动高度
* scrollLeft: 设置或获取位于对象左边界的窗口中目前可见内容的最左端之间的距离
* scrollTop:设置或获取位于对象最顶端和窗口中可见内容的最顶端之间的距离
* scrollWidth:获取对象的滚动宽度

* offsetHeight:获取对象相对于版面或由父坐标 offsetParent属性指定的父坐标的高度
* offsetLeft:获取对象相对于版面或由offsetParent属性指定的父坐标的计算左侧位置
* offsetTop:获取对象相对于版面或由offsetTop属性指定的父坐标的计算顶端位置

* event.clientX:相对于文档的水平坐标
* event.clientY:相对于文档的垂直坐标

* event.offsetX:相对于容器的水平坐标
* event.offsetY:相对于容器的垂直坐标

* document.documentElement.scrollTop:垂直方向滚动的值

* event.clientX+document.documentElement.scrollTop:相对于文档的水平坐标+垂直方向滚动的量

###例子
####普通

* IE6/7/8：对于没有doctype声明的页面里可以使用 document.body.scrollTop 来获取 scrollTop 高度；
* 对于有doctype声明的页面则可以使用 document.documentElement.scrollTop；
* Safari：safari 比较特别，有自己获取scrollTop的函数 ： window.pageYOffset ；
* Firefox：火狐等等相对标准些的浏览器就省心多了，直接用 document.documentElement.scrollTop ；
* var scrollTop = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop;

####有w3c标准
>（在页面中添加这行标记的话）
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">


#####在IE中：

* document.body.clientWidth ==> BODY对象宽度
* document.body.clientHeight ==> BODY对象高度
* document.documentElement.clientWidth ==> 可见区域宽度
* document.documentElement.clientHeight ==> 可见区域高度

#####在FireFox中：

* document.body.clientWidth ==> BODY对象宽度
* document.body.clientHeight ==> BODY对象高度
* document.documentElement.clientWidth ==> 可见区域宽度
* document.documentElement.clientHeight ==> 可见区域高度

#####在Opera中：

* document.body.clientWidth ==> 可见区域宽度
* document.body.clientHeight ==> 可见区域高度
* document.documentElement.clientWidth ==> 页面对象宽度（即BODY对象宽度加上Margin宽）
* document.documentElement.clientHeight ==> 页面对象高度（即BODY对象高度加上Margin高）

####没有定义W3C的标准，则
#####IE为：

* document.documentElement.clientWidth ==> 0
* document.documentElement.clientHeight ==> 0

#####FireFox为：

* document.documentElement.clientWidth ==> 页面对象宽度（即BODY对象宽度加上Margin宽）
* document.documentElement.clientHeight ==> 页面对象高度（即BODY对象高度加上Margin高）

#####Opera为：

* document.documentElement.clientWidth ==> 页面对象宽度（即BODY对象宽度加上Margin宽）
* document.documentElement.clientHeight ==> 页面对象高度（即BODY对象高度加上Margin高）

####判断浏览器的类型：

    var ua = navigator.userAgent.toLowerCase ();
    var os = new Object();
    os.isFirefox = ua.indexOf ("gecko") != -1;
    os.isOpera = ua.indexOf ("opera") != -1;
    os.isIE = !os.isOpera && ua.indexOf ("msie") != -1;
    
    
    
