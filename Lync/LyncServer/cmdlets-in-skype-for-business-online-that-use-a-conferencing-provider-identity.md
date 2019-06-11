---
title: Skype for Business Online 中使用会议提供商标识的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e36c04b2f5728ff624a280696bacf4eacb032967
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837093"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="56852-102">Skype for Business Online 中使用会议提供商标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="56852-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="56852-103">若要返回有关你的组织已与之签约的所有音频会议提供商的信息, 你可以只调用[CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet 而不使用任何参数:</span><span class="sxs-lookup"><span data-stu-id="56852-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="56852-104">如果你希望将返回的数据限制为单个提供程序 (在此示例中为提供商 Contoso 音频服务), 请使用 Identity 参数:</span><span class="sxs-lookup"><span data-stu-id="56852-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="56852-105">只有一个 Skype for Business Online cmdlet 可接受音频会议提供商 ID:</span><span class="sxs-lookup"><span data-stu-id="56852-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="56852-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="56852-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="56852-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56852-107">See Also</span></span>


[<span data-ttu-id="56852-108">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="56852-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="56852-109">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="56852-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

