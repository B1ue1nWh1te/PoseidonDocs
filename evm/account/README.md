# Account

Account 是账户实例，后续的交易将由该账户签署并发送至链上。

## 成员变量

* `eth_account`: eth\_account 的 LocalAccount 实例
* `address`: 账户地址
* `private_key`: 账户私钥

## 方法列表

* [**init**](\_\_init\_\_.md): 初始化 Account 实例
* [set\_need\_confirm\_before\_send\_transaction](set\_need\_confirm\_before\_send\_transaction.md): 设置发送交易前是否需要确认
* [get\_self\_balance](get\_self\_balance.md): 获取账户余额
* [send\_transaction](send\_transaction.md): 发送 EIP-155 交易
* [send\_transaction\_by\_eip1559](send\_transaction\_by\_eip1559.md): 发送 EIP-1559 交易
* [deploy\_contract](deploy\_contract.md): 部署合约
* [sign\_message\_string](sign\_message\_string.md): 签名消息字符串
* [sign\_message\_hash](sign\_message\_hash.md): 签名消息哈希
* [sign\_typed\_message](sign\_typed\_message.md): 签名 EIP-712 结构化数据
