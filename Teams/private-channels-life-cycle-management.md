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
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117740"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="1b0aa-103">管理专用频道在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b0aa-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="1b0aa-104">可在此处找到管理所需的指导，使用 Graph API 管理[Teams专用](./private-channels.md)频道。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](./private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="1b0aa-105">设置团队成员是否可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="1b0aa-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="1b0aa-106">作为管理员，可以使用 Graph API 来控制成员是否可以在特定的团队中创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="1b0aa-107">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="1b0aa-108">代表团队所有者创建专用频道</span><span class="sxs-lookup"><span data-stu-id="1b0aa-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="1b0aa-109">作为管理员，可以使用 Graph API 代表团队所有者创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="1b0aa-110">例如，如果你的组织想要集中创建专用频道，你可能希望这样做。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="1b0aa-111">获取所有专用频道消息的列表</span><span class="sxs-lookup"><span data-stu-id="1b0aa-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="1b0aa-112">你可能希望获取在专用频道中发布的所有消息和答复的列表，以便进行存档和审核。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="1b0aa-113">下面将了解如何使用 Graph API 来这样做。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="1b0aa-114">查找SharePoint中所有专用频道的 URL</span><span class="sxs-lookup"><span data-stu-id="1b0aa-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="1b0aa-115">无论是希望对专用通道中的文件执行电子数据展示还是法定保留，还是想要构建将文件放在特定专用通道中的自定义应用，您都想通过一种方法查询针对每个专用通道创建的唯一 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="1b0aa-116">作为管理员，可以使用 Graph API 命令来查询这些 URL。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="1b0aa-117">可以通过资源管理器 尝试[Graph命令](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="1b0aa-118">使用以下代码获取给定团队的专用频道 ID 列表，其中<group_id>是团队的组 ID。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="1b0aa-119">后续调用中将需要此。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="1b0aa-120"> (可以在团队组链接中轻松找到组 ID) 。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="1b0aa-121">**请求**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="1b0aa-122">**响应**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-122">**Response**</span></span>

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

2. <span data-ttu-id="1b0aa-123">对于要获取该 URL 的每个专用SharePoint，请提出以下请求，其中channel_id &lt; &gt; 是通道 ID。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="1b0aa-124">**请求**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="1b0aa-125">**响应**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="1b0aa-126">列出和更新专用频道中所有者和成员的角色</span><span class="sxs-lookup"><span data-stu-id="1b0aa-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="1b0aa-127">你可能希望列出专用频道的所有者和成员，以决定是否需要将专用频道的某些成员提升为所有者。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="1b0aa-128">当专用频道的所有者已离开组织，而专用频道需要管理员帮助来声明通道所有权时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="1b0aa-129">作为管理员，可以使用 Graph API 来执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="1b0aa-130">可以通过资源管理器 尝试[Graph命令](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="1b0aa-131">使用以下代码，其中group_id是团队的 &lt; &gt; 组 ID，channel_id &lt; &gt; 是频道 ID。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="1b0aa-132">**请求**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="1b0aa-133">**响应**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-133">**Response**</span></span>

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
2. <span data-ttu-id="1b0aa-134">使用以下代码将成员提升为所有者，其中，group_id 、channel_id 和 ID 从上一个 &lt; &gt; &lt; &gt; &lt; &gt; 调用返回。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="1b0aa-135">请注意，从上一个调用返回的 ID 和 userId 不相同， &lt; &gt; &lt; &gt; 并且不可互换。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="1b0aa-136">请确保使用 &lt; ID &gt; 。</span><span class="sxs-lookup"><span data-stu-id="1b0aa-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="1b0aa-137">**请求**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="1b0aa-138">**响应**</span><span class="sxs-lookup"><span data-stu-id="1b0aa-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="1b0aa-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b0aa-139">Related topics</span></span>

[<span data-ttu-id="1b0aa-140">将 Microsoft Graph API 与 Teams 结合使用</span><span class="sxs-lookup"><span data-stu-id="1b0aa-140">Use the Microsoft Graph API to work with Teams</span></span>](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="1b0aa-141">列出频道</span><span class="sxs-lookup"><span data-stu-id="1b0aa-141">List channels</span></span>](/graph/api/channel-list)

[<span data-ttu-id="1b0aa-142">创建频道</span><span class="sxs-lookup"><span data-stu-id="1b0aa-142">Create channel</span></span>](/graph/api/channel-post)

[<span data-ttu-id="1b0aa-143">将成员添加到频道</span><span class="sxs-lookup"><span data-stu-id="1b0aa-143">Add member to channel</span></span>](/graph/api/conversationmember-add)

[<span data-ttu-id="1b0aa-144">更新频道中的成员</span><span class="sxs-lookup"><span data-stu-id="1b0aa-144">Update member in channel</span></span>](/graph/api/conversationmember-update)

[<span data-ttu-id="1b0aa-145">从频道中删除成员</span><span class="sxs-lookup"><span data-stu-id="1b0aa-145">Remove member from channel</span></span>](/graph/api/conversationmember-delete)