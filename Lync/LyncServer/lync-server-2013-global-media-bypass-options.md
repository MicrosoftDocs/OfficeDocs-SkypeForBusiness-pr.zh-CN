---
title: Lync Server 2013：全局媒体绕过选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="3355b-102">Lync Server 2013 中的全局媒体绕过选项</span><span class="sxs-lookup"><span data-stu-id="3355b-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3355b-103">_**主题上次修改时间：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3355b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3355b-104">本主题假设你已针对特定网站或服务将针对任何中继的任何将媒体绕过配置到 Internet 电话服务提供商的任何对等（公共交换电话网络（PSTN）网关、IP PBX 或会话边界控制器（SBC））您希望媒体绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="3355b-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="3355b-p101">除了为与对等方关联的各个中继连接启用媒体旁路功能外，还必须在全局范围内启用媒体旁路功能。全局媒体旁路设置可以指定始终为对 PSTN 的呼叫尝试媒体旁路，或者指定通过将子网映射到网络站点和网络区域来使用媒体旁路，这与呼叫允许控制（另一高级语音功能）所执行的操作类似。同时启用媒体旁路和呼叫允许控制后，在确定是否使用媒体旁路时，会自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。这意味着，启用呼叫允许控制后无法指定始终为对 PSTN 的呼叫尝试媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="3355b-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="3355b-109">本主题介绍了如何将 Lync Server 控制面板和 Lync Server Management Shell 一起使用来配置全局媒体绕过设置。</span><span class="sxs-lookup"><span data-stu-id="3355b-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3355b-110">使用这些步骤配置媒体旁路时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。</span><span class="sxs-lookup"><span data-stu-id="3355b-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="3355b-111">如果链接上有任何带宽限制，则媒体旁路无法应用于呼叫。</span><span class="sxs-lookup"><span data-stu-id="3355b-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="3355b-112">媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="3355b-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="3355b-113">Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="3355b-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3355b-114">只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>Lync Server at。</span><span class="sxs-lookup"><span data-stu-id="3355b-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="3355b-115">后续步骤：选择全局媒体绕过设置</span><span class="sxs-lookup"><span data-stu-id="3355b-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="3355b-116">在针对特定网站或服务对等方的任何中继连接上启用了媒体旁路后，请使用以下内容之一：</span><span class="sxs-lookup"><span data-stu-id="3355b-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="3355b-117">按 "在[Lync server 2013 中配置媒体旁路](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)" 中所述，始终启用媒体绕过，以始终绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="3355b-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="3355b-118">或者，将媒体旁路配置为使用网站和区域信息，如在[Lync Server 2013 中配置媒体绕过全局设置以使用网站和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="3355b-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3355b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3355b-119">See Also</span></span>


[<span data-ttu-id="3355b-120">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3355b-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="3355b-121">在 Lync Server 2013 中将子网与网络站点相关联</span><span class="sxs-lookup"><span data-stu-id="3355b-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="3355b-122">在 Lync Server 2013 中配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="3355b-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="3355b-123">Lync Server 2013 中的媒体绕过和中介服务器</span><span class="sxs-lookup"><span data-stu-id="3355b-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

