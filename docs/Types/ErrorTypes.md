---
sidebar_position: 3
---

# 错误类型

当 **适配器** 接收到不支持的请求，或者在处理请求时发生错误，则会产生错误类型。

| 字段名称  | 数据类型 |   描述   |
| --------- | -------- | -------- |
|   Error   |  String  | 错误名称 |
|Discription|  String  | 错误描述 |

## ActionNotFound

当请求的 Action 未定义时产生此错误类型。

## ActionNotAllowed

当请求的 Action 不被允许时产生此错误类型。*例如在不支持删除消息的平台使用 "DeleteMessage" 动作。*

## TargetNotFound

当发送消息的目标不存在时产生此错误。

## TargetNotAllowed

当发送消息的目标不允许发送消息时产生此错误

## MessageTooLong

当尝试发送/更新的消息内容过长时产生此错误。

## MessageNotFound

当找不到目标消息时产生此错误。

## RepliedMessageNotFound

当找不到被回复的消息时产生此错误。

## UnknownSegmentType

当出现未知消息段类型时产生此错误。