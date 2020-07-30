---
title: 由 Microsoft Graph 构建的中小型企业的团队模板
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
description: 使用 microsoft Graph 中内置的预定义模板快速轻松地为中小型企业创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9807e7f3694731af398abd83189698420ec36b8a
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506145"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Microsoft Graph 中为中小型企业构建的团队模板

Microsoft 团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。

对于小型企业和中型企业，模板非常强大，因为它们有助于管理员在其组织中快速部署团队。 模板还有助于为用户调整方向，并开始有效地使用团队。 本文适用于你负责在你的组织中规划、部署和管理多个团队的情况。

我们目前提供三个第一方的 SMB 模板，您可以利用这些模板在各种情况下使用。 所有模板都将创建*专用*团队。 创建团队并准备好向组织推出后，您可以根据需要将隐私设置为*组织范围*或*公共*。 若要深入了解有关团队模板的详细信息，请参阅[团队模板入门](get-started-with-teams-templates.md)。

## <a name="company-wide-template"></a>公司范围的模板
公司范围的模板适用于与整个公司相关的通信和协作。 您可以将常规频道用于公司范围内的公告、行业新闻或执行公告。 人力资源频道是整合所有与人力资源相关的活动（如作业发布、新员工加入、培训和开发）的绝佳位置。 有趣内容频道为所有随机和有趣的文章提供了社交平台。

| 基本模板类型  | baseTemplateId | 此基本模板附带的属性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| 中小型 <br>公司范围 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 频道 <ul><li>常规\*</li><li>人力资源\*</li><li>有趣的资料\*</li></ul><br> 应用<ul><li>公司门户（固定到**人力资源**频道的网站） </li> </UL><br>团队属性 <ul><li>将团队可见性设置为私密</li></ul> |

* 自动收藏频道 

若要通过从预定义的模板中获取默认值来创建公司范围的团队，请在请求正文中提供团队对象的 JSON 表示形式。 若要了解有关如何部署团队模板的详细信息，请参阅 Microsoft Graph[文章创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

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

## <a name="executive-team-template"></a>管理层团队模板

执行官团队模板非常适合于为公司主管创建团队，以便与年度优先级、财务预算、战略计划、热门客户等公司计划进行沟通和协作。此模板附带了一个*专用*频道，用于邀请选择特定主题的用户。

| 基本模板类型  | baseTemplateId | 此基本模板附带的属性 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| 中小型 <br>主管团队 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 频道 <ul><li>常规\*</li><li>专有\*</li></ul> 应用<ul><li>OneNote （已固定到**专用**频道）</li> <li>Planner （已固定到**专用**频道） </li></ul><br>团队属性 <ul><li>将团队可见性设置为私密</li></ul> | 

* 自动收藏频道<br>

若要通过从预定义的模板中获取默认设置来创建主管团队，请在请求正文中提供团队对象的 JSON 表示形式。 若要了解有关如何部署团队模板的详细信息，请参阅 Microsoft Graph[文章创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

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

部门团队模板可用于为单个部门或项目创建团队。 "财务" 团队模板非常适合于财务团队成员中的所有文章、公告和日常协作以及沟通以及管理团队成员（根据需要）。 该模板附带了一个*专用*频道，用于邀请选择特定主题的用户。 我们还为 "财务" 团队提供了以下脚本，可用于将模板扩展到其他部门或特定项目，方法是添加、删除或编辑特定项目。 例如，如果您有一个*市场营销*部门，则可以通过将团队从*财务*部门重命名为 "*市场营销*" 来调整该脚本，以创建新的市场营销团队

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| 中小型 <br>财务  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 频道 <ul><li>常规\*</li><li>专有\*</li></ul><br> 应用<ul><li>OneNote （已固定到**专用**频道）</li> <li>Planner （已固定到**专用**频道） </li> </ul><br>团队属性 <ul><li>将团队可见性设置为私密</li></ul> | 

* 自动收藏频道

若要通过从预定义的模板中获取默认值来创建财务团队，请在请求正文中提供团队对象的 JSON 表示形式。 若要了解有关如何部署团队模板的详细信息，请参阅 Microsoft Graph[文章创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

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

### <a name="example-finance-team-template-extension-script"></a>示例： "财务" 团队模板扩展脚本

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

- [开始使用 Teams 模板](get-started-with-teams-templates.md)
- [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在预览中）

