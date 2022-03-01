# [剑指 Offer 58 - II. 左旋转字符串](https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/)

方法一：把与旋转的字符串拿出来放到该放到的地方去。

```js
/**
 * @param {string} s
 * @param {number} n
 * @return {string}
 */
var reverseLeftWords = function(s, n) {
s=s.split("");
 let num;
for(let i=0;i<n;i++){
    num=s.shift();
    if(num){
        s.push(num)
    }
}
return s.join("");
};
```

方法二：切成两个数组，再拼接到一起去。

```js
/**
 * @param {string} s
 * @param {number} n
 * @return {string}
 */
var reverseLeftWords = function (s, n) {
    let arr = s.split("").splice(0, n);
    let arr2 = s.split("").splice(n, s.length);
    let res = arr2.concat(arr).join("");
    return res
};
```

