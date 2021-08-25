---
title: 为直接路由启用基于位置的路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何为直接Location-Based启用路由，包括为用户、网络站点、网关配置和调用策略启用路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8dc1c36c0a82bb7323f5919c788508a4ef028f21
ms.sourcegitcommit: a8965ff7b05ff600e3c426a4fff5fdba8b4c8b0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2021
ms.locfileid: "58523813"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>为直接路由启用基于位置的路由

在按照本文中的步骤操作之前，请确保已阅读规划直接路由Location-Based[](location-based-routing-plan.md)路由，并完成配置路由的网络设置中的[Location-Based步骤](location-based-routing-configure-network-settings.md)。

本文介绍如何为直接路由Location-Based路由。 部署电话系统路由并设置网络区域、站点和子网后，即可启用Location-Based路由。 若要完成本文中的步骤，需要熟悉 PowerShell cmdlet。 有关详细信息，请参阅[PowerShell Teams概述](teams-powershell-overview.md)。

 必须针对以下Location-Based启用路由：
- 用户
- 网络站点
- 网关配置
- 通话策略

可以使用 Microsoft Teams[管理中心](#using-the-microsoft-teams-admin-center)或[PowerShel](#using-powershell)l 来启用Location-Based路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

### <a name="enable-location-based-routing-for-users"></a>为Location-Based启用路由

1. 创建语音路由策略并将 PSTN 使用情况分配给该策略。 将 PSTN 使用情况分配给策略时，请确保执行下列操作之一：

    - 使用与使用站点本地 PSTN 网关的语音路由关联的 PSTN 使用情况。
    - 使用与使用 PSTN 网关的语音路由关联的 PSTN 使用情况，该网关位于Location-Based不需要路由限制的区域。
2. 将语音路由策略分配给需要强制实施路由限制的用户。

若要详细了解如何创建语音路由策略并将其分配给用户，请参阅在 Microsoft Teams 中管理语音[路由策略](manage-voice-routing-policies.md)。

### <a name="enable-location-based-routing-for-network-sites"></a>为Location-Based启用路由

为Location-Based实施路由限制的站点启用路由。 为此，请在 Microsoft Teams 管理中心的左侧导航中，转到"位置""网络拓扑"，选择一个网络站点，单击"编辑"，然后打开"基于位置的路由  >  **"。**   

有关详细信息，请参阅 [管理网络拓扑](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>为Location-Based启用路由

启用Location-Based路由到将呼叫路由到 PSTN 网关的网关，将呼叫路由到 PSTN，并关联网关所在的网络站点。 

1. 在左侧导航中，转到 **"语音**  >  **直接路由"，** 然后单击 **"SDC"** 选项卡。
2. 选择 SBC，然后单击"编辑 **"。** 
3. 在 **"基于位置的路由和媒体优化"下**，启用 **"启用基于位置的路由"。**
4. 指定网关站点 ID，然后设置绕过模式。
5. 单击“**保存**”。

### <a name="enable-location-based-routing-for-calling-policies"></a>为Location-Based启用路由

若要为Location-Based用户强制实施呼叫路由，请设置用户的呼叫策略以防止 PSTN 收费绕过。 为此，请打开呼叫 **策略中的** "防止绕过收费"设置。

若要了解有关详细信息，请参阅[调用 Teams](teams-calling-policy.md)中的策略。

## <a name="using-powershell"></a>使用 PowerShell

### <a name="enable-location-based-routing-for-users"></a>为Location-Based启用路由

1. 使用 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet 设置 PSTN 使用情况。 对于多个用法，请用逗号分隔每个用法。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    例如：
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 创建语音路由策略，将用户与相应的 PSTN 使用情况关联。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    将 PSTN 使用情况分配到语音路由策略时，请确保执行下列操作之一：
    - 使用与使用站点本地 PSTN 网关的语音路由关联的 PSTN 使用情况
    - 使用与使用 PSTN 网关的语音路由关联的 PSTN 使用情况，该网关位于Location-Based不需要路由限制的区域。

    本示例将创建两个新的语音路由策略，并为其分配 PSTN 使用情况。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    下表显示了本示例中定义的语音路由策略。 
    
    ||语音路由策略 1|语音路由策略 2|
    |---------|---------|---------|
    |联机语音策略 ID   |印地语在线语音路由策略   |海得拉巴在线语音路由策略    |
    |联机 PSTN 使用情况  |长距离  |长距离、本地、内部  |

3. 使用 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 将联机语音路由策略关联到需要强制实施路由限制的用户。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>为Location-Based启用路由

1.  使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet 启用 Location-Based 路由并将语音路由策略关联到需要强制实施路由限制的网络站点。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    此示例中，我们为Location-Based和海得拉巴站点启用路由。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表显示了本示例中为Location-Based路由启用的站点。

    ||网站 1 (里尼)   |Site 2 (Hyderabad)   |
    |---------|---------|---------|
|站点名称    |网站 1 (里尼)     |Site 2 (Hyderabad)    
    |EnableLocationBasedRouting    |True    |True    |
    |子网     |子网 1 (里尼)      |Hyderabad (子网 2)      |

### <a name="enable-location-based-routing-for-gateways"></a>为Location-Based启用路由

1. 使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet 为每个网关或网络站点创建网关配置。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    如果多个网关与一个系统 (例如网关或 PBX) ，请修改每个网关以启用Location-Based限制。 

    本示例为每个网关创建一个网关配置。 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。
    
2. 使用 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet 为需要强制实施路由Location-Based网关启用路由。 

    启用Location-Based路由到将呼叫路由到 PSTN 网关的网关，将呼叫路由到 PSTN，并关联网关所在的网络站点。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    本示例为与Location-Based Hyderabad 站点中的 PSTN 网关关联的每个网关启用路由。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    不要为Location-Based PSTN 路由呼叫的网关启用路由。 但是，仍必须将网关关联到系统所在的网络站点。 这是因为对于Location-Based通过此网关连接的终结点的 PSTN 呼叫，需要强制实施路由限制。 本示例中，Location-Based和海得拉巴站点中与 PBX 系统关联的每个网关未启用路由。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>为Location-Based启用路由

若要为Location-Based用户强制实施语音路由，请设置用户的语音策略以防止 PTSN 收费绕过。 

使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet Location-Based PSTN 收费绕过来启用自动路由。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
本示例阻止用户 1 的呼叫策略绕过 PSTN 收费。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>相关主题

- [云语音功能的网络设置Teams](cloud-voice-network-settings.md)