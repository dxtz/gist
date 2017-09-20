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