---
title: 使用 Graph API 管理 Microsoft Teams 中的专用通道
author: MikePlumleyMSFT
ms.author: mikeplum
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
description: 了解如何使用 API 管理组织中专用Graph通道。
ms.openlocfilehash: 82a9f865099be4012456a1c3a854e08b79d15db432e965a60e32d44c36147b9c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350504"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>管理专用频道在 Microsoft Teams

可在此处找到管理所需的指导，使用 Graph API 管理[Teams专用](./private-channels.md)频道。

## <a name="set-whether-team-members-can-create-private-channels"></a>设置团队成员是否可以创建专用频道

作为管理员，可以使用 Graph API 来控制成员是否可以在特定的团队中创建专用频道。 下面是一个示例。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>代表团队所有者创建专用频道

作为管理员，可以使用 Graph API 代表团队所有者创建专用频道。 例如，如果你的组织想要集中创建专用频道，你可能希望这样做。

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

## <a name="get-a-list-of-all-private-channel-messages"></a>获取所有专用频道消息的列表

你可能希望获取在专用频道中发布的所有消息和答复的列表，以便进行存档和审核。  下面将了解如何使用 Graph API 来这样做。

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>查找SharePoint中所有专用频道的 URL

无论是希望对专用通道中的文件执行电子数据展示还是法定保留，还是想要构建将文件放在特定专用通道中的自定义应用，您都想通过一种方法查询针对每个专用通道创建的唯一 SharePoint 网站集。

作为管理员，可以使用 Graph API 命令来查询这些 URL。

可以通过资源管理器 尝试[Graph命令](https://developer.microsoft.com/graph/graph-explorer)。

1. 使用以下代码获取给定团队的专用频道 ID 列表，其中<group_id>是团队的组 ID。 后续调用中将需要此。  (可以在团队组链接中轻松找到组 ID) 。

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

2. 对于要获取该 URL 的每个专用SharePoint，请提出以下请求，其中channel_id &lt; &gt; 是通道 ID。

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>列出和更新专用频道中所有者和成员的角色

你可能希望列出专用频道的所有者和成员，以决定是否需要将专用频道的某些成员提升为所有者。 当专用频道的所有者已离开组织，而专用频道需要管理员帮助来声明通道所有权时，可能会发生这种情况。

作为管理员，可以使用 Graph API 来执行这些操作。

可以通过资源管理器 尝试[Graph命令](https://developer.microsoft.com/graph/graph-explorer)。

1. 使用以下代码，其中group_id是团队的 &lt; &gt; 组 ID，channel_id &lt; &gt; 是频道 ID。

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

2. 使用以下代码将成员提升为所有者，其中，group_id 、channel_id 和 ID 从上一个 &lt; &gt; &lt; &gt; &lt; &gt; 调用返回。 请注意，从上一个调用返回的 ID 和 userId 不相同， &lt; &gt; &lt; &gt; 并且不可互换。 请确保使用 &lt; ID &gt; 。

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

[将 Microsoft Graph API 与 Teams 结合使用](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[列出频道](/graph/api/channel-list)

[创建频道](/graph/api/channel-post)

[将成员添加到频道](/graph/api/conversationmember-add)

[更新频道中的成员](/graph/api/conversationmember-update)

[从频道中删除成员](/graph/api/conversationmember-delete)