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
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969410"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="ed730-103">在 Microsoft 团队中管理专用频道的生命周期</span><span class="sxs-lookup"><span data-stu-id="ed730-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="ed730-104">在这里，你将找到管理你的组织中的[专用频道](private-channels.md)的生命周期所需的指南。</span><span class="sxs-lookup"><span data-stu-id="ed730-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="ed730-105">设置团队成员是否可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="ed730-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="ed730-106">团队所有者可以关闭或打开成员在团队设置中创建专用频道的功能。</span><span class="sxs-lookup"><span data-stu-id="ed730-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="ed730-107">若要执行此操作，请在团队的 "**设置**" 选项卡上，关闭或打开 "**允许成员创建专用频道**"。</span><span class="sxs-lookup"><span data-stu-id="ed730-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="ed730-108">作为管理员，你可以使用 Graph API 控制成员是否可以在特定团队中创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="ed730-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="ed730-109">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="ed730-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="ed730-110">设置组织中的用户是否可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="ed730-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="ed730-111">作为管理员，你可以使用 Microsoft 团队管理中心或 PowerShell 来设置策略，以控制允许组织中的哪些用户创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="ed730-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ed730-112">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="ed730-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="ed730-113">使用团队策略设置允许组织中的哪些用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="ed730-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="ed730-114">若要了解详细信息，请参阅[管理团队中的团队策略](teams-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ed730-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed730-115">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed730-115">Using PowerShell</span></span>

<span data-ttu-id="ed730-116">使用**CsTeamsChannelsPolicy**设置允许组织中的哪些用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="ed730-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="ed730-117">将**AllowPrivateChannelCreation**参数设置为**true** ，以允许分配了该策略的用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="ed730-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="ed730-118">将该参数设置为**false**将关闭为分配了该策略的用户创建专用通道的功能。</span><span class="sxs-lookup"><span data-stu-id="ed730-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="ed730-119">若要了解详细信息，请参阅[CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ed730-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="ed730-120">代表团队所有者创建专用频道</span><span class="sxs-lookup"><span data-stu-id="ed730-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="ed730-121">作为管理员，你可以使用 PowerShell 或 Graph API 代表团队所有者创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="ed730-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="ed730-122">例如，如果您的组织想要集中创建专用频道，您可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ed730-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed730-123">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed730-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="ed730-124">使用图形 API</span><span class="sxs-lookup"><span data-stu-id="ed730-124">Using Graph API</span></span>

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="ed730-125">获取所有专用信道消息的列表</span><span class="sxs-lookup"><span data-stu-id="ed730-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="ed730-126">您可能希望获取在专用频道中发布的所有邮件和答复的列表，以便存档和审核。</span><span class="sxs-lookup"><span data-stu-id="ed730-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="ed730-127">下面介绍了如何使用 Graph API 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ed730-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="ed730-128">查找团队中所有专用通道的 SharePoint Url</span><span class="sxs-lookup"><span data-stu-id="ed730-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="ed730-129">无论您是要针对专用频道中的文件执行电子数据展示或法律封存，还是希望构建一种在特定专用通道中放置文件的业务线应用，您将需要一种方法来查询为其创建的唯一 SharePoint 网站集每个专用频道。</span><span class="sxs-lookup"><span data-stu-id="ed730-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="ed730-130">作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。</span><span class="sxs-lookup"><span data-stu-id="ed730-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed730-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed730-131">Using PowerShell</span></span>

1. <span data-ttu-id="ed730-132">通过管理员帐户安装和连接到[SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 。</span><span class="sxs-lookup"><span data-stu-id="ed730-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="ed730-133">运行以下，其中&lt;group_id&gt;是团队的组 id。</span><span class="sxs-lookup"><span data-stu-id="ed730-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="ed730-134">（您可以轻松地在与团队的链接中找到组 Id。）</span><span class="sxs-lookup"><span data-stu-id="ed730-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="ed730-135">使用图形 API</span><span class="sxs-lookup"><span data-stu-id="ed730-135">Using Graph API</span></span>

<span data-ttu-id="ed730-136">你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。</span><span class="sxs-lookup"><span data-stu-id="ed730-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="ed730-137">使用以下各项获取给定团队的专用通道 Id 的列表，其中 <group_id> 是团队的组 Id。</span><span class="sxs-lookup"><span data-stu-id="ed730-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="ed730-138">您将在后续通话中需要此内容。</span><span class="sxs-lookup"><span data-stu-id="ed730-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="ed730-139">（您可以轻松地在与团队的链接中找到组 Id）。</span><span class="sxs-lookup"><span data-stu-id="ed730-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="ed730-140">**请求**</span><span class="sxs-lookup"><span data-stu-id="ed730-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="ed730-141">**响应**</span><span class="sxs-lookup"><span data-stu-id="ed730-141">**Response**</span></span>

    ```
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

2. <span data-ttu-id="ed730-142">对于要获取 SharePoint URL 的每个专用通道，请执行以下请求，其中&lt;channel_id&gt;是通道 id。</span><span class="sxs-lookup"><span data-stu-id="ed730-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="ed730-143">**请求**</span><span class="sxs-lookup"><span data-stu-id="ed730-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="ed730-144">**响应**</span><span class="sxs-lookup"><span data-stu-id="ed730-144">**Response**</span></span>

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="ed730-145">在专用通道中列出和更新所有者和成员的角色</span><span class="sxs-lookup"><span data-stu-id="ed730-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="ed730-146">你可能希望列出专用通道的所有者和成员，以确定是否需要将专用通道的某些成员提升为所有者。</span><span class="sxs-lookup"><span data-stu-id="ed730-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="ed730-147">如果您拥有已离开组织的专用频道的所有者，并且专用频道需要管理员帮助来声明频道所有权，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ed730-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="ed730-148">作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。</span><span class="sxs-lookup"><span data-stu-id="ed730-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ed730-149">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed730-149">Using PowerShell</span></span>

1. <span data-ttu-id="ed730-150">通过管理员帐户安装并连接到[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="ed730-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="ed730-151">运行以下， &lt;其中 group_id&gt;是团队的组 id， &lt;channel_id&gt;是信道 id。</span><span class="sxs-lookup"><span data-stu-id="ed730-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="ed730-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="ed730-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="ed730-153">**响应**</span><span class="sxs-lookup"><span data-stu-id="ed730-153">**Response**</span></span>

    ```
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

3. <span data-ttu-id="ed730-154">将成员提升为所有者。</span><span class="sxs-lookup"><span data-stu-id="ed730-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="ed730-155">使用图形 API</span><span class="sxs-lookup"><span data-stu-id="ed730-155">Using Graph API</span></span>

<span data-ttu-id="ed730-156">你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。</span><span class="sxs-lookup"><span data-stu-id="ed730-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="ed730-157">使用以下， &lt;其中 group_id&gt;是团队的组 id， &lt;channel_id&gt;是通道 id。</span><span class="sxs-lookup"><span data-stu-id="ed730-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="ed730-158">**请求**</span><span class="sxs-lookup"><span data-stu-id="ed730-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="ed730-159">**响应**</span><span class="sxs-lookup"><span data-stu-id="ed730-159">**Response**</span></span>

    ```
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
2.  <span data-ttu-id="ed730-160">使用以下将成员提升为所有者&lt;，其中 group_id&gt;、 &lt;channel_id&gt;和&lt;id&gt;从以前的调用中返回。</span><span class="sxs-lookup"><span data-stu-id="ed730-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="ed730-161">请注意&lt;，&gt;从&lt;以前&gt;的调用返回的 id 和 userId 不相同，并且不能互换。</span><span class="sxs-lookup"><span data-stu-id="ed730-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="ed730-162">请确保使用&lt;id&gt;。</span><span class="sxs-lookup"><span data-stu-id="ed730-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="ed730-163">**请求**</span><span class="sxs-lookup"><span data-stu-id="ed730-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="ed730-164">**响应**</span><span class="sxs-lookup"><span data-stu-id="ed730-164">**Response**</span></span>

    ```
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

## <a name="related-topics"></a><span data-ttu-id="ed730-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed730-165">Related topics</span></span>

- [<span data-ttu-id="ed730-166">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="ed730-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="ed730-167">使用 Microsoft Graph API 与团队协作</span><span class="sxs-lookup"><span data-stu-id="ed730-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="ed730-168">列出频道</span><span class="sxs-lookup"><span data-stu-id="ed730-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="ed730-169">创建频道</span><span class="sxs-lookup"><span data-stu-id="ed730-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="ed730-170">向频道添加成员</span><span class="sxs-lookup"><span data-stu-id="ed730-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="ed730-171">更新频道中的成员</span><span class="sxs-lookup"><span data-stu-id="ed730-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="ed730-172">从频道中删除成员</span><span class="sxs-lookup"><span data-stu-id="ed730-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)