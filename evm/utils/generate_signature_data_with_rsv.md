# generate_signature_data_with_rsv

使用 R,S,V 生成 SignatureData 对象。

## 方法定义

```python
@staticmethod
def generate_signature_data_with_rsv(r: HexBytes, s: HexBytes, v: HexBytes) -> Optional[SignatureData]
```

## 参数说明

| 参数 | 类型     | 说明      |
| ---- | -------- | --------- |
| r    | HexBytes | 签名 r 值 |
| s    | HexBytes | 签名 s 值 |
| v    | HexBytes | 签名 v 值 |

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
# 从 R,S,V 生成签名数据
r = HexBytes("0x...")  # 32 字节
s = HexBytes("0x...")  # 32 字节
v = HexBytes("0x...")  # 1 字节
signature_data = Utils.generate_signature_data_with_rsv(r, s, v)
if signature_data:
    print(f"Combined Signature: {signature_data.signature.hex()}")
```
