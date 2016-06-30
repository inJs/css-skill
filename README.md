##收集的CSS小技巧

###CSS3-波浪线
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
```css
