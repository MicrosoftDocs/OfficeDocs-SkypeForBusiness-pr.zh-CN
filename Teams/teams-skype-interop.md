---
title: Teams 和 Skype 互操作性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 了解你组织中 Teams 用户与 Skype (Consumer) 互操作性功能。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093952"
---
# <a name="teams-and-skype-interoperability"></a>Teams 和 Skype 互操作性

本文概述了 Microsoft Teams 与 Skype (Consumer) 。 了解 Teams 用户和 Skype 用户如何通过聊天和通话以及应用的管理控件进行通信。

你组织的 Teams 用户可以使用其电子邮件地址与 Skype 用户聊天和呼叫 Skype 用户，反之亦然。

- Teams 用户可以搜索并开始与 Skype 用户进行一对一纯文本对话或音频/视频通话。
- Skype 用户可以搜索并启动一对一纯文本对话或与 Teams 用户的音频/视频通话。

这些功能在 Android 和 iOS 客户端的桌面 (和移动版) Teams 和 Skype 提供。 为获得最佳体验，我们建议使用 Skype 8.58 和更高版本。

> [!NOTE]
> 本文中讨论的 Teams 和 Skype 互操作功能在 GCC、GCC High 或 DOD 部署或私有云环境中不可用。

## <a name="chat-and-calling-experience"></a>聊天和通话体验

下面是聊天和通话体验的概述。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams 用户启动与 Skype 用户的聊天或通话

Teams 用户可以通过在新聊天或搜索栏中键入其电子邮件地址来搜索 Skype 用户。  然后，Teams 用户可以在搜索结果中选择 Skype 用户以开始聊天或呼叫他们。

Skype 用户可能会选择不在搜索结果中显示。 在这种情况下，它们不会显示在 Teams 中的搜索结果中，Teams 用户将无法找到它们。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 用户启动与 Teams 用户的聊天或通话

Skype 用户可以使用 Teams 用户的电子邮件地址搜索并开始与 Teams 用户聊天。 Teams 用户将收到来自 Skype 用户的新消息的通知，并且必须先接受该消息，然后才能回复消息。

- 如果 Teams 用户选择"接受 **"，** 则接受对话，并且两个用户都可以聊天并互相呼叫。
- 如果 Teams **用户选择"** 阻止"，对话将被阻止，来自该 Skype 用户的后续消息和呼叫将被阻止。
- 如果 Teams 用户选择" **查看** 消息"，消息将显示在 Teams 中，这有助于用户决定是接受还是阻止对话。

> [!NOTE]
> 如果你从 Skype for Business 升级到 Teams，并且你的用户已进入"仅 Teams"模式，则 Skype 用户与 Teams 用户的聊天和通话将传递到 Teams。 如果你的用户在群岛模式下，Skype 用户与 Teams 用户的聊天和通话将传递到 Skype for Business。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams 用户阻止或取消阻止 Skype 用户

Teams 用户接受或阻止 Skype 用户的初始对话请求后，他们可以选择随时阻止或取消阻止该用户。 他们可以在对话中或在 Teams 中的隐私设置中执行此操作。 Skype 用户不会知道他们已被阻止。

Teams 中已阻止的 Skype 用户以及其他人和公共电话交换网 (PSTN) 电话号码将列在 Teams 中用户阻止的联系人列表中。

## <a name="limitations"></a>限制

- 对话是纯文本对话。 这意味着没有丰富的格式、@mentions、表情符号或其他任何在本机 Teams 聊天体验 [中可用的聊天功能](native-chat-for-external-users.md)。
- 对话是一对一的。 不支持群组聊天。
- Teams 用户和 Skype 用户无法看到彼此的存在状态。
- 不支持使用 Skype ID 或电话号码搜索 Skype 用户。
- Skype 用户无法呼叫设置了呼叫转发到其他用户号码、代理人号码或 PSTN 公用电话交换网 (PSTN) 的 Teams 用户。  仅支持语音邮件。
- 不支持互操作升级、群组通话和会议。
- 不支持代理人代表 Teams 用户呼叫 Skype 用户。
- 不支持通过聊天进行屏幕共享。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>设置 Teams 用户是否可以与 Skype 用户通信

作为管理员，你使用 Microsoft Teams 管理中心或 PowerShell 设置外部访问设置，以控制你组织中 Teams 用户是否可以与 Skype 用户通信。 默认情况下，此功能已针对新租户启用。 但是，有一个先决条件是，以下 DNS SRV 记录需要由 IT 管理员配置（如果尚未适用于你的域，例如 _sipfederationtls.contoso.com）。  

**服务**：sipfederationtls<br/>
**协议**：TCP<br/>
**优先级**：100<br/>
**权重**：1<br/>
**端口**：5061<br/>
**目标**：sipfed.online.lync.com

如果你从 Skype for Business 升级到 Teams，你在 Skype for Business 管理中心配置的外部通信设置将迁移到 Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心

在 Microsoft Teams 管理中心中，转到 **"组织范围的** 设置""外部访问"，然后打开"用户可以  >  与 **Skype 用户通信"。** 有关如何配置此和其他外部访问设置的分步指南，请参阅在 Teams 中 [管理外部访问](./manage-external-access.md#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

执行以下操作： 
1. 将 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与 参数一起用于控制 ```EnablePublicCloudAccess``` Teams 用户是否可以与 Skype 用户通信。 将 参数设置为 ```true``` 允许 Teams 用户与 Skype 用户通信。 可以使用 参数 ```EnablePublicCloudAudioVideoAccess``` 来启用/禁用音频/视频呼叫。

2. 将 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与参数设置为 一起使用，以便 ```Provider``` ```"WindowsLive"``` Teams 用户可以与 Skype 用户通信。

## <a name="related-topics"></a>相关主题

- [在 Teams 中管理外部访问](manage-external-access.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)