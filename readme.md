# 一面
- ### 写一个左边img右边消息的布局
使用flex写
使用float写
使用绝对布局写
- ### 多行文本省略号
###### 单行
```js
white-space:nowrap;//不换行
text-overflow:ellipsis;//省略号
overflow:hidden;
```
###### 多行
```js
display:-webkit-box;//必须
-webkit-box-orient:vertical;//排列方式，必须
-webkit-line-clamp:3;//行数
text-overflow:ellipsis;
```
display: -webkit-box;-webkit-box-orient: vertical;-webkit-line-clamp: 3;
1.-webkit-line-clamp用来限制在一个块元素显示的文本的行数。 为了实现该效果，它需要组合其他的WebKit属性。常见结合属性： 
2.display: -webkit-box; 必须结合的属性 ，将对象作为弹性伸缩盒子模型显示 。 
3.-webkit-box-orient 必须结合的属性 ，设置或检索伸缩盒对象的子元素的排列方式 。
- ### 可以继承的css元素
不可继承的：display、margin、border、padding、background、height、min-height、max- height、width、min-width、max-width、overflow、position、left、right、top、 bottom、z-index、float、clear、table-layout、vertical-align、page-break-after、 page-bread-before和unicode-bidi。

所有元素可继承：visibility和cursor。

内联元素可继承：letter-spacing、word-spacing、white-space、line-height、color、font、 font-family、font-size、font-style、font-variant、font-weight、text- decoration、text-transform、direction。

块状元素可继承：text-indent和text-align。

列表元素可继承：list-style、list-style-type、list-style-position、list-style-image。

表格元素可继承：border-collapse。
可继承就是父节点设置了这个属性后，子节点就可以继承他的属性
- ### inline-block布局的问题（空白间隙）
这是因为字符占有一定的空间，导致了空白位置，设置
```js
letter-spacing:-3px;
font-size:0;
```
可以解决。
- ### 前端数据本地缓存的方式
###### 1、cookie
###### 2、localStorage
###### 3、sessionStorage
- ### storage如何为缓存的数据加上时间失效限制
新建一个关于时间的字段，在每次取值的时候与当前的时间做减法，然后与失效时间做判断。
- ### instanceof的原理
instanceof是基于继承的方式进行判断，将left的__proto__和右边的prototype进行===的比较。
- ### node中继承会有`__proto__`吗
是的，node中继承也有__proto__
- ### 手写Promise.All，并且在这个All中加一个超时时间
1、使用setTimeout方式，在一个promise.all中设置。
2、将setTimeout封装成promise，然后使用promise.race来输出最快的promise。
- ### 判断一个对象是正则对象（判断类型）
###### 1、instanceof
内部使用原型链的方式进行比较。
所以必须是引用类型，不可以是基本类型。
但是！！如果使用new创建的string为对象（引用类型）
###### 2、typeof
只能对基本类型进行判断，对引用类型（Array、RegExp）返回object
###### 3、constructor
```js
str.constructor == String    //true
arr.constructor == Array     //true
```
###### 4、toString
```js
Object.prototype.toString.call(arr)      //"[object Array]"
Object.prototype.toString.call(str)      //"[object String]"
```
###### 5、原型链比较__proto__
```js
str.__proto__ == String.prototype      //true
arr.__proto__ == Array.prototype      //true
```
- ### typeof的局限
- ### react写一个组件，这个组件可以监听到子组件的click或者hover事件
```js
        document.addEventListener('click', function(e){
            console.log(e.target.className)
        })
```
- ### 使用for in会出现什么问题
```js
Array.prototype.is = true;
var a = [1,2];
for(var i in a) {
  console.log(a[i]);
}
 //1
 //2
 //true

//所以数组的遍历中千万不要用for in，我们一般对对象的遍历使用。同时上面的i变量是string，并不是number
```
# 二面
- ### 学过算法吗，解释一下树，平衡树，搜索树
- ### 用过vuex吗，说一下都由哪些部分构成，动作在action和mutition哪个里面完成，哪个可以异步，为什么？
- ### 如果让你设计一个dialog，你会如何设计他的props
- ### 了解过setIntervar和setTimeout吗？可以用setTimeout实现一个setInterval吗？
- ### 做过小程序开发，小程序都有哪些生命周期？
- ### 使用taro开发小程序有哪些体会？
- ### 说说你常用的webpack loader
- ### CSS实现一个梯形
- ### 说说跨域方式？
- ### 说说前端优化方式？
- ### setTimeout+promise看输出问题
- ### 设计一个计算器，可以输入数字并进行加减。
- ### 给定一个字符串，输出重复第二多的字符。
