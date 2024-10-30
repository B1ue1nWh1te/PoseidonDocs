# TransactionReceiptData

交易回执数据结构。

## 字段说明

| 字段                     | 类型                       | 说明                           |
| ------------------------ | -------------------------- | ------------------------------ |
| transaction_hash         | HexBytes                   | 交易哈希                       |
| block_number             | BlockNumber                | 区块高度                       |
| transaction_index        | int                        | 交易在区块中的索引             |
| transaction_status       | int                        | 交易状态(1 成功,0 失败)        |
| transaction_type         | int                        | 交易类型                       |
| action                   | str                        | 交易动作类型                   |
| sender                   | ChecksumAddress            | 发送者地址                     |
| to                       | ChecksumAddress            | 接收者地址                     |
| nonce                    | Nonce                      | 交易序号                       |
| value                    | Wei                        | 转账金额                       |
| gas_used                 | int                        | 实际使用的 Gas                 |
| gas_limit                | int                        | Gas 上限                       |
| gas_price                | Optional[Wei]              | Gas 价格                       |
| max_fee_per_gas          | Optional[Wei]              | 最大 Gas 费用(EIP-1559)        |
| max_priority_fee_per_gas | Optional[Wei]              | 最大优先费用(EIP-1559)         |
| effective_gas_price      | Optional[Wei]              | 实际 Gas 价格                  |
| contract_address         | Optional[ChecksumAddress]  | 部署的合约地址(仅合约创建交易) |
| contract                 | Optional[Any]              | 合约实例(仅合约创建交易)       |
| logs                     | Optional[List[LogReceipt]] | 交易日志                       |
| input_data               | HexBytes                   | 交易输入数据                   |
| r                        | HexBytes                   | 签名 r 值                      |
| s                        | HexBytes                   | 签名 s 值                      |
| v                        | HexBytes                   | 签名 v 值                      |

## 示例代码

```python
# 获取交易回执
receipt: TransactionReceiptData = chain.get_transaction_receipt_by_hash("0x...")

if receipt.transaction_status:
    print(f"Transaction successful: {receipt.transaction_hash.hex()}")
    print(f"Block Number: {receipt.block_number}")
    print(f"From: {receipt.sender}")
    print(f"To: {receipt.to}")
    print(f"Value: {Web3.from_wei(receipt.value, 'ether')} ETH")
    print(f"Gas Used: {receipt.gas_used}")

    if receipt.contract_address:
        print(f"Deployed Contract: {receipt.contract_address}")
```
