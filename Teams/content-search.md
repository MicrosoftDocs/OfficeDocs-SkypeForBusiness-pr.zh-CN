---
title: 在 Microsoft Teams 中使用内容搜索
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 了解如何在 Microsoft 团队中使用 "内容搜索" 查询来自 Exchange、SharePoint Online、OneDrive for business 和 OneNote 的 Microsoft 团队信息。
appliesto:
- Microsoft Teams
ms.openlocfilehash: af81b857d6cf60f7de1a1b1e199d08ede089de5f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137742"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="3458c-103">在 Microsoft Teams 中使用内容搜索</span><span class="sxs-lookup"><span data-stu-id="3458c-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="3458c-104">[专用频道](private-channels.md)中的邮件和文件的内容搜索与在标准频道中的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="3458c-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="3458c-105">若要了解详细信息，请参阅[私人频道的内容搜索](#content-search-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="3458c-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="3458c-106">内容搜索提供了一种方法，可查询 Microsoft 团队信息，跨越 Exchange、SharePoint Online 和 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="3458c-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="3458c-107">若要了解详细信息，请阅读[Office 365 中的内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)。</span><span class="sxs-lookup"><span data-stu-id="3458c-107">To learn more, read [Content Search in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="3458c-108">例如，针对制造规范邮箱和制造规范 SharePoint 网站使用**内容搜索**，您可以从 Exchange、文件上传和 sharepoint Online 的修改以及 OneNote 更改中搜索团队标准频道对话。</span><span class="sxs-lookup"><span data-stu-id="3458c-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="3458c-109">您还可以将查询条件添加到**内容搜索**，以缩小返回的结果范围。</span><span class="sxs-lookup"><span data-stu-id="3458c-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="3458c-110">在上面的示例中，你可以查找使用 "**新工厂规范"** 关键字的内容。</span><span class="sxs-lookup"><span data-stu-id="3458c-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="3458c-111">添加搜索条件后，您可以将报表或数据导出到计算机进行分析。</span><span class="sxs-lookup"><span data-stu-id="3458c-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="3458c-112">专用频道的内容搜索</span><span class="sxs-lookup"><span data-stu-id="3458c-112">Content search of private channels</span></span>

<span data-ttu-id="3458c-113">在私人频道中发送的消息记录将传递到所有私人频道成员的邮箱，而不是传递到组邮箱。</span><span class="sxs-lookup"><span data-stu-id="3458c-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="3458c-114">记录的标题已格式化为指示它们是从哪个私人频道发送的。</span><span class="sxs-lookup"><span data-stu-id="3458c-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="3458c-115">由于每个专用频道都有自己的 SharePoint 网站集，独立于父团队网站，因此专用通道中的文件独立于父团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="3458c-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="3458c-116">团队不支持对单个频道进行内容搜索，因此必须搜索整个团队。</span><span class="sxs-lookup"><span data-stu-id="3458c-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="3458c-117">若要执行私人频道的内容搜索，请搜索整个团队、与专用频道相关联的网站集（包括文件）和专用频道成员的邮箱（包括邮件）。</span><span class="sxs-lookup"><span data-stu-id="3458c-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="3458c-118">使用以下步骤标识要包括在内容搜索中的专用频道中的文件和邮件。</span><span class="sxs-lookup"><span data-stu-id="3458c-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="3458c-119">在内容搜索中包括专用通道文件</span><span class="sxs-lookup"><span data-stu-id="3458c-119">Include private channel files in a content search</span></span>

<span data-ttu-id="3458c-120">在执行这些步骤之前，请安装[Sharepoint Online 命令行管理程序并连接到 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="3458c-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="3458c-121">运行以下操作以获取与团队中的专用通道相关联的所有 SharePoint 网站集的列表。</span><span class="sxs-lookup"><span data-stu-id="3458c-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="3458c-122">运行以下 PowerShell 脚本，获取与团队和父团队组 ID 中的专用通道相关联的所有 SharePoint 网站集 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="3458c-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="3458c-123">对于每个团队或组 ID，请运行以下 PowerShell 脚本以标识所有相关的专用通道站点。</span><span class="sxs-lookup"><span data-stu-id="3458c-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="3458c-124">在内容搜索中包括专用频道消息</span><span class="sxs-lookup"><span data-stu-id="3458c-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="3458c-125">在执行这些步骤之前，请确保安装了[最新版本的团队 PowerShell 模块](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3458c-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="3458c-126">运行以下操作以获取团队中的专用通道的列表。</span><span class="sxs-lookup"><span data-stu-id="3458c-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="3458c-127">运行以下操作以获取专用通道成员的列表。</span><span class="sxs-lookup"><span data-stu-id="3458c-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="3458c-128">将团队中每个专用频道的所有成员的邮箱添加为内容搜索查询的一部分。</span><span class="sxs-lookup"><span data-stu-id="3458c-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3458c-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="3458c-129">Related topics</span></span>

- [<span data-ttu-id="3458c-130">Office 365 安全 & 合规中心中的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="3458c-130">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 