---
title: 在 Microsoft Teams 中管理紧急呼叫策略
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
description: 了解如何在 Microsoft Teams 中使用和管理紧急呼叫策略，以定义当组织中的 Teams 用户发出紧急呼叫时会发生什么情况。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1d2dc0e2213f6294e2c596722a4f5ab49bec8487
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727744"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理紧急呼叫策略

如果你的组织使用 Microsoft 通话套餐、运营商连接、Teams 电话移动或直接路由作为 [PSTN 连接选项](pstn-connectivity.md)，则可以使用 Microsoft Teams 中的紧急呼叫策略来定义当组织中的 Teams 用户发出紧急呼叫时会发生什么情况。

可以设置在分配策略的用户调用紧急服务时通知谁以及如何通知他们。 例如，可以将策略设置配置为自动通知组织的安全部门，并让他们在紧急呼叫中侦听。  

可以通过转到 Microsoft Teams 管理中心中的 **“语音** > **紧急策略**”或使用Windows PowerShell来管理紧急呼叫策略。 可以将策略分配给用户和 [网络站点](cloud-voice-network-settings.md)。

对于用户，可以使用全局 (组织范围的默认) 策略或创建和分配自定义策略。 除非创建并分配自定义策略，否则用户将自动获取全局策略。 请记住，可以在全局策略中编辑设置，但不能重命名或删除它。 对于网络站点，可以创建并分配自定义策略。

如果向网络站点和用户分配了紧急呼叫策略，并且该用户位于该网络站点，则分配给该网络站点的策略将覆盖分配给该用户的策略。

## <a name="create-a-custom-emergency-calling-policy"></a>创建自定义紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **紧急策略**”，然后单击“ **呼叫策略** ”选项卡。

2. 单击“**添加**”。

3. 输入策略的名称和说明。

4. 将 **“外部位置查找模式** ”设置为“打开”，以允许最终用户在公司网络外部的网络位置工作时配置其紧急地址。

5. 设置在发出紧急呼叫时要通知组织中的人员（通常是安全台）的方式。 为此，请在 **“通知模式**”下选择以下选项之一：

    - **仅发送通知**：Teams 聊天消息将发送给指定的用户和组。
    - **会议，但已静音**：Teams 聊天消息将发送给你指定的用户和组，他们可以收听 (但不参与呼叫方和 PSAP 操作员之间的对话) 。
    - **会议并取消静音**：Teams 聊天消息将发送给你指定的用户和组，他们可以取消静音以收听和参与呼叫方与 PSAP 操作员之间的对话。

6.  设置 **紧急服务免责声明** 以显示横幅，提醒最终用户确认其紧急位置。

7.  如果选择了静音通知模式中的任一 **会议** ，请在“ **拨打紧急呼叫通知** 号码”框中输入用户或组的 PSTN 电话号码，以便呼叫并加入紧急呼叫。 例如，输入组织的安全服务台号码，该安全台将在发出紧急呼叫时接听呼叫，然后可以侦听呼叫。 即使模式设置为会议静音 **但能够取消静音**，PSTN 电话也无法取消静音。

8. 设置在发出紧急呼叫时要通知的人员，例如，安全服务台人员。 可以定义用户、通讯组或安全组的列表。 最多可以通知 50 个用户。

9. 单击“**应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>编辑紧急呼叫策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以编辑全局策略或创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **紧急策略**”，然后单击“ **呼叫策略** ”选项卡。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 进行所需的更改，然后单击“ **应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>向用户分配自定义紧急呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另请参阅 [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>将自定义紧急呼叫策略分配给网络站点

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

可以分配全局策略或创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“位置** > **网络拓扑**”，然后单击“ **网络站点** ”选项卡。
2. 单击名称左侧选择站点，然后单击“ **编辑**”。
3. 在 **“紧急呼叫策略**”下，选择该策略，然后单击“ **保存**”。

### <a name="using-powershell"></a>使用 PowerShell
使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫策略分配给网络站点。

以下示例演示如何将名为 Contoso 紧急呼叫策略 1 的策略分配给 Site1 站点。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相关主题

[在 Teams 中管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)
