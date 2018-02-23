---
title: "Microsoft Teams 概述"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "了解 Microsoft Teams、其基础结构以及如何配合使用 Teams 与 Office 365。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 353e757c12b4e72a72b49abe4381abb9a188166b
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="overview-of-microsoft-teams"></a>Microsoft Teams 概述
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


Microsoft Teams 结合了 Office 365 的完整宽度和深度，为团队合作提供了基于聊天的实际中心，让客户有机会创建更加开放、流动的数字化环境。 Microsoft Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。 

Teams 属于开箱可用，它利用了 Azure Active Directory (Azure AD) 中存储的标识，并与 Office 365 中的其他服务集成在一起，可为创建的每个团队创建 SharePoint Online 网站和 Exchange Online 组邮箱。

与 Office 365 基底交互的聊天服务提供了 Teams 持久聊天功能，呈现了许多 Office 365 内置功能，例如，对 Teams 中交换的数据进行存档和电子数据展示。

Teams 还提供通话和会议体验，这些体验建立在下一代基于云的基础结构之上，而 Skype 和 Skype for Business 也使用该基础结构。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。

要扩展 Teams 功能，请使用连接器、选项卡和聊天机器人（以[应用](https://go.microsoft.com/fwlink/?linkid=854629)方式提供）以将外部信息、内容和聊天机器人交互传入 Teams。

<a name="microsoft-teams-infrastructure"></a>Microsoft Teams 基础结构
------------------------------

Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。 由 Microsoft 云提供技术支持，组织在其协作情景中利用 Teams 时，可以预见卓越性能和可靠性。

Teams 中创建的团队立即可用，创建团队时会创建 Office 365 组、SharePoint Online 网站（附带文档库）、Exchange Online 组邮箱（将由 Teams 用于存储会议邀请等信息）。 可以使用现有 Office 365 组创建团队，从而允许现有组成员身份以及 SharePoint Online 和 Exchange Online 中存储的内容转到 Teams。

与 Office 365 交互的聊天服务提供了 Teams 持久聊天功能，呈现了许多 Office 365 内置功能，例如，对 Teams 中交换的数据进行存档和电子数据展示。

为了补充作为持久聊天板的 Teams 功能（在此进行非正式的实时对话），Teams 还提供了建立在下一代基于云的基础结构（Skype 和 Skype for Business 也使用该基础结构）之上的会议体验。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。

Office 365 组利用 Azure Active Directory (Azure AD) 中存储的标识，因此，Teams 可以很容易地使用 Azure AD 中的所有身份验证和授权功能（例如，支持多重身份验证 (MFA)）。


<a name="microsoft-teams-and-office-365"></a>Microsoft Teams 和 Office 365
------------------------------

不同的组有自己的职能角色和工作方式，因此需求各不相同。 Office 365 适合每个组的独特工作方式，包含基于用途的集成应用，包括：

-   用于企业级电子邮件的 Outlook，现在具有组功能

-   用于网站和门户、智能内容服务、业务流程自动化和企业搜索的 SharePoint

-   用于推动公司范围的连接的 Yammer

-   作为企业语音和视频的主干网的 Skype for Business

-   以及现在的 Microsoft Teams，这是 Office 365 中基于聊天的新型工作区

下面是 Office 365 中每个应用的常见用例。 有关详细的使用指导，请访问 [FastTrack 生产力库](https://go.microsoft.com/fwlink/?linkid=854630)。

![Microsoft Teams 图标。](media/Overview_of_Microsoft_Teams_image1.png)

-   由希望与同一组用户实时协作的用户和团队利用。

-   对希望快速对项目进行重复操作同时共享文件并对共享交付物进行协作的团队提供帮助。

-   让希望将各种工具连接到其工作区（例如 Planner、Power BI、GitHub 等）的用户达到目的。

![Microsoft Outlook 图标。](media/Overview_of_Microsoft_Teams_image2.png)

-   由更希望以熟悉的电子邮件环境和/或更加正式的结构化方式协作的用户利用。

-   提供特定的业务流程，这些业务流程要求使用电子邮件在企业边界内部和外部传输文档和信息。

-   与直接工作组或组织外部的用户沟通和联系。

![Yammer 图标。](media/Overview_of_Microsoft_Teams_image3.png)

-   用于协助连接跨组织的用户以围绕实践社区进行组织以及共享最佳做法。

-   通过基于供给的开放式透明平台改进跨职能的工作流

-   通过领导与较广泛的员工群体之间的双向对话，加强高层-员工交流。

-   激励你的一线员工分享和接收知识和专业技能

![Skype for Business 图标。](media/Overview_of_Microsoft_Teams_image4.png)

-   用于在内部和外部与客户/合作伙伴实时通信与协作。

-   为小型或大型团队（包括最多有 10,000 位参与者的企业员工大会）提供包含音频、视频和内容的会议。

-   提供企业电话服务功能。


![Microsoft SharePoint 图标。](media/Overview_of_Microsoft_Teams_image5.png)

-   用于网站和门户（例如，公司新闻和公告、搜索和文档协作）。

-   通过集成 Microsoft Flow 和 PowerApps 对文档库和信息列表实施业务流程自动化。

-   每个 Microsoft 团队都自动预配了功能完善的 SharePoint 团队网站，用于文件存储、团队新闻、页面以及列表等。

-   请参阅 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](SharePoint-OneDrive-interact.md)

## <a name="teams-known-issuesknown-issuesmd"></a>[Teams 已知问题](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[Teams 客户端发行说明](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a>Teams 管理员 FAQ 发生了什么情况？

虽然我们首次发布 Teams 时 Teams 管理员 FAQ 使用起来很方便，但它很快变成了“杂物抽屉”，使得很难找到特定内容。 因此，我们将 FAQ 拆分开，并将其有用信息合并到你现在看到的 Teams 文档中。 你将在此文档的上下文中找到以前属于 FAQ 中的所有信息。

如果你遇到在此找不到的信息，请在下面的“**评论**”部分中告诉我们。 我们会尽力在 24 小时内回复你的评论。

顺便提一下，我们仍**提供**了针对[从 Skype for Business 到 Microsoft Teams 的旅程](FAQ-journey.md)的 FAQ。 