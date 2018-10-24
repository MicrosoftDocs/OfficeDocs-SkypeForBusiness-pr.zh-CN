---
title: Lync Server 2013：新的语音邮件功能
TOCTitle: 新的语音邮件功能
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49888493
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的语音邮件功能

 

_**上一次修改主题：** 2012-10-05_

Lync Server 2013 引入了语音邮件 Escape（用于管理语音邮件的增强）。此新功能可检测到呼叫路由到语音邮件的情况，防止在用户无机会应答呼叫的情况下直接将呼叫路由到用户的移动电话语音邮件。此情况在用户对其移动电话启用了同时响铃以及用户的移动电话关机、没电或不在服务区时发生。Voicemail Escape 检测到用户的移动电话语音邮件立即应答了呼叫，并且断开了发往移动电话语音邮件的呼叫。呼叫继续在用户的其他终结点上响铃，以便为用户提供应答呼叫的机会。如果用户未应答呼叫，则呼叫将路由到企业语音邮件中。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置语音电子邮件转义](lync-server-2013-configuring-voice-mail-escape.md)  

#### 概念

[Lync Server 2013 中新的企业语音功能](lync-server-2013-new-enterprise-voice-features.md)

