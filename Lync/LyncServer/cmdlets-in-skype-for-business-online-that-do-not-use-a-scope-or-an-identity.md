---
title: Skype for Business Online 中不使用作用域或标识的 cmdlet
description: Skype for Business Online 中不使用作用域或标识的 cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d893c4cf9203c8657dfbdfd7fb2bf46dbdfe4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545718"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Skype for Business Online 中不使用作用域或标识的 cmdlet

 


在修改允许的列表和阻止的列表时使用的 cmdlet (列表，用于确定允许用户与) 通信的外部组织。不使用范围或标识。 事实上， **CsEdgeAllowAllKnownDomains** cmdlet 没有任何参数。 不使用作用域或标识的 cmdlet 为：

  - [新 CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [新 CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [新 CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

请注意，同时使用 **CsEdgeAllowList** Cmdlet 和 **CsEdgeDomainPattern** Cmdlet，必须包括 Domain 参数。 例如：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

