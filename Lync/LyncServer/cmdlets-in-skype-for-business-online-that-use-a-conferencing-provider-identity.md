---
title: Skype for Business Online 中使用会议提供商标识的 cmdlet
description: Skype for Business Online 中使用会议提供商标识的 cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 61ab4fb410878ca73314b73737948d9961462c87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545728"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="14b6d-103">Skype for Business Online 中使用会议提供商标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="14b6d-103">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="14b6d-104">若要返回有关您的组织已与之签订的所有音频会议提供商的信息，您可以只调用 [CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet，而无需任何参数：</span><span class="sxs-lookup"><span data-stu-id="14b6d-104">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="14b6d-105">如果要将返回的数据限制为单个提供程序 (在此示例中，提供商 Contoso 音频服务) ，请使用 Identity 参数：</span><span class="sxs-lookup"><span data-stu-id="14b6d-105">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="14b6d-106">仅有一个可接受音频会议提供商 ID 的 Skype for Business Online cmdlet：</span><span class="sxs-lookup"><span data-stu-id="14b6d-106">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="14b6d-107">[CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="14b6d-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="14b6d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14b6d-108">See Also</span></span>


[<span data-ttu-id="14b6d-109">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="14b6d-109">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="14b6d-110">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="14b6d-110">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

