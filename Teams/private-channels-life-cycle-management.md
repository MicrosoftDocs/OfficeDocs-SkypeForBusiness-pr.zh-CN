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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理组织中专用频道的生命周期。
ms.openlocfilehash: 263f25e283670b0ab8cc0337c0936eee23f43c61
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952885"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>在 Microsoft 团队中管理专用频道的生命周期

在这里，你将找到管理你的组织中的[专用频道](private-channels.md)的生命周期所需的指南。

> [!IMPORTANT]
> 如果你使用本文中的 PowerShell 步骤管理专用通道，则必须从 PowerShell 测试库安装并使用团队 PowerShell 模块的最新版本。 有关如何执行此操作的步骤，请参阅[从 PowerShell 测试库中安装最新团队 PowerShell 模块](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。 团队 PowerShell 模块的最新公开可用版本（当前[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支持管理专用通道。

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

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

使用团队策略设置允许组织中的哪些用户创建专用频道。 若要了解详细信息，请参阅[管理团队中的团队策略](teams-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell

使用**CsTeamsChannelsPolicy**设置允许组织中的哪些用户创建专用频道。 将**AllowPrivateChannelCreation**参数设置为**true** ，以允许分配了该策略的用户创建专用频道。 将该参数设置为**false**将关闭为分配了该策略的用户创建专用通道的功能。

若要了解详细信息，请参阅[CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表团队所有者创建专用频道

作为管理员，你可以使用 PowerShell 或 Graph API 代表团队所有者创建专用通道。 例如，如果您的组织想要集中创建专用频道，您可能需要执行此操作。

### <a name="using-powershell"></a>使用 PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
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

无论您是要针对专用频道中的文件执行电子数据展示或法律封存，还是希望构建一种在特定专用通道中放置文件的业务线应用，您将需要一种方法来查询为其创建的唯一 SharePoint 网站集每个专用频道。

作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。

### <a name="using-powershell"></a>使用 PowerShell

1. 通过管理员帐户安装和连接到[SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 。
2. 运行以下，其中&lt;group_id&gt;是团队的组 id。 （您可以轻松地在与团队的链接中找到组 Id。）

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>使用图形 API

你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。

1. 使用以下操作获取给定团队的专用通道 Id 的列表，其中 <group_id> 是团队的组 Id。 您将在后续通话中需要此内容。 （您可以轻松地在与团队的链接中找到组 Id）。

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

2. 对于要获取 SharePoint URL 的每个专用通道，请执行以下请求，其中&lt;channel_id&gt;是通道 id。

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

作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。

### <a name="using-powershell"></a>使用 PowerShell

1. 通过管理员帐户安装并连接到[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。
2. 运行以下， &lt;其中 group_id&gt;是团队的组 id， &lt;channel_id&gt;是信道 id。

    **请求**

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    **响应**

    ```PowerShell
    HTTP/1.1 200 OK Content-type: application/json
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

3. 将成员提升为所有者。

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>使用图形 API

你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。

1. 使用以下， &lt;其中 group_id&gt;是团队的组 id， &lt;channel_id&gt;是信道 id。

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
2.  使用以下将成员提升为所有者&lt;，其中 group_id&gt;、 &lt;channel_id&gt;和&lt;id&gt;从以前的调用中返回。 请注意&lt;，&gt;从&lt;以前&gt;的调用返回的 id 和 userId 不相同，并且不能互换。 请确保使用&lt;id&gt;。

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

## <a name="teams-powershell-module"></a>团队 Powershell 模块

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>从 PowerShell 测试库安装最新团队 PowerShell 模块

团队 PowerShell 模块的最新公开可用版本（当前[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支持管理专用通道。 使用以下步骤，使用 PowerShell 测试库中的专用通道支持（当前1.0.18）来安装最新版本的团队 PowerShell 模块。

> [!NOTE]
> 不要使用来自公共 PowerShell 库的模块版本并排从 PowerShell 测试库中安装团队 PowerShell 模块。 按照以下步骤，首先从公共 PowerShell 库中卸载团队 PowerShell 模块，然后从 PowerShell 测试库中安装最新版本的模块。

1. 关闭所有现有 PowerShell 会话。
2. 启动 Windows PowerShell 模块的新实例。
3. 运行以下内容从公共 PowerShell 库中卸载团队 PowerShell 模块：

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 关闭所有现有 PowerShell 会话。
5. 再次启动 Windows PowerShell 模块，然后运行以下内容以将 PowerShell 测试库注册为受信任的来源：

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 运行以下内容从 PowerShell 测试库安装最新的团队 PowerShell 模块：

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>从 PowerShell 测试库更新到团队 PowerShell 模块的最新版本

如果已从 PowerShell 测试库中安装了团队 PowerShell 模块，请使用以下步骤更新到最新版本。

1. 关闭所有现有 PowerShell 会话。
2. 启动 Windows PowerShell 模块的新实例。
3. 运行以下内容从 PowerShell 测试库更新当前安装的团队 PowerShell 模块版本：

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [使用 Microsoft Graph API 与团队协作](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [列出频道](https://docs.microsoft.com/graph/api/channel-list)
    - [创建频道](https://docs.microsoft.com/graph/api/channel-post)
    - [向频道添加成员](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [更新频道中的成员](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [从频道中删除成员](https://docs.microsoft.com/graph/api/conversationmember-delete)
