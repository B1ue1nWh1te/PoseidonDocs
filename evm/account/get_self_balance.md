# get_self_balance

获取当前账户的原生代币余额。

## 方法定义

```python
def get_self_balance(self) -> Optional[Wei]
```

## 参数说明

无

## 返回值

| 类型          | 说明                   |
| ------------- | ---------------------- |
| Optional[Wei] | 当前账户的原生代币余额 |

## 示例代码

```python
# 获取账户余额
balance = account.get_self_balance()
if balance is not None:
    print(f"Balance: {Web3.from_wei(balance, 'ether')} ETH")
```
