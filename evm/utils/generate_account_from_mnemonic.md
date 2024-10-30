# generate_account_from_mnemonic

将助记词转换为账户地址与私钥。参考 BIP-39 标准。

## 方法定义

```python
@staticmethod
def generate_account_from_mnemonic(mnemonic: str, passphrase: str = "", account_path: str = "m/44'/60'/0'/0/0") -> Optional[Tuple[ChecksumAddress, HexBytes]]
```

## 参数说明

| 参数         | 类型 | 说明                                  |
| ------------ | ---- | ------------------------------------- |
| mnemonic     | str  | 助记词字符串,以空格分隔               |
| passphrase   | str  | 助记词密码,可为空,默认为空字符串      |
| account_path | str  | 分层确定性钱包账户路径,默认为标准路径 |

## 返回值

| 类型                                       | 说明                       |
| ------------------------------------------ | -------------------------- |
| Optional[Tuple[ChecksumAddress, HexBytes]] | 由账户地址和私钥组成的元组 |

## 示例代码

```python
# 从助记词生成账户
mnemonic = "abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon about"
account_data = Utils.generate_account_from_mnemonic(
    mnemonic=mnemonic,
    passphrase="optional password",
    account_path="m/44'/60'/0'/0/1"  # 使用自定义路径
)

if account_data:
    address, private_key = account_data
    print(f"Generated Account Address: {address}")
    print(f"Private Key: {private_key.hex()}")
```
