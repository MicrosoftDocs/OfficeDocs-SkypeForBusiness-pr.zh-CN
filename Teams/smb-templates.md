---
title: 使用 Microsoft Graph 构建的中小型企业团队模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 使用 Microsoft Graph 中内置的 Microsoft Teams 预定义模板，快速轻松地为中小型企业创建团队。
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: 85f1573cb93f5362dc046ab97e2ac621f147fe4a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198714"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>在适用于中小型企业的 Microsoft Graph 中构建的团队模板

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于中小型企业，模板可能特别强大，因为它们可以帮助你在组织中快速部署 Teams。 模板还帮助用户了解如何有效使用 Teams。 如果你负责规划、部署和管理组织中的多个团队，则本文适合你。

我们目前为中小型企业提供了三个预构建的模板，可用于各种情况。 所有模板创建 *专用* 团队。 创建团队并准备好向组织推出后，可以根据需要将隐私设置为 *“组织范围* ”或 *“公共*”。

> [!NOTE]
> 还可以使用 Microsoft Graph 创建自己的自定义模板。 若要了解详细信息，请参阅 [teamTemplate 资源类型](/graph/api/resources/teamtemplate)。

若要了解有关团队模板的一般信息，请参阅[使用 Microsoft Graph 开始使用团队模板](get-started-with-teams-templates.md)。

## <a name="company-wide-template"></a>Company-Wide模板

Company-Wide模板用于整个公司的通信和协作。 可以使用“常规”频道发布公司范围的公告、行业新闻或高管职位。 人力资源渠道是整合所有人力资源相关活动（如职位、新员工入职、培训和开发）的好地方。 Fun Stuff 频道为所有随机和有趣的帖子提供了一个社交平台。

| 模板类型  | TemplateId | 此基本模板包含的属性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Smb- <br>公司范围 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 频道 <ul><li>常规\*</li><li>人力资源\*</li><li>有趣的内容\*</li></ul><br> 应用<ul><li>公司门户 (网站固定到 **人力资源** 频道)  </li> </UL><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> |

*自动收藏的频道 

若要通过从预定义模板中获取默认设置来创建Company-Wide团队，请在请求正文中提供团队对象的 JSON 表示形式。 若要详细了解如何部署团队模板，请参阅[有关创建团队](/graph/api/team-post?view=graph-rest-beta&preserve-view=true)的 Microsoft Graph 一文。

#### <a name="request"></a>请求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>高管团队模板

“管理团队”模板非常适合创建一个团队，供公司高管就年度优先事项、财政预算、战略计划和顶级客户等公司计划进行沟通和协作。 此模板附带一个 *专用* 频道，用于邀请特定主题的选定用户。

| 模板类型  | TemplateId | 此基本模板包含的属性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Smb- <br>高管团队 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 频道 <ul><li>常规\*</li><li>私人 \*</li></ul> 应用<ul><li>OneNote (固定到 **专用** 频道) </li> <li>Planner (固定到 **专用** 频道)  </li></ul><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> | 

*自动收藏的频道<br>

若要通过从预定义模板获取默认设置来创建高管团队，请在请求正文中提供团队对象的 JSON 表示形式。 若要详细了解如何部署团队模板，请参阅[有关创建团队](/graph/api/team-post?view=graph-rest-beta&preserve-view=true)的 Microsoft Graph 一文。

#### <a name="request"></a>请求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>部门团队模板

部门团队模板可用于为单个部门或项目创建团队。 财务团队模板非常适合财务团队成员和执行团队成员内部的所有帖子、公告以及日常协作和沟通。 该模板附带一个 *专用* 频道，用于邀请特定主题的特定用户。

我们还为财务团队提供以下脚本，这些脚本可用于通过添加、删除或编辑自己的喜好，将模板扩展到其他部门或特定项目。 例如，如果你有 *一个营销* 部门，则可以通过将团队从 *财务* 重命名为 *Marketing* 来修改脚本，以创建新的营销团队

| 模板类型 | TemplateId | 此基本模板包含的属性 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| Smb- <br>财务  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 频道 <ul><li>常规\*</li><li>私人 \*</li></ul><br> 应用<ul><li>OneNote (固定到 **专用** 频道) </li> <li>Planner (固定到 **专用** 频道)  </li> </ul><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> | 

*自动收藏的频道

若要通过从预定义模板获取默认设置来创建财务团队，请在请求正文中提供团队对象的 JSON 表示形式。 若要详细了解如何部署团队模板，请参阅[有关创建团队](/graph/api/team-post?view=graph-rest-beta&preserve-view=true)的 Microsoft Graph 一文。

#### <a name="request"></a>请求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>示例：财务团队模板扩展脚本

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>相关主题

- [在管理中心内开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)
- [开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)
- 以预览版) [创建团队](/graph/api/team-post?view=graph-rest-beta&preserve-view=true) (
