### 关于数组的一些方法
***注意：每个函数的第一个function参数都要有返回值***
##### 1.Array.prototype.filter()
filter()返回一个新数组，其中的元素由function决定。cunction是用来测试数组的每个元素的函数。返回 true 表示该元素通过测试，保留该元素，false 则不保留。
```
arr.filter(function(currentElement,index,arr), thisValue)
```
currentElement是遍历过程中数组当前正在处理的元素。
##### 2.Array.prototype.map()
map()返回一个新数组,新元素是对原数组的每个元素用function处理之后的元素，俩数组length相同。
```
arr.map(function callback(currentValue, index, array){}, thisArg])
```
currentValue是数组中正在处理的当前元素。
##### 3.Array.prototype.sort()
sort()将原数组排序后返回,如果省略参数，元素将被转换成字符串，按照unicode编码由小到大排序。如果有compareFunction，数组将根据`compareFunction(a,b)`的返回值进行排序。
返回值>0,b在前，返回值<0，a在前。
```
arr.sort([compareFunction])
```
如，将数组中的数字由大到小排列
```
var arr=[2,8,90,15,6,25];
arr.sort((a,b)=>{
if(a>b) 
  return -1;
else 
  return 1;
});
console.log(arr);
```
##### 4.Array.prototype.reduce()
函数的累计处理。对原数组的每个值执行一次callback函数(升序执行),每次的返回值都和上一次的值汇总，最终返回一个值
```
arr.reduce(callback(accumulator, currentValue, index, array), initialValue])
```
**accumulator是数组当前遍历过程中已经得出的累加值，当遍历完成后，它就是最终的返回值！**
initialValue是第一次调用 callback函数时的第一个参数accumulator的值。 如果没有提供初始值，则将使用数组中的第一个元素。 在没有初始值的空数组上调用 reduce 将报错。
>注意：如果没有提供initialValue，reduce 会从索引1的地方开始执行 callback 方法(因为索引0的值被设为了初始值)，跳过第一个索引。如果提供initialValue，从索引0开始。
