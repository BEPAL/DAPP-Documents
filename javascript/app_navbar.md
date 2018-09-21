# app、navbar

------------
## 介绍
bepal app 提供了一系列调用原生方法模块的接口，方便 DApp 调用包括但不限于以下的接口。

------------
## navbar.toggleNavbar
bepal app 通过内置浏览器打开DApp，最上面会有一个导航栏，用户可进行一些操作，如后退，刷新，关闭等。但某些DApp 需要全屏显示或已自实现导航功能，可调用此api 隐藏导航栏

调用示例

```javascript
bepal.callAPP('navbar.toggleNavbar');
```
------------
## navbar.closeDapp

DApp 调用此api后，app会 关闭当前 DApp 页面，返回到 DApp列表页

调用示例

```javascript
bepal.callAPP('navbar.closeDapp');
```
------------
## navbar.goBack
返回到历史记录的上一页， 类似 history.go(-1) 如果没有上一页，则直接关闭dapp，等同于navbar.closeDapp

```javascript
bepal.callAPP('navbar.goBack');
```
------------
## app.toast
app 的轻弹框提示
参数说明：

|  参数 | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| message  | string  |  否 | 不超过20个字  |

调用示例

```javascript
bepal.callAPP('app.toast','I am Bepal !');
```
------------
## app.confirm
app的确认框, 如果用户点击了 取消 按钮， 将会返回一个 error 对象。

|  参数 | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| title  | string  |  否 | 确认框标题  |
| message  | string  |  否 | 确认文本信息  |
| cancelButtonText  | string  |  是 | 默认显示为取消  |
| confirmButtonText  | string  |  是 | 默认显示为确认  |

调用示例

```javascript
var params = {
  title: '标题',
  message: '确认文本',
  cancelButtonText: '取消按钮显示文本',
  confirmButtonText: '确认按钮显示文本'
};
bepal.callAPP('app.confirm',params , function (error, result) {
  if(error) {
    alert('用户点击了退出');
  } else {
    alert('用户点击了确认');
  }
}) ;
```
------------
## app.setClipboard
设置文本到用户剪贴板
参数说明：

|  参数 | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| content  | string  |  否 | 不超过200字  |

调用示例

```javascript
bepal.callAPP('app.setClipboard','I am Bepal !');
```
## app.scanQRCode
打开手机摄像头, 返回二维码的文本内容

```javascript
bepal.callAPP('app.scanQRCode', function (error, result) {
  if(error) {
    alert('用户退出扫描或其他错误原因');
  } else {
    alert('扫描结果='+result);
  }
}) ;
```

------------
## app.getCurrentLanguage
获取用户当前的语言设置，如果 DApp 需要支持多语言

调用示例

```javascript
bepal.callAPP('app.getCurrentLanguage', function (error, result) {
  if(error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert('语言='+result);
  }
}) ;
```
------------
## app.getCurrentCurrency
获取用户当前的货币单位设置

调用示例

```javascript
bepal.callAPP('app.getCurrentCurrency', function (error, result) {
  if(error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert('货币单位='+result);
  }
}) ;
```
