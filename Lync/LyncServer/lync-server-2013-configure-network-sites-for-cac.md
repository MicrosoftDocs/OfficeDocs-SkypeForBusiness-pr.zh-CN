---
title: 'Lync Server 2013: 配置 CAC 的网络站点'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="61b92-102">在 Lync Server 2013 中配置 CAC 的网络站点</span><span class="sxs-lookup"><span data-stu-id="61b92-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61b92-103">_**主题上次修改时间:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="61b92-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="61b92-104">如果你已为 E9 或媒体旁路创建了网络站点, 则可以通过使用<STRONG>CsNetworkSite</STRONG> cmdlet 修改现有网络站点以应用带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="61b92-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="61b92-105">有关如何修改网络网站的示例, 请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络网站</A>。</span><span class="sxs-lookup"><span data-stu-id="61b92-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="61b92-106">*网络站点*是呼叫许可控制 (CAC)、E9-1 和媒体绕过部署的每个网络区域内的办公室或位置。</span><span class="sxs-lookup"><span data-stu-id="61b92-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="61b92-107">使用以下过程创建网络站点, 这些站点与 CAC 的示例网络拓扑中的网络站点对齐。</span><span class="sxs-lookup"><span data-stu-id="61b92-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="61b92-108">这些过程演示了如何创建和配置受 WAN 带宽限制的网络站点, 因此需要带宽策略来限制实时音频或视频流量流。</span><span class="sxs-lookup"><span data-stu-id="61b92-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="61b92-109">在示例 CAC 部署中, 北美地区有六个站点。</span><span class="sxs-lookup"><span data-stu-id="61b92-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="61b92-110">以下三个网站受 WAN 带宽的约束: Reno、伯克基和。</span><span class="sxs-lookup"><span data-stu-id="61b92-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="61b92-111">*不*受 WAN 带宽约束的其他三个站点: 纽约、芝加哥和底特律。</span><span class="sxs-lookup"><span data-stu-id="61b92-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="61b92-112">有关如何创建或修改其他网络网站的示例, 请参阅[在 Lync Server 2013 中创建或修改网络网站](lync-server-2013-create-or-modify-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="61b92-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="61b92-113">若要查看示例网络拓扑, 请参阅: 在规划文档中[收集 Lync Server 2013 中的呼叫许可控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="61b92-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="61b92-114">在以下过程中, Lync Server Management Shell 用于创建网络网站。</span><span class="sxs-lookup"><span data-stu-id="61b92-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="61b92-115">有关使用 Lync Server "控制面板" 创建网络网站的详细信息, 请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中创建或修改网络网站</A>。</span><span class="sxs-lookup"><span data-stu-id="61b92-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="61b92-116">为呼叫许可控制创建网络站点</span><span class="sxs-lookup"><span data-stu-id="61b92-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="61b92-117">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="61b92-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="61b92-118">运行**CsNetworkSite** cmdlet 以创建网络站点并将相应的带宽策略配置文件应用到每个站点。</span><span class="sxs-lookup"><span data-stu-id="61b92-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="61b92-119">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="61b92-119">For example, run:</span></span>
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="61b92-120">若要完成为整个示例拓扑创建网络网站, 请对 EMEA 和 APAC 区域中带宽受限的网络网站重复步骤2。</span><span class="sxs-lookup"><span data-stu-id="61b92-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

