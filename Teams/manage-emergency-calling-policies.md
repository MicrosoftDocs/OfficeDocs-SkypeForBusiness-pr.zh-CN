---
title: 管理紧急呼叫策略Microsoft Teams
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
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何使用和管理紧急呼叫Microsoft Teams，以定义当Teams用户进行紧急呼叫时会发生什么情况。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: c05318f34f7c52570a061aa66644cde4b8ac020c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632086"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>管理紧急呼叫策略Microsoft Teams

如果你的组织使用呼叫[](set-up-calling-plans.md)计划或电话系统[直接](direct-routing-landing-page.md)路由，可以使用 Microsoft Teams 中的紧急呼叫策略来定义当Teams用户进行紧急呼叫时会发生什么情况。 可以设置在分配有策略的用户呼叫紧急服务时要通知哪些人以及如何通知他们。 例如，可以将策略设置配置为自动通知组织的安全服务台，让他们侦听紧急呼叫。  

你可以通过以下方法管理紧急呼叫策略：在 Microsoft Teams 管理中心中通过语音  >  Windows PowerShell。 可以将策略分配给用户和网络 [站点](cloud-voice-network-settings.md)。

对于用户，可以使用全局策略 (组织范围内的默认) 策略，或者创建和分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，可以在全局策略中编辑设置，但不能重命名或删除设置。 对于网络站点，请创建并分配自定义策略。

如果向网络站点和用户分配了紧急呼叫策略，并且该用户位于该网络站点，则分配给网络站点的策略将覆盖分配给用户的策略。

## <a name="create-a-custom-emergency-calling-policy"></a>创建自定义紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心左侧导航Microsoft Teams，转到"**语音** 紧急策略  >  "，然后单击"呼叫 **策略"** 选项卡。
2. 单击“**添加**”。
3. 输入策略的名称和说明。
4. 设置在拨打紧急呼叫时希望如何通知组织内部人员（通常是安全服务台）。 为此，请在"通知 **模式"下** 选择下列选项之一：
    - **仅发送通知**：Teams用户和组发送一条聊天消息。
    - 已 **静音** 且无法取消静音的会议：Teams 聊天消息将发送到您指定的用户和组，他们可以侦听 (但不能参与呼叫方与 PSAP 操作员之间的) 对话。
    - 已 **静音** 但能够取消静音的会议：Teams 聊天消息将发送给你指定的用户和组，他们可以取消静音以收听和参与呼叫方与 PSAP 操作员之间的对话。
5.  如果在静音通知模式下选择了任一会议，可在"拨打紧急呼叫通知号码"框中输入要呼叫和加入紧急呼叫的用户或组的 PSTN 电话号码。 例如，输入组织安全服务台的号码，当进行紧急呼叫时，谁将收到呼叫，然后可以侦听呼叫。 PSTN 电话无法取消静音，即使模式设置为静音会议，但 **能够取消静音**。
6. 搜索并选择一个或多个用户或组（例如组织的安全服务台）以在拨打紧急呼叫时通知。  通知可以发送到用户、通讯组和安全组的电子邮件地址。 最多可以通知 50 个用户。
7. 单击“**应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[New-CsTeamsEmergencyCallingPolicy。](/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>编辑紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在管理中心左侧导航Microsoft Teams，转到"**语音** 紧急策略  >  "，然后单击"呼叫 **策略"** 选项卡。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 进行你需要的更改，然后单击"应用 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>向用户分配自定义紧急呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>向网络站点分配自定义紧急呼叫策略

使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫策略分配给网络站点。

以下示例演示如何将名为 Contoso 紧急呼叫策略 1 的策略分配到 Site1 站点。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相关主题

[管理呼叫中心中的紧急呼叫Teams](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向 Teams 中的用户分配策略](assign-policies.md)