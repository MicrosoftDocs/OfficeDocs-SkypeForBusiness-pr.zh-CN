---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & OneDrive for Business 与团队交互私人聊天文件存储 & 团队、标准频道 & 文档库之间的交互。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a66cacf7a60b020b4b56e0824d0a275efdf704f8
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "45140934"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="df06e-103">SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="df06e-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="df06e-104">观看以下会话，了解团队如何与 Azure Active Directory （AAD）、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for business 进行交互： [Microsoft 团队基础](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="df06e-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="df06e-105">Microsoft 团队中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个标准频道都将获取默认工作组网站文档库中的一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="df06e-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="df06e-106">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="df06e-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="df06e-107">若要查看更改 SharePoint 中的网站地址的影响，请阅读[更改网站地址](https://docs.microsoft.com/sharepoint/change-site-address)。</span><span class="sxs-lookup"><span data-stu-id="df06e-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="df06e-108">本文仅适用于标准频道。</span><span class="sxs-lookup"><span data-stu-id="df06e-108">This article applies only to standard channels.</span></span> <span data-ttu-id="df06e-109">专用信道的体系结构与标准信道不同。</span><span class="sxs-lookup"><span data-stu-id="df06e-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="df06e-110">每个专用频道都有其自己的与父团队网站分开的 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="df06e-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="df06e-111">若要了解详细信息，请参阅[Microsoft 团队中的专用频道](private-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="df06e-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="df06e-112">私人聊天文件存储在发件人的 OneDrive for business 文件夹中，并将权限自动授予所有参与者作为文件共享过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="df06e-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="df06e-113">如果未使用 SharePoint Online 许可证分配和启用用户，则他们在 Microsoft 365 或 Office 365 中没有 OneDrive for business 存储。</span><span class="sxs-lookup"><span data-stu-id="df06e-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="df06e-114">文件共享将继续在标准频道中工作，但是在 Microsoft 365 或 Office 365 中，用户无法在没有 OneDrive for business 存储的情况下共享文件。</span><span class="sxs-lookup"><span data-stu-id="df06e-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="df06e-115">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="df06e-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="df06e-116">目前不支持 Microsoft 团队与本地 SharePoint 的集成。</span><span class="sxs-lookup"><span data-stu-id="df06e-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="df06e-117">下面是团队、标准频道和文档库之间的关系的示例。</span><span class="sxs-lookup"><span data-stu-id="df06e-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="df06e-118">对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹**共享文档**。</span><span class="sxs-lookup"><span data-stu-id="df06e-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="df06e-119">每个标准频道（包括**常规**频道（每个团队的默认频道）在 "**共享文档**" 中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="df06e-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online 中的 "共享文档" 文件夹的图表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="df06e-121">当前无法替代默认 SharePoint 站点和文档库。</span><span class="sxs-lookup"><span data-stu-id="df06e-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="df06e-122">我们已经知道你的需求，我们正在考虑。</span><span class="sxs-lookup"><span data-stu-id="df06e-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="df06e-123">查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="df06e-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="df06e-124">若要向团队添加链接到现有 SharePoint 网站页面或现有 SharePoint 文档库的选项卡，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="df06e-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="df06e-125">选择选项卡旁边的加号。</span><span class="sxs-lookup"><span data-stu-id="df06e-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="df06e-126">为现有文档库的现有 SharePoint 网站页面或**文档库**选择任一**SharePoint** 。</span><span class="sxs-lookup"><span data-stu-id="df06e-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="df06e-127">选择相应的页面或文档库。</span><span class="sxs-lookup"><span data-stu-id="df06e-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="df06e-128">对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件**用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="df06e-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![名为 Microsoft 团队聊天文件的 OneDrive 文件夹的图表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="df06e-130">请注意，对于公共团队，SharePoint 团队网站使用 "除外部用户之外的所有人" 访问设置。</span><span class="sxs-lookup"><span data-stu-id="df06e-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="df06e-131">对于不是该团队成员的人员，不会在团队中显示公共团队。</span><span class="sxs-lookup"><span data-stu-id="df06e-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="df06e-132">但是，他们可以使用 SharePoint 团队网站的 URL 访问 SharePoint 团队网站上的内容。</span><span class="sxs-lookup"><span data-stu-id="df06e-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="df06e-133">频道文件选项卡</span><span class="sxs-lookup"><span data-stu-id="df06e-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="df06e-134">团队中的 "**文件**" 选项卡紧密类似于 SharePoint 文档视图。</span><span class="sxs-lookup"><span data-stu-id="df06e-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="df06e-135">在 "**文件**" 选项卡上，用户可以：</span><span class="sxs-lookup"><span data-stu-id="df06e-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="df06e-136">在 "**新建**文件" 菜单中查看其他选项。</span><span class="sxs-lookup"><span data-stu-id="df06e-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="df06e-137">将文件同步到其本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="df06e-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="df06e-138">在 "**所有文档**" 菜单上，从**列表**视图切换到**压缩列表**到 "**磁贴**" 视图。</span><span class="sxs-lookup"><span data-stu-id="df06e-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="df06e-139">确定需要关注或有恶意软件的文件。</span><span class="sxs-lookup"><span data-stu-id="df06e-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="df06e-140">立即查看文件是否为只读或已签出。</span><span class="sxs-lookup"><span data-stu-id="df06e-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="df06e-141">签出和签入文件。</span><span class="sxs-lookup"><span data-stu-id="df06e-141">Check out and check in files.</span></span>
- <span data-ttu-id="df06e-142">固定、取消固定和更改文件的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="df06e-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="df06e-143">确定需要元数据的文件</span><span class="sxs-lookup"><span data-stu-id="df06e-143">Identify which files need metadata</span></span>
- <span data-ttu-id="df06e-144">从更多筛选选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="df06e-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="df06e-145">基于列标题对文件进行分组。</span><span class="sxs-lookup"><span data-stu-id="df06e-145">Group files based on column headings.</span></span>
- <span data-ttu-id="df06e-146">修改栏设置（向左或向右移动、隐藏）和列宽。</span><span class="sxs-lookup"><span data-stu-id="df06e-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="df06e-147">默认链接类型设置</span><span class="sxs-lookup"><span data-stu-id="df06e-147">Default link type setting</span></span>

<span data-ttu-id="df06e-148">SharePoint 和 OneDrive 具有管理员设置，用于指定为文件创建的链接的默认链接类型。</span><span class="sxs-lookup"><span data-stu-id="df06e-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="df06e-149">团队通过重复使用管理员为 SharePoint 和 OneDrive 设置的设置来采用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="df06e-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="df06e-150">有关此方法的更多详细信息，[请参阅更改用户获取共享链接时的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。</span><span class="sxs-lookup"><span data-stu-id="df06e-150">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="df06e-151">更多信息</span><span class="sxs-lookup"><span data-stu-id="df06e-151">More information</span></span>

<span data-ttu-id="df06e-152">有关 SharePoint 如何与团队协同工作的详细信息，请参阅[sharepoint 和团队：更好地协作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="df06e-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="df06e-153">若要了解有关团队中的来宾体验的详细信息，请阅读[来宾体验](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="df06e-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

