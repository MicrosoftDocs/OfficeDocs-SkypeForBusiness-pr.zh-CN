---
title: Microsoft Teams 概述
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 了解 Microsoft Teams、其基础结构以及如何配合使用 Teams 与 Office 365。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb291c8bd338fa88d5d9b5788413c5e687fc0864
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883776"
---
<a name="overview-of-microsoft-teams"></a>Microsoft Teams 概述
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


Microsoft Teams 结合了 Office 365 的完整宽度和深度，为团队合作提供了基于聊天的实际中心，让客户有机会创建更加开放、流动的数字化环境。 Microsoft Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。 

Teams 属于开箱可用，它利用了 Azure Active Directory (Azure AD) 中存储的标识，并与 Office 365 中的其他服务集成在一起，可为创建的每个团队创建 SharePoint Online 网站和 Exchange Online 组邮箱。

具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以作为来宾团队中参与。 团队中的所有来宾都涵盖的相同的遵从性和 Office 365 的其余部分的审核保护并来宾可以安全地管理 Azure AD 中。 管理员可以集中管理来宾其 Office 365 环境中的参与如何和轻松地查看、 添加或取消对主机租户来宾访问权限。

Teams 提供持久聊天功能、通话和会议、快速访问 Office 365 其他组件的功能以及强大的扩展功能。  它提供了一个适用于大型公司、小型组织及其所有成员的团队合作中心。  

要扩展 Teams 功能，请使用连接器、选项卡和聊天机器人（以[应用](https://go.microsoft.com/fwlink/?linkid=854629)方式提供）以将外部信息、内容和聊天机器人交互传入 Teams。  

<a name="microsoft-teams-infrastructure"></a>Microsoft Teams 基础结构
------------------------------

Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。 由 Microsoft 云提供技术支持，组织在其协作情景中利用 Teams 时，可以预见卓越性能和可靠性。

Teams 中创建的团队立即可用，创建团队时会创建 Office 365 组、SharePoint Online 网站（附带文档库）、Exchange Online 组邮箱（将由 Teams 用于存储会议邀请等信息）。 可以使用现有 Office 365 组创建团队，从而允许现有组成员身份以及 SharePoint Online 和 Exchange Online 中存储的内容转到 Teams。

若要为多个持久聊天主板其中非正式、 实时对话进行，也团队补充团队功能提供呼叫和会议体验的下一个生成基于云的基础结构还使用 Skype 和 Skype 的构建业务。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。

Office 365 组利用 Azure Active Directory (Azure AD) 中存储的标识，因此，Teams 可以很容易地使用 Azure AD 中的所有身份验证和授权功能（例如，支持多重身份验证 (MFA)）。

> [!NOTE]
> 根据客户反馈，由于 Microsoft 团队在创建团队生成的新 Office 365 组将不再显示在 Outlook 中默认情况下。 对于要继续在 Outlook 中显示这些组的现有行为的客户，将其可以启用 Outlook 体验的组提供 Exchange Online PowerShell cmdlet。 组创建通过 Outlook 和更高版本启用团队将继续要显示在 Outlook 和团队。 此更新将逐步执行跨 Outlook 和团队滚月。


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

-   允许用户连接到其工作区 （如规划器、 Power BI、 GitHub 等） 的各种工具。

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


