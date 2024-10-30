# get_chain_information

获取 EVM 链基本信息。

## 方法定义

```python
def get_chain_information(self, show_timeslot: bool = True, show_client_version: bool = True) -> ChainInformationData
```

## 参数说明

| 参数                | 类型 | 说明                                |
| ------------------- | ---- | ----------------------------------- |
| show_timeslot       | bool | 是否显示 timeslot,默认为 True       |
| show_client_version | bool | 是否显示 client_version,默认为 True |

## 返回值

返回 ChainInformationData 对象,包含以下字段:

| 字段           | 类型          | 说明               |
| -------------- | ------------- | ------------------ |
| chain_id       | int           | 链 ID              |
| block_number   | BlockNumber   | 当前区块高度       |
| gas_price      | Wei           | Gas 价格           |
| timeslot       | Optional[int] | 平均出块时间(可选) |
| client_version | Optional[str] | 客户端版本(可选)   |

## 示例代码

```python
# 获取所有信息
info = chain.get_chain_information()
print(f"Chain ID: {info.chain_id}")
print(f"Current Block: {info.block_number}")
print(f"Gas Price: {Web3.from_wei(info.gas_price, 'gwei')} Gwei")
if info.timeslot:
    print(f"Average Block Time: {info.timeslot}s")
if info.client_version:
    print(f"Client Version: {info.client_version}")

# 不显示 timeslot 和 client_version
info = chain.get_chain_information(show_timeslot=False, show_client_version=False)
```
