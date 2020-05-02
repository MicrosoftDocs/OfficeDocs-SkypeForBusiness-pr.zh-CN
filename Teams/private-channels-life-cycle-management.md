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
ms.openlocfilehash: 10746605895732af19a43ffb85df06a81ae34316
ms.sourcegitcommit: 3325fd9de57367e9dd60685d1fef096921441a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997243"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="dc6ef-103">在 Microsoft 团队中管理专用频道的生命周期</span><span class="sxs-lookup"><span data-stu-id="dc6ef-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="dc6ef-104">在这里，你将找到管理你的组织中的[专用频道](private-channels.md)的生命周期所需的指南。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc6ef-105">如果你使用本文中的 PowerShell 步骤管理专用通道，则必须从 PowerShell 测试库安装并使用团队 PowerShell 模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="dc6ef-106">有关如何执行此操作的步骤，请参阅[从 PowerShell 测试库中安装最新团队 PowerShell 模块](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="dc6ef-107">团队 PowerShell 模块的最新公开可用版本（当前[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)）不支持管理专用通道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="dc6ef-108">设置团队成员是否可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="dc6ef-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="dc6ef-109">团队所有者可以关闭或打开成员在团队设置中创建专用频道的功能。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="dc6ef-110">若要执行此操作，请在团队的 "**设置**" 选项卡上，关闭或打开 "**允许成员创建专用频道**"。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="dc6ef-111">作为管理员，你可以使用 Graph API 控制成员是否可以在特定团队中创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="dc6ef-112">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="dc6ef-113">设置组织中的用户是否可以创建专用频道</span><span class="sxs-lookup"><span data-stu-id="dc6ef-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="dc6ef-114">作为管理员，你可以使用 Microsoft 团队管理中心或 PowerShell 来设置策略，以控制允许组织中的哪些用户创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="dc6ef-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="dc6ef-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="dc6ef-116">使用团队策略设置允许组织中的哪些用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="dc6ef-117">若要了解详细信息，请参阅[管理团队中的团队策略](teams-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dc6ef-118">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc6ef-118">Using PowerShell</span></span>

<span data-ttu-id="dc6ef-119">使用**CsTeamsChannelsPolicy**设置允许组织中的哪些用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="dc6ef-120">将**AllowPrivateChannelCreation**参数设置为**true** ，以允许分配了该策略的用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="dc6ef-121">将该参数设置为**false**将关闭为分配了该策略的用户创建专用通道的功能。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="dc6ef-122">若要了解详细信息，请参阅[CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="dc6ef-123">代表团队所有者创建专用频道</span><span class="sxs-lookup"><span data-stu-id="dc6ef-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="dc6ef-124">作为管理员，你可以使用 PowerShell 或 Graph API 代表团队所有者创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="dc6ef-125">例如，如果您的组织想要集中创建专用频道，您可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dc6ef-126">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc6ef-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="dc6ef-127">使用图形 API</span><span class="sxs-lookup"><span data-stu-id="dc6ef-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="dc6ef-128">获取所有专用信道消息的列表</span><span class="sxs-lookup"><span data-stu-id="dc6ef-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="dc6ef-129">您可能希望获取在专用频道中发布的所有邮件和答复的列表，以便存档和审核。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="dc6ef-130">下面介绍了如何使用 Graph API 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="dc6ef-131">查找团队中所有专用通道的 SharePoint Url</span><span class="sxs-lookup"><span data-stu-id="dc6ef-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="dc6ef-132">无论是要针对专用频道中的文件执行电子数据展示或法律封存，还是希望构建一个自定义应用来将文件放入特定的专用通道中，你将需要一种方法来查询为每个专用通道创建的唯一 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="dc6ef-133">作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dc6ef-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc6ef-134">Using PowerShell</span></span>

1. <span data-ttu-id="dc6ef-135">通过管理员帐户安装和连接到[SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="dc6ef-136">运行以下，其中&lt;group_id&gt;是团队的组 id。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="dc6ef-137">（您可以轻松地在与团队的链接中找到组 ID。）</span><span class="sxs-lookup"><span data-stu-id="dc6ef-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="dc6ef-138">使用图形 API</span><span class="sxs-lookup"><span data-stu-id="dc6ef-138">Using Graph API</span></span>

<span data-ttu-id="dc6ef-139">你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="dc6ef-140">使用以下操作获取给定团队的专用通道 Id 的列表，其中 <group_id> 是团队的组 ID。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="dc6ef-141">您将在后续通话中需要此内容。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="dc6ef-142">（您可以轻松地在与团队的链接中找到组 ID）。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="dc6ef-143">**请求**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="dc6ef-144">**响应**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-144">**Response**</span></span>

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

2. <span data-ttu-id="dc6ef-145">对于要获取 SharePoint URL 的每个专用通道，请执行以下请求，其中&lt;channel_id&gt;是通道 id。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="dc6ef-146">**请求**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="dc6ef-147">**响应**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="dc6ef-148">在专用通道中列出和更新所有者和成员的角色</span><span class="sxs-lookup"><span data-stu-id="dc6ef-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="dc6ef-149">你可能希望列出专用通道的所有者和成员，以确定是否需要将专用通道的某些成员提升为所有者。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="dc6ef-150">如果您拥有已离开组织的专用频道的所有者，并且专用频道需要管理员帮助来声明频道所有权，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="dc6ef-151">作为管理员，你可以使用 PowerShell 或图形 Api 命令查询这些 Url。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="dc6ef-152">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc6ef-152">Using PowerShell</span></span>

1. <span data-ttu-id="dc6ef-153">运行以下， &lt;其中 group_id&gt;是团队的组 id， &lt;channel_name&gt;是信道名称。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="dc6ef-154">将成员提升为所有者。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="dc6ef-155">使用图形 API</span><span class="sxs-lookup"><span data-stu-id="dc6ef-155">Using Graph API</span></span>

<span data-ttu-id="dc6ef-156">你可以通过[图表资源管理器](https://developer.microsoft.com/graph/graph-explorer)尝试这些命令。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="dc6ef-157">使用以下， &lt;其中 group_id&gt;是团队的组 id， &lt;channel_id&gt;是信道 id。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="dc6ef-158">**请求**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="dc6ef-159">**响应**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-159">**Response**</span></span>

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
2.     <span data-ttu-id="dc6ef-160">使用以下将成员提升为所有者&lt;，其中 group_id&gt;、 &lt;channel_id&gt;和&lt;id&gt;从以前的调用中返回。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="dc6ef-161">请注意&lt;，&gt;从&lt;以前&gt;的调用返回的 id 和 userId 不相同，并且不能互换。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="dc6ef-162">请确保使用&lt;id&gt;。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="dc6ef-163">**请求**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="dc6ef-164">**响应**</span><span class="sxs-lookup"><span data-stu-id="dc6ef-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="dc6ef-165">团队 Powershell 模块</span><span class="sxs-lookup"><span data-stu-id="dc6ef-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="dc6ef-166">从 PowerShell 测试库安装最新团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="dc6ef-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="dc6ef-167">团队 PowerShell 模块的最新公开可用版本（当前[1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)）不支持管理专用通道。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) doesn't support managing private channels.</span></span> <span data-ttu-id="dc6ef-168">使用以下步骤，使用 PowerShell 测试库中的专用通道支持（当前1.0.21）来安装最新版本的团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.21) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="dc6ef-169">不要使用来自公共 PowerShell 库的模块版本并排从 PowerShell 测试库中安装团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="dc6ef-170">按照以下步骤，首先从公共 PowerShell 库中卸载团队 PowerShell 模块，然后从 PowerShell 测试库中安装最新版本的模块。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="dc6ef-171">关闭所有现有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="dc6ef-172">启动 Windows PowerShell 模块的新实例。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="dc6ef-173">运行以下内容从公共 PowerShell 库中卸载团队 PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="dc6ef-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="dc6ef-174">关闭所有现有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="dc6ef-175">再次启动 Windows PowerShell 模块，然后运行以下内容以将 PowerShell 测试库注册为受信任的来源：</span><span class="sxs-lookup"><span data-stu-id="dc6ef-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="dc6ef-176">运行以下内容从 PowerShell 测试库安装最新的团队 PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="dc6ef-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="dc6ef-177">运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：</span><span class="sxs-lookup"><span data-stu-id="dc6ef-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="dc6ef-178">从 PowerShell 测试库更新到团队 PowerShell 模块的最新版本</span><span class="sxs-lookup"><span data-stu-id="dc6ef-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="dc6ef-179">如果已从 PowerShell 测试库中安装了团队 PowerShell 模块，请使用以下步骤更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="dc6ef-180">关闭所有现有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="dc6ef-181">启动 Windows PowerShell 模块的新实例。</span><span class="sxs-lookup"><span data-stu-id="dc6ef-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="dc6ef-182">运行以下内容从 PowerShell 测试库更新当前安装的团队 PowerShell 模块版本：</span><span class="sxs-lookup"><span data-stu-id="dc6ef-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="dc6ef-183">运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：</span><span class="sxs-lookup"><span data-stu-id="dc6ef-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="dc6ef-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc6ef-184">Related topics</span></span>

- [<span data-ttu-id="dc6ef-185">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="dc6ef-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="dc6ef-186">将 Microsoft Graph API 与 Teams 结合使用</span><span class="sxs-lookup"><span data-stu-id="dc6ef-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="dc6ef-187">列出频道</span><span class="sxs-lookup"><span data-stu-id="dc6ef-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="dc6ef-188">创建频道</span><span class="sxs-lookup"><span data-stu-id="dc6ef-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="dc6ef-189">向频道添加成员</span><span class="sxs-lookup"><span data-stu-id="dc6ef-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="dc6ef-190">更新频道中的成员</span><span class="sxs-lookup"><span data-stu-id="dc6ef-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="dc6ef-191">从频道中删除成员</span><span class="sxs-lookup"><span data-stu-id="dc6ef-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
