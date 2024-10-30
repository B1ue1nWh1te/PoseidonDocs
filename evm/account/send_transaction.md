# send_transaction

发送自定义 EIP-155 交易。

## 方法定义

```python
def send_transaction(self, to: Optional[ChecksumAddress] = None, data: HexBytes = HexBytes("0x"), value: Wei = Wei(0), gas_price: Optional[Wei] = None, gas_limit: int = 500000) -> Optional[TransactionReceiptData]
```

## 参数说明

| 参数      | 类型                      | 说明                                |
| --------- | ------------------------- | ----------------------------------- |
| to        | Optional[ChecksumAddress] | 接收者地址,为 None 时表示创建合约   |
| data      | HexBytes                  | 交易数据,默认为空                   |
| value     | Wei                       | 发送的原生代币数量,默认为 0         |
| gas_price | Optional[Wei]             | Gas 价格,默认使用链上当前 gas_price |
| gas_limit | int                       | Gas 最大使用量,默认为 500000        |

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
# 发送 ETH
receipt = account.send_transaction(
    to="0x...",
    value=Web3.to_wei(0.1, 'ether')
)
if receipt and receipt.transaction_status:
    print(f"Transaction successful: {receipt.transaction_hash.hex()}")

# 调用合约函数
contract_function_data = HexBytes("0x...")  # 合约函数的编码数据
receipt = account.send_transaction(
    to="0x...",  # 合约地址
    data=contract_function_data,
    gas_limit=100000
)
```
