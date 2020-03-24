---
title: 团队和 Skype 互操作性
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 了解组织中的团队用户与 Skype （消费者）用户之间的互操作性功能。
localization_priority: Normal
ms.openlocfilehash: 6e157cb04687d0577ad5b4cb5fd8da7d2f55e0b4
ms.sourcegitcommit: 87022aa009eae868e1fd945dc299367e16733a3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42545019"
---
# <a name="teams-and-skype-interoperability"></a>团队和 Skype 互操作性

[!INCLUDE [preview-feature](includes/preview-feature.md)]

本文概括介绍了 Microsoft 团队和 Skype （消费者）之间的互操作性功能。 了解团队用户和 Skype 用户可以如何通过聊天和通话以及适用的管理控制进行通信。

你的组织中的团队用户可以使用其电子邮件地址与 Skype 用户聊天和呼叫 Skype 用户，反之亦然。

- 团队用户可以搜索和启动与 Skype 用户之间的一次性文本对话或音频/视频通话。
- Skype 用户可以使用团队用户搜索和启动一对一的纯文本对话或音频/视频呼叫。

这可在桌面版、web 版和移动版（Android 和 iOS）客户端（适用于团队和 Skype）上使用。 为获得最佳体验，我们建议使用 Skype 版本8.58 和更高版本。

## <a name="chat-and-calling-experience"></a>聊天和通话体验

下面是聊天和通话体验的概述。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>团队用户与 Skype 用户开始聊天或通话

团队用户可以通过在新聊天或搜索栏中键入其电子邮件地址来搜索 Skype 用户。  然后，团队用户可以在搜索结果中选择 Skype 用户，以便与他们开始聊天或通话。

Skype 用户可能选择不在搜索结果中显示。 在这种情况下，不会在团队和团队用户无法找到它们的搜索结果中显示它们。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 用户与团队用户开始聊天或通话

Skype 用户可以使用其电子邮件地址搜索和开始与团队用户聊天。 将通知团队用户收到来自 Skype 用户的新邮件，并且必须首先接受邮件，然后他们才能回复。

- 如果团队用户选择 "**接受**"，则接受对话，并且这两个用户都可以互相聊天和通话。
- 如果团队用户选择 "**阻止**"，则对话会被阻止，并且将阻止来自该 Skype 用户的后续消息和呼叫。
- 如果团队用户选择 "**查看邮件**"，则邮件将显示在 "团队" 中，帮助用户决定是接受还是阻止对话。

> [!NOTE]
> 如果您从 Skype for Business 升级到团队，并且您的用户在 "仅限工作组" 模式下，则 Skype 用户与团队用户之间的聊天和通话将发送给团队。 如果你的用户处于 "孤岛" 模式，Skype 用户的聊天和呼叫将发送到 Skype for business。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>团队用户阻止或取消阻止 Skype 用户

在团队用户接受或阻止来自 Skype 用户的初始对话请求后，他们可以随时在对话或团队的隐私设置中随时选择阻止或取消阻止该用户。 Skype 用户不知道他们已被阻止。

已阻止的 Skype 用户以及团队用户已阻止的其他人和公共交换电话网络（PSTN）电话号码在用户的阻止联系人列表中列出。

## <a name="limitations"></a>优缺点

- 对话是纯文本的。 这意味着没有丰富的格式、@mentions、表情符号或其他任何其他聊天功能，这些功能在[本机团队聊天体验](native-chat-for-external-users.md)中可用。
- 对话仅一对一。 不支持群组聊天。
- 团队用户和 Skype 用户看不到彼此的状态。
- 不支持使用 Skype ID 或电话号码搜索 Skype 用户。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>设置团队用户是否可以与 Skype 用户进行通信

作为管理员，你可以使用 Microsoft 团队管理中心或 PowerShell 设置外部访问设置，以控制你的组织中的团队用户是否可以与 Skype 用户通信。 默认情况下，新租户的此功能处于关闭状态。

如果您从 Skype for Business 升级到团队，您在 Skype for business 管理中心配置的外部通信设置将迁移到团队。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心

在 "Microsoft 团队管理中心" 中，转到 "**组织范围的设置** > **外部访问**"，然后打开 "**用户可以与 Skype 用户通信**"。 有关如何配置此和其他外部访问设置的分步指导，请参阅[管理团队中的外部访问](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

将[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与```EnablePublicCloudAccess```参数结合使用，以控制用户是否可以与 Skype 用户进行通信。 设置参数以```true```允许团队用户与 Skype 用户进行通信。

## <a name="related-topics"></a>相关主题

- [管理团队中的外部访问](manage-external-access.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)