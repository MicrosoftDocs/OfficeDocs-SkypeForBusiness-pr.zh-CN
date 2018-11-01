---
title: 从允许的域列表中删除域
TOCTitle: 从允许的域列表中删除域
ms:assetid: 04948582-363b-49bd-8305-166c4c1d0dd9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362766(v=OCS.15)
ms:contentKeyID: 56271116
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从允许的域列表中删除域

 

_**上一次修改主题：** 2015-06-22_

从允许的域列表中删除域涉及一系列步骤。首先，您必须使用以下类似命令检索列表上当前存在的所有域的集合：

    $x = (Get-CsTenantFederationConfiguration).AllowedDomains

接下来，运行此命令以查看这些域：

``` 
$x
```

记下要删除的域的数值位置。如果域是列表中的第一个域，它具有索引值 0。如果域是列表中的第二个域，它具有索引值 1，以此类推。

知道索引编号之后，请使用以下类似命令删除指定域，确保使用正确的索引编号。此命令将删除列表中的第一个域（索引编号 0）：

    $x.AllowedDomain.RemoveAt(0)

最后，调用 [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) cmdlet 以将您的更改写入到 Skype for Business Online：

    Set-CsTenantFederationConfiguration -AllowedDomains $x

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

