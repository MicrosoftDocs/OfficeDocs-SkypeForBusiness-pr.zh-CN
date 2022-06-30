---
title: 为直接路由启用基于位置的路由
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何为直接路由启用Location-Based路由，包括为用户、网络站点、网关配置和调用策略启用它。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562191"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>为直接路由启用基于位置的路由

本文介绍如何为直接路由启用Location-Based路由。 在执行本文中的步骤之前，请确保已阅读 [直接路由的计划Location-Based路由](location-based-routing-plan.md) ，并完成了 [为Location-Based路由配置网络设置](location-based-routing-configure-network-settings.md)中的步骤。

 部署直接路由并设置网络区域、站点和子网后，即可启用Location-Based路由。 若要完成本文中的步骤，需要熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅 [Teams PowerShell 概述](teams-powershell-overview.md)

 必须为以下内容启用Location-Based路由：

- 用户
- 网络站点
- 网关配置
- 通话策略

可以使用 [Teams 管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShell](#using-powershell) 启用Location-Based路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

### <a name="enable-location-based-routing-for-users"></a>为用户启用Location-Based路由

1. 创建语音路由策略并将 PSTN 用法分配给策略。 将 PSTN 用法分配到策略时，请确保执行下列操作之一：

    - 使用与使用本地到站点的 PSTN 网关的语音路由关联的 PSTN 用法。

    - 使用与使用 PSTN 网关的语音路由关联的 PSTN 用法，该网关位于不需要Location-Based路由限制的区域中。

2. 将语音路由策略分配给需要强制实施路由限制的用户。

若要详细了解如何创建语音路由策略并将其分配给用户，请参阅 [Microsoft Teams 中的“管理语音路由策略](manage-voice-routing-policies.md)”。

### <a name="enable-location-based-routing-for-network-sites"></a>为网络站点启用Location-Based路由

为需要强制实施路由限制的站点启用Location-Based路由。 为此，请在 Microsoft Teams 管理中心的左侧导航中，转到 **“位置** > **网络拓扑**”，选择一个网络站点，单击 **“编辑**”，然后启用 **基于位置的路由**。  

若要了解详细信息，请参阅 [“管理网络拓扑](manage-your-network-topology.md)”。

### <a name="enable-location-based-routing-for-gateways"></a>为网关启用Location-Based路由

启用Location-Based路由到将调用路由到 PSTN 的 PSTN 网关的网关，并将网关所在的网络站点关联。 

1. 在左侧导航栏中，转到 **“语音** > **直接路由**”，然后单击 **“SBC”** 选项卡。

2. 选择 SBC，然后单击 **“编辑**”。 

3. 在 **基于位置的路由和媒体优化** 下，启 **用基于位置的路由**。

4. 指定网关站点 ID，然后设置旁路模式。

5. 单击“**保存**”。

### <a name="enable-location-based-routing-for-calling-policies"></a>为调用策略启用Location-Based路由

若要对特定用户强制执行Location-Based路由，请设置用户的调用策略以防止 PSTN 通行费绕过。 为此，请在调用策略中启用 **“阻止通行费旁路** 设置”。

若要了解详细信息，请参阅 [Teams 中的通话策略](teams-calling-policy.md)。

## <a name="using-powershell"></a>使用 PowerShell

### <a name="enable-location-based-routing-for-users"></a>为用户启用Location-Based路由

1. 若要设置 PSTN 使用情况，请使用 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet。 对于多个用法，请使用逗号分隔每个用法。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    例如：

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. 若要创建语音路由策略以将用户与适当的 PSTN 使用情况相关联，请使用 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    将 PSTN 用法分配到语音路由策略时，请确保执行下列操作之一：

    - 使用与使用本地到站点的 PSTN 网关的语音路由关联的 PSTN 用法。

    - 使用与使用 PSTN 网关的语音路由关联的 PSTN 用法，该网关位于不需要Location-Based路由限制的区域中。

    以下示例创建两个新的语音路由策略，并向其分配 PSTN 用法。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    下表显示了本示例中定义的语音路由策略。 
    
    |&nbsp;|语音路由策略 1|语音路由策略 2|
    |---------|---------|---------|
    |联机语音策略 ID   |德里在线语音路由政策   |海得拉巴在线语音路由策略    |
    |联机 PSTN 使用情况  |长距离  |长距离、本地、内部  |

3. 若要将联机语音路由策略关联到需要强制实施路由限制的用户，请使用 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet。

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>为网络站点启用Location-Based路由

1. 若要启用Location-Based路由并将语音路由策略关联到需要强制实施路由限制的网络站点，请使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet。

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    本示例为德里站点和海得拉巴站点启用Location-Based路由。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表显示了在此示例中为Location-Based路由启用的站点。

    |&nbsp;|德里)  (1号站点  |海得拉巴)  (站点 2  |
    |---------|---------|---------|
    |站点名称    |德里)  (1号站点    |海得拉巴)  (站点 2|
    |EnableLocationBasedRouting    |True    |True    |
    |子网     | (德里) 子网 1     |海得拉巴 (子网 2)      |


### <a name="enable-location-based-routing-for-gateways"></a>为网关启用Location-Based路由

1. 若要为每个网关或网络站点创建网关配置，请使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    如果多个网关与系统 (（例如网关或 PBX) ）关联，请修改每个网关以启用Location-Based路由限制。 

    以下示例为每个网关创建一个网关配置。 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。
    
2. 若要为需要强制实施路由限制的网关启用Location-Based路由，请使用 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet。 

    启用Location-Based路由到将调用路由到 PSTN 的 PSTN 网关的网关，并将网关所在的网络站点关联。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   以下示例为与德里和海得拉巴站点的 PSTN 网关关联的每个网关启用Location-Based路由。 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    请勿为不将调用路由到 PSTN 的网关启用Location-Based路由。 但是，仍必须将网关关联到系统所在的网络站点。 这是因为需要对通过此网关连接的终结点的 PSTN 调用实施Location-Based路由限制。 在此示例中，不会为与德里和海得拉巴站点中的 PBX 系统关联的每个网关启用Location-Based路由。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>为调用策略启用Location-Based路由

若要对特定用户强制执行Location-Based路由，请设置用户的语音策略以防止 PTSN 收费旁路。 

若要通过防止 PSTN 通行费旁路来启用Location-Based路由，请使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet。


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

在此示例中，我们防止 PSTN 通行费绕过 User1 的调用策略。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>相关主题

- [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)