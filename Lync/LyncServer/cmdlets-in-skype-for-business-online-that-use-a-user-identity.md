---
title: Skype for Business Online 中使用用户标识的 cmdlet
description: Skype for Business Online 中使用用户标识的 cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545648"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Skype for Business Online 中使用用户标识的 cmdlet

 


在 Skype for Business Online 中，可以通过多种不同的方式引用单个用户标识：

  - 使用用户的 Active Directory 域服务显示名称。 例如：
    
        -Identity "Ken Myer"

  - 使用用户的 SIP 地址。 例如：
    
        -Identity "sip:kenmyer@litwareinc.com"

  - 使用用户的 UPN。 例如：
    
        -Identity " kenmyer@litwareinc.com"

  - 使用用户的 Active Directory 域服务可分辨名称。 例如：
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

以下 cmdlet 接受用户标识：

  - [Disable-Disable-csmeetingroom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-Disable-csmeetingroom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-csonlineuser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [新 CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

请注意，调用 **Cs** cmdlet 之一时无需指定用户标识。 在这种情况下，cmdlet 将返回指定项目的所有实例。 例如，以下命令将返回已为 Skype for Business Online 启用的所有用户的相关信息：

    Get-CsOnlineUser

只有当您要返回特定用户的信息时，Identity 参数才是必需的：

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

