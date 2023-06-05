---
sidebar_position: 4
---

# 消息类型

与消息相关的类型

## Message

| 字段名称  | 数据类型 | 描述        |
| --------- | -------- | ----------- |
| MessageID |  Number  | 消息ID |
| Time      |  Number  | 消息时间，unix时间戳。 |
| From      |  [User](./CommonTypes#user) | 发送消息的用户 |
| Chat      |  [Chat](./CommonTypes#chat) | 消息所属会话 |
| Reply     |  Number? | 被回复的消息ID。不回复则无此字段。 |


## Segment

消息段是消息组成的基本元素。

| 字段名称 | 数据类型 | 描述        |
| -------- | -------- | ----------- |
| Type     | String   | [消息段类型](#消息段类型) |
| Text     | Srting?  | / |
| Mention  | Number?  | / |
| FileID   | Number?  | / |


## 消息段类型

### Text

纯文本类型，文本内容位于 Text 字段。

### RichText

富文本类型，文本内容位于 Text 字段，使用类HTML方法解析。

### Mention

提及(@)类型。被提及的用户ID位于 Mention 字段。提及全体成员时 Mention 值为 0。

### Picture

图片类型。图片文件ID位于 FileID 字段。

### Voice

语音类型。语音文件ID位于 FileID 字段。

### Video

视频类型。视频文件ID位于 FileID 字段。

### File

文件类型。文件ID位于 FileID 字段。