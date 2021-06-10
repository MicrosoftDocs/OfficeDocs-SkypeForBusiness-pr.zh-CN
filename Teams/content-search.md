---
title: 在 Microsoft Teams 中使用内容搜索
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 了解如何使用 Microsoft 365 合规性中心的内容搜索来搜索 Exchange Online、SharePoint Online、OneDrive for Business 和 OneNote 中存储的 Microsoft Teams 内容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb63f3668ef03cdaf760a24ae1df0a815e7f282d
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855801"
---
# <a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="11a73-103">在"搜索"中Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11a73-103">Use Content search in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="11a73-104">在专用通道中对消息和文件 [进行](private-channels.md) 内容搜索的方式与在标准通道中不同。</span><span class="sxs-lookup"><span data-stu-id="11a73-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="11a73-105">若要了解有关详细信息，请参阅 [专用频道的内容搜索](#content-search-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="11a73-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="11a73-106">内容搜索提供了一种方法，Microsoft Teams跨 Exchange、SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="11a73-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="11a73-107">若要了解有关详细信息，请参阅[在 中搜索Microsoft 365。](/microsoft-365/compliance/content-search)</span><span class="sxs-lookup"><span data-stu-id="11a73-107">To learn more, see [Content search in Microsoft 365](/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="11a73-108">例如，对制造规范邮箱和制造规范 SharePoint 网站使用内容搜索，可以搜索 Exchange 中的 Teams 标准频道对话、SharePoint Online 中的文件上传和修改以及 OneNote 更改。</span><span class="sxs-lookup"><span data-stu-id="11a73-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="11a73-109">还可以向内容搜索添加查询 **条件，** 以缩小返回的结果范围。</span><span class="sxs-lookup"><span data-stu-id="11a73-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="11a73-110">在以上示例中，可以查找使用了关键字"**新工厂规范"** 的内容。</span><span class="sxs-lookup"><span data-stu-id="11a73-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="11a73-111">添加搜索条件后，可以将报表或实际内容导出到计算机进行分析。</span><span class="sxs-lookup"><span data-stu-id="11a73-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="11a73-112">专用频道的内容搜索</span><span class="sxs-lookup"><span data-stu-id="11a73-112">Content search of private channels</span></span>

<span data-ttu-id="11a73-113">在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。</span><span class="sxs-lookup"><span data-stu-id="11a73-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="11a73-114">记录的标题已格式化为指示它们是从哪个私人频道发送的。</span><span class="sxs-lookup"><span data-stu-id="11a73-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="11a73-115">由于每个专用频道都有自己的SharePoint网站集，独立于父团队网站，因此专用频道中的文件独立于父团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="11a73-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="11a73-116">Teams不支持单个频道的内容搜索，因此必须搜索整个团队。</span><span class="sxs-lookup"><span data-stu-id="11a73-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="11a73-117">若要执行专用频道的内容搜索，请在整个团队中搜索、与专用频道 (关联的网站集以包含文件) ，以及专用频道成员的邮箱 (以包含) 。</span><span class="sxs-lookup"><span data-stu-id="11a73-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="11a73-118">使用以下步骤识别专用通道中的文件和消息，以包括在内容搜索中。</span><span class="sxs-lookup"><span data-stu-id="11a73-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="11a73-119">在内容搜索中包括专用频道文件</span><span class="sxs-lookup"><span data-stu-id="11a73-119">Include private channel files in a content search</span></span>

<span data-ttu-id="11a73-120">执行这些步骤之前，请安装[SharePoint Online 命令行管理程序并连接到 SharePoint Online。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="11a73-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="11a73-121">运行以下代码，获取与SharePoint专用频道关联的所有网站集的列表。</span><span class="sxs-lookup"><span data-stu-id="11a73-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="11a73-122">运行以下 PowerShell 脚本，获取与团队中专用SharePoint关联的所有网站集 URL 的列表，以及父团队组 ID。</span><span class="sxs-lookup"><span data-stu-id="11a73-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="11a73-123">对于每个团队或组 ID，请运行以下 PowerShell 脚本来标识所有相关的专用频道网站。</span><span class="sxs-lookup"><span data-stu-id="11a73-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="11a73-124">在内容搜索中包括专用频道消息</span><span class="sxs-lookup"><span data-stu-id="11a73-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="11a73-125">执行这些步骤之前，请确保已安装最新版本Teams [PowerShell 模块](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="11a73-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="11a73-126">运行以下代码，获取团队中的专用频道列表。</span><span class="sxs-lookup"><span data-stu-id="11a73-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="11a73-127">运行以下代码获取专用频道成员的列表。</span><span class="sxs-lookup"><span data-stu-id="11a73-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="11a73-128">在内容搜索查询中包括团队中每个专用频道中所有成员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="11a73-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="11a73-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="11a73-129">Related topics</span></span>

- [<span data-ttu-id="11a73-130">Microsoft 365合规中心中的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="11a73-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](/Office365/SecurityCompliance/ediscovery-cases)