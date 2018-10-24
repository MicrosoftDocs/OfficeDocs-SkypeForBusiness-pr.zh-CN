---
title: 防止自动准许匿名用户加入会议
TOCTitle: 防止自动准许匿名用户加入会议
ms:assetid: 23f120d2-4c39-4509-aa1f-4d186a525075
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362775(v=OCS.15)
ms:contentKeyID: 56271128
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 防止自动准许匿名用户加入会议

 

_**上一次修改主题：** 2015-06-22_

要防止自动准许匿名用户加入联机会议，请使用 [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md) cmdlet 并将 AdmitAnonymousUsersByDefault 属性设置为 False ($False)：

    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

要启用自动准许，请再次将 AdmitAnonymousUsersByDefault 属性设置为 True ($True)：

    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

