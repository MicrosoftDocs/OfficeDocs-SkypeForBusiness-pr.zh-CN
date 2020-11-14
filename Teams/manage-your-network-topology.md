---
title: 在 Microsoft 团队中管理云语音功能的网络拓扑
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何为 Microsoft 团队中的云语音功能配置网络设置。
ms.openlocfilehash: 2414010a6e7098a18954067dad659cb8c9912736
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031098"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>在 Microsoft 团队中管理云语音功能的网络拓扑

如果你的组织为 [直接路由](location-based-routing-plan.md) 或 [动态紧急呼叫](configure-dynamic-emergency-calling.md)部署基于位置的路由，则必须在 Microsoft 团队中配置用于这些云语音功能的网络设置。 网络设置用于确定团队客户端的位置，包括网络区域、网络站点、子网和受信任的 IP 地址。 你可以配置部分或所有这些设置，具体取决于你部署的云语音功能和功能。 若要了解有关这些术语的详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

在 Microsoft 团队管理中心或使用 Windows PowerShell 的 " **网络拓扑** " 页面上配置网络设置。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中配置网络设置

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在 " **网络拓扑结构** " 页面的 " **网络站点** " 选项卡上定义网络区域、网络站点和子网。 在此处，你可以创建或修改网络网站、将网站与网络区域关联、将子网关联到网站、打开基于位置的路由，以及向网站分配紧急策略。 你还可以添加可针对所有网站全局使用的网络区域。

#### <a name="add-and-configure-a-network-site"></a>添加和配置网络网站

1. 在 Microsoft 团队管理中心的左侧导航中，转到 " **位置**  >  **网络拓扑** "，然后单击 " **网络站点** " 选项卡。
2. 单击 " **添加** "，然后输入网站的名称和说明。

    !["添加网络" 网站页面的屏幕截图](media/manage-network-topology-add-site.png)

3. 若要将网站与网络区域相关联，请单击 " **添加网络区域** "，选择现有区域或单击 " **添加** " 以添加区域，然后单击 " **链接** "。  
4. 若要为网站启用 Location-Based 路由，请打开 **基于位置的路由** 。
5. 若要向网站分配紧急服务策略，请执行下列一项或两项操作：

    - 如果您的组织使用呼叫计划或部署的电话系统直接路由，请在 " **紧急呼叫策略** " 下，选择所需的策略。
    - 如果您的组织部署了 "电话系统直接路由"，请在 " **紧急呼叫路由策略** " 下，选择所需的策略。

6. 要将子网与网站相关联，请在 " **子网** " 下单击 " **添加子网** "。 指定 "IP 版本"、"IP 地址"、"网络范围"、"添加说明"，然后单击 " **应用** "。 每个子网都必须与特定网站相关联。
7. 单击“ **保存** ”。

#### <a name="modify-a-network-site"></a>修改网络网站

1. 在 Microsoft 团队管理中心的左侧导航中，转到 " **位置**  >  **网络拓扑** "，然后单击 " **网络站点** " 选项卡。
2. 通过单击网站名称左侧的位置选择网站，然后单击 " **编辑** "。
3. 进行所需的更改，然后单击 " **保存"。**

### <a name="manage-external-trusted-ip-addresses"></a>管理外部受信任的 IP 地址

可在 Microsoft 团队管理中心的 " **网络拓扑** " 页面上的 " **受信任** 的 ip" 选项卡上管理外部受信任的 IP 地址。 你可以添加不限数量的外部受信任 IP 地址。

#### <a name="add-a-trusted-ip-address"></a>添加受信任的 IP 地址

1. 在 Microsoft 团队管理中心的左侧导航中，转到 " **位置**  >  **网络拓扑** "，然后单击 " **受信任的 ip** " 选项卡。
2. 单击“新建”。
3. 在 " **添加信任的 IP 地址** " 窗格中，指定 "ip 版本"、"ip 地址"、"网络范围"、"添加说明"，然后单击 " **应用** "。

    !["添加信任的 IP 地址" 窗格的屏幕截图](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>编辑受信任的 IP 地址

1. 在 Microsoft 团队管理中心的左侧导航中，转到 " **位置**  >  **网络拓扑** "，然后单击 " **受信任的 ip** " 选项卡。
2. 通过单击 IP 地址左侧的，然后单击 " **编辑** " 来选择 IP 地址。
3. 在 " **编辑信任的 IP 地址** " 窗格中，进行所需的更改，然后单击 " **应用** "。

## <a name="configure-network-settings-using-powershell"></a>使用 PowerShell 配置网络设置

若要完成本部分中的步骤，你需要熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅 [团队 PowerShell 概述](teams-powershell-overview.md)。

### <a name="define-network-regions"></a>定义网络区域

 使用 [CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet 定义网络区域。 请注意，RegionID 参数是一个逻辑名称，表示区域的地理位置，并且没有相关性或限制，并且 CentralSite &lt; SITE ID &gt; 参数是可选的。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

在此示例中，我们创建一个名为 "印度" 的网络区域。
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

另请参阅 [设置-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)。

### <a name="define-network-sites"></a>定义网络站点

使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 定义网络站点。 每个网络站点都必须与一个网络区域相关联。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

在此示例中，我们将在印度地区创建两个新的网络站点：新德里和 Hyderabad。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

下表显示了本示例中定义的网络站点。

||站点1 |网站2 |
|---------|---------|---------|
|网站 ID    |    站点 1 (新德里)      |  网站 2 (Hyderabad)        |
|区域 ID  |     地区 1 (印度)     |   地区 1 (印度)       |

另请参阅 [设置-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)。

### <a name="define-network-subnets"></a>定义网络子网

使用 [CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 定义网络子网并将其与网络站点相关联。 每个网络子网只能与一个网站相关联。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

在此示例中，我们将创建子网192.168.0.0 和新德里网络站点之间以及子网2001之间的关联：4898： e8：25：844e：926f：85ad： dd8e 和 Hyderabad 网络站点。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

下表显示了在此示例中定义的子网。

||站点1 |网站2 |
|---------|---------|---------|
|子网 ID   |    含     |  2001：4898： e8：25：844e：926f：85ad： dd8e     |
|Usm  |     全    |   120      |
|网站 ID  |  (新德里) 的网站 | 网站 2 (Hyderabad)  |

对于多个子网，您可以使用如下所示的脚本导入 CSV 文件。

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

在此示例中，CSV 文件的外观如下所示： 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

另请参阅 [设置-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)。

### <a name="define-external-subnets-external-trusted-ip-addresses"></a> (外部受信任的 IP 地址定义外部子网) 

使用 [CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet 定义外部子网并将其分配给租户。 你可以为租户定义无限数量的外部子网。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

例如：

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

另请参阅 [设置-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)。

## <a name="related-topics"></a>相关主题

- [团队中云语音功能的网络设置](cloud-voice-network-settings.md)
