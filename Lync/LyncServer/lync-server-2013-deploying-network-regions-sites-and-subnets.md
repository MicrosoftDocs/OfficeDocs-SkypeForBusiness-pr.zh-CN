---
title: Lync Server 2013：部署网络区域、站点和子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e4db701dc3d43ed30b8101ef2af5ff2e4a2ad0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="54f1b-102">在 Lync Server 2013 中部署网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="54f1b-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f1b-103">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="54f1b-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="54f1b-104">部署企业语音后，您需要配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="54f1b-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="54f1b-105">网络区域</span><span class="sxs-lookup"><span data-stu-id="54f1b-105">Network regions</span></span>

  - <span data-ttu-id="54f1b-106">网络站点</span><span class="sxs-lookup"><span data-stu-id="54f1b-106">Network sites</span></span>

  - <span data-ttu-id="54f1b-107">网络子网</span><span class="sxs-lookup"><span data-stu-id="54f1b-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="54f1b-108">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="54f1b-108">Define Network Regions</span></span>

<span data-ttu-id="54f1b-109">使用 Lync Server Windows PowerShell 命令、CsNetworkRegion 或 Lync Server 控制面板定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="54f1b-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="54f1b-110">有关详细信息，请参阅[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。</span><span class="sxs-lookup"><span data-stu-id="54f1b-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="54f1b-111">对于此示例，以下 Windows PowerShell 命令说明了此方案中定义的网络区域（国家/地区1（印度））。</span><span class="sxs-lookup"><span data-stu-id="54f1b-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="54f1b-112">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="54f1b-112">Define Network Sites</span></span>

<span data-ttu-id="54f1b-113">使用 Lync Server Windows PowerShell 命令、CsNetworkSite 或 Lync Server 控制面板定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="54f1b-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="54f1b-114">有关详细信息，请参阅[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。</span><span class="sxs-lookup"><span data-stu-id="54f1b-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="54f1b-115">对于此示例，下表和 Lync Server Windows PowerShell 命令说明了此方案中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="54f1b-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="54f1b-116">为了便于说明，仅在表中包含特定于基于位置的路由的设置。</span><span class="sxs-lookup"><span data-stu-id="54f1b-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="54f1b-117">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="54f1b-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="54f1b-118">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="54f1b-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54f1b-119">网站 ID</span><span class="sxs-lookup"><span data-stu-id="54f1b-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="54f1b-120">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="54f1b-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="54f1b-121">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="54f1b-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54f1b-122">区域 ID</span><span class="sxs-lookup"><span data-stu-id="54f1b-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="54f1b-123">区域1（印度）</span><span class="sxs-lookup"><span data-stu-id="54f1b-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="54f1b-124">区域1（印度）</span><span class="sxs-lookup"><span data-stu-id="54f1b-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="54f1b-125">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="54f1b-125">Define Network Subnets</span></span>

<span data-ttu-id="54f1b-126">使用 Lync Server Windows PowerShell 命令、CsNetworkSubnet 或 Lync Server 控制面板定义网络子网并将其分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="54f1b-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="54f1b-127">有关详细信息，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="54f1b-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="54f1b-128">对于此示例，下表和 Windows PowerShell 命令说明了如何将网络子网分配给在此方案中定义的网络站点（新德里和 Hyderabad）。</span><span class="sxs-lookup"><span data-stu-id="54f1b-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="54f1b-129">为了便于说明，仅在表中包含特定于基于位置的路由的设置。</span><span class="sxs-lookup"><span data-stu-id="54f1b-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="54f1b-130">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="54f1b-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="54f1b-131">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="54f1b-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54f1b-132">子网 ID</span><span class="sxs-lookup"><span data-stu-id="54f1b-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="54f1b-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="54f1b-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="54f1b-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="54f1b-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54f1b-135">Mask</span><span class="sxs-lookup"><span data-stu-id="54f1b-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="54f1b-136">24</span><span class="sxs-lookup"><span data-stu-id="54f1b-136">24</span></span></p></td>
<td><p><span data-ttu-id="54f1b-137">24</span><span class="sxs-lookup"><span data-stu-id="54f1b-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54f1b-138">网站 ID</span><span class="sxs-lookup"><span data-stu-id="54f1b-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="54f1b-139">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="54f1b-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="54f1b-140">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="54f1b-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54f1b-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54f1b-141">See Also</span></span>


[<span data-ttu-id="54f1b-142">在 Lync Server 2013 中配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="54f1b-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

