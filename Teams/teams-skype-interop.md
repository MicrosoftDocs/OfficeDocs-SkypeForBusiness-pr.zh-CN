---
title: Teams和Skype互操作性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 了解组织中Teams用户与Skype (使用者) 用户之间的互操作性功能。
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167266"
---
# <a name="teams-and-skype-interoperability"></a>Teams和Skype互操作性

本文概述了Microsoft Teams与Skype (使用者) 之间的互操作性功能。 了解Teams用户和Skype用户如何通过聊天和呼叫以及应用的管理员控件进行通信。

Teams组织中的用户可以使用其电子邮件地址与Skype用户聊天和呼叫，反之亦然。

- Teams用户可以与Skype用户一起搜索和启动一对一的仅限文本的对话或音频/视频通话。
- Skype用户可以与Teams用户一起搜索和启动一对一的仅限文本的对话或音频/视频通话。

这些功能在桌面、Web 和移动 (Android上提供，iOS) 客户端适用于Teams和Skype。 为了获得最佳体验，建议Skype版本 8.58 及更高版本。

> [!NOTE]
> 本文中讨论的 Teams 和 Skype 互操作功能在 GCC、GCC 高部署或 DOD 部署或私有云环境中不可用。

## <a name="chat-and-calling-experience"></a>聊天和通话体验

下面是聊天和通话体验的概述。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams用户开始与Skype用户聊天或通话

Teams用户可以通过在新聊天或搜索栏中键入其电子邮件地址来搜索Skype用户。  然后，Teams用户可以在搜索结果中选择Skype用户以开始聊天或与他们通话。

Skype用户可以选择不出现在搜索结果中。 在这种情况下，它们不会显示在搜索结果中Teams并且Teams用户将无法找到它们。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype用户与Teams用户开始聊天或通话

Skype用户可以使用其电子邮件地址搜索并开始与Teams用户聊天。 Teams用户收到来自Skype用户的新消息的通知，必须先接受该消息，然后才能答复它。

- 如果Teams用户选择 **“接受**”，则会话被接受，并且两个用户都可以互相聊天和呼叫。
- 如果Teams用户选择 **“阻止**”，则会阻止对话，并阻止来自该Skype用户的后续消息和调用。
- 如果Teams用户选择 **“查看”消息**，则消息将显示在Teams中，这有助于用户决定是否接受或阻止对话。

> [!NOTE]
> 如果从Skype for Business升级到Teams并且用户处于“仅限Teams模式”，则Skype用户到Teams用户的聊天和呼叫将传递给Teams。 如果用户处于 Islands 模式，则会将Skype用户与Teams用户的聊天和呼叫传递给Skype for Business。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams用户阻止或取消阻止Skype用户

Teams用户接受或阻止来自Skype用户的初始对话请求后，他们可以选择随时阻止或取消阻止该用户。 他们可以在对话中或在Teams中的隐私设置中执行此操作。 Skype用户不会知道他们已被阻止。

阻止Skype用户以及其他人和公共交换电话网络 (PSTN) Teams用户阻止的电话号码，列在用户在Teams中被阻止的联系人列表中。

## <a name="limitations"></a>限制

- 对话是仅限文本的。 这意味着没有丰富的格式设置、@mentions、表情符号或其他任何在[本机聊天体验中可用的聊天功能Teams](native-chat-for-external-users.md)。
- 对话仅一对一。 不支持组聊天。
- Teams用户和Skype用户看不到彼此的存在。
- 不支持使用Skype ID 或电话号码搜索Skype用户。
- Skype用户无法调用Teams设置呼叫转接到其他用户号码、委托号码或公共交换电话网络 (PSTN) 号码的用户。  仅支持语音邮件。
- 不支持互操作升级、组呼叫和会议。
- 不支持委托代表Teams用户调用Skype用户。
- 不支持通过聊天进行屏幕共享。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>设置Teams用户是否可以与Skype用户通信

作为管理员，可以使用Microsoft Teams管理中心或 PowerShell 设置外部访问设置，以控制组织中Teams用户是否可以与Skype用户通信。 默认情况下，为新租户启用此功能。 但是，有一个先决条件，需要由 IT 管理员配置以下 DNS SRV 记录（例如，_sipfederationtls._tcp.contoso.com）。  

**服务**：sipfederationtls<br/>
**协议**：TCP<br/>
**优先级**：100<br/>
**重量**：1<br/>
**端口**：5061<br/>
**目标**：sipfed.online.lync.com

如果从Skype for Business升级到Teams，则在Skype for Business管理中心配置的外部通信设置将迁移到Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心

在Microsoft Teams管理中心，转到 **“用户** > **外部访问**”，然后启用 **用户可以与Skype用户通信**。 有关如何配置此设置和其他外部访问设置的分步指南，请参阅[管理Teams中的外部访问](./manage-external-access.md#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

执行以下操作： 
1. 将 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与参数一起```EnablePublicCloudAccess```使用，以控制Teams用户是否可以与Skype用户通信。 将参数设置为```true```允许Teams用户与Skype用户通信。 可以使用 ```EnablePublicCloudAudioVideoAccess``` 该参数启用/禁用音频/视频呼叫。

2. 将 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与```Provider```设置为```"WindowsLive"```的参数一起使用，以便Teams用户可以与Skype用户通信。

## <a name="related-topics"></a>相关主题

- [在Teams中管理外部访问](manage-external-access.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
