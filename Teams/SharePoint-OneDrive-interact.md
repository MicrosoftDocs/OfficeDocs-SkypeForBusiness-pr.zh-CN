---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: 了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互，例如，如何存储私人聊天文件，以及团队、频道和文档库之间的关系。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567117"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="64bb9-103">SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="64bb9-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="64bb9-104">观看以下会话，了解团队如何与 Azure Active Directory （AAD）、Office 365 组、Exchange、SharePoint 和 OneDrive for business 进行交互： [Microsoft 团队基础](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="64bb9-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="64bb9-105">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="64bb9-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="64bb9-106">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="64bb9-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="64bb9-107">私人聊天文件存储在发送方的 OneDrive for Business 文件夹中，在文件共享过程中，系统会自动向所有参与者授予权限。</span><span class="sxs-lookup"><span data-stu-id="64bb9-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="64bb9-108">如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。</span><span class="sxs-lookup"><span data-stu-id="64bb9-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="64bb9-109">文件共享将继续在频道中工作，但用户无法在 Office 365 中共享没有 OneDrive for business 存储的聊天文件。</span><span class="sxs-lookup"><span data-stu-id="64bb9-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="64bb9-110">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="64bb9-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="64bb9-111">目前不支持 Microsoft 团队与本地 SharePoint 的集成。</span><span class="sxs-lookup"><span data-stu-id="64bb9-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="64bb9-112">下面是团队、频道和文档库之间的关系示例。</span><span class="sxs-lookup"><span data-stu-id="64bb9-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="64bb9-113">对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹**共享文档**。</span><span class="sxs-lookup"><span data-stu-id="64bb9-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="64bb9-114">包括每个团队的默认频道“**常规**”频道在内的每个频道在“**共享文档**”下都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="64bb9-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![SharePoint Online 中的 "共享文档" 文件夹的图表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="64bb9-116">当前无法替代默认 SharePoint 站点和文档库。</span><span class="sxs-lookup"><span data-stu-id="64bb9-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="64bb9-117">我们已经知道你的需求，我们正在考虑。</span><span class="sxs-lookup"><span data-stu-id="64bb9-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="64bb9-118">查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="64bb9-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="64bb9-119">若要向团队添加链接到现有 SharePoint 网站页面或现有 SharePoint 文档库的选项卡，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64bb9-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="64bb9-120">选择选项卡旁边的加号。</span><span class="sxs-lookup"><span data-stu-id="64bb9-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="64bb9-121">为现有文档库的现有 SharePoint 网站页面或**文档库**选择任一**SharePoint** 。</span><span class="sxs-lookup"><span data-stu-id="64bb9-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="64bb9-122">选择相应的页面或文档库。</span><span class="sxs-lookup"><span data-stu-id="64bb9-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="64bb9-123">对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件**用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="64bb9-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![名为 Microsoft 团队聊天文件的 OneDrive 文件夹的图表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="64bb9-125">频道文件选项卡</span><span class="sxs-lookup"><span data-stu-id="64bb9-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="64bb9-126">团队中的 "**文件**" 选项卡紧密类似于 SharePoint 文档视图。</span><span class="sxs-lookup"><span data-stu-id="64bb9-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="64bb9-127">在 "**文件**" 选项卡上，用户可以：</span><span class="sxs-lookup"><span data-stu-id="64bb9-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="64bb9-128">在 "**新建**文件" 菜单中查看其他选项。</span><span class="sxs-lookup"><span data-stu-id="64bb9-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="64bb9-129">将文件同步到其本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="64bb9-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="64bb9-130">在 "**所有文档**" 菜单上，从**列表**视图切换到**压缩列表**到 "**磁贴**" 视图。</span><span class="sxs-lookup"><span data-stu-id="64bb9-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="64bb9-131">确定需要关注或有恶意软件的文件。</span><span class="sxs-lookup"><span data-stu-id="64bb9-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="64bb9-132">立即查看文件是否为只读或已签出。</span><span class="sxs-lookup"><span data-stu-id="64bb9-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="64bb9-133">签出和签入文件。</span><span class="sxs-lookup"><span data-stu-id="64bb9-133">Check out and check in files.</span></span>
- <span data-ttu-id="64bb9-134">固定、取消固定和更改文件的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="64bb9-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="64bb9-135">确定需要元数据的文件</span><span class="sxs-lookup"><span data-stu-id="64bb9-135">Identify which files need metadata</span></span>
- <span data-ttu-id="64bb9-136">从更多筛选选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="64bb9-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="64bb9-137">基于列标题对文件进行分组。</span><span class="sxs-lookup"><span data-stu-id="64bb9-137">Group files based on column headings.</span></span>
- <span data-ttu-id="64bb9-138">修改栏设置（向左或向右移动、隐藏）和列宽。</span><span class="sxs-lookup"><span data-stu-id="64bb9-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="64bb9-139">默认链接类型设置</span><span class="sxs-lookup"><span data-stu-id="64bb9-139">Default link type setting</span></span>

<span data-ttu-id="64bb9-140">SharePoint 和 OneDrive 具有管理员设置，用于指定为文件创建的链接的默认链接类型。</span><span class="sxs-lookup"><span data-stu-id="64bb9-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="64bb9-141">团队通过重复使用管理员为 SharePoint 和 OneDrive 设置的设置来采用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="64bb9-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="64bb9-142">有关此方法的更多详细信息，[请参阅更改用户获取共享链接时的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。</span><span class="sxs-lookup"><span data-stu-id="64bb9-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="64bb9-143">更多信息</span><span class="sxs-lookup"><span data-stu-id="64bb9-143">More information</span></span>

<span data-ttu-id="64bb9-144">有关 SharePoint 如何与团队协同工作的详细信息，请参阅[sharepoint 和团队：更好地协作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="64bb9-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="64bb9-145">若要了解有关团队中的来宾体验的详细信息，请阅读[来宾体验](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="64bb9-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

