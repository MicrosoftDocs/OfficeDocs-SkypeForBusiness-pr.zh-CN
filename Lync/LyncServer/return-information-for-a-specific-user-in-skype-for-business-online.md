---
title: 返回特定用户的信息
TOCTitle: 返回特定用户的信息
ms:assetid: 6c8c2190-8e62-4f92-bbe9-4f692bd7ebf5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362803(v=OCS.15)
ms:contentKeyID: 56271163
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回特定用户的信息

 

_**上一次修改主题：** 2015-06-22_

调用 [Get-CsOnlineUser](get-csonlineuser.md) cmdlet 时有多种方法可引用特定用户帐户。您可以使用用户的 Active Directory 域服务显示名称：

    Get-CsOnlineUser -Identity "Ken Myer"

您可以使用用户的 SIP 地址：

    Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"

您可以使用用户的用户主体名称 (UPN)：

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

