---
title: Teams 和 Skype 互操作性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 了解组织中的 Teams 用户与 Skype (使用者) 用户之间的互操作性功能。
ms.localizationpriority: medium
ms.openlocfilehash: 5cbb4bdf492de67131c75c97685317ef8cae866c
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242316"
---
# <a name="teams-and-skype-interoperability"></a>Teams 和 Skype 互操作性

本文概述了 Microsoft Teams 与 Skype (使用者) 之间的互操作性功能。 了解 Teams 用户和 Skype 用户如何通过聊天和通话以及适用的管理员控制进行通信。

组织中的 Teams 用户可以使用其电子邮件地址与 Skype 用户聊天和呼叫，反之亦然。

- Teams 用户可以搜索并启动一对一纯文本对话或与 Skype 用户的音频/视频通话。
- Skype 用户可以搜索并启动一对一纯文本对话或与 Teams 用户的音频/视频通话。

这些功能在桌面、Web 和移动 (Android 和 iOS) Teams 和 Skype 客户端上可用。 为了获得最佳体验，建议使用 Skype 版本 8.58 及更高版本。

> [!NOTE]
> 本文中讨论的 Teams 和 Skype 互操作功能在 GCC、GCC 高部署或 DOD 部署或私有云环境中不可用。

## <a name="chat-and-calling-experience"></a>聊天和通话体验

下面是聊天和通话体验的概述。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams 用户与 Skype 用户开始聊天或通话

Teams 用户可以通过在新聊天或搜索栏中键入其电子邮件地址来搜索 Skype 用户。  然后，Teams 用户可以在搜索结果中选择 Skype 用户来与他们开始聊天或通话。

Skype 用户可以选择不在搜索结果中显示。 在这种情况下，它们不会显示在 Teams 的搜索结果中，Teams 用户将无法找到它们。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 用户启动与 Teams 用户的聊天或通话

Skype 用户可以使用其电子邮件地址搜索 Teams 用户并开始聊天。 Teams 用户会收到来自 Skype 用户的新消息的通知，并且必须先接受该消息，然后才能回复该消息。

- 如果 Teams 用户选择“ **接受”**，则接受对话，并且两个用户可以相互聊天和呼叫。
- 如果 Teams 用户选择“ **阻止**”，则会阻止对话，并阻止来自该 Skype 用户的后续消息和呼叫。
- 如果 Teams 用户选择“ **查看邮件**”，则消息将显示在 Teams 中，这有助于用户决定是接受还是阻止对话。

> [!NOTE]
> 如果你从Skype for Business升级到 Teams，并且你的用户处于“仅限 Teams”模式，则从 Skype 用户到 Teams 用户的聊天和通话将传送到 Teams。 如果用户处于“孤岛”模式，则从 Skype 用户到 Teams 用户的聊天和通话将传送到Skype for Business。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams 用户阻止或取消阻止 Skype 用户

Teams 用户接受或阻止来自 Skype 用户的初始对话请求后，他们可以随时选择阻止或取消阻止该用户。 他们可以在对话中或在 Teams 中的隐私设置中执行此操作。 Skype 用户不会知道他们已被阻止。

已阻止的 Skype 用户以及其他人和公共电话交换网络 (PSTN) Teams 用户已阻止的电话号码将列在 Teams 中用户的阻止联系人列表中。

## <a name="limitations"></a>限制

- 对话仅包含文本。 这意味着， [本机 Teams 聊天体验](native-chat-for-external-users.md)中没有丰富的格式、@mentions、表情符号或其他任何可用的聊天功能。
- 对话仅是一对一的。 不支持群组聊天。
- Teams 用户和 Skype 用户无法看到彼此的状态。
- 不支持使用 Skype ID 或电话号码搜索 Skype 用户。
- Skype 用户无法呼叫设置了呼叫转接到其他用户号码、代理人号码或公用电话交换网 (PSTN) 号码的 Teams 用户。  仅支持语音邮件。
- 不支持互操作升级、群组呼叫和会议。
- 不支持委托代表 Teams 用户呼叫 Skype 用户的功能。
- 不支持使用聊天进行屏幕共享。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>设置 Teams 用户是否可以与 Skype 用户通信

作为管理员，你可以使用 Microsoft Teams 管理中心或 PowerShell 设置外部访问设置，以控制组织中的 Teams 用户是否可以与 Skype 用户通信。 默认情况下，对于新租户，此功能处于打开状态。 但是，必须让 IT 管理员配置以下 DNS SRV 记录（如果尚未可用于域），例如 _sipfederationtls._tcp.contoso.com。  

**服务**：sipfederationtls<br/>
**协议**：TCP<br/>
**优先级**：100<br/>
**权重**：1<br/>
**端口**：5061<br/>
**目标**：sipfed.online.lync.com

如果从 Skype for Business 升级到 Teams，则会将Skype for Business管理中心配置的外部通信设置迁移到 Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心

在 Microsoft Teams 管理中心，转到 **“用户** > **外部访问权限**”，然后打开 **“用户可以与 Skype 用户通信**”。 有关如何配置此外部访问设置和其他外部访问设置的分步指南，请参阅 [在 Teams 中管理外部访问](./manage-external-access.md)。

### <a name="using-powershell"></a>使用 PowerShell

执行以下操作： 
1. 将 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与 ```EnablePublicCloudAccess``` 参数一起使用，以控制 Teams 用户是否可以与 Skype 用户通信。 将 参数设置为 ```true``` 允许 Teams 用户与 Skype 用户通信。 可以使用 ```EnablePublicCloudAudioVideoAccess``` 参数启用/禁用音频/视频呼叫。

2. 将 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与 参数一起使用 ```Provider``` ， ```"WindowsLive"``` 以便 Teams 用户可以与 Skype 用户通信。

## <a name="related-topics"></a>相关主题

- [在 Teams 中管理外部访问](manage-external-access.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
