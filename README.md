# hx-storage (javascript storage)

### 1. 前端js使用localStorage的时候只能存字符串,不能存储对象

> hx-storage 可以存储 object undefined number string

### 2. localStorage没有过期时间

> hx-storage 可以设置以天为单位的过期时间

## 安装

```base
npm i hx-storage

or

yarn add hx-storage  
```

## 使用

```js
import hxStorage from 'hx-storage';

// 设值
// set （<key>, value, options? = { expires: 0, encode: true }）
hxStorage.set('key', { name: "测试", age: 23 });

// 或者
// expires 过期时间, 单位是天, 默认为零，不设置
hxStorage.set('key', { name: "测试", age: 23 }, { expires: 1, encode: true }) // expires: 设置到期时间，1 代表一天， encode:  encodeURIComponent 进行编码，默认为开启，false为关闭

// 获取值
hxStorage.get('key')

// 清楚所有缓存
hxStorage.clear()

// 删除某个key
hxStorage.remove('key')


// 获取 storage 存储的数据
hxStorage.list();   // { ...data }

```

## 配置

```javascript
import hxStorage from 'hx-storage'

// 配置
hxStorage.setOptions({
    namespace: 'KEY_',      // 设置全局名称前缀
    storage: 'local',       // 存储方式: local 永久存储 和 临时存储  session， 默认为 local
})


hxStorage.set('name', "bar");  // 存储为  { KEY_name : "bar" }

hxStorage.get('name')   // bar
```
