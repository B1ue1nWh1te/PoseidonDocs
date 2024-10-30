# BlockInformationData

区块信息数据结构。

## 字段说明

| 字段         | 类型                                        | 说明             |
| ------------ | ------------------------------------------- | ---------------- |
| block_hash   | HexBytes                                    | 区块哈希         |
| block_number | BlockNumber                                 | 区块高度         |
| timestamp    | Timestamp                                   | 区块时间戳       |
| miner        | ChecksumAddress                             | 矿工地址         |
| gas_used     | int                                         | 区块已使用的 Gas |
| gas_limit    | int                                         | 区块 Gas 上限    |
| transactions | Union[Sequence[HexBytes], Sequence[TxData]] | 区块内的交易列表 |

## 示例代码

```python
block: BlockInformationData = chain.get_block_information("latest")

print(f"Block Hash: {block.block_hash.hex()}")
print(f"Block Number: {block.block_number}")
print(f"Timestamp: {block.timestamp}")
print(f"Miner: {block.miner}")
print(f"Gas Used: {block.gas_used}")
print(f"Gas Limit: {block.gas_limit}")
print(f"Transaction Count: {len(block.transactions)}")
```
