## BOM

## window对象

BOM的核心是window对象，控制窗口及弹窗

### 窗口位置

```js
//窗口移动到左上角
window.moveTo(0,0);

//窗口向下移动100像素
window.moveBy(0,100);
```



### 调整窗口大小

```js
//窗口缩放到100 x 100，设置新的缩放宽度和高度
window.resizeTo(100,100)
//窗口缩放到 200 x 150，resizeBy 接收宽度和高度各要缩放多少
window.resizeBy(100,50)
```



### 视口位置（滚动条）

```js
//滚动到页面左上角
window.scrollTo(0,0);
window.scrollBy(x,y);
```

### 打开新窗口

```js
//用于导航到指定URL，也可以用于打开新的浏览器窗口
window.open("url","已经存在的窗口名字");
//单纯弹出一个窗口
window.open();
//open()里面有四个参数，参考《高级程序设计》P365
```

### 定时器也属于BOM的windows对象

代码略

###  系统对话框

```js
alert();
confirm(); //有确认和取消按钮
prompt();//输入一个值，会获得那个输入的值
//两个异步对话框
window.print();//显示打印对话框
window.find();//显示查找对话框
```



## location对象

《高级程序设计》P372

查询字符串

```js
        /*
        查询URL字符串
        */
        let getQueryStringArgs = function () {
            let qs = (location.search.length > 0 ? location.search.substring(1) : ""),
            //保存数据对象
                args = {};
            //把每个参数添加到 args 对象
            for (let item of qs.split("&").map(kv => kv.split("="))) {
                let name = decodeURIComponent(item[0]),
                    value = decodeURIComponent(item[1]);
                if (name.length) {
                    args[name] = value;
                }
            }
            return args;
        }
        //console.log(getQueryStringArgs);
```



## navigator对象

**主要用于查询浏览器的属性**

检测浏览器是否安装了某个插件插件p376

注册处理程序p378



## screen对象

浏览器窗口外面的客户端显示器的信息



## history对象

```js
//后退一页
history.go(-1);
//前进一页
history.go(1);
//前进两页
history.go(2);
//导航到最近的 wrox.com 页面
history.go("wrox.com");
//go 有两个简写方法
history.back();//后退一页
history.forward();//前进一页
```



> 参考资料：《高级程序设计指南第四版》
>
> [《JavaScript高级程序设计》 · 艾克佐迪亚/我的阅读 - 码云 - 开源中国 (gitee.com)](https://gitee.com/ekzodia_lty/my-reading/tree/master/《JavaScript高级程序设计》)

