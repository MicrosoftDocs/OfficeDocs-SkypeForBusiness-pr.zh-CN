---
title: Microsoft Teams 的限制和规范
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: 本文介绍了适用于 Microsoft Teams 的限制、规范和其他要求。
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b34f22d5ef038eff44b5488588902d1a99af8676
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486612"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams 的限制和规范

本文介绍了适用于 Teams 的一些限制、规范和其他要求。

## <a name="teams-and-channels"></a>团队和频道

|功能    | 最大限制 |
|-----------|---------------|
|用户可创建的团队数 | 限制为 250 个对象&sup1;         |
|用户可以成为其成员的团队数|1,000&sup2;|
|团队中的成员数 | 25,000<sup>6</sup>     |
|每个团队的所有者数 | 100   |
|租户中允许的组织范围内的团队数 | 5&sup2;     |
|[组织范围内的团队](create-an-org-wide-team.md)中的成员数 | 10,000       |
|全局管理员可创建的团队数        |  500,000   |
|Microsoft 365 或 Office 365 组织可拥有的团队数    | 500,000&sup3;     |
|每个团队的频道数    | 200（包括已删除的频道）<sup>4</sup>        |
|各团队专用频道数    |30（包括已删除的频道）<sup>4</sup>        |
|专用频道中的成员数    |250|
|可导入到团队中的通讯组列表、安全组或 Microsoft 365 组的最大大小    |3,500|
|Microsoft 365 组中可转换为团队的最大成员数    |10,000<sup>6</sup>     |
|频道对话文章大小 | 每个帖子约 28 KB<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> 此限制包含已存档的团队。 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KB 是近似限制，因为它包括邮件本身（文本、图像链接等）、@提及、连接线数目以及反应。

<sup>6</sup> 来自团队外部的共享频道成员计入此限制。 进一步请注意，拥有 10，000 多个成员的团队/频道提及将被阻止。

> [!NOTE]
> 有关共享频道的限制，请参阅[共享频道的限制](/MicrosoftTeams/shared-channels#limits-for-shared-channels)。

## <a name="messaging"></a>消息传递

### <a name="chat"></a>聊天

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|功能  | 最大限制  |
|---------|---------|
|私人聊天中的人员数<sup>1</sup>  | 250<sup>2</sup> |
|通过视频或音频通话聊天的人员数 | 20 |
|文件附件数<sup>3</sup>  |10     |
|聊天大小 | 每篇文章约 28 KB<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> 如果附件数超过此限制，你将看到一条错误消息。

<sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。

### <a name="emailing-a-channel"></a>向频道发送电子邮件

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|功能  | 最大限制  |
|---------|---------|
|邮件大小<sup>1<sup> | 24 KB |
|文件附件数<sup>2</sup>  |20     |
|每个文件附件的大小 | 小于 10 MB |
|内嵌图像数<sup>2</sup> |50   |

> [!NOTE]
> 可以向频道发送的电子邮件数量存在限制。 限制是每个用户每个渠道每 10 秒 6 封邮件，每个用户每个租户每 10 秒 8 封邮件。
<sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。

<sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。

有关详细信息，请参阅 [Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>频道名称

频道名称不得包含以下字符或字词。

|类型|示例|
|---------|---------|
|字符     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|下述范围内的字符    | 0 到 1F<br>80 到 9F        |
|字词     | forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;|

此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。

## <a name="meetings-and-calls"></a>会议和通话

|功能     | 最大限制 |
|------------|---------------|
|会议中的人数（可聊天和通话）  | 1000，包括 GCC、GCCH 和 DoD，但不包括 A1 (300)。 “**仅供查看**”允许最多 20，000 名仅收听的参与者加入组织者拥有 E3/E5/A3/A5 SKU 以及政府版（GCC、GCC High 和 DoD）许可证。 仅查看体验很快也可用于网络研讨会。 了解关于 [仅供查看体验](view-only-meeting-experience.md) 的详细信息。<sup>1，2</sup>|
|通过视频或音频通话聊天的人员数 | 20 |
|PowerPoint 文件的最大大小 | 2 GB|
|Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md) | 20 天 |
| 会议记录最大长度 | 4 小时或 1.5 GB。 达到此限制后，录制将结束并自动重启。
  
<sup>1</sup> 为了在大型会议、网络研讨会和直播活动中获得最佳体验，Microsoft 建议使用最新版本的 Teams 桌面客户端或 Teams 移动客户端。

<sup>2</sup> 大型会议、网络研讨会和直播活动中的演示者应使用 Teams 桌面客户端。 有关托管大型会议的更多提示，请参阅 [大型 Teams 会议最佳做法](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)。

> [!NOTE]
> 分组讨论室只能在与会者少于 300 人的会议上创建。 此外，在会议中创建分组讨论室会自动将会议平台的数量限制在 300 个。 建议最终用户不要在预计超过 300 人的会议上启动分组讨论室。 有关大型 Team 会议的更多信息，请与最终用户共享 [大型 Teams 会议的最佳实践](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16) 指南。

### <a name="meeting-expiration"></a>会议过期时间

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|会议类型  |会议将在此时间后过期  |每次发起或更新会议时，过期时间都延长此时间  |
|---------|---------|---------|
|立即开会     |开始时间 + 8 小时         |不适用         |
|常规，无结束时间     |开始时间 + 60 天         | 60 天        |
|常规，设有结束时间     |结束时间 + 60 天         |60 天         |
|定期，无结束时间     |开始时间 + 60 天         |60 天         |
|定期，设有结束时间     |上次会议的结束时间 + 60 天         |60 天         |

> [!NOTE]
> Microsoft Teams 会议的时间限制为 30 小时。

## <a name="teams-live-events"></a>Teams 实时事件

|功能     | 最大限制 |
|------------|---------------|
|受众规模 | 10,000 名与会者 |
|事件持续时间 | 4 小时 |
|Microsoft 365 或 Office 365 组织中运行的并发实时事件数 <sup>1</sup> | 15 |

<sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.

有关直播活动的详细信息，请转到 [Teams 直播活动](teams-live-events/plan-for-teams-live-events.md#teams-live-events)。 另请参阅[安排 Teams 实时事件](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

> [!IMPORTANT]
> **Microsoft 365 实时事件限制的增加**
>
> **为了继续满足客户需求，我们将现场活动的临时限制增加延长至 2022 年 12 月 31 日，包括**：
>
>- 可为多达20,000名与会者提供活动支持
>- 一个租户可同时举办50场活动
>- 每次广播的活动持续时间为16小时
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Outlook 中的状态

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>存储

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> 每个[专用频道](./private-channels.md)都拥有自己的 SharePoint 网站（以前称为“网站集”）。

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|功能                 |Microsoft 365 商业基础版  |Microsoft 365 商业标准版   |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|存储空间                 |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。  |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。  |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。   |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。 |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。  |每个组织 1 TB 空间           |
|Teams 文件存储空间 |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |
|文件上传限制（每个文件）    |250GB    |250GB    |250GB    |250GB    |250GB    |250GB    |

频道由 SharePoint Online 网站（以前称为“网站集”）中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。

有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="class-teams"></a>课堂团队

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

课堂团队是一种模板类型，其中包含附加应用，且具有单独限制团队成员数量的功能。

> [!NOTE]
> 使用课堂团队需要 [Office 365 教育版许可证](https://www.microsoft.com/education/products/office)。

下表列出了课堂团队的限制：

|功能  |最大限制  |
|---------|---------|
|团队中的成员数    | 请参阅本文的[“团队和频道”](#teams-and-channels)部分        |
|课堂团队中使用“作业”的成员数    | 300        |
|课堂团队中使用 OneNote 课堂笔记本的成员数     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>标记

|功能  |最大限制  |
|---------|---------|
|每个团队的标记数    | 100        |
|每个团队建议的默认标记数    | 25        |
|分配有标记的团队成员数    |200         |
|分配给每个团队每个用户的标记数    |25         |

## <a name="contacts"></a>联系人

Teams 使用下述联系人：

- 组织的 Active Directory 中的联系人
- 添加到用户的 Outlook 默认文件夹中的联系人

Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。

通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。

## <a name="browsers"></a>浏览器

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>操作系统

要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。
