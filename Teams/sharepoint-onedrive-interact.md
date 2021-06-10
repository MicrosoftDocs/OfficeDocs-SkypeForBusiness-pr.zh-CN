---
title: 如何SharePoint OneDrive交互Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive与 Teams 交互;私人聊天文件存储&团队、标准频道和文档库&交互。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855951"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="4dfa8-103">如何SharePoint OneDrive交互Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4dfa8-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="4dfa8-104">观看以下会话，了解 Teams 如何与 Azure Active Directory (AAD) 、Microsoft 365 组、Exchange、SharePoint 和 OneDrive 交互：Microsoft Teams [](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="4dfa8-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="4dfa8-105">每个团队Microsoft Teams都有一个团队网站SharePoint，团队中的每个标准频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="4dfa8-106">每个[专用频道](private-channels.md)都有自己的独立SharePoint站点。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="4dfa8-107">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="4dfa8-108">若要了解更改网站地址对SharePoint的影响，请阅读[更改网站地址](/sharepoint/change-site-address)。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="4dfa8-109">私人聊天文件存储在发件人的 OneDrive 文件夹中，权限会在文件共享过程中自动授予所有参与者。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="4dfa8-110">如果未为用户分配SharePoint许可证，则他们OneDrive存储Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="4dfa8-111">文件共享在标准通道中正常工作，但如果没有在聊天中存储OneDrive用户Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="4dfa8-112">通过将文件存储在文档SharePoint库OneDrive，将遵循在组织级别配置的所有符合性规则。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="4dfa8-113">不支持SharePoint服务器集成Teams。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="4dfa8-114">下面是团队、标准频道和文档库之间的关系示例。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="4dfa8-115">对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹 **共享文档**。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="4dfa8-116">每个标准频道（包括 **"** 常规" (每个团队的默认频道) 共享 **文档"中都有一个文件夹**。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

!["共享文档"文件夹在SharePoint。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="4dfa8-118">不能SharePoint网站和文档库的默认文档。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="4dfa8-119">对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件** 用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![名为 OneDrive 聊天文件Microsoft Teams文件夹的图示](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="4dfa8-121">请注意，对于公共团队，SharePoint网站预配了"除外部用户以外的所有人"访问权限。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="4dfa8-122">对于不是该团队Teams，公共团队不会显示在"公共团队"中。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="4dfa8-123">但是，他们可以使用团队SharePoint网站的 URL 访问SharePoint网站上的内容。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="4dfa8-124">"频道文件"选项卡</span><span class="sxs-lookup"><span data-stu-id="4dfa8-124">Channel Files tab</span></span>

<span data-ttu-id="4dfa8-125">"**文件"** 选项卡Teams文档视图SharePoint视图。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="4dfa8-126">在" **文件"** 选项卡上，用户可以：</span><span class="sxs-lookup"><span data-stu-id="4dfa8-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="4dfa8-127">在"新建文件" **菜单中查看其他** 选项。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="4dfa8-128">将文件同步到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="4dfa8-129">在"**所有文档"** 菜单上，从"列表 **"** 视图切换到 **"压缩列表"，切换到\*\*\*\*"平铺"** 视图。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="4dfa8-130">识别需要关注或具有恶意软件的文件。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="4dfa8-131">立即查看文件是只读还是签出。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="4dfa8-132">签出并签入文件。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-132">Check out and check in files.</span></span>
- <span data-ttu-id="4dfa8-133">固定、取消固定和更改文件的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="4dfa8-134">确定哪些文件需要元数据</span><span class="sxs-lookup"><span data-stu-id="4dfa8-134">Identify which files need metadata</span></span>
- <span data-ttu-id="4dfa8-135">从更多筛选器选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="4dfa8-136">基于列标题对文件进行分组。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-136">Group files based on column headings.</span></span>
- <span data-ttu-id="4dfa8-137">修改列设置 (向左或向右移动，) 和列宽。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="4dfa8-138">默认链接类型设置</span><span class="sxs-lookup"><span data-stu-id="4dfa8-138">Default link type setting</span></span>

<span data-ttu-id="4dfa8-139">当用户共享文件时，默认显示的共享链接类型在SharePoint设置。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="4dfa8-140">有关 [信息，请参阅在用户获取用于共享的链接时更改](/sharepoint/change-default-sharing-link) 默认链接类型。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4dfa8-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="4dfa8-141">Related topics</span></span>

<span data-ttu-id="4dfa8-142">[SharePoint和Teams：更好地在一起](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="4dfa8-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="4dfa8-143">来宾体验介绍</span><span class="sxs-lookup"><span data-stu-id="4dfa8-143">What the guest experience is like</span></span>](guest-experience.md)