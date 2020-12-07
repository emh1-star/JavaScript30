#### 1.Array.prototype.some()
>返回一个bool值，数组中是否至少有一个元素满足检测函数的条件

#### 2.Array.prototype.every()
>返回一个bool值，数组中是否所有的元素都满足检测函数的条件

#### 3.Array.prototype.find()
>返回1个元素，它是数组中满足检测函数条件的第一个元素
 
#### 4.Array.prototype.findIndex()
>返回1个下标，它是数组中满足检测函数条件的第一个元素的下标，就是find获得元素的下标啦

#### 5.Array.prototype.slice(begin,end)
>提取数组的一部分并返回这个新数组。这一对象是一个由 begin 和 end 决定的原数组的**浅拷贝**（包括 begin，不包括end）。原始数组不会被改变。

#### 5.Array.prototype.splice(start, deleteCount, item1, item2, ...)
>修改数组并以数组形式返回被修改的内容。此方法会改变原数组。从start位开始,删除deleteCount个元素，并插入item1, item2, ...。只有1个参数时表示从第start位开始删除全部元素。
[参数的使用例子看这里](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
