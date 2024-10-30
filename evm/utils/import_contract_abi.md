# import_contract_abi

导入指定的合约 ABI 文件内容。

## 方法定义

```python
@staticmethod
def import_contract_abi(file_path: str) -> Optional[dict]
```

## 参数说明

| 参数      | 类型 | 说明             |
| --------- | ---- | ---------------- |
| file_path | str  | ABI 文件完整路径 |

## 返回值

| 类型           | 说明     |
| -------------- | -------- |
| Optional[dict] | ABI 内容 |

## 示例代码

```python
# 导入 ABI 文件
abi = Utils.import_contract_abi("Token.abi.json")
if abi:
    print(f"Imported ABI: {abi}")
```
