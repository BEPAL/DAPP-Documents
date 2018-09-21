# Bepal DAPP

帮助DAPP开发者接入 BEPAL APP

- [币种交易](#币种交易)
- [本地钱包](#本地钱包)
- [错误编码](#错误编码)
- [其它接口](#其它接口)


# 币种交易


|接口类型|描述|
|:---:|:---:|
|[ETH](javascript/transaction.md#ethbepalpay)|以太坊交易转账|
|[EOS](javascript/transaction.md#eosbepalpay)|柚子交易转账|


# 本地钱包

|接口类型|描述|
|:---:|:---:|
|[获取账户/地址](javascript/wallet.md#walletgetcurrentaccount)|获取当前钱包地址或账号|
|[获取账户/地址列表](javascript/wallet.md#walletgetaccountlist)|获取当前钱包地址或账号列表|
|[切换钱包](javascript/wallet.md#walletshowaccountswitch)|唤出一个钱包切换器， 用户可进行选择切换|


# 错误编码

| 错误编号  | 错误消息  |
|:---:|:---:|
| 1001 |  用户取消操作 |
| 1002 | 当前币种不可用  |
| 1003 | 钱包中未存在该地址或账号 |
| 1004 | 余额不足 |
| 1005 | 参数错误 |
| 1006 | 签名失败 |
| 1100 | 未知错误 |

# 其它接口

|接口类型|描述|
|:---:|:---:|
|[隐藏导航栏](javascript/app_navbar.md#navbartogglenavbar)|隐藏系统内置导航栏，使DAPP全屏|
|[关闭DAPP](javascript/app_navbar.md#navbarclosedapp)|关闭当前DAPP，回到进入DAPP前的页面|
|[返回上一页](javascript/app_navbar.md#navbargoback)|返回到历史记录的上一页|
|[提示框](javascript/app_navbar.md#apptoast)|轻弹框提示|
|[确认框](javascript/app_navbar.md#appconfirm)|确认框（确认/取消）|
|[设置剪切板](javascript/app_navbar.md#appsetclipboard)|设置文本到用户剪贴板|
|[获取二维码](javascript/app_navbar.md#appscanqrcode)|打开摄像头扫描一张二维码|
|[获取当前语言](javascript/app_navbar.md#appgetcurrentlanguage)|获取当前APP的语言|
|[获取货币单位](javascript/app_navbar.md#appgetcurrentcurrency)|获取当前APP的货币单位|
