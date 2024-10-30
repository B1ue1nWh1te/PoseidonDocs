# SignedMessageData

已签名消息数据结构。

## 字段说明

| 字段           | 类型            | 说明       |
| -------------- | --------------- | ---------- |
| message_hash   | HexBytes        | 消息哈希   |
| message        | Optional[str]   | 原始消息   |
| signer         | ChecksumAddress | 签名者地址 |
| signature_data | SignatureData   | 签名数据   |

## 示例代码

```python
# 签名消息
message = "Hello, Ethereum!"
signed: SignedMessageData = account.sign_message_string(message)

print(f"Message: {signed.message}")
print(f"Message Hash: {signed.message_hash.hex()}")
print(f"Signer: {signed.signer}")
print(f"Signature: {signed.signature_data.signature.hex()}")
```
