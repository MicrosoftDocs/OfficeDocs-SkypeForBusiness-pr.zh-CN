---
title: 返回有关所有 Lync Online 用户的信息
TOCTitle: 返回有关所有 Lync Online 用户的信息
ms:assetid: 0b59fadf-67e6-48ea-86f1-2efef500ebdf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362769(v=OCS.15)
ms:contentKeyID: 56271123
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 返回有关所有 Lync Online 用户的信息

 

_**上一次修改主题：** 2015-06-22_

要返回已启用 Skype for Business Online 的所有用户的信息，请不带任何附加参数调用 [Get-CsOnlineUser](get-csonlineuser.md) cmdlet：

    Get-CsOnlineUser

要返回随机选择的单个用户的信息（例如，出于测试目的使用此帐户），请调用 **Get-CsOnlineUser** cmdlet 并将 ResultSize 参数设置为 1：

    Get-CsOnlineUser -ResultSize 1

这会导致 **Get-CsOnlineUser** cmdlet 仅返回一个用户的信息，无论您的组织内有多少用户都是如此。要返回五个用户的信息，请将 ResultSize 参数的值设置为 5：

    Get-CsOnlineUser -ResultSize 5

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

