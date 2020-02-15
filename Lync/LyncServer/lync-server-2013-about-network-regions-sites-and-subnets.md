---
title: Lync Server 2013：关于网络区域、站点和子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2f6de7a39b3029f1edc1252b90ec264d774632f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="f9a0a-102">关于 Lync Server 2013 中的网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="f9a0a-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9a0a-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f9a0a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f9a0a-p101">本节所述的高级企业语音功能共享了网络区域、网络站点和子网的某些配置要求。例如，三种高级功能都要求拓扑中的每个子网与特定*网络站点* 关联，而每个网络站点必须与*网络区域* 关联。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9a0a-106">在为呼叫允许控制、E9-1-1 或媒体旁路配置网络配置之前，请务必阅读规划文档中的 " <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的高级企业语音功能的网络设置</A>" 中的 "网络设置" 中的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="f9a0a-107">有关主要有关呼叫允许控制的网络配置的详细信息，请参阅规划文档中的在<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 中定义呼叫允许控制的要求</A>。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="f9a0a-108">呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：</span><span class="sxs-lookup"><span data-stu-id="f9a0a-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="f9a0a-109">呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定*带宽策略配置文件*。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="f9a0a-110">如果您计划部署呼叫允许控制，则必须在配置网络站点之前[在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="f9a0a-111">E9-1-1 要求为每个站点指定*位置策略*。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="f9a0a-112">如果您计划部署 E9-1-1，则必须在配置网络站点之前[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="f9a0a-113">创建或修改网络区域、网络站点和子网</span><span class="sxs-lookup"><span data-stu-id="f9a0a-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="f9a0a-p105">以下主题提供有关创建或修改网络区域和网络站点，以及将子网与网络站点关联的步骤。这些主题不特定于任何特定高级企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="f9a0a-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="f9a0a-116">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="f9a0a-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="f9a0a-117">在 Lync Server 2013 中创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="f9a0a-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="f9a0a-118">在 Lync Server 2013 中将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="f9a0a-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

