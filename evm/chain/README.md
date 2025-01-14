# Chain

Chain 是 EVM 链实例，后续的所有链上交互操作都将发往该链处理。

## 成员变量

* `chain_id`: 链 ID
* `provider`: web3.py 原生的 HTTPProvider 实例
* `eth`: HTTPProvider 实例中的 eth 模块

## 方法列表

* [**init**](\_\_init\_\_.md): 初始化 Chain 实例
* [get\_chain\_information](get\_chain\_information.md): 获取链基本信息
* [get\_block\_information](get\_block\_information.md): 获取区块信息
* [get\_transaction\_receipt\_by\_hash](get\_transaction\_receipt\_by\_hash.md): 通过交易哈希获取交易回执
* [get\_transaction\_receipt\_by\_block\_id\_and\_index](get\_transaction\_receipt\_by\_block\_id\_and\_index.md): 通过区块和索引获取交易回执
* [get\_balance](get\_balance.md): 获取账户余额
* [get\_code](get\_code.md): 获取合约字节码
* [get\_storage](get\_storage.md): 获取存储值
* [dump\_storage](dump\_storage.md): 批量获取存储值
