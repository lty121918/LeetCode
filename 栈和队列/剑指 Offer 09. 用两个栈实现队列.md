# [剑指 Offer 09. 用两个栈实现队列](https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/)

复杂程度已经无法用言语形容...大概就是两个栈，一个入队栈，一个出队栈。当一个元素入队时，push到入队栈；里，当一个元素出队时，把入队栈的元素pop出来push到出队栈内，然后判断出队栈是否有元素，有的话pop出去，没有的话返回-1。

```js
var CQueue = function () {
    this.stack1 = [];
    this.stack2 = [];
};

/** 
 * @param {number} value
 * @return {void}
 */
CQueue.prototype.appendTail = function (value) {
    this.stack1.push(value)
};

/**
 * @return {number}
 */
CQueue.prototype.deleteHead = function () {
    const stack1 = this.stack1;
    const stack2 = this.stack2;
    if (stack2.length) {
        return stack2.pop();
    } else {
        while (stack1.length) {
            const n = stack1.pop();
            stack2.push(n);
        }
        if (!stack2.length) {
            return -1;
        } else {
            return stack2.pop()
        }
    }
};
/**
 * Your CQueue object will be instantiated and called as such:
 * var obj = new CQueue()
 * obj.appendTail(value)
 * var param_2 = obj.deleteHead()
 */
```

