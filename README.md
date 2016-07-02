##CSS笔记

###CSS-形状系列

1. 波浪线

```css
.wavy {
    height: 5px;
}

.wavy::after {
    content: '';
    display: block;
    height: 4px;
    width: 100%;
    /* 画圆 */
    background-image: -webkit-radial-gradient(#FFF 0, #FFF 2px, #FFF 3px, #AFAEAE 2px, transparent 5px, transparent);
    background-image: -moz-radial-gradient(-webkit-radial-gradient(#FFF 0, #FFF 2px, #FFF 3px, #AFAEAE 2px, transparent 5px, transparent);
    backgorund-image: radial-gradient(-webkit-radial-gradient(#FFF 0, #FFF 2px, #FFF 3px, #AFAEAE 2px, transparent 5px, transparent);
    
    background-size: 10px 10px;
    background-position: 0 10px;
    /* 旋转 */
    -moz-transform: rotate(-180deg);
    -o-transform: rotate(-180deg);
    -webkit-transform: rotate(-180deg);
    transform: rotate(-180deg);
}
```

1. 圆形

```css
.circle {
    display: inline-block;

    width: 80px;
    height: 80px;
    background-color: #32B16C;
    -moz-border-radius: 50px;
    -webkit-border-radius: 50px;
    border-radius: 50px;
}
```

1. 钩子

```css
.hanger {
    display: inline-block;
    width: 27px;
    height: 3px;
    background-color: #FFF;
    line-height: 0;
    font-size: 0;
    vertical-align: middle;
    -webkit-transform: rotate(41deg);
}

.hanger::after {
    content: '/';
    display: block;
    width: 40px;
    height: 3px;
    background-color: #FFF;
    -webkit-transform: rotate(-86deg) translateY(186%) translateX(50%);
}
```

###居中系列

1. `margin:0 auto;`
1. parent element: `text-align: center;` target element: `display: inline-block; *display:inline;/*兼容低版本IE*/`
1. 浮动居中：
```css
.pagination {
    position: relative;
    float: left;
    width: 100%;
    overflow: hidden;
} 
.pagination ul {
    position: relative;
    clear: left;
    float: left;
    left: 50%;
    text-align: center;
} 
.pagination li {
    position: relative;
    line-height: 25px; 
    margin: 0 5px;
    display: block;
    float: left;
    right: 50%
}
```
1. 绝对定位居中：
```css
.center { /*水平居中*/
    position: absolute;
    width: 30px; /*指定宽度值*/
    left: 50%;
    margin-left: 15px; /*宽度值的一般*/
}
.center { /*垂直居中*/
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
```

## 清除浮动

```css
.clear {
    zoom: 1;
}
.clear::after {
    display: block;
    content: '任意字符';
    clear: both;
    height: 0; /*line-height: 0;与height: 0; 取一即可。*/
    line-height: 0;
    visibility: hidden;
}
```