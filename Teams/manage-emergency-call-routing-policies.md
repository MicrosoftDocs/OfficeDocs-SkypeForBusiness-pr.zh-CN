---
title: 管理紧急呼叫路由策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的紧急呼叫路由策略来设置紧急电话号码，并指定如何路由紧急电话。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217693"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的紧急呼叫路由策略

如果您已在您的组织中部署了 [手机系统直接路由](direct-routing-landing-page.md) ，则可以使用 Microsoft 团队中的紧急呼叫路由策略来设置紧急电话号码，并指定如何路由紧急电话。 紧急呼叫路由策略确定是否为分配了该策略的用户启用增强的紧急服务，用于呼叫紧急服务的号码 (例如，911在美国) ，以及如何路由紧急服务通话。

通过转到**Voice**  >  Microsoft 团队管理中心或使用 Windows PowerShell 中的语音**紧急策略**，管理紧急呼叫路由策略。 可将策略分配给用户和 [网络站点](cloud-voice-network-settings.md)。

对于用户，你可以使用全局 (组织范围默认) 策略或创建和分配自定义策略。 除非你创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。 对于网络站点，您可以创建和分配自定义策略。

如果为某个网络网站和用户分配了紧急呼叫路由策略，并且该用户在该网络站点上，则分配给网络网站的策略将覆盖分配给该用户的策略。

## <a name="create-a-custom-emergency-call-routing-policy"></a>创建自定义紧急呼叫路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫路由策略**" 选项卡。
2. 单击“添加”****。
3. 输入策略的名称和说明。
4. 若要启用动态紧急呼叫，请打开 **动态紧急呼叫**。 启用动态紧急呼叫时，团队将从服务中检索策略和位置信息，并将该信息作为紧急呼叫的一部分包括在其中。
5. 定义一个或多个紧急电话号码。 若要执行此操作，请在 " **紧急电话号码**" 下，单击 " **添加**"，然后执行以下操作：
    1. **紧急拨号字符串**：输入 "紧急拨号" 字符串。 此拨号字符串表示呼叫是紧急呼叫。
        > [!NOTE]
        > 对于直接路由，我们将通过 "+" 在 "紧急拨号" 字符串前面的 "+" 发送紧急呼叫的团队客户进行转移。 在转换完成之前，与紧急拨号字符串匹配的语音路线模式应确保对具有前面没有 "+" （如911和 + 911）的字符串进行匹配。 例如，^ \\ +？911或. *。
    2. **紧急拨号掩码**：对于每个紧急电话号码，您可以指定零个或多个紧急拨号掩码。 拨号掩码是要转换为 "紧急拨号字符串" 值的数字。 这允许拨打备用紧急号码，并且仍然可以拨打紧急服务。 <br>例如，您将112添加为 "紧急拨号掩码"，这是欧洲大多数欧洲的紧急服务号码，911作为 "紧急拨号" 字符串。 欧洲来访的团队用户可能不知道911是美国的紧急电话，当他们拨打112时，将拨打911。 若要定义多个拨号掩码，请用分号分隔每个值。 例如，112; 212。
    3. **Pstn 使用记录**：选择公共交换电话网络 (PSTN) 使用情况记录。 PSTN 使用记录用于确定使用哪个路由来路由紧急呼叫，这些用户有权使用它们。 与此使用关联的路由应指向会话初始协议 (SIP) 专用于紧急呼叫或紧急位置标识 (ELIN) 网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。

    > [!NOTE]
    > 拨号式字符串和拨号掩码在策略中必须是唯一的。 这意味着对于策略，你可以定义多个紧急号码，并且可以为拨号字符串设置多个拨号掩码，但每个拨号字符串和拨号掩码只能使用一次。

6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [新-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>编辑紧急呼叫路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫路由策略**" 选项卡。
2. 通过单击策略名称左侧，然后单击 " **编辑**"，选择策略。
3. 进行所需的更改，然后单击 " **保存**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [设置-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>为用户分配自定义紧急呼叫路由策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [授权 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>为网络站点分配自定义紧急呼叫路由策略

使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫路由策略分配给网络站点。

此示例显示了如何将名为 "紧急呼叫路由策略 1" 的策略分配给 Site1 网站。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相关主题

[管理团队中的紧急呼叫策略](manage-emergency-calling-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向团队中的用户分配策略](assign-policies.md)
