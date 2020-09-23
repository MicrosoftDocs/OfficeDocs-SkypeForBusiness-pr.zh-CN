---
title: 管理 Microsoft 团队中的紧急呼叫策略
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
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的紧急呼叫策略，定义当组织中的团队用户拨打紧急电话时会发生什么情况。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217663"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的紧急呼叫策略

如果您的组织使用 [呼叫计划](set-up-calling-plans.md) 或部署的 [电话系统直接路由](direct-routing-landing-page.md)，则可以使用 Microsoft 团队中的紧急呼叫策略定义当组织中的团队用户进行紧急呼叫时发生的情况。 你可以设置被分配了策略的用户呼叫紧急服务时通知的人员以及通知的方式。 例如，你可以将策略设置配置为自动通知组织的安全桌面，并让他们在紧急呼叫中进行侦听。  

通过转到**Voice**  >  Microsoft 团队管理中心或使用 Windows PowerShell 中的语音**紧急策略**来管理紧急呼叫策略。 可将策略分配给用户和 [网络站点](cloud-voice-network-settings.md)。

对于用户，你可以使用全局 (组织范围默认) 策略或创建和分配自定义策略。 除非你创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。 对于网络站点，您可以创建和分配自定义策略。

如果你为某个网络网站和用户分配了紧急呼叫策略，并且该用户在该网络站点上，则分配给网络网站的策略将覆盖分配给该用户的策略。

## <a name="create-a-custom-emergency-calling-policy"></a>创建自定义紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。
2. 单击“添加”****。
3. 输入策略的名称和说明。
4. 设置当进行紧急呼叫时，您希望将组织中的人员（通常是安全桌面）通知的方式。 若要执行此操作，请在 " **通知模式**" 下，选择下列操作之一：
    - **仅发送通知**：团队聊天消息将发送到您指定的用户和组。
    - **Conferenced in 但已静音**：团队聊天消息将发送给你指定的用户和组，并且他们可以 (，但不参与调用方和 PSAP 运算符之间的对话中的) 。
    - **Conferenced 在已取消静音** ** (即将) 推出 **：团队聊天消息将发送给你指定的用户和组，并且可以取消静音以侦听和参与调用方和 PSAP 运算符之间的对话。
5.  如果您选择了 "Conferenced"， **但处于静音** 通知模式，请在 " **拨打紧急电话通知的号码** " 框中，输入用户或组的 PSTN 电话号码以呼叫并加入紧急呼叫。 例如，输入您的组织的安全桌面号码，当进行紧急呼叫时，您将收到呼叫，然后就能接听电话。
6. 搜索并选择一个或多个用户或组（如组织的安全桌面），以便在发生紧急呼叫时发出通知。  通知可以发送到用户、通讯组和安全组的电子邮件地址。 最多可通知50用户。
7. 单击“**应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>编辑紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。
2. 通过单击策略名称左侧，然后单击 " **编辑**"，选择策略。
3. 进行所需的更改，然后单击 " **应用**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [设置-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>为用户分配自定义紧急呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [授权 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>将自定义紧急呼叫策略分配给网络站点

使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫策略分配给网络站点。

以下示例显示了如何将名为 Contoso 紧急呼叫策略1的策略分配给 Site1 网站。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相关主题

[管理团队中的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向团队中的用户分配策略](assign-policies.md)
