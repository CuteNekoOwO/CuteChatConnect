---
sidebar_position: 2
---

# 订阅 Subscribe

**Action: "SubScribe"**

连接建立后，**适配器** 默认不会主动向 **客户端** 推送任何数据。**客户端** 应在建立连接并收到 [连接成功](../events/connected) 事件后主动发起此请求进行订阅。

订阅状态与 WebSocket连接 有相同的生命周期。当 WebSocket连接 被关闭时订阅状态失效。若因网络等问题导致 WebSocket连接 意外断开，请在重新建立连接后重新订阅消息。

## 请求

Data为消息来源组成的数组，可包含以下元素中的一个或多个。

- "System"
- "Private"
- "Private:{ID}"
- "Group"
- "Group:{ID}"

其中`{ID}`可以为用户ID或群组ID，可用于仅订阅特定用户或群组的消息。

多次请求后**仅最后一次**的订阅请求生效。不支持的消息类型将会被**忽略**。

## 响应

Data中包含成功订阅的消息类型。该请求永远**不应产生错误**。

## 例子

请求：
```JSON
{
    "Type": "Request",
    "Action": "Subscribe",
    "ID": 1234,
    "Data": ["System", "Private", "Group:12345"]
}
```

响应：
```JSON
{
    "Type": "Respond",
    "Action": "Subscribe",
    "ID": 1234,
    "Data": ["System", "Private", "Group:12345"]
}
```

## 另一个例子

请求：
```JSON {5}
{
    "Type": "Request",
    "Action": "Subscribe",
    "ID": 2333,
    "Data": ["meow", "System"] // 包含不支持的消息类型
}
```

响应：
```JSON {5}
{
    "Type": "Respond",
    "Action": "Subscribe",
    "ID": 2333,
    "Data": ["System"] // 忽略不支持的消息类型
}
```
