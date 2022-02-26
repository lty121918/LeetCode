# JS正则表达式

## 正则表达式常用方法

+ test 方法用来检测字符串是否符合正则表达式要求。

```js
//regexp.test();
let rg=/123/;
console.log(rg.test(123));//true
console.log(rg.test("abc"));//false
```

+ match() 方法可在字符串内检索指定的值，或找到一个或多个正则表达式的匹配。

```js
//贪婪匹配
let rg=/\d{2,5}/g;
let str="123 1234 12345 123456"
console.log(str.match(rg));
//正则 /\d{2,5}/，表示数字连续出现 2 到 5 次。会匹配 2 位、3 位、4 位、5 位连续数字,其是贪婪的，它会尽可能多的匹配
//惰性匹配
var regex = /\d{2,5}?/g;
var string = "123 1234 12345 123456";
console.log( string.match(regex) );//["12", "12", "34", "12", "34", "12", "34", "56"]
//其中 /\d{2,5}?/ 表示，虽然 2 到 5 次都行，当 2 个就够的时候，就不再往下尝试了。
```

+ replace() 方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。

```js
stringObject.replace(regexp/substr,replacement);
var str1="Visit Microsoft!"
console.log(str1.replace(/Microsoft/, "W3School"));//Visit W3School!
```



## 边界符^$

+ /^123/表示必须以123**开头**

```js
let rg=/^123/;
console.log(rg.test('123456'));//true
console.log(rg.test('456123'));//false
```

+ /123$/表示必须以123**结尾**

```js
let rg=/123$/;
console.log(rg.test('123456'));//false
console.log(rg.test('456123'));//true
```

+ ^和$一起使用代表精确匹配

```js
let rg=/^123$/;
console.log(rg.test('123456'));//false
console.log(rg.test('456123'));//false
console.log(rg.test('123'));//true
```

## 常用字符[]-^

+ **[]:表示有一系列字符可以选择，只要匹配其中的一个就可以**I

```js
let rg=/[123]/;
console.log(rg.test('123456'));//true
console.log(rg.test('456123'));//true
console.log(rg.test('1'));//true
```

+ **-:选择范围[1-9]表示1-9其中一个数字都符合，常见的还有[a-z]小写字母都匹配,[a-zA-Z]大小写都匹配,[a-zA-Z0-9\_-]大小写和-\_都匹配**

```js
let rg=/[1-9]/;
console.log(rg.test('asdf'));//false
console.log(rg.test('456123'));//false
console.log(rg.test('1'));//true
```

+ **如果中括号内[]有^字符，代表取反的意思，区别于中括号外的边界符**

```js
let rg=/[^1-9]/;
console.log(rg.test('asdf'));//true
console.log(rg.test('456123'));//true
console.log(rg.test('1'));//false
```

## 量词符*+？{n}{n,}{n,m}

+ **\*相当于>=0，可以出现0次或者很多次**

```js
let rg=/^a*/;
console.log(rg.test('asdf'));;//true
console.log(rg.test('4561a23'));;//true
console.log(rg.test('1'));//true
```

+ **+想当与>=1，可以出现1次或者很多次**

```js
let rg=/^a+/;
console.log(rg.test('asdf'));//true
console.log(rg.test('4561a23'));//false
console.log(rg.test('1'));//false
```

+ **？相当于1||0**

+ **{3}就是重复3次**
+ **{3，}大于等于3**
+ **{3，16}大于等于3且小于等于16**

## 常见的简写形式

![](https://gitee.com/ekzodia_lty/blog-image/raw/master/img/20220226223735.png)



















