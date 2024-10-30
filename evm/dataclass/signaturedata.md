# SignatureData

签名数据结构。

## 字段说明

| 字段      | 类型     | 说明      |
| --------- | -------- | --------- |
| signature | HexBytes | 完整签名  |
| r         | HexBytes | 签名 r 值 |
| s         | HexBytes | 签名 s 值 |
| v         | HexBytes | 签名 v 值 |

## 示例代码

```python
# 从签名生成签名数据
signature = HexBytes("0x...")  # 65 字节的签名
signature_data: SignatureData = Utils.generate_signature_data_with_signature(signature)

print(f"Full Signature: {signature_data.signature.hex()}")
print(f"R: {signature_data.r.hex()}")
print(f"S: {signature_data.s.hex()}")
print(f"V: {signature_data.v.hex()}")
```
