# decode_function_calldata

解码针对当前合约执行调用的 CallData,得出所调用的函数名称及其参数值。

## 方法定义

```python
def decode_function_calldata(self, calldata: HexStr) -> Optional[tuple]
```

## 参数说明

| 参数     | 类型   | 说明                          |
| -------- | ------ | ----------------------------- |
| calldata | HexStr | 对当前合约执行调用的 CallData |

## 返回值

| 类型            | 说明                         |
| --------------- | ---------------------------- |
| Optional[tuple] | 包含函数名称及其参数值的元组 |

返回的元组格式为: (function_name, parameters_dict)

- function_name: 函数名称
- parameters_dict: 包含参数名和值的字典

## 示例代码

```python
# 解码函数调用数据
calldata = "0xa9059cbb000000000000000000000000ab5801a7d398351b8be11c439e05c5b3259aec9b0000000000000000000000000000000000000000000000000de0b6b3a7640000"

result = contract.decode_function_calldata(calldata)
if result:
    function_name, parameters = result
    print(f"Function Name: {function_name}")
    print(f"Parameters: {parameters}")

# 编码后解码验证
encoded = contract.encode_function_calldata(
    "transfer",
    "0xab5801a7d398351b8be11c439e05c5b3259aec9b",
    Web3.to_wei(1, 'ether')
)
if encoded:
    decoded = contract.decode_function_calldata(encoded)
    print(f"Decoded: {decoded}")
```
