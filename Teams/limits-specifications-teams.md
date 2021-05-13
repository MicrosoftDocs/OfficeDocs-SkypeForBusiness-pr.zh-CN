---
title: Microsoft Teams 的限制和规范
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: 本文介绍了适用于 Microsoft Teams 的限制、规范和其他要求。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fbf2efa3ad1d77300138a57336b4254ea788e84
ms.sourcegitcommit: 242561bfc12504614633539ca696b91dfc890b92
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52328504"
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
|可导入到团队中的通讯组列表、安全组或 Office 365 组的最大大小    |3,500|
|Office 365 组中最多可以有多少名成员以转换为团队    |10,000<sup>6</sup>     |
|频道对话文章大小 | 每个帖子约 28 KB<sup>5</sup> |

<sup>1</sup> Azure Active Directory 中的目录对象均计入此限额。与使用[应用程序权限](/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。

<sup>2</sup> 此限制包含已存档的团队。 

<sup>3</sup> 若要进一步增加团队数量，必须联系 Microsoft 支持人员，并请求进一步增加租户中的 Azure Active Directory 对象数量。 仅针对真实生产方案进行了增加。

<sup>4</sup> 30 天内可还原已删除的频道。 在这 30 天内，已删除的频道仍然计入每个团队 200 个频道或 30 个专用频道这一限额内。 30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队的限额内。

<sup>5</sup> 28 KB 是近似限制，因为它包括邮件本身（文本、图像链接等）、@提及、连接线数目以及反应。

<sup>GCC</sup> 6 个工作组可容纳 25，000 名成员，但 GCCH/DoD 中的团队仅能容纳 2，500 个成员。 进一步请注意，拥有 10，000 多个成员的团队/频道提及将被阻止。

## <a name="messaging"></a>消息传递

### <a name="chat"></a>聊天

参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）

Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。

|功能  | 最大限制  |
|---------|---------|
|私人聊天中的人员数<sup>1</sup>  | 250<sup>2</sup> |
|通过视频或音频通话聊天的人员数 | 20 |
|文件附件数<sup>3</sup>  |10     |
|聊天大小 | 每篇文章约 28 KB<sup>4</sup> |

<sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。当专用组聊天包含超过 20 个成员时，还将删除“设置发送选项”按钮 (!)。

<sup>2</sup> 一次仅有 200 个成员可添加到群组聊天。 [请参阅本文了解详细信息](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)。

<sup>3</sup> 如果附件数超过此限制，你将看到一条错误消息。

<sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。

### <a name="emailing-a-channel"></a>向频道发送电子邮件

 如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。下面是有关向频道发送电子邮件的一些适用限制。

|功能  | 最大限制  |
|---------|---------|
|邮件大小<sup>1<sup> | 24 KB |
|文件附件数<sup>2</sup>  |20     |
|每个文件附件的大小 | 小于 10 MB |
|内嵌图像数<sup>2</sup> |50   |

<sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。

<sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。

有关详细信息，请参阅 [Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。

> [!NOTE]
> 所有 Microsoft 365 和 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。Office GCC/GCCH/DOD 组织无法在 Teams 中通过电子邮件发送频道。

## <a name="channel-names"></a>频道名称

频道名称不得包含以下字符或字词。

|类型|示例|
|---------|---------|
|字符     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|下述范围内的字符    | 0 到 1F<br>80 到 9F        |
|字词     | forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;|

此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。

## <a name="meetings-and-calls"></a>会议和通话

> [!IMPORTANT]
> **Microsoft 365 实时事件限制的增加**
>
> **若要继续支持客户的需求，直至2021年6月30日，我们将扩展现场活动的临时增加限额，包括**：
>
>- 可为多达20,000名与会者提供活动支持
>- 一个租户可同时举办50场活动
>- 每次广播的活动持续时间为16小时
>
> 此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。

|功能     | 最大限制 |
|------------|---------------|
|会议中的人数（可聊天和通话）  | 1000，包括 GCC，但还不包括 GCCH 或 DoD。 “**仅供查看**”允许最多 20，000 名仅收听的参与者加入组织者拥有 E3/E5/A3/A5 SKU 以及政府版（GCC、GCC High 和 DoD）许可证。 了解关于[仅供查看体验](view-only-meeting-experience.md)的详细信息。|
|通过视频或音频通话聊天的人员数 | 20 |
|PowerPoint 文件的最大大小 | 2GB|
|Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md) | 20 天 |

### <a name="meeting-expiration"></a>会议过期时间

> [!NOTE]
> 会议 URL 永远不会停止工作。过期仅涉及任何 PSTN 拨入号码和/或基础会议策略和设置。

|会议类型  |会议将在此时间后过期  |每次发起或更新会议时，过期时间都延长此时间  |
|---------|---------|---------|
|立即开会     |开始时间 + 8 小时         |不适用         |
|常规，无结束时间     |开始时间 + 60 天         | 60 天        |
|常规，设有结束时间     |结束时间 + 60 天         |60 天         |
|定期，无结束时间     |开始时间 + 60 天         |60 天         |
|定期，设有结束时间     |上次会议的结束时间 + 60 天         |60 天         |

> [!NOTE]
> Microsoft Teams 会议的时间限制为 24 小时。

## <a name="teams-live-events"></a>Teams 实时事件

|功能     | 最大限制 |
|------------|---------------|
|受众规模 | 10,000 名与会者 |
|事件持续时间 | 4 小时 |
|Microsoft 365 或 Office 365 组织中运行的并发实时事件数 <sup>1</sup> | 15 |

<sup>1</sup> 可根据需要安排许多实时事件，但每次只能运行 15 个。一旦制造者加入实时事件，即被视为正在运行。尝试加入第 16 个实时事件的制造者将收到错误消息。

要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。另请参阅[安排 Teams 实时事件](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

> [!IMPORTANT]
> **Microsoft 365 实时事件限制的增加**
>
> **若要继续支持客户的需求，直至2021年6月30日，我们将扩展现场活动的临时增加限额，包括**：
>
>- 可为多达20,000名与会者提供活动支持
>- 一个租户可同时举办50场活动
>- 每次广播的活动持续时间为16小时
>
> 此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。 

## <a name="presence-in-outlook"></a>Outlook 中的状态

Outlook 2013 桌面应用及更高版本支持 Outlook 中的 Teams 状态。若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。

## <a name="storage"></a>存储

Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。

> [!NOTE]
> 每个[专用频道](./private-channels.md)都拥有自己的 SharePoint 网站（以前称为“网站集”）。

如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。

通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）

由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。下面是一些适用于 SharePoint Online 的存储限制。

|功能                 |Microsoft 365 商业基础版  |Microsoft 365 商业标准版   |Office 365 企业版 E1  |Office 365 企业版 E3  |Office 365 企业版 E5  |Office 365 企业版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|存储空间                 |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。  |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。  |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。   |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。 |每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。  |每个组织 1 TB 空间           |
|Teams 文件存储空间 |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |每个网站或组最多 25 TB |
|文件上传限制（每个文件）    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |

频道由 SharePoint Online 网站（以前称为“网站集”）中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。

有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="class-teams"></a>课堂团队

Microsoft Teams 教育版提供了专为独特教育场景设计的模板，如课堂教学。有关团队类型的详细信息（包括课堂团队），可在“[在 Microsoft Teams 中选择团队类型进行协作](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)”中找到。

课堂团队是一种模板类型，其中包含附加应用，且具有单独限制团队成员数量的功能。

> [!NOTE]
> 使用课堂团队需要 [Office 365 教育版许可证](https://www.microsoft.com/education/products/office)。

下表列出了课堂团队的限制：

|功能  |最大限制  |
|---------|---------|
|团队中的成员数    | 请参阅本文的[“团队和频道”](#teams-and-channels)部分        |
|课堂团队中使用“作业”的成员数    | 200        |
|课堂团队中使用“OneNote 课堂笔记本”的成员数     |200         |

课堂团队可以支持超过 200 位成员。但是，如果你计划在你的团队中使用“作业”应用或“课堂笔记本”应用，则需要保留低于最大限制的成员数。

## <a name="tags"></a>标记

|功能  |最大限制  |
|---------|---------|
|每个团队的标记数    | 100        |
|每个团队建议的默认标记数    | 25        |
|分配有标记的团队成员数    |100         |
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
