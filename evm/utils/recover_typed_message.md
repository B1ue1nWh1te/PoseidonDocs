# recover_typed_message

通过结构化消息数据和签名还原出签署者的账户地址。

## 方法定义

```python
@staticmethod
def recover_typed_message(domain_data: dict, message_types: dict, message_data: dict, signature: HexBytes) -> Optional[SignedMessageData]
```

## 参数说明

| 参数          | 类型     | 说明         |
| ------------- | -------- | ------------ |
| domain_data   | dict     | 域数据       |
| message_types | dict     | 消息类型定义 |
| message_data  | dict     | 消息数据     |
| signature     | HexBytes | 签名         |

## 返回值

返回 SignedMessageData 对象,包含以下字段:

| 字段           | 类型            | 说明       |
| -------------- | --------------- | ---------- |
| message_hash   | HexBytes        | 消息哈希   |
| message        | str             | 原始消息   |
| signer         | ChecksumAddress | 签名者地址 |
| signature_data | SignatureData   | 签名数据   |

## 示例代码

```python
# 恢复 EIP-712 结构化数据签名者
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

signature = HexBytes("0x...")  # 65 字节的签名
signed_data = Utils.recover_typed_message(domain_data, message_types, message_data, signature)
if signed_data:
    print(f"Signer: {signed_data.signer}")
```
