---
title: 为基于位置的路由配置网络设置
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置网络区域、 网站和子网为基于位置的路由直接路由。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222360"
---
# <a name="configure-network-settings-for-location-based-routing"></a>为基于位置的路由配置网络设置

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

如果您尚未进行，请阅读[Plan Location-Based 路由直接路由中](location-based-routing-plan.md)查看您需要执行其他步骤之后，配置基于位置的路由的网络设置。

本文介绍如何配置基于位置的路由的网络设置。 在组织中部署电话系统直接路由后下, 一步步骤是创建和设置网络区域、 网络站点和网络子网。 若要完成本文中的步骤，您将需要一些熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

## <a name="define-network-regions"></a>定义网络区域
 网络区域互连跨多个地理区域的网络的各个部分。 [新建 CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet 用于定义网络区域。 请注意，RegionID 参数是逻辑名称，它代表区域的地理位置和已没有依赖项或限制和 CentralSite&lt;网站 ID&gt;参数是可选的。 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

本示例中，我们将创建名为印度网络区域。 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>定义网络站点

[新建 CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 用于定义网络站点。 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
本示例中，我们将创建两个新网络站点，德里和海德拉巴，印度区域中。 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
下表显示了在此示例中定义的网络站点。 

||站点 1 |站点 2 |
|---------|---------|---------|
|网站 ID    |    站点 1 （德里）     |  站点 2 （海德拉巴）       |
|地区 ID  |     区域 1 （印度）    |   区域 1 （印度）      |

## <a name="define-network-subnets"></a>定义网络子网

[新建 CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 用于定义网络子网，并将它们关联到网络站点。 每个内部子网只能与一个站点关联。 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
本示例中，我们将创建子网 192.168.0.0 之间德里网络站点和子网为 192.168.1.0 和海德拉巴网络站点之间的关联。
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
下表显示了在此示例中定义的子网。 

||站点 1 |站点 2 |
|---------|---------|---------|
|子网 ID   |    192.168.0.0     |  192.168.1.0     |
|掩码  |     24    |   24      |
|网站 ID  | 网站 （德里） | 站点 2 （海德拉巴） |

对于多子网，您可以使用如下所示脚本导入 CSV 文件。
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
本示例中，该 CSV 文件如下所示：
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>定义外部子网
[新建 CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet 用于定义外部子网，并将其分配到租户。 您可以定义任意的数量的子网租户。 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
例如：
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>后续步骤
转到[启用直接路由基于位置的路由](location-based-routing-enable.md)。

### <a name="related-topics"></a>相关主题
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [基于位置的路由术语](location-based-routing-terminology.md)
