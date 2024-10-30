# send_transaction_by_eip1559

发送自定义 EIP-1559 交易。

## 方法定义

```python
def send_transaction_by_eip1559(self, to: Optional[ChecksumAddress] = None, data: HexBytes = HexBytes("0x"), value: Wei = Wei(0), base_fee: Optional[Wei] = None, max_priority_fee: Optional[Wei] = None, gas_limit: int = 500000) -> Optional[TransactionReceiptData]
```

## 参数说明

| 参数             | 类型                      | 说明                                |
| ---------------- | ------------------------- | ----------------------------------- |
| to               | Optional[ChecksumAddress] | 接收者地址,为 None 时表示创建合约   |
| data             | HexBytes                  | 交易数据,默认为空                   |
| value            | Wei                       | 发送的原生代币数量,默认为 0         |
| base_fee         | Optional[Wei]             | 基础费用,默认使用链上当前 gas_price |
| max_priority_fee | Optional[Wei]             | 最高优先费用,默认使用链上建议值     |
| gas_limit        | int                       | Gas 最大使用量,默认为 500000        |

## 返回值

返回值格式与 send_transaction 相同。

## 示例代码

```python
# 发送 EIP-1559 交易
receipt = account.send_transaction_by_eip1559(
    to="0x...",
    value=Web3.to_wei(0.1, 'ether'),
    max_priority_fee=Web3.to_wei(2, 'gwei')
)
if receipt and receipt.transaction_status:
    print(f"Transaction successful: {receipt.transaction_hash.hex()}")
    print(f"Effective gas price: {Web3.from_wei(receipt.effective_gas_price, 'gwei')} Gwei")
```
