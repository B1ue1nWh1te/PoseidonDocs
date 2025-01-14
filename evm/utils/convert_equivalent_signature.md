# convert_equivalent_signature

根据 ECDSA 签名可延展性原理，生成另一个等效的签名。

## 方法定义

```python
@staticmethod
def convert_equivalent_signature(signature: HexBytes) -> Optional[SignatureData]:
```

## 参数说明

| 参数      | 类型     | 说明     |
| --------- | -------- | -------- |
| signature | HexBytes | 原始签名 |

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
# 生成等效签名
original_signature = HexBytes("0x...")
equivalent_signature = Utils.convert_equivalent_signature(original_signature)

if equivalent_signature:
    print(f"Equivalent Signature: {equivalent_signature.signature.hex()}")
    print(f"r: {equivalent_signature.r.hex()}")
    print(f"s: {equivalent_signature.s.hex()}")
    print(f"v: {equivalent_signature.v.hex()}")
```
