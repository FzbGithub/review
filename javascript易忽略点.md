### 1.js 属于弱语言，其变量遵循字母、$、_组合，大小写敏感
```
var a= 1234;
var a; 
console.log(a); //1234
// 变量重复声明，该变量的值不会丢失
```
```
// 声明无值的变量，其值是默认的undefined
var name;
console.log(name); // undefined
```
1. let、var都可声明的变量，唯一的区别就是作用域的范围，let的作用域仅在它所在的块中，var的作用域是包围它的函数
2. const 声明的变量，也是块作用域变量，其作用域也是在其所在的块中，但是const声明的变量是常量，必须得赋值，并且
   该值是只读的引用，只能赋值一次，不赋值或者多次赋值都会报错，值得注意的是常量的对象属性是可以改变的
   ```
   const name= '1234';
   name= '456' // 多次赋值报错：error
   const test; // 首次不赋值报错： error
   const some= {name:'2344'}
   some.name= 'change' // const是常量，常量的对象对其属性多次赋值不会报错
   ```
3. static、final在js中貌似不能用来声明变量的，也没有这几个声明的关键字，如有，后期改正
