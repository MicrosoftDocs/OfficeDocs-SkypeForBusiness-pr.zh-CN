---
title: 在 Microsoft 团队中管理专用频道的生命周期
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
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
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理组织中专用频道的生命周期。
ms.openlocfilehash: 0f4f4d21adcb73731c8d0218a7b776c0aacbc7da
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012288"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>在 Microsoft 团队中管理专用频道的生命周期

在这里，你将找到管理你的组织中的[专用频道](private-channels.md)的生命周期所需的指南。

> [!IMPORTANT]
> 如果你使用本文中的 PowerShell 步骤管理专用通道，则必须从[Powershell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/)安装并使用团队 PowerShell 公共预览版模块。 有关如何安装该模块的步骤，请参阅[安装 Microsoft 团队 PowerShell](teams-powershell-install.md)。 最新的常规可用性团队 PowerShell 模块不支持管理专用通道。

## <a name="set-whether-team-members-can-create-private-channels"></a>设置团队成员是否可以创建专用频道

团队所有者可以关闭或打开成员在团队设置中创建专用频道的功能。 若要执行此操作，请在团队的 "**设置**" 选项卡上，关闭或打开 "**允许成员创建专用频道**"。

作为管理员，你可以使用 Graph API 控制成员是否可以在特定团队中创建专用通道。 下面是一个示例。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>设置组织中的用户是否可以创建专用频道

作为管理员，你可以使用 Microsoft 团队管理中心或 PowerShell 来设置策略，以控制允许组织中的哪些用户创建专用通道。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

使用团队策略设置允许组织中的哪些用户创建专用频道。 若要了解详细信息，请参阅[管理团队中的团队策略](teams-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell

使用**CsTeamsChannelsPolicy**设置允许组织中的哪些用户创建专用频道。 将**AllowPrivateChannelCreation**参数设置为**true** ，以允许分配了该策略的用户创建专用频道。 将该参数设置为**false**将关闭为分配了该策略的用户创建专用通道的功能。

若要了解详细信息，请参阅[CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表团队所有者创建专用频道

作为管理员，你可以使用 PowerShell 或 Graph API 代表团队所有者创建专用通道。 例如，如果您的组织想要集中创建专用频道，您可能需要执行此操作。

### <a name="using-powershell"></a>使用 PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>使用图形 API

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>获取所有专用信道消息的列表

您可能希望获取在专用频道中发布的所有邮件和答复的列表，以便存档和审核。  下面介绍了如何使用 Graph API 执行此操作。

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>查找团队中所有专用通道的 SharePoint Url

无论是要针对专用频道中的文件执行电子数据展示或法律封存，还是希望构建一个自定义应用来将文件放入特定的专用通道中，你将需要一种方法来查询为每个专用通道创建的唯一 SharePoint 网站集。

作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。

### <a name="using-powershell"></a>使用 PowerShell

1. 通过管理员帐户安装和连接到[SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 。
2. 运行以下，其中 &lt; group_id &gt; 是团队的组 id。 （您可以轻松地在与团队的链接中找到组 ID。）

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>使用图形 API

你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。

1. 使用以下操作获取给定团队的专用通道 Id 的列表，其中 <group_id> 是团队的组 ID。 您将在后续通话中需要此内容。 （您可以轻松地在与团队的链接中找到组 ID）。

    **请求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **响应**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. 对于要获取 SharePoint URL 的每个专用通道，请执行以下请求，其中 &lt; channel_id &gt; 是通道 id。

    **请求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **响应**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>在专用通道中列出和更新所有者和成员的角色

你可能希望列出专用通道的所有者和成员，以确定是否需要将专用通道的某些成员提升为所有者。 如果您拥有已离开组织的专用频道的所有者，并且专用频道需要管理员帮助来声明频道所有权，则可能会发生这种情况。

作为管理员，你可以使用 Microsoft 团队管理中心、PowerShell 或图形 API 来执行这些操作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

若要了解如何使用 Microsoft 团队管理中心管理团队成员，请参阅[管理 Microsoft 团队管理中心中的团队](manage-teams-in-modern-portal.md)。

### <a name="using-powershell"></a>使用 PowerShell

1. 运行以下，其中 &lt; group_id &gt; 是团队的组 id， &lt; channel_name &gt; 是信道名称。

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. 将成员提升为所有者。

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>使用图形 API

你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。

1. 使用以下，其中 &lt; group_id &gt; 是团队的组 id， &lt; CHANNEL_ID &gt; 是信道 id。

    **请求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **响应**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. 使用以下将成员提升为所有者，其中 &lt; group_id &gt; 、 &lt; channel_id &gt; 和 &lt; id &gt; 从以前的调用中返回。 请注意 &lt; ， &gt; &lt; &gt; 从以前的调用返回的 id 和 userId 不相同，并且不能互换。 请确保使用 &lt; id &gt; 。

    **请求**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **响应**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [将 Microsoft Graph API 与 Teams 结合使用](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [列出频道](https://docs.microsoft.com/graph/api/channel-list)
    - [创建频道](https://docs.microsoft.com/graph/api/channel-post)
    - [向频道添加成员](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [更新频道中的成员](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [从频道中删除成员](https://docs.microsoft.com/graph/api/conversationmember-delete)
