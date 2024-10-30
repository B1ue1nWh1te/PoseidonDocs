# Account

Account 是账户实例,后续的交易将由该账户签署并发送至链上。

## 功能概述

Account 类提供了以下主要功能:

- 通过私钥导入账户
- 发送交易(支持 EIP-155 和 EIP-1559)
- 部署智能合约
- 签名消息(支持普通消息、消息哈希和 EIP-712)
- 查询账户余额

## 成员变量

- `eth_account`: eth_account 的 LocalAccount 实例
- `address`: 账户地址
- `private_key`: 账户私钥

## 方法列表

- [**init**](./__init__.md): 初始化 Account 实例
- [set_need_confirm_before_send_transaction](./set_need_confirm_before_send_transaction.md): 设置发送交易前是否需要确认
- [get_self_balance](./get_self_balance.md): 获取账户余额
- [send_transaction](./send_transaction.md): 发送 EIP-155 交易
- [send_transaction_by_eip1559](./send_transaction_by_eip1559.md): 发送 EIP-1559 交易
- [deploy_contract](./deploy_contract.md): 部署合约
- [sign_message_string](./sign_message_string.md): 签名消息字符串
- [sign_message_hash](./sign_message_hash.md): 签名消息哈希
- [sign_typed_message](./sign_typed_message.md): 签名 EIP-712 结构化数据
