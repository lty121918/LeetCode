### 求最大公约数

```js
//1.辗转相除法（也叫欧几里得算法）
function gcd(a, b) {
  if (a % b === 0) {
    return b
  }
  return gcd(b, a % b)
}
console.log(gcd(319, 377)) // 29
//2.更相减损法
function gcd(a, b) {
  if (a === b) {
    return b
  }
  if (a > b) {
    a = a - b
  } else {
    b = b - a
  }
  return gcd(a, b)
}
console.log(gcd(319, 377)) // 29
```

### 判断元素是否为数字

```js
function isNumber(obj) { 
    return typeof obj === 'number' && !isNaN(obj) 
}
```

### 自动截取字符串长度

```js
/*
	自动截取字符串长度，截取的部分用省略号代替。
	str目标字符串
	len截取的长度
*/
function cutString(str, len) {
      if (str.length <= len) {
        return str;
      }
      let strlen = 0;
      let s = "";
      for (let i = 0; i < str.length; i++) {
        s = s + str.charAt(i);
        if (str.charCodeAt(i) > 128) {
          strlen = strlen + 2;
          if (strlen >= len) {
            return s.substring(0, s.length - 1) + "...";
          }
        } else {
          strlen = strlen + 1;

          if (strlen >= len) {
            return s.substring(0, s.length - 2) + "...";
          }
        }
      }
      return s;
    }
```



### 获得当前时间

```js
/*
*return 2022-02-17 17:21
*/
function getTime(){
        let time=new Date();
        let year=time.getFullYear();
        let mounth=time.getMonth()+1;
        let date=time.getDate();
        let hour= time.getHours();//得到小时数
        let minute= time.getMinutes();//得到分钟数
        return  `${year}-${mounth}-${date}  ${hour}:${minute}`;
    }
```

