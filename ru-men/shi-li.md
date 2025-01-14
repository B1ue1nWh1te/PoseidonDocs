# 示例

* [测试样例](https://github.com/B1ue1nWh1te/Poseidon/tree/main/tests)
* [模板库](https://github.com/B1ue1nWh1te/PoseidonTemplate)

以下通过对比 Poseidon 与 web3.py 的使用，展示 Poseidon 的简洁性优势。

### 使用 Poseidon

```python
from poseidon.evm import Chain, Account, Contract, Utils

rpc_url = "https://<RPC_URL>"
chain = Chain(rpc_url)

address, private_key = Utils.generate_new_account()
account = Account(chain, private_key)
signature_data = account.sign_message_string("test")
signed_message_data = Utils.recover_message_string("test", signature_data.signature_data.signature)
account.send_transaction(to=ZERO_ADDRESS, data="0x", value=1)

Utils.set_solidity_version("0.8.28")
abi, bytecode = Utils.compile_solidity_contract("./Contract.sol", "Contract")
tx_receipt = account.deploy_contract(abi, bytecode)

contract: Contract = tx_receipt.contract
contract.call_function("anyWriteFunction", "(param1)", "(param2)")
contract.read_only_call_function("anyReadOnlyFunction", "(param1)", "(param2)")
```

### 使用 web3.py

```python
from web3 import Web3
from eth_account import Account as Web3Account
from eth_account.messages import encode_defunct
from solcx import compile_source, install_solc
import json

w3 = Web3(Web3.HTTPProvider("https://<RPC_URL>"))

account = Web3Account.create()
address = account.address
private_key = account.key.hex()
message = encode_defunct(text="test")
signed_message = w3.eth.account.sign_message(message, private_key=private_key)
recovered_address = w3.eth.account.recover_message(message, signature=signed_message.signature)
transaction = {
    'nonce': w3.eth.get_transaction_count(address),
    'to': ZERO_ADDRESS,
    'value': 1,
    'gas': 21000,
    'gasPrice': w3.eth.gas_price,
    'data': '0x'
}
signed_txn = w3.eth.account.sign_transaction(transaction, private_key)
tx_hash = w3.eth.send_raw_transaction(signed_txn.rawTransaction)
tx_receipt = w3.eth.wait_for_transaction_receipt(tx_hash)

install_solc('0.8.28')
with open('./Contract.sol', 'r') as file:
    source = file.read()
compiled_sol = compile_source(source)
contract_interface = compiled_sol['<stdin>:Contract']
bytecode = contract_interface['bin']
abi = contract_interface['abi']
contract = w3.eth.contract(abi=abi, bytecode=bytecode)
transaction = contract.constructor().build_transaction({
    'from': address,
    'nonce': w3.eth.get_transaction_count(address),
    'gas': 2000000,
    'gasPrice': w3.eth.gas_price
})
signed_txn = w3.eth.account.sign_transaction(transaction, private_key)
tx_hash = w3.eth.send_raw_transaction(signed_txn.rawTransaction)
tx_receipt = w3.eth.wait_for_transaction_receipt(tx_hash)

contract_instance = w3.eth.contract(address=tx_receipt.contractAddress, abi=abi)
write_txn = contract_instance.functions.anyWriteFunction("(param1)", "(param2)").build_transaction({
    'from': address,
    'nonce': w3.eth.get_transaction_count(address),
    'gas': 200000,
    'gasPrice': w3.eth.gas_price
})
signed_txn = w3.eth.account.sign_transaction(write_txn, private_key)
tx_hash = w3.eth.send_raw_transaction(signed_txn.rawTransaction)
tx_receipt = w3.eth.wait_for_transaction_receipt(tx_hash)
result = contract_instance.functions.anyReadOnlyFunction("(param1)", "(param2)").call()
```
