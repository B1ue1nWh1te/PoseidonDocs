# sign_message_hash

对消息哈希进行签名。

## 方法定义

```python
def sign_message_hash(self, message_hash: HexBytes) -> Optional[SignedMessageData]
```

## 参数说明

| 参数         | 类型     | 说明           |
| ------------ | -------- | -------------- |
| message_hash | HexBytes | 待签名消息哈希 |

## 返回值

返回 SignedMessageData 对象,包含以下字段:

| 字段           | 类型            | 说明         |
| -------------- | --------------- | ------------ |
| message_hash   | HexBytes        | 消息哈希     |
| message        | None            | 原始消息(无) |
| signer         | ChecksumAddress | 签名者地址   |
| signature_data | SignatureData   | 签名数据     |

SignatureData 包含以下字段:

| 字段      | 类型     | 说明      |
| --------- | -------- | --------- |
| signature | HexBytes | 完整签名  |
| r         | HexBytes | 签名 r 值 |
| s         | HexBytes | 签名 s 值 |
| v         | HexBytes | 签名 v 值 |

## 示例代码

```python
# 签名消息哈希
message_hash = HexBytes("0x...")
signed = account.sign_message_hash(message_hash)

if signed:
    print(f"Message Hash: {signed.message_hash.hex()}")
    print(f"Signer: {signed.signer}")
    print(f"Signature: {signed.signature_data.signature.hex()}")
```
