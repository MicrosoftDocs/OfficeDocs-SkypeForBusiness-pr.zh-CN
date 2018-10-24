---
title: Lync Server 2013：验证呼叫寄存的规范化规则
TOCTitle: 验证呼叫寄存的规范化规则
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398981(v=OCS.15)
ms:contentKeyID: 49314495
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证呼叫寄存的规范化规则

 

_**上一次修改主题：** 2012-09-11_

不能对 呼叫寄存通道进行规范化。检查拨号计划以确保未对通道号码进行规范化。如果必须创建其他规范化规则来阻止对通道进行规范化，请按照 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)中的过程来定义新的规范化规则，例如，“要匹配的模式”表示通道范围，“转换模式”为 **$1**。例如，如果 呼叫寄存通道范围是 7000 – 7999，则“要匹配的模式”为 **^(7\\d{3})$**，“转换模式”为 **$1**。

> [!IMPORTANT]
> 请确保拨号计划中的默认规范化规则不包含 <strong>^(\d*)</strong>。否则， 呼叫寄存规范化规则将始终不会运行。


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)

