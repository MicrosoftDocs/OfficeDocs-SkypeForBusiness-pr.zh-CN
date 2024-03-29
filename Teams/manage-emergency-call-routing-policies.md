---
title: 管理直接路由的紧急呼叫路由策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何使用和管理Microsoft Teams中的紧急呼叫路由策略来设置紧急号码，并指定如何路由紧急呼叫。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624116"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>管理直接路由的紧急呼叫路由策略

如果已在组织中部署了[直接路由](direct-routing-landing-page.md)，则可以在Microsoft Teams中使用紧急呼叫路由策略来设置紧急号码并指定如何路由紧急呼叫。 紧急呼叫路由策略确定是否为分配了策略的用户启用增强的紧急服务、用于呼叫紧急服务的号码 (例如，美国) 中的 911 以及如何路由对紧急服务的呼叫。 

> [!Note]
> **请注意，这些呼叫路由策略仅适用于直接路由，不适用于呼叫计划或运营商连接。**

可以通过转到Microsoft Teams管理中心中的 **VoiceEmergency**  >  策略或使用Windows PowerShell来管理紧急呼叫路由策略。 可以将策略分配给用户和 [网络站点](cloud-voice-network-settings.md)。

对于用户，可以使用全局 (组织范围的默认) 策略或创建和分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。 对于网络站点，创建并分配自定义策略。

如果向网络站点和用户分配了紧急呼叫路由策略，并且该用户位于该网络站点，则分配给网络站点的策略将替代分配给用户的策略。

## <a name="create-a-custom-emergency-call-routing-policy"></a>创建自定义紧急呼叫路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceEmergency** >  策略，然后单击 **“呼叫路由策略**”选项卡。
2. 单击“**添加**”。
3. 输入策略的名称和说明。
4. 若要启用动态紧急呼叫，请启用 **动态紧急呼叫**。 启用动态紧急呼叫后，Teams从服务中检索策略和位置信息，并将该信息作为紧急呼叫的一部分包含在内。
5. 定义一个或多个紧急号码。 为此，请在 **“紧急号码**”下单击 **“添加**”，然后执行以下操作：
    1. **紧急拨号字符串**：输入紧急拨号字符串。 此拨号字符串指示呼叫是紧急呼叫，路由模式必须与此拨号字符串完全匹配。 
        > [!NOTE]
        > **对于直接路由，Teams客户端不再在紧急拨号字符串前使用“+”发送紧急呼叫。请确保与紧急拨号字符串匹配的语音路由模式反映了此更改。**
    2. **紧急拨号掩码**：对于每个紧急号码，可以指定零个或多个紧急拨号掩码。 拨号掩码是要转换为紧急拨号字符串值的号码。 这允许拨号备用紧急号码，并且仍有呼叫到达紧急服务。 <br>例如，添加 112 作为紧急拨号掩码，这是大多数欧洲的紧急服务号码，911 作为紧急拨号字符串。 来自欧洲的Teams用户可能不知道 911 是美国中的紧急号码，当他们拨打 112 时，会拨打 911。 若要定义多个拨号掩码，请用分号分隔每个值。 例如，112;212。
    3. **PSTN 使用情况记录**：选择公共交换电话网络 (PSTN) 使用情况记录。 PSTN 使用情况记录用于确定用于路由授权使用这些呼叫的用户发出的紧急呼叫的路由。 与此用法关联的路由应指向专用于紧急呼叫的会话启动协议 (SIP) 中继，或指向紧急位置标识号 (ELIN) 网关，该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。

    > [!NOTE]
    > 拨号字符串和拨号掩码在策略中必须是唯一的。 这意味着，对于策略，可以定义多个紧急号码，并且可以为拨号字符串设置多个拨号掩码，但每个拨号字符串和拨号掩码只能使用一次。

6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>编辑紧急呼叫路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceEmergency** >  策略，然后单击 **“呼叫路由策略**”选项卡。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 进行所需的更改，然后单击 **“保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>为用户分配自定义紧急呼叫路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>将自定义紧急呼叫路由策略分配到网络站点

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以分配全局策略或创建的任何自定义策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **LocationsNetwork** >  **拓扑**，然后单击“**网络站点**”选项卡。
2. 单击名称左侧选择网站，然后单击 **“编辑**”。
3. 在 **紧急呼叫路由策略** 下，选择策略，然后单击 **“保存**”。

### <a name="using-powershell"></a>使用 PowerShell

使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫路由策略分配给网络站点。

此示例演示如何将名为“紧急呼叫路由策略 1”的策略分配到 Site1 站点。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相关主题

[管理Teams中的紧急呼叫策略](manage-emergency-calling-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)
