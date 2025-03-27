# recover\_message\_hash

通过 EIP-191 消息哈希和签名还原出签署者的账户地址。

## 方法定义

```python
@staticmethod
def recover_message_hash(message_hash: HexBytes, signature: HexBytes) -> Optional[SignedMessageData]
```

## 参数说明

| 参数            | 类型       | 说明   |
| ------------- | -------- | ---- |
| message\_hash | HexBytes | 消息哈希 |
| signature     | HexBytes | 签名   |

## 返回值

返回 SignedMessageData 对象,包含以下字段:

| 字段              | 类型              | 说明      |
| --------------- | --------------- | ------- |
| message\_hash   | HexBytes        | 消息哈希    |
| message         | None            | 原始消息(无) |
| signer          | ChecksumAddress | 签名者地址   |
| signature\_data | SignatureData   | 签名数据    |

## 示例代码

```python
# 恢复消息哈希签名者
message_hash = HexBytes("0x...")  # 32 字节的消息哈希
signature = HexBytes("0x...")     # 65 字节的签名
signed_data = Utils.recover_message_hash(message_hash, signature)
if signed_data:
    print(f"Message Hash: {signed_data.message_hash.hex()}")
    print(f"Signer: {signed_data.signer}")
    print(f"Signature: {signed_data.signature_data.signature.hex()}")
```
