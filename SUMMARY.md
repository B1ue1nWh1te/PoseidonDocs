# Table of contents

## 入门

* [简介](README.md)
* [安装](ru-men/an-zhuang.md)
* [示例](ru-men/shi-li.md)
* [注意事项](ru-men/zhu-yi-shi-xiang.md)
* [更新日志](ru-men/geng-xin-ri-zhi/README.md)
  * [v2.0.0](ru-men/geng-xin-ri-zhi/v2.0.0.md)

## EVM

* [(DataClass)](evm/dataclass/README.md)
  * [ChainInformationData](evm/dataclass/chaininformationdata.md)
  * [BlockInformationData](evm/dataclass/blockinformationdata.md)
  * [TransactionReceiptData](evm/dataclass/transactionreceiptdata.md)
  * [SignatureData](evm/dataclass/signaturedata.md)
  * [SignedMessageData](evm/dataclass/signedmessagedata.md)
* [Chain](evm/chain/README.md)
  * [\_\_init\_\_](evm/chain/\_\_init\_\_.md)
  * [get\_chain\_information](evm/chain/get\_chain\_information.md)
  * [get\_block\_information](evm/chain/get\_block\_information.md)
  * [get\_transaction\_receipt\_by\_hash](evm/chain/get\_transaction\_receipt\_by\_hash.md)
  * [get\_transaction\_receipt\_by\_block\_id\_and\_index](evm/chain/get\_transaction\_receipt\_by\_block\_id\_and\_index.md)
  * [get\_balance](evm/chain/get\_balance.md)
  * [get\_code](evm/chain/get\_code.md)
  * [get\_storage](evm/chain/get\_storage.md)
  * [dump\_storage](evm/chain/dump\_storage.md)
* [Account](evm/account/README.md)
  * [\_\_init\_\_](evm/account/\_\_init\_\_.md)
  * [set\_need\_confirm\_before\_send\_transaction](evm/account/set\_need\_confirm\_before\_send\_transaction.md)
  * [get\_self\_balance](evm/account/get\_self\_balance.md)
  * [send\_transaction](evm/account/send\_transaction.md)
  * [send\_transaction\_by\_eip1559](evm/account/send\_transaction\_by\_eip1559.md)
  * [deploy\_contract](evm/account/deploy\_contract.md)
  * [sign\_message\_string](evm/account/sign\_message\_string.md)
  * [sign\_message\_hash](evm/account/sign\_message\_hash.md)
  * [sign\_typed\_message](evm/account/sign\_typed\_message.md)
* [Contract](evm/contract/README.md)
  * [\_\_init\_\_](evm/contract/\_\_init\_\_.md)
  * [call\_function](evm/contract/call\_function.md)
  * [call\_function\_with\_parameters](evm/contract/call\_function\_with\_parameters.md)
  * [read\_only\_call\_function](evm/contract/read\_only\_call\_function.md)
  * [encode\_function\_calldata](evm/contract/encode\_function\_calldata.md)
  * [decode\_function\_calldata](evm/contract/decode\_function\_calldata.md)
* [Utils](evm/utils/README.md)
  * [set\_solidity\_version](evm/utils/set\_solidity\_version.md)
  * [compile\_solidity\_contract](evm/utils/compile\_solidity\_contract.md)
  * [import\_contract\_abi](evm/utils/import\_contract\_abi.md)
  * [generate\_new\_account](evm/utils/generate\_new\_account.md)
  * [generate\_account\_from\_mnemonic](evm/utils/generate\_account\_from\_mnemonic.md)
  * [calculate\_create\_case\_contract\_address](evm/utils/calculate\_create\_case\_contract\_address.md)
  * [calculate\_create2\_case\_contract\_address](evm/utils/calculate\_create2\_case\_contract\_address.md)
  * [generate\_signature\_data\_with\_signature](evm/utils/generate\_signature\_data\_with\_signature.md)
  * [generate\_signature\_data\_with\_rsv](evm/utils/generate\_signature\_data\_with\_rsv.md)
  * [recover\_message\_string](evm/utils/recover\_message\_string.md)
  * [recover\_message\_hash](evm/utils/recover\_message\_hash.md)
  * [recover\_typed\_message](evm/utils/recover\_typed\_message.md)
  * [convert\_equivalent\_signature](evm/utils/convert\_equivalent\_signature.md)
  * [assembly\_to\_bytecode\_legacy](evm/utils/assembly\_to\_bytecode\_legacy.md)
  * [bytecode\_to\_assembly\_legacy](evm/utils/bytecode\_to\_assembly\_legacy.md)

## Solana

* [(stay tuned)](solana/stay-tuned.md)

## TON

* [(stay tuned)](ton/stay-tuned.md)

## Sui

* [(stay tuned)](sui/stay-tuned.md)
