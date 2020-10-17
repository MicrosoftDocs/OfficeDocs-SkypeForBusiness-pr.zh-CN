---
title: Lync Server 2013：全局媒体旁路选项
description: Lync Server 2013：全局媒体旁路选项。
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
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554548"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="53a81-103">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="53a81-103">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a81-104">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="53a81-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53a81-105">本主题假定您已将任何中继的媒体旁路配置为对等方 ( (PSTN) 网关、ip-pbx 或会话边界控制器 (SBC) 在 Internet 电话服务提供程序) 针对您希望媒体绕过中介服务器的特定站点或服务。</span><span class="sxs-lookup"><span data-stu-id="53a81-105">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="53a81-106">除了为与对等方关联的各个中继连接启用媒体绕过功能外，还必须在全局范围内启用媒体绕过功能。</span><span class="sxs-lookup"><span data-stu-id="53a81-106">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="53a81-107">全局媒体旁路设置可以指定始终尝试媒体绕过对 PSTN 的呼叫，或使用将子网映射到网络站点和网络区域时使用的媒体旁路，类似于呼叫允许控制（另一高级语音功能）所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="53a81-107">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="53a81-108">如果启用了媒体旁路和呼叫允许控制，则在确定是否使用媒体旁路时，将自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。</span><span class="sxs-lookup"><span data-stu-id="53a81-108">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="53a81-109">这意味着，在启用呼叫允许控制时，不能指定始终尝试将媒体旁路用于对 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="53a81-109">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="53a81-110">本主题介绍如何将 Lync Server 控制面板和 Lync Server 命令行管理程序一起使用，以配置全局媒体旁路设置。</span><span class="sxs-lookup"><span data-stu-id="53a81-110">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53a81-111">使用这些步骤配置媒体绕过时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。</span><span class="sxs-lookup"><span data-stu-id="53a81-111">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="53a81-112">如果链接上有任何带宽限制，则媒体绕过无法应用于呼叫。</span><span class="sxs-lookup"><span data-stu-id="53a81-112">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="53a81-113">媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="53a81-113">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="53a81-114">Microsoft 已使用认证的合作伙伴测试了一组 PSTN 网关和 SBCs，并且已通过 Cisco IP Pbx 进行了一些测试。</span><span class="sxs-lookup"><span data-stu-id="53a81-114">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="53a81-115">仅在统一通信开放互操作性计划– Lync Server 上列出的产品和版本支持媒体旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="53a81-115">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="53a81-116">后续步骤：选择全局媒体绕过设置</span><span class="sxs-lookup"><span data-stu-id="53a81-116">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="53a81-117">在任何到特定站点或特定服务的对等方的中继连接上启用媒体绕过后，请使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="53a81-117">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="53a81-118">按在 [Lync server 2013 中配置媒体旁路以始终绕过中介服务器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)中所述，始终启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="53a81-118">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="53a81-119">或者，将媒体旁路配置为使用站点和区域信息，如在 [Lync Server 2013 中配置媒体旁路全局设置以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="53a81-119">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53a81-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53a81-120">See Also</span></span>


[<span data-ttu-id="53a81-121">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="53a81-121">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="53a81-122">在 Lync Server 2013 中将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="53a81-122">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="53a81-123">在 Lync Server 2013 中配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="53a81-123">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="53a81-124">Lync Server 2013 中的媒体旁路和中介服务器</span><span class="sxs-lookup"><span data-stu-id="53a81-124">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

