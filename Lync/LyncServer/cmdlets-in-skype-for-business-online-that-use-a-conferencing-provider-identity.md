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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="1cb67-102">Skype for Business Online 中使用会议提供商标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="1cb67-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="1cb67-103">若要返回有关您的组织已与之签订的所有音频会议提供商的信息，您可以只调用[CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet，而无需任何参数：</span><span class="sxs-lookup"><span data-stu-id="1cb67-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="1cb67-104">如果要将返回的数据限制为单个提供程序（本示例中为 "提供商 Contoso 音频服务"），请使用 Identity 参数：</span><span class="sxs-lookup"><span data-stu-id="1cb67-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="1cb67-105">仅有一个可接受音频会议提供商 ID 的 Skype for Business Online cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1cb67-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="1cb67-106">[CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cb67-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="1cb67-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cb67-107">See Also</span></span>


[<span data-ttu-id="1cb67-108">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="1cb67-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="1cb67-109">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1cb67-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

