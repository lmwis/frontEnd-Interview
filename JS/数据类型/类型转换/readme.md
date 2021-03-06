<!--
 * @Author       : BigDgreen
 * @Date         : 2020-07-17 21:41:42
 * @LastEditors  : BigDgreen
 * @LastEditTime : 2020-07-29 20:14:10
 * @FilePath     : \前端知识点总结\JS\数据类型\类型转换\readme.md
--> 
## 字符串转数组
let str = '213';

1. Array.from(str);
2. [...new Set(str)];
3. Array.prototype.slice.call(str)
4. str.split('');

## 类数组对象转数组
Arguments 对象就是一个类数组对象。在客户端 JavaScript 中，一些 DOM 方法(document.getElementsByTagName()等)也返回类数组对象。
```js
var arrayLike = {
    0: 'name',
    1: 'age',
    2: 'sex',
    length: 3
}
```

1. slice
```
Array.prototype.slice.call(arrayLike);
```

2. splice
```
Array.prototype.splice.call(arrayLike, 0); // ["name", "age", "sex"] 
```
3. ES6 Array.from
```
Array.from(arrayLike); // ["name", "age", "sex"] 
```
4. apply
```
Array.prototype.concat.apply([], arrayLike)
```
5. ES6 ... 展开符
```
... arrayLike
```

### `Array.from()`与 `...` 展开符的区别
使用展开符，展开对象必须可迭代

## 转对象
创建对象的方式：
1. 字面量
2. 构造函数
3. `Object.create()`

创建空对象：`Object.create(null)`，不会创建`Object.prototype`这个委托，比`{}`更空。
