---
title: Lync Server 2013：部署网络区域、站点和子网
description: Lync Server 2013：部署网络区域、站点和子网。
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
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561088"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="a3926-103">在 Lync Server 2013 中部署网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="a3926-103">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3926-104">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="a3926-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="a3926-105">部署企业语音后，您需要配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="a3926-105">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="a3926-106">网络区域</span><span class="sxs-lookup"><span data-stu-id="a3926-106">Network regions</span></span>

  - <span data-ttu-id="a3926-107">网络站点</span><span class="sxs-lookup"><span data-stu-id="a3926-107">Network sites</span></span>

  - <span data-ttu-id="a3926-108">网络子网</span><span class="sxs-lookup"><span data-stu-id="a3926-108">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="a3926-109">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="a3926-109">Define Network Regions</span></span>

<span data-ttu-id="a3926-110">使用 Lync Server Windows PowerShell 命令、CsNetworkRegion 或 Lync Server 控制面板定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="a3926-110">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="a3926-111">有关详细信息，请参阅 [CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。</span><span class="sxs-lookup"><span data-stu-id="a3926-111">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="a3926-112">在此示例中，以下 Windows PowerShell 命令说明了在此方案中定义的网络区域（区域 1 (印度) ）。</span><span class="sxs-lookup"><span data-stu-id="a3926-112">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="a3926-113">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="a3926-113">Define Network Sites</span></span>

<span data-ttu-id="a3926-114">使用 Lync Server Windows PowerShell 命令、CsNetworkSite 或 Lync Server 控制面板定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="a3926-114">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="a3926-115">有关详细信息，请参阅 [CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。</span><span class="sxs-lookup"><span data-stu-id="a3926-115">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="a3926-116">对于此示例，下表和 Lync Server Windows PowerShell 命令说明了此方案中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="a3926-116">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="a3926-117">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="a3926-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="a3926-118">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="a3926-118">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="a3926-119">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="a3926-119">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3926-120">网站 ID</span><span class="sxs-lookup"><span data-stu-id="a3926-120">Site ID</span></span></p></td>
<td><p><span data-ttu-id="a3926-121">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="a3926-121">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a3926-122">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="a3926-122">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3926-123">区域 ID</span><span class="sxs-lookup"><span data-stu-id="a3926-123">Region ID</span></span></p></td>
<td><p><span data-ttu-id="a3926-124">区域 1 (印度) </span><span class="sxs-lookup"><span data-stu-id="a3926-124">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="a3926-125">区域 1 (印度) </span><span class="sxs-lookup"><span data-stu-id="a3926-125">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="a3926-126">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="a3926-126">Define Network Subnets</span></span>

<span data-ttu-id="a3926-127">使用 Lync Server Windows PowerShell 命令、CsNetworkSubnet 或 Lync Server 控制面板定义网络子网并将其分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="a3926-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="a3926-128">有关详细信息，请参阅 [CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="a3926-128">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="a3926-129">对于此示例，下表和 Windows PowerShell 命令说明了如何将网络子网分配给在此方案中定义的网络站点（新德里和 Hyderabad）。</span><span class="sxs-lookup"><span data-stu-id="a3926-129">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="a3926-130">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="a3926-130">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="a3926-131">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="a3926-131">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="a3926-132">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="a3926-132">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3926-133">子网 ID</span><span class="sxs-lookup"><span data-stu-id="a3926-133">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="a3926-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="a3926-134">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="a3926-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a3926-135">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3926-136">Mask</span><span class="sxs-lookup"><span data-stu-id="a3926-136">Mask</span></span></p></td>
<td><p><span data-ttu-id="a3926-137">24</span><span class="sxs-lookup"><span data-stu-id="a3926-137">24</span></span></p></td>
<td><p><span data-ttu-id="a3926-138">24</span><span class="sxs-lookup"><span data-stu-id="a3926-138">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3926-139">网站 ID</span><span class="sxs-lookup"><span data-stu-id="a3926-139">Site ID</span></span></p></td>
<td><p><span data-ttu-id="a3926-140">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="a3926-140">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a3926-141">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="a3926-141">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3926-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3926-142">See Also</span></span>


[<span data-ttu-id="a3926-143">在 Lync Server 2013 中配置 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="a3926-143">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

