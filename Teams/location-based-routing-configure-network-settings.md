---
title: 为基于位置的路由配置网络设置
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置用于直接路由的基于位置的路由的网络区域、站点和子网。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570695"
---
# <a name="configure-network-settings-for-location-based-routing"></a>为基于位置的路由配置网络设置

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

如果尚未执行此操作，请阅读[基于计划位置的路由，直接路由](location-based-routing-plan.md)以查看在为基于位置的路由配置网络设置之前需要执行的其他步骤。

本文介绍如何为基于位置的路由配置网络设置。 在组织中部署手机系统直接路由后，下一步是创建和设置网络区域、网络网站和网络子网。 若要完成本文中的步骤，你需要熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

## <a name="define-network-regions"></a>定义网络区域
 网络区域跨多个地理区域互连网络的各个部分。 使用[CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet 定义网络区域。 请注意，RegionID 参数是一个逻辑名称，表示区域的地理位置，并且没有相关性或限制，并且 CentralSite &lt;site ID&gt;参数是可选的。 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

在此示例中，我们创建一个名为 "印度" 的网络区域。 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>定义网络站点

使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 定义网络站点。 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
在此示例中，我们将在印度地区创建两个新的网络站点：新德里和 Hyderabad。 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
下表显示了本示例中定义的网络站点。 

||站点1 |网站2 |
|---------|---------|---------|
|网站 ID    |    站点1（新德里）     |  Site 2 （Hyderabad）       |
|区域 ID  |     区域1（印度）    |   区域1（印度）      |

## <a name="define-network-subnets"></a>定义网络子网

使用[CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 定义网络子网并将其与网络站点相关联。 每个内部子网仅可与一个网站相关联。 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
在此示例中，我们将创建子网192.168.0.0 和新德里网络站点之间以及子网2001之间的关联：4898： e8：25：844e：926f：85ad： dd8e 和 Hyderabad 网络站点。
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
下表显示了在此示例中定义的子网。 

||站点1 |网站2 |
|---------|---------|---------|
|子网 ID   |    含     |  2001：4898： e8：25：844e：926f：85ad： dd8e     |
|Usm  |     全    |   120      |
|网站 ID  | 站点（新德里） | Site 2 （Hyderabad） |

对于多个子网，您可以使用如下所示的脚本导入 CSV 文件。
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
在此示例中，CSV 文件的外观如下所示：
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>定义外部子网
使用[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet 定义外部子网并将其分配给租户。 你可以为租户定义无限数量的子网。 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
例如：
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>后续步骤
转到 "为[直接路由启用基于位置的路由](location-based-routing-enable.md)"。

### <a name="related-topics"></a>相关主题
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [基于位置的路由术语](location-based-routing-terminology.md)
