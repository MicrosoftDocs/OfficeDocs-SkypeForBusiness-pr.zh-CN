---
title: Lync Server 2013：为 CAC 配置网络区域
description: Lync Server 2013：为 CAC 配置网络区域。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f016e0c943963ea4ce9739bd486c6996da502e73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577558"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="70d7b-103">在 Lync Server 2013 中配置 CAC 的网络区域</span><span class="sxs-lookup"><span data-stu-id="70d7b-103">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70d7b-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="70d7b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="70d7b-105">如果已为 E9-1-1 或媒体旁路创建网络区域，则可以通过使用 <STRONG>Set-CsNetworkRegion</STRONG> cmdlet 添加特定于呼叫允许控制 (CAC) 的设置来修改现有网络区域。</span><span class="sxs-lookup"><span data-stu-id="70d7b-105">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="70d7b-106">有关如何修改网络区域的示例，请参阅 <A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</A>。</span><span class="sxs-lookup"><span data-stu-id="70d7b-106">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="70d7b-107">“网络区域”\*\* 是在配置 CAC、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。</span><span class="sxs-lookup"><span data-stu-id="70d7b-107">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="70d7b-108">使用以下过程创建网络区域，这些网络区域与 CAC 的示例网络拓扑中的网络区域一致。</span><span class="sxs-lookup"><span data-stu-id="70d7b-108">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="70d7b-109">若要查看示例网络拓扑，请参阅规划文档中的 [示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="70d7b-109">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="70d7b-110">CAC 的示例网络拓扑有三个区域：北美、EMEA 和 APAC。</span><span class="sxs-lookup"><span data-stu-id="70d7b-110">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="70d7b-111">每个区域都有一个指定的中央站点。</span><span class="sxs-lookup"><span data-stu-id="70d7b-111">Each region has a specified central site.</span></span> <span data-ttu-id="70d7b-112">对于 North America 区域，指定的中央站点名为 CHICAGO。</span><span class="sxs-lookup"><span data-stu-id="70d7b-112">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="70d7b-113">以下过程显示了如何使用 **New-CsNetworkRegion** cmdlet 创建 North America 区域的示例。</span><span class="sxs-lookup"><span data-stu-id="70d7b-113">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70d7b-114">在下面的过程中，将使用 Lync Server 命令行管理程序创建网络区域。</span><span class="sxs-lookup"><span data-stu-id="70d7b-114">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="70d7b-115">有关使用 Lync Server 控制面板创建网络区域的详细信息，请参阅 <A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中创建或修改网络区域</A>。</span><span class="sxs-lookup"><span data-stu-id="70d7b-115">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="70d7b-116">创建呼叫允许控制的网络区域</span><span class="sxs-lookup"><span data-stu-id="70d7b-116">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="70d7b-117">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70d7b-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="70d7b-118">对于每个需要创建的区域，运行 **New-CsNetworkRegion** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="70d7b-118">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="70d7b-119">例如，要创建 North America 区域，请运行：</span><span class="sxs-lookup"><span data-stu-id="70d7b-119">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="70d7b-120">重复步骤 2 以创建网络区域、EMEA 和 APAC。</span><span class="sxs-lookup"><span data-stu-id="70d7b-120">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

