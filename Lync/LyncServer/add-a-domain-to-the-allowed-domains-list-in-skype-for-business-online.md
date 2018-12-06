---
title: Lync Online：向允许的域列表添加域
TOCTitle: 向允许的域列表添加域
ms:assetid: 7b7f76c8-3047-40be-a938-8ac2868a6bc8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362818(v=OCS.15)
ms:contentKeyID: 56271170
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Online 中向允许的域列表添加域

 

_**上一次修改主题：** 2015-06-22_

向允许的域列表添加第一个域涉及三个步骤。首先，使用 [New-CsEdgeDomainPattern](new-csedgedomainpattern.md) cmdlet 为要添加的域创建域对象：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

接下来，使用 [New-CsEdgeAllowList](new-csedgeallowlist.md) cmdlet 创建新的包括该域对象的允许列表：

    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x

最后，使用 [Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md) cmdlet 将新的允许列表写入到 Skype for Business Online 中：

    Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList

## 另请参阅

#### 概念

[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

