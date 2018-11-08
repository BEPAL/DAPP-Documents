# transaction

------------
## 介绍
DApp 最频繁的操作是发送一笔交易，此章节介绍了如何发送一笔交易。现支持ETH 和 EOS 的交易发送。DAPP 调用交易发送API 后，APP 会显示一个modal 弹窗让用户确认交易信息，用户确认后根据选择的钱包进行接下来的签名操作，签名后调用APP 的交易发送操作，广播该笔交易。交易成功后，APP 会将交易标识（txid）通过回调方法返回给DApp，如果发生错误或者用户取消操作等，会返回error对象，error包含code及message属性。DApp 根据返回值再进行相应的业务流程操作。

------------
## eth.bepalPay
以太坊交易

params参数说明：

| 参数  | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| to  |  string | 否  | 交易目标地址  |
| from  |  string |  否 |  交易源地址，通常是用户的钱包内相关地址，可通过app.getCurrentAccount 获取 |
| value | string | 否 | 交易金额，纯数字，单位WEI |
| data | string | 是 | eth transaction 中的 Input Data  |

调用示例（转账1 ETH）

```javascript
var params = {
  to: '目标地址',
  from: '用户地址',
  data: '0x98a0871d00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002',
  value: '1000000000000'
};
bepal.callAPP('eth.bepalPay', params, function (error, txid) {
  if (error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert(txid);
  }
});
```
------------
## eos.bepalPay
eos 交易

params参数说明：

| 参数  | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| to  |  string | 否  | 交易目标地址  |
| from  |  string |  否 |  交易源地址，通常是用户的钱包内相关地址，可通过app.getCurrentAccount 获取 |
| value | string | 否 | 交易金额，纯数字，单位 EOS ，小数点四位，小数点过多会直接截断 |

调用示例（转账10 EOS）

```javascript
var params = {
  to: '目标账户',
  from: '用户账户',
  value: '10.0000',
  contract: 'eosio.token'

};
bepal.callAPP('eos.bepalPay', params, function (error, txid) {
  if (error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert(txid);
  }
});
```
------------
## eos.bepalTokenPay
eos 合约交易

params参数说明：

| 参数  | 类型  | 是否可空  | 说明  |
| ------------ | ------------ | ------------ | ------------ |
| to  |  string | 否  | 调用合约名  |
| from  |  string |  否 |  交易源地址，通常是用户的钱包内相关地址，可通过app.getCurrentAccount 获取 |
| funName | string | 否 | 合约方法名 |
| content | string | 否 | 16进制数据 合约内容数据 |
| data | string | 否 | 合约方法列表 |

调用示例

```javascript
var params = {
  to: '调用合约账户',
  from: '用户账户',
  data : [ {
 	funName: "调用方法名",
  	content : '16进制数据 合约内容数据'
	}
  ]
};
bepal.callAPP('eos.bepalTokenPay', params, function (error, txid) {
  if (error) {
    alert('code='+error.code+',message='+error.message);
  } else {
    alert(txid);
  }
});
```

