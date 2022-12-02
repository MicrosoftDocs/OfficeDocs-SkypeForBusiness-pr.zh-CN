---
title: Microsoft Teams 中的呼叫策略：呼叫和呼叫转接功能
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何创建、修改用户并将其添加到 Microsoft Teams 中的自定义呼叫策略，以及各种呼叫策略设置。
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
ms.openlocfilehash: a02df903574c7e7db796294ad90c9e05ab732eb0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245668"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>呼叫策略：Teams 中的呼叫和呼叫转接功能

在 Microsoft Teams 中，呼叫策略控制哪些呼叫和呼叫转接功能可供用户使用。 呼叫策略确定用户是否可以进行专用呼叫、使用呼叫转接或同时拨打其他用户或外部电话号码、将呼叫路由到语音邮件、向呼叫组发送呼叫、对入站和出站呼叫使用委派等。

可以使用自动创建的全局 (组织范围的默认) 策略，也可以创建和分配自定义策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义呼叫策略

按照以下步骤创建自定义调用策略。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **呼叫策略**”。
2. 选择“**添加**”。
3. 打开或关闭要在呼叫策略中使用的功能。
    - 例如，若要控制用户是否可以将入站呼叫路由到语音邮件，请选择 **“已启用”** 或“ **用户控制**”。 若要阻止路由到语音邮件，请选择“ **未启用**”。
4. 选择“**保存**”。

## <a name="edit-a-calling-policy"></a>编辑呼叫策略

按照以下步骤编辑现有呼叫策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，选择“**语音** > **呼叫策略**”。
2. 单击要修改的策略旁边的，然后选择 **“编辑**”。
3. 进行所需的更改，然后单击“ **保存**”。

## <a name="assign-a-custom-calling-policy-to-users"></a>向用户分配自定义呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>呼叫策略设置

下面是可为调用策略配置的设置。

### <a name="make-private-calls"></a>拨打私人电话

此设置控制 Teams 中的所有通话功能。 关闭此功能可关闭 Teams 中的所有通话功能。

### <a name="cloud-recording-for-calling"></a>用于通话的云录制

此设置控制用户是否可以录制呼叫。 默认情况下，这是关闭的。

### <a name="transcription"></a>转录

此设置控制呼叫听录是否可供用户使用。 默认情况下，这是关闭的。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>呼叫转接和同时响铃给组织中的人员

此设置控制传入呼叫是否可以转接到其他用户，或者是否可以同时拨打组织中的另一个人电话。 默认情况下，此选项处于打开状态。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转接和同时拨打外部电话号码

此设置控制传入呼叫是可以转接到外部号码，还是可以同时拨打外部号码。 默认情况下，此选项处于打开状态。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>语音邮件可用于路由入站呼叫

此设置允许将入站呼叫发送到语音邮件。 默认设置为 **“用户控制**”。 有效选项包括：

- **启用** 语音邮件始终可用于入站呼叫。
- **未启用**  语音邮件不适用于入站呼叫。
- **用户控制** 用户可以确定是否希望语音邮件可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>可将入站呼叫路由到呼叫组

此设置控制传入呼叫是否可以转接到呼叫组。 默认情况下，此选项处于打开状态。

### <a name="delegation-for-inbound-and-outbound-calls"></a>入站和出站呼叫的委派

此设置允许将入站呼叫路由到代理人，从而允许委托代表其具有委派权限的用户进行出站呼叫。 默认情况下，此设置处于打开状态。 有关详细信息，请参阅 [与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止绕过收费并通过 PSTN 发送呼叫

将此设置为 **“开”** 将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送电话并绕过通行费。 默认情况下，此设置处于关闭状态。

### <a name="music-on-hold-for-pstn-calls"></a>PSTN 呼叫的保留音乐

此设置允许在 PSTN 呼叫者处于保留状态时打开或关闭音乐保持。 默认情况下，它处于打开状态。 此设置不适用于呼叫寄存和老板委托功能。 详细了解如何 [配置自定义音乐](music-on-hold.md)。

### <a name="busy-on-busy-when-in-a-call"></a>在通话中忙于忙碌

在呼叫 (也称为“忙碌选项”) ，你可以配置在用户已参与通话或会议或将呼叫置于保留状态时如何处理传入呼叫。 新的或传入的呼叫可能会因信号繁忙而被拒绝，也可以相应地路由到用户的未接听设置。 无论其忙碌选项的配置方式如何，呼叫或会议中的用户或呼叫处于保留状态的用户都不会阻止发起新的呼叫或会议。 默认情况下，此设置设置为 **“未启用** ”。

- **未启用** 未启用忙碌选项，并且当用户已在呼叫中时，仍可以向用户发送新的呼叫或传入呼叫。
- **启用** 新的或传入的呼叫将被拒绝，并显示繁忙的信号。
- **悬而未决** 将使用用户的未解决设置，例如路由到语音邮件或转发给其他用户。

### <a name="web-pstn-calling"></a>Web PSTN 呼叫

此设置使用户能够使用 Teams Web 客户端呼叫 PSTN 号码。 默认情况下，此选项处于打开状态。

### <a name="real-time-captions-in-teams-calls"></a>Teams 通话中的实时字幕

此设置控制 Teams 通话中的实时字幕是否可供用户使用。 默认情况下，此选项处于打开状态。

### <a name="automatically-answer-incoming-meeting-invites"></a>自动回答传入的会议邀请

此设置控制是否自动答复传入的会议邀请。 默认情况下处于禁用状态。 请记住，此设置仅适用于传入的会议邀请。 它不适用于其他类型的调用。

### <a name="spam-filtering"></a>垃圾邮件筛选

此设置允许你控制传入呼叫可用的垃圾邮件筛选类型。 可以执行基本和 Captcha 交互式语音 (IVR) 检查。 默认情况下，此选项处于打开状态。

### <a name="sip-devices-can-be-used-for-calls"></a>SIP 设备可用于呼叫

此设置使用户能够使用 SIP 设备拨打和接听呼叫。 默认情况下，此功能处于关闭状态。

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>在浏览器中为传入 PSTN 呼叫打开应用

此设置控制是否在浏览器中自动打开应用，以便向用户发出传入 PSTN 呼叫。 这可用于将入站呼叫者的电话号码传递给应用，以在呼叫进行时查找关联的客户记录。 默认情况下，此设置处于关闭状态。

如果启用，则需要在 URL 中提供应用链接， **以便在浏览器中为传入 PSTN 呼叫框打开应用** 。 可以使用 {phone} 占位符将 E.164 格式的电话号码 () 传递到提供的 URL。 或者，你可以提供不带任何占位符的通用 URL。 这只会启动列出的 URL。

![在浏览器中为传入 PSTN 呼叫打开应用策略设置的屏幕截图。](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>相关文章

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

[PSTN 连接选项](pstn-connectivity.md)

[为用户配置呼叫设置](user-call-settings.md)
