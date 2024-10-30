# get_code

根据合约地址获取其字节码。

## 方法定义

```python
def get_code(self, address: ChecksumAddress) -> Optional[HexBytes]
```

## 参数说明

| 参数    | 类型            | 说明     |
| ------- | --------------- | -------- |
| address | ChecksumAddress | 合约地址 |

## 返回值

| 类型               | 说明       |
| ------------------ | ---------- |
| Optional[HexBytes] | 合约字节码 |

## 示例代码

```python
# 获取合约字节码
bytecode = chain.get_code("0x...")
if bytecode:
    print(f"Contract Bytecode: {bytecode.hex()}")
```
