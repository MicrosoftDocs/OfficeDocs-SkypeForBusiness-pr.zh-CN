---
title: Lync Server 2013：为 CAC 配置网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="88eb1-102">在 Lync Server 2013 中配置 CAC 的网络站点</span><span class="sxs-lookup"><span data-stu-id="88eb1-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88eb1-103">_**上次修改的主题：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="88eb1-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="88eb1-104">如果您已为 E9-1-1 或媒体旁路创建网络站点，则可以使用 <STRONG>Set-CsNetworkSite</STRONG> cmdlet 修改现有的网络站点，以应用带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="88eb1-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="88eb1-105">有关如何修改网络站点的示例，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络站点</A>。</span><span class="sxs-lookup"><span data-stu-id="88eb1-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="88eb1-p102">*网络站点*是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。使用以下过程创建网络站点，这些网络站点与 CAC 的示例网络拓扑中的网络站点一致。这些过程显示如何创建并配置受 WAN 带宽限制，并因此需要用于限制实时音频或视频流量的带宽策略的网络站点。</span><span class="sxs-lookup"><span data-stu-id="88eb1-p102">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments. Use the following procedures to create network sites that align to network sites in the example network topology for CAC. These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="88eb1-109">在示例 CAC 部署中，北美区域有六个站点。</span><span class="sxs-lookup"><span data-stu-id="88eb1-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="88eb1-110">其中三个站点受 WAN 带宽限制：里诺、波特兰和阿尔布开克。</span><span class="sxs-lookup"><span data-stu-id="88eb1-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="88eb1-111">其他三个站点*不*受 WAN 带宽限制：纽约、芝加哥和底特律。</span><span class="sxs-lookup"><span data-stu-id="88eb1-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="88eb1-112">有关如何创建或修改其他网络站点的示例，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="88eb1-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="88eb1-113">若要查看示例网络拓扑，请参阅规划文档中的[示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="88eb1-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="88eb1-114">在下面的过程中，将使用 Lync Server 命令行管理程序创建网络站点。</span><span class="sxs-lookup"><span data-stu-id="88eb1-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="88eb1-115">有关使用 Lync Server 控制面板创建网络站点的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中创建或修改网络站点</A>。</span><span class="sxs-lookup"><span data-stu-id="88eb1-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="88eb1-116">为呼叫允许控制创建网络站点</span><span class="sxs-lookup"><span data-stu-id="88eb1-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="88eb1-117">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88eb1-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="88eb1-118">运行 **New-CsNetworkSite** cmdlet 以创建网络站点并将相应带宽策略配置文件应用到每个站点。</span><span class="sxs-lookup"><span data-stu-id="88eb1-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="88eb1-119">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="88eb1-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="88eb1-120">要为整个示例拓扑完成网络站点的创建，请针对 EMEA 和 APAC 区域中受带宽限制的网络站点重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="88eb1-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

