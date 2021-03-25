---
title: 使用 Microsoft Graph 构建的中小型企业的 Teams 模板
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 使用 Microsoft Graph 中内置的 Microsoft Teams 预定义模板快速轻松地为中小型企业创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116990"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Microsoft Graph 中为中小型企业构建的 Teams 模板

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于中小型企业，模板可能特别强大，因为它们可帮助管理员在整个组织中快速部署 Teams。 模板还有助于确定用户方向并开始有效使用 Teams。 如果你负责在整个组织中规划、部署和管理多个团队，则本文适合你。

我们目前提供三个可用于各种情况的第一方 SMB 模板。 所有模板都将创建 *专用* 团队。 创建 Teams 并准备好向组织推出后，可适当地将隐私设置为 *"组织* 范围"或"公共"。  要总体上了解有关团队模板的详细信息，请参阅 [开始使用 Teams 模板](get-started-with-teams-templates.md)。

## <a name="company-wide-template"></a>Company-Wide模板
Company-Wide模板适用于与整个公司相关的通信和协作。 您可以使用"常规"频道进行公司范围的公告、行业新闻或高管文章。 人力资源渠道是整合所有人力资源相关活动（如职位、新员工入职、培训和开发）的一个不错位置。 "有趣内容"频道提供一个社交平台，供所有随机和有趣的帖子使用。

| 基本模板类型  | baseTemplateId | 此基本模板包含的属性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>公司范围内 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 频道 <ul><li>常规\*</li><li>人力资源\*</li><li>有趣的内容\*</li></ul><br> 应用<ul><li>公司门户 (网站固定到 **人力资源** 频道)  </li> </UL><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> |

*自动收藏的频道 

若要通过Company-Wide模板中的默认值创建团队，在请求正文中提供团队对象的 JSON 表示形式。 若要详细了解如何部署 Teams 模板，请参阅有关创建团队的 Microsoft Graph [文章](/graph/api/team-post?view=graph-rest-beta)。

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

## <a name="executive-team-template"></a>执行团队模板

"执行团队"模板非常适合创建一个团队，供公司主管就年度优先级、预算、战略计划以及顶级客户等公司计划进行沟通和协作。 此模板附带一个 *专用* 通道，用于邀请特定主题的选定用户。

| 基本模板类型  | baseTemplateId | 此基本模板包含的属性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>高管团队 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 频道 <ul><li>常规\*</li><li>专用 \*</li></ul> 应用<ul><li>OneNote (已固定到"专用 **"** 频道) </li> <li>Planner (固定到"专用 **"** 频道)  </li></ul><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> | 

*自动收藏的频道<br>

若要通过采用预定义模板中的默认值创建高层团队，在请求正文中提供团队对象的 JSON 表示形式。 若要详细了解如何部署 Teams 模板，请参阅有关创建团队的 Microsoft Graph [文章](/graph/api/team-post?view=graph-rest-beta)。

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

部门团队模板可用于为各个部门或项目创建团队。 财务团队模板非常适合财务团队成员和高层团队成员内部的所有帖子、公告以及日常协作和通信。 该模板附带一个 *专用* 通道，用于邀请特定主题的选定用户。 我们还为财务团队提供以下脚本，该脚本可用于通过添加、删除或编辑来将模板扩展到其他部门或特定项目。 例如，如果您有 *营销部门，* 则可以通过将团队从 Finance 重命名为 *Marketing* 来修改脚本，以创建新的市场营销团队

| 基本模板类型 | baseTemplateId | 此基本模板包含的属性 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>财务  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 频道 <ul><li>常规\*</li><li>专用 \*</li></ul><br> 应用<ul><li>OneNote (已固定到"专用 **"** 频道) </li> <li>Planner (固定到"专用 **"** 频道)  </li> </ul><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> | 

*自动收藏的频道

若要通过采用预定义模板中的默认值创建财务团队，在请求正文中提供团队对象的 JSON 表示形式。 若要详细了解如何部署 Teams 模板，请参阅有关创建团队的 Microsoft Graph [文章](/graph/api/team-post?view=graph-rest-beta)。

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

- [管理员控制台中的 Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)
- [Teams 模板入门](get-started-with-teams-templates.md)
- [在预览](/graph/api/team-post?view=graph-rest-beta) (创建团队) 