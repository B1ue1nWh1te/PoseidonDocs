# compile_solidity_contract

根据给定的参数使用 py-solc-x 编译合约。

## 方法定义

```python
@staticmethod
def compile_solidity_contract(file_path: str, contract_name: str, solidity_version: Optional[str] = None, evm_version: Optional[str] = None, optimize: bool = False, optimize_runs: int = 200, base_path: Optional[str] = None, allow_paths: Optional[str] = None) -> Optional[Tuple[dict, HexBytes]]
```

## 参数说明

| 参数             | 类型          | 说明                      |
| ---------------- | ------------- | ------------------------- |
| file_path        | str           | 合约代码文件路径          |
| contract_name    | str           | 要编译的合约的名称        |
| solidity_version | Optional[str] | 指定使用的 Solidity 版本  |
| evm_version      | Optional[str] | 指定编译时使用的 EVM 版本 |
| optimize         | bool          | 是否开启优化器            |
| optimize_runs    | int           | 优化器运行次数参数        |
| base_path        | Optional[str] | 指定基础路径              |
| allow_paths      | Optional[str] | 指定许可路径              |

## 返回值

| 类型                            | 说明                          |
| ------------------------------- | ----------------------------- |
| Optional[Tuple[dict, HexBytes]] | 由 ABI 和 Bytecode 组成的元组 |

## 示例代码

```python
# 编译合约
contract_data = Utils.compile_solidity_contract(
    file_path="Token.sol",
    contract_name="Token",
    solidity_version="0.8.20",
    optimize=True
)

if contract_data:
    abi, bytecode = contract_data
    print(f"Contract ABI: {abi}")
    print(f"Contract Bytecode: {bytecode.hex()}")
```
