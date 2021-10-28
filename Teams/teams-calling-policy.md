---
title: 呼叫策略Microsoft Teams：呼叫和呼叫转发功能
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 了解如何创建、修改用户以及将其添加到 Microsoft Teams 中的自定义调用策略，以及各种调用策略设置。
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
ms.openlocfilehash: 60a6f78d99f6481f2c10db5467f3e7e7bad9f7fb
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2021
ms.locfileid: "60606951"
---
# <a name="calling-and-call-forwarding-in-teams"></a>在 Teams 中调用和呼叫Teams

在Microsoft Teams，调用策略控制哪些呼叫和呼叫转发功能可供用户使用。 呼叫策略确定用户是否可以进行私人呼叫、使用呼叫转发或同时拨打其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、对入站和出站呼叫使用委派，等等。

可以使用自动创建的 (组织范围的) 策略，或者创建和分配自定义策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义调用策略

按照以下步骤创建自定义调用策略。

1. 在管理中心左侧导航Microsoft Teams，转到 **"语音**  >  **呼叫策略"。**
2. 选择“**添加**”。
3. 打开或关闭要用于呼叫策略的功能。
4. 若要控制用户是否可以将入站呼叫路由到语音邮件，请选择"**已启用"或**"**用户控制"。** 若要阻止路由到语音邮件，请选择"已 **禁用"。**
5. 选择“**保存**”。

## <a name="edit-a-calling-policy"></a>编辑呼叫策略

按照以下步骤编辑现有的调用策略。

1. 在管理中心左侧导航Microsoft Teams，选择"**语音**  >  **呼叫策略"。**
2. 单击要修改的策略旁边的 ，然后选择"编辑 **"。**
3. 进行您需要的更改，然后单击"保存 **"。**

## <a name="assign-a-custom-calling-policy-to-users"></a>向用户分配自定义呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>调用策略设置

下面是你可以为调用策略配置的设置。

### <a name="make-private-calls"></a>拨打私人电话

此设置控制所有调用Teams。 关闭此选项可关闭所有呼叫Teams。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>呼叫转发和同时拨打给您的组织中的人员

此设置控制传入呼叫是否可以转发给其他用户，还是可以同时拨打其他人。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转发和同时拨打外部电话号码

此设置控制传入呼叫是否可以转发到外部号码，或者是否可以同时拨打外部号码。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>语音邮件可用于路由入站呼叫

此设置允许将入站呼叫发送到语音邮件。 有效选项包括：

- **已启用** 语音邮件始终可用于入站呼叫。
- **已禁用**  语音邮件不可用于入站呼叫。
- **用户控制** 用户可以确定是否希望语音邮件可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>入站呼叫可以路由到呼叫组

此设置控制是否可以将传入呼叫转发到呼叫组。

### <a name="delegation-for-inbound-and-outbound-calls"></a>入站和出站呼叫的委派

此设置允许将入站呼叫路由到代理人，从而允许代理人代表他们具有委派权限的用户进行出站呼叫。 有关详细信息，请参阅 [与代理人共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止收费绕过并通过 PSTN 发送呼叫

将此设置 **设置为"开** "将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送呼叫和绕过收费。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>在通话中忙碌时可用

"忙碌" (") "选项"选项可用于配置在用户已处于呼叫或会议状态或呼叫处于保持状态时如何处理传入呼叫。 新的或传入的呼叫可能会被拒绝并发出繁忙信号，也可以相应地根据用户的未答设置进行路由。 可以在租户级别或用户级别启用繁忙选项。 无论如何配置其忙碌选项，呼叫或会议中的用户或呼叫保持的用户不会阻止发起新的呼叫或会议。 此设置在默认情况下处于禁用状态。

### <a name="web-pstn-calling"></a>Web PSTN 呼叫

此设置允许用户使用客户端客户端呼叫 PSTN Teams PSTN 号码。

### <a name="incoming-meeting-invites-are-automatically-answered"></a>自动应答传入会议邀请

此设置控制是否自动应答传入会议邀请。 默认情况下处于禁用状态。 请记住，此设置仅适用于传入的会议邀请。 它不适用于其他类型的调用。

### <a name="allow-music-on-hold"></a>允许保留音乐

此设置允许你在 PSTN 呼叫者处于保留状态时打开或关闭保持音乐。 默认情况下，它已打开。 此设置不适用于呼叫公园和老板代理人功能，目前仅通过 PowerShell 提供。

## <a name="related-articles"></a>相关文章

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)
