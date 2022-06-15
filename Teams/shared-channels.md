---
title: Microsoft Teams 中的共享频道
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用和管理共享频道。
ms.openlocfilehash: 11abe6245dea7ee72bc2f71b412addbed5aa6e30
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057052"
---
# <a name="shared-channels-in-microsoft-teams"></a>Microsoft Teams 中的共享频道

Microsoft Teams 中的共享频道可创建协作空间，你可以在其中邀请部署于团队的人员。 仅具有共享频道所有者或成员身份的用户可以访问该频道。 虽然无法将来宾（组织中具有 Azure Active Directory 来宾帐户的人员）添加到共享频道，但可通过使用 Azure AD B2B 直接连接邀请组织外部人员参与共享频道。

如果希望与一组属于不同团队成员的人员进行协作，则可能需要使用共享频道。 例如，工程、销售和支持人员均在同一项目或产品的不同方面工作，他们可以使用共享渠道进行协作。

只有共享频道的成员才能查看和参与将他们添加到的共享频道。 共享频道连接到的团队的其他成员将看不到该频道。

创建共享频道后，该频道将链接到父级团队，并且无法移动到其他团队。 此外，共享频道无法转换为标准频道，反之亦然。

[比较共享频道和其它类型的频道](/microsoftteams/teams-channels-overview#channel-feature-comparison)。

## <a name="getting-started-with-shared-channels"></a>共享频道入门

共享频道在 Teams 中默认启动。你可以选择用户是否可以创建共享频道、他们是否可以与组织外部的人员共享该频道，以及他们是否可以通过 [创建频道策略](/MicrosoftTeams/teams-policies) 来参与外部共享频道。

如果计划与组织外部人员共享频道，请阅读 [计划外部协作](/microsoft-365/solutions/plan-external-collaboration) 以了解重要的规划注意事项。

与组织外部的人员共享频道还需要在 Azure AD 中配置跨租户访问设置。 要与之共享频道的每个组织也必须完成此配置。 有关详细信息，请参阅 [与频道中的外部参与者进行协作](/microsoft-365/solutions/collaborate-teams-direct-connect)。

## <a name="shared-channel-creation"></a>共享频道创建

只有团队所有者才能创建共享频道。 团队成员和来宾无法创建共享频道。 可以在组织级别管理创建共享频道的功能。 使用 [策略](teams-policies.md) 控制允许组织中的哪些用户可以创建共享频道。

创建共享频道的人员将成为共享频道所有者，并且只有共享频道所有者可以直接在其中添加或删除人员。 （如果需要，可以添加多个所有者。）共享频道所有者可以将组织中的任何人添加到他们创建的共享频道。 共享频道的成员具有安全的对话空间，添加新成员后，他们可以查看该共享频道中的所有对话（甚至是旧对话）。

团队所有者可以查看其团队中所有共享频道的名称，也可以删除该团队中的任何共享频道。 团队所有者无法查看共享频道中的文件或共享频道的对话和成员列表，除非他们是该共享频道的成员。

团队成员只能看到已将其添加到的共享频道。

克隆团队将不会克隆关联的共享频道。

## <a name="shared-channel-deletion"></a>共享频道删除

删除的共享频道可以在删除后 30 天内还原。 还原已删除的共享频道后，将还原所有以前的成员身份（个人和团队共享）。

删除的团队可以在删除后 30 天内还原。 删除团队后，也将删除所有共享频道。 还原已删除的团队后，也将还原所有共享频道以及所有共享关系。

存档团队后，个人共享将保持不变，但将删除与父团队以外的团队的共享。 当存档的团队未存档时，所有共享频道将仅通过单个共享进行还原。

## <a name="adding-and-removing-owners-and-members"></a>添加和删除所有者和成员

如果共享频道所有者是一个或多个共享频道的最后一个所有者，则无法通过 Teams 客户端将其删除。

如果共享频道所有者离开组织，或者从与团队关联的 Microsoft 365 组中被删除，则将自动提升一名共享频道成员成为共享频道所有者。请考虑添加一位以上所有者以预防此情况。

## <a name="channel-owner-settings"></a>频道所有者设置

每个共享频道都具有自己的可以由频道所有者管理的设置，包括面向整个频道的添加和删除成员、添加选项卡以及 @提及功能。 这些设置独立于父团队设置。 创建共享频道时，该频道将继承父级团队的设置，之后可以独立于父级团队设置更改其设置。

共享频道所有者可以单击“**管理频道**”，然后使用“**成员**”和“**设置**”选项卡来添加或删除成员以及编辑设置。

## <a name="shared-channel-owner-and-member-actions"></a>共享频道所有者和成员操作

下表概述了所有者、成员和来宾可以在共享频道中执行的操作。

|操作  |团队所有者|团队成员|团队来宾|共享频道所有者|共享频道成员|共享频道外部参与者|
|---------|---------|---------|---------|---------|---------|---------|
|创建共享频道|管理员控制|管理员和团队所有者控制|否|不适用|否|否|
|删除共享频道|是|否|否|是|否|否|
|退出共享频道|不适用|不适用|不适用|是，除非他们最后一次拥有|是|是|
|编辑共享频道|否|不适用|不适用|是|否|否|
|还原已删除的共享频道|是|否|否|是|否|否|
|添加成员|否|不适用|不适用|是|否|否|
|编辑设置|否|不适用|不适用|是|否|否|
|管理选项卡和应用|否|不适用|不适用|是，必须为团队安装应用|频道所有者控制|不支持|

## <a name="shared-channel-sharepoint-sites"></a>共享频道 SharePoint 网站

每个共享频道都有 [自己的 SharePoint 网站](/SharePoint/teams-connected-sites)。 单独的网站用于确保只有共享频道成员才能有权访问共享频道文件。 默认情况下，这些网站集是使用文档库创建的，并且可通过[网站管理界面](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04)轻松增强为功能齐全的网站集。 每个网站创建在与父团队网站相同的地理区域创建。 这些轻型网站具有自定义模板 ID“TEAMCHANNEL#0”，可通过 PowerShell 和 Graph API 实现更轻松的管理。 

共享频道网站继承父团队的敏感度标签。 即使频道直接与另一个团队共享，也是如此。

> [!NOTE]
> 只有具有频道中所有者或成员权限的人员才能访问共享频道网站中的内容。 父团队和管理员中的人员将无权访问权限，除非他们也是频道成员。

网站所有者和成员组的成员资格将与共享频道的成员资格保持同步。 无法通过 SharePoint 独立管理共享频道网站的网站权限。 

团队管理共享频道网站的生命周期。 如果网站在 Teams 外部删除，则只要共享频道仍处于活动状态，该站点就会在四小时内自动还原。 如果已永久删除该网站，则将为该共享频道预配新的网站。

如果还原了含有共享频道的共享频道或团队，则网站将随其一起还原。 如果已还原共享频道网站，并且超出了共享频道的 30 天软删除时间段，则该网站将作为独立网站运行。

## <a name="shared-channel-messages"></a>共享频道邮件

共享频道邮件存储在与共享频道（而不是组邮箱）关联的专用系统邮箱中。

有关对共享频道邮件执行电子数据展示搜索的详细信息，请参阅 [在 Microsoft Teams 中对内容进行电子数据展示调查](ediscovery-investigation.md)。

## <a name="considerations-around-file-access-in-shared-channels"></a>有关共享频道中的文件访问的注意事项

通过使用 [标准 SharePoint 文件共享](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c)，可以与频道外部的人员共享位于共享频道中的文件、文件夹和 OneNote 笔记本。

如果通过 SharePoint 向用户授予对共享频道中文件、文件夹或笔记本的访问权限，则从团队或共享频道中删除用户将不会删除用户对文件、文件夹或笔记本的访问权限。

如果将现有笔记本作为选项卡添加到共享频道，则不更改对共享频道的访问权限，且笔记本将保留其现有权限。

## <a name="resources-for-your-users"></a>为你的用户准备的资源

以下文章可能对组织中的用户在使用共享频道时有所帮助。

[在 Teams 中创建共享频道](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[与 Teams 中的人员共享频道](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[与团队共享频道](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[为什么在 Teams 中使用共享频道或其他频道类型？](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Teams 中的来宾和共享频道](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[在 Teams 中共享频道所有者和成员角色](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels"></a>共享频道的限制

下表说明了频道和成员数的上限。

|最大值...|值|注释|
|:---------|:----|:----|
|团队中的成员|25,000|包括团队中的所有用户和共享频道中的直接成员。|
|每个团队的共享频道数|200|托管并与团队共享。 （包括 30 天恢复时段内已删除的频道。）|
|可以与团队共享的频道|50|排除父级团队|
|共享频道中的成员|5,000 个直接成员，包括最多 50 个团队。 （出于此限制的目的，将与之共享频道的每个团队计作一个成员。）|实时更新一次仅对 25,000 个用户可用，并且在频道列表中仅显示 25,000 个用户。|

以下限制也适用：

- 共享频道支持除 Stream、Planner 和 Forms 以外的选项卡。

- 不支持 LOB 应用、机器人、连接器和消息扩展。

- 根据现有团队创建团队时，将不会复制现有团队中的任何共享频道。

- 错过的活动电子邮件中不包含来自共享频道的通知。

## <a name="supported-apps-in-shared-channels"></a>共享频道中支持的应用

有关如何为共享频道准备应用的信息，请参阅[如何开放应用以通过 Microsoft Teams Connect 进行跨组织协作](https://mybuild.microsoft.com/sessions/4d84d73c-08de-4f56-990b-2a73b2037df1)。

共享频道中支持使用以下应用。 

- 活动
- Adobe Acrobat Sign
- Asana
- 日历
- Calendar Pro
- 通话
- 聊天
- Code by Vivani
- Conceptboard
- Excel
- FileBrowser
- 文件
- Flipgrid
- Freehand by InVision
- HeyTaco
- Jira Cloud
- Kahoot！
- 列表
- Lucidchart
- Lumio
- MeisterTask
- MindMeister
- Mindomo
- Miro
- Monday.com
- MURAL
- Nearpod
- OneNote
- PDF
- Pear Deck
- PowerPoint
- Priority Matrix
- Quicklinks
- Quizlet
- Saved
- Scrum-Poker
- 搜索
- SharePoint
- SharePoint Pages
- Slido
- Smartsheet
- SurveyMonkey
- Tasks in a Box
- Teams
- Teams Manager
- TeamViewer
- 团队合作
- Testportal
- TrackingTime
- Trello
- Vevox
- Visio
- VSTS
- Wakelet
- Web
- Wooclap
- Word
- YouTube
- Zendesk
- Zoho Projects

## <a name="related-topics"></a>相关主题

[B2B 直接连接概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[配置 B2B 直接连接的跨租户访问设置](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Teams 中的团队和频道概述](teams-channels-overview.md)

[Microsoft Teams 中的私人频道](/microsoftteams/private-channels)
