# 19-10-15 尚游宣讲会 + 笔试

## 一堆js输出，html输出

## 下面代码输出什么

``` JS
function f(n) {
    n = n || 3;
    return function(x) {
        return x * n;
    }
}
var f2 = f();
var f3 = f(3);

console.log(f2(3));
console.log(f3(f2(3)));
```

9

27

## get index.html http1.1 origin: www.syyx.com 是什么意思

get请求，http协议，协议版本1.1 请求头 url index.html 请求源为 www.syyx.com

## 输入网址到页面加载总共有多少种计网协议

应用层 HTTP协议 超文本传输

传输层 TCP协议

DNS协议 获取IP地址

表示层 HTML协议 网页显示

网络层 ARP协议 取物理地址

数据链路层 以太网协议

## http content-type有什么类型

### 常见的媒体格式类型如下

text/html ： HTML格式

text/plain ：纯文本格式

text/xml ：  XML格式

image/gif ：gif图片格式

image/jpeg ：jpg图片格式

image/png：png图片格式

### 以application开头的媒体格式类型

application/xhtml+xml ：XHTML格式

application/xml     ： XML数据格式

application/atom+xml  ：Atom XML聚合格式

application/json    ： JSON数据格式

application/pdf       ：pdf格式

application/msword  ： Word文档格式

application/octet-stream ： 二进制流数据（如常见的文件下载）

application/x-www-form-urlencoded ： <form encType=""> 中默认的encType，form表单数据被编码为key/value格式发送到服务器（表单默认的提交数据的格式）

另外一种常见的媒体格式是上传文件之时使用的：

multipart/form-data ： 需要在表单中进行文件上传时，就需要使用该格式

## 4个sql语句题

## 一个linux cat命令接一堆参数的题

cat是查看命令

## 手动实现一个to_lower_case

``` JS
const to_lower_case = (str) => {
    let arr = str.split('');
    let AscCode;
    let maxCode = 'Z'.charCodeAt();
    let minCode = 'A'.charCodeAt();
    for (let i = 0; i < arr.length; i++) {
        AscCode = arr[i].charCodeAt();
        if (maxCode >= AscCode && minCode <= AscCode) {
            arr[i] = String.fromCharCode(AscCode + 32);
        }
    }
    return arr.join('');
}

console.log(to_lower_case( `ABCZ` ));
```

## 以下代码输出什么，改写成非递归的形式

``` js
function f(n) {
    return n < 2 ? 1 : f(n - 1) + f(n - 2);
}

console.log(f(6));
```

13

### 即斐波那契数列去第一项

改写

``` JS
function fib2(n) {
    let i = 1, j = 2, res;  // 去掉第一项
    if (n < 2) {
        return 1;
    }
    for (let k = 2; k < n; k++) {
        res = i + j;
        i = j;
        j = res;
    }
    return res;
}

console.log(fib2(6));
```

## 数组去重

``` JS
const duplicateArray = arr => {
    let res = [],
        hash = {};
    for (let i = 0; i < arr.length; i++) {
        if (!hash[arr[i]]) {
            hash[arr[i]] = arr[i];
            res.push(arr[i]);
        }
    }
    return res;
}
```

### 其实可以 ES6 一行解决 一下子没想起来 不过还是老老实实 O(n) 哈希表

``` JS
const duplicateArray = (array) => {
    return Array.from(new Set(array));
}
```

## 智力题*2

### 24 张牌 13 张朝下 11 张朝上 在不看的情况下 分成两堆牌 如何分能使左右朝上牌数量一样

X 张朝上，先分 X 张出来，再将这 X 张牌翻转即可

### 大在小这个年纪小4岁    小在大这个年纪大70岁 问爷孙多少岁

设小的 X 岁 大的 Y 岁 小的长到大的需要 (Y - X) 年 得到 Y + (Y - X) = 70

X - (Y - X) = 4

Y = 48   X = 26
