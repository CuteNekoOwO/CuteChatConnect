---
sidebar_position: 1
---

# 概述

**CuteChatConnect** 是一个可爱的即时通讯传输协议

下文将以 **C³** 作为 **CuteChatConnect** 的简称。

## 组成部分

一个最简单的应用由两部分构成 **适配器** 和 **客户端**

### 适配器

**适配器** 的作用是将平台特异API转换为 **C³** 通讯协议。**适配器** 需要实现文档中所有标注为 **必须实现** 的部分。

### 客户端

**客户端** 通过于 **适配器** 使用 **C³** 进行通讯，即可操作 **适配器** 背后的特定平台，而无须关心平台具体的API。