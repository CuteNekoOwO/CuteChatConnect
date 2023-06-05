---
sidebar_position: 1
---

# 包装类型

包装类型包括 **事件包装类型** ， **请求包装类型** ， **响应包装类型** 和 **错误包装类型**。

一个基本的包装类型所需字段如表格所示

| 字段名称 | 数据类型 |   描述   |
| -------- | -------- | -------- |
|   Type   | [见下文] | 包装类型 |
|  Action  |  String  |   动作   |
|    ID    |  Number? |  请求ID  |
|   Date   |  Object? |   数据   |

##  事件包装类型

该包装类型的 **Type** 字段的值始终为 `"Event"` ， **Action** 和 **Date** 由发送的事件决定。 事件类型不需要 **ID**。

## 请求包装类型

该包装类型的 **Type** 字段的值始终为 `"Request"` ， **Action** 和 **Date** 由发送的请求决定。 **ID** 为 **客户端** 生成的 **唯一请求ID**。

## 响应包装类型

该包装类型的 **Type** 字段的值始终为 `"Respond"` ， **Action**， **Date** 和 **ID** 由该响应对应的请求决定。

## 错误包装类型

该包装类型的 **Type** 字段的值始终为 `"Error"` ， **Action** 和 **ID** 由该响应对应的请求决定， **Date** 为一个 [**错误类型**](./ErrorTypes) 对象。

例如，当发生 [ActionNotFound](./ErrorTypes#actionnotfound) 错误时，客户端将会收到这样的数据：

```JSON
{
    "Type": "Error",
    "Action": "SomeActionHere",
    "ID": 1234,
    "Data": {
        "Error": "ActionNotFound",
        "Discription": "Action不存在"
    }
}
```