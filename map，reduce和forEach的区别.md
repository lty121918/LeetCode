# 数组的迭代和归并方法

## 数组有五种迭代方法：

+ every()
+ filter()
+ forEach()
+ map()
+ some()

传入的函数中，参数可以有三个值（item，index，array），item表示当前元素的值，index表示当前元素的索引，array表示数组本身。

### every和some最相似，从数组中搜索符合条件的某个元素。

```js
let nums = [1, 2, 3, 4, 5, 4, 3, 2, 1];
//every要每个函数都返回true，方法才返回true
let everyResult = nums.every((item, index, array) =>
    item > 2
)
//some有一项返回true，方法就返回true
let someResult = nums.some((item, index, array) =>
    item > 2
)
console.log(everyResult);//false
console.log(someResult);//true
```

### filter返回的是符合条件的数组

```js
let nums = [1, 2, 3, 4, 5, 4, 3, 2, 1];
let filterResult = nums.every((item, index, array) =>{
   return item > 2
    //函数返回true之后才会形成数组返回
})
console.log(filterResult);//[ 3, 4, 5, 4, 3 ]
```

### map也会返回一个数组，是对原始数组中同样位置的元素进行传入函数所返回的结果。

```js
let nums = [1, 2, 3, 4, 5, 4, 3, 2, 1];
let mapResult = nums.map((item, index, array) => {
    return item * 2
})
console.log(mapResult); //[2, 4, 6, 8, 10,8, 6, 4, 2]
```

### forEach方法，没有返回值，相当于for循环遍历数组

```js
let nums = [1, 2, 3, 4, 5, 4, 3, 2, 1];
let newNums = [];
let forEachResult = nums.forEach((item, index, array) => {
    newNums.push(item * 2)
})
console.log(newNums); //[2, 4, 6, 8, 10, 8, 6, 4, 2]
```



## 数组的归并方法

+ reduce()
+ reduceRight()

两种方法都会迭代数组的所有项，并在此基础上构建一个最终返回值。reduce()是从第一项开始遍历到最后一项，reduceRight是从最后一项开始遍历到第一项。

```js
arr.reduce(callback,[initialValue])
```

initialValue可选参数：初始化最开始的归并值。

> 如果没有提供initialValue，reduce 会从索引1的地方开始执行 callback 方法，跳过第一个索引。如果提供initialValue，从索引0开始。

prev：上一项归并值，

cur：当前项

index：当前项索引

array：数组本身

```js
let nums = [1, 2, 3, 4, 5];
let result=nums.reduce((prev,cur,index,array)=>{
    return prev + cur;
})
console.log(result);//15
```

```js
let nums = [1, 2, 3, 4, 5];
let result=nums.reduce((prev,cur,index,array)=>{
    return prev + cur;
},2)
console.log(result);//17
```



除了方向不同，两个方法并没有区别。

### reduce的高级用法

（1）计算数组中每个元素出现的次数

```js
let names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice'];

let nameNum = names.reduce((pre,cur)=>{
  if(cur in pre){
    pre[cur]++
  }else{
    pre[cur] = 1 
  }
  return pre
},{})
console.log(nameNum); //{Alice: 2, Bob: 1, Tiff: 1, Bruce: 1}
```

（2）数组去重

```js
let arr = [1,2,3,4,4,1]
let newArr = arr.reduce((pre,cur)=>{
    if(!pre.includes(cur)){
      return pre.concat(cur)
    }else{
      return pre
    }
},[])
console.log(newArr);// [1, 2, 3, 4]
```

（3）将二维数组转化为一维

```js
let arr = [[0, 1], [2, 3], [4, 5]]
let newArr = arr.reduce((pre,cur)=>{
    return pre.concat(cur)
},[])
console.log(newArr); // [0, 1, 2, 3, 4, 5]
```

（3）将多维数组转化为一维

```js
let arr = [[0, 1], [2, 3], [4,[5,6,7]]]
const newArr = function(arr){
   return arr.reduce((pre,cur)=>pre.concat(Array.isArray(cur)?newArr(cur):cur),[])
}
console.log(newArr(arr)); //[0, 1, 2, 3, 4, 5, 6, 7]
```

（4）对象里的属性求和

```js
var result = [
    {
        subject: 'math',
        score: 10
    },
    {
        subject: 'chinese',
        score: 20
    },
    {
        subject: 'english',
        score: 30
    }
];

var sum = result.reduce(function(prev, cur) {
    return cur.score + prev;
}, 0);
console.log(sum) //60
```



