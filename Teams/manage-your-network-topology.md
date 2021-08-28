---
title: 管理云语音功能的网络拓扑Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在云语音中配置云语音功能的网络Microsoft Teams。
ms.openlocfilehash: 7ed9837b676197b588669ae95db77c9e834371dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598416"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>管理云语音功能的网络拓扑Microsoft Teams

如果组织为直接路由或[](location-based-routing-plan.md)动态紧急呼叫部署基于位置的路由[](configure-dynamic-emergency-calling.md)，则必须配置网络设置，以在 Microsoft Teams 中使用这些云语音功能。 网络设置用于确定客户端Teams，包括网络区域、网络站点、子网和受信任的 IP 地址。 根据要部署的云语音功能，可以配置其中一些或所有设置。 若要详细了解这些条款，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

在管理中心的"网络 **拓扑**"页上Microsoft Teams配置网络设置，或者使用 Windows PowerShell。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>在管理中心Microsoft Teams设置

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在"网络拓扑"页的"网络站点"选项卡上定义网络区域、**网络站点和** 子网。 可在此处创建或修改网络站点、将站点与网络区域关联、将子网关联到站点、启用基于位置的路由，以及向站点分配紧急策略。 还可以添加可全局用于所有站点的网络区域。

#### <a name="add-and-configure-a-network-site"></a>添加和配置网络站点

1. 在管理中心的左侧导航Microsoft Teams，转到"位置  >  **""网络拓扑**"，然后单击"网络 **站点"** 选项卡。
2. 单击 **"** 添加"，然后输入网站的名称和说明。

    !["添加网络站点"页的屏幕截图](media/manage-network-topology-add-site.png)

3. 若要将站点与网络区域关联，请单击"添加网络区域"，选择现有区域或单击"添加"以添加区域，然后单击"链接 **"。**  
4. 若要为Location-Based启用"基于位置的路由"，请启用 **"基于位置的路由"。**
5. 若要向网站分配紧急服务策略，请执行下列一项或两项操作：

    - 如果你的组织使用"呼叫计划"或电话系统直接路由"，请在"紧急呼叫策略"下选择想要的策略。
    - 如果组织已电话系统直接路由，**请在"紧急** 呼叫路由策略"下选择想要的策略。

6. 若要将子网关联到站点，请在 **"子网"下** 单击"**添加子网"。** 指定 IP 版本、IP 地址、网络范围，添加说明，并单击"应用 **"。** 每个子网必须与特定站点相关联。
7. 单击“**保存**”。

#### <a name="modify-a-network-site"></a>修改网络站点

1. 在管理中心的左侧导航Microsoft Teams，转到"位置  >  **""网络拓扑**"，然后单击"网络 **站点"** 选项卡。
2. 单击网站名称左侧选择网站，然后单击"编辑 **"。**
3. 进行您需要的更改，然后单击"保存 **"。**

### <a name="manage-external-trusted-ip-addresses"></a>管理外部受信任的 IP 地址

在管理中心的"网络拓扑"页上的"受信任的 IP"选项卡上管理Microsoft Teams IP 地址。 可以添加无限数量的外部受信任 IP 地址。

#### <a name="add-a-trusted-ip-address"></a>添加受信任的 IP 地址

1. 在管理中心的左侧导航Microsoft Teams，转到"位置""网络拓扑"，然后单击"受信任的  >  **IP"** 选项卡。
2. 单击“新建”。
3. 在"**添加受信任的 IP 地址**"窗格中，指定 IP 版本、IP 地址、网络范围，添加说明，并单击"应用 **"。**

    !["添加受信任的 IP 地址"窗格的屏幕截图](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>编辑受信任的 IP 地址

1. 在管理中心的左侧导航Microsoft Teams，转到"位置""网络拓扑"，然后单击"受信任的  >  **IP"** 选项卡。
2. 单击 IP 地址的左侧，选择该 IP 地址，然后单击"编辑 **"。**
3. 在 **"编辑受信任的 IP 地址**"窗格中，进行想要的更改，然后单击"应用 **"。**

## <a name="configure-network-settings-using-powershell"></a>使用 PowerShell 配置网络设置

若要完成本部分中的步骤，需要熟悉 PowerShell cmdlet。 有关详细信息，请参阅[PowerShell Teams概述](teams-powershell-overview.md)。

### <a name="define-network-regions"></a>定义网络区域

 使用 [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet 定义网络区域。 请注意，RegionID 参数是表示区域地理位置的逻辑名称，没有依赖项或限制，CentralSite 站点 ID 参数 &lt; &gt; 是可选的。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

本示例创建名为"印度"的网络区域。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

另请参阅[Set-CsTenantNetworkRegion。](/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>定义网络站点

使用 [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 定义网络站点。 每个网络站点必须与网络区域相关联。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

本示例将印度区域创建两个新的网络站点，即"通信"和"海得拉巴"。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

下表显示了本示例中定义的网络站点。

||站点 1 |站点 2 |
|---------|---------|---------|
|站点 ID    |    网站 1 (里尼)      |  Site 2 (Hyderabad)        |
|区域 ID  |     印度 (区域 1)     |   印度 (区域 1)       |

另请参阅[Set-CsTenantNetworkRegion。](/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>定义网络子网

使用 [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 定义网络子网并将其关联到网络站点。 每个网络子网只能与一个站点相关联。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

本示例在子网 192.168.0.0 与乌克兰网络站点之间以及子网 2001：4898：e8：25：844e：926f：85ad：dd8e 与 Hyderabad 网络站点之间创建关联。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

下表显示了本示例中定义的子网。

||站点 1 |站点 2 |
|---------|---------|---------|
|子网 ID   |    192.168.0.0     |  2001：4898：e8：25：844e：926f：85ad：dd8e     |
|Mask  |     24    |   120      |
|站点 ID  | Site (一)  | Site 2 (Hyderabad)  |

对于多个子网，可以使用如下脚本导入 CSV 文件。

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

本示例中的 CSV 文件如下所示：

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


另请参阅[Set-CsTenantNetworkSubnet。](/powershell/module/skype/set-cstenantnetworksubnet)


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>定义外部子网 (外部受信任的 IP 地址) 

使用 [New-CsTenantTrustedIPAddress cmdlet](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) 定义外部子网并将其分配给租户。 可以定义无限数量的租户外部子网。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

例如：

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

另请参阅 [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress)。

## <a name="related-topics"></a>相关主题

- [云语音功能的网络设置Teams](cloud-voice-network-settings.md)
