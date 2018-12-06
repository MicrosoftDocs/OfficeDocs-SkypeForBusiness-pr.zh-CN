---
title: 返回有关已分配给用户的音频会议提供商的信息
TOCTitle: 返回有关已分配给用户的音频会议提供商的信息
ms:assetid: 7fae822f-9f6c-4381-95c5-879661027925
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362814(v=OCS.15)
ms:contentKeyID: 56271168
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回有关已分配给用户的音频会议提供商的信息

 

_**上一次修改主题：** 2015-06-22_

要返回有关已分配给用户的音频会议提供商的信息，请使用 [Get-CsUserAcp](get-csuseracp.md) cmdlet 和以下语法：

    Get-CsUserAcp -Identity "Ken Myer" | Select-Object -ExpandProperty AcpInfo

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

