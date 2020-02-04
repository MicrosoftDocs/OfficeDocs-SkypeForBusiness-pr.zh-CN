---
title: Lync Server 2013：部署网络区域、网站和子网
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
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="73655-102">在 Lync Server 2013 中部署网络区域、网站和子网</span><span class="sxs-lookup"><span data-stu-id="73655-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73655-103">_**主题上次修改时间：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="73655-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="73655-104">部署企业语音后，您需要配置：</span><span class="sxs-lookup"><span data-stu-id="73655-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="73655-105">网络区域</span><span class="sxs-lookup"><span data-stu-id="73655-105">Network regions</span></span>

  - <span data-ttu-id="73655-106">网络站点</span><span class="sxs-lookup"><span data-stu-id="73655-106">Network sites</span></span>

  - <span data-ttu-id="73655-107">网络子网</span><span class="sxs-lookup"><span data-stu-id="73655-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="73655-108">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="73655-108">Define Network Regions</span></span>

<span data-ttu-id="73655-109">使用 Lync Server Windows PowerShell 命令、"新建-CsNetworkRegion" 或 "Lync Server 控制面板" 定义网络区域。</span><span class="sxs-lookup"><span data-stu-id="73655-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="73655-110">有关详细信息，请参阅[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。</span><span class="sxs-lookup"><span data-stu-id="73655-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="73655-111">在此示例中，以下 Windows PowerShell 命令演示了在此方案中定义的网络区域（国家/地区1（印度））。</span><span class="sxs-lookup"><span data-stu-id="73655-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="73655-112">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="73655-112">Define Network Sites</span></span>

<span data-ttu-id="73655-113">使用 Lync Server Windows PowerShell 命令、"新建-CsNetworkSite" 或 "Lync Server 控制面板" 定义网络站点。</span><span class="sxs-lookup"><span data-stu-id="73655-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="73655-114">有关详细信息，请参阅[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。</span><span class="sxs-lookup"><span data-stu-id="73655-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="73655-115">对于此示例，下表和 Lync Server Windows PowerShell 命令演示了在此方案中定义的网络站点。</span><span class="sxs-lookup"><span data-stu-id="73655-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="73655-116">只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="73655-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="73655-117">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="73655-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="73655-118">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="73655-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73655-119">网站 ID</span><span class="sxs-lookup"><span data-stu-id="73655-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="73655-120">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="73655-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="73655-121">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="73655-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73655-122">区域 ID</span><span class="sxs-lookup"><span data-stu-id="73655-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="73655-123">区域1（印度）</span><span class="sxs-lookup"><span data-stu-id="73655-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="73655-124">区域1（印度）</span><span class="sxs-lookup"><span data-stu-id="73655-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="73655-125">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="73655-125">Define Network Subnets</span></span>

<span data-ttu-id="73655-126">使用 Lync Server Windows PowerShell 命令、"新建-CsNetworkSubnet" 或 "Lync Server 控制面板" 定义网络子网并将其分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="73655-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="73655-127">有关详细信息，请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="73655-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="73655-128">对于此示例，下表和 Windows PowerShell 命令演示在此方案中定义的网络子网到 Hyderabad 和的分配。</span><span class="sxs-lookup"><span data-stu-id="73655-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="73655-129">只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="73655-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="73655-130">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="73655-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="73655-131">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="73655-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73655-132">子网 ID</span><span class="sxs-lookup"><span data-stu-id="73655-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="73655-133">含</span><span class="sxs-lookup"><span data-stu-id="73655-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="73655-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="73655-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73655-135">Usm</span><span class="sxs-lookup"><span data-stu-id="73655-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="73655-136">全</span><span class="sxs-lookup"><span data-stu-id="73655-136">24</span></span></p></td>
<td><p><span data-ttu-id="73655-137">全</span><span class="sxs-lookup"><span data-stu-id="73655-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73655-138">网站 ID</span><span class="sxs-lookup"><span data-stu-id="73655-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="73655-139">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="73655-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="73655-140">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="73655-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73655-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73655-141">See Also</span></span>


[<span data-ttu-id="73655-142">在 Lync Server 2013 中配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="73655-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

