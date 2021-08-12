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
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 了解组织中用户与Teams使用者用户Skype (互操作性) 功能。
localization_priority: Normal
ms.openlocfilehash: 42a6631a70156cf150e175b7c5dd1cd661a84c77f0523e61c9d7b9313e4f81e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312460"
---
# <a name="teams-and-skype-interoperability"></a>Teams和Skype互操作性

本文概述了使用者与使用者之间Microsoft Teams Skype (互操作性) 。 了解如何Teams用户Skype用户可以通过聊天和呼叫以及所应用的管理控件进行通信。

Teams组织的用户可以使用其电子邮件地址Skype聊天和呼叫用户，反之亦然。

- Teams用户可以搜索并启动一对一纯文本对话或与用户进行的音频/视频Skype通话。
- Skype用户可以搜索并启动一对一纯文本对话或与用户进行的音频/视频Teams通话。

这些功能在 Android 和 iOS (桌面、Web 和移动设备上) 客户端Teams Skype。 为获得最佳体验，我们建议Skype 8.58 及更高版本。

> [!NOTE]
> 本文Teams和 Skype 互操作功能在 GCC、GCC High 或 DOD 部署或私有云环境中不可用。

## <a name="chat-and-calling-experience"></a>聊天和通话体验

下面是聊天和通话体验的概述。

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams用户启动与用户聊天或Skype通话

Teams用户可以通过Skype聊天或搜索栏中键入其电子邮件地址来搜索用户。  然后Teams用户可以在搜索结果中选择Skype用户以开始聊天或呼叫他们。

用户Skype选择不显示在搜索结果中。 在这种情况下，它们不会显示在搜索的搜索结果中Teams Teams用户无法找到它们。

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype用户启动与用户聊天或Teams通话

Skype用户可以使用其电子邮件地址搜索Teams用户开始聊天。 通知Teams用户有来自新用户的新Skype，并且必须首先接受该消息，然后才能答复它。

- 如果Teams选择"接受"，则接受对话，并且两个用户都可以聊天和呼叫对方。
- 如果Teams选择"阻止"，则会话将被阻止，来自该用户的后续消息Skype调用将被阻止。
- 如果用户Teams"查看消息"，消息会显示在 Teams 中，这有助于用户决定是接受还是阻止对话。

> [!NOTE]
> 如果你从 Skype for Business 升级到 Teams 并且你的用户进入 Teams 仅模式，则来自 Skype 用户的聊天和呼叫将传递到 Teams 用户Teams。 如果你的用户在群岛模式下，来自Skype用户的聊天Teams呼叫将传递到Skype for Business。

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams用户阻止或取消阻止Skype用户

在Teams用户接受或阻止来自用户的初始Skype请求后，他们可以选择随时阻止或取消阻止该用户。 他们可以在对话中或在对话中的隐私设置中Teams。 Skype用户不会知道他们已被阻止。

阻止Skype用户以及其他人和公共电话交换网 (PSTN) 电话号码（Teams 用户已被阻止）列在 Teams 中用户的阻止联系人列表中。

## <a name="limitations"></a>限制

- 对话是纯文本对话。 这意味着没有丰富的格式、@mentions、表情符号或其他任何在本机聊天体验中可用的Teams[功能](native-chat-for-external-users.md)。
- 对话是一对一的。 不支持群组聊天。
- Teams用户Skype用户无法看到对方的状态。
- 不支持使用Skype ID 或电话号码Skype搜索用户。
- Skype用户无法呼叫设置了呼叫Teams其他用户号码、代理人号码或公用电话交换网 (PSTN) 号码的用户。  仅支持语音邮件。
- 不支持互操作升级、群组通话和会议。
- 不支持代理人代表Skype呼叫用户Teams权限。
- 不支持通过聊天进行屏幕共享。

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>设置Teams用户是否可以与Skype通信

作为管理员，可以使用 Microsoft Teams 管理中心或 PowerShell 设置外部访问设置，控制Teams用户是否可以与Skype通信。 默认情况下，此功能已针对新租户启用。 但是，有一个先决条件是，以下 DNS SRV 记录需要由 IT 管理员配置（如果尚未适用于你的域，例如 _sipfederationtls.contoso.com）。  

**服务**：sipfederationtls<br/>
**协议**：TCP<br/>
**优先级**：100<br/>
**权重**：1<br/>
**端口**：5061<br/>
**目标**：sipfed.online.lync.com

如果从 Skype for Business 升级到 Teams，在 Skype for Business 管理中心配置的外部通信设置将迁移到 Teams。

### <a name="in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心

在Microsoft Teams管理中心，转到"**组织范围的** 设置""外部访问"，然后打开"用户可以与Skype  >  **通信"。** 有关如何配置此设置和其他外部访问设置的分步指南，请参阅在 Teams 中管理[外部访问](./manage-external-access.md#allow-or-block-domains)。

### <a name="using-powershell"></a>使用 PowerShell

执行以下操作： 
1. 将[Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与 参数一起Teams用户是否可以与 ```EnablePublicCloudAccess``` Skype通信。 将 参数设置为 ```true``` 可让Teams与用户Skype通信。 可以使用 参数 ```EnablePublicCloudAudioVideoAccess``` 来启用/禁用音频/视频呼叫。

2. 将[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与参数设置为 一起Teams，以便用户能够 ```Provider``` ```"WindowsLive"``` 与Skype通信。

## <a name="related-topics"></a>相关主题

- [管理 Teams 中的外部Teams](manage-external-access.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)