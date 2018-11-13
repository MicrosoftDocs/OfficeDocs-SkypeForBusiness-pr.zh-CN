---
title: 工作组模板入门
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295004"
---
# <a name="get-started-with-teams-templates"></a>工作组模板入门 

工作组模板是预建的团队的结构围绕业务需要或项目设计的定义。 工作组模板可用于快速使用不同的主题的通道创建丰富的协作空格和预安装应用程序提取在任务关键型内容和服务。 工作组模板提供可帮助您轻松地在整个组织中创建一致的团队的预定义的团队结构。 

本文中，我们将介绍可以在模板类型是，哪些基本模板定义的属性和如何使用了几个示例请求从模板创建工作组。
 
本文适用于您，如果您是：

• 负责规划、 部署和管理跨组织 • 为开发人员的多个团队希望创建与工作组预定义通道和应用程序以编程方式

## <a name="team-template-capabilities"></a>工作组模板功能

包含和模板的支持团队中的大多数属性。 但是，有几个属性，当前不支持的功能。 下表提供了包含的组件和工作组模板中不包含内容的快速摘要。

| **支持的工作组模板的团队属性** | **尚未支持的工作组模板的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 频道设置 （例如，自动收藏夹和隐私） |
| 工作组可见性 （公共或专用） | 连接器 |
| 团队设置 （例如，成员、 来宾，@ 提及） | 文件和内容 |
| 自动收藏夹通道 | |
| 已安装应用程序 | |
| 固定的选项卡 | | 

> [!NOTE]
> 我们将为添加更多模板功能的将来版本中的 Microsoft 团队，因此检查返回有关支持的属性的最新信息。

## <a name="what-are-base-template-types"></a>基本模板类型是什么？

基本模板类型是 Microsoft 创建针对特定行业的特殊模板。 这些基本模板通常包含在尚未在工作组模板支持单独的存储和团队属性中不可用的专用应用程序。

定义基本模板类型后，您可以扩展或重写这些特殊模板与您想要指定的其他属性。 但是，某些基本模板类型包含不能重写的属性。 

默认情况下基本模板设置为**标准**其不包含任何其他专用应用程序或特殊属性。 下面是可用的基本模板类型的当前列表。

| 基本模板类型 | baseTemplateId | 基本模板专用应用程序和特殊属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | 没有其他应用程序和属性 |
| 医疗保健-护理协调 | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | 应用程序：<br/> -患者应用程序 （固定到**常规**选项卡）<br/> <br/>频道： <br/> -通知<br/> -糖尿病<br/> -心血管<br/> -已注册护理 |
| 医疗保健-过程 huddle | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | 频道：<br/> -避免辅<br/> -Mortality 审阅 <br/> -阻止降到 <br/> -Sepsis 计划 |
| 教育-类工作组<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | 应用程序：<br/> -OneNote 类笔记本 （固定到**常规**选项卡） <br/> -分配应用程序 （固定到**常规**选项卡） <br/><br/> 团队属性 <br/> 团队可见性设置为**HiddenMembership** （不能重写） |
| 培训-员工团队<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | 应用<br/> -OneNote 员工笔记本 （固定到**常规**选项卡） |

<sup>1</sup>出版物中后期年 10 月，2018

> [!NOTE]
> 我们将添加更多基本模板类型在将来版本的 Microsoft 团队，因此请检查以便获得最新信息支持属性。

## <a name="examples"></a>示例 

您可以开始通过安装[Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview)中创建模板通过团队。

### <a name="create-a-team-from-a-template"></a>从模板创建工作组

#### <a name="requests"></a>请求

**使用标准的基本模板创建团队的请求**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**请求创建额外的通道团队和禁止从删除通道的成员**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**请求创建工作组使用所有受支持的属性**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>响应

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
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

- [创建团队](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams)（在预览）
- [新团队](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams 管理培训](itadmin-readiness.md)