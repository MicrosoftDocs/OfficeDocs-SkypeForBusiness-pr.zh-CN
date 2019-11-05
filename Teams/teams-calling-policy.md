---
title: Microsoft Teams 中的呼叫策略
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft 团队中调用策略设置。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-voice
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 788cc0e93b16585f1d3424d3bfa0a62693528740
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972443"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams 中的呼叫策略
===================================

在 Microsoft 团队中，呼叫策略控制用户可以使用哪些呼叫和呼叫转接功能。 呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转接或同时拨打给其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、将呼叫发送到拨入和出站呼叫等。 默认全局策略是自动创建的，但是管理员还可以创建和分配自定义呼叫策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义呼叫策略

请按照以下步骤创建自定义呼叫策略。

1. 在 "Microsoft 团队管理中心" 中，选择 "**语音** > **呼叫策略**"。
2. 选择 "**新建策略**"。
3. 打开要在呼叫策略中使用的功能。 默认情况下，所有选项均处于**关闭状态**。
4. 若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 "**始终启用**" 或 "**用户控制**"。 若要阻止路由到语音邮件，请选择 "**始终禁用**"。
5. 选择 "**保存**"。

## <a name="modify-an-existing-calling-policy"></a>修改现有呼叫策略

请按照以下步骤修改现有的呼叫策略。

1. 在 "Microsoft 团队管理中心" 中，选择 "**语音** > **呼叫策略**"。
2. 单击要修改的策略旁边的，然后选择 "**编辑**"。
3. 打开要在呼叫策略中使用的功能。 默认情况下，所有选项均处于**关闭状态**。
4. 若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 "**始终启用**" 或 "**用户控制**"。 若要阻止路由到语音邮件，请选择 "**始终禁用**"。
5. 选择 "**保存**"。

## <a name="assign-a-calling-policy-to-a-user"></a>向用户分配呼叫策略

按照以下步骤将自定义呼叫策略分配给用户。

1. 在 "Microsoft 团队管理中心" 中，选择 "**语音** > **呼叫策略**"。
2. 单击策略名称旁边的以将其选中，然后选择 "**管理用户**"。
3. 在 "**管理用户**" 窗格中，搜索用户的名称。 （必须至少输入三个字符。）
4. 选择用户的名称，然后选择 "**添加**"。
5. 选择 "**保存**"。

## <a name="calling-policy-settings"></a>呼叫策略设置

使用以下设置创建自定义呼叫策略。

### <a name="user-can-make-private-calls"></a>用户可以进行私人通话

此设置控制团队中的所有呼叫功能。 关闭此功能以关闭团队中的所有通话功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>呼叫转接和同时拨打给其他用户

此设置控制是否可以将传入呼叫转发给其他用户，或者可以同时拨打其他用户。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转接和同时拨打外部电话号码

此设置控制是否可以将传入呼叫转发到外部号码或同时拨打外部号码。

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>语音邮件可用于将入站呼叫路由到用户

此设置允许将入站呼叫发送到语音邮件。 有效选项包括：

   - **始终启用**语音邮件始终可用于拨入呼叫。 
   - **始终禁用** 语音邮件不可用于入站呼叫。 
   - **用户控制**。 用户可以确定是否希望语音邮件可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>入站呼叫可以路由到呼叫组 

> [!Include [feature preview](includes/preview-feature.md)]

此设置控制是否可以将传入呼叫转移到呼叫组。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>允许委派入站和出站呼叫

> [!Include [feature preview](includes/preview-feature.md)]

此设置使入站呼叫能够路由到代理人，从而允许代理人代表他们为其委派权限的用户发出出站呼叫。 有关详细信息，请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>通过 PSTN 阻止电话绕过和发送呼叫 

将此设置为 **"开**" 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送，而是绕过 tolls。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通话时，忙闲电话可用

忙/闲（忙碌选项））是团队调用策略的新设置，可让你配置当用户已加入通话或会议或有呼叫处于保持状态时如何处理传入呼叫。 可以使用占线信号拒绝新电话或拨入电话。 你可以在租户级别或用户级别启用繁忙选项。 无论其繁忙选项是如何配置的，通话或会议中的用户或通话暂停的用户都不会被阻止发起新的通话或会议。 默认情况下，此设置处于禁用状态。

## <a name="see-also"></a>另请参阅

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)