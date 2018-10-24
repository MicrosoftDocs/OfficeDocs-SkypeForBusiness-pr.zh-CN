---
title: 返回有关您的音频会议提供商的信息
TOCTitle: 返回有关您的音频会议提供商的信息
ms:assetid: df9c8fc0-8bb6-4416-a5cc-aa9b1601a688
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362848(v=OCS.15)
ms:contentKeyID: 56271217
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回有关您的音频会议提供商的信息

 

_**上一次修改主题：** 2015-06-22_

要返回有关已分配给用户的音频会议提供商的信息，请使用 [Get-CsUserAcp](get-csuseracp.md) cmdlet 和以下语法：

    Get-CsUserAcp -Identity "Ken Myer" | Select-Object -ExpandProperty AcpInfo

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

