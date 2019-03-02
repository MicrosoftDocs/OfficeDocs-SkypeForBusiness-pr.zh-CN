---
title: 为直接路由启用基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 了解如何启用基于位置的路由，以便直接路由。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854f0fefc006c02bc07c73cd4519b943411094f5
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352543"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>为直接路由启用基于位置的路由

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

在按照本文中的步骤之前，请确保您已阅读[Plan Location-Based 路由直接路由](location-based-routing-plan.md)并完成[配置的基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)中的步骤。

本文介绍如何启用基于位置的路由，以便直接路由。 在部署电话系统直接路由，并设置网络区域、 网站和子网后，您已准备好启用基于位置的路由。 若要完成本文中的步骤，您将需要一些熟悉 PowerShell cmdlet。 若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

 您必须启用以下基于位置的路由：
- 用户
- 网络站点
- 网关配置
- 调用策略

## <a name="enable-location-based-routing-for-users"></a>启用的用户的基于位置的路由

1. 使用``Set-CsOnlinePstnUsages``cmdlet 设置 PSTN 用法。 使用多个实例，用逗号分隔每个使用率。

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    例如：
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用``New-CsOnlineVoiceRoutingPolicy``cmdlet 以创建语音路由策略，以将用户与相应的 PSTN 用法相关联。

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    当您将 PSTN 用法分配语音路由策略时时，请确保您执行下列选项之一：
    - 使用对网站使用本地 PSTN 网关的语音路由相关联的 PSTN 用法
    - 使用与使用 PSTN 网关位于其中不需要基于位置的路由限制区域中的语音路由相关联的 PSTN 用法。

    本示例中，我们将创建两个新的语音路由策略和 PSTN 用法分配给它们。 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    下表显示了在此示例中定义的语音路由策略。 
    
    ||语音路由策略 1|语音路由策略 2|
    |---------|---------|---------|
    |Online 语音策略 ID   |德里联机语音路由策略   |海德拉巴联机语音路由策略    |
    |联机 PSTN 用法  |长途电话  |Long Distance，Local，内部  |

    有关详细信息，请参阅[新建 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。
3. 使用``Grant-CsOnlineVoiceRoutingPolicy``cmdlet 将联机语音路由到用户需要路由限制以强制实施策略。
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>启用基于位置的路由的网络站点
1.  使用``Set-CsTenantNetworkSite``cmdlet 启用基于位置的路由和关联的语音路由策略给您需要强制执行路由限制的网络站点。
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    本示例中，我们启用德里网站和海德拉巴站点基于位置的路由。 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    下表显示了在此示例基于位置的路由启用的网站。

    ||站点 1 （德里）  |站点 2 （海德拉巴）  |
    |---------|---------|---------|
|站点名称    |站点 1 （德里）    |站点 2 （海德拉巴）   
    |EnableLocationBasedRouting    |True    |True    |
    |子网     |子网 1 （德里）     |子网 2 （海德拉巴）     |

## <a name="enable-location-based-routing-for-gateways"></a>启用基于位置的网关的路由
1. 使用``New-CsOnlinePstnGateway``cmdlet 以创建网关配置为每个网关或网络站点。 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    如果多个网关相关联 （例如，网关或 PBX） 系统，修改每个网关，若要启用基于位置的路由限制。 

    本示例中，我们将创建一个网关配置，每个网关。 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。
    
2. 使用``Set-CSOnlinePSTNGateway``cmdlet 来启用基于位置的路由需要强制执行路由限制您网关。 

    启用基于位置的路由到网关将呼叫路由到 PSTN 网关的呼叫路由到 PSTN，并将网关所在的网络站点相关联。

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    本示例中，我们启用基于位置的每个网关关联到德里和海德拉巴站点中的 PSTN 网关的路由。 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    不启用基于位置的不将呼叫路由至 PSTN 网关的路由。 但是，您仍需要将的网关的系统所在的网络站点相关联。 这是因为需要达到通过此网关连接的终结点的 PSTN 呼叫的强制实施基于位置的路由限制。 本示例中，基于位置的路由到 PBX 系统的德里和海德拉巴站点中具有关联的每个网关未启用。

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    连接到系统不将呼叫路由至 PSTN (例如，PBX) 的终结点将作为团队启用的用户的基于位置的路由的终结点具有类似的限制。 这意味着这些用户可以发起和接收呼叫与团队用户无论用户的位置。 此外可以发起和接收呼叫与其他系统不将呼叫路由至 PSTN 网络 （例如，连接到不同 PBX 终结点） 无论系统已关联的网络站点。 所有入站的呼叫、 出站呼叫、 呼叫转接和涉及 PSTN 终结点的呼叫转接将采用基于位置的路由执行进行。 这些呼叫必须使用仅 PSTN 网关定义为本地到这些系统。 

    下表显示的四个网关的网关配置在两个不同的网络站点： 两个连接到 PSTN 网关和两个连接到 PBX 系统。 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway:Gateway 1 DEL 网关    |    True     |   站点 1 （德里）      |
    |PstnGateway:Gateway 2 HYD 网关     |   True      |      站点 2 （海德拉巴）   |
    |PstnGateway:Gateway 3 DEL PBX    |    False     |     站点 1 （德里）    |
    |PstnGateway:Gateway 4 HYD PBX    |    False     |    站点 2 （海德拉巴）     |

## <a name="enable-location-based-routing-for-calling-policies"></a>启用基于位置的路由调用策略

若要强制执行的特定用户的基于位置的路由，用户的语音策略，可防止 PTSN 收费电话设置，绕过。 

使用``Grant-CsTeamsCallingPolicy``cmdlet 来启用基于位置的路由通过防止 PSTN 收费绕过。

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
本示例中，我们将禁止 PSTN 收费绕过为 User1 的调用策略。 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>相关主题
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [基于位置的路由术语](location-based-routing-terminology.md)
