# wallet

------------
## 介绍
bepal app 提供了一系列钱包相关接口

------------
## wallet.getCurrentAccount
获取当前钱包地址或账号，参数说明：

|  参数 | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| chain  | string  |  否 | eth或eos，eth 返回地址，eos返回账号  |

调用示例（eth）

```javascript
var chain = 'eth';
bepal.callAPP('wallet.getCurrentAccount',chain, function (error, result) {
  if(error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert('account='+result);
  }
}) ;
```

调用示例（eos）

```javascript
var chain = 'eos';
bepal.callAPP('wallet.getCurrentAccount',chain, function (error, result) {
  if(error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert('account='+result.account);
    alert('pubkey'+=result.pubkey);
  }
}) ;
```

------------
## wallet.getAccountList
获取当前钱包地址或账号列表，回调中的result 返回值是一个数组，参数说明：

|  参数 | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| chain  | string  |  否 | eth或eos，eth 返回地址，eos返回账号  |

调用示例

```javascript
bepal.callAPP('wallet.getAccountList','eth', function (error, result) {
  if(error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert('account='+JSON.stringify(result));
  }
}) ;
```
------------
## wallet.showAccountSwitch
唤出一个账号切换器， 用户可进行选择切换，eth 选择硬件级别地址，eos 先选择硬件级别，后选择账号级别，参数说明：

|  参数 | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| chain  | string  |  否 | eth或eos，eth 返回地址，eos返回账号  |

调用示例

```javascript
bepal.callAPP('wallet.showAccountSwitch','eth', function (error, result) {
  if(error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert('account='+result);
  }
}) ;
