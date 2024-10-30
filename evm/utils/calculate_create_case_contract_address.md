# calculate_create_case_contract_address

计算某账户以 CREATE 方式部署的合约的地址。

## 方法定义

```python
@staticmethod
def calculate_create_case_contract_address(deployer: ChecksumAddress, nonce: Nonce) -> Optional[ChecksumAddress]
```

## 参数说明

| 参数     | 类型            | 说明                              |
| -------- | --------------- | --------------------------------- |
| deployer | ChecksumAddress | 部署者地址                        |
| nonce    | Nonce           | 部署者发送合约部署交易的 nonce 值 |

## 返回值

| 类型                      | 说明             |
| ------------------------- | ---------------- |
| Optional[ChecksumAddress] | 计算出的合约地址 |

## 示例代码

```python
# 计算合约地址
contract_address = Utils.calculate_create_case_contract_address(
    deployer="0x...",  # 部署者地址
    nonce=5            # 部署者的 nonce 值
)
if contract_address:
    print(f"Contract will be deployed at: {contract_address}")
```
