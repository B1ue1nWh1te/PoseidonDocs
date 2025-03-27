# Table of contents

## 入门

* [简介](README.md)
* [安装](ru-men/an-zhuang.md)
* [示例](ru-men/shi-li.md)
* [注意事项](ru-men/zhu-yi-shi-xiang.md)
* [更新日志](ru-men/geng-xin-ri-zhi/README.md)
  * [v2.0.1](ru-men/geng-xin-ri-zhi/v2.0.1.md)
  * [v2.0.0](ru-men/geng-xin-ri-zhi/v2.0.0.md)

## EVM

* [(DataClass)](evm/dataclass/README.md)
  * [ChainInformationData](evm/dataclass/chaininformationdata.md)
  * [BlockInformationData](evm/dataclass/blockinformationdata.md)
  * [TransactionReceiptData](evm/dataclass/transactionreceiptdata.md)
  * [SignatureData](evm/dataclass/signaturedata.md)
  * [SignedMessageData](evm/dataclass/signedmessagedata.md)
* [Chain](evm/chain/README.md)
  * [\_\_init\_\_](evm/chain/__init__.md)
  * [get\_chain\_information](evm/chain/get_chain_information.md)
  * [get\_block\_information](evm/chain/get_block_information.md)
  * [get\_transaction\_receipt\_by\_hash](evm/chain/get_transaction_receipt_by_hash.md)
  * [get\_transaction\_receipt\_by\_block\_id\_and\_index](evm/chain/get_transaction_receipt_by_block_id_and_index.md)
  * [get\_balance](evm/chain/get_balance.md)
  * [get\_code](evm/chain/get_code.md)
  * [get\_storage](evm/chain/get_storage.md)
  * [dump\_storage](evm/chain/dump_storage.md)
* [Account](evm/account/README.md)
  * [\_\_init\_\_](evm/account/__init__.md)
  * [set\_need\_confirm\_before\_send\_transaction](evm/account/set_need_confirm_before_send_transaction.md)
  * [get\_self\_balance](evm/account/get_self_balance.md)
  * [send\_transaction](evm/account/send_transaction.md)
  * [send\_transaction\_by\_eip1559](evm/account/send_transaction_by_eip1559.md)
  * [deploy\_contract](evm/account/deploy_contract.md)
  * [sign\_message\_string](evm/account/sign_message_string.md)
  * [sign\_message\_raw\_hash](evm/account/sign_message_hash.md)
  * [sign\_message\_hash](evm/account/sign_message_hash-1.md)
  * [sign\_typed\_message](evm/account/sign_typed_message.md)
* [Contract](evm/contract/README.md)
  * [\_\_init\_\_](evm/contract/__init__.md)
  * [call\_function](evm/contract/call_function.md)
  * [call\_function\_with\_parameters](evm/contract/call_function_with_parameters.md)
  * [read\_only\_call\_function](evm/contract/read_only_call_function.md)
  * [encode\_function\_calldata](evm/contract/encode_function_calldata.md)
  * [decode\_function\_calldata](evm/contract/decode_function_calldata.md)
* [Utils](evm/utils/README.md)
  * [set\_solidity\_version](evm/utils/set_solidity_version.md)
  * [compile\_solidity\_contract](evm/utils/compile_solidity_contract.md)
  * [import\_contract\_abi](evm/utils/import_contract_abi.md)
  * [generate\_new\_account](evm/utils/generate_new_account.md)
  * [generate\_account\_from\_mnemonic](evm/utils/generate_account_from_mnemonic.md)
  * [calculate\_create\_case\_contract\_address](evm/utils/calculate_create_case_contract_address.md)
  * [calculate\_create2\_case\_contract\_address](evm/utils/calculate_create2_case_contract_address.md)
  * [generate\_signature\_data\_with\_signature](evm/utils/generate_signature_data_with_signature.md)
  * [generate\_signature\_data\_with\_rsv](evm/utils/generate_signature_data_with_rsv.md)
  * [recover\_message\_string](evm/utils/recover_message_string.md)
  * [recover\_message\_raw\_hash](evm/utils/recover_message_hash.md)
  * [recover\_message\_hash](evm/utils/recover_message_hash-1.md)
  * [recover\_typed\_message](evm/utils/recover_typed_message.md)
  * [convert\_equivalent\_signature](evm/utils/convert_equivalent_signature.md)
  * [assembly\_to\_bytecode\_legacy](evm/utils/assembly_to_bytecode_legacy.md)
  * [bytecode\_to\_assembly\_legacy](evm/utils/bytecode_to_assembly_legacy.md)

## Solana

* [(stay tuned)](solana/stay-tuned.md)

## TON

* [(stay tuned)](ton/stay-tuned.md)

## Sui

* [(stay tuned)](sui/stay-tuned.md)
