#### 1.CSS变量的声明和使用
  ```
  :root{
  --variablename:initvalue
  }
  ```
  :root伪元素代表html元素，其中可定义全局变量，将变量看作html的属性。也可为某元素定义局部变量。用`var(--variablename)`使用变量。
  
#### 2.为全局变量赋值
```
document.documentElement.style.setProperty(变量名,值);
```
`document.documentElement`等同于`document.querySelector('html')`
#### 3.dataset自定义属性对象
  使用`data-属性名`在标签中可以定义自定义属性，可以通过`元素.dataset.属性名`获取值
#### 4.为什么需要绑定两个事件？
```
inputs.forEach(input => input.addEventListener('change', handleUpdate));
inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));
```
 因为change只有在滑动结束时才触发，这里需要的是鼠标滑动时也触发。
  
