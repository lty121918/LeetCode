### 两数之和 II - 输入有序数组

暴力解法

```js
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(numbers, target) {
    let left=0;
    for(let i=0;i<numbers.length;i++){
        for(let j=i+1;j<numbers.length;j++){
            if(numbers[i]+numbers[j]===target){
                return [i+1,j+1];
            }
        }
    }
};
```

双指针+二分查找

```js
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(numbers, target) {
   let start=0;
   let end=numbers.length;
   while(start<end){
       if(numbers[start]+numbers[end]>target){
           end--;
       }else if(numbers[start]+numbers[end]<target){
           start++;
       }else if(numbers[start]+numbers[end]===target){
           return [start+1,end+1]
       }
   }
};
```

