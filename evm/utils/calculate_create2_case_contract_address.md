# calculate_create2_case_contract_address

计算某合约账户以 CREATE2 方式部署的另一个合约的地址。

## 方法定义

```python
@staticmethod
def calculate_create2_case_contract_address(deployer: ChecksumAddress, salt: HexStr, creation_code: HexStr) -> Optional[ChecksumAddress]
```

## 参数说明

| 参数          | 类型            | 说明                                   |
| ------------- | --------------- | -------------------------------------- |
| deployer      | ChecksumAddress | 部署者地址(此处应该为合约地址)         |
| salt          | HexStr          | 盐值                                   |
| creation_code | HexStr          | 合约的创建时字节码(与运行时字节码不同) |

## 返回值

| 类型                      | 说明             |
| ------------------------- | ---------------- |
| Optional[ChecksumAddress] | 计算出的合约地址 |

## 示例代码

```python
# 计算 CREATE2 部署的合约地址
contract_address = Utils.calculate_create2_case_contract_address(
    deployer="0x...",      # 工厂合约地址
    salt="0x123...",       # 盐值
    creation_code="0x..."  # 创建时字节码
)
if contract_address:
    print(f"Contract will be deployed at: {contract_address}")
```
