# dump_storage

根据合约地址和起止插槽索引,批量获取存储值。

## 方法定义

```python
def dump_storage(self, address: ChecksumAddress, start_slot_index: int, end_slot_index: int) -> Optional[List[HexBytes]]
```

## 参数说明

| 参数             | 类型            | 说明         |
| ---------------- | --------------- | ------------ |
| address          | ChecksumAddress | 合约地址     |
| start_slot_index | int             | 起始插槽索引 |
| end_slot_index   | int             | 终止插槽索引 |

## 返回值

| 类型                     | 说明       |
| ------------------------ | ---------- |
| Optional[List[HexBytes]] | 存储值列表 |

## 示例代码

```python
# 获取前10个存储槽的值
storage_list = chain.dump_storage("0x...", 0, 10)
if storage_list:
    for i, value in enumerate(storage_list):
        print(f"Slot {i}: {value.hex()}")

# 获取指定范围的存储值
storage_list = chain.dump_storage("0x...", 100, 120)
if storage_list:
    for i, value in enumerate(storage_list, start=100):
        print(f"Slot {i}: {value.hex()}")
```
