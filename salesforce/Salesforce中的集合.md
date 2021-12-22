### Salesforce中的集合

#### List

###### 初期化

```java
List<String> list1 = new List<String>(); // ()

List<String> list2 = new List<String> {'str2-1','str2-2'}; // (str2-1, str2-2)

List<String> list3 = new List<String>(list2); // (str2-1, str2-2)

List<String> list4 = new List<String>(new Set<String> {'str4-1','str4-2'}); // (str4-1, str4-2)

List<String> list5 = new String[1]; // (null)

String[] list6 = new String[1]; // (null)
```



###### 常用方法

###### 转换

---

#### Set

###### 初期化

```java
Set<String> testList = new Set<String> {'test','dazei'};
```

###### 常用方法

###### 转换

---

#### Map

###### 初期化

```java
Map<String, String> testMap = new Map<String, String>{
	'zei1' => 'error'
	,'zei2' => 'ga'
};
```



###### 常用方法

###### 转换

---

