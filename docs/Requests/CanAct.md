---
sidebar_position: 3
---

# 查询请求动作 CanAct

**Action: "CanAct"**
**必须实现**

**客户端** 向 **适配器** 询问是否支持特定请求动作。

## 请求

Data为要查询的请求动作组成的数组。

## 响应

Data为被查询请求动作中可用请求动作组成的数组。

## 例子

请求：
```JSON
{
    "Type": "Request",
    "Action": "CanAct",
    "ID": 1234,
    "Data": ["SendMessage", "DeleteMessage", "UpdateMessage"]
}
```

响应：
```JSON {5}
{
    "Type": "Respond",
    "Action": "CanAct",
    "ID": 1234,
    "Data": ["SendMessage"] // 查询的三个Action中只有"SendMessage"可用
}
```