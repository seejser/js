# js code
##### JS传入指定长度生成随机数组
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


