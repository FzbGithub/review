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
4. js 的数据类型有字符串String、数字Number、布尔值Boolean、数组Array、对象Object、Null、Undefined
   ```
   var name= new String();
   var x   = new Number();
   var y   = new Boolean(true);
   var z   = new Array();
   var t   = new Object();
   ```
   js 属于弱语言，声明变量后，根据赋值确定变量的类型，声明变量未赋值，其值在编译时会自动赋值为undefined,变量均为
   对象，当声明一个变量时，就创建了一个对象
5. js 变量用new赋值会创建一个连接到该变量prototype成员的新对象，同时该变量如果是对象或者数组等引用型变量的话，里面的
   this将绑定到这个新的对象上，其实例话对象instanceof 指向的是引用型的变量Objec,否则则指向变量的本身，而如果变量没有
   用new 赋值，返回的是该变量的默认值或者返回值
   ```
   function single () {
      var a= 'abc';
      return a;
   }
   function testWithReturn () {
      var t= [1,2,3];
      return t;
   }
   var single= single();
   var testSingle= new single();
   var test = testWithReturn();
   var newTest = new testWithReturn();
   console.log(single); // 'abc'
   console.log(testSingle); // [object object]
   console.log(testSingle instanceof single); // true
   console.log(test); // [1,2,3]
   console.log(newTest); // [1,2,3]
   console.log(test instanceof Array); // true
   // 返回的是引用型类型，有没有new,都得到引用类型，有了new,也不返回引用的prototype
   console.log(newTest instanceof Array); // true
   console.log(newTest instanceof testWithReturn); // false
   ```
6. js变量的划分为原始型和引用型，也叫字面型变量和引用型变量，字面型变量包括Undefined,Unll,String,Number,Boolean,
   它的值直接存储在变量访问的位置（栈），引用型变量包括Array,Objec,Function,它的值存储在变量值的一个指针，指向存储
   对象的内存处（堆）
