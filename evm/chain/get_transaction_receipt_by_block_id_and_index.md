# get_transaction_receipt_by_block_id_and_index

根据区块 ID 和索引来获取该交易的回执信息。

## 方法定义

```python
def get_transaction_receipt_by_block_id_and_index(self, block_id: BlockIdentifier, transaction_index: int) -> Optional[TransactionReceiptData]
```

## 参数说明

| 参数              | 类型            | 说明                                |
| ----------------- | --------------- | ----------------------------------- |
| block_id          | BlockIdentifier | 区块 ID(区块号/区块哈希/'latest'等) |
| transaction_index | int             | 交易在区块中的索引                  |

## 返回值

返回 TransactionReceiptData 对象,字段说明与 get_transaction_receipt_by_hash 相同。

## 示例代码

```python
# 获取最新区块的第一笔交易
receipt = chain.get_transaction_receipt_by_block_id_and_index("latest", 0)
if receipt:
    print(f"Transaction Hash: {receipt.transaction_hash.hex()}")
    print(f"From: {receipt.sender}")
    print(f"To: {receipt.to}")
    print(f"Value: {Web3.from_wei(receipt.value, 'ether')} ETH")
```
