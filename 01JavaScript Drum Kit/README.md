# JavaScript Drum Kit
>用户点击键盘上的A,S,D,F,G,,H,J,K,L键，发出不同的声音。
### 1.html
每个键的html结构如下，重点是为每个盒子设置自定义属性data-key,值为`<kbd>`标签内的字母的keycode。  
创建9个`<audio>`标签用于播放声音，为其设置data-key属性。  
`<kbd>`为行标签,定义键盘文本,表示文本是从键盘输入的，这里要display:block。

```
<div data-key="" class="key">
  <kbd>A/S/...</kbd>
  <span></span>  
</div>
```
### 2.css
##### 元素的transition属性
transition: property duration timing-function delay;
* property: 指定元素需要过渡效果的属性名称
* duration: 过渡效果的完成时间
* timing-function: 指定transition效果的转速曲线
* delay: 定义transition效果开始的时候

##### 元素的transform属性
这个属性允许你将元素旋转，缩放，移动，倾斜等

### 3.JS
1)为window绑定keydown事件，回调函数为playSound，键盘按下时发出相应的声音，样式做出改变。 
```
window.addEventListener('keydown',playSound);
```
2)获取到dom内的所有按键元素
```
const keys=document.querySelectorAll(`.key`);
```
3)为每个键绑定transitionEnd事件，回调函数为removeTransform，传给它的参数是TansitionEvent，键盘松开时，样式回归正常。
```
keys.forEach(key=>{
     key.addEventListener("transitionend",removeTransform);
 });
```
4)playSound()，播放声音，改变样式（尺寸变大，border-color和box-shadow变化）。  

通过keyBoardEvent获得用户所按按键的keyCode属性，找到dom中data-key属性值与它相等的audio，播放。  
通过keyBoardEvent获得用户所按按键的keyCode属性，找到dom中data-key属性值与它相等的div，添加playing类名。  

5）removeTransoform()，当声音播放一次后，样式应该回归正常，当transitionend时要取消div上的playing类名。  
**注意:** 当按键按下时，由于过渡属性不止一个，transitionEnd会发生多次，这里应该判断，只去掉一次即可。
