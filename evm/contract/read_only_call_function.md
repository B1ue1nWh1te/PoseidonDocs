# read_only_call_function

通过传入函数名称及参数来调用该合约内的只读函数。

## 方法定义

```python
def read_only_call_function(self, function_name: str, *args: Optional[Any]) -> Optional[Any]
```

## 参数说明

| 参数          | 类型          | 说明     |
| ------------- | ------------- | -------- |
| function_name | str           | 函数名称 |
| \*args        | Optional[Any] | 函数参数 |

## 返回值

| 类型          | 说明           |
| ------------- | -------------- |
| Optional[Any] | 只读函数返回值 |

## 示例代码

```python
# 调用只读函数
balance = contract.read_only_call_function(
    "balanceOf",    # 函数名
    "0x..."        # 账户地址
)
if balance is not None:
    print(f"Balance: {balance}")

# 调用多参数的只读函数
result = contract.read_only_call_function(
    "allowance",    # 函数名
    "0x...",       # owner 地址
    "0x..."        # spender 地址
)
```
