# call_function

通过传入函数名称及参数来调用该合约内的函数。

## 方法定义

```python
def call_function(self, function_name: str, *args: Optional[Any]) -> Optional[TransactionReceiptData]
```

## 参数说明

| 参数          | 类型          | 说明     |
| ------------- | ------------- | -------- |
| function_name | str           | 函数名称 |
| \*args        | Optional[Any] | 函数参数 |

## 返回值

返回 TransactionReceiptData 对象,包含以下字段:

| 字段               | 类型                       | 说明                           |
| ------------------ | -------------------------- | ------------------------------ |
| transaction_hash   | HexBytes                   | 交易哈希                       |
| block_number       | BlockNumber                | 区块高度                       |
| transaction_index  | int                        | 交易在区块中的索引             |
| transaction_status | int                        | 交易状态(1 成功,0 失败)        |
| transaction_type   | int                        | 交易类型                       |
| action             | str                        | 交易动作类型                   |
| sender             | ChecksumAddress            | 发送者地址                     |
| to                 | ChecksumAddress            | 接收者地址                     |
| nonce              | Nonce                      | 交易序号                       |
| value              | Wei                        | 转账金额                       |
| gas_used           | int                        | 实际使用的 Gas                 |
| gas_limit          | int                        | Gas 上限                       |
| gas_price          | Optional[Wei]              | Gas 价格                       |
| contract_address   | Optional[ChecksumAddress]  | 部署的合约地址(仅合约创建交易) |
| logs               | Optional[List[LogReceipt]] | 交易日志                       |
| input_data         | HexBytes                   | 交易输入数据                   |
| r                  | HexBytes                   | 签名 r 值                      |
| s                  | HexBytes                   | 签名 s 值                      |
| v                  | HexBytes                   | 签名 v 值                      |

## 示例代码

```python
# 调用合约函数
receipt = contract.call_function(
    "transfer",  # 函数名
    "0x...",    # 接收者地址
    1000        # 转账金额
)

if receipt and receipt.transaction_status:
    print(f"Transaction successful: {receipt.transaction_hash.hex()}")
    print(f"Gas used: {receipt.gas_used}")
```
