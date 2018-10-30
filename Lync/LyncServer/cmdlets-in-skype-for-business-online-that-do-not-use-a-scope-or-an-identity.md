---
title: 不使用作用域或标识的 Cmdlet
TOCTitle: 不使用作用域或标识的 Cmdlet
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56271181
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 不使用作用域或标识的 Cmdlet

 

_**上一次修改主题：** 2015-06-22_

修改允许的列表和阻止的列表（这些列表确定允许您的用户与哪些外部组织进行通信）时使用的 cmdlet 不使用作用域或标识。事实上，**New-CsEdgeAllowAllKnownDomains** cmdlet 没有任何参数。不使用作用域或标识的 cmdlet 包括：

  - [New-CsEdgeAllowAllKnownDomains](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowAllKnownDomains)

  - [New-CsEdgeAllowList](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowList)

  - [New-CsEdgeDomainPattern](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeDomainPattern)

请注意，对于 **New-CsEdgeAllowList** cmdlet 和 **New-CsEdgeDomainPattern** cmdlet，您必须包括 Domain 参数。例如：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## 另请参阅

#### 概念

[标识、作用域和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

