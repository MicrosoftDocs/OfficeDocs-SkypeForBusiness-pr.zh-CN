---
title: Lync Online：向阻止的域列表添加域
TOCTitle: 向阻止的域列表添加域
ms:assetid: ea6ebeea-3031-4c42-9a2c-88eaab790636
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362853(v=OCS.15)
ms:contentKeyID: 56271219
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Online 中向阻止的域列表添加域

 

_**上一次修改主题：** 2015-06-22_

要向阻止的域列表添加域，请使用以下类似语法：

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -BlockedDomains @{Add=$x}

如您所见，此命令需要两个步骤。首先，使用 [New-CsEdgeDomainPattern](new-csedgedomainpattern.md) 创建代表要添加到阻止的列表的域的域对象。之后，使用 [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) cmdlet 和 Add 方法将该域（在此示例中，存储在变量 $x 中的域）添加到列表。

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

