---
title: 返回特定用户的特定信息
TOCTitle: 返回特定用户的特定信息
ms:assetid: bbee85bd-d8a7-4b28-90d7-45c43eee48f6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362838(v=OCS.15)
ms:contentKeyID: 56271202
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回特定用户的特定信息

 

_**上一次修改主题：** 2015-06-22_

默认情况下，[Get-CsOnlineUser](get-csonlineuser.md) cmdlet 返回每个 Skype for Business Online 用户帐户的大量信息。如果您仅对一小部分信息感兴趣，请将返回的数据通过管道传递到 **Select-Object** cmdlet。例如，此命令返回用户 Ken Myer 的所有数据，然后使用 **Select-Object** cmdlet 将屏幕上显示的信息限制为 Ken 的 Active Directory 域服务显示名称和拨号计划：

    Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan

以下命令可返回所有用户的显示名称和拨号计划。

    Get-CsOnlineUser | Select-Object DisplayName, DialPlan

要查找 Skype for Business Online 用户帐户的属性，请使用此命令：

    Get-CsOnlineUser | Get-Member

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

