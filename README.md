### Bepal DAPP JS SDK 

------------
#### 更新记录
|  日期 | 版本  |
| ------------ | ------------ |
|  2018年9月7日 |  1.0.0 |

------------
#### 介绍
此文档用户帮助 DApp 开发者接入 Bepal DApp SDK。

------------
#### js sdk 引入
JS SDK  DApp 中的 Bepal JS SDK 脚本文件, 这个脚本是 app 自动注入的，开发者无需引入，只需要根据接口文档中，选择业务需要的api进行使用。

SDK 会在 DApp 的 document 上增加一个 bepal 对象。

还有一件事需要注意的是： Bepal APP 注入 SDK 脚本是在 DApp 的页面 加载完成之后，有可能 DApp 的脚本访问 bepal 对象时还没有完成注入，这样的话 DApp 就不能正常接入APP，所以我们提供了一个事件 onSdkReady，使用如下：

```javascript
document.addEventListener('onSdkReady', function () {
  alert('bepal sdk ready !');
});

```

------------

#### 统一交互入口
为了方便接入和后期扩展，我们提供了统一的调用方法，开发者只需要调用这一个方法，可以进行多项业务操作。调用方式：
```javascript
bepal.callAPP(api, params, callback);
```
##### 参数说明
|  参数 | 类型  | 说明  |
| ------------ | ------------ | ------------ |
| api  | string  | 调用的api方法，请参考提供的api列表  |
|  params | object  | 参数，请根据具体的api 进行传值  |
|  callback | function  |  回调方法 |
