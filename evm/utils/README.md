# Utils

Utils 是通用工具集,整合了常用的链下操作。静态类,无需实例化。

## 功能概述

Utils 类提供了以下功能:

- Solidity 编译相关
  - 设置/切换 Solidity 版本
  - 编译 Solidity 合约
  - 导入合约 ABI
- 账户管理
  - 创建新账户
  - 从助记词生成账户
- 合约地址计算
  - CREATE 方式部署的合约地址计算
  - CREATE2 方式部署的合约地址计算
- 签名相关
  - 签名数据转换
  - 签名恢复
  - EVM 汇编转换

## 方法列表

- [set_solidity_version](./set_solidity_version.md): 选择 Solidity 版本
- [compile_solidity_contract](./compile_solidity_contract.md): 编译 Solidity 合约
- [import_contract_abi](./import_contract_abi.md): 导入合约 ABI
- [generate_new_account](./generate_new_account.md): 创建新账户
- [generate_account_from_mnemonic](./generate_account_from_mnemonic.md): 从助记词生成账户
- [calculate_create_case_contract_address](./calculate_create_case_contract_address.md): 计算 CREATE 方式部署的合约地址
- [calculate_create2_case_contract_address](./calculate_create2_case_contract_address.md): 计算 CREATE2 方式部署的合约地址
- [generate_signature_data_with_signature](./generate_signature_data_with_signature.md): 使用签名生成签名数据
- [generate_signature_data_with_rsv](./generate_signature_data_with_rsv.md): 使用 R,S,V 生成签名数据
- [recover_message_string](./recover_message_string.md): 恢复消息字符串的签名者
- [recover_message_hash](./recover_message_hash.md): 恢复消息哈希的签名者
- [recover_typed_message](./recover_typed_message.md): 恢复结构化消息的签名者
- [convert_equivalent_signature](./convert_equivalent_signature.md): 生成等效签名
- [assembly_to_bytecode_legacy](./assembly_to_bytecode_legacy.md): EVM 汇编转字节码
- [bytecode_to_assembly_legacy](./bytecode_to_assembly_legacy.md): 字节码转 EVM 汇编
