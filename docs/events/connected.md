---
sidebar_position: 2
---

# 连接成功

当 **适配器** 于 **客户端** 成功建立 *WebSocket* 链接时， **适配器** 发送此事件。

| 字段名称 |    值    |
| -------- | -------- |
|   Type   |  "Event" |
|  Action  |"Connected"|
|   Data   |   Null   |

以下是一个JSON序列化后的例子

```JSON
{
    "Type": "Event",
    "Action": "Connected"
}
```