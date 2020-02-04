---
title: Lync Server 2013：语音策略 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policy cmdlets
ms:assetid: 92744ec6-754d-498b-b430-dcd5c985ce10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415663(v=OCS.15)
ms:contentKeyID: 48184800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f45a7da053dd6dc150ae99e93b780117ba01e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policy-cmdlets-in-lync-server-2013"></a><span data-ttu-id="7ea5a-102">Lync Server 2013 中的语音策略 cmdlet</span><span class="sxs-lookup"><span data-stu-id="7ea5a-102">Voice policy cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ea5a-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7ea5a-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7ea5a-104">管理企业语音包括配置语音策略和拨号计划等内容，以及将语音策略与语音路由相关联。</span><span class="sxs-lookup"><span data-stu-id="7ea5a-104">Managing Enterprise Voice includes configuring such things as voice policies and dial plans, and associating voice policies with voice routes.</span></span> <span data-ttu-id="7ea5a-105">与管理语音策略相关的 cmdlet 可用于设置诸如同时拨打等功能（每次有人呼叫您的 office phone 时有第二个电话响铃的能力）、呼叫转接和拨号要求。</span><span class="sxs-lookup"><span data-stu-id="7ea5a-105">Cmdlets related to managing voice policies can be used to set features such as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone), call forwarding, and dialing requirement.</span></span>

<div>

## <a name="voice-policy-cmdlets"></a><span data-ttu-id="7ea5a-106">语音策略 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7ea5a-106">Voice Policy Cmdlets</span></span>

<span data-ttu-id="7ea5a-107">以下 cmdlet 可用于管理企业语音的语音策略和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="7ea5a-107">The following cmdlets can be used to manage voice policies and dial plans for Enterprise Voice.</span></span>

<span data-ttu-id="7ea5a-108">**语音策略**</span><span class="sxs-lookup"><span data-stu-id="7ea5a-108">**Voice Policy**</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-109">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-109">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-110">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-110">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-111">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-111">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-112">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-112">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-113">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-113">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-114">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-114">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7ea5a-115">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-115">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-116">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-116">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7ea5a-117">[CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-117">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-118">[授权-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-118">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-119">[新-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-119">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-121">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-121">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7ea5a-122">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7ea5a-122">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ea5a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ea5a-123">See Also</span></span>


[<span data-ttu-id="7ea5a-124">Lync Server 2013 中的企业语音 cmdlet</span><span class="sxs-lookup"><span data-stu-id="7ea5a-124">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="7ea5a-125">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="7ea5a-125">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

