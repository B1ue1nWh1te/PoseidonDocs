# generate_signature_data_with_signature

使用签名数据生成 SignatureData 对象。

## 方法定义

```python
@staticmethod
def generate_signature_data_with_signature(signature: HexBytes) -> Optional[SignatureData]
```

## 参数说明

| 参数      | 类型     | 说明     |
| --------- | -------- | -------- |
| signature | HexBytes | 签名数据 |

## 返回值

返回 SignatureData 对象,包含以下字段:

| 字段      | 类型     | 说明      |
| --------- | -------- | --------- |
| signature | HexBytes | 完整签名  |
| r         | HexBytes | 签名 r 值 |
| s         | HexBytes | 签名 s 值 |
| v         | HexBytes | 签名 v 值 |

## 示例代码

```python
# 从签名生成签名数据
signature = HexBytes("0x...")  # 65 字节的签名数据
signature_data = Utils.generate_signature_data_with_signature(signature)
if signature_data:
    print(f"Signature: {signature_data.signature.hex()}")
    print(f"R: {signature_data.r.hex()}")
    print(f"S: {signature_data.s.hex()}")
    print(f"V: {signature_data.v.hex()}")
```
