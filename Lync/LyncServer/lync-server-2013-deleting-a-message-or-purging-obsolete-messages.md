---
title: Lync Server 2013：删除消息或清除作废的消息
TOCTitle: 删除消息或清除作废的消息
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215874(v=OCS.15)
ms:contentKeyID: 49312616
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中删除消息或清除作废的消息

 

_**上一次修改主题：** 2014-02-05_

持久聊天管理员可以从持久聊天聊天室中删除一条消息（并可以选择性地将该消息替换为另一条消息）。此外，作为正在进行的维护工作的一部分，管理员可以清除已作废的消息以便最大程度地减小数据库的增长量。例如，以下 Windows PowerShell 命令从 ITChatRoom 聊天室中删除由用户 kenmyer@litwareinc.com 发布的所有消息：

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

而且在此示例中，任何已删除的消息都将替换为说明消息已不再可用的通知：

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

有关详细信息，请参阅 [Remove-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet 的帮助主题。

