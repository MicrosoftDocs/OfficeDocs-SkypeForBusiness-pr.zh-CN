---
title: 在 Lync Server 2013 中部署网络区域、站点和子网
TOCTitle: 在 Lync Server 2013 中部署网络区域、站点和子网
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994067(v=OCS.15)
ms:contentKeyID: 52061116
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署网络区域、站点和子网

 

_**上一次修改主题：** 2015-03-09_

部署企业语音之后，您需要配置：

  - 网络区域

  - 网络站点

  - 网络子网

## 定义网络区域

使用 Lync ServerWindows PowerShell 命令 New-CsNetworkRegion 或 Lync Server 控制面板 定义网络区域。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

有关详细信息，请参阅[New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)。

对于此示例，下面的 Windows PowerShell 命令说明了此方案中定义的网络区域“区域 1（印度）”。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"


## 定义网络站点

使用 Lync ServerWindows PowerShell 命令 New-CsNetworkSite 或 Lync Server 控制面板 定义网络站点。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

有关详细信息，请参阅[New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)。

对于此示例，下表和 Lync ServerWindows PowerShell 命令说明了此方案中定义的网络站点。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

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
<th>站点 1（德里）</th>
<th>站点 2（海得拉巴）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>站点 ID</p></td>
<td><p>站点 1（德里）</p></td>
<td><p>站点 2（海得拉巴）</p></td>
</tr>
<tr class="even">
<td><p>区域 ID</p></td>
<td><p>区域 1（印度）</p></td>
<td><p>区域 1（印度）</p></td>
</tr>
</tbody>
</table>



## 定义网络子网

使用 Lync ServerWindows PowerShell 命令 New-CsNetworkSubnet 或 Lync Server 控制面板 定义网络子网并将它们分配给网络站点。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

有关详细信息，请参阅[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)。

对于此示例，下表和 Windows PowerShell 命令说明了如何为此方案中定义的网络站点“德里”和“海得拉巴”分配网络子网。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

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
<th>站点 1（德里）</th>
<th>站点 2（海得拉巴）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>子网 ID</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>掩码</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>站点 ID</p></td>
<td><p>站点 1（德里）</p></td>
<td><p>站点 2（海得拉巴）</p></td>
</tr>
</tbody>
</table>



## 另请参阅

#### 其他资源

[在 Lync Server 2013 中配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)

