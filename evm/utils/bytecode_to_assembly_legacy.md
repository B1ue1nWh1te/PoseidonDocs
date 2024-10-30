# bytecode_to_assembly_legacy

将 EVM Bytecode 转为 EVM Assembly。由于依赖的第三方库 pyevmasm 很久没有更新,所以该功能不一定能支持最新的 EVM 版本。

## 方法定义

```python
@staticmethod
def bytecode_to_assembly_legacy(bytecode: HexBytes) -> Optional[str]
```

## 参数说明

| 参数     | 类型     | 说明         |
| -------- | -------- | ------------ |
| bytecode | HexBytes | EVM Bytecode |

## 返回值

| 类型          | 说明         |
| ------------- | ------------ |
| Optional[str] | EVM Assembly |

## 示例代码

```python
# 将字节码转换为汇编
bytecode = HexBytes("0x6080604052...")
assembly = Utils.bytecode_to_assembly_legacy(bytecode)
if assembly:
    print(f"Assembly:\n{assembly}")
```
