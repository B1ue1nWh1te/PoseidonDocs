# \_\_init\_\_

实例初始化。根据给定的节点 RPC 地址以 HTTP/HTTPS 方式进行连接，可通过代理访问。

## 方法定义

```python
def __init__(self, rpc_url: str, request_params: Optional[dict] = None) -> None
```

## 参数说明

| 参数              | 类型              | 说明                   |
| --------------- | --------------- | -------------------- |
| rpc\_url        | str             | 节点 RPC 地址            |
| request\_params | Optional\[dict] | 连接时使用的 request 参数,可选 |

当需要使用代理进行访问时，request\_params 示例:

```python
request_params = {
    "proxies": {
        "http": "http://localhost:<ProxyPort>",
        "https": "http://localhost:<ProxyPort>"
    }
}
```

## 成员变量

| 变量        | 类型                    | 说明                          |
| --------- | --------------------- | --------------------------- |
| chain\_id | int                   | 链 ID                        |
| provider  | web3.HTTPProvider     | web3.py 原生的 HTTPProvider 实例 |
| eth       | web3.HTTPProvider.eth | HTTPProvider 实例中的 eth 模块    |

## 示例代码

```python
from poseidon.evm import Chain

# 直接连接
chain = Chain("https://eth-sepolia.g.alchemy.com/v2/YOUR-API-KEY")

# 使用代理连接
proxy_params = {
    "proxies": {
        "http": "http://localhost:7890",
        "https": "http://localhost:7890"
    }
}
chain = Chain("https://eth-sepolia.g.alchemy.com/v2/YOUR-API-KEY", proxy_params)
```
