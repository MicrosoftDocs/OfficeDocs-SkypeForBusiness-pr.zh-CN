---
title: 向用户分配音频会议提供商
TOCTitle: 向用户分配音频会议提供商
ms:assetid: 60db6896-9c5c-4d64-ab7e-10d91748587c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362791(v=OCS.15)
ms:contentKeyID: 56271143
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向用户分配音频会议提供商

 

_**上一次修改主题：** 2015-06-22_

[Set-CsUserAcp](set-csuseracp.md) cmdlet 为您提供一种方式向用户分配音频会议提供商：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "12065551219" -TollFreeNumbers "18005550712" -ParticipantPasscode "p@ssw0rd" -Domain "sip.contoso.com" -Name "Contoso ACP"

除非您已与指定提供商签订合同，否则此分配毫无意义。

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

