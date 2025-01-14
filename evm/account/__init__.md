# \_\_init\_\_

实例初始化。通过私钥导入账户并与 Chain 实例绑定。

## 方法定义

```python
def __init__(self, chain: Chain, private_key: HexBytes) -> None
```

## 参数说明

| 参数           | 类型       | 说明      |
| ------------ | -------- | ------- |
| chain        | Chain    | EVM 链实例 |
| private\_key | HexBytes | 账户私钥    |

## 成员变量

| 变量           | 类型              | 说明                             |
| ------------ | --------------- | ------------------------------ |
| eth\_account | LocalAccount    | eth\_account 的 LocalAccount 实例 |
| address      | ChecksumAddress | 账户地址                           |
| private\_key | HexBytes        | 账户私钥                           |

## 示例代码

```python
from poseidon.evm import Chain, Account
from hexbytes import HexBytes

# 连接到链
chain = Chain("https://eth-sepolia.g.alchemy.com/v2/YOUR-API-KEY")

# 导入账户
private_key = HexBytes("0x...")  # 你的私钥
account = Account(chain, private_key)

print(f"Account Address: {account.address}")
```
