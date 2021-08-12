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
description: 了解如何创建、修改用户以及将用户添加到 Microsoft Teams 中的自定义呼叫策略，以及各种呼叫策略设置。
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
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309241"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>呼叫和呼叫Teams

在 Microsoft Teams 中，呼叫策略控制哪些呼叫和呼叫转移功能可供用户使用。 呼叫策略确定用户是否可以拨打私人电话、将呼叫转发或同时响铃用于其他用户或外部电话号码、将呼叫路由到语音邮件、将呼叫发送到呼叫组、对入站和出站呼叫使用委派等。

可以使用自动创建的全局 (组织范围的默认) 策略，也可以创建和分配自定义策略。

## <a name="create-a-custom-calling-policy"></a>创建自定义呼叫策略

按照以下步骤创建自定义呼叫策略。

1. 在管理中心左侧导航Microsoft Teams，转到"**语音**  >  **呼叫策略"。**
2. 选择“**添加**”。
3. 打开或关闭要在呼叫策略中使用的功能。
4. 若要控制用户是否可以将来电路由到语音邮件，请选择“**已启用**”或“**用户控制**”。 若要阻止路由到语音邮件，请选择“**已禁用**”。
5. 选择“**保存**”。

## <a name="edit-a-calling-policy"></a>编辑呼叫策略

按照以下步骤编辑现有呼叫策略。

1. 在管理中心的左侧导航Microsoft Teams，选择"**语音**  >  **呼叫策略"。**
2. 单击要修改的策略旁边的""，然后选择"编辑 **"。**
3. 进行您需要的更改，然后单击"保存 **"。**

## <a name="assign-a-custom-calling-policy-to-users"></a>向用户分配自定义呼叫策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>呼叫策略设置

下面是你可以为呼叫策略配置的设置。

### <a name="make-private-calls"></a>拨打私人电话

此设置控制呼叫服务中Teams。 关闭此选项将关闭 Teams 中的所有呼叫功能。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>对组织中的人员呼叫转移和同时响铃

此设置控制传入呼叫是可转发给其他用户，还是可以同时拨打其他人电话。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>呼叫转接并同时拨打外部电话号码

此设置控制传入呼叫是可转发到外部号码，还是可以同时拨打外部号码。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>语音邮件可用于路由来电

此设置允许将入站呼叫发送到语音邮件。 有效选项包括：

- **已启用** 语音邮件始终可用于入站呼叫。
- **已禁用**  语音邮件不可用于入站呼叫。
- **用户控制** 用户可以确定是否希望语音邮件可用。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>来电可路由到呼叫组

此设置控制是否可以将传入呼叫转发到呼叫组。

### <a name="delegation-for-inbound-and-outbound-calls"></a>入站和出站呼叫的委派

此设置允许将入站呼叫路由到代理，从而允许代理代表其拥有委派权限的用户进行出站呼叫。 有关详细信息，请参阅与代理人 [共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>防止绕过收费并通过 PSTN 发送呼叫 

将此设置 **设置为"开** "将通过 PSTN 发送呼叫并产生费用，而不是通过网络发送呼叫并绕过收费。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>呼叫时忙/闲状态可用

Busy on Busy (Busy Options) lets you configure how incoming calls are handled when a user is already in a call or conference or has a call on hold. 新呼叫或传入呼叫可以使用繁忙信号拒绝，也可以相应地路由到用户的未接听设置。 您可以在租户级别或用户级别启用忙碌选项。 无论如何配置忙碌选项，不会阻止呼叫或会议中的用户或呼叫保持状态的用户发起新的呼叫或会议。 默认情况下，禁用此设置。

### <a name="web-pstn-calling"></a>Web PSTN 呼叫

通过此设置，用户可以使用 web 客户端Teams PSTN 号码。

### <a name="incoming-meeting-invites-are-automatically-answered"></a>自动应答传入会议邀请

此设置控制是否自动应答传入会议邀请。 默认情况下，它已关闭。 请记住，此设置仅适用于传入会议邀请。 它不适用于其他类型的呼叫。

### <a name="allow-music-on-hold"></a>允许播放保留音乐

此设置允许你在将 PSTN 呼叫者置于呼叫等待时打开或关闭保持音乐。 默认情况下，此选项处于启用状态。 此设置不适用于呼叫管理和代理代理功能，当前仅通过 PowerShell 提供。

## <a name="related-articles"></a>相关文章

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[向 Teams 中的用户分配策略](assign-policies.md)
