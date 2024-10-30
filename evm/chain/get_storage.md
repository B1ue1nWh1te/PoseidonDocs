# get_storage

根据合约地址和存储插槽索引获取存储值。

## 方法定义

```python
def get_storage(self, address: ChecksumAddress, slot_index: int) -> Optional[HexBytes]
```

## 参数说明

| 参数       | 类型            | 说明         |
| ---------- | --------------- | ------------ |
| address    | ChecksumAddress | 合约地址     |
| slot_index | int             | 存储插槽索引 |

## 返回值

| 类型               | 说明   |
| ------------------ | ------ |
| Optional[HexBytes] | 存储值 |

## 示例代码

```python
# 获取存储值
storage = chain.get_storage("0x...", 0)
if storage:
    print(f"Storage Value: {storage.hex()}")
```
