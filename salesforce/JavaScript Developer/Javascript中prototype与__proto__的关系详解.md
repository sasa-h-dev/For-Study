### Javascript中prototype与__proto__的关系详解

#### **前言**

学到原型的时候感觉头都大了/(ㄒoㄒ)/~~ 尤其是prototype和__proto__ 傻傻分不清 通过多番查找资料，根据自己的理解，总结如下：

#### **一、构造函数：**

构造函数：通过new关键字可以用来创建特定类型的对象的函数。比如像Object和Array，两者属于内置的原生的构造函数，在运行时会自动的出现在执行环境中，可以直接使用。如下：

```javascript
var arr = new Array();//使用Array构造函数创建了一个array实例arr
arr[0]="a";
arr[1]="b";
alert(arr);//a,b

var obj=new Object();//使用Object构造函数创建了一个Object实例obj
obj.name="c";
obj.age=12;
alert(obj.name);//c
```

我们可以自定义的创建构造函数，并为其自定义属性和方法，如：

```javascript
//创建构造函数Person
function Person(name,age){
 this.name=name;
 this.age=age;
 this.sayName=function(){
 alert(this.name)//
 };
}

//使用new关键字，来生成Person实例
var person1=new Person("Tom",22);
var person2=new Person("Jerry",21);
person1.sayName();//Tom
person2.sayName();//Jerry
```

**注意以下几点：**

- 构造函数的名字始终要以大写字母开头（主要是为了区别于非构造函数，也即是区别于普通函数）
- 构造函数也就是函数，定义构造函数和定义普通函数的语法一样。构造函数和普通函数的区别在于：使用他们的方式不同。任何函数只要使用new操作符来调用，那他就可以作为构造函数；不使用new操作符来调用就是普通函数

```javascript
function Person(name,age){
 this.name=name;
 this.age=age;
 this.sayName=function(){
 alert(this.name)//
 };
}

//当做构造函数使用
var person=new Person("Tom",22);
person.sayName();//Tom 
//当做普通函数使用
Person("Jerry",30);//添加到window
sayName();//Jerry 等同于window.sayName();
```

#### **二、原型对象：**

每个函数都有一个prototype属性，它是一个指向原型对象的指针，原型对象在定义函数时同时被创建，原型对象的用途是包含所有实例共享的属性和方法

```javascript
function Person(){
}
//自定义原型对象的属性和方法
Person.prototype.name="Tom";
Person.prototype.age=25;
Person.prototype.sayName=function(){
 alert(this.name);
};
//原型对象中的所有属性和方法 都会自动被所有实例所共享
var person1=new Person();
var person2=new Person();
person1.sayName();//Tom
person2.sayName();//Tom
```

只要创建了一个新函数，每个函数在创建之后都会获得一个prototype的属性，这个属性指向函数的原型对象（原型对象在定义函数时同时被创建），此原型对象又有一个名为“constructor”的属性，反过来指向函数本身，达到一种循环指向，

如在上边的例子中：alert(Person.prototype.constructor===Person);//会返回true

```
function Person(){}alert(Person.prototype.constructor===Person);//true
```

#### **三、___proto_**__

当调用构造函数创建一个新实例后，该实例的内部将包含一个指针[[Prototype]]，该指针指向创建它的构造函数的原型，在脚本上没有标准的方法来访问[[Prototype]]，但大多数浏览器都支持通过__proto__来访问。(注意这里proto左右两边都有两个"_")

```javascript
function Person(){
}
//自定义原型对象的属性和方法
Person.prototype.name="Tom";
Person.prototype.age=25;
Person.prototype.sayName=function(){
 alert(this.name);
};
//原型对象中的所有属性和方法 都会自动被所有实例所共享
var person1=new Person();
var person2=new Person();
person1.sayName();//Tom
person2.sayName();//Tom
alert(person1.__proto__===Person.prototype);//true
```

以上述的示例代码为例，各个对象之间的关系如下图所示：

<img src="http://ssforce-dev.oss-cn-beijing.aliyuncs.com/images/fb673c6d-c776-4ea4-a5ed-3f301e43fdb2/prototype1637211579517.PNG" style="zoom: 67%;" />

#### **总结：**

①只要创建了一个函数，该函数的原型对象也随之同时被创建出来，原型对象中的属性和方法被经由其相对应的构造函数所创建的实例所共享

②每个函数在创建之后都会获得一个prototype的属性，这个属性指向该函数的原型对象

③每个对象的__proto__属性都指向其构造函数的原型

好了，以上就是这篇文章的全部内容了，希望本文的内容对大家的学习或者工作具有一定的参考学习价值，如果有疑问大家可以留言交流，谢谢大家对脚本之家的支持。

---

