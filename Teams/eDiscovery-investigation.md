---
title: 对内容进行电子数据展示调查
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解需要执行电子数据展示时（例如，需要提交所有电子数据存储信息进行法律诉讼时）应执行的操作。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980456"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="18cac-103">在 Microsoft Teams 中对内容进行电子数据展示调查</span><span class="sxs-lookup"><span data-stu-id="18cac-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="18cac-104">大型企业通常面临高损失诉讼，这些诉讼要求提交所有电子 (ESI) 。</span><span class="sxs-lookup"><span data-stu-id="18cac-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="18cac-105">可在电子数据展示调查期间搜索和使用 Microsoft Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="18cac-106">概述</span><span class="sxs-lookup"><span data-stu-id="18cac-106">Overview</span></span>

<span data-ttu-id="18cac-107">所有 Microsoft Teams 1：1 或群组聊天都记录到相应用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="18cac-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="18cac-108">所有标准频道邮件都记录在代表团队的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="18cac-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="18cac-109">在标准频道中上传的文件包括在 SharePoint Online 和 OneDrive for Business 的电子数据展示功能下。</span><span class="sxs-lookup"><span data-stu-id="18cac-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="18cac-110">私人频道中 [消息和文件](private-channels.md) 电子数据展示的工作方式与标准通道中的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="18cac-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="18cac-111">若要了解有关详细信息，请参阅 [专用通道的电子数据展示](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="18cac-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="18cac-112">并非所有 Teams 内容都是可电子数据展示的。</span><span class="sxs-lookup"><span data-stu-id="18cac-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="18cac-113">下表显示了可以使用 Microsoft 电子数据展示工具搜索的内容类型：</span><span class="sxs-lookup"><span data-stu-id="18cac-113">The following table shows the content types that you can search for using Microsoft eDiscovery tools:</span></span>

| <span data-ttu-id="18cac-114">内容类型</span><span class="sxs-lookup"><span data-stu-id="18cac-114">Content type</span></span> | <span data-ttu-id="18cac-115">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="18cac-115">eDiscoverable</span></span> | <span data-ttu-id="18cac-116">注释</span><span class="sxs-lookup"><span data-stu-id="18cac-116">Notes</span></span> |
|:--- | :--- |:--- |
|<span data-ttu-id="18cac-117">录音</span><span class="sxs-lookup"><span data-stu-id="18cac-117">Audio recordings</span></span> | <span data-ttu-id="18cac-118">否</span><span class="sxs-lookup"><span data-stu-id="18cac-118">No</span></span> | |
|<span data-ttu-id="18cac-119">卡片内容</span><span class="sxs-lookup"><span data-stu-id="18cac-119">Card content</span></span>|<span data-ttu-id="18cac-120">是</span><span class="sxs-lookup"><span data-stu-id="18cac-120">Yes</span></span>|<span data-ttu-id="18cac-121">有关详细信息 [，请参阅"搜索](#search-for-card-content) 卡片内容"。</span><span class="sxs-lookup"><span data-stu-id="18cac-121">See [Search for card content](#search-for-card-content) for more information.</span></span>|
|<span data-ttu-id="18cac-122">聊天链接</span><span class="sxs-lookup"><span data-stu-id="18cac-122">Chat links</span></span> | <span data-ttu-id="18cac-123">是</span><span class="sxs-lookup"><span data-stu-id="18cac-123">Yes</span></span> | |
|<span data-ttu-id="18cac-124">聊天消息</span><span class="sxs-lookup"><span data-stu-id="18cac-124">Chat messages</span></span> | <span data-ttu-id="18cac-125">是</span><span class="sxs-lookup"><span data-stu-id="18cac-125">Yes</span></span> |<span data-ttu-id="18cac-126">这包括 Teams 频道中的内容、1 对 1 聊天、1：N 群组聊天以及与来宾用户参与者的聊天。</span><span class="sxs-lookup"><span data-stu-id="18cac-126">This includes content in Teams channels, 1:1 chats, 1:N group chats, and chats with guest user participants.</span></span>  |
|<span data-ttu-id="18cac-127">代码片段</span><span class="sxs-lookup"><span data-stu-id="18cac-127">Code snippets</span></span> | <span data-ttu-id="18cac-128">否</span><span class="sxs-lookup"><span data-stu-id="18cac-128">No</span></span> | |
|<span data-ttu-id="18cac-129">已编辑的邮件</span><span class="sxs-lookup"><span data-stu-id="18cac-129">Edited messages</span></span> | <span data-ttu-id="18cac-130">是</span><span class="sxs-lookup"><span data-stu-id="18cac-130">Yes</span></span> | <span data-ttu-id="18cac-131">如果用户保持保留状态，也会保留以前版本的已编辑消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-131">If the user is on hold, previous versions of edited messages are also preserved.</span></span> |
|<span data-ttu-id="18cac-132">表情符号、GIF 和贴纸</span><span class="sxs-lookup"><span data-stu-id="18cac-132">Emojis, GIFs, and stickers</span></span> | <span data-ttu-id="18cac-133">是</span><span class="sxs-lookup"><span data-stu-id="18cac-133">Yes</span></span> | |
|<span data-ttu-id="18cac-134">内联图像</span><span class="sxs-lookup"><span data-stu-id="18cac-134">Inline images</span></span> | <span data-ttu-id="18cac-135">是</span><span class="sxs-lookup"><span data-stu-id="18cac-135">Yes</span></span> | |
|<span data-ttu-id="18cac-136">会议 IM 对话</span><span class="sxs-lookup"><span data-stu-id="18cac-136">Meeting IM conversations</span></span> | <span data-ttu-id="18cac-137">是</span><span class="sxs-lookup"><span data-stu-id="18cac-137">Yes</span></span> | |
|<span data-ttu-id="18cac-138">会议元数据<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="18cac-138">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="18cac-139">是</span><span class="sxs-lookup"><span data-stu-id="18cac-139">Yes</span></span> |  |
|<span data-ttu-id="18cac-140">频道名称</span><span class="sxs-lookup"><span data-stu-id="18cac-140">Name of channel</span></span> | <span data-ttu-id="18cac-141">否</span><span class="sxs-lookup"><span data-stu-id="18cac-141">No</span></span> | |
|<span data-ttu-id="18cac-142">专用频道消息</span><span class="sxs-lookup"><span data-stu-id="18cac-142">Private channel messages</span></span> | <span data-ttu-id="18cac-143">是</span><span class="sxs-lookup"><span data-stu-id="18cac-143">Yes</span></span> | |
|<span data-ttu-id="18cac-144">引号</span><span class="sxs-lookup"><span data-stu-id="18cac-144">Quotes</span></span> | <span data-ttu-id="18cac-145">是</span><span class="sxs-lookup"><span data-stu-id="18cac-145">Yes</span></span> | <span data-ttu-id="18cac-146">引用的内容是可搜索的。</span><span class="sxs-lookup"><span data-stu-id="18cac-146">Quoted content is searchable.</span></span> <span data-ttu-id="18cac-147">但是，搜索结果不会指示内容已引用。</span><span class="sxs-lookup"><span data-stu-id="18cac-147">However, search results don't indicate that the content was quoted.</span></span> |
|<span data-ttu-id="18cac-148">反应 (如点子、心声和其他反应) </span><span class="sxs-lookup"><span data-stu-id="18cac-148">Reactions (such as likes, hearts, and other reactions)</span></span> | <span data-ttu-id="18cac-149">否</span><span class="sxs-lookup"><span data-stu-id="18cac-149">No</span></span> | |
|<span data-ttu-id="18cac-150">主题</span><span class="sxs-lookup"><span data-stu-id="18cac-150">Subject</span></span> | <span data-ttu-id="18cac-151">是</span><span class="sxs-lookup"><span data-stu-id="18cac-151">Yes</span></span> | |
|<span data-ttu-id="18cac-152">表</span><span class="sxs-lookup"><span data-stu-id="18cac-152">Tables</span></span> | <span data-ttu-id="18cac-153">是</span><span class="sxs-lookup"><span data-stu-id="18cac-153">Yes</span></span> | |
|||

<span data-ttu-id="18cac-154"><sup>1</sup> 会议 (呼叫) 元数据包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="18cac-154"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="18cac-155">会议开始时间和结束时间以及持续时间</span><span class="sxs-lookup"><span data-stu-id="18cac-155">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="18cac-156">每个参与者的会议加入和离开事件</span><span class="sxs-lookup"><span data-stu-id="18cac-156">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="18cac-157">VOIP 加入/呼叫</span><span class="sxs-lookup"><span data-stu-id="18cac-157">VOIP join/calls</span></span>
- <span data-ttu-id="18cac-158">匿名加入</span><span class="sxs-lookup"><span data-stu-id="18cac-158">Anonymous join</span></span>
- <span data-ttu-id="18cac-159">联合用户加入</span><span class="sxs-lookup"><span data-stu-id="18cac-159">Federated user join</span></span>
- <span data-ttu-id="18cac-160">来宾用户加入</span><span class="sxs-lookup"><span data-stu-id="18cac-160">Guest user join</span></span>

  <span data-ttu-id="18cac-161">该图像显示了会议元数据的示例。</span><span class="sxs-lookup"><span data-stu-id="18cac-161">The image shows an example of meeting metadata.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="18cac-162">![图像是 CVR 记录会议元数据的图像。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="18cac-162">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="18cac-163">下面是会议期间参与者之间的即时消息对话示例。</span><span class="sxs-lookup"><span data-stu-id="18cac-163">Here's an example of an IM conversation between participants during the meeting.</span></span>

![Teams 中参与者之间的对话。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="18cac-165">![电子数据展示搜索结果中的参与者之间的对话。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="18cac-165">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="18cac-166">有关执行电子数据展示调查详细信息，请参阅核心 [电子数据展示入门](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="18cac-166">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="18cac-167">Microsoft Teams 数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话。</span><span class="sxs-lookup"><span data-stu-id="18cac-167">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="18cac-168">导出邮件 `.pst` 后，可以在 Outlook 中打开该文件以查看这些邮件。</span><span class="sxs-lookup"><span data-stu-id="18cac-168">You can open the `.pst` file in Outlook to view those messages after you export them.</span></span>

<span data-ttu-id="18cac-169">查看团队的 .pst 文件时，所有对话都保存在"对话历史记录"下的"团队聊天"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="18cac-169">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="18cac-170">消息的标题包含团队名称和频道名称。</span><span class="sxs-lookup"><span data-stu-id="18cac-170">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="18cac-171">例如，下图显示了 Bob 发来的消息，他向制造规范团队的 Project 7 标准频道发送消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-171">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook 中用户邮箱中的"团队聊天"文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="18cac-173">用户邮箱中的私人聊天存储在"对话历史记录"下的"团队聊天"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="18cac-173">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="18cac-174">专用通道电子数据展示</span><span class="sxs-lookup"><span data-stu-id="18cac-174">eDiscovery of private channels</span></span>

<span data-ttu-id="18cac-175">在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。</span><span class="sxs-lookup"><span data-stu-id="18cac-175">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="18cac-176">记录的标题已格式化为指示它们是从哪个私人频道发送的。</span><span class="sxs-lookup"><span data-stu-id="18cac-176">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="18cac-177">由于每个专用频道都有自己的 SharePoint 网站，该网站独立于父团队网站，因此专用频道中的文件独立于父团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="18cac-177">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="18cac-178">Teams 不支持对团队中的单个频道进行电子数据展示搜索，因此必须搜索整个团队。</span><span class="sxs-lookup"><span data-stu-id="18cac-178">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="18cac-179">若要在专用频道中对内容执行电子数据展示搜索，请在整个团队中搜索、与专用频道关联的网站集 (以包含文件) 以及专用频道成员的邮箱 (以包含消息) 。</span><span class="sxs-lookup"><span data-stu-id="18cac-179">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="18cac-180">使用以下步骤识别专用通道中要包括在电子数据展示搜索中的文件和消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-180">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="18cac-181">在电子数据展示搜索中包括专用频道文件</span><span class="sxs-lookup"><span data-stu-id="18cac-181">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="18cac-182">执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="18cac-182">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="18cac-183">运行以下代码，获取与团队中的专用频道关联的所有 SharePoint 网站集的列表。</span><span class="sxs-lookup"><span data-stu-id="18cac-183">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="18cac-184">运行以下 PowerShell 脚本，获取与团队中的专用频道关联的所有 SharePoint 网站集 URL 的列表和父团队组 ID。</span><span class="sxs-lookup"><span data-stu-id="18cac-184">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="18cac-185">对于每个团队或组 ID，请运行以下 PowerShell 脚本来识别所有相关专用频道站点，其中$groupID是团队的组 ID。</span><span class="sxs-lookup"><span data-stu-id="18cac-185">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="18cac-186">在电子数据展示搜索中包括私人频道消息</span><span class="sxs-lookup"><span data-stu-id="18cac-186">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="18cac-187">执行这些步骤之前，请确保已安装最新版本的 Teams [PowerShell 模块](teams-powershell-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="18cac-187">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="18cac-188">运行以下命令，获取团队中的专用频道列表。</span><span class="sxs-lookup"><span data-stu-id="18cac-188">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="18cac-189">运行以下命令获取专用通道成员的列表。</span><span class="sxs-lookup"><span data-stu-id="18cac-189">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="18cac-190">在电子数据展示搜索查询中包括团队中每个专用频道中所有成员 [的邮箱](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="18cac-190">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="18cac-191">搜索来宾用户的内容</span><span class="sxs-lookup"><span data-stu-id="18cac-191">Search for content for guest users</span></span>

<span data-ttu-id="18cac-192">可以使用电子数据展示工具搜索与组织中来宾用户相关的 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-192">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="18cac-193">与来宾用户关联的 Teams 聊天内容保留在基于云的存储位置，并且可以使用电子数据展示进行搜索。</span><span class="sxs-lookup"><span data-stu-id="18cac-193">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="18cac-194">这包括在 1：1 和 1：N 聊天对话中搜索内容，其中来宾用户是组织中其他用户的参与者。</span><span class="sxs-lookup"><span data-stu-id="18cac-194">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="18cac-195">还可以搜索来宾用户是参与者的私人频道消息，在来宾 *：* 来宾聊天对话中搜索内容，其中只有参与者是来宾用户。</span><span class="sxs-lookup"><span data-stu-id="18cac-195">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="18cac-196">搜索来宾用户的内容：</span><span class="sxs-lookup"><span data-stu-id="18cac-196">To search for content for guest users:</span></span>

1. <span data-ttu-id="18cac-197">连接到 Azure AD PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18cac-197">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="18cac-198">有关说明，请参阅"使用 PowerShell 连接到 Microsoft 365"中的"使用 Azure Active Directory [PowerShell 进行连接"部分](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="18cac-198">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="18cac-199">请务必完成上一主题中的步骤 1 和步骤 2。</span><span class="sxs-lookup"><span data-stu-id="18cac-199">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="18cac-200">成功连接到 Azure AD PowerShell 后，请运行以下命令，为组织的所有来宾 (UPN) 用户显示用户主体名称。</span><span class="sxs-lookup"><span data-stu-id="18cac-200">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="18cac-201">在步骤 4 创建搜索时，您必须使用来宾用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="18cac-201">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="18cac-202">可以将命令的输出重定向到文本文件，而不是在计算机屏幕上显示用户主体名称列表。</span><span class="sxs-lookup"><span data-stu-id="18cac-202">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="18cac-203">为此，可以追加到上 `> filename.txt` 一命令。</span><span class="sxs-lookup"><span data-stu-id="18cac-203">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="18cac-204">具有用户主体名称的文本文件将保存到当前文件夹。</span><span class="sxs-lookup"><span data-stu-id="18cac-204">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="18cac-205">在不同的安全Windows PowerShell，连接到安全&中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18cac-205">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="18cac-206">有关说明，请参阅["连接到安全&中心 PowerShell"。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="18cac-206">For instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="18cac-207">可以使用或不使用多重身份验证进行连接。</span><span class="sxs-lookup"><span data-stu-id="18cac-207">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="18cac-208">通过运行以下命令创建内容搜索 (，例如聊天消息和电子邮件) 指定来宾用户是参与者）。</span><span class="sxs-lookup"><span data-stu-id="18cac-208">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="18cac-209">例如，若要搜索与来宾用户 Sara Sara 关联的内容，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="18cac-209">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="18cac-210">有关使用 PowerShell 创建内容搜索详细信息，请参阅[New-ComplianceSearch。](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)</span><span class="sxs-lookup"><span data-stu-id="18cac-210">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="18cac-211">运行以下命令，启动在步骤 4 中创建的内容搜索：</span><span class="sxs-lookup"><span data-stu-id="18cac-211">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="18cac-212">转到， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击"显示 **所有**  >  **内容搜索"。**</span><span class="sxs-lookup"><span data-stu-id="18cac-212">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="18cac-213">在搜索列表中，选择在步骤 4 中创建的搜索以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="18cac-213">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="18cac-214">在"飞出"页上，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="18cac-214">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="18cac-215">单击 **"查看** 结果"以查看搜索结果并预览内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-215">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="18cac-216">在" **查询"字段** 旁边，单击 **"编辑** "进行编辑，然后重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="18cac-216">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="18cac-217">例如，可以添加搜索查询来缩小结果范围。</span><span class="sxs-lookup"><span data-stu-id="18cac-217">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="18cac-218">单击 **"导出结果** "导出并下载搜索结果。</span><span class="sxs-lookup"><span data-stu-id="18cac-218">Click **Export results** to export and download the search results.</span></span>

## <a name="search-for-card-content"></a><span data-ttu-id="18cac-219">搜索卡片内容</span><span class="sxs-lookup"><span data-stu-id="18cac-219">Search for card content</span></span>

<span data-ttu-id="18cac-220">Teams 频道、1 对 1 聊天和 1xN 聊天中应用生成的卡内容存储在邮箱中，可以搜索。</span><span class="sxs-lookup"><span data-stu-id="18cac-220">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="18cac-221">*卡* 是一个 UI 容器，用于提供简短的内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-221">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="18cac-222">卡片可以有多个属性和附件，并且可以包含可以触发卡片操作的按钮。</span><span class="sxs-lookup"><span data-stu-id="18cac-222">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="18cac-223">有关详细信息，请参阅 ["卡片"](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="18cac-223">For more information, see [Cards](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

<span data-ttu-id="18cac-224">与其他 Teams 内容一样，卡片内容的存储位置取决于卡的使用位置。</span><span class="sxs-lookup"><span data-stu-id="18cac-224">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="18cac-225">Teams 频道中使用的卡片内容存储在 Teams 组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="18cac-225">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="18cac-226">1：1 和 1xN 聊天的卡内容存储在聊天参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="18cac-226">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

<span data-ttu-id="18cac-227">若要搜索卡内容，可以使用或 `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` 搜索条件。</span><span class="sxs-lookup"><span data-stu-id="18cac-227">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="18cac-228">查看搜索结果时，Teams 频道中机器人生成的卡内容具有发件人 **/** 作者电子邮件属性，其中生成卡内容的应用 `<appname>@teams.microsoft.com` `appname` 的名称。</span><span class="sxs-lookup"><span data-stu-id="18cac-228">When reviewing search results, card content generated by bots in a Teams channel has the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="18cac-229">如果卡内容是由用户生成的，则 **发送方/作者的值将** 标识该用户。</span><span class="sxs-lookup"><span data-stu-id="18cac-229">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

<span data-ttu-id="18cac-230">在内容搜索结果中查看卡片内容时，内容显示为邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="18cac-230">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="18cac-231">将命名附件 `appname.html` ，其中， `appname` 生成卡内容的应用的名称。</span><span class="sxs-lookup"><span data-stu-id="18cac-231">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="18cac-232">以下屏幕截图显示名为 Asana (应用的卡片内容) Teams 和搜索结果的显示方式。</span><span class="sxs-lookup"><span data-stu-id="18cac-232">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

<span data-ttu-id="18cac-233">**Teams 中的卡片内容**</span><span class="sxs-lookup"><span data-stu-id="18cac-233">**Card content in Teams**</span></span>

![Teams 频道消息中的卡片内容](media/CardContentTeams.png)

<span data-ttu-id="18cac-235">**搜索结果中的卡片内容**</span><span class="sxs-lookup"><span data-stu-id="18cac-235">**Card content in search results**</span></span>
  
![内容搜索结果中的相同卡内容](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> <span data-ttu-id="18cac-237">若要在此时在搜索结果中显示卡内容的图像 (如上一屏幕截图) 中的勾号，你必须在用于查看搜索结果的同一浏览器会话的不同选项卡中登录到 Teams (。 https://teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="18cac-237">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="18cac-238">否则会显示图像占位符。</span><span class="sxs-lookup"><span data-stu-id="18cac-238">Otherwise, image placeholders are displayed.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="18cac-239">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="18cac-239">Advanced eDiscovery</span></span>

<span data-ttu-id="18cac-240">也可使用高级电子数据展示工作流搜索和保留某些 Microsoft Teams [内容](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="18cac-240">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="18cac-241">虽然电子数据展示提供了一系列搜索、保留和导出功能，但高级电子数据展示为合规性管理员提供了更多工具来识别数据源并分析其内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-241">While eDiscovery provides a range of search, hold, and export functionality, Advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="18cac-242">Teams 内容的高级电子数据展示管理员工作流</span><span class="sxs-lookup"><span data-stu-id="18cac-242">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="18cac-243">管理员可能是各种团队的成员。</span><span class="sxs-lookup"><span data-stu-id="18cac-243">Custodians might be a member of various teams.</span></span> <span data-ttu-id="18cac-244">你可以捕获与这些管理员相关的 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-244">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="18cac-245">有关监管员工作流的说明，请参阅"[将管理员添加到高级电子数据展示案例"。](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)</span><span class="sxs-lookup"><span data-stu-id="18cac-245">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="18cac-246">添加管理员后，单击"下 **一步"** 按钮，然后单击" **添加"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="18cac-246">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="18cac-247">随后将显示一个窗口，提示您选择其他位置，该窗口将显示管理员的所有成员身份及其数据的相应 SharePoint 网站位置。</span><span class="sxs-lookup"><span data-stu-id="18cac-247">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="18cac-248">从所有这些数据源和团队中，您可以选择要用于电子数据展示的内容，然后将该用户和已标识的所有数据源放在保留状态。</span><span class="sxs-lookup"><span data-stu-id="18cac-248">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="18cac-249">可以选择是包括 Exchange 内容、OneDrive 内容还是两者。</span><span class="sxs-lookup"><span data-stu-id="18cac-249">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="18cac-250">Exchange 内容包括用户邮箱中所有应用程序内容，例如其电子邮件、存储在其邮箱中的 Teams 内容，等等。</span><span class="sxs-lookup"><span data-stu-id="18cac-250">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="18cac-251">OneDrive 内容不仅包括用户的内容，还包括 OneDrive 中存储的所有 Teams 内容，例如 1：1 聊天、1：N 聊天和聊天中共享的文件。</span><span class="sxs-lookup"><span data-stu-id="18cac-251">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="18cac-252">您还可以选择关联监管员是其中成员的任何团队，以便包括监管员有权访问的频道聊天消息和文件。</span><span class="sxs-lookup"><span data-stu-id="18cac-252">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="18cac-253">此外，任何其他团队都可以与监管员相关联。</span><span class="sxs-lookup"><span data-stu-id="18cac-253">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="18cac-254">私人频道中 [消息和文件](private-channels.md) 电子数据展示的工作方式与标准通道中的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="18cac-254">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="18cac-255">若要了解有关详细信息，请参阅 [专用通道的电子数据展示](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="18cac-255">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="18cac-256">保留数据源</span><span class="sxs-lookup"><span data-stu-id="18cac-256">Placing a data source on hold</span></span>

<span data-ttu-id="18cac-257">如果没有特定用户指定为监管员，您可以保留整个数据源。</span><span class="sxs-lookup"><span data-stu-id="18cac-257">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="18cac-258">有关保留详细信息，请参阅["管理高级电子数据展示中的保留"。](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)</span><span class="sxs-lookup"><span data-stu-id="18cac-258">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="18cac-259">为 Teams 内容创建保留时，可以选择要包括在保留中的所有位置。</span><span class="sxs-lookup"><span data-stu-id="18cac-259">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="18cac-260">即使用户正在删除或更改内容，保留也将保留该内容的所有以前版本的副本。</span><span class="sxs-lookup"><span data-stu-id="18cac-260">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="18cac-261">还可使用可选查询，根据关键字、日期范围、作者和许多其他条件设置保留条件。</span><span class="sxs-lookup"><span data-stu-id="18cac-261">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="18cac-262">如果未指定关键字，则来自该数据源的所有内容都将受到保留。</span><span class="sxs-lookup"><span data-stu-id="18cac-262">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="18cac-263">高级电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="18cac-263">Advanced eDiscovery searches</span></span>

<span data-ttu-id="18cac-264">还可以搜索 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-264">Teams content can also be searched.</span></span> <span data-ttu-id="18cac-265">有关搜索详细信息，请参阅["在高级电子数据展示中收集案例的数据"。](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="18cac-265">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="18cac-266">即使一条消息与搜索查询匹配，搜索也将返回整个对话。</span><span class="sxs-lookup"><span data-stu-id="18cac-266">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="18cac-267">创建搜索查询时，可以选择监管员，以便搜索已选择的所有源。</span><span class="sxs-lookup"><span data-stu-id="18cac-267">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="18cac-268">还可以搜索非监管源，例如未映射到用户的 Teams 网站。</span><span class="sxs-lookup"><span data-stu-id="18cac-268">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="18cac-269">还可使用可选查询缩小 Teams 内容中的搜索范围。</span><span class="sxs-lookup"><span data-stu-id="18cac-269">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="18cac-270">创建并选中搜索后，会显示一个窗口，该窗口包含对所选搜索可以执行的其他详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="18cac-270">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="18cac-271">如果单击"统计信息"按钮，您可以查看有关搜索的统计信息，包括根据位置类型、内容的原始源以及内容位于组邮箱、单个用户邮箱还是 SharePoint 网站中的细分。</span><span class="sxs-lookup"><span data-stu-id="18cac-271">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="18cac-272">因此，可以看到哪些源对搜索结果有贡献。</span><span class="sxs-lookup"><span data-stu-id="18cac-272">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="18cac-273">还有一 **个"查询** "视图，可用于查看哪些单个关键字对结果有影响。</span><span class="sxs-lookup"><span data-stu-id="18cac-273">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="18cac-274">完成搜索后，可以单击"添加 **结果以审阅集** "按钮，并将其添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="18cac-274">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="18cac-275">有关评审集详细信息，请参阅本文稍后在 ["管理高级电子](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 数据展示和 [审阅](#review-sets-workflow) 集"工作流中的审阅集。</span><span class="sxs-lookup"><span data-stu-id="18cac-275">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="18cac-276">普通审阅集和会话审阅集</span><span class="sxs-lookup"><span data-stu-id="18cac-276">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="18cac-277">将搜索添加到评论集时，可以从普通审阅集或对话评审集进行选择。</span><span class="sxs-lookup"><span data-stu-id="18cac-277">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="18cac-278">普通审阅集类似于导出;它提供 Teams `.msg` 内容的单个文件，并且以基本视图显示内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-278">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="18cac-279">如果计划以后使用其他软件工具重新处理文件，通常使用普通审阅集。</span><span class="sxs-lookup"><span data-stu-id="18cac-279">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="18cac-280">对话审阅集提供了更直观、更线程的对话视图;它以正确的顺序一起显示相关消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-280">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="18cac-281">![对话审阅集的屏幕截图](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="18cac-281">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="18cac-282">两种类型的评审集都提供修订等功能。</span><span class="sxs-lookup"><span data-stu-id="18cac-282">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="18cac-283">有关评审集详细信息，请参阅高级电子数据展示[中的"审阅对话"。](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)</span><span class="sxs-lookup"><span data-stu-id="18cac-283">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="18cac-284">集合选项</span><span class="sxs-lookup"><span data-stu-id="18cac-284">Collection options</span></span>

<span data-ttu-id="18cac-285">添加到评审集时，窗口的"集合选项"部分下有几个选项作为复选框提供 **，包括"** 对话检索选项"和 **"Teams 对话"。**</span><span class="sxs-lookup"><span data-stu-id="18cac-285">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="18cac-286">如果启用这些选项，则作为审阅集的一部分的任何单独的 Teams 消息也会显示，并包含附加消息用于上下文。</span><span class="sxs-lookup"><span data-stu-id="18cac-286">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="18cac-287">例如，如果查询是特定的，因此只返回一条消息，则启用这些选项还会返回多条消息，导致并遵循与查询匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-287">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="18cac-288">许多逻辑条件用于确定其他消息是否为匹配查询的消息提供上下文。</span><span class="sxs-lookup"><span data-stu-id="18cac-288">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="18cac-289">例如，对于 Teams 内容，启用这些选项将检索父消息以及所有子消息，因为消息的线程处理方式。</span><span class="sxs-lookup"><span data-stu-id="18cac-289">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="18cac-290">还会检查邮件时间戳。</span><span class="sxs-lookup"><span data-stu-id="18cac-290">Message time stamps are also checked.</span></span> <span data-ttu-id="18cac-291">如果消息与查询匹配，则 4 小时内位于其前的相邻消息或 4 小时内的相邻消息被视为聊天的一部分，并且也会包含在结果中。</span><span class="sxs-lookup"><span data-stu-id="18cac-291">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="18cac-292">如果必须确定将返回哪些上下文消息，但与搜索查询匹配，则不需要使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="18cac-292">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="18cac-293">可以收集所有内容，也可以扩大搜索的日期范围，以便查询后返回更多消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-293">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="18cac-294">审阅集工作流</span><span class="sxs-lookup"><span data-stu-id="18cac-294">Review sets workflow</span></span>

<span data-ttu-id="18cac-295">可以通过单击"审阅集"选项卡查看现有审阅集 **或创建新** 审阅集。有关评审集详细信息，请参阅"[管理高级电子数据展示中的审阅集"。](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)</span><span class="sxs-lookup"><span data-stu-id="18cac-295">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="18cac-296">除了文档，还可以向审阅集添加电子邮件、Teams 消息、Yammer 消息和其他内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-296">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="18cac-297">在评审集内，还可以执行可在其他上下文中执行的许多相同操作，例如搜索内容和创建自定义查询。</span><span class="sxs-lookup"><span data-stu-id="18cac-297">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="18cac-298">这些操作仅适用于已添加到评审集的项。</span><span class="sxs-lookup"><span data-stu-id="18cac-298">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="18cac-299">" **管理审阅集** "按钮提供了其他选项，例如分析、摘要报告、已添加的负载集数等。</span><span class="sxs-lookup"><span data-stu-id="18cac-299">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="18cac-300">若要访问数据的可视化效果和图表，请单击右上角的"单个 **结果** 搜索 \> 配置文件"视图。</span><span class="sxs-lookup"><span data-stu-id="18cac-300">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="18cac-301">可以单击这些图表中的"拨片"以交互方式选择要查询的内容类型。</span><span class="sxs-lookup"><span data-stu-id="18cac-301">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="18cac-302">例如，可以选择仅查询 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-302">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="18cac-303">也可以保存这些查询，就像保存手动写入的查询一样。</span><span class="sxs-lookup"><span data-stu-id="18cac-303">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="18cac-304">摘要视图、文本视图和批注视图</span><span class="sxs-lookup"><span data-stu-id="18cac-304">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="18cac-305">如果在评论集内单击 Teams 对话，它将显示"摘要"视图，该视图将整个 Teams 对话显示为可单独交互的消息列表。</span><span class="sxs-lookup"><span data-stu-id="18cac-305">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="18cac-306">单击邮件右侧向下箭头可显示一个上下文菜单，允许您查看消息详细信息或下载单个 `.msg` 文件。</span><span class="sxs-lookup"><span data-stu-id="18cac-306">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="18cac-307">单击消息详细信息会显示元数据摘要或消息的完整元数据。</span><span class="sxs-lookup"><span data-stu-id="18cac-307">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="18cac-308">若要下载 PDF，请单击摘要视图右上角的下载按钮。</span><span class="sxs-lookup"><span data-stu-id="18cac-308">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="18cac-309">单击 **"文本视图** "选项卡可显示 Teams 对话提取文本的纯文本视图。</span><span class="sxs-lookup"><span data-stu-id="18cac-309">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="18cac-310">此纯文本内容适用于导出，可以使用其他软件工具轻松使用它。</span><span class="sxs-lookup"><span data-stu-id="18cac-310">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="18cac-311">单击" **批注视图"选项卡** 访问批注功能。</span><span class="sxs-lookup"><span data-stu-id="18cac-311">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="18cac-312">此选项卡以类似于 Teams 对话的格式显示内容，但还有其他编辑选项。</span><span class="sxs-lookup"><span data-stu-id="18cac-312">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="18cac-313">有一个铅笔工具可用于做笔记、在邮件上绘图或执行精细的划掉以用于修订。</span><span class="sxs-lookup"><span data-stu-id="18cac-313">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="18cac-314">还有 **一个"** 区域修订"工具，可用于绘制一个矩形，用于将该区域标记为"修订"。</span><span class="sxs-lookup"><span data-stu-id="18cac-314">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="18cac-315">下面是用户之间线程聊天的修订文件示例。</span><span class="sxs-lookup"><span data-stu-id="18cac-315">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="18cac-316">![已修订文件的屏幕截图](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="18cac-316">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="18cac-317">"批注视图 **"选项卡的底部** 是" **标记文档** "按钮，它显示标记面板。</span><span class="sxs-lookup"><span data-stu-id="18cac-317">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="18cac-318">在此面板中，可以将标记应用到 Teams 对话内的所有消息。</span><span class="sxs-lookup"><span data-stu-id="18cac-318">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="18cac-319">可以将聊天标记为响应性或非响应性、特权或非特权，包括是否包含"有趣项"、是否应包含在导出中，以及是否需要进一步评审。</span><span class="sxs-lookup"><span data-stu-id="18cac-319">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="18cac-320">还可以管理和应用其他可自定义的标记。</span><span class="sxs-lookup"><span data-stu-id="18cac-320">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="18cac-321">操作菜单</span><span class="sxs-lookup"><span data-stu-id="18cac-321">Action menu</span></span>

<span data-ttu-id="18cac-322">在"审阅集"窗口中，可以通过单击"操作 **导出"导出** \> **内容**。</span><span class="sxs-lookup"><span data-stu-id="18cac-322">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="18cac-323">导出时有许多选项可用。</span><span class="sxs-lookup"><span data-stu-id="18cac-323">There are many options available when exporting.</span></span>

<span data-ttu-id="18cac-324">若要导出包含所有 Teams 消息的所有元数据的文件，请单击以选中"加载 **文件"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="18cac-324">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="18cac-325">若要在文件中包括已应用到内容的任何标记，请单击以选中"标记 **"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="18cac-325">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="18cac-326">使用 **"本机文件"** 选项以本机格式导出文件。</span><span class="sxs-lookup"><span data-stu-id="18cac-326">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="18cac-327">您可以选择将对话导出为一个文件，或者将单个聊天消息导出到它们自己的单独文件中。</span><span class="sxs-lookup"><span data-stu-id="18cac-327">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="18cac-328">" **文本文件"** 选项允许您保存纯文本版本的内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-328">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="18cac-329">若要详细了解如何在评论集内获取 Teams 对话的纯文本视图，请参阅上面的摘要视图、文本视图和 [批注](#summary-view-text-view-and-annotate-view) 视图。</span><span class="sxs-lookup"><span data-stu-id="18cac-329">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="18cac-330">如果按照上述"摘要视图、文本视图"和"批注视图[](#summary-view-text-view-and-annotate-view)"部分中所述对内容应用了任何修订，可以选择"将修订的本机文件替换为转换后的 PDF"选项，以 PDF 格式将本机文件替换为转换后的副本。</span><span class="sxs-lookup"><span data-stu-id="18cac-330">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="18cac-331">可以选择导出到 Microsoft 提供的 Azure Blob 存储容器，也可以提供自己的 Azure Blob 存储容器。</span><span class="sxs-lookup"><span data-stu-id="18cac-331">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="18cac-332">准备好开始导出过程时，请单击"导出 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="18cac-332">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="18cac-333">请参阅 ["下载导出](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 作业"，详细了解如何在导出完成后访问 Azure Blob 存储容器并下载导出的内容。</span><span class="sxs-lookup"><span data-stu-id="18cac-333">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="18cac-334">导出可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="18cac-334">Exporting can take an extended period of time.</span></span> <span data-ttu-id="18cac-335">若要跟踪导出过程的状态，请退出"审阅集 **"选项卡，** 然后单击"导出 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="18cac-335">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18cac-336">相关主题</span><span class="sxs-lookup"><span data-stu-id="18cac-336">Related topics</span></span>

- [<span data-ttu-id="18cac-337">Microsoft 365 中的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="18cac-337">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="18cac-338">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="18cac-338">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
