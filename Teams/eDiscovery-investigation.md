---
title: 对内容进行电子数据展示调查
author: LolaJacobsen
ms.author: hakank
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解需要执行电子数据展示时需要执行的操作，如需要提交所有电子存储的法律程序存储信息。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 67006fba94a58514fa33c91edd0a46312396b31a
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918580"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="81715-103">在 Microsoft Teams 中对内容进行电子数据展示调查</span><span class="sxs-lookup"><span data-stu-id="81715-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="81715-104">大型企业经常面临高处罚的法律诉讼，要求提交所有电子存储的信息（ESI）。</span><span class="sxs-lookup"><span data-stu-id="81715-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="81715-105">Microsoft 团队内容可在电子数据展示调查期间进行搜索和使用。</span><span class="sxs-lookup"><span data-stu-id="81715-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="81715-106">概述</span><span class="sxs-lookup"><span data-stu-id="81715-106">Overview</span></span>

<span data-ttu-id="81715-107">将向相应用户的邮箱中记录所有团队1:1 或群组聊天。</span><span class="sxs-lookup"><span data-stu-id="81715-107">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="81715-108">所有标准频道消息都将记录到代表团队的组邮箱。</span><span class="sxs-lookup"><span data-stu-id="81715-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="81715-109">在标准频道中上载的文件包含在 SharePoint Online 和 OneDrive for business 的电子数据展示功能下方。</span><span class="sxs-lookup"><span data-stu-id="81715-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="81715-110">电子数据展示[专用频道](private-channels.md)中的消息和文件的工作方式与在标准信道中的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="81715-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="81715-111">若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="81715-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="81715-112">并非所有团队内容都是 eDiscoverable。</span><span class="sxs-lookup"><span data-stu-id="81715-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="81715-113">下表显示了可以通过电子数据展示找到的内容类型。</span><span class="sxs-lookup"><span data-stu-id="81715-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="81715-114">内容类型</span><span class="sxs-lookup"><span data-stu-id="81715-114">Content type</span></span> | <span data-ttu-id="81715-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="81715-115">eDiscoverable</span></span> | <span data-ttu-id="81715-116">注释</span><span class="sxs-lookup"><span data-stu-id="81715-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="81715-117">团队聊天消息</span><span class="sxs-lookup"><span data-stu-id="81715-117">Teams chat messages</span></span> | <span data-ttu-id="81715-118">是</span><span class="sxs-lookup"><span data-stu-id="81715-118">Yes</span></span> | <span data-ttu-id="81715-119">聊天来自聊天的消息，其中来宾用户是1:1 或1： N 聊天中的唯一参与者不 eDiscoverable。</span><span class="sxs-lookup"><span data-stu-id="81715-119">Chat messages from chats where guest users are the only participants in a 1:1 or 1:N chat are not eDiscoverable.</span></span> |
| <span data-ttu-id="81715-120">录音</span><span class="sxs-lookup"><span data-stu-id="81715-120">Audio recordings</span></span> | <span data-ttu-id="81715-121">否</span><span class="sxs-lookup"><span data-stu-id="81715-121">No</span></span> | |
| <span data-ttu-id="81715-122">专用频道消息</span><span class="sxs-lookup"><span data-stu-id="81715-122">Private channel messages</span></span> | <span data-ttu-id="81715-123">否</span><span class="sxs-lookup"><span data-stu-id="81715-123">No</span></span> | |
| <span data-ttu-id="81715-124">表情符号、Gif、贴纸</span><span class="sxs-lookup"><span data-stu-id="81715-124">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="81715-125">是</span><span class="sxs-lookup"><span data-stu-id="81715-125">Yes</span></span> | |
| <span data-ttu-id="81715-126">代码片段</span><span class="sxs-lookup"><span data-stu-id="81715-126">Code snippets</span></span> | <span data-ttu-id="81715-127">否</span><span class="sxs-lookup"><span data-stu-id="81715-127">No</span></span> | |
| <span data-ttu-id="81715-128">聊天链接</span><span class="sxs-lookup"><span data-stu-id="81715-128">Chat links</span></span> | <span data-ttu-id="81715-129">是</span><span class="sxs-lookup"><span data-stu-id="81715-129">Yes</span></span> | |
| <span data-ttu-id="81715-130">反应（赞、红心大战等）</span><span class="sxs-lookup"><span data-stu-id="81715-130">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="81715-131">否</span><span class="sxs-lookup"><span data-stu-id="81715-131">No</span></span> | |
| <span data-ttu-id="81715-132">已编辑邮件</span><span class="sxs-lookup"><span data-stu-id="81715-132">Edited messages</span></span> | <span data-ttu-id="81715-133">是</span><span class="sxs-lookup"><span data-stu-id="81715-133">Yes</span></span> | <span data-ttu-id="81715-134">如果用户处于保留状态，将保留已编辑邮件的以前版本。</span><span class="sxs-lookup"><span data-stu-id="81715-134">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="81715-135">内联图像</span><span class="sxs-lookup"><span data-stu-id="81715-135">Inline images</span></span> | <span data-ttu-id="81715-136">是</span><span class="sxs-lookup"><span data-stu-id="81715-136">Yes</span></span> | |
| <span data-ttu-id="81715-137">题注</span><span class="sxs-lookup"><span data-stu-id="81715-137">Tables</span></span> | <span data-ttu-id="81715-138">是</span><span class="sxs-lookup"><span data-stu-id="81715-138">Yes</span></span> | |
| <span data-ttu-id="81715-139">主题</span><span class="sxs-lookup"><span data-stu-id="81715-139">Subject</span></span> | <span data-ttu-id="81715-140">是</span><span class="sxs-lookup"><span data-stu-id="81715-140">Yes</span></span> | |
| <span data-ttu-id="81715-141">引述</span><span class="sxs-lookup"><span data-stu-id="81715-141">Quotes</span></span> | <span data-ttu-id="81715-142">是</span><span class="sxs-lookup"><span data-stu-id="81715-142">Yes</span></span> | <span data-ttu-id="81715-143">已引用内容可搜索。</span><span class="sxs-lookup"><span data-stu-id="81715-143">Quoted content is searchable.</span></span> <span data-ttu-id="81715-144">但是，搜索结果不表示内容已加引号。</span><span class="sxs-lookup"><span data-stu-id="81715-144">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="81715-145">频道的名称</span><span class="sxs-lookup"><span data-stu-id="81715-145">Name of channel</span></span> | <span data-ttu-id="81715-146">否</span><span class="sxs-lookup"><span data-stu-id="81715-146">No</span></span> | |

- <span data-ttu-id="81715-147">若要使用 Microsoft 团队内容执行电子数据展示调查，请查看["安全 & 合规中心" 链接中的 "管理电子数据展示事例"](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)中的步骤1。</span><span class="sxs-lookup"><span data-stu-id="81715-147">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [Manage eDiscovery cases in the Security & Compliance Center](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

- <span data-ttu-id="81715-148">Microsoft 团队数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话。</span><span class="sxs-lookup"><span data-stu-id="81715-148">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="81715-149">可以在 Outlook 中`.pst`打开文件以在导出后查看这些邮件。</span><span class="sxs-lookup"><span data-stu-id="81715-149">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

    <span data-ttu-id="81715-150">查看团队的`.pst`文件时，请注意所有对话都保存在 "对话历史记录" 下的 "工作组聊天" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="81715-150">When viewing the `.pst` file for the team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="81715-151">邮件标题包含团队名称和频道名称。</span><span class="sxs-lookup"><span data-stu-id="81715-151">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="81715-152">例如，下面的图像显示来自 Bob 的一条消息，messaged 制造规范团队的项目7标准频道。</span><span class="sxs-lookup"><span data-stu-id="81715-152">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Outlook 中的用户邮箱中的工作组聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

- <span data-ttu-id="81715-154">用户邮箱中的私人聊天存储在 "对话历史记录" 下的 "工作组聊天" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="81715-154">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="81715-155">专用频道的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="81715-155">eDiscovery of private channels</span></span>

<span data-ttu-id="81715-156">在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。</span><span class="sxs-lookup"><span data-stu-id="81715-156">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="81715-157">记录的标题已格式化为指示它们是从哪个私人频道发送的。</span><span class="sxs-lookup"><span data-stu-id="81715-157">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="81715-158">由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="81715-158">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="81715-159">团队不支持团队中的单个频道的电子数据展示搜索，因此必须搜索整个团队。</span><span class="sxs-lookup"><span data-stu-id="81715-159">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="81715-160">若要在专用频道中执行电子数据展示搜索，请在团队中搜索与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。</span><span class="sxs-lookup"><span data-stu-id="81715-160">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="81715-161">使用以下步骤标识要包括在电子数据展示搜索中的专用通道中的文件和邮件。</span><span class="sxs-lookup"><span data-stu-id="81715-161">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="81715-162">在电子数据展示搜索中包括专用信道文件</span><span class="sxs-lookup"><span data-stu-id="81715-162">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="81715-163">在执行这些步骤之前，请安装[Sharepoint Online 命令行管理程序并连接到 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="81715-163">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="81715-164">运行以下操作以获取与团队中的专用通道相关联的所有 SharePoint 网站集的列表。</span><span class="sxs-lookup"><span data-stu-id="81715-164">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="81715-165">运行以下 PowerShell 脚本，获取与团队和父团队组 ID 中的专用通道相关联的所有 SharePoint 网站集 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="81715-165">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="81715-166">对于每个团队或组 ID，运行以下 PowerShell 脚本来标识所有相关专用通道网站，其中 $groupID 是团队的组 ID。</span><span class="sxs-lookup"><span data-stu-id="81715-166">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="81715-167">在电子数据展示搜索中包括专用信道消息</span><span class="sxs-lookup"><span data-stu-id="81715-167">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="81715-168">在执行这些步骤之前，请确保安装了[最新版本的团队 PowerShell 模块](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="81715-168">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="81715-169">运行以下操作以获取团队中的专用通道的列表。</span><span class="sxs-lookup"><span data-stu-id="81715-169">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="81715-170">运行以下操作以获取专用通道成员的列表。</span><span class="sxs-lookup"><span data-stu-id="81715-170">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="81715-171">将团队中每个专用频道的所有成员的邮箱添加为电子数据展示搜索查询的一部分。</span><span class="sxs-lookup"><span data-stu-id="81715-171">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="81715-172">高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="81715-172">Advanced eDiscovery</span></span>

<span data-ttu-id="81715-173">还可以使用[高级电子数据展示工作流](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)搜索和保留某些 Microsoft 团队内容。</span><span class="sxs-lookup"><span data-stu-id="81715-173">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="81715-174">虽然电子数据展示提供了一系列搜索、保留和导出功能，但高级电子数据展示为合规性管理员提供了更多用于识别数据源和分析其内容的工具。</span><span class="sxs-lookup"><span data-stu-id="81715-174">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="81715-175">工作组内容的高级电子数据展示保管人工作流</span><span class="sxs-lookup"><span data-stu-id="81715-175">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="81715-176">保管人可能是各种团队的成员。</span><span class="sxs-lookup"><span data-stu-id="81715-176">Custodians might be a member of various teams.</span></span> <span data-ttu-id="81715-177">你可以捕获与这些保管人相关的团队内容。</span><span class="sxs-lookup"><span data-stu-id="81715-177">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="81715-178">有关保管人工作流的背景和说明，请参阅[高级电子数据展示工作流](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="81715-178">For background and instructions on the custodian workflow, see [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span>

<span data-ttu-id="81715-179">添加保管人后，单击 "**下一步**" 按钮，然后单击 "**添加**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="81715-179">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="81715-180">此时将显示一个窗口，提示你选择其他位置，这将向你显示所有保管人成员的成员身份以及对应的 SharePoint 网站位置。</span><span class="sxs-lookup"><span data-stu-id="81715-180">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="81715-181">从所有这些数据源和团队中，你可以选择要用于电子数据展示的内容，然后将该用户和你已标识的所有数据源置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="81715-181">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="81715-182">你可以选择是否包括 Exchange 内容、其 OneDrive 内容或两者。</span><span class="sxs-lookup"><span data-stu-id="81715-182">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="81715-183">Exchange 内容包括用户邮箱中的所有应用程序内容，例如其电子邮件、存储在其邮箱中的团队内容等。</span><span class="sxs-lookup"><span data-stu-id="81715-183">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="81715-184">OneDrive 内容不仅包括用户的内容，还包括存储在 OneDrive 中的所有团队内容，如1:1 聊天、1： N 聊天和聊天中共享的文件。</span><span class="sxs-lookup"><span data-stu-id="81715-184">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="81715-185">你还可以选择将保管人成员与保管人成员相关联，以便包括保管人对其具有访问权限的频道聊天消息和文件。</span><span class="sxs-lookup"><span data-stu-id="81715-185">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="81715-186">此外，任何其他团队都可以与管理员关联。</span><span class="sxs-lookup"><span data-stu-id="81715-186">Additionally, any other team can be associated with a custodian.</span></span> <span data-ttu-id="81715-187">有关详细信息，请参阅[将保管人添加到高级电子数据展示事例](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="81715-187">For more information, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

> [!NOTE]
> <span data-ttu-id="81715-188">电子数据展示[专用频道](private-channels.md)中的消息和文件的工作方式与在标准信道中的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="81715-188">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="81715-189">若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="81715-189">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="81715-190">将数据源置于保持状态</span><span class="sxs-lookup"><span data-stu-id="81715-190">Placing a data source on hold</span></span>

<span data-ttu-id="81715-191">如果没有特定用户指定为保管人，则可以将整个数据源置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="81715-191">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="81715-192">有关保留的详细信息，请参阅[管理高级电子数据展示中的保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="81715-192">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="81715-193">为团队内容创建保留时，可以选择要包含在保留中的所有位置。</span><span class="sxs-lookup"><span data-stu-id="81715-193">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="81715-194">即使用户正在删除或更改内容，保留仍将保留该内容所有以前版本的副本。</span><span class="sxs-lookup"><span data-stu-id="81715-194">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="81715-195">你还可以使用可选查询基于关键字、日期范围、作者和许多其他条件设置保留条件。</span><span class="sxs-lookup"><span data-stu-id="81715-195">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="81715-196">如果不指定关键字，则来自该数据源的所有内容都将受到保留。</span><span class="sxs-lookup"><span data-stu-id="81715-196">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="81715-197">高级电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="81715-197">Advanced eDiscovery searches</span></span>

<span data-ttu-id="81715-198">还可以搜索团队内容。</span><span class="sxs-lookup"><span data-stu-id="81715-198">Teams content can also be searched.</span></span> <span data-ttu-id="81715-199">有关搜索的详细信息，请参阅[在高级电子数据展示中收集事例的数据](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="81715-199">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="81715-200">如果即使一条消息与搜索查询匹配，搜索也会返回整个对话。</span><span class="sxs-lookup"><span data-stu-id="81715-200">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="81715-201">创建搜索查询时，可以选择 "保管人"，以便搜索已选择的所有源。</span><span class="sxs-lookup"><span data-stu-id="81715-201">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="81715-202">您还可以搜索非 custodial 源，如未映射到用户的团队网站。</span><span class="sxs-lookup"><span data-stu-id="81715-202">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="81715-203">还可使用可选查询缩小团队内容中的搜索范围。</span><span class="sxs-lookup"><span data-stu-id="81715-203">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="81715-204">创建搜索并选中它后，将显示一个窗口，其中包含可在所选搜索上执行的其他详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="81715-204">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="81715-205">如果单击 "**统计**" 按钮，则可以查看有关搜索的统计信息，包括根据位置类型、内容的原始源以及内容位于组邮箱、单个用户邮箱还是 SharePoint 网站中的细目。</span><span class="sxs-lookup"><span data-stu-id="81715-205">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="81715-206">这样，您就可以看到对搜索结果有哪些来源的细目。</span><span class="sxs-lookup"><span data-stu-id="81715-206">This allows you to see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="81715-207">还有可用的 "**查询**" 视图，以便你可以查看哪些单个关键字对你的结果有影响。</span><span class="sxs-lookup"><span data-stu-id="81715-207">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="81715-208">完成搜索后，您可以单击 "**将结果添加到审阅集**" 按钮并将其添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="81715-208">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="81715-209">有关审阅集的详细信息，请参阅本文后面的[管理高级电子数据展示和审阅中的审阅集](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)[工作流](#review-sets-workflow)。</span><span class="sxs-lookup"><span data-stu-id="81715-209">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="81715-210">常规审阅集和对话审阅集</span><span class="sxs-lookup"><span data-stu-id="81715-210">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="81715-211">向审阅集添加搜索时，可以从 "常规" 审阅集或 "对话审阅" 集进行选择。</span><span class="sxs-lookup"><span data-stu-id="81715-211">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="81715-212">常规审阅集类似于导出;它为团队内容`.msg`提供单个文件，并在基本视图中显示内容。</span><span class="sxs-lookup"><span data-stu-id="81715-212">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="81715-213">当你计划使用其他软件工具在以后重新处理文件时，通常会使用常规的审阅集。</span><span class="sxs-lookup"><span data-stu-id="81715-213">You would typically use a normal review set when you plan to use other software tools to re-process the files later.</span></span>

<span data-ttu-id="81715-214">对话审核集提供了更直观的对话视图;它以正确的顺序显示相关邮件。</span><span class="sxs-lookup"><span data-stu-id="81715-214">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

<span data-ttu-id="81715-215">在两种类型的审阅集中都提供了密文之类的功能。</span><span class="sxs-lookup"><span data-stu-id="81715-215">Functionality such as redaction is available in both types of review sets.</span></span>

<span data-ttu-id="81715-216">有关审阅集的详细信息，请参阅[在高级电子数据展示中查看对话](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="81715-216">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="81715-217">收集选项</span><span class="sxs-lookup"><span data-stu-id="81715-217">Collection options</span></span>

<span data-ttu-id="81715-218">添加到审阅集时，窗口的 "**集合选项**" 部分下有多个选项可用作复选框，包括**对话检索选项**和**团队对话**。</span><span class="sxs-lookup"><span data-stu-id="81715-218">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="81715-219">如果你启用这些选项，则属于你的审阅集的任何单个团队邮件也将显示在其上下文中的其他消息周围。</span><span class="sxs-lookup"><span data-stu-id="81715-219">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="81715-220">例如，如果你的查询非常具体且仅返回一条消息，则启用这些选项还将返回指向和关注与查询匹配的消息的多条消息。</span><span class="sxs-lookup"><span data-stu-id="81715-220">For example, if your query is very specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="81715-221">许多逻辑条件用于确定其他消息是否提供与查询匹配的消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="81715-221">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="81715-222">例如，对于团队内容，启用这些选项将检索父消息和所有子消息，因为消息的串接方式。</span><span class="sxs-lookup"><span data-stu-id="81715-222">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="81715-223">还会检查消息时间戳。</span><span class="sxs-lookup"><span data-stu-id="81715-223">Message time stamps are also checked.</span></span> <span data-ttu-id="81715-224">如果某条消息与你的查询相匹配，则在4小时以内或在4小时范围内关注它的相邻消息将被视为对话的一部分，并且也包含在结果中。</span><span class="sxs-lookup"><span data-stu-id="81715-224">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="81715-225">如果你必须确定将返回哪些上下文消息与搜索查询匹配项，则无需使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="81715-225">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="81715-226">你可以收集所有内容，也可以放宽搜索的日期范围，以便更多邮件作为查询结果返回。</span><span class="sxs-lookup"><span data-stu-id="81715-226">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="81715-227">审阅集工作流</span><span class="sxs-lookup"><span data-stu-id="81715-227">Review sets workflow</span></span>

<span data-ttu-id="81715-228">通过单击 "**审阅集**" 选项卡，可以查看现有的审阅集或创建新的审阅集。有关审阅集的详细信息，请参阅[在高级电子数据展示中管理审阅集](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="81715-228">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="81715-229">除了文档之外，您还可以将电子邮件、团队邮件、Yammer 邮件和其他内容添加到你的审阅集。</span><span class="sxs-lookup"><span data-stu-id="81715-229">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="81715-230">在审阅集内，你也可以执行可以在其他上下文中执行的许多相同的操作，例如搜索内容和创建自定义查询。</span><span class="sxs-lookup"><span data-stu-id="81715-230">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="81715-231">这些操作仅适用于已添加到审阅集的项目。</span><span class="sxs-lookup"><span data-stu-id="81715-231">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="81715-232">"**管理审阅集**" 按钮提供其他选项，例如 "分析"、"摘要报告"、已添加的加载集等。</span><span class="sxs-lookup"><span data-stu-id="81715-232">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="81715-233">若要访问数据的可视化效果和图表，**请单击右上** \>角的 "**搜索个人资料" 视图**。</span><span class="sxs-lookup"><span data-stu-id="81715-233">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="81715-234">可以单击这些图表中的楔形，以交互方式选择要查询的内容类型。</span><span class="sxs-lookup"><span data-stu-id="81715-234">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="81715-235">例如，您可以选择仅查询团队内容。</span><span class="sxs-lookup"><span data-stu-id="81715-235">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="81715-236">您也可以像保存手动编写的查询一样保存这些查询。</span><span class="sxs-lookup"><span data-stu-id="81715-236">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="81715-237">摘要视图、文本视图和批注视图</span><span class="sxs-lookup"><span data-stu-id="81715-237">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="81715-238">如果您单击 "审阅" 集中的团队对话，它将显示 "**摘要" 视图**，其中显示整个团队对话，作为可单独与之交互的消息列表。</span><span class="sxs-lookup"><span data-stu-id="81715-238">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="81715-239">单击消息右侧的向下箭头以显示上下文菜单，可在其中查看消息详细信息或下载单个`.msg`文件。</span><span class="sxs-lookup"><span data-stu-id="81715-239">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="81715-240">单击 "消息详细信息" 将显示元数据的摘要或消息的完整元数据。</span><span class="sxs-lookup"><span data-stu-id="81715-240">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="81715-241">若要下载 PDF，请单击 "摘要" 视图右上角的 "下载" 按钮。</span><span class="sxs-lookup"><span data-stu-id="81715-241">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="81715-242">单击 "**文本视图**" 选项卡以显示 "团队对话" 的提取文本的纯文本视图。</span><span class="sxs-lookup"><span data-stu-id="81715-242">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="81715-243">这适合导出，并且你可以使用其他软件工具轻松处理此提取的文本。</span><span class="sxs-lookup"><span data-stu-id="81715-243">This is suitable for export and you can easily work with this extracted text using other software tools.</span></span>

<span data-ttu-id="81715-244">单击 "**批注视图**" 选项卡以访问 "批注" 功能。</span><span class="sxs-lookup"><span data-stu-id="81715-244">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="81715-245">此选项卡以类似团队对话的格式显示内容，但还有其他编辑选项。</span><span class="sxs-lookup"><span data-stu-id="81715-245">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="81715-246">有一个铅笔工具可用于在邮件上进行笔记、绘制邮件或进行细化的 scratching，以供密文使用。</span><span class="sxs-lookup"><span data-stu-id="81715-246">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="81715-247">还有一种**区域密文**工具，可用于绘制黑色缩小区域的矩形，并将其标记为 "Redacted"。</span><span class="sxs-lookup"><span data-stu-id="81715-247">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="81715-248">"**批注视图**" 选项卡底部是 "**标记文档**" 按钮，用于显示 "标记" 面板。</span><span class="sxs-lookup"><span data-stu-id="81715-248">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="81715-249">在此面板中，你可以将标记应用到团队对话中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="81715-249">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="81715-250">你可以将对话标记为 "响应" 或 "无响应"、"特权" 或 "无权限"，无论它是否包含 "感兴趣的项目"、是否应包括在导出中以及是否需要进一步查看。</span><span class="sxs-lookup"><span data-stu-id="81715-250">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="81715-251">您还可以管理和应用其他可自定义的标记。</span><span class="sxs-lookup"><span data-stu-id="81715-251">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="81715-252">操作菜单</span><span class="sxs-lookup"><span data-stu-id="81715-252">Action menu</span></span>

<span data-ttu-id="81715-253">在 "审阅集" 窗口中，可以通过单击 "**操作** \> **导出**" 来导出内容。</span><span class="sxs-lookup"><span data-stu-id="81715-253">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="81715-254">导出时有许多选项可供使用。</span><span class="sxs-lookup"><span data-stu-id="81715-254">There are many options available when exporting.</span></span>

<span data-ttu-id="81715-255">若要导出包含所有团队邮件的所有元数据的文件，请单击以选中 "**加载文件**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="81715-255">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="81715-256">若要将已应用于内容的任何标记包含在您的文件中，请单击以选中 "**标记**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="81715-256">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="81715-257">使用 "**本机文件**" 选项以其本机格式导出文件。</span><span class="sxs-lookup"><span data-stu-id="81715-257">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="81715-258">你可以选择将对话作为一个文件或所有单独的聊天消息导出到各自的单独文件中。</span><span class="sxs-lookup"><span data-stu-id="81715-258">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="81715-259">"**文本文件**" 选项允许保存纯文本版本的内容。</span><span class="sxs-lookup"><span data-stu-id="81715-259">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="81715-260">有关如何在审阅集中获取团队对话的纯文本视图的详细信息，请参阅上面的[摘要视图、文本视图和批注视图](#summary-view-text-view-and-annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="81715-260">See [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above for more information about how to obtain a plain text view of Teams conversations in the review set.</span></span>

<span data-ttu-id="81715-261">如果在上面的 "[摘要视图"、"文本视图" 和 "批注视图](#summary-view-text-view-and-annotate-view)" 部分中所述对内容应用了任何密文，则可以选择 "将**redacted natives 替换为转换的 pdf** " 选项，以将本机文件替换为 PDF 中的已转换副本。</span><span class="sxs-lookup"><span data-stu-id="81715-261">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="81715-262">你可以选择导出到 Microsoft 提供的 Azure blob 存储容器，或者你可以提供你自己的 Azure Blob 存储容器。</span><span class="sxs-lookup"><span data-stu-id="81715-262">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="81715-263">准备好开始导出过程时，请单击 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="81715-263">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="81715-264">导出完成后，有关如何访问 Azure blob 存储容器和下载导出的内容的详细信息，请参阅[下载导出作业](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs)。</span><span class="sxs-lookup"><span data-stu-id="81715-264">After export is complete, see [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content.</span></span>

> [!NOTE]
> <span data-ttu-id="81715-265">导出可能会延长一段时间。</span><span class="sxs-lookup"><span data-stu-id="81715-265">Exporting can take an extended period of time.</span></span> <span data-ttu-id="81715-266">若要跟踪导出过程的状态，请退出 "**审阅集**" 选项卡，然后单击 "**导出**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="81715-266">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81715-267">相关主题</span><span class="sxs-lookup"><span data-stu-id="81715-267">Related topics</span></span>

- [<span data-ttu-id="81715-268">Microsoft 365 中的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="81715-268">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="81715-269">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="81715-269">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
