# get_block_information

根据区块 ID 获取该区块基本信息。

## 方法定义

```python
def get_block_information(self, block_id: BlockIdentifier) -> Optional[BlockInformationData]
```

## 参数说明

| 参数     | 类型            | 说明                                                                    |
| -------- | --------------- | ----------------------------------------------------------------------- |
| block_id | BlockIdentifier | 区块 ID,可以是区块号、区块哈希或 'latest','earliest','pending' 等标识符 |

## 返回值

返回 BlockInformationData 对象,包含以下字段:

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
# 获取最新区块信息
latest_block = chain.get_block_information("latest")
print(f"Block Number: {latest_block.block_number}")
print(f"Block Hash: {latest_block.block_hash.hex()}")
print(f"Miner: {latest_block.miner}")
print(f"Gas Used: {latest_block.gas_used}")

# 通过区块号获取
block = chain.get_block_information(12345678)

# 通过区块哈希获取
block = chain.get_block_information("0x...")
```
