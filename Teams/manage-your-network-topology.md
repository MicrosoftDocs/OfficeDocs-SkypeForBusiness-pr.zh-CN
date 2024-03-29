---
title: 在 Microsoft Teams 中管理云语音功能的网络拓扑
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中为云语音功能配置网络设置。
ms.openlocfilehash: bdb81fa7f8dee559f7c47e276224ecb2333c7bb5
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812689"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>在 Microsoft Teams 中管理云语音功能的网络拓扑

如果你的组织正在 [为直接路由](location-based-routing-plan.md) 或 [动态紧急呼叫](configure-dynamic-emergency-calling.md)部署基于位置的路由，则必须配置网络设置以用于 Microsoft Teams 中的这些云语音功能。 网络设置用于确定 Teams 客户端的位置，包括网络区域、网络站点、子网和受信任的 IP 地址。 根据要部署的云语音功能和功能，可以配置部分或所有这些设置。 若要详细了解这些术语，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。

可以在 Microsoft Teams 管理中心的“**网络拓扑**”页上或使用 Windows PowerShell 配置网络设置。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心配置网络设置

可以在“网络拓扑”页的“网络站点”选项卡上定义网络区域、**网络****站点** 和子网。 在这里，可以创建或修改网络站点，将站点与网络区域关联，将子网关联到站点，打开基于位置的路由，并向站点分配紧急策略。 还可以添加可全局用于所有站点的网络区域。

#### <a name="add-and-configure-a-network-site"></a>添加和配置网络站点

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“位置** > **网络拓扑**”，然后单击“ **网络站点** ”选项卡。
2. 单击“ **添加”**，然后输入站点的名称和说明。

    ![“添加网络站点”页的屏幕截图。](media/manage-network-topology-add-site.png)

3. 若要将站点与网络区域关联，请单击“ **添加网络区域**”，选择现有区域或单击“ **添加** ”添加区域，然后单击“ **链接**”。  
4. 若要为站点启用Location-Based路由，请启用 **基于位置的路由**。
5. 若要将紧急服务策略分配到站点，请执行以下一项或两项操作：

    - 如果你的组织使用通话套餐、运营商连接或直接路由，请在 **“紧急呼叫策略**”下选择所需的策略。
    - 如果组织部署了直接路由，请在 **“紧急呼叫路由策略**”下选择所需的策略。

6. 若要将子网关联到站点，请在“ **子网**”下单击“ **添加子网**”。 指定 IP 版本、IP 地址、网络范围，添加说明，然后单击“ **应用**”。 每个子网必须与特定站点关联。
7. 单击“**保存**”。

#### <a name="modify-a-network-site"></a>修改网络站点

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“位置** > **网络拓扑**”，然后单击“ **网络站点** ”选项卡。
2. 通过单击网站名称左侧选择网站，然后单击 **“编辑**”。
3. 进行所需的更改，然后单击“ **保存”。**

### <a name="manage-external-trusted-ip-addresses"></a>管理外部受信任的 IP 地址

可在 Microsoft Teams 管理中心的“**网络拓扑**”页上的“**受信任的 IP**”选项卡上管理外部受信任的 IP 地址。 可以添加无限数量的外部受信任 IP 地址。

#### <a name="add-a-trusted-ip-address"></a>添加受信任的 IP 地址

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“位置** > **网络拓扑**”，然后单击“ **受信任的 IP** ”选项卡。
2. 单击“新建”。
3. 在 **“添加受信任的 IP 地址** ”窗格中，指定 IP 版本、IP 地址、网络范围，添加说明，然后单击“ **应用**”。

    ![“添加受信任的 IP 地址”窗格的屏幕截图。](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>编辑受信任的 IP 地址

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“位置** > **网络拓扑**”，然后单击“ **受信任的 IP** ”选项卡。
2. 单击该 IP 地址左侧，选择该地址，然后单击“ **编辑**”。
3. 在 **“编辑受信任的 IP 地址** ”窗格中，进行所需的更改，然后单击“ **应用**”。

## <a name="configure-network-settings-using-powershell"></a>使用 PowerShell 配置网络设置

若要完成本部分中的步骤，需要熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅 [Teams PowerShell 概述](teams-powershell-overview.md)。

### <a name="define-network-regions"></a>定义网络区域

 使用 [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet 定义网络区域。 请注意，RegionID 参数是一个逻辑名称，表示区域的地理位置，没有依赖项或限制，CentralSite &lt;站点 ID&gt; 参数是可选的。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

在此示例中，我们将创建一个名为 India 的网络区域。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

另请参阅 [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion)。

### <a name="define-network-sites"></a>定义网络站点

使用 [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet 定义网络站点。 每个网络站点必须与网络区域相关联。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

在此示例中，我们在印度区域创建了两个新网络站点，即德里和海得拉巴。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

下表显示了此示例中定义的网络站点。

|&nbsp;|站点 1 |站点 2 |
|---------|---------|---------|
|站点 ID    |    德里)  (站点 1     |  海得拉巴)  (站点 2       |
|区域 ID  |     区域 1 (印度)     |   区域 1 (印度)       |

另请参阅 [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite)。

### <a name="define-network-subnets"></a>定义网络子网

使用 [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet 定义网络子网并将其关联到网络站点。 每个网络子网只能与一个站点关联。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

在此示例中，我们在子网 192.168.0.0 和德里网络站点之间以及子网 2001：4898：e8：25：844e：926f：85ad：dd8e 和 Hyderabad 网络站点之间创建关联。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

下表显示了此示例中定义的子网。

|&nbsp;|站点 1 |站点 2 |
|---------|---------|---------|
|子网 ID   |    192.168.0.0     |  2001：4898：e8：25：844e：926f：85ad：dd8e     |
|面具  |     24    |   120      |
|站点 ID  | 德里) 网站 ( | 海得拉巴)  (站点 2 |

对于多个子网，可以使用如下所示的脚本导入 CSV 文件。

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

在此示例中，CSV 文件如下所示：

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


另请参阅 [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet)。


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>定义外部子网 (外部受信任 IP 地址) 

使用 [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet 定义外部子网并将其分配给租户。 可以为租户定义无限数量的外部子网。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

例如：

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

另请参阅 [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress)。

## <a name="enabling-network-roaming-policies"></a>启用网络漫游策略

配置网络漫游策略后，需要在 Teams 管理员中心会议策略下的每个 _ *Meeting Policies** 中启用 **网络配置查找****>。**

你可能希望编辑全局策略，或创建新策略并将策略分配给特定用户。

## <a name="related-topics"></a>相关主题

- [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)
