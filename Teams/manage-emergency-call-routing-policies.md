---
title: 管理直接路由的紧急语音路由策略
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
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理紧急语音路由策略Microsoft Teams设置紧急号码并指定紧急呼叫的路由方式。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e83b33d7e6b9c13b178a7481f5061615836d0c94c4bfcc7c97ec42a3b8250777
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848897"
---
# <a name="manage-emergency-voice-routing-policies-for-direct-routing"></a>管理直接路由的紧急语音路由策略

如果已在你的组织中电话系统直接[](direct-routing-landing-page.md)路由，可以使用 Microsoft Teams 中的紧急语音路由策略来设置紧急号码并指定紧急呼叫的路由方式。 紧急语音路由策略确定是否为分配了该策略的用户启用了增强型紧急服务、用于呼叫紧急服务 (例如，美国) 的 911 号码，以及如何路由对紧急服务的呼叫。

可以管理紧急语音路由策略，方法为：在 Microsoft Teams 管理中心中，或者使用语音  >  Windows PowerShell。 可以将策略分配给用户和网络 [站点](cloud-voice-network-settings.md)。

对于用户，可以使用全局策略 (组织范围内的默认) 策略，或者创建和分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，可以在全局策略中编辑设置，但不能重命名或删除设置。 对于网络站点，请创建并分配自定义策略。

如果向网络站点和用户分配了紧急语音路由策略，并且该用户位于该网络站点，则分配给网络站点的策略将覆盖分配给用户的策略。

## <a name="create-a-custom-emergency-voice-routing-policy"></a>创建自定义紧急语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，转到"**语音** 紧急策略  >  "，然后单击"呼叫 **路由策略"** 选项卡。
2. 单击“**添加**”。
3. 输入策略的名称和说明。
4. 若要启用动态紧急呼叫，请打开 **"动态紧急呼叫"。** 启用动态紧急呼叫后，Teams从服务检索策略和位置信息，并包含该信息作为紧急呼叫的一部分。
5. 定义一个或多个紧急号码。 为此，请在"紧急 **号码"下** 单击" **添加**"，然后执行以下操作：
    1. **紧急拨号字符串**：输入紧急拨号字符串。 此拨号字符串指示呼叫是紧急呼叫。
        > [!NOTE]
        > 对于直接路由，我们将从发送紧急Teams呼叫的客户端过渡，紧急拨号字符串前面有一个"+"。 在转换完成之前，与紧急拨号字符串匹配的语音路由模式应确保匹配具有和没有前面"+"的字符串，例如 911 和 +911。 例如 \\ ^+？911 或 .*。
    2. **紧急拨号掩码**：对于每个紧急号码，可以指定零个或多个紧急拨号掩码。 拨号掩码是您想要转换为紧急拨号字符串的值的号码。 这允许拨打备用紧急号码，同时仍可让呼叫进入紧急服务。 <br>例如，添加 112 作为紧急拨号掩码，即欧洲大多数国家/地区紧急服务号码，911 作为紧急拨号字符串。 正在Teams欧洲的用户可能不知道 911 是美国的紧急号码，当他们拨打 112 时，呼叫将拨打 911。 若要定义多个拨号掩码，请用分号分隔每个值。 例如，112;212。
    3. **PSTN 使用记录**：选择 PSTN 公用电话交换 (PSTN) 使用记录。 PSTN 使用记录用于确定使用哪种路由来路由有权使用紧急呼叫的用户的紧急呼叫。 与此用法关联的路由应指向专用于紧急呼叫的会话启动协议 (SIP) 中继，或指向紧急位置标识号 (ELIN) 网关，该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。

    > [!NOTE]
    > 拨号字符串和拨号掩码在策略中必须是唯一的。 这意味着，对于策略，可以定义多个紧急号码，也可以为拨号字符串设置多个拨号掩码，但每个拨号字符串和拨号掩码只能使用一次。

6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[New-CsTeamsEmergencyCallRoutingPolicy。](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)

## <a name="edit-an-emergency-voice-routing-policy"></a>编辑紧急语音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在管理中心的左侧导航Microsoft Teams，转到"**语音** 紧急策略  >  "，然后单击"呼叫 **路由策略"** 选项卡。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 进行您需要的更改，然后单击"保存 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅[Set-CsTeamsEmergencyCallRoutingPolicy。](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-voice-routing-policy-to-users"></a>向用户分配自定义紧急语音路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-voice-routing-policy-to-a-network-site"></a>向网络站点分配自定义紧急语音路由策略

使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫路由策略分配给网络站点。

此示例演示如何将名为"紧急呼叫路由策略 1"的策略分配到 Site1 站点。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相关主题

[管理紧急呼叫策略Teams](manage-emergency-calling-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向 Teams 中的用户分配策略](assign-policies.md)