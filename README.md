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