---
title: Microsoft Teams 中的呼叫策略
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何创建、修改用户以及将用户添加到 Microsoft 团队中的自定义呼叫策略以及各种通话策略设置。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581070"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams 中的呼叫策略
===================================

在 Microsoft 团队中，呼叫策略控制用户可以使用哪些呼叫和呼叫转接功能。 呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转接或同时拨打给其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、将呼叫发送到拨入和出站呼叫等。

你可以使用全局 (组织范围的默认) 策略，该策略自动创建，或者创建和分配自定义策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义呼叫策略

请按照以下步骤创建自定义呼叫策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫策略**"。
2. 选择 " **添加**"。
3. 打开或关闭要在呼叫策略中使用的功能。
4. 要控制用户是否可以将入站呼叫路由到语音邮件，请选择 " **已启用** " 或 " **用户控制**"。 若要阻止路由到语音邮件，请选择 " **已禁用**"。
5. 选择 " **保存**"。

## <a name="edit-a-calling-policy"></a>编辑呼叫策略

请按照以下步骤编辑现有呼叫策略。

1. 在 Microsoft 团队管理中心的左侧导航中，选择 "**语音**  >  **呼叫策略**"。
2. 单击要修改的策略旁边的，然后选择 " **编辑**"。
3. 进行所需的更改，然后单击 " **保存**"。

## <a name="assign-a-custom-calling-policy-to-users"></a>为用户分配自定义呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>呼叫策略设置

下面是您可以为呼叫策略配置的设置。

### <a name="make-private-calls"></a>拨打私人电话

此设置控制团队中的所有呼叫功能。 关闭此功能以关闭团队中的所有通话功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>呼叫转接和同时拨打您组织中的人员

此设置控制是否可以将传入呼叫转发给其他用户，或者可以同时拨打其他用户。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转接和同时拨打外部电话号码

此设置控制是否可以将传入呼叫转发到外部号码或同时拨打外部号码。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>语音邮件可用于路由入站呼叫

此设置允许将入站呼叫发送到语音邮件。 有效选项包括：

- **已启用** 语音邮件始终可用于拨入呼叫。
- **已禁用**  语音邮件不可用于入站呼叫。
- **用户控制** 用户可以确定是否希望语音邮件可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>入站呼叫可以路由到呼叫组 

> [!Include [feature preview](includes/preview-feature.md)]

此设置控制是否可以将传入呼叫转移到呼叫组。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允许委派入站和出站呼叫

> [!Include [feature preview](includes/preview-feature.md)]

此设置使入站呼叫能够路由到代理人，从而允许代理人代表他们为其委派权限的用户发出出站呼叫。 有关详细信息，请参阅 [与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>通过 PSTN 阻止电话绕过和发送呼叫 

将此设置为 **"开** " 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送，而是绕过 tolls。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通话时，忙闲电话可用

忙碌的忙 (闲选项) 是一种新设置，可让你配置当用户已加入通话或会议或有呼叫处于保持状态时如何处理传入呼叫。 可以使用占线信号拒绝新电话或拨入电话。 你可以在租户级别或用户级别启用繁忙选项。 无论其繁忙选项是如何配置的，通话或会议中的用户或通话暂停的用户都不会被阻止发起新的通话或会议。 默认情况下，此设置处于禁用状态。

### <a name="allow-web-pstn-calling"></a>允许 web PSTN 呼叫

此设置使用户能够使用团队 web 客户端呼叫 PSTN 号码。

### <a name="allow-music-on-hold"></a>允许暂停音乐

此设置允许你在将 PSTN 呼叫者置于保持状态时启用或禁用保留的音乐。 默认情况下，它处于打开状态。 此设置不适用于呼叫寄存和老板代理人功能，并且目前仅可通过 PowerShell 使用。

## <a name="related-topics"></a>相关主题

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[向团队中的用户分配策略](assign-policies.md)
