---
title: 在 Microsoft Teams 中对内容进行电子数据展示调查
author: LolaJacobsen
ms.author: lolaj
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
description: 了解当你需要执行电子数据展示时需要执行的操作，例如当你需要提交所有电子存储的法律程序存储信息时需要执行的操作。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 315ec351450224dc8d5b98dc0d974b64573bc0ab
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033266"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="6ab00-103">在 Microsoft Teams 中对内容进行电子数据展示调查</span><span class="sxs-lookup"><span data-stu-id="6ab00-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="6ab00-104">大型企业经常面临高处罚的法律诉讼，要求提交所有电子存储的信息（ESI）。</span><span class="sxs-lookup"><span data-stu-id="6ab00-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="6ab00-105">所有团队1:1 或群组聊天将被记录到各自的用户的邮箱中，并且所有标准信道消息都将记录到代表团队的组邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ab00-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="6ab00-106">在标准频道中上载的文件包含在 SharePoint Online 和 OneDrive for business 的电子数据展示功能下方。</span><span class="sxs-lookup"><span data-stu-id="6ab00-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="6ab00-107">电子数据展示[专用频道](private-channels.md)中的消息和文件与在标准频道中的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="6ab00-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="6ab00-108">若要了解详细信息，请参阅[电子数据展示专用频道](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="6ab00-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="6ab00-109">目前，我们不支持仅在来宾用户是1:1 或1： N 聊天的参与者的方案中聊天消息的电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="6ab00-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="6ab00-110">这些类型的聊天也称为*来宾到来宾*聊天，因为它们不包括家庭租户用户。</span><span class="sxs-lookup"><span data-stu-id="6ab00-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="6ab00-111">若要使用 Microsoft 团队内容执行电子数据展示调查，请查看[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)链接中的步骤1。</span><span class="sxs-lookup"><span data-stu-id="6ab00-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="6ab00-112">Microsoft 团队数据将在 Excel 电子数据展示导出输出中显示为即时消息或对话，您可以在 Outlook 中打开该 PST 以查看这些邮件的导出内容。</span><span class="sxs-lookup"><span data-stu-id="6ab00-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="6ab00-113">查看团队的 PST 时，请注意所有对话都保存在 "对话历史记录" 下的 "工作组聊天" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6ab00-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="6ab00-114">消息的标题与团队和频道一致。</span><span class="sxs-lookup"><span data-stu-id="6ab00-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="6ab00-115">查看下面的图像，您可以从 messaged 中看到此消息，这些信息来自于制造规范团队的项目7标准频道。</span><span class="sxs-lookup"><span data-stu-id="6ab00-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Outlook 中的用户邮箱中的工作组聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="6ab00-117">若要查看用户邮箱中的私人聊天，他们还位于 "对话历史记录" 下的 "工作组聊天" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6ab00-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="6ab00-118">专用频道的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="6ab00-118">eDiscovery of private channels</span></span>

<span data-ttu-id="6ab00-119">在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ab00-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="6ab00-120">记录的标题已格式化为指示它们是从哪个私人频道发送的。</span><span class="sxs-lookup"><span data-stu-id="6ab00-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="6ab00-121">由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="6ab00-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="6ab00-122">团队不支持单个通道的电子数据展示，因此必须搜索整个团队。</span><span class="sxs-lookup"><span data-stu-id="6ab00-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="6ab00-123">若要在专用频道中执行电子数据展示搜索，请在团队中搜索与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。</span><span class="sxs-lookup"><span data-stu-id="6ab00-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="6ab00-124">使用以下步骤标识要包括在电子数据展示搜索中的专用通道中的文件和邮件。</span><span class="sxs-lookup"><span data-stu-id="6ab00-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="6ab00-125">在电子数据展示搜索中包括专用信道文件</span><span class="sxs-lookup"><span data-stu-id="6ab00-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="6ab00-126">在执行这些步骤之前，请安装[Sharepoint Online 命令行管理程序并连接到 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="6ab00-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="6ab00-127">运行以下操作以获取与团队中的专用通道相关联的所有 SharePoint 网站集的列表。</span><span class="sxs-lookup"><span data-stu-id="6ab00-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="6ab00-128">运行以下 PowerShell 脚本，获取与团队和父团队组 ID 中的专用通道相关联的所有 SharePoint 网站集 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="6ab00-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="6ab00-129">对于每个团队或组 ID，运行以下 PowerShell 脚本来标识所有相关专用通道网站，其中 $groupID 是团队的组 ID。</span><span class="sxs-lookup"><span data-stu-id="6ab00-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="6ab00-130">在电子数据展示搜索中包括专用信道消息</span><span class="sxs-lookup"><span data-stu-id="6ab00-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="6ab00-131">在执行这些步骤之前，请确保安装了[最新版本的团队 PowerShell 模块](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab00-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="6ab00-132">运行以下操作以获取团队中的专用通道的列表。</span><span class="sxs-lookup"><span data-stu-id="6ab00-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="6ab00-133">运行以下操作以获取专用通道成员的列表。</span><span class="sxs-lookup"><span data-stu-id="6ab00-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="6ab00-134">将团队中每个专用频道的所有成员的邮箱添加为电子数据展示搜索查询的一部分。</span><span class="sxs-lookup"><span data-stu-id="6ab00-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6ab00-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="6ab00-135">Related topics</span></span>

- [<span data-ttu-id="6ab00-136">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="6ab00-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
