---
sidebar_position: 2
---

# 连接成功

**Action: "Connected"**
**必须实现**

当 **适配器** 于 **客户端** 成功建立 *WebSocket* 链接时， **适配器** 发送此事件。

Data 为 [**Status**](../Types/CommonTypes#Status) 类型的数据。


## 例子

以下是一个JSON序列化后的例子

```JSON
{
    "Type": "Event",
    "Action": "Connected",
    "Data": {
        "Online": true
    }
}
```