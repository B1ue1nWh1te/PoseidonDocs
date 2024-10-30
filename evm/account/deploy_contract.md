# deploy_contract

部署合约。

## 方法定义

```python
def deploy_contract(self, abi: dict, bytecode: HexBytes, value: Wei = Wei(0), gas_price: Optional[Wei] = None, *args: Optional[Any]) -> Optional[TransactionReceiptData]
```

## 参数说明

| 参数      | 类型          | 说明                                |
| --------- | ------------- | ----------------------------------- |
| abi       | dict          | 合约 ABI                            |
| bytecode  | HexBytes      | 合约字节码                          |
| value     | Wei           | 发送给合约的原生代币数量,默认为 0   |
| gas_price | Optional[Wei] | Gas 价格,默认使用链上当前 gas_price |
| \*args    | Optional[Any] | 传给合约构造函数的参数              |

## 返回值

返回 TransactionReceiptData 对象,当合约部署成功时,返回值中会额外添加"contract"字段(Contract 实例)。其他字段与 send_transaction 相同。

## 示例代码

```python
# 部署合约
abi = [...] # 合约 ABI
bytecode = HexBytes("0x...") # 合约字节码

receipt = account.deploy_contract(
    abi=abi,
    bytecode=bytecode,
    value=Web3.to_wei(0.1, 'ether'),  # 发送 0.1 ETH 到合约
    gas_price=Web3.to_wei(50, 'gwei')  # 使用 50 Gwei 的 gas 价格
)

if receipt and receipt.transaction_status:
    print(f"Contract deployed at: {receipt.contract_address}")
    # 可以直接使用返回的合约实例
    contract = receipt.contract
```
