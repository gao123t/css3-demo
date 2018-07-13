日常整理的 css3特效。
## 一.卡片翻转特效
[页面效果访问地址跳转](http://htmlpreview.github.io/?https://github.com/gao123t/css3-demo/blob/master/cardFlip.html)
效果呈现：
![效果呈现](static/images/卡片翻转特效.gif)
### 特效bug 整理：
#### 1. 跳转过程中背面会显示出来的问题
**场景**
![跳转过程中背面显示的问题](static/images/翻转特效应用中的bug场景.gif)
**解决方案**
>通过在更改正面背面的透明度。正面的透明度设置为1，背面的透明度设置为0。即可解决此问题。