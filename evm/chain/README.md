# Chain

Chain 是 EVM 链实例,后续的所有链上交互操作都将发往该链处理。

## 功能概述

Chain 类提供了与 EVM 链交互的基础功能:

- 链接到 EVM 兼容链的节点
- 获取链上基本信息(区块高度、Gas 价格等)
- 获取区块信息
- 获取交易回执
- 查询账户余额
- 获取合约字节码和存储数据

## 成员变量

- `chain_id`: 链 ID
- `provider`: web3.py 原生的 HTTPProvider 实例
- `eth`: HTTPProvider 实例中的 eth 模块

## 方法列表

- [**init**](./__init__.md): 初始化 Chain 实例
- [get_chain_information](./get_chain_information.md): 获取链基本信息
- [get_block_information](./get_block_information.md): 获取区块信息
- [get_transaction_receipt_by_hash](./get_transaction_receipt_by_hash.md): 通过交易哈希获取交易回执
- [get_transaction_receipt_by_block_id_and_index](./get_transaction_receipt_by_block_id_and_index.md): 通过区块和索引获取交易回执
- [get_balance](./get_balance.md): 获取账户余额
- [get_code](./get_code.md): 获取合约字节码
- [get_storage](./get_storage.md): 获取存储值
- [dump_storage](./dump_storage.md): 批量获取存储值
