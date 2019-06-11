---
title: 'Lync Server 2013: PSTN 连接 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity cmdlets
ms:assetid: b19ba43c-3987-410d-a704-aba0a4fb0498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415670(v=OCS.15)
ms:contentKeyID: 48185142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7271622dbfefee9c0c96063b242015ab7f7225b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a2fb7-102">Lync Server 2013 中的 PSTN 连接 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a2fb7-102">PSTN connectivity cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2fb7-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a2fb7-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a2fb7-104">企业语音提供的设置允许呼叫和从公共交换电话网络 (PSTN) 呼叫, 而不会拒绝任何服务质量 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="a2fb7-104">Enterprise Voice provides settings that allow for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="a2fb7-105">你可以通过 Lync Server 命令行管理程序中提供的 cmdlet 配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="a2fb7-105">You can configure these settings through cmdlets available from the Lync Server Management Shell.</span></span>

<div>

## <a name="pstn-connectivity-cmdlets"></a><span data-ttu-id="a2fb7-106">PSTN 连接 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a2fb7-106">PSTN Connectivity Cmdlets</span></span>

<span data-ttu-id="a2fb7-107">使用以下 cmdlet 配置 PSTN 连接的各个方面。</span><span class="sxs-lookup"><span data-stu-id="a2fb7-107">Use the following cmdlets to configure various aspects of PSTN connectivity.</span></span>

<span data-ttu-id="a2fb7-108">**[Lync Server 2013 中的 PSTN 网关 cmdlet](lync-server-2013-pstn-gateways-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="a2fb7-108">**[PSTN gateways cmdlets in Lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span></span>

<span data-ttu-id="a2fb7-113">**[Lync Server 2013 中的静态路由 cmdlet](lync-server-2013-static-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="a2fb7-113">**[Static routing cmdlets in Lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-114">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-114">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-115">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-115">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-116">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-116">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-117">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-117">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-118">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-118">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-119">[CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-119">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-120">[新-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-120">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-121">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-121">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-122">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-122">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-123">[新-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-123">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-124">[新-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-124">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-125">[新-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-125">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-126">[新-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-126">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-127">[新-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-127">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-128">[新-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-128">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-129">[新-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-129">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-130">[新-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-130">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span></span>

<span data-ttu-id="a2fb7-131">**[Lync Server 2013 中的中继配置 cmdlet](lync-server-2013-trunking-configuration-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="a2fb7-131">**[Trunking configuration cmdlets in Lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**</span></span>

  - <span data-ttu-id="a2fb7-132">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-132">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a2fb7-133">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-133">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="a2fb7-134">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-134">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="a2fb7-135">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-135">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="a2fb7-136">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-136">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-137">[CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-137">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-138">[新-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-138">[New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-139">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-139">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-140">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-140">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a2fb7-141">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-141">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-142">[New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-142">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-143">[新-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-143">[New-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-144">[Remove-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-144">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-145">[Set-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-145">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-146">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-146">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-147">[新-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-147">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="a2fb7-148">**[Lync Server 2013 中的语音路由 cmdlet](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="a2fb7-148">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-149">[CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-149">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-150">[新-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-150">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-151">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-151">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-152">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-152">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a2fb7-153">[CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-153">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-154">[新-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-154">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-155">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-155">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-156">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-156">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a2fb7-157">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a2fb7-157">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2fb7-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2fb7-158">See Also</span></span>


[<span data-ttu-id="a2fb7-159">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="a2fb7-159">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

