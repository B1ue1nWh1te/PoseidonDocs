# set_need_confirm_before_send_transaction

设置在通过该账户发送每一笔交易之前是否需要控制台回车确认。开启后会在每笔交易即将发送前暂停流程，在控制台询问是否发送该笔交易。

## 方法定义

```python
def set_need_confirm_before_send_transaction(self, need_confirm: bool = True) -> None
```

## 参数说明

| 参数         | 类型 | 说明                   |
| ------------ | ---- | ---------------------- |
| need_confirm | bool | 是否需要控制台回车确认 |

## 返回值

无

## 示例代码

```python
# 开启发送交易前的确认
account.set_need_confirm_before_send_transaction(True)

# 关闭发送交易前的确认
account.set_need_confirm_before_send_transaction(False)
```
