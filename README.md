# JS传入指定长度生成随机数组
```
let randomArray = (length) => {
    let i = 0
    let index = 0
    let temp = null
    let arr = [length]
    length = typeof(length) === 'undefined' ? 9 : length
    for(i=1; i<=length; i++) {
        arr[i - 1] = i
    }
    for(i = 1; i<=length; i++) {
        index = window.parseInt(Math.random() * (length - i)) + i
        if (index != i) {
        temp = arr[i-1]
        arr[i-1] = arr[index-1]
        arr[index-1] = temp
        }
    }
    return arr
}
```

执行调用

```
    let arr = randomArray(12)
    // [11, 10, 9, 2, 4, 6, 8, 1, 3, 5, 7, 12]
```


代码解析

方法接收需要生成的数组长度

通过for循环生成指定长度的数组

打乱数组

返回数组


# 实现方法调用计数
#### code：
```
'use strict';

var count = 0;
var oldParseInt = parseInt; // 保存原函数

window.parseInt = function () {
    count += 1;
    return oldParseInt.apply(null, arguments); // 调用原函数
};
```

#### 测试：
```
parseInt('10.1');
parseInt('20.5');
parseInt('30.9');
console.log('count = ' + count); // 3
```

