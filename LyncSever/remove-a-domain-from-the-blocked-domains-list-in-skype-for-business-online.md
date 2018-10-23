---
title: 从阻止的域列表中删除域
TOCTitle: 从阻止的域列表中删除域
ms:assetid: a11ea475-bb8b-44be-a5a5-4abb2fed42b8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362830(v=OCS.15)
ms:contentKeyID: 56271185
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从阻止的域列表中删除域

 

_**上一次修改主题：** 2015-06-22_

从阻止的域列表中删除域需要两个步骤。首先，您必须使用 [New-CsEdgeDomainPattern](new-csedgedomainpattern.md) cmdlet 为要删除的域创建域对象：

    $x = New-CsEdgeDomainPattern "fabrikam.com"

创建此对象之后，请使用以下语法从阻止的域列表中删除域（在此示例中为存储在变量 $x 中的域）：

    Set-CsTenantFederationConfiguration -BlockedDomains @{Remove=$x}

要从阻止的域列表中删除所有域，请将 BlockedDomains 属性的值设置为 null ($Null)：

    Set-CsTenantFederationConfiguration -BlockedDomains $Null

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

