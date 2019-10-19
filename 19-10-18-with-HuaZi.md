# 19-10-15 华资软件宣讲会 + 笔试

## 20 个智力题

## 28 个心理测评题

## 23 个前端题

### event.preventDefault 和event.stopPropagation的作用分别是？

1. preventDefault，prevent是动词，意为“防止，阻止”；Default是名词，有“系统默认值”的意思，preventDefault在js中的意思就   是“阻止系统默认（行为）”。

2. stopPropagation，stop是动词，意为“中止”；Propagation是名词，意为“传播”，stopPropagation在意为“中止传播”，在js中的意思是“阻止js事件冒泡”。

### 使用react.js通常在______生命周期阶段发起Ajax请求

componentDidMount

1. React 下一代调和算法 Fiber 会通过开始或停止渲染的方式优化应用性能，其会影响到 componenТWillMount 的触发次数。对于 componenТWillMount 这个生命周期函数的调用次数会变得不确定，React 可能会多次频繁调用 componenТWillMount。如果我们将 AJAX 请求放到 componenТWillMount 函数中，那么显而易见其会被触发多次，自然也就不是好的选择。

2. 如果我们将 AJAX 请求放置在生命周期的其他函数中，我们并不能保证请求仅在组件挂载完毕后才会要求响应。如果我们的数据请求在组件挂载之前就完成，并且调用了setState函数将数据添加到组件状态中，对于未挂载的组件则会报错。而在 componentDidMount 函数中进行 AJAX 请求则能有效避免这个问题。

## 执行 ['1', '2', '3'].filter(el => typeof el === 'string') 的结果是

['1', '2', '3']

### filter 是返回值

### js 中 5 种不同数据类型分别是

Number, String, Boolean, Undefined, Null

### function 和 object 和 array -> 引用数据类型

---

其实还有Symbol

## 以下代码的执行结果

``` JS
function foo() {
    let i = 0;
    return function() {
        console.log(i++);
    }
}
const f1 = foo();
const f2 = foo();

f1();
f1();
f1();
f2();
```

### 0 1 2 0 -> 关于闭包

## 可以使用 typeof 判断一个变量是不是数组类型 -> 错 （es6 Array.isArray()）

## 2个算法题

``` JS
// 清除数组中的重复元素，要求返回的内容只有字符串或者数字
const isStrOrNum = el => {
    return typeof el === 'number' || typeof el === 'string';
}

const dedu = arr => {
    let res = [],
        hash = {};
    for (let i = 0; i < arr.length; i++) {
        if (!hash[arr[i]] && isStrOrNum(arr[i])) {
            hash[arr[i]] = true;
            res.push(arr[i]);
        }
    }
    return res;
}
const arr = [1, '1', '2', 1, {
    'a': 1
}];

console.log(dedu(arr));
```

``` js
// “如果的如果，还是如果，xxxxx” 替换掉最后一个如果成没如果（正则表达式
let str = `如果的如果，还是如果，xxxx` ;
let res = ``;
let lIndex = str.lastIndexOf("如果");
let re = /如果/g;
let str1 = str.substring(0, lIndex);
let str2 = str.substring(lIndex);
str2 = str2.replace(re, '没如果');
res = str1 + str2;
console.log(res);
```

