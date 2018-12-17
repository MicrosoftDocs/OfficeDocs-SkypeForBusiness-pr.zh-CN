---
title: Microsoft Teams 概述
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.date: 11/06/18
ms.reviewer: LolaJ
description: 了解 Microsoft Teams、其基础结构以及如何配合使用 Teams 与 Office 365。
localization_priority: Priority
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02848be0401bf06fff989b9b5ab79cdddcc70070
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240674"
---
# <a name="welcome-to-microsoft-teams"></a>欢迎使用 Microsoft Teams

如果你是贵组织的 Microsoft Teams 管理员，本文正适合你。 在此你将了解到规划、部署和运行 Teams 所需的所有信息。  

## <a name="overview-of-teams"></a>Teams 概述

如果你刚开始使用 Teams，请观看此短视频：[欢迎使用 Teams](https://support.office.com/article/video-welcome-to-microsoft-teams-b98d533f-118e-4bae-bf44-3df2470c2b12?wt.mc_id=otc_microsoft_teams)。 Teams 基于 Office 365 组、Office Graph 以及与 Office 365 其余产品相同的企业级安全性、合规性和可管理性构建而成。 Teams 利用 Azure Active Directory (Azure AD) 中存储的身份。 创建团队时，将会创建以下各项：
- 新 [Office 365 组](office-365-groups.md)
- 用于存储团队文件的 [SharePoint Online](sharepoint-onedrive-interact.md) 站点和文档库
- [Exchange Online](exchange-teams-interact.md) 共享邮箱和日历
- OneNote 笔记本
- 与其他 Office 365 应用（例如 Planner 和 Power BI）的关联

从现有组创建团队时，该组的成员身份、站点、邮箱和笔记本将移植到 Teams。 不要错误新的[组织范围的团队](create-an-org-wide-team.md)，这是一种特殊类型的团队，它将组织中所有用户包含进来，并在用户加入和离开组织时在 Active Directory 中更新成员身份。 

要自定义和扩展 Teams，请通过[选项卡](built-in-custom-tabs.md)、[连接器](office-365-custom-connectors.md)和[聊天机器人](add-bots.md)添加第三方应用。 在 Teams 中，你可以将贵组织外的人员包含进来，方法是[将其以来宾身份添加](guest-access.md)到团队或频道中。 作为 Office 365 的一部分，Teams 提供了强大的[扩展功能](https://docs.microsoft.com/en-us/microsoftteams/platform)，以便你可以构建贵组织所需的团队合作中心。 

![Teams 桌面应用和移动应用](media/teams-overview-hub.png)

Teams 是 Office 365 中的主要智能通信客户端，将逐渐取代 Skype for Business Online。 要详细了解已内置到 Teams 中的 Skype for Business 特性和功能，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](http://aka.ms/skype2teamsroadmap)。 为了补充持久聊天和消息传递功能，Teams 通过内置的完全集成的语音和视频功能提供全面的会议和通话体验。 请查看 Microsoft Teams 博客中的 [Teams 现在是完整的会议和通话解决方案](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)。

## <a name="teams-admin-experience"></a>Teams 管理体验

我们正在推出全新的 Microsoft Teams 与 Skype for Business 管理中心。 如果你尚未看到，不久将会看到，此管理中心将为你提供统一的 Teams 和 Skype for Business 管理体验。 自 2018 年 3 月起，我们已逐步将设置从 Skype for Business 管理中心和 Office 365 管理中心中的 Teams 体验迁移至此管理中心。 

在迁移期间，你将会面临两种不同的管理体验。 不用担心 - 我们会确保你不会有任何迷失！ 迁移了某项设置后，你将收到通知，并被定向到该设置在 Microsoft Teams 与 Skype for Business 管理中心中的新位置。 要了解详细信息，请参阅[在过渡到全新的 Microsoft Teams 与 Skype for Business 管理中心期间管理团队](manage-teams-skypeforbusiness-admin-center.md)。 

要时刻了解贵组织中的 Teams 及所有其他 Office 365 产品和服务的新动向，请务必检查[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)和 [Teams 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams)。 你将获取有关新功能和更新功能、规划更改以及一些问题的公告，以帮助你及时了解情况并做好准备。 

## <a name="upgrade-from-skype-for-business-to-teams"></a>从 Skype for Business 升级到 Teams
如果你已在使用 Teams，那就太棒了！ 使用此处的资源可充分利用作为贵组织团队合作中心的 Teams。 

如果你正在运行 Skype for Business 并准备升级到 Teams，或者你正在同时运行 Skype for Business 和 Teams 并准备完全转为运行 Teams，我们提供了工具、提示和指导，以帮助你成功完成过渡。 要了解详细信息，请参阅 [Skype for Business 到 Microsoft Teams 升级](journey-skypeforbusiness-teams.md)。

## <a name="teamwork-and-office-365"></a>团队合作和 Office 365
每个团队各不相同，因此不存在适用于所有团队的通用协作方法。 Office 365 旨在满足每个团队的独特需求，从而使大家能够通过专用的集成应用进行交流、协作以及取得更大的成就。 

在决定要使用的 Office 365 应用和服务时，应考虑贵组织的工作内容以及你的团队需要采用的对话类型。 

- **Teams** 是一个数字化中心，为了核心项目紧密合作的人员（包括贵组织外部的人员）可以在此实时主动联系和协作来完成工作。 无论是共同创作文档、举行会议还是在其他应用和服务中合作，都可以在开展工作的地方进行对话。 在 Teams 中，可以进行非正式聊天、快速对项目进行重复操作、处理团队文件以及对共享的可交付结果进行协作。 

- **Outlook** 用于以熟悉的电子邮件环境和更加正式的结构化方式或在需要进行有目标的直接通信时进行协作。 

- **SharePoint** 用于网站和门户、智能内容服务、业务流程自动化和企业搜索。 SharePoint 将内容保留在团队合作的中心位置，从而使所有类型的内容可在团队之间轻松共享和访问。 通过与 Outlook、Yammer 和 Teams 紧密集成，可在对话体验中实现无缝内容协作。   

- **OneDrive for Business** 用于存储文件以及与用户邀请的人员共享这些文件。 用户保存到 OneDrive for Business 的内容在本人与其他人共享之前一直是私人的，因此 OneDrive for Business 非常适合存储不打算共享或未准备好共享的个人文档和草稿文档。

- **Yammer** 用于整个组织中的人员进行联系。 可推动公司范围的计划、共享最佳做法以及就共同的兴趣、领域或做法主题进行交流。 可汇聚众人的想法来提倡整个公司的人员进行开放式讨论。

- **Office 应用**是大家都知道并经常使用的所有熟悉的工具，包括 Word、Excel、PowerPoint 和 OneNote。 

## <a name="teams-known-issues"></a>Teams 已知问题

请参阅 [Microsoft Teams 的已知问题](Known-issues.md)

## <a name="teams-client-release-notes"></a>Teams 客户端发行说明

请参阅 [Microsoft Teams 中的新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)

