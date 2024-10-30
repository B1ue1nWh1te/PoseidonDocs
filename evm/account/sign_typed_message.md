# sign_typed_message

对结构化消息数据进行 EIP-712 签名。

## 方法定义

```python
def sign_typed_message(self, domain_data: dict, message_types: dict, message_data: dict) -> Optional[SignedMessageData]
```

## 参数说明

| 参数          | 类型 | 说明             |
| ------------- | ---- | ---------------- |
| domain_data   | dict | 域数据           |
| message_types | dict | 消息类型定义     |
| message_data  | dict | 待签名的消息数据 |

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
# EIP-712 结构化数据签名
domain_data = {
    "name": "MyDApp",
    "version": "1",
    "chainId": 1,
    "verifyingContract": "0x..."
}

message_types = {
    "Person": [
        {"name": "name", "type": "string"},
        {"name": "wallet", "type": "address"}
    ]
}

message_data = {
    "name": "Bob",
    "wallet": "0x..."
}

signed = account.sign_typed_message(domain_data, message_types, message_data)

if signed:
    print(f"Message Hash: {signed.message_hash.hex()}")
    print(f"Signer: {signed.signer}")
    print(f"Signature: {signed.signature_data.signature.hex()}")
```
