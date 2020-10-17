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
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531139"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中部署网络区域、站点和子网

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-12_

部署企业语音后，您需要配置以下各项：

  - 网络区域

  - 网络站点

  - 网络子网

<div>

## <a name="define-network-regions"></a>定义网络区域

使用 Lync Server Windows PowerShell 命令、CsNetworkRegion 或 Lync Server 控制面板定义网络区域。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

有关详细信息，请参阅 [CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。

在此示例中，以下 Windows PowerShell 命令说明了在此方案中定义的网络区域（区域 1 (印度) ）。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>定义网络站点

使用 Lync Server Windows PowerShell 命令、CsNetworkSite 或 Lync Server 控制面板定义网络站点。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

有关详细信息，请参阅 [CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。

对于此示例，下表和 Lync Server Windows PowerShell 命令说明了此方案中定义的网络站点。 为了便于说明，表中仅包括特定于 Location-Based 路由的设置。

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
<th>Site 1 (新德里) </th>
<th>Site 2 (Hyderabad) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>网站 ID</p></td>
<td><p>Site 1 (新德里) </p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
<tr class="even">
<td><p>区域 ID</p></td>
<td><p>区域 1 (印度) </p></td>
<td><p>区域 1 (印度) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>定义网络子网

使用 Lync Server Windows PowerShell 命令、CsNetworkSubnet 或 Lync Server 控制面板定义网络子网并将其分配给网络站点。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

有关详细信息，请参阅 [CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

对于此示例，下表和 Windows PowerShell 命令说明了如何将网络子网分配给在此方案中定义的网络站点（新德里和 Hyderabad）。 为了便于说明，表中仅包括特定于 Location-Based 路由的设置。

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
<th>Site 1 (新德里) </th>
<th>Site 2 (Hyderabad) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>子网 ID</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Mask</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>网站 ID</p></td>
<td><p>Site 1 (新德里) </p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置 Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

