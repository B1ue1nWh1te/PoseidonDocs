# generate_new_account

创建新账户。

## 方法定义

```python
@staticmethod
def generate_new_account() -> Optional[Tuple[ChecksumAddress, HexBytes]]
```

## 参数说明

无

## 返回值

| 类型                                       | 说明                       |
| ------------------------------------------ | -------------------------- |
| Optional[Tuple[ChecksumAddress, HexBytes]] | 由账户地址和私钥组成的元组 |

## 示例代码

```python
# 创建新账户
account_data = Utils.generate_new_account()
if account_data:
    address, private_key = account_data
    print(f"New Account Address: {address}")
    print(f"Private Key: {private_key.hex()}")
```
