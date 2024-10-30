# sign_message_string

对消息字符串进行签名。

## 方法定义

```python
def sign_message_string(self, message: str) -> Optional[SignedMessageData]
```

## 参数说明

| 参数    | 类型 | 说明             |
| ------- | ---- | ---------------- |
| message | str  | 待签名消息字符串 |

## 返回值

返回 SignedMessageData 对象,包含以下字段:

| 字段           | 类型            | 说明       |
| -------------- | --------------- | ---------- |
| message_hash   | HexBytes        | 消息哈希   |
| message        | str             | 原始消息   |
| signer         | ChecksumAddress | 签名者地址 |
| signature_data | SignatureData   | 签名数据   |

SignatureData 包含以下字段:

| 字段      | 类型     | 说明      |
| --------- | -------- | --------- |
| signature | HexBytes | 完整签名  |
| r         | HexBytes | 签名 r 值 |
| s         | HexBytes | 签名 s 值 |
| v         | HexBytes | 签名 v 值 |

## 示例代码

```python
# 签名消息
message = "Hello, Ethereum!"
signed = account.sign_message_string(message)

if signed:
    print(f"Message: {signed.message}")
    print(f"Message Hash: {signed.message_hash.hex()}")
    print(f"Signer: {signed.signer}")
    print(f"Signature: {signed.signature_data.signature.hex()}")
```
