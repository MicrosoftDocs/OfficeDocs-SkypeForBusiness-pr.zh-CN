---
title: 与 Microsoft Teams 中其他组织的用户通信
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 了解如何使用外部访问（联合身份验证）和来宾访问，与 Microsoft Teams 中其他组织的用户进行通信。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 8132fa07445beb9e9d26195a4269d025169ec94f
ms.sourcegitcommit: d46e739785595727e2b3e1e5f96f5bff65e78540
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753379"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>与 Microsoft Teams 中其他组织的用户通信
======================================================

当需要与组织外部的人员进行通信和协作时，Microsoft Teams 为你提供了两种不同的方法来实现这一目的。 第一个 – **外部访问**（联合身份验证）– 可用于查找、呼叫和与其他域（例如 contoso.com）中的用户进行聊天。 第二个 – **来宾访问** – 允许你使用个人的电子邮件地址将其作为来宾添加到团队中。 你可以像与组织中的其他任何用户一样与来宾协作。

如果需要，可同时使用外部访问和来宾访问（它们彼此之间不相排斥）。

下面大体介绍了选择方法（要进行详细比较，请跳转到[比较外部和来宾访问](#compare-external-and-guest-access)）：

## <a name="external-access"></a>外部访问

当需要允许其他域中的外部用户查找、呼叫你、与你聊天和安排会议的解决方案时，可使用**外部访问**（联合身份验证）。 外部用户无权访问贵组织的团队或团队资源。 当你要与仍在 Skype for Business（在线或本地）或 Skype（将在 2020 年初推出）上的外部用户进行通信时，请选择外部访问。 

默认情况下，Teams 中的外部访问处于启用状态，这意味着你的组织可以与所有外部域进行通信。 Teams 管理员可以将其关闭，也可以指定要包含（或排除）的域。 要了解详细信息，请参阅[管理外部访问](manage-external-access.md)。 

如果希望外部用户拥有访问团队和频道的权限，则选择使用[来宾访问](#guest-access)可能是更好的方法。 


## <a name="guest-access"></a>来宾访问

使用**来宾访问**将单个用户（无论来自哪个域）添加到团队，以便他们可以聊天、呼叫、召开会议和使用 Office 365 应用（如 Word、Excel 或 PowerPoint）就组织文件（存储在 SharePoint 或 OneDrive for Business）进行协作。 可以为来宾用户提供与本机团队成员几乎所有相同的 Teams 功能。 要了解详细信息，请阅读 [Teams 中的来宾访问](guest-access.md)。

- 来宾已添加到组织的 Active Directory 中。
- 要与来宾通信，来宾必须使用其来宾帐户登录到 Teams。 这意味着，来宾可能必须注销自己的 Teams 帐户才能登录到 Teams 帐户。
- 与外部访问（联合）用户相比，来宾用户有权访问 Teams 中的更多资源（例如文件、团队和频道）。
- Teams 管理员在 Teams 管理中心中控制来宾可以（或不可）执行的所有操作。 要了解详细信息，请阅读[管理来宾访问](manage-guests.md)。

如果你已准备好在组织中启用来宾访问，请从[来宾访问清单](guest-access-checklist.md)开始。


## <a name="compare-external-and-guest-access"></a>比较外部访问和来宾访问

| 功能 | 外部访问用户 | 来宾访问用户 |
|---------|-----------------------|--------------------|
| 用户可与其他公司的人聊天 | 是 |是 |
| 用户可呼叫其他公司的人员 | 是 | 是 |
| 用户可查看其他公司是否有人可供呼叫或聊天 | 是 | 是<sup>1</sup> |
| 用户可以跨外部租户搜索用户 | 是<sup>2</sup> | 否 |
| 用户可以共享文件 | 否 | 是 |
| 用户可访问 Teams 资源 | 否 | 是 |
| 可将用户添加到群聊 | 否 | 是 |
| 可邀请用户加入会议 | 是 | 是 |
| 可以将其他用户添加到与外部用户的聊天中 | 否<sup>3</sup> | 不适用 |
| 用户被标识为外部方 | 是 | 是 |
| 将显示状态 | 是 | 是 |
| 将显示外出消息 | 否 | 是 |
| 可阻止单个用户 | 否 | 是 |
| 支持 @提及 | 是<sup>4</sup> | 是 |
| 拨打私人电话 | 是 | 是 |
| 允许 IP 视频 | 是 | 是 |
| 屏幕共享模式 | 是<sup>4</sup> | 是 |
| 允许立即召开会议 | 否 | 是 |
| 编辑已发送的消息 | 是<sup>4</sup> | 是 |
| 可以删除已发送的消息 | 是<sup>4</sup> | 是 |
| 在对话中使用 Giphy | 是<sup>4</sup> | 是 |
| 在对话中使用 Meme | 是<sup>4</sup> | 是 |
| 在对话中使用贴纸 | 是<sup>4</sup> | 是 |
||||

<sup>1</sup> 前提是已将用户添加为来宾，并且已作为来宾登录到来宾租户。<br>
<sup>2</sup> 仅通过电子邮件或会话初始协议 (SIP) 地址。<br>
<sup>3</sup> 外部（联合）聊天仅可为一对一。<br>
<sup>4</sup> 支持来自两个不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。 *这是预览版或早期版本功能。*

## <a name="related-topics"></a>相关主题

[Teams 中的外部访问](manage-external-access.md)

[Teams 中的来宾访问](guest-access.md)

