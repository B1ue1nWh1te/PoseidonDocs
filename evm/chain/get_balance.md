# get_balance

根据账户地址获取其原生代币余额。

## 方法定义

```python
def get_balance(self, address: ChecksumAddress) -> Optional[Wei]
```

## 参数说明

| 参数    | 类型            | 说明     |
| ------- | --------------- | -------- |
| address | ChecksumAddress | 账户地址 |

## 返回值

| 类型          | 说明                  |
| ------------- | --------------------- |
| Optional[Wei] | 账户原生代币余额(Wei) |

## 示例代码

```python
# 获取账户余额
balance = chain.get_balance("0x...")
if balance is not None:
    print(f"Balance: {Web3.from_wei(balance, 'ether')} ETH")
```
