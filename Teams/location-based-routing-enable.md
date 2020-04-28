---
title: 为直接路由启用基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何为直接路由启用基于位置的路由，包括为用户、网络站点、网关配置和呼叫策略启用它。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56ea3f8b27a582a9cea282244a03be692d0781be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905774"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>为直接路由启用基于位置的路由

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

在按照本文中的步骤操作之前，请确保已阅读[基于计划位置的路由以进行直接路由](location-based-routing-plan.md)，并完成了为[基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)中的步骤。

本文介绍如何为直接路由启用基于位置的路由。 部署手机系统直接路由和设置网络区域、网站和子网后，您就可以启用基于位置的路由。 若要完成本文中的步骤，你需要熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

 您必须启用以下各项的基于位置的路由：
- 用户
- 网络站点
- 网关配置
- 通话政策

## <a name="enable-location-based-routing-for-users"></a>为用户启用基于位置的路由

1. 使用[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) CMDLET 设置 PSTN 用法。 对于多种用途，用逗号分隔每个用法。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    例如：
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 创建语音路由策略，以将用户与适当的 PSTN 用法关联起来。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    将 PSTN 使用分配给语音路由策略时，请确保执行下列操作之一：
    - 使用与使用网站本地的 PSTN 网关的语音路由相关联的 PSTN 用法
    - 使用与使用不需要基于位置的路由限制的区域中的 PSTN 网关相关的语音路由的 PSTN 用法。

    在此示例中，我们将创建两个新的语音路由策略，并向其分配 PSTN 使用情况。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    下表显示了本示例中定义的语音路由策略。 
    
    ||语音路由策略1|语音路由策略2|
    |---------|---------|---------|
    |在线语音政策 ID   |新德里 online 语音路由策略   |Hyderabad online 语音路由策略    |
    |联机 PSTN 使用  |长途  |长途、本地、内部  |

3. 使用[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 将联机语音路由策略与需要执行路由限制的用户相关联。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>为网络站点启用基于位置的路由
1.  使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 启用基于位置的路由，并将语音路由策略与你的网络站点进行关联，以强制执行路由限制。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    在此示例中，我们为新德里网站和 Hyderabad 网站启用基于位置的路由。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表显示了在此示例中为基于位置的路由启用的网站。

    ||站点1（新德里）  |Site 2 （Hyderabad）  |
    |---------|---------|---------|
|站点名称    |站点1（新德里）    |Site 2 （Hyderabad）   
    |EnableLocationBasedRouting    |True    |True    |
    |子网     |子网1（新德里）     |子网2（Hyderabad）     |

## <a name="enable-location-based-routing-for-gateways"></a>启用网关的基于位置的路由
1. 使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet 为每个网关或网络网站创建网关配置。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    如果多个网关与系统（例如网关或 PBX）相关联，请修改每个网关以启用基于位置的路由限制。 

    在此示例中，我们为每个网关创建一个网关配置。 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。
    
2. 使用[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet 为你的网关启用需要强制使用路由限制的基于位置的路由。 

    支持将呼叫路由到将呼叫路由到 PSTN 的 PSTN 网关的基于位置的路由，并关联网关所在的网络站点。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    在此示例中，我们为与新德里和 Hyderabad 网站中的 PSTN 网关相关联的每个网关启用基于位置的路由。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    不要为不将调用路由到 PSTN 的网关启用基于位置的路由。 但是，您仍然必须将网关与系统所在的网络站点相关联。 这是因为基于位置的路由限制需要强制实施 PSTN 呼叫，从而达到通过此网关连接的终结点。 在此示例中，没有为与新德里和 Hyderabad 网站中的 PBX 系统相关联的每个网关启用基于位置的路由。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    连接到不路由到 PSTN 的系统的终结点（例如，PBX）将具有类似于为基于位置的路由启用的团队用户的终结点的限制。 这意味着，无论用户的位置如何，这些用户都可以与团队用户进行呼叫和接收呼叫。 他们还可以在不将呼叫路由到 PSTN 网络的其他系统（例如，连接到其他 PBX 的终结点）的情况下与其他系统进行呼叫和接收呼叫，而不管与系统关联的网络站点。 所有入站呼叫、出站呼叫、呼叫转移以及涉及 PSTN 终结点的呼叫转移将受到基于位置的路由 enforcements。 这些调用必须仅使用定义为此类系统本地的 PSTN 网关。 

    下表显示两个不同网络站点中的四个网关的网关配置：两个连接到 PSTN 网关的两个网关和连接到 PBX 系统的两个。 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway：网关 1 DEL-GW    |    True     |   站点1（新德里）      |
    |PstnGateway：网关 2 HYD-GW     |   True      |      Site 2 （Hyderabad）   |
    |PstnGateway：网关 3 DEL-PBX    |    False     |     站点1（新德里）    |
    |PstnGateway：网关 4 HYD-PBX    |    False     |    Site 2 （Hyderabad）     |

## <a name="enable-location-based-routing-for-calling-policies"></a>为呼叫策略启用基于位置的路由

若要为特定用户强制执行基于位置的路由，请设置用户的语音策略，以防止 PTSN 收费旁路。 

通过阻止 PSTN 免绕过，使用[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet 启用基于位置的路由。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
在此示例中，我们将阻止 PSTN 免绕过 User1's 呼叫策略。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>相关主题

- [团队中云语音功能的网络设置](cloud-voice-network-settings.md)
