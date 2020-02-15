---
title: Skype for Business Online 中使用会议提供商标识的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0ae3167b1cb6c83b46e4f9d4846e8863b43515d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001717"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Skype for Business Online 中使用会议提供商标识的 cmdlet

 


若要返回有关您的组织已与之签订的所有音频会议提供商的信息，您可以只调用[CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet，而无需任何参数：

    Get-CsAudioConferencingProvider

如果要将返回的数据限制为单个提供程序（本示例中为 "提供商 Contoso 音频服务"），请使用 Identity 参数：

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

仅有一个可接受音频会议提供商 ID 的 Skype for Business Online cmdlet：

  - [CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

