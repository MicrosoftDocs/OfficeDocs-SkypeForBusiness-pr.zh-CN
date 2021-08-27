---
title: 欢迎使用 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: serdars
description: 找到在组织中部署 Microsoft Teams 的正确途径。 了解 Teams 基础结构以及如何与 Microsoft 365 或 Office 365 配合使用。
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: d16047b643ee8312a250156cbb5abcd083b01bc2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603641"
---
# <a name="welcome-to-microsoft-teams"></a>欢迎使用 Microsoft Teams
如果你是贵组织的 Microsoft Teams 管理员，本文正适合你。 准备好使用 Teams 时，请从 [如何推出 Teams](./deploy-overview.md) 和 [设置与 Microsoft 365 和 Microsoft Teams 的安全协作](/microsoft-365/solutions/setup-secure-collaboration-with-teams) 开始。

如果是第一次使用 Teams 且想要了解详细信息，请观看短视频“[欢迎使用 Teams](https://www.youtube.com/embed/s3aQV3T0D6c)”（55 秒）。

不要错过我们的视频“欢迎使用 Teams（针对 Teams 管理员）”（3 分多钟）：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE47cdp]

若要获取最终用户 Teams 帮助，请单击应用左侧的“帮助”，或转到 [Microsoft Teams 帮助中心](https://support.office.com/teams)。 有关培训，请访问 [Microsoft Teams 培训](training-microsoft-teams-landing-page.md)。 

## <a name="teams-architecture"></a>Teams 体系结构

Teams 基于 Microsoft 365 组、Microsoft Graph 以及与其余 Microsoft 365 和 Office 365 产品相同的企业级安全性、合规性和可管理性构建而成。 Teams 利用 Azure Active Directory (Azure AD) 中存储的身份。 即使在你脱机或遇到网络时好时坏的情况时，Teams 也会继续工作。

若要了解 Teams 在 Microsoft 365 上下文中的位置，请查看以下体系结构海报：[作为 Microsoft 365 一部分的 Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

创建团队时，将会创建以下各项：
- 新的 [Microsoft 365 组](office-365-groups.md)
- 用于存储团队文件的 [SharePoint Online](sharepoint-onedrive-interact.md) 站点和文档库
- [Exchange Online](exchange-teams-interact.md) 共享邮箱和日历
- OneNote 笔记本
- 与其他 Microsoft 365 和 Office 365 应用（例如 Planner 和 Power BI）的关联

从现有组创建团队时，该组的成员身份、站点、邮箱和笔记本将在 Teams 中出现。 要了解详细信息，请查看此海报：[面向 IT 架构师的 Microsoft 365 中的组](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

若要自定义和扩展 Teams，请通过[应用、机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)添加第三方应用。 在 Teams 中，你可以将组织外部的人员包含进来，方法是[将其以来宾身份添加](guest-access.md)到团队或频道中。 作为 Microsoft 365 和 Office 365 的一部分，Teams 提供了强大的[开发平台](/microsoftteams/platform)，以便你可以构建组织所需的团队合作中心。 

> [!TIP]
> 如需深入了解 Teams 体系结构，请观看 [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy) 中的视频。


## <a name="managing-teams"></a>管理团队

作为管理员，你将通过 Microsoft Teams 管理中心来管理团队。 要快速定位，请观看“使用 Teams 管理中心管理 Teams”视频（3:03 分钟）：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

要了解详细信息：

- [使用 Teams 管理员角色管理 Teams](using-admin-roles.md)
- [在 Teams 管理中心中管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [在过渡到全新的 Teams 管理中心期间管理 Teams](manage-teams-in-modern-portal.md)
- [在你的 Microsoft 365 或 Office 365 中管理 Teams 功能](enable-features-office-365.md)

要时刻了解贵组织中的 Teams 及所有其他 Microsoft 365 或 Office 365 产品和服务的新动向，请务必检查[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)和 [Teams 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)。 你将获取有关新功能和更新功能、规划更改以及一些问题的公告，以帮助你及时了解情况并做好准备。 

## <a name="upgrade-from-skype-for-business-to-teams"></a>从 Skype for Business 升级到 Teams
Teams 是 Microsoft 365 和 Office 365 中的主要智能通信客户端，它最终将取代 Skype for Business Online。 若要了解要添加到 Teams 的新功能，请参阅 [Microsoft 365 路线图](https://aka.ms/O365Roadmap)。 为了补充持久聊天和消息传递功能，Teams 通过完全集成的内置语音和视频功能提供全面的会议和通话体验。 请查看 Microsoft Teams 博客中的 [Teams 现在是完整的会议和通话解决方案](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)。

如果你正在运行 Skype for Business 并准备升级到 Teams，或者你正在同时运行 Skype for Business 和 Teams 并准备完全转为运行 Teams，我们提供了工具、提示和指导，以帮助你成功完成过渡。 若要了解详细信息，请参阅[升级到 Teams](upgrade-start-here.md)。

## <a name="teamwork"></a>团队合作
每个团队都是不同的，协作没有一刀切的方法。Microsoft 365 和 Office 365 旨在满足每个团队的独特需求，从而使大家能够通过专用的集成应用进行交流、协作以及取得更大的成就。

在决定要使用的 Microsoft 365 或 Office 365 应用和服务时，应考虑贵组织的工作内容以及你的团队需要采用的对话类型。 

- 作为团队合作的中心，组织内外的人员可在 **Teams** 中主动联系和协作来完成工作。 无论是共同创作文档、举行会议还是在其他应用和服务中合作，都可以在开展工作的地方进行对话。 在 Teams 中，可以进行非正式聊天、快速对项目进行重复操作、处理团队文件以及对共享的可交付结果进行协作。 

- **Outlook** 用于以熟悉的电子邮件环境和更加正式的结构化方式或在需要进行有目标的直接通信时进行协作。

- **SharePoint** 用于网站和门户、智能内容服务、业务流程自动化和企业搜索。 SharePoint 将内容保留在团队合作的中心位置，从而使所有类型的内容可在团队之间轻松共享和访问。 通过与 Outlook、Yammer 和 Teams 紧密集成，可在对话体验中实现无缝内容协作。

- **OneDrive for Business** 用于存储文件以及与用户邀请的人员共享这些文件。 用户保存到 OneDrive for Business 的内容在本人与其他人共享之前一直是私人的，因此 OneDrive for Business 非常适合存储不打算共享或未准备好共享的个人文档和草稿文档。

- **Yammer** 用于整个组织中的人员进行联系。 可推动公司范围的计划、共享最佳做法以及就共同的兴趣、领域或做法主题进行交流。 可汇聚众人的想法来提倡整个公司的人员进行开放式讨论。

- **Office 应用** 是大家都知道并经常使用的所有熟悉的工具，包括 Word、Excel、PowerPoint 和 OneNote。 

## <a name="teams-content-updates"></a>Teams 内容更新

查看[每周更新的 Teams 主题列表](teams-updates.md)。

## <a name="teams-known-issues"></a>Teams 已知问题

请参阅 [Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)。

## <a name="teams-client-release-notes"></a>Teams 客户端发行说明

请参阅 [Teams 中的新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)。