# ChainInformationData

链信息数据结构。

## 字段说明

| 字段              | 类型             | 说明         |
| --------------- | -------------- | ---------- |
| chain\_id       | int            | 链 ID       |
| block\_number   | BlockNumber    | 当前区块高度     |
| gas\_price      | Wei            | Gas 价格     |
| timeslot        | Optional\[int] | 平均出块时间(可选) |
| client\_version | Optional\[str] | 客户端版本(可选)  |

## 示例代码

```python
from poseidon.evm import Chain

chain = Chain("https://eth-sepolia.g.alchemy.com/v2/YOUR-API-KEY")
info: ChainInformationData = chain.get_chain_information()

print(f"Chain ID: {info.chain_id}")
print(f"Current Block: {info.block_number}")
print(f"Gas Price: {Web3.from_wei(info.gas_price, 'gwei')} Gwei")
if info.timeslot:
    print(f"Average Block Time: {info.timeslot}s")
if info.client_version:
    print(f"Client Version: {info.client_version}")
```
