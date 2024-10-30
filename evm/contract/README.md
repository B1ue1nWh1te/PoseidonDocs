# Contract

Contract 是合约实例,后续需要基于该实例调用合约中的函数。

## 功能概述

Contract 类提供了与智能合约交互的功能:

- 实例化已部署的合约
- 调用合约函数(支持写入和只读)
- 编码和解码合约调用数据

## 成员变量

- `address`: 合约地址
- `web3py_contract`: web3.py 原生的 Contract 实例

## 方法列表

- [**init**](./__init__.md): 初始化 Contract 实例
- [call_function](./call_function.md): 调用合约函数
- [call_function_with_parameters](./call_function_with_parameters.md): 调用合约函数(可指定参数)
- [read_only_call_function](./read_only_call_function.md): 调用只读函数
- [encode_function_calldata](./encode_function_calldata.md): 编码函数调用数据
- [decode_function_calldata](./decode_function_calldata.md): 解码函数调用数据
