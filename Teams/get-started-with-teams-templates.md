---
title: 工作组模板入门
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: 了解如何使用团队模板来创建工作组使用预定义的通道。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801461"
---
# <a name="get-started-with-teams-templates"></a>工作组模板入门 

工作组模板是预建的团队的结构围绕业务需要或项目设计的定义。 工作组模板可用于快速使用不同的主题的通道创建丰富的协作空格和预安装应用程序提取在任务关键型内容和服务。 工作组模板提供可帮助您轻松地在整个组织中创建一致的团队的预定义的团队结构。 

本文中，我们将介绍可以在模板类型是，哪些基本模板定义的属性和如何使用了几个示例请求从模板创建工作组。
 
本文适用于您，如果您是：

- 负责规划、 部署和管理您的组织内的多个团队<br>
- 开发人员希望以编程方式使用预定义的通道和应用程序创建团队 

## <a name="teams-template-capabilities"></a>工作组模板功能

包含和模板的支持团队中的大多数属性。 但有一些属性，当前不支持的功能。 下表提供了包含的组件和工作组模板中不包含内容的快速摘要。

| **支持的工作组模板的团队属性** | **尚未支持的工作组模板的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 通道设置 |
| 工作组可见性 （公共或专用） | 连接器 |
| 团队设置 （例如，成员、 来宾，@ 提及） | 文件和内容 |
| 自动收藏夹通道 | |
| 已安装应用程序 | |
| 固定的选项卡 | | 

> [!NOTE]
> 我们将为添加更多模板功能的将来版本中的 Microsoft 团队，因此检查返回有关支持的属性的最新信息。

## <a name="what-are-base-template-types"></a>基本模板类型是什么？

基本模板类型是 Microsoft 创建针对特定行业的特殊模板。 这些基本模板通常包含在尚不支持分别在工作组模板中存储和团队属性中不可用的专用应用程序。

定义基本模板类型后，您可以扩展或重写这些特殊模板与您想要指定的其他属性。 但某些基本模板类型包含不能重写的属性。 

默认情况下基本模板设置为**标准**其不包含任何其他专用应用程序或特殊属性。 下面是可用的基本模板类型的当前列表。

| 基本模板类型 | baseTemplateId | 基本模板专用应用程序和特殊属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | 没有其他应用程序和属性 |
| 培训- <br>类工作组<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | 应用程序：<ul><li>OneNote 类笔记本 （固定到**常规**选项卡） </li><li>分配应用程序 （固定到**常规**选项卡）</li></ul> 团队属性：<ul><li>工作组可见性设置为**HiddenMembership** （不能重写）</li></ul> |
| 培训-<br>员工工作组<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | 应用程序：<ul><li>OneNote 员工笔记本 （固定到**常规**选项卡）</li></ul> |
|培训-<br>PLC 团队 |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | 应用程序：<ul><li>OneNote PLC 笔记本 （固定到**常规**选项卡）</ul></li>|
|||

<sup>1</sup>出版物中后期年 10 月，2018

> [!NOTE]
> 我们将添加更多基本模板类型在将来版本的 Microsoft 团队，因此请检查以便获得最新信息支持属性。

## <a name="examples"></a>示例 

您可以开始使用模板创建工作组使用[Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

### <a name="create-a-team-from-a-template"></a>从模板创建工作组

#### <a name="requests"></a>请求

**使用标准的基本模板创建团队的请求**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

**请求创建额外的通道团队和禁止从删除通道的成员**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

**请求创建工作组使用所有受支持的属性**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a>获取状态

#### <a name="request"></a>请求

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>响应

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>相关主题

- [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在预览）
- [新团队](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams 管理培训](itadmin-readiness.md)