---
title: 执行内容的电子数据展示调查
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
description: 了解在需要提交所有电子数据展示信息以进行行程时要执行的操作。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4679d8ed59ab8eec0fb856961f646d1f20049ff3
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814108"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="018d1-103">在 Microsoft Teams 中对内容进行电子数据展示调查</span><span class="sxs-lookup"><span data-stu-id="018d1-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="018d1-104">大型企业通常会面向要求使用热门合法定规定的要求将所有电子信息提交商业 (ESI) 。</span><span class="sxs-lookup"><span data-stu-id="018d1-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="018d1-105">可在电子数据展示调查期间搜索和使用 Microsoft Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="018d1-106">概述</span><span class="sxs-lookup"><span data-stu-id="018d1-106">Overview</span></span>

<span data-ttu-id="018d1-107">所有 Microsoft Teams 1：1 或群组聊天都通过各自的用户的邮箱进行逐步写入。</span><span class="sxs-lookup"><span data-stu-id="018d1-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="018d1-108">所有标准频道邮件都将通过代表团队的组邮箱进行日记。</span><span class="sxs-lookup"><span data-stu-id="018d1-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="018d1-109">在标准频道中上传的文件将在 SharePoint Online 和 OneDrive for Business 的电子数据展示功能下介绍。</span><span class="sxs-lookup"><span data-stu-id="018d1-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="018d1-110">私人频道中的消息和文件的电子数据展示 [与](private-channels.md) 标准频道中的操作有所不同。</span><span class="sxs-lookup"><span data-stu-id="018d1-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="018d1-111">若要了解详细信息 [，请参阅专用频道的电子数据展示](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="018d1-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="018d1-112">并非所有 Teams 内容都是可发现。</span><span class="sxs-lookup"><span data-stu-id="018d1-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="018d1-113">下表显示了可通过电子数据展示找到的内容类型。</span><span class="sxs-lookup"><span data-stu-id="018d1-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="018d1-114">内容类型</span><span class="sxs-lookup"><span data-stu-id="018d1-114">Content type</span></span> | <span data-ttu-id="018d1-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="018d1-115">eDiscoverable</span></span> | <span data-ttu-id="018d1-116">注释</span><span class="sxs-lookup"><span data-stu-id="018d1-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="018d1-117">Teams 聊天消息</span><span class="sxs-lookup"><span data-stu-id="018d1-117">Teams chat messages</span></span> | <span data-ttu-id="018d1-118">是</span><span class="sxs-lookup"><span data-stu-id="018d1-118">Yes</span></span> |  |
| <span data-ttu-id="018d1-119">私人频道消息</span><span class="sxs-lookup"><span data-stu-id="018d1-119">Private channel messages</span></span> | <span data-ttu-id="018d1-120">是</span><span class="sxs-lookup"><span data-stu-id="018d1-120">Yes</span></span> | |
| <span data-ttu-id="018d1-121">频道名称</span><span class="sxs-lookup"><span data-stu-id="018d1-121">Name of channel</span></span> | <span data-ttu-id="018d1-122">否</span><span class="sxs-lookup"><span data-stu-id="018d1-122">No</span></span> | |
| <span data-ttu-id="018d1-123">会议 IM 对话</span><span class="sxs-lookup"><span data-stu-id="018d1-123">Meeting IM conversations</span></span> | <span data-ttu-id="018d1-124">是</span><span class="sxs-lookup"><span data-stu-id="018d1-124">Yes</span></span> | |
| <span data-ttu-id="018d1-125">会议元数据<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="018d1-125">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="018d1-126">是</span><span class="sxs-lookup"><span data-stu-id="018d1-126">Yes</span></span> |  |
| <span data-ttu-id="018d1-127">已编辑的邮件</span><span class="sxs-lookup"><span data-stu-id="018d1-127">Edited messages</span></span> | <span data-ttu-id="018d1-128">是</span><span class="sxs-lookup"><span data-stu-id="018d1-128">Yes</span></span> | <span data-ttu-id="018d1-129">如果用户处于保留状态，则会保留以前版本的编辑消息。</span><span class="sxs-lookup"><span data-stu-id="018d1-129">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="018d1-130">表情符号、GF、贴光</span><span class="sxs-lookup"><span data-stu-id="018d1-130">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="018d1-131">是</span><span class="sxs-lookup"><span data-stu-id="018d1-131">Yes</span></span> | |
| <span data-ttu-id="018d1-132">代码片段</span><span class="sxs-lookup"><span data-stu-id="018d1-132">Code snippets</span></span> | <span data-ttu-id="018d1-133">否</span><span class="sxs-lookup"><span data-stu-id="018d1-133">No</span></span> | |
| <span data-ttu-id="018d1-134">聊天链接</span><span class="sxs-lookup"><span data-stu-id="018d1-134">Chat links</span></span> | <span data-ttu-id="018d1-135">是</span><span class="sxs-lookup"><span data-stu-id="018d1-135">Yes</span></span> | |
| <span data-ttu-id="018d1-136">对喜 (、听到心等的反应包括) </span><span class="sxs-lookup"><span data-stu-id="018d1-136">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="018d1-137">否</span><span class="sxs-lookup"><span data-stu-id="018d1-137">No</span></span> | |
| <span data-ttu-id="018d1-138">嵌入式图像</span><span class="sxs-lookup"><span data-stu-id="018d1-138">Inline images</span></span> | <span data-ttu-id="018d1-139">是</span><span class="sxs-lookup"><span data-stu-id="018d1-139">Yes</span></span> | |
| <span data-ttu-id="018d1-140">表</span><span class="sxs-lookup"><span data-stu-id="018d1-140">Tables</span></span> | <span data-ttu-id="018d1-141">是</span><span class="sxs-lookup"><span data-stu-id="018d1-141">Yes</span></span> | |
| <span data-ttu-id="018d1-142">主题</span><span class="sxs-lookup"><span data-stu-id="018d1-142">Subject</span></span> | <span data-ttu-id="018d1-143">是</span><span class="sxs-lookup"><span data-stu-id="018d1-143">Yes</span></span> | |
| <span data-ttu-id="018d1-144">引号</span><span class="sxs-lookup"><span data-stu-id="018d1-144">Quotes</span></span> | <span data-ttu-id="018d1-145">是</span><span class="sxs-lookup"><span data-stu-id="018d1-145">Yes</span></span> | <span data-ttu-id="018d1-146">可以搜索引发的内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-146">Quoted content is searchable.</span></span> <span data-ttu-id="018d1-147">但是，搜索结果并不指明内容已引号。</span><span class="sxs-lookup"><span data-stu-id="018d1-147">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="018d1-148">音频录制</span><span class="sxs-lookup"><span data-stu-id="018d1-148">Audio recordings</span></span> | <span data-ttu-id="018d1-149">否</span><span class="sxs-lookup"><span data-stu-id="018d1-149">No</span></span> | |

<span data-ttu-id="018d1-150"><sup>1</sup> 会议元数据包括：</span><span class="sxs-lookup"><span data-stu-id="018d1-150"><sup>1</sup> Meeting metadata includes the following:</span></span>

- <span data-ttu-id="018d1-151">会议或通话开始时间和结束时间以及持续时间</span><span class="sxs-lookup"><span data-stu-id="018d1-151">Meeting or call start and end time, and duration</span></span>
- <span data-ttu-id="018d1-152">呼叫/加入和关注每个参与者的活动</span><span class="sxs-lookup"><span data-stu-id="018d1-152">Call/Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="018d1-153">VOIP 加入/呼叫</span><span class="sxs-lookup"><span data-stu-id="018d1-153">VOIP join/calls</span></span>
- <span data-ttu-id="018d1-154">匿名加入</span><span class="sxs-lookup"><span data-stu-id="018d1-154">Anonymous join</span></span>
- <span data-ttu-id="018d1-155">联合用户加入</span><span class="sxs-lookup"><span data-stu-id="018d1-155">Federated user join</span></span>
- <span data-ttu-id="018d1-156">来宾用户加入</span><span class="sxs-lookup"><span data-stu-id="018d1-156">Guest user join</span></span>

<span data-ttu-id="018d1-157">该图像显示了元数据示例。</span><span class="sxs-lookup"><span data-stu-id="018d1-157">The image shows an example of the metadata.</span></span>

![图像为 CVR 记录会议元数据。](media/conversationOption3.png)

<span data-ttu-id="018d1-159">下面是会议期间参与者之间的 IM 对话的示例。</span><span class="sxs-lookup"><span data-stu-id="018d1-159">Here's an example of IM conversation between participants during the meeting.</span></span>

![参与者之间对话的图像。](media/MeetingIMConversations.png)

![参与者之间对话的图像。](media/MeetingImConversation2.png)

<span data-ttu-id="018d1-162">若要与 Microsoft Teams 内容实现电子数据展示调查，请查看"小本电子数据展示"入门 [中的步骤](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)1。</span><span class="sxs-lookup"><span data-stu-id="018d1-162">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="018d1-163">Microsoft Teams 数据在 Excel 电子数据展示导出输出中显示为即时消息或对话。</span><span class="sxs-lookup"><span data-stu-id="018d1-163">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="018d1-164">可以在 `.pst` Outlook 中打开该文件，以便导出后查看这些邮件。</span><span class="sxs-lookup"><span data-stu-id="018d1-164">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

<span data-ttu-id="018d1-165">查看该团队的 .pst 文件时，所有对话会保存在"对话历史记录"下的"工作组聊天"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="018d1-165">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="018d1-166">该邮件标题包含团队名称和频道名称。</span><span class="sxs-lookup"><span data-stu-id="018d1-166">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="018d1-167">例如，下图显示了 Bob 发出的消息向 Bob 发送了制造计划团队的 Project 7 标准频道。</span><span class="sxs-lookup"><span data-stu-id="018d1-167">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook 中用户邮箱中的"团队聊天"文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="018d1-169">用户邮箱中的私有聊天存储在"对话历史记录"下的"团队聊天"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="018d1-169">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="018d1-170">电子数据展示私人频道</span><span class="sxs-lookup"><span data-stu-id="018d1-170">eDiscovery of private channels</span></span>

<span data-ttu-id="018d1-171">在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。</span><span class="sxs-lookup"><span data-stu-id="018d1-171">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="018d1-172">记录的标题已格式化为指示它们是从哪个私人频道发送的。</span><span class="sxs-lookup"><span data-stu-id="018d1-172">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="018d1-173">由于每个专用频道都具有自己的独立于父团队网站的 SharePoint 网站集，因此专用频道中的文件可独立于父团队管理。</span><span class="sxs-lookup"><span data-stu-id="018d1-173">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="018d1-174">Teams 不支持在团队中搜索单个频道的电子数据展示搜索，因此必须对整个团队进行搜索。</span><span class="sxs-lookup"><span data-stu-id="018d1-174">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="018d1-175">若要对专用频道中的内容执行电子数据展示搜索，请在以下所有团队中搜索内容，与专用频道集关联的网站集 (包括文件) 和专用频道成员 (以包括消息) 。</span><span class="sxs-lookup"><span data-stu-id="018d1-175">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="018d1-176">使用以下步骤识别专用频道中的文件和消息以包括在电子数据展示搜索中。</span><span class="sxs-lookup"><span data-stu-id="018d1-176">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="018d1-177">在电子数据展示搜索中包括专用通道文件</span><span class="sxs-lookup"><span data-stu-id="018d1-177">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="018d1-178">执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="018d1-178">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="018d1-179">运行以下操作获取与团队中的私人频道相关联的所有 SharePoint 网站集的列表。</span><span class="sxs-lookup"><span data-stu-id="018d1-179">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="018d1-180">运行以下 PowerShell 脚本可获取与团队和父团队组 ID 中的专用频道关联的所有 SharePoint 网站集 URL 的列表。</span><span class="sxs-lookup"><span data-stu-id="018d1-180">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="018d1-181">对于每个团队或组 ID，运行以下 PowerShell 脚本以识别所有相关私人频道网站，其中$groupID是团队的组 ID。</span><span class="sxs-lookup"><span data-stu-id="018d1-181">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="018d1-182">在电子数据展示搜索中包括专用通道消息</span><span class="sxs-lookup"><span data-stu-id="018d1-182">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="018d1-183">执行这些步骤之前，请确保安装 [了最新版本的 Teams PowerShell 模块](teams-powershell-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="018d1-183">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="018d1-184">运行以下命令可获取团队中的私人频道列表。</span><span class="sxs-lookup"><span data-stu-id="018d1-184">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="018d1-185">运行以下命令可获取专用频道成员的列表。</span><span class="sxs-lookup"><span data-stu-id="018d1-185">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="018d1-186">将团队中每个专用频道中的所有成员的邮箱包含在电子数据展示搜索查询中。</span><span class="sxs-lookup"><span data-stu-id="018d1-186">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="018d1-187">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="018d1-187">Advanced eDiscovery</span></span>

<span data-ttu-id="018d1-188">还可以使用高级电子数据展示工作流搜索和 [保留某些](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)Microsoft Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-188">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="018d1-189">电子数据展示提供一系列搜索、保持和导出功能，但是高级电子数据展示提供了更多工具，可识别数据源并分析其内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-189">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="018d1-190">Teams 内容的高级电子数据展示环境工作流</span><span class="sxs-lookup"><span data-stu-id="018d1-190">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="018d1-191">"语言管理器"可能是各种团队的成员。</span><span class="sxs-lookup"><span data-stu-id="018d1-191">Custodians might be a member of various teams.</span></span> <span data-ttu-id="018d1-192">你可以捕获与这些维斯使用的 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-192">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="018d1-193">有关维兰工作流的背景和说明，请参阅 ["高级电子数据展示"工作流](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="018d1-193">For background and instructions on the custodian workflow, see [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span>

<span data-ttu-id="018d1-194">添加卡通亚语后，单击"下一步" **按钮，** 然后单击"添加 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="018d1-194">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="018d1-195">随后会显示一个窗口，提示您选择其他位置，该窗口将向您显示您的所有和员工的成员身份及其数据对应的 SharePoint 网站位置。</span><span class="sxs-lookup"><span data-stu-id="018d1-195">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="018d1-196">在所有这些数据源和团队中，可选择要用于电子数据展示的内容，然后保留该用户以及所有已在保留的数据源中。</span><span class="sxs-lookup"><span data-stu-id="018d1-196">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="018d1-197">可以选择是否包含其 Exchange 内容及其 OneDrive 内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-197">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="018d1-198">Exchange 内容包括用户邮箱中的所有应用程序内容，如电子邮件、存储在其邮箱中的 Teams 内容等等。</span><span class="sxs-lookup"><span data-stu-id="018d1-198">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="018d1-199">OneDrive 内容不仅包括用户的内容，还包括存储在 OneDrive 中的所有 Teams 内容，例如 1：1 聊天、1：N 聊天以及在聊天中共享的文件。</span><span class="sxs-lookup"><span data-stu-id="018d1-199">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="018d1-200">此外，您还可以选择将该聊天机员兼容为一名团队，因此，系统包含该聊天机制可访问的频道聊天消息和文件。</span><span class="sxs-lookup"><span data-stu-id="018d1-200">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="018d1-201">此外，任何其他团队还可以与您的加人关联。</span><span class="sxs-lookup"><span data-stu-id="018d1-201">Additionally, any other team can be associated with a custodian.</span></span> <span data-ttu-id="018d1-202">有关详细信息，请参阅 [向高级电子数据展示事例添加技能人员](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="018d1-202">For more information, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

> [!NOTE]
> <span data-ttu-id="018d1-203">私人频道中的消息和文件的电子数据展示 [与](private-channels.md) 标准频道中的操作有所不同。</span><span class="sxs-lookup"><span data-stu-id="018d1-203">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="018d1-204">若要了解详细信息 [，请参阅专用频道的电子数据展示](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="018d1-204">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="018d1-205">保留数据源</span><span class="sxs-lookup"><span data-stu-id="018d1-205">Placing a data source on hold</span></span>

<span data-ttu-id="018d1-206">如果没有指定为回收器的特定用户，则可以保留整个数据源。</span><span class="sxs-lookup"><span data-stu-id="018d1-206">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="018d1-207">有关保留的详细信息，请参阅高级 [电子数据展示中的"管理保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)"。</span><span class="sxs-lookup"><span data-stu-id="018d1-207">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="018d1-208">为 Teams 内容创建保留时，可以选择希望在保留中包含的所有位置。</span><span class="sxs-lookup"><span data-stu-id="018d1-208">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="018d1-209">即使用户删除或更改内容，保留会保留所有早期版本内容的副本。</span><span class="sxs-lookup"><span data-stu-id="018d1-209">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="018d1-210">您也可以使用可选查询根据关键字、日期范围、作者和其他许多条件设置保留条件。</span><span class="sxs-lookup"><span data-stu-id="018d1-210">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="018d1-211">如果不指定任何关键字，则该数据源中的所有内容将保留。</span><span class="sxs-lookup"><span data-stu-id="018d1-211">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="018d1-212">高级电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="018d1-212">Advanced eDiscovery searches</span></span>

<span data-ttu-id="018d1-213">还可以搜索 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-213">Teams content can also be searched.</span></span> <span data-ttu-id="018d1-214">有关搜索的详细信息，请参阅"高级电子数据展示"中的 [事例数据](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="018d1-214">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="018d1-215">如果即使一条邮件与搜索查询匹配，搜索也将返回整个对话。</span><span class="sxs-lookup"><span data-stu-id="018d1-215">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="018d1-216">创建搜索查询时，你可以选择"库"，以便搜索已选择的所有源。</span><span class="sxs-lookup"><span data-stu-id="018d1-216">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="018d1-217">也可以搜索不可信来源（例如未映射到用户的 Teams 网站）的非可信来源。</span><span class="sxs-lookup"><span data-stu-id="018d1-217">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="018d1-218">可选查询还可以用于缩小 Teams 内容中搜索范围的范围。</span><span class="sxs-lookup"><span data-stu-id="018d1-218">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="018d1-219">在创建搜索并选中搜索之后，将显示一个窗口，其中包含可对所选搜索执行的其他详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="018d1-219">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="018d1-220">如果单击" **统计信息"** 按钮，您可以查看有关搜索的统计信息，包括按位置类型细分、内容的原始来源，以及内容是否位于组邮箱、单个用户邮箱或 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="018d1-220">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="018d1-221">因此，你可以查看有关源会为搜索结果提供怎一些细目。</span><span class="sxs-lookup"><span data-stu-id="018d1-221">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="018d1-222">也有一 **个可用的查询** 视图，以便您可以查看哪些单个关键字在您的结果中提供。</span><span class="sxs-lookup"><span data-stu-id="018d1-222">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="018d1-223">完成搜索后，可以单击"添加结果"以查看集 **合按钮** 并将其添加到评论集。</span><span class="sxs-lookup"><span data-stu-id="018d1-223">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="018d1-224">有关审阅集的详细信息，请参阅本文后面的"高级 [电](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 子数据展示"和"审阅 [设置"工作](#review-sets-workflow) 流。</span><span class="sxs-lookup"><span data-stu-id="018d1-224">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="018d1-225">普通审阅集和对话评审集</span><span class="sxs-lookup"><span data-stu-id="018d1-225">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="018d1-226">将搜索添加到审阅集时，可从普通审阅集或对话检查集中进行选择。</span><span class="sxs-lookup"><span data-stu-id="018d1-226">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="018d1-227">"正常的评论"集与导出类似;还为 Teams 内容提供单独 `.msg` 的文件，并以基本视图显示内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-227">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="018d1-228">如果计划以后使用其他软件工具重新处理文件，通常会使用正常的审阅集。</span><span class="sxs-lookup"><span data-stu-id="018d1-228">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="018d1-229">对话审阅集提供对话的更直线程度的线程视图;它按正确的顺序一并显示相关邮件。</span><span class="sxs-lookup"><span data-stu-id="018d1-229">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

![对话审阅集的屏幕截图](media/conversationOptions2.png)

<span data-ttu-id="018d1-231">两种类型的审阅集均提供了这样的功能，如重新拨出。</span><span class="sxs-lookup"><span data-stu-id="018d1-231">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="018d1-232">有关查看集的详细信息，请参阅 [高级电子数据展示中的"查看对话](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)"。</span><span class="sxs-lookup"><span data-stu-id="018d1-232">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="018d1-233">集合选项</span><span class="sxs-lookup"><span data-stu-id="018d1-233">Collection options</span></span>

<span data-ttu-id="018d1-234">添加到审阅集时，窗口的"集合选项"部分下有多个可用选项，其中包括"**Collection Options**对话检索**选项"和\*\*\*\*"团队对话**"。</span><span class="sxs-lookup"><span data-stu-id="018d1-234">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="018d1-235">如果启用这些选项，则作为查看集的一部分的任何单独 Teams 消息，其中附加的消息会显示在上下文中。</span><span class="sxs-lookup"><span data-stu-id="018d1-235">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="018d1-236">例如，如果查询非常具体并且只返回一条消息，因此，启用这些选项还将返回使以下一封邮件组成的值，并跟后与您的查询相匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="018d1-236">For example, if your query is very specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="018d1-237">许多逻辑条件用于确定邮件是否对与您的查询相匹配的邮件提供上下文。</span><span class="sxs-lookup"><span data-stu-id="018d1-237">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="018d1-238">例如，对于 Teams 内容，启用这些选项可以检索父消息以及由于消息的来看方式的所有子件。</span><span class="sxs-lookup"><span data-stu-id="018d1-238">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="018d1-239">还会选中消息时间戳。</span><span class="sxs-lookup"><span data-stu-id="018d1-239">Message time stamps are also checked.</span></span> <span data-ttu-id="018d1-240">如果一封邮件与您的查询相匹配，则缩略邮件位于 4 个小时之内的时间段内或者其后面 4 小时的邮件被视为对话的一部分，且也包含在筛选结果中。</span><span class="sxs-lookup"><span data-stu-id="018d1-240">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="018d1-241">如果必须确定哪些上下文消息将与搜索查询匹配的匹配项返回，则不需要使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="018d1-241">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="018d1-242">可收集所有内容，也可加宽搜索的日期范围，以便由查询结果返回更多消息。</span><span class="sxs-lookup"><span data-stu-id="018d1-242">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="018d1-243">查看设置工作流</span><span class="sxs-lookup"><span data-stu-id="018d1-243">Review sets workflow</span></span>

<span data-ttu-id="018d1-244">您可以通过单击"审阅设置"选项卡查看现有的审阅 **集或创建新** 库。有关审阅集的详细信息，请参阅高级电子数据展示 [中的管理设置](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="018d1-244">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="018d1-245">除了文档，还可以在查看集合中添加电子邮件、Teams 消息、Yammer 消息和其他内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-245">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="018d1-246">在审阅集内，您还可以执行许多您可以在其他上下文中执行的相同操作，例如搜索内容和创建自定义查询。</span><span class="sxs-lookup"><span data-stu-id="018d1-246">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="018d1-247">这些操作仅适用于已添加到审阅集的项目。</span><span class="sxs-lookup"><span data-stu-id="018d1-247">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="018d1-248">" **管理审阅设置** "按钮提供其他选项，如分析、汇总报告、已添加的加载组数等。</span><span class="sxs-lookup"><span data-stu-id="018d1-248">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="018d1-249">若要访问数据的可视化效果和图表，请单击 **右**上角的 \> **"单个结果搜索** 个人资料"视图。</span><span class="sxs-lookup"><span data-stu-id="018d1-249">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="018d1-250">你可以单击这些图表中的边缘以交互方式选择要查询的内容类型。</span><span class="sxs-lookup"><span data-stu-id="018d1-250">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="018d1-251">例如，可以选择仅查询 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-251">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="018d1-252">你也可以保存这些查询，就像手动保存查询一样。</span><span class="sxs-lookup"><span data-stu-id="018d1-252">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="018d1-253">摘要视图、文本视图和注注视图</span><span class="sxs-lookup"><span data-stu-id="018d1-253">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="018d1-254">如果你单击评论集中的 Teams 对话，它会显示摘要 **视图**，其中显示整个 Teams 对话，作为你可以单独交互的消息列表。</span><span class="sxs-lookup"><span data-stu-id="018d1-254">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="018d1-255">单击邮件右侧的向下箭头可显示一个上下文菜单，该菜单允许您查看邮件详细信息或下载单个 `.msg` 文件。</span><span class="sxs-lookup"><span data-stu-id="018d1-255">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="018d1-256">单击邮件详细信息将向您显示邮件的元数据摘要或完整的元数据。</span><span class="sxs-lookup"><span data-stu-id="018d1-256">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="018d1-257">若要下载 PDF，请单击摘要视图右上方的下载按钮。</span><span class="sxs-lookup"><span data-stu-id="018d1-257">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="018d1-258">单击 **"文本** 视图"选项卡可显示 Teams 对话中提取的文本的纯文本视图。</span><span class="sxs-lookup"><span data-stu-id="018d1-258">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="018d1-259">此纯文本内容适合进行导出，您可以使用其他软件工具轻松使用该内容进行处理。</span><span class="sxs-lookup"><span data-stu-id="018d1-259">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="018d1-260">单击" **注阅视图"** 选项卡可以访问注文注明功能。</span><span class="sxs-lookup"><span data-stu-id="018d1-260">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="018d1-261">此选项卡以与 Teams 对话类相类的格式显示内容，但也有用于编辑的其他选项。</span><span class="sxs-lookup"><span data-stu-id="018d1-261">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="018d1-262">有一个可用于做笔记、在邮件上绘图或进行细化的集细边编以实现重新重复目的的移动工具。</span><span class="sxs-lookup"><span data-stu-id="018d1-262">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="018d1-263">这还有 **一个可以** 用来绘制用于将该区域突出的一个复原的框。</span><span class="sxs-lookup"><span data-stu-id="018d1-263">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="018d1-264">以下是用户间的线程对话的已重新阅读文件示例。</span><span class="sxs-lookup"><span data-stu-id="018d1-264">Here's an example of a redacted file for threaded conversation between users.</span></span>

!["保留的文件"的屏幕截图](media/RedactedFileExample.png)

<span data-ttu-id="018d1-266">"注音" **视图选项卡底部** 是"标记 **文档"** 按钮，它显示了"标记"面板。</span><span class="sxs-lookup"><span data-stu-id="018d1-266">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="018d1-267">在此面板中，你可以将标记应用到 Teams 对话中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="018d1-267">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="018d1-268">可将对话标记为响应或非响应、有权限或不特权限的形式标记它，无论它是否应包含"有趣的项目"，是否应包括在导出中，以及是否需要进一步的评论。</span><span class="sxs-lookup"><span data-stu-id="018d1-268">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="018d1-269">你也可以管理和应用其他可自定义标记。</span><span class="sxs-lookup"><span data-stu-id="018d1-269">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="018d1-270">操作菜单</span><span class="sxs-lookup"><span data-stu-id="018d1-270">Action menu</span></span>

<span data-ttu-id="018d1-271">在"审阅"设置窗口内，可以通过单击"操作导出 **"导出** \> **内容**。</span><span class="sxs-lookup"><span data-stu-id="018d1-271">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="018d1-272">导出时有许多可用选项。</span><span class="sxs-lookup"><span data-stu-id="018d1-272">There are many options available when exporting.</span></span>

<span data-ttu-id="018d1-273">要导出包含所有 Teams 邮件的所有元数据的文件，请单击以选中"加 **载文件** "复选框。</span><span class="sxs-lookup"><span data-stu-id="018d1-273">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="018d1-274">若要包括任何已应用于内容的标记，请单击以 **选择"标记"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="018d1-274">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="018d1-275">使用 **本机文件选项** 以文件本机格式导出文件。</span><span class="sxs-lookup"><span data-stu-id="018d1-275">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="018d1-276">您可以选择将对话导出为单独的文件中的单个文件或所有单独的聊天消息。</span><span class="sxs-lookup"><span data-stu-id="018d1-276">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="018d1-277">" **文本文件** "选项允许保存纯文本版本的内容。</span><span class="sxs-lookup"><span data-stu-id="018d1-277">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="018d1-278">有关如何以审阅集获取 Teams 对话的纯文本视图的详细信息，请参阅上方的"摘要视图"、" [文本](#summary-view-text-view-and-annotate-view) 视图"和"注解"。</span><span class="sxs-lookup"><span data-stu-id="018d1-278">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="018d1-279">如果你按上述"摘要"视图、文本视图和"注阅视图[Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view)"部分所述应用了任何内容缩写，您可以选择"将缩略缓存"选项替换为**转换后的 PDF**选项，以将本机文件替换为转换后的副本。</span><span class="sxs-lookup"><span data-stu-id="018d1-279">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="018d1-280">你可以选择导出到 Microsoft 提供的 Azure Blob 存储容器，也可以提供自己的 Azure Blob 存储容器。</span><span class="sxs-lookup"><span data-stu-id="018d1-280">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="018d1-281">准备好开始导出过程时，单击"导出 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="018d1-281">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="018d1-282">有关 [如何访问](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) Azure Blob 存储容器以及导出完成后下载导出内容的详细信息，请参阅下载导出作业。</span><span class="sxs-lookup"><span data-stu-id="018d1-282">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="018d1-283">导出可能需要更长的时间。</span><span class="sxs-lookup"><span data-stu-id="018d1-283">Exporting can take an extended period of time.</span></span> <span data-ttu-id="018d1-284">若要跟踪导出过程的状态，请退出"审 **阅"选项卡** 并单击" **导出"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="018d1-284">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="018d1-285">相关主题</span><span class="sxs-lookup"><span data-stu-id="018d1-285">Related topics</span></span>

- [<span data-ttu-id="018d1-286">Microsoft 365 中的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="018d1-286">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="018d1-287">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="018d1-287">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
