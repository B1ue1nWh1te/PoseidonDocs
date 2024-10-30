# encode_function_calldata

通过传入函数名及参数进行编码,生成调用该函数的 CallData。

## 方法定义

```python
def encode_function_calldata(self, function_name: str, *args: Optional[Any]) -> Optional[HexStr]
```

## 参数说明

| 参数          | 类型          | 说明     |
| ------------- | ------------- | -------- |
| function_name | str           | 函数名称 |
| \*args        | Optional[Any] | 函数参数 |

## 返回值

| 类型             | 说明         |
| ---------------- | ------------ |
| Optional[HexStr] | 调用数据编码 |

## 示例代码

```python
# 编码函数调用数据
calldata = contract.encode_function_calldata(
    "transfer",     # 函数名
    "0x...",       # 接收者地址
    1000           # 转账金额
)
if calldata:
    print(f"Encoded CallData: {calldata}")

# 使用编码后的数据手动构造交易
if calldata:
    receipt = account.send_transaction(
        to=contract.address,
        data=HexBytes(calldata)
    )
```
