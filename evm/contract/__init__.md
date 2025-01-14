# \_\_init\_\_

实例初始化。通过合约地址与 ABI 来实例化合约，并与 Account 绑定，后续所有对该合约的调用都会由这一账户发起。

## 方法定义

```python
def __init__(self, account: Account, address: ChecksumAddress, abi: dict) -> None
```

## 参数说明

| 参数      | 类型              | 说明     |
| ------- | --------------- | ------ |
| account | Account         | 账户实例   |
| address | ChecksumAddress | 合约地址   |
| abi     | dict            | 合约 ABI |

## 成员变量

| 变量               | 类型                             | 说明                      |
| ---------------- | ------------------------------ | ----------------------- |
| address          | ChecksumAddress                | 合约地址                    |
| web3py\_contract | web3.HTTPProvider.eth.Contract | web3.py 原生的 Contract 实例 |

## 示例代码

```python
from poseidon.evm import Chain, Account, Contract

# 连接到链并导入账户
chain = Chain("https://eth-mainnet.g.alchemy.com/v2/YOUR-API-KEY")
account = Account(chain, HexBytes("0x..."))  # 你的私钥

# 实例化合约
contract_address = "0x..."  # 合约地址
contract_abi = [...]  # 合约 ABI
contract = Contract(account, contract_address, contract_abi)
```
