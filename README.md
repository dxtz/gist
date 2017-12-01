css
------------------
移动端使用click绑定，点击时在绑定元素上会闪一下，并出现一个半透明背景，解决办法：给该元素加一个样式，如下
```CSS
-webkit-tap-highlight-color: rgba(0,0,0,0); // 属性值：transparent 的效果一样
```

js判断函数是否存在
------------------
```javascript
    if ( typeof funcName === "function" ) {
        alert("is function or exist");
    } else {
        alert("isn't function or not exist");
    }
```

php获得上一个月有多少天
--------------------
```php
    echo date('t', strtotime('last month'));
    //或者
    echo date('t', strtotime('-1 month'));
```

css的box-shadow
-------------------
**外阴影**: box-shadow: X Y Spx Rpx color; (*X轴 Y轴 阴影半径 阴影模糊值 阴影颜色*)  
**内阴影**: box-shadow: X Y Spx Rpx color inset; (比外阴影多一个属性`inset`)  
还可以设置多重阴影，例如：
```CSS
box-shadow: 0 0 8px 2px rgba(0, 0, 0, 0.5),
            -4px 0 0 0 #000,
            0 6px 4px 0 red,
            0 0 5px 5px green inset;
```
`box-shadow`使用于盒模型，设置文字阴影可以使用`text-shadow`，使用方法与`box-shadow`一致

css更改伪元素的值(::after, ::before)
--------------
```html
<div class="class" data-value="test"></div>
```
```css
.class::before {
    content: attr(data-value);
}
// 伪元素的值为："test"
```


禁止屏幕滑动
----------------
```JS
var mo = function(e){e.preventDefault();};
function stop() {  //禁止
    document.body.style.overflow = 'hidden';
    document.addEventListener('touchmove', mo, false);
}
function move() {   //取消禁止
    document.body.style.overflow = '';
    document.removeEventListener('touchmove', mo, false);
}
```

另一种禁止滑动的方法
-------------------
```JS
var scrollTop;
// 禁止滑动
scrollTop = document.scrollingElement.scrollTop;
document.body.style.position = 'fixed';
document.body.style.top = -scrollTop + 'px';

// 取消禁止
document.body.style.position = '';
document.scrollingElement.scrollTop = scrollTop;
```

简单设置跨域(Nginx)
----------------
```
add_header Access-Control-Allow-Origin *; //(*可设置具体IP地址)
add_header Access-Control-Allow-Methods GET,POST,DELETE,OPTIONS,PUT; //也可不加上这行
```

VUE-ROUTE-TITLE
----------------------
```JS
let setDocumentTitle = function (title) {
  document.title = title
  let ua = navigator.userAgent
  if (/\bMicroMessenger\/([\d.]+)/.test(ua) && /ip(hone|od|ad)/i.test(ua)) {
    var i = document.createElement('iframe')
    i.src = '/favicon.ico'
    i.style.display = 'none'
    i.onload = function () {
      setTimeout(function () {
        i.remove()
      }, 9)
    }
    document.body.appendChild(i)
  }
}
router.afterEach(routes => {
  typeof routes.meta.title !== undefined && setDocumentTitle(routes.meta.title)
})
