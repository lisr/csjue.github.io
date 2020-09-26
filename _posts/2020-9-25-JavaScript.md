## 嵌入html

javascript 一般放在head 中

```html
<html>
<head>
  <script>
    alert('Hello, world');
  </script>
</head>
<body>
  ...
</body>
</html>
```

放入单独.js

```
<html>
<head>
  <script src="/static/js/abc.js"></script>
</head>
<body>
  ...
</body>
</html>
```

## 变量

```
var x = 1;
```

可以赋值不同类型，只能一次声明

并不强制var，但是没有var，会成全局变量

应在第一行声明 'use strict'; 

## 相等

== 会自动转换类型，有时会得到诡异的结果

=== 尽量使用这个



## null undefined

null表示空 undefined表示未定义



## 数组

[ ] 或者 new Array()

用索引 arr[0] ，不会越界

IndexOf() slice()返回部分

unshift()往头部增加元素 shift()删除

sort() reverse() 

splice()万能操作法

```
var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
// 从索引2开始删除3个元素,然后再添加两个元素:
arr.splice(2, 3, 'Google', 'Facebook'); // 返回删除的元素 ['Yahoo', 'AOL', 'Excite']
arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
// 只删除,不添加:
arr.splice(2, 2); // ['Google', 'Facebook']
arr; // ['Microsoft', 'Apple', 'Oracle']
// 只添加,不删除:
arr.splice(2, 0, 'Google', 'Facebook'); // 返回[],因为没有删除任何元素
arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
```

concat 连接两个数组，不修改，返回新的，自动拆开Array

join

```
var arr = ['A', 'B', 'C', 1, 2, 3];
arr.join('-'); // 'A-B-C-1-2-3'
```

自动转换成字符串

## 对象

```
var person = {
    name: 'Bob',
    age: 20,
    tags: ['js', 'web', 'mobile'],
    city: 'Beijing',
    hasCar: true,
    zipcode: null
};
```

键是字符串 值是任意类型

获取对象用 类名.键 也可以索引 ['age']

可以随意增加 删除 (delete)属性

可以用in 检测有没有属性 也有可能是继承来的属性

```
'name' in xiaoming; 
```

hasOwnProperty()可以排除掉继承

## 字符串

### 多行字符串

```
`这是一个
多行
字符串`;
```

用esc下的反引号

### 模板字符串

```
var name = '小明';
var age = 20;
var message = `你好, ${name}, 你今年${age}岁了!`;
alert(message);
```

### 操作字符串

利用索引访问

字符串无法修改，使用方法会返回新字符串

toUpperCase() toLowerCase() IndexOf substring()

substring(n) 从n开始 不包括

## 循环

for

```
for (i=1; i<=10000; i++) {
    x = x + i;
}
```

for in

```
var o = {
    name: 'Jack',
    age: 20,
    city: 'Beijing'
};
for (var key in o) {
    console.log(key); // 'name', 'age', 'city'
}
```

要过滤掉对象继承的属性，用`hasOwnProperty()`来实现：

```
var o = {
    name: 'Jack',
    age: 20,
    city: 'Beijing'
};
for (var key in o) {
    if (o.hasOwnProperty(key)) {
        console.log(key); // 'name', 'age', 'city'
    }
```

```
var a = ['A', 'B', 'C'];
for (var i in a) {
    console.log(i); // '0', '1', '2'
    console.log(a[i]); // 'A', 'B', 'C'
}
```

Array遍历得到的是string

while

```
var x = 0;
var n = 99;
while (n > 0) {
    x = x + n;
    n = n - 2;
}
x; // 2500
```

do while

```
var n = 0;
do {
    n = n + 1;
} while (n < 100);
n; // 100
```