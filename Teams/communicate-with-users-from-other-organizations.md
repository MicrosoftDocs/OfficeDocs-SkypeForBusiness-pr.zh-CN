---
title: 使用来宾访问权限和外部访问权限与组织外部的人员进行协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: 了解如何使用外部访问和来宾访问在 Microsoft Teams 中与组织外部的人员进行通话和聊天以及查找和添加这些人员。
ms.openlocfilehash: f416453a93c07945f9df55c863f76cbb8b736a78
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198314"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>使用来宾访问权限和外部访问权限与组织外部的人员进行协作

本文介绍与组织外部人员协作的两个选项：

- **外部访问** - 一种联盟，允许用户查找其他组织中的人员以及与其通话和聊天。 除非作为来宾受到邀请，否则这些人员无法添加到团队。
- **来宾访问** - 来宾访问允许邀请组织外部人员加入团队。 受邀人员将在 Azure Active Directory 中获得来宾帐户。

有关 Microsoft 365 中的外部协作的完整概述，请参阅 [Microsoft 365 中的外部协作选项概述](/microsoft-365/enterprise/external-guest-access)。

## <a name="external-access-external-chat-and-meetings"></a>外部访问（外部聊天和会议） 

针对组织外部使用 Teams、Skype for Business（联机或本地）或 Skype 的人员，如果需要查找此类人员、与其通话和聊天以及设置与此类人员的会议，可设置外部访问。 

默认情况下，将针对所有域启用外部访问。 你可以通过允许或阻止特定域或者通过关闭该设置来限制外部访问。

![外部访问设置的屏幕截图。](media/external-access-federation-settings.png)

外部访问可供以下租户使用：
- 托管企业帐户
     - 仅限商业版之间
     - 仅在 GCC 之间
     - 仅在 GCC High 之间
     - 仅在 DOD 之间
- 非托管 (个人) 帐户
     - 仅在商业帐户和个人帐户之间
- Skype for Business互操作
     - 在商业、GCC、GCC High 和 DoD 之间和跨
- Skype 互操作
     - 仅限商业版和 Skype 之间

若要配置外部访问，请参阅[管理外部访问](manage-external-access.md)。 

>[!NOTE]
> [Microsoft Teams 免费版 (经典)](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c) 许可证不支持外部访问。

## <a name="guest-access"></a>来宾访问

使用来宾访问将组织外部人员添加到团队，他们可在其中聊天、通话、开会和协作处理文件。 来宾可以获得几乎与本地团队成员相同的 Teams 功能。 有关详细信息，请参阅 [Teams 中的来宾体验](guest-experience.md)。

来宾作为 B2B 协作用户添加到组织的 Azure Active Directory，必须使用其来宾帐户登录到 Teams。 这意味着，他们可能需要从自己的组织注销才能登录到你的组织。

来宾访问权限可供以下租户使用：

- 商业和 GCC 之间
- 仅在 GCC High 之间
- 仅在 DOD 之间

若要为 Teams 配置来宾访问，请参阅[在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)。

## <a name="compare-external-and-guest-access"></a>比较外部访问和来宾访问

下表显示了使用外部访问（联盟）和来宾访问的区别。 在这两种情况下，组织外部人员均被标识为外部用户。

### <a name="things-your-users-can-do"></a>你的用户可以进行的一些操作

| 用户可以 | 外部访问用户 | 来宾 |
|---------|-----------------------|--------------------|
| 与其他组织中的人聊天 | 是 | 是 |
| 呼叫其他组织中的人 | 是 | 是 |
| 查看其他组织中的人是否可接受呼叫或聊天 | 是 | 是<sup>1</sup> |
| 搜索其他组织中的人员 | 是<sup>2</sup> | 否 |
| 共享文件 | 否 | 是 |
| 查看另一个组织中某人外出期间的邮件 | 否 | 是 |
| 组织其他组织中的某个人  | 否 | 是 |
| 使用 @提及 | 是<sup>3</sup> | 是 |

### <a name="things-people-outside-your-organization-can-do"></a>组织外部的人员可以进行的一些操作

| 组织外部的人员可以 | 外部访问用户 | 来宾 |
|---------|-----------------------|--------------------|
| 访问 Teams 资源 | 否 | 是 |
| 被添加到群聊 | 是 | 是 |
| 受邀加入会议 | 是 | 是 |
| 拨打私人电话 | 是 | 是<sup>5</sup> |
| 查看拨入会议参与者的电话号码 | 否<sup>4</sup> | 是 |
| 使用 IP 视频 | 是 | 是<sup>5</sup> |
| 使用屏幕共享 | 是<sup>3</sup> | 是<sup>5</sup> |
| 使用立即开会 | 否 | 是<sup>5</sup> |
| 编辑已发送的消息 | 是<sup>3</sup> | 是<sup>5</sup> |
| 删除已发送的消息 | 是<sup>3</sup> | 是<sup>5</sup> |
| 在对话中使用 Giphy | 是<sup>3</sup> | 是<sup>5</sup> |
| 在对话中使用 Meme | 是<sup>3</sup> | 是<sup>5</sup> |
| 在对话中使用贴纸 | 是<sup>3</sup> | 是<sup>5</sup> |
| 将显示状态 | 是 | 是 |
| 使用 @提及 | 是<sup>3</sup> | 是 |

<br>

<sup>1</sup> 前提是已将用户添加为来宾，并且对方已使用来宾帐户登录。<br>
<sup>2</sup> 仅通过电子邮件或会话初始协议 (SIP) 地址。<br>
<sup>3</sup> 支持来自不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。 <br>
<sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> 默认允许，但可由 Teams 管理员禁用

## <a name="related-topics"></a>相关主题

[Teams 中的外部访问](manage-external-access.md)

[Teams 中的来宾访问](guest-access.md)
