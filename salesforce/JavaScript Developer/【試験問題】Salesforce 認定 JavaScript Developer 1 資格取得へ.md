## 問5

try … catch構文でcatchするための引数として渡されるエラーオブジェクトの2つの主なプロパティは何ですか？

A.名前とスタックトレース
B.タイトルとメッセージ
C.タイトルとスタック
D.名前とメッセージ

答え

D.名前とメッセージ



## 問6

下記のコードを実行するとどれが出力されますか？

```
let s_prim = 'foo'
let s_obj = new String(s_prim) // 
console.log(typeof s_prim)
console.log(typeof s_obj)
console.log(typeof s_obj) String {'2 + 2'}
```

A.String,Object
B.String,String
C.Object,Object
D.String,Class

答え

A.String,Object

>  众所周知使用 new 关键字定义的都是对象。所以可以清楚的知道str3是一个对象，对于str1只是定义了一个变量，然后做了赋值操作，str2就是使用类似于Number、Boolean等方法的类型转换。最终返回的str2也只是是一个字符串。
>
> ```javascript
> let str1 = 'test'
> let str2 = String('test')
> let str3 = new String('test')
> 
> console.log(typeof str1);//string
> console.log(typeof str2);//string
> console.log(typeof str3);//object
> ```



## 問8

BigIntとして値をインスタンス化するにはどうすればよいですか？

A.何もありません。値が（（2 ^ 53）-1）より大きい場合、JavaScriptは自動的に数値をBigIntにキャストします。
B. const bigInt = BigInt.parse（1234567890123456789012345678901234567890）;
C. const bigInt = 1234567890123456789012345678901234567890n;
D. const bigInt = BigInt.parse（ ‘1234567890123456789012345678901234567890’）;

答え

C. const bigInt = 1234567890123456789012345678901234567890n;



## 問9

下記のコードを実行するとどれが出力されますか？

```
const obj = { a: 'one', b: 'two', a: 'three' };
console.log(obj);
```

A: { a: “one”, b: “two” }
B: { b: “two”, a: “three” }
C: { a: “three”, b: “two” }
D: SyntaxError

答え

C: { a: “three”, b: “two” }



## 問10

下記のコードを実行するとどれが出力されますか？

```
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}

const member = new Person('Lydia', 'Hallie');

Person.getFullName = function() {
    return `${this.firstName} ${this.lastName}`;
};

console.log(member.getFullName());
```

A: TypeError
B: SyntaxError
C: Lydia Hallie
D: undefined

答え

A: TypeError

JavaScriptでは、関数はオブジェクトであるため、メソッドgetFullNameはコンストラクター関数オブジェクト自体に追加されます。 そのため、Person.getFullName()を呼び出すことはできますが、member.getFullNameはTypeErrorをスローします。

すべてのオブジェクトインスタンスでメソッドを使用できるようにする場合は、そのメソッドをプロトタイププロパティに追加する必要があります。

```
Person.prototype.getFullName = function（）{
    return $ {this.firstName} $ {this.lastName};
};
or
member.__proto__.getFullName = function（）{
    return $ {this.firstName} $ {this.lastName};
};
```



## 問12

下記のコードを実行するとどれが出力されますか？

```javascript
const arr = [1, 2, 3];
arr.push(6);
console.log(arr);
arr.pop();
console.log(arr);
arr.shift();
console.log(arr);
arr.unshift(8);
console.log(arr);
```

A.[1, 2, 3, 6],[2, 3, 6],[3, 6],[8, 3, 6]
B.[6, 1, 2, 3],[6, 1, 2],[1, 2],[8, 1, 2]
C.[6, 1, 2, 3],[1, 2, 3],[2, 3],[2, 3, 8]
D.[1, 2, 3, 6],[1, 2, 3],[2, 3],[8, 2, 3]

答案D

> arr.pop(); 移除数组最后一个元素
>
> arr.shift();移除数组第一个元素
>
> arr.unshift(8);将新项目添加到数组的开头：
>



## 問14

下記のコードを実行するとどれが出力されますか？

```javascript
String.prototype.giveLydiaPizza = () => {
    return 'Just give Lydia pizza already!';
};
const name = 'Lydia';
name.giveLydiaPizza();
```

A. “Just give Lydia pizza already!”
B. TypeError: not a function
C. SyntaxError
D. undefined

答え

A. “Just give Lydia pizza already!”

Stringは組み込みのコンストラクターであり、プロパティを追加できます。



## 問15

下記のコードを実行するとどれが出力されますか？

```javascript
function sayHi() {
    return (() => 0)();
}
console.log(typeof sayHi());
```

A. “object”
B. “number”
C. “function”
D. “undefined”

答え

B. “number”



## 問16

イベント伝播の3つのフェーズは何ですか？

A.ターゲット>キャプチャ>バブリング
B.バブリング>ターゲット>キャプチャ
C.ターゲット>バブリング>キャプチャ
D.キャプチャ>ターゲット>バブリング

答え

D.キャプチャ>ターゲット>バブリング



## 問18

どのデータコレクションがキー順に並べられていますか？

A.Map
B.Array
C.Set
D.Object

答え

A.Map
C.Set



## 問19

下記のコードを実行するとどれが出力されますか？

```
function Person (fName, lName) {
    this.fName = fName;
    this.lName = lName;
}

Person.prototype.age = 29;
let jim = new Person('Jim', 'Smith');

jim.age = 18;

console.log(jim.age);
console.log(jim.__proto__.age);
```

A: 18,29
B: 18,18
C: 18,undefined
D: 29,29

答え

A: 18,29 

[解答]: https://blog.csdn.net/ixygj197875/article/details/79243712	"解答"



## 問23

下記のコードを実行するとどれが出力されますか？

```
const num = parseInt('7*6', 10);
console.log(num);
```

A.42
B.”42″
C.7
D.NaN

答え

C.7

>  parseInt() 函数可解析一个字符串，并返回一个整数。
>
> - 如果 string 以 "0x" 开头，parseInt() 会把 string 的其余部分解析为十六进制的整数。
>
> - 如果 string 以 0 开头，那么 ECMAScript v3 允许 parseInt() 的一个实现把其后的字符解析为八进制或十六进制的数字。
>
> - 如果 string 以 1 ~ 9 的数字开头，parseInt() 将把它解析为十进制的整数。
>
> - **注意：** 只有字符串中的第一个数字会被返回。
>
>   **注意：** 开头和结尾的空格是允许的。
>
>   **注意：**如果字符串的第一个字符不能被转换为数字，那么 parseInt() 会返回 NaN。
>
>   **注意：**在字符串以"0"为开始时旧的浏览器默认使用八进制基数。ECMAScript 5，默认的是十进制的基数。
>
>   ```javascript
>   parseInt("10")  // 10
>   parseInt("10.33")  // 10
>   parseInt("34 45 66")  // 34
>   parseInt(" 60 ")  // 60
>   parseInt("40 years")  // 40
>   parseInt("He was 40")  // NaN
>   parseInt("10",10) // 10
>   parseInt("010") // 10
>   parseInt("10",8) // 8
>   parseInt("0x10") // 16
>   parseInt("10",16) // 16
>   ```
>
>   



## 問32

falsyな値はどれですか？

A: 0, ”, undefined
B: 0, new Number(0), ”, new Boolean(false), undefined
C: 0, ”, new Boolean(false), undefined
D: 上記全て

答え

A: 0, ”, undefined

> avaScript中存在Truthy值和Falsy值的概念 — 除了boolean值true、false外，所有类型的JavaScript值均可用于逻辑判断，其规则如下：
>
> 1.所有的Falsy值，当进行逻辑判断时均为false。Falsy值包括：false、undefined、null、正负0、NaN、”"。
> 2.其余所有的值均为Truthy，当进行逻辑判断时均为true。值得注意的是，Infinity、空数组、”0″都是Truthy值。
>
> 注意：[]为Truthy



## 問40

下記のコードを実行するとどれが出力されますか？

```javascript
const person = { name: 'Lydia' };

function sayHi(age) {
    return `${this.name} is ${age}`;
}
console.log(sayHi.call(person, 21));
console.log(sayHi.bind(person, 21));
```

A: undefined is 21, Lydia is 21
B: function, function
C: Lydia is 21, Lydia is 21
D: Lydia is 21, function

答え

D: Lydia is 21, function

> call apply bind总结
>
> 相同点:都可以改变函数内部的this指向
>
> 区别点:
>
> 1.call和apply会调用函数，并且改变函数内部this指向
>
> 2.call和apply传递的参数不一样，call传递参数aru1,aru2...形式 apply必须是数组形式
>
> 3.bind不会调用函数，可以改变函数内部this指向
>
> 主要应用场景
>
> 1.call经常做继承
>
> 2.apply经常跟数组又关系，比如借助于数学对象实现数组最大值最小值
>
> 3.bind不调用函数，但是还想改变this指向，比如改变定时器内部的this指向



## 問42

次のうち、モジュールについて間違っているのはどれですか？

A.モジュールは常に厳密モードで実行されます。つまり、変数を宣言する必要があります。
B.それらは一度だけ実行されます。これはロードされたときです。
C.インポートステートメントが引き上げられます。つまり、モジュールがロードされると、すべての依存関係が実行されます。
D.モジュールには、エクスポートするコンストラクターが含まれている必要があります。

答え

D.モジュールには、エクスポートするコンストラクターが含まれている必要があります。

## 問44

2つのネストされたdivと、その下でwindow.onloadが開始されるコードがあるとします。

```
document.querySelector('.outerDiv') .addEventListener('click', displayOuterMessage, true);

document.querySelector('.innerDiv') .addEventListener('click', displayInnerMessage, true); };
```

innerDivがクリックされたときに、イベントリスナーはどのような順序で呼び出されますか？

A. displayInnerMessage, displayOuterMessage
B. displayInnerMessage のみ
C. displayOuterMessage のみ
D. displayOuterMessage, displayInnerMessage

答え

D. displayOuterMessage, displayInnerMessage

> <img src="https://img-blog.csdnimg.cn/20190822171027508.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2tvdXJ5b3VzaGluZQ==,size_16,color_FFFFFF,t_70" alt="flow" style="zoom: 33%;" />
>
> https://blog.csdn.net/kouryoushine/article/details/100019632
>
> - 捕获阶段capture：事件对象通过目标的祖先（windows）逐层往下遍历，直到target的父元素。这个过程就是捕获阶段。
>
> - 目标阶段target: 事件对象在目标的时候。（at target）.如果生命bubble属性不冒泡，则事件停止传播。
>
> - 冒泡阶段：事件对象反向（capture的反序），从目标的父元素开始往dom的祖先window传播。
>
> 
>
>   addEventListener第三个参数可以设定为ture，意思是改变触发handler的顺序。这个listener在capture阶段捕获到时间后就执行。捕获阶段是从外向内向的，所以这样的监听器就会先执行父元素的handler.



## 問48

次のコードで出力されるのはなんですか？

```
let person = { 
    name: 'Lydia'
};
const members = [person];
person = null;
console.log(members);
```

A: null
B: [null]
C: [{}]
D: [{ name: “Lydia” }]

答え

D: [{ name: “Lydia” }]

> javascript和其他语言不同，其不允许直接访问内存中的位置，也就是说不能直接操作对象的内存空间，那我们操作啥呢？ 实际上，是操作对象的引用，所以引用类型的值是按引用访问的。
>
> ```person = null;``` 改变了person的引用地址
>
> 而members的引用地址没有变化。
>
> ```person = null;``` 如改成```person.name='tony';``` 
>
> 则members也会受到影响



## 問50

下記のコードを実行するとどれが出力されますか？

```
const arr = [1, 4, 9, 16];
console.log(arr.slice(1,3));
```

A: [1,9]
B: [1,16]
C: [4,9]
D: [4,16]

答え

C: [4,9]

> arr.slice(1,3) 方法以新的数组对象，返回数组中被选中的元素。
>
> 选择从给定的 *start* 参数开始的元素，并在给定的 *end* 参数处结束.



## 問52

下記のコードがあります。3行目に入る正しいコードはどれですか？

```
const https = require('https');
const server = https.createServer((req, res) => {
// Line 3: ここに正解コードを入れる
let reqData = JSON.parse(chunk);
console.log(reqData);});
res.end('OK');});
server.listen(8000);
```

A. req.on(‘data’, (chunk) => {
B. req.get(‘data’, (chunk) => {
C. req.data((chunk) => {
D. req.on(‘get’, (chunk) => {

答え

A. req.on(‘data’, (chunk) => {



## 問55

下記のコードを実行するとどれが出力されますか？

```
let s1 = '2 + 2'
let s2 = new String('2 + 2')
console.log(eval(s1))
console.log(eval(s2))
console.log(eval(s2.valueOf()))
```

A.’2 + 2′,’2 + 2′,4
B.’2 + 2′,String{‘2 + 2’}
C.4,String{‘2 + 2’},4
D.4,’2 + 2′,4

答え

C.4,String{‘2 + 2’},4

[eval()](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/eval)

> eval() 函数计算或执行参数。

## 問58

次のコードで出力されるのはなんですか？

```
const months = ['Jan', 'March', 'April', 'June'];
months.splice(3, 1, 'May');
console.log(months);
```

A: [‘Jan’, ‘March’, ‘April’, ‘May’ ,’June’]
B: [‘Jan’, ‘March’, ‘April’, ‘May’]
C: [‘Jan’, ‘March’, ‘May’]
D: [‘Jan’, ‘March’, ‘April’],’May’

答え

B: [‘Jan’, ‘March’, ‘April’, ‘May’]

[Array.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

> splice() 方法用于添加或删除数组中的元素。
>
> | 参数                  | 描述                                                         |
> | :-------------------- | :----------------------------------------------------------- |
> | *index*               | 必需。规定从何处添加/删除元素。 该参数是开始插入和（或）删除的数组元素的下标，必须是数字。 |
> | *howmany*             | 可选。规定应该删除多少元素。必须是数字，但可以是 "0"。 如果未规定此参数，则删除从 index 开始到原数组结尾的所有元素。 |
> | *item1*, ..., *itemX* | 可选。要添加到数组的新元素                                   |
>
> ## 返回值
>
> | Type  | 描述                                                         |
> | :---- | :----------------------------------------------------------- |
> | Array | 如果从 arrayObject 中删除了元素，则返回的是含有被删除的元素的数组。 |

---

## 問69

下記のコードを実行するとどれが出力されますか？

```
(() => {
    let x, y;
    try {
        throw new Error();
    } catch (x) {
        (x = 1), (y = 2);
        console.log(x);
    }
    console.log(x);
    console.log(y);
})();
```

A: undefined,1,2
B: 1,1,2
C: 1,undefined,2
D: undefined,undefined,2

答え

C: 1,undefined,2

---

setIntervalメソッドはブラウザに何を返しますか？

```javascript
setInterval(() => console.log('Hi'), 1000); // 1000毫米后执行第一次，之后每隔1000毫米执行一次
```

A：一意のID
B：指定されたミリ秒数
C：渡された関数
D：未定義

答え

A：一意のID

---

A developer has code that calculates a restaurant bill, but generates incorrect answers while testing the code:
function calculateBill ( items ) {
let total = 0;
total += findSubTotal(items);
total += addTax(total);
total += addTip(total);
return total;
}
Which option allows the developer to step into each function execution within calculateBill?

**A.** Using the debugger command on line 05.

**B.** Calling the console.trace (total) method on line 03.

**C.** Wrapping findSubtotal in a console.log() method.

**D.** Using the debugger command on line 03

Correct Answer: A

---

Which option is a core Node,js module?

**A.** Memory

**B.** locate

**C.** Path

**D.** Ios

Correct Answer: C

---

Which statement accurately describes the behaviour of the async/ await keyworks ?

**A.** The associated class contains some asynchronous functions.

**B.** The associated function will always return a promise

**C.** The associated sometimes returns a promise.

**D.** The associated function can only be called via asynchronous methods

Correct Answer: B

---

What will the output be in the console for the following:

import { printMsg } from './module1.js';
import { msg1, msg2 } from './module2.js';
msg1 = 'Did this variable change?';
printMsg(msg1 + msg2);



ANSWER:
TypeError: Assignment to constant variable.

Additional Info:
You CANNOT reassign the exported value. It can only be changed from inside the module it was exported from.

---

The JavaScript global execution context creates two things for you: the global object, and the "this" keyword.
A: true
B: false
C: it depends

ANSWER:
A: true

Additional Info:
The base execution context is the global execution context: it's what's accessible everywhere in your code.

---

