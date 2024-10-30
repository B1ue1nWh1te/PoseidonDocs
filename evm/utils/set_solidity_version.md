# set_solidity_version

选择 Solidity 版本,若该版本未安装则会自动安装。

## 方法定义

```python
@staticmethod
def set_solidity_version(solidity_version: str) -> None
```

## 参数说明

| 参数             | 类型 | 说明            |
| ---------------- | ---- | --------------- |
| solidity_version | str  | Solidity 版本号 |

## 返回值

无

## 示例代码

```python
from poseidon.evm import Utils

# 设置 Solidity 版本
Utils.set_solidity_version("0.8.20")
```
