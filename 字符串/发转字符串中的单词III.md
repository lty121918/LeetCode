# 发转字符串中的单词III

api做的，有些投机取巧。

```js
/**
 * @param {string} s
 * @return {string}
 */
var reverseWords = function (s) {
   let result=s.split(' ').map((item)=>{
      return item.split('').reverse().join('')
   }).join(' ');
   return result;
};
```

