---
title: 在Microsoft Teams中管理紧急呼叫策略
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
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在Microsoft Teams中使用和管理紧急呼叫策略，以定义组织中Teams用户进行紧急呼叫时会发生什么情况。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 66ff287911a22de8b65ed356cd07833a2bbbb0ca
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624096"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>在Microsoft Teams中管理紧急呼叫策略

如果你的组织使用 Microsoft 呼叫计划、运营商连接或直接路由作为 [PSTN 连接选项](pstn-connectivity.md)，则可以在Microsoft Teams中使用紧急呼叫策略来定义组织中Teams用户进行紧急呼叫时会发生什么情况。

当分配了策略的用户调用紧急服务时，可以设置通知谁以及通知他们的方式。 例如，可以配置策略设置以自动通知组织的安全部门，并让他们在紧急呼叫中侦听。  

可以通过转到Microsoft Teams管理中心中的 **VoiceEmergency**  >  策略或使用Windows PowerShell来管理紧急呼叫策略。 可以将策略分配给用户和 [网络站点](cloud-voice-network-settings.md)。

对于用户，可以使用全局 (组织范围的默认) 策略或创建和分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。 对于网络站点，创建并分配自定义策略。

如果向网络站点和用户分配了紧急呼叫策略，并且该用户位于该网络站点，则分配给网络站点的策略将替代分配给用户的策略。

## <a name="create-a-custom-emergency-calling-policy"></a>创建自定义紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceEmergency** >  策略，然后单击 **“呼叫策略**”选项卡。
2. 单击“**添加**”。
3. 输入策略的名称和说明。
4. 将 **外部位置查找模式** 设置为允许最终用户在从公司网络外部的网络位置工作时配置其紧急地址。
5. 设置在发出紧急呼叫时要通知组织中人员的方式（通常是安全部门）。 为此，请在 **“通知”模式** 下，选择下列操作之一：
    - **仅发送通知**：Teams聊天消息将发送到指定的用户和组。
    - **静音会议，无法取消静音**：Teams聊天消息发送给你指定的用户和组，他们可以侦听 (但不能参与调用方与 PSAP 运算符之间的对话) 。
    - **会议静音，但能够取消静音**：Teams聊天消息将发送给你指定的用户和组，他们可以取消静音以侦听和参与调用方与 PSAP 运算符之间的对话。
5.  设置 **紧急服务免责声明** 以显示横幅，提醒最终用户确认其紧急位置。
6.  如果 **在静音** 通知模式下选择了任一会议，则在“拨打 **紧急呼叫通知** 号码”框中，可以输入用户或组的 PSTN 电话号码来呼叫和加入紧急呼叫。 例如，输入组织的安全服务台的号码，当发出紧急呼叫时，他们将接听呼叫，然后可以侦听呼叫。 即使模式设置为 **静音会议，但能够取消静音**，也无法取消调用 PSTN 手机。
7. 搜索并选择一个或多个用户或组，例如组织的安全部门，以在发出紧急呼叫时通知。  通知可以发送到用户、通讯组和安全组的电子邮件地址。 最多可以通知 50 个用户。
8. 单击“**应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>编辑紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceEmergency** >  策略，然后单击 **“呼叫策略**”选项卡。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 进行所需的更改，然后单击“ **应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>为用户分配自定义紧急呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>将自定义紧急呼叫策略分配到网络站点

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以分配全局策略或创建的任何自定义策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **LocationsNetwork** >  **拓扑**，然后单击“**网络站点**”选项卡。
2. 单击名称左侧选择网站，然后单击 **“编辑**”。
3. 在 **“紧急呼叫策略**”下，选择策略，然后单击 **“保存**”。

### <a name="using-powershell"></a>使用 PowerShell
使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急调用策略分配给网络站点。

以下示例演示如何将名为 Contoso 紧急呼叫策略 1 的策略分配到 Site1 站点。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相关主题

[在Teams中管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)
