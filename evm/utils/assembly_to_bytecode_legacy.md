# assembly_to_bytecode_legacy

将 EVM Assembly 转为 EVM Bytecode。由于依赖的第三方库 pyevmasm 很久没有更新,所以该功能不一定能支持最新的 EVM 版本。

## 方法定义

```python
@staticmethod
def assembly_to_bytecode_legacy(assembly: str) -> Optional[HexBytes]
```

## 参数说明

| 参数     | 类型 | 说明         |
| -------- | ---- | ------------ |
| assembly | str  | EVM Assembly |

## 返回值

| 类型               | 说明         |
| ------------------ | ------------ |
| Optional[HexBytes] | EVM Bytecode |

## 示例代码

```python
# 将汇编转换为字节码
assembly = """
    PUSH1 0x80
    PUSH1 0x40
    MSTORE
    CALLVALUE
    DUP1
    ISZERO
    PUSH2 0x000f
    JUMPI
"""
bytecode = Utils.assembly_to_bytecode_legacy(assembly)
if bytecode:
    print(f"Bytecode: {bytecode.hex()}")
```
