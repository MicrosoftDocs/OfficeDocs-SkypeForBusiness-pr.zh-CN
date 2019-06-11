---
title: 'Lync Server 2013: 部署网络区域、网站和子网'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e75c18a582be046755a54656e9f367edabdda3e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中部署网络区域、网站和子网

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-12_

部署企业语音后, 您需要配置:

  - 网络区域

  - 网络站点

  - 网络子网

<div>

## <a name="define-network-regions"></a>定义网络区域

使用 Lync Server Windows PowerShell 命令、"新建-CsNetworkRegion" 或 "Lync Server 控制面板" 定义网络区域。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

有关详细信息, 请参阅[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。

在此示例中, 以下 Windows PowerShell 命令演示了在此方案中定义的网络区域 (国家/地区 1 (印度))。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>定义网络站点

使用 Lync Server Windows PowerShell 命令、"新建-CsNetworkSite" 或 "Lync Server 控制面板" 定义网络站点。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

有关详细信息, 请参阅[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。

对于此示例, 下表和 Lync Server Windows PowerShell 命令演示了在此方案中定义的网络站点。 只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。

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
<th>站点 1 (新德里)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>网站 ID</p></td>
<td><p>站点 1 (新德里)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>区域 ID</p></td>
<td><p>区域 1 (印度)</p></td>
<td><p>区域 1 (印度)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>定义网络子网

使用 Lync Server Windows PowerShell 命令、"新建-CsNetworkSubnet" 或 "Lync Server 控制面板" 定义网络子网并将其分配给网络站点。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

有关详细信息, 请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

对于此示例, 下表和 Windows PowerShell 命令演示在此方案中定义的网络子网到 Hyderabad 和的分配。 只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。

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
<th>站点 1 (新德里)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>子网 ID</p></td>
<td><p>含</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Usm</p></td>
<td><p>全</p></td>
<td><p>全</p></td>
</tr>
<tr class="odd">
<td><p>网站 ID</p></td>
<td><p>站点 1 (新德里)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

