# recover_message_string

通过消息原文和签名还原出签署者的账户地址。

## 方法定义

```python
@staticmethod
def recover_message_string(message: str, signature: HexBytes) -> Optional[SignedMessageData]
```

## 参数说明

| 参数      | 类型     | 说明     |
| --------- | -------- | -------- |
| message   | str      | 消息原文 |
| signature | HexBytes | 签名     |

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
# 恢复消息签名者
message = "Hello, Ethereum!"
signature = HexBytes("0x...")  # 65 字节的签名
signed_data = Utils.recover_message_string(message, signature)
if signed_data:
    print(f"Message: {signed_data.message}")
    print(f"Signer: {signed_data.signer}")
    print(f"Signature: {signed_data.signature_data.signature.hex()}")
```
