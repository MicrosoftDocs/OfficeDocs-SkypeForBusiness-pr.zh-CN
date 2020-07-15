---
title: 在 Microsoft Teams 中共享文件
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: 了解 Microsoft 团队中的文件共享体验。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138324"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="ea7e4-103">在 Microsoft Teams 中共享文件</span><span class="sxs-lookup"><span data-stu-id="ea7e4-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="ea7e4-104">在 Microsoft 团队中，用户可以与组织内部和外部的其他团队用户共享内容。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="ea7e4-105">团队中的共享基于 SharePoint 和 OneDrive 中配置的设置，因此你为 SharePoint 和 OneDrive 设置的任何内容也将控制团队中的共享。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="ea7e4-106">概述</span><span class="sxs-lookup"><span data-stu-id="ea7e4-106">Overview</span></span>

<span data-ttu-id="ea7e4-107">用户可以从 OneDrive、他们有权访问的团队和网站以及他们的计算机共享文件。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="ea7e4-108">若要共享文件，用户可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea7e4-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="ea7e4-109">在通道中，单击 "**附加**" （曲别针图标），选择 "**最近**"、"**浏览团队和频道**"、" **OneDrive**" 或 **"从我的计算机上传**"，然后选择要共享的文件。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="ea7e4-110">![显示从频道共享文件的屏幕截图](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="ea7e4-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="ea7e4-111">在聊天中，单击 "**附加**" （曲别针图标），选择或 " **OneDrive** " 或 **"从我的计算机上传**"，然后选择要共享的文件。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="ea7e4-112">![显示从聊天共享文件的屏幕截图](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="ea7e4-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="ea7e4-113">将共享链接复制并粘贴在撰写框中。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="ea7e4-114">![显示 "撰写" 框中的文件预览的屏幕截图](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="ea7e4-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="ea7e4-115">您需要了解的有关文件共享体验的哪些信息</span><span class="sxs-lookup"><span data-stu-id="ea7e4-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="ea7e4-116">共享文件和共享链接的权限</span><span class="sxs-lookup"><span data-stu-id="ea7e4-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="ea7e4-117">当用户通过在 OneDrive 或团队和频道中浏览来共享文件时，将向所有收件人授予访问权限以及[在组织级别设置的默认权限](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="ea7e4-118">当用户复制和粘贴共享链接时，将接受在该共享链接上设置的权限，并将 SharePoint URL 缩短为文件名。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="ea7e4-119">换言之，团队只使用文件名链接到文件。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="ea7e4-120">当用户从团队内部共享文件时，他们可以设置可以访问该文件的人员，就像在 Microsoft 365 中访问该文件一样。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="ea7e4-121">他们可以向组织中的人员、拥有现有访问权限的人员或特定用户（可在1:1 聊天、群组聊天或频道中包括人员）授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="ea7e4-122">共享文件时，文件预览在邮件中可用，以及所有文件操作，如 "**打开联机**"、"**下载**" 和 "**复制链接**"。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="ea7e4-123">默认情况下，将在 "团队" 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="ea7e4-124">有时，共享链接可能在用户发送邮件时未转换为文件预览。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="ea7e4-125">文件预览将由系统生成，但在这种情况下，不会将共享链接缩短为唯一的文件名。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="ea7e4-126">当用户在聊天或频道中共享文件时，系统会通知某些收件人是否有查看该文件的权限。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="ea7e4-127">他们可以在共享文件之前更改文件的权限，方法是单击 "文件预览" 旁边的箭头（现在出现在邮件中）。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![收件人没有权限时通知的屏幕截图](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="ea7e4-129">复制团队中的共享链接</span><span class="sxs-lookup"><span data-stu-id="ea7e4-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="ea7e4-130">用户可以复制 SharePoint 共享链接，并更改共享权限，就像他们在 Microsoft 365 中所做的那样。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="ea7e4-131">他们可以向您的组织中的人员、拥有现有访问权限的人员或特定人员授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="ea7e4-132">链接的默认权限与组织级别的默认权限集相同，除非 SharePoint 网站级别权限覆盖它。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="ea7e4-133">在 OneDrive 和 SharePoint 中配置共享</span><span class="sxs-lookup"><span data-stu-id="ea7e4-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="ea7e4-134">有关在 OneDrive 和 SharePoint 中共享文件的详细信息，包括如何配置共享以及如何打开和关闭共享，请参阅：</span><span class="sxs-lookup"><span data-stu-id="ea7e4-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="ea7e4-135">[外部共享概述](https://docs.microsoft.com/sharepoint/external-sharing-overview)-介绍用户共享时所发生的情况，具体取决于他们共享的内容和用户。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="ea7e4-136">[管理共享设置](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)-介绍全局管理员和 sharepoint 管理员如何更改其组织级别的 SharePoint 和 OneDrive 共享设置。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="ea7e4-137">[为网站启用或禁用外部共享](https://docs.microsoft.com/sharepoint/change-external-sharing-site)-介绍全局管理员和 SharePoint 管理员如何为网站打开或关闭外部共享。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="ea7e4-138">[更改网站的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)-介绍如何设置默认链接类型，以使其更具限制性。</span><span class="sxs-lookup"><span data-stu-id="ea7e4-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="ea7e4-139">更多信息</span><span class="sxs-lookup"><span data-stu-id="ea7e4-139">More information</span></span>

- [<span data-ttu-id="ea7e4-140">SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="ea7e4-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="ea7e4-141">SharePoint 和团队：更好地协作</span><span class="sxs-lookup"><span data-stu-id="ea7e4-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="ea7e4-142">共享 OneDrive 文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="ea7e4-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="ea7e4-143">共享 SharePoint 文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="ea7e4-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
