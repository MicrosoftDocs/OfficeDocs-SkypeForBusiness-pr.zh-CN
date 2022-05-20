---
title: Microsoft Teams中的调用策略：呼叫和呼叫转发功能
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何在Microsoft Teams中创建、修改和添加用户到自定义调用策略，以及各种调用策略设置。
ms.localizationpriority: medium
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
ms.openlocfilehash: 6a52b30e1ced457377d7dd1c820192cb856827ba
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2022
ms.locfileid: "65601591"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Teams中的呼叫和呼叫转接

在Microsoft Teams中，调用策略控制哪些呼叫和呼叫转发功能可供用户使用。 呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转接或同时拨打其他用户或外部电话号码、将呼叫路由到语音邮件、向呼叫组发送呼叫、使用委派进行入站和出站呼叫等。

可以使用自动创建或创建和分配自定义策略的全局 (组织范围的默认) 策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义调用策略

按照以下步骤创建自定义调用策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceCalling** >  策略。
2. 选择“**添加**”。
3. 打开或关闭要在调用策略中使用的功能。
4. 若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 **“已启用** ”或 **“用户控制**”。 若要防止路由到语音邮件，请选择 **“已禁用**”。
5. 选择“**保存**”。

## <a name="edit-a-calling-policy"></a>编辑调用策略

按照以下步骤编辑现有调用策略。

1. 在Microsoft Teams管理中心的左侧导航中，选择 **VoiceCalling** >  策略。
2. 单击要修改的策略旁边，然后选择 **“编辑**”。
3. 进行所需的更改，然后单击 **“保存**”。

## <a name="assign-a-custom-calling-policy-to-users"></a>向用户分配自定义调用策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>调用策略设置

下面是可为调用策略配置的设置。

### <a name="make-private-calls"></a>拨打私人电话

此设置控制Teams中的所有调用功能。 关闭此功能以关闭Teams中的所有调用功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>呼叫转接和同时向组织中的人员拨打电话

此设置控制传入呼叫是可以转发给其他用户还是可以同时给其他人打电话。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转接和同时拨打外部电话号码

此设置控制传入调用是可以转发到外部号码还是可以同时拨打外部号码。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>语音邮件可用于路由入站呼叫

此设置允许将入站呼叫发送到语音邮件。 有效选项包括：

- **启用** 语音邮件始终可用于入站呼叫。
- **禁用**  语音邮件不可用于入站呼叫。
- **用户控制** 用户可以确定他们是否希望语音邮件可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>入站调用可以路由到呼叫组

此设置控制传入调用是否可以转发到调用组。

### <a name="delegation-for-inbound-and-outbound-calls"></a>入站和出站调用的委派

此设置允许将入站调用路由到委托，从而允许委托代表具有委派权限的用户进行出站呼叫。 有关详细信息，请参阅 [与委托共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止通行费绕过并通过 PSTN 发送呼叫

将此设置为 **On** 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送呼叫并绕过收费。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>在通话中忙碌时可用

忙碌 (忙选项) 使你可以配置当用户已在电话或会议中或呼叫处于暂停状态时如何处理传入呼叫。 新的或传入的调用可以使用繁忙的信号被拒绝，也可以相应地路由到用户未答复的设置。 可以在租户级别或用户级别启用忙碌选项。 无论如何配置忙碌选项，呼叫或会议中的用户或被搁置呼叫的用户都不会阻止发起新的电话或会议。 默认情况下禁用此设置。

### <a name="web-pstn-calling"></a>Web PSTN 调用

此设置使用户能够使用Teams Web 客户端调用 PSTN 号码。

### <a name="automatically-answer-incoming-meeting-invites"></a>自动回答传入会议邀请

此设置控制是否自动应答传入会议邀请。 默认情况下处于禁用状态。 请记住，此设置仅适用于传入的会议邀请。 它不适用于其他类型的调用。

### <a name="allow-music-on-hold"></a>允许保留音乐

此设置允许在 PSTN 调用方处于暂停状态时打开或关闭音乐。 默认情况下，它已启用。 此设置不适用于调用寄存和老板委托功能。

### <a name="allow-sip-devices-calling"></a>允许 SIP 设备调用

此设置使用户能够使用 SIP 设备发出和接听呼叫。

### <a name="spam-filtering"></a>垃圾邮件筛选

此设置允许你控制传入呼叫上可用的垃圾邮件筛选类型。

### <a name="call-recording-live-captions-and-transcription"></a>通话录制、实时字幕和听录

这些设置允许你控制呼叫录制、实时字幕和听录是否适用于用户。

## <a name="related-articles"></a>相关文章

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)
