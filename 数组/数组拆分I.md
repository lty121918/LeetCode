# 数组拆分I

​		这个题的思路就是，要取两两组合中最小的数，来组成一个最大的和，所以想要一个最大的和，两两组成的数就要差不多大，这样才能出现最大的数，所以先进行排序，取排序之后，靠后的那个数字，组成最大值，代码如下。

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var arrayPairSum = function(nums) {
    nums.sort((a,b)=>a-b);
    let result=0;
    for(let i=0;i<nums.length;i+=2){
        result += nums[i];
    }
    return result;
};
```

​		nums=[1,4,3,2]排序之后[1,2,3,4],分成两组(1,2)(3,4)，取2和4组成最大值。

