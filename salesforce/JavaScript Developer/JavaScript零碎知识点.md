```javascript

// 移除数组第一个元素
arr.shift();
// 将新项目添加到数组的开头：
arr.unshift(8);

// 移除数组最后一个元素
arr.pop(); 
// 将新项目添加到数组的结尾：
arr.push(8);

// 方法以新的数组对象，返回数组中被选中的元素。(选择从给定的 *start* 参数开始的元素，并在给定的 *end* 参数处结束.
arr.slice(1,3) 

// splice() 方法用于添加或删除数组中的元素。
// 参数1 index 必须 start index
// 参数2 deleteCount 可选 规定应该删除多少元素 0:不删除 
// 参数3 *item1, ..., itemX* 可选。要添加到数组的新元素
// 返回被删除元素的数组
arr.splice(3, 1, 'May');

// 方法用于连接两个或多个数组
arr.concat(arr1, arr2) 

// 使用 reduce 累加
// https://blog.csdn.net/weixin_41229588/article/details/106858685
arr = [1, 2, 3]
// reduce的两个参数callback函数，initialValue
//  callback函数的四个参数 分别为累计值、当前元素、当前索引、原数组
const sum = arr.reduce((acc, current) => acc + current, 100)
console.log(sum) // 106

[1, 2, 3, 4].reduce((x, y) => console.log(x, y));
// 1 2
// 1 undefined 3
// 1 undefined 4
// undefined
```



----

prototype __proto__

①只要创建了一个函数，该函数的原型对象也随之同时被创建出来，原型对象中的属性和方法被经由其相对应的构造函数所创建的实例所共享

②每个函数在创建之后都会获得一个prototype的属性，这个属性指向该函数的原型对象

③每个对象的__proto__属性都指向其构造函数的原型

----

console.log({ a: 'one', b: 'two', a: 'three' }); //  b: 'two', a: 'three'

键名相同 后面的覆盖前面的

---

let str1 = 'test'
let str2 = String('test')
let str3 = new String('test')

console.log(typeof str1);//string
console.log(typeof str2);//string
console.log(typeof str3);//object

---

const bigInt = 1234567890123456789012345678901234567890n;

---

try … catch構文でcatchするための引数として渡されるエラーオブジェクトの2つの主なプロパティは何ですか？

名前とメッセージ

---

1.所有的Falsy值，当进行逻辑判断时均为false。Falsy值包括：false、undefined、null、NaN、”"、正负0。
2.其余所有的值均为Truthy，当进行逻辑判断时均为true。值得注意的是，Infinity、空数组、”0″都是Truthy值。

---

let x = y = 10; // x=10,y=10

---

```javascript
var a= b= 0
var i= j= 10;

a= i++; // i先赋值再自加
console.log('a:',a) // 10
console.log('i:',i) // 11

b= ++j; // j先自加再赋值
console.log('b:',b) // 11
console.log('j:',j) // 11
```

---

parseInt() 函数可解析一个字符串，并返回一个整数。

- 如果 string 以 "0x" 开头，parseInt() 会把 string 的其余部分解析为十六进制的整数。

- 如果 string 以 0 开头，那么 ECMAScript v3 允许 parseInt() 的一个实现把其后的字符解析为八进制或十六进制的数字。

- 如果 string 以 1 ~ 9 的数字开头，parseInt() 将把它解析为十进制的整数。

- **注意：** 只有字符串中的第一个数字会被返回。

  **注意：** 开头和结尾的空格是允许的。

  **注意：**如果字符串的第一个字符不能被转换为数字，那么 parseInt() 会返回 NaN。

  **注意：**在字符串以"0"为开始时旧的浏览器默认使用八进制基数。ECMAScript 5，默认的是十进制的基数。

  ```javascript
  parseInt("10")  // 10
  parseInt("10.33")  // 10
  parseInt("34 45 66")  // 34
  parseInt(" 60 ")  // 60
  parseInt("40 years")  // 40
  parseInt("He was 40")  // NaN
  parseInt("10",10) // 10
  parseInt("010") // 10
  parseInt("10",8) // 8
  parseInt("0x10") // 16
  parseInt("10",16) // 16
  ```

---

### Promise 对象有以下两个特点:

1、对象的状态不受外界影响。Promise 对象代表一个异步操作，有三种状态：

- pending: 初始状态，不是成功或失败状态。
- fulfilled: 意味着操作成功完成。
- rejected: 意味着操作失败。

2、无法取消 Promise，一旦新建它就会立即执行，无法中途取消。

```javascript
var myFirstPromise = new Promise(function(resolve, reject){
    //当异步代码执行成功时，我们才会调用resolve(...), 当异步代码失败时就会调用reject(...)
    setTimeout(function(){
        resolve("成功!"); //代码正常执行！
    }, 250);
});
 
myFirstPromise.then(function(successMessage){
    document.write("Yay! " + successMessage);
});
```

Promise.all()

```javascript
var p = Promise.all([p1,p2,p3]);
// Promise.all 方法接受一个数组作为参数，p1、p2、p3 都是 Promise 对象的实例。（Promise.all 方法的参数不一定是数组，但是必须具有 iterator 接口，且返回的每个成员都是 Promise 实例。）

// p 的状态由 p1、p2、p3 决定，分成两种情况。

// （1）只有p1、p2、p3的状态都变成fulfilled，p的状态才会变成fulfilled，此时p1、p2、p3的返回值组成一个数组，传递给p的回调函数。
// （2）只要p1、p2、p3之中有一个被rejected，p的状态就变成rejected，此时第一个被reject的实例的返回值，会传递给p的回调函数。

// 生成一个Promise对象的数组
var promises = [2, 3, 5, 7, 11, 13].map(function(id){
  return getJSON("/post/" + id + ".json");
});
 
Promise.all(promises).then(function(posts) {
  // ...  
}).catch(function(reason){
  // ...
});
```

Promise.race

```javascript
// 上面代码中，只要p1、p2、p3之中有一个实例率先改变状态，p的状态就跟着改变。那个率先改变的Promise实例的返回值，就传递给p的返回值。
var p = Promise.race([p1,p2,p3]);
```

Promise.resolve 方法，Promise.reject 方法

有时需要将现有对象转为Promise对象，Promise.resolve方法就起到这个作用。

```javascript
var p = Promise.resolve('Hello');
console.log(p) // Promise {<fulfilled>: 'Hello'}
p.then(function (s){  console.log(s) });// Hello
```

---

排序：

```javascript
const arr = [7、3、400、10];
// xxx.sort(function)
// 升序
arr.sort((a, b) => a – b); 
// 降序
arr.sort((a, b) => b – a);
```

```javascript
const arr = ["Banana", "Orange", "Apple", "Mango"];
// 升序
arr.sort()
// 降序
arr.reverse();
```

---

History API

`history.pushState(state, title, url)` : 无刷新的向浏览器 **历史最前方** 加入一条记录。

- `state`(any) 需要保存的数据，这个数据在触发`popstate`事件时保存在`event.state`上。
- `title`(string)：

`popstate`： 浏览器点击前进后退时触发的事件。`event.state`可以获取当前url下设置的`state`。

另外获取`pushState`中设置的`state`不一定要在`popstate`事件中获取，直接`history.state`也可以拿到。



```javascript
var next = document.getElementById('next');
var cur = document.getElementById('cur');
var page = 0;
next.onclick = function(){
  page++;
  history.pushState({page: page}, '','?page=' + page);
  //状态对象中存储当前页数
  cur.innerHTML = page;
}
window.onpopstate = function(e){
  if(e.state){
    cur.innerHTML = e.state.page;
  }else{
    cur.innerHTML = 0;
  }
}
```

---

call apply bind总结

1. call和apply会调用函数，并且改变函数内部this指向

2. call和apply传递的参数不一样，call传递参数aru1,aru2...形式 apply必须是数组形式

3. bind不会调用函数，可以改变函数内部this指向

```javascript
const person = { name: 'Lydia' };

function sayHi(age) {
    return `${this.name} is ${age}`;
}
console.log(sayHi.call(person, 21));
console.log(sayHi.bind(person, 21));
```

---

モジュールには、エクスポートするコンストラクターが含まれている必要があります。

---

Event出发顺序

```javascript
document.querySelector('.outerDiv') .addEventListener('click', displayOuterMessage, true);
document.querySelector('.innerDiv') .addEventListener('click', displayInnerMessage, true); };
// displayOuterMessage, displayInnerMessage
```

<img src="https://img-blog.csdnimg.cn/20190822171027508.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2tvdXJ5b3VzaGluZQ==,size_16,color_FFFFFF,t_70" alt="flow" style="zoom: 33%;" />

[参照文档]: (https://blog.csdn.net/kouryoushine/article/details/100019632)	"test"

- 捕获阶段capture：事件对象通过目标的祖先（windows）逐层往下遍历，直到target的父元素。这个过程就是捕获阶段。

- 目标阶段target: 事件对象在目标的时候。（at target）.如果生命bubble属性不冒泡，则事件停止传播。

- 冒泡阶段：事件对象反向（capture的反序），从目标的父元素开始往dom的祖先window传播。



  addEventListener第三个参数可以设定为ture，意思是改变触发handler的顺序。这个listener在capture阶段捕获到时间后就执行。捕获阶段是从外向内向的，所以这样的监听器就会先执行父元素的handler.

---

对象的引用

```javascript
let person = { 
    name: 'Lydia'
};
const members = [person];
person = null;
console.log(members); // [{ name: “Lydia” }]
```

> javascript和其他语言不同，其不允许直接访问内存中的位置，也就是说不能直接操作对象的内存空间. 
> 是操作对象的引用，所以引用类型的值是按引用访问的。
>
> ```person = null;``` 改变了person的引用地址
>
> 而members的引用地址没有变化。
>
> ```person = null;``` 如改成```person.name='tony';``` 
>
> 则members也会受到影响

---

eval(arg)  函数计算或执行参数。

```javascript
let s1 = '2 + 2'
let s2 = new String('2 + 2')

console.log(eval(s1)) // 4
console.log(s2) // String {'2 + 2'}
console.log(eval(s2)) // String {'2 + 2'}
console.log(s2) // '2 + 2'
console.log(eval(s2.valueOf())) // 4
```

---

JSON.stringify() 方法用于将 JavaScript 值转换为 JSON 字符串。

### 语法

```javascript
JSON.stringify(value,replacer?, space?])
```

**参数说明：**

- value:

  必需， 要转换的 JavaScript 值（通常为对象或数组）。

- replacer:

  可选。用于转换结果的函数或数组。

  如果 replacer 为函数，则 JSON.stringify 将调用该函数，并传入每个成员的键和值。使用返回值而不是原始值。如果此函数返回 undefined，则排除成员。根对象的键是一个空字符串：""。

  如果 replacer 是一个数组，则仅转换该数组中具有键值的成员。成员的转换顺序与键在数组中的顺序一样。

- space:

  可选，文本添加缩进、空格和换行符，如果 space 是一个数字，则返回值文本在每个级别缩进指定数目的空格，如果 space 大于 10，则文本缩进 10 个空格。space 也可以使用非数字，如：\t。

### 返回值：

返回包含 JSON 文本的字符串。

```javascript
JSON.stringify(new Number(3)) // '3'
```

---

Object.defineProperty(obj, prop, descriptor)接受3个参数：

- obj: 要操作的对象
- prop: 要操作的属性
- descriptor: 描述符对象。包含6个属性：configurable、enumerable、writable、value、get、set

注意：应当直接在Object构造器对象上调用此方法，而不是在任意一个Object类型的实例上调用。

https://www.cnblogs.com/nidalise/p/13296704.html

数据属性有4个描述其行为的特性：

- configurable: 能否通过delete删除属性，能否修改属性特性（注意是特性），能否修改为访问器属性，默认是true
- enumerable: 能否通过for-in遍历到该属性，默认是true
- writable: 能否修改属性值，默认是true
- value: 这个属性的数据值。读取属性值的时候，从这里读取；写入属性值得时候，把新值保存在这个位置。默认是undefined

```javascript
let person = {}
person.name // 给person添加一个数据属性，Configurable、Enumerable、Writable默认是true，Value是undefined
person.name = 'a' // Value特性被设置为'a'

Object.defineProperty(person, 'name', {
  value: 'b'
})
console.log(person.name) // b  configurable为false，writable为true时还能修改
```

访问器属性

访问器属性不包含数据值，包含一对getter和setter函数（不需要同时存在）。
访问器属性必须通过Object.defineProperty定义。访问器属性有以下四个特性：

- configurable: 能否通过delete删除属性，能否修改属性特性（注意是特性），能否修改为数据属性，默认是true
- enumerable: 能否通过for-in遍历到该属性，默认是true
- get: 在读取属性时调用的函数。默认值是undefined
- set: 在写入属性时调用的函数。默认是undefined

```javascript
let person = {}
let _name = 'a'

Object.defineProperty(person, 'name', {
  get: function () {
    return _name
  },
  set: function (newVal) {
    (newVal !== _name) && (_name = newVal)
  }
})

_name = 'b'
console.log(person.name) // b

person.name = 'c'
console.log(_name) // c
```

---

Object

- 对象的所有键名都是字符串（ES6 又引入了 Symbol 值也可以作为键名），所以加不加引号都可以。

- 如果键名不符合标识名的条件（比如第一个字符为数字，或者含有空格或运算符），且也不是数字，则必须加上引号，否则会报错。

- ```javascript
  const a = {};
  const b = { key: 'b' };
  const c = { key: 'c' };
  
  a[b] = 123;
  a[c] = 456;
  
  console.log(a); // {"[object Object]":456}
  console.log(a[b]); // 456
  console.log(a[C]); // 456
  ```

---

JavaScript 数据类型

- 值类型(基本类型)：字符串（String）、数字(Number)、布尔(Boolean)、对空（Null）、未定义（Undefined）、Symbol。
- 引用数据类型：对象(Object)、数组(Array)、函数(Function)。

---

```javascript
const myDt = new Date();
console.log(myDt + 10); // Thu Nov 18 2021 15:56:12 GMT+0900 (日本标准时间)10
```

---

Object.freeze()

- 设置Object.preventExtension()，禁止添加新属性(绝对存在)
- 设置writable为false，禁止修改(绝对存在)
- 设置configurable为false，禁止配置(绝对存在)
- 禁止更改访问器属性(getter和setter)
- `Object.isFrozen()`判断一个对象是否是冻结对象。

Object.seal()

- 设置Object.preventExtension()，禁止添加新属性(绝对存在)

- 设置configurable为false，禁止配置(绝对存在)

- 禁止更改访问器属性(getter和setter)

- 可以使用`Object.isSealed()`判断一个对象是否是封闭对象。

  

使用`Object.freeze()`冻结的对象中的现有属性是不可变的。用`Object.seal()`密封的对象可以改变其现有属性。



Object.preventExtensions()

- 让一个对象变的不可扩展，也就是永远不能再添加新的属性。
- 可以使用`Object.isExtensible()`判断一个对象是否可扩展

---

delete：

只能删除自有属性 不能删除继承属性

var data = {key1:"peo",key2:"12"};

delete data.key2; //返回true 且 data{key1:"peo"}

delete data.name; //返回true 要删除的本身就不存在

---

Which three browser specific APIs are available for developers to persist data between page loads ?

- IIFEs

- indexedDB

- localStorage.

---

方法将数据转换为 JavaScript 对象。

```javascript
// JSON.parse(text,reviver)
// text:必需， 一个有效的 JSON 字符串。
// reviver: 可选，一个转换结果的函数， 将为对象的每个成员调用此函数。
var obj = JSON.parse('{ "name":"runoob", "alexa":10000, "site":"m.runoob.com" }');
JSON.parse('"foo"'); // 'foo'

var text = '{ "name":"Runoob", "initDate":"2013-12-14", "site":"m.runoob.com"}';
var obj = JSON.parse(text, function (key, value) {
    if (key == "initDate") {
        return new Date(value);
    } else {
        return value;
}});
```

---

```javascript
// 值类型传入方法后 改变不会影响到参数元
function changeValue(param) {
 param =5;
}
let a =10;
let b =100;
changeValue(b);
console.log( a+ " - "+ b) // 10 - 100

// 引用类型传入方法后 改变会影响到参数元
function changeValue(param) {
 param.age =5;
}
let a = {age:10};
let b = {age:100};
changeValue(b);
console.log( a.age+ " - "+ b.age) // 10 - 5
```

---

```javascript
参数1 searchString
参数2 position 开始位置
'1abcd1'.includes('a',1) // true
'1abcd1'.includes('a',2) // false
```

---

```javascript
// 循环可以中改变数据 
// 删除数组元素 循环次数变少
let array = [1, 2, 3, 4, 4, 5, 4, 4];
for (let i =0; i < array.length; i++){
if (array[i] === 4) {
  console.log(i)
  console.log('before',array)
	array.splice(i, 1);
  console.log('after',array)
	}
}
console.log(array) // [1, 2, 3, 4, 5, 4]
```

---

```javascript
let sayHello = () => {
console.log ('Hello, world');
};
// setTimeout 调用function时不能带参数 不能带(): 例如不能：setTimeout(sayHello(), 120)
setTimeout(sayHello, 120) // Hello, world

sayHello = (name,age) => {
console.log ('Hello '+ name +','+ age +' old');
};
// setTimeout 调用function有参数时在后面追加
setTimeout(sayHello, 120,'tony',18) // Hello tony,18 old
```

---

```javascript
// true与数字加减时候为1
console.log(true + 3 + '100' + null) // 4100null
// false与数字加减时候为0
console.log(false + 3 + '100' + null) // 3100null
```

---

```javascript
let first = 'who';
let second = 'what';
try{
  console.log('try1')
	try{
    console.log('try2')
		throw new error('Sad trombone');
	}catch(err){
    console.log('catch2')
		first ='Why';
    // throw err
	}finally {
    console.log('finally2')
		second ='when';
  }
}
catch(err) {
  console.log('catch1')
	second ='Where';
}
console.log('first:',first)
console.log('second:',second)

// 因为catch2没有throw 所有没有进catch1
//log 
// >3 try1
// >6 try2
// >9 catch2
// >12 finally2
// >20 first: Why
// >21 second: when
```

---

```javascript
// 记录执行的时间
console.time('performance')
// logic function
console.timeEnd('performance')
console.timeLog() // performance: 29473.177978515625 ms

```

Basic DOM data type

- document
- node
- nodelist
- namedNodemap
- element
- attribute

---

https://javascript.info/debugging-chrome

---

Node.js有很多core模块

- The Node.js events module
- The Node.js fs module
- The Node.js http module
- The Node.js os module
- The Node.js path module

...还有很多可参照 https://flaviocopes.com/node-core-modules/

---

```javascript
new Promise((resolve, reject )) => {
	setTimeout(() => reject(console.log(3)), 1000)
})
.catch(() => 
console.log(4);
);
```

---

```javascript
function getPersonInfo(one, two, three) {
	console.log(one);
	console.log(two);
	console.log(three);
}
const person = 'Lydia';
const age = 21;
getPersonInfo`${person} is ${age} years old`; //  ["", " is ", " years old"] "Lydia" 21

```

---

```javascript
typeof(new Boolean(false)) // 'object'
if(new Boolean(false)) console.log('a') // a
```

---

```javascript
const numbers = [1, 2, 3];
numbers[10] = 11;
console.log(numbers); //  [1, 2, 3, empty × 7, 11]
```

---

```javascript
console.log(JSON.stringify([new Number(3), new String('false'), new
Boolean(false)]));// '[3,"false",false]'
```

​	
