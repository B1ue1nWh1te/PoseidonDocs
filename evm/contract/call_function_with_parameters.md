# call_function_with_parameters

通过传入函数名称及参数来调用该合约内的函数(可指定发送的原生代币数量、Gas 价格、Gas 最大使用量)。

## 方法定义

```python
def call_function_with_parameters(self, value: Wei, gas_price: Optional[Wei], gas_limit: int, function_name: str, *args: Optional[Any]) -> Optional[TransactionReceiptData]
```

## 参数说明

| 参数          | 类型          | 说明                                |
| ------------- | ------------- | ----------------------------------- |
| value         | Wei           | 发送的原生代币数量                  |
| gas_price     | Optional[Wei] | Gas 价格,默认使用链上当前 gas_price |
| gas_limit     | int           | Gas 最大使用量                      |
| function_name | str           | 函数名称                            |
| \*args        | Optional[Any] | 函数参数                            |

## 返回值

返回值格式与 call_function 相同。

## 示例代码

```python
# 调用合约函数并发送 ETH
receipt = contract.call_function_with_parameters(
    value=Web3.to_wei(0.1, 'ether'),     # 发送 0.1 ETH
    gas_price=Web3.to_wei(50, 'gwei'),   # 使用 50 Gwei 的 gas 价格
    gas_limit=100000,                     # 设置 gas 限制为 100000
    "deposit",                            # 函数名
    "0x..."                              # 函数参数
)

if receipt and receipt.transaction_status:
    print(f"Transaction successful: {receipt.transaction_hash.hex()}")
```
