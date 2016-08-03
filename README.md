##CSS笔记

### 动画系列

> loading

```css

.overlay {
  position: fixed;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  z-index: 99;
  overflow: hidden;

  .spinner {
    margin: 200px auto;
    width: 20px;
    height: 20px;
    position: relative;
  }

  .container1 > div,
  .container2 > div,
  .container3 > div {
    width: 6px;
    height: 6px;
    background-color: #333;

    border-radius: 100%;
    position: absolute;
    -webkit-animation: bouncedelay 1.2s infinite ease-in-out;
    animation: bouncedelay 1.2s infinite ease-in-out;
    -webkit-animation-fill-mode: both;
    animation-fill-mode: both;
  }

  .spinner .spinner-container {
    position: absolute;
    width: 100%;
    height: 100%;
  }

  .circle1 {
    top: 0;
    left: 0;
  }
  .circle2 {
    top: 0;
    right: 0;
  }
  .circle3 {
    right: 0;
    bottom: 0;
  }
  .circle4 {
    left: 0;
    bottom: 0;
  }

  .container1 {
    .circle2 {
      -webkit-animation-delay: -0.9s;
      animation-delay: -0.9s;
    }

    .circle3 {
      -webkit-animation-delay: -0.6s;
      animation-delay: -0.6s;
    }

    .circle4 {
      -webkit-animation-delay: -0.3s;
      animation-delay: -0.3s;
    }

  }

  .container2 {
    -webkit-transform: rotateZ(45deg);
    transform: rotateZ(45deg);

    .circle1 {
      -webkit-animation-delay: -1.1s;
      animation-delay: -1.1s;
    }

    .circle2 {
      -webkit-animation-delay: -0.8s;
      animation-delay: -0.8s;
    }

    .circle3 {
      -webkit-animation-delay: -0.5s;
      animation-delay: -0.5s;
    }

    .circle4 {
      -webkit-animation-delay: -0.2s;
      animation-delay: -0.2s;
    }
  }

  .container3 {
    -webkit-transform: rotateZ(90deg);
    transform: rotateZ(90deg);

    .circle1 {
      -webkit-animation-delay: -1.0s;
      animation-delay: -1.0s;
    }

    .circle2 {
      -webkit-animation-delay: -0.7s;
      animation-delay: -0.7s;
    }

    .circle3 {
      -webkit-animation-delay: -0.4s;
      animation-delay: -0.4s;
    }

    .circle4 {
      -webkit-animation-delay: -0.1s;
      animation-delay: -0.1s;
    }
  }

  @-webkit-keyframes bouncedelay {
    0%, 80%, 100% {
      -webkit-transform: scale(0.0)
    }
    40% {
      -webkit-transform: scale(1.0)
    }
  }

  @keyframes bouncedelay {
    0%, 80%, 100% {
      transform: scale(0.0);
      -webkit-transform: scale(0.0);
    }
    40% {
      transform: scale(1.0);
      -webkit-transform: scale(1.0);
    }
  }
}

```

### 形状系列

> 波浪线

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
    background-image: -moz-radial-gradient(#FFF 0, #FFF 2px, #FFF 3px, #AFAEAE 2px, transparent 5px, transparent);
    background-image: radial-gradient(#FFF 0, #FFF 2px, #FFF 3px, #AFAEAE 2px, transparent 5px, transparent);
    
    background-size: 10px 10px;
    background-position: 0 10px;
    /* 旋转 */
    -moz-transform: rotate(-180deg);
    -o-transform: rotate(-180deg);
    -webkit-transform: rotate(-180deg);
    transform: rotate(-180deg);
}
```

> 圆形

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

> 钩子

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

### 居中系列

> `margin:0 auto;`
> parent element: `text-align: center;` target element: `display: inline-block; *display:inline;/*兼容低版本IE*/`
> 浮动居中：

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

> 绝对定位居中：

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

> 垂直居中

```css
.outer {
    display: table-cell;
}

.inner {
    vertical-align: middle;
}
```

### 清除浮动

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

### CHROME 默认样式 RESET

1. `input[type=number]`时去掉上下小箭头
```
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none !important;
  margin: 0;
}
```

1. `input`、`textarea`、`select` 自动填充（eg. 记住密码等）时, 去掉黄色背景
```
input:-webkit-autofill, 
textarea:-webkit-autofill, 
select:-webkit-autofill {
    -webkit-box-shadow: 0 0 0 1000px white inset;
}
```