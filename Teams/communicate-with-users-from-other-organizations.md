---
title: 与其他组织中的用户通话和聊天
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用外部访问（联合身份验证）和来宾访问在 Microsoft Teams 中与组织外部的用户进行通话、聊天、查找和添加这些用户。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031808"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a>在 Microsoft Teams 中与其他组织的用户进行通话和聊天
======================================================

当你需要与组织外部人员进行沟通和协作时，Microsoft Teams 提供了两种不同的方法来实现这一目的。第一 – **外部访问** （联合身份验证） – 可用于查找、呼叫和与其他域（例如 contoso.com）中的用户聊天。第二 – **访客访问** – 使你可以使用其电子邮件地址将个人作为来并添加到你的团队中。可以像与组织中的其他任何用户一样与访客协作。

如果需要，可同时使用外部访问和来宾访问（它们彼此之间不相排斥）。

下面大体介绍了选择方法（要进行详细比较，请跳转到[比较外部和来宾访问](#compare-external-and-guest-access)）：

## <a name="external-access"></a>外部访问

当需要允许其他域中的外部用户查找、呼叫、聊天和安排会议的解决方案时，可使用 **外部访问** （联盟）。外部用户无法访问你组织的团队或团队资源。当你想要与仍在使用 Skype for Business（在线或本地）或 Skype （将于2020年年初推出）的组织外部用户进行沟通时，请选择外部访问。 

外部访问在 Teams 中默认为开启，这意味着你的组织可以与所有外部域进行通信。Teams 管理员可以将其关闭或指定要包括（或排除）的域。若要了解更多信息，请参阅[管理外部访问](manage-external-access.md)。 

如果希望外部用户拥有访问团队和频道的权限，则选择使用[来宾访问](#guest-access)可能是更好的方法。 


## <a name="guest-access"></a>来宾访问权限

使用 **来宾访问** 将个人用户（无论域）添加到团队中，以便他们可以使用 Microsoft 365 或者 Office 365 应用程序（例如 Word、Excel 或 PowerPoint）就组织文件（存储在 SharePoint 或 OneDrive for Business中）进行聊天、通话、开会和协作。来宾用户可以获得与本地团队成员几乎相同的所有团队功能。要了解更多信息，请阅读 [Teams 中的访客访问](guest-access.md)。

- 来宾已添加到组织的 Active Directory 中。
- 要与访客沟通，访客必须使用他们的访客账户登录到 Teams。这意味着访客可能需要从自己的 Teams 账户中注销才能登录到你的 Teams 账户，如果是同一个账户，则需要切换组织。
- 与外部访问（联合）用户相比，来宾用户有权访问 Teams 中的更多资源（例如文件、团队和频道）。
- Teams 管理员在 Teams 管理中心中控制来宾可以（或无法）执行的所有操作。要了解更多信息，请阅读[管理访客访问](manage-guests.md)。 

如果你已准备好在组织中启用来宾访问，请从[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)开始。


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
| 查看适用于拨入会议参加者的电话号码 | 否<sup>5</sup> | 是 |
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
<sup>4</sup> 支持来自两个不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。 <br>
<sup>5</sup> 默认情况下，外部参与者无法看到已拨入的参与者的电话号码。如果想要维持这些电话号码的隐私，请选择 **进入/退出公告类型** （这会阻止Teams读取号码）的 **音调** 。若要了解更多详细信息，请参阅 [在Microsoft Teams中打开或关闭会议的进入和退出公告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。

## <a name="related-topics"></a>相关主题

[Teams 中的外部访问](manage-external-access.md)

[Teams 中的来宾访问](guest-access.md)

