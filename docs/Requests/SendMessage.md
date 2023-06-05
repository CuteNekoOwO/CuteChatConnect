---
sidebar_position: 4
---

# 发送消息 SendMessage

**Action: "SendMessage"**

向指定目标发送一条消息。


## 请求

| 字段名称 | 数据类型 | 描述        |
| -------- | -------- | ----------- |
|  Target  |  String  | 消息发送的目标 |
|  Reply   | Number?  | 被回复的消息ID。不回复则无此字段。 |
|  Content | array[[Segment](../Types/MessageTypes#segment)] | 发送的消息内容 |

### Target

由于 **适配器** 的目标平台不同，目标可以有以下形式

- "@UserName" (直接指定用户名)
- "123456" (直接指定目标ID)
- "Group:23333" (发送到特定ID的群组)
- "" (无目标，平台没有多个目标因此不需要指定目标)

但是无论目标为何种形式，都应使用String类型传输。

## 响应

| 字段名称  | 数据类型 | 描述        |
| --------- | -------- | ----------- |
| MessageID |  Number  | 被发送的消息ID |

## 错误

可能发生的错误有

- [TargetNotFound](../Types/ErrorTypes#targetnotfound)
- [TargetNotAllowed](../Types/ErrorTypes#targetnotallowed)
- [MessageTooLong](../Types/ErrorTypes#messagetoolong)
- [RepliedMessageNotFound](../Types/ErrorTypes#repliedmessagenotfound)
- [UnknownSegmentType](../Types/ErrorTypes#unknownsegmenttype)