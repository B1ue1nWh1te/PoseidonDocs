# Utils

Utils 是通用工具集，整合了常用的链下操作。静态类，无需实例化。

## 方法列表

* [set\_solidity\_version](set\_solidity\_version.md): 选择 Solidity 版本
* [compile\_solidity\_contract](compile\_solidity\_contract.md): 编译 Solidity 合约
* [import\_contract\_abi](import\_contract\_abi.md): 导入合约 ABI
* [generate\_new\_account](generate\_new\_account.md): 创建新账户
* [generate\_account\_from\_mnemonic](generate\_account\_from\_mnemonic.md): 从助记词生成账户
* [calculate\_create\_case\_contract\_address](calculate\_create\_case\_contract\_address.md): 计算 CREATE 方式部署的合约地址
* [calculate\_create2\_case\_contract\_address](calculate\_create2\_case\_contract\_address.md): 计算 CREATE2 方式部署的合约地址
* [generate\_signature\_data\_with\_signature](generate\_signature\_data\_with\_signature.md): 使用签名生成签名数据
* [generate\_signature\_data\_with\_rsv](generate\_signature\_data\_with\_rsv.md): 使用 R,S,V 生成签名数据
* [recover\_message\_string](recover\_message\_string.md): 恢复消息字符串的签名者
* [recover\_message\_hash](recover\_message\_hash.md): 恢复消息哈希的签名者
* [recover\_typed\_message](recover\_typed\_message.md): 恢复结构化消息的签名者
* [convert\_equivalent\_signature](convert\_equivalent\_signature.md): 生成等效签名
* [assembly\_to\_bytecode\_legacy](assembly\_to\_bytecode\_legacy.md): EVM 汇编转字节码
* [bytecode\_to\_assembly\_legacy](bytecode\_to\_assembly\_legacy.md): 字节码转 EVM 汇编
