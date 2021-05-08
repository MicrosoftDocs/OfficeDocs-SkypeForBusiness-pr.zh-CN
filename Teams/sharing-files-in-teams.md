---
title: 在文件夹中共享文件和Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: 了解文件夹中的文件和文件夹共享Microsoft Teams。
ms.openlocfilehash: 53997f4493a0217e980427ab0d1f85d64095b9c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117020"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="ef834-103">在 Microsoft Teams 中共享文件</span><span class="sxs-lookup"><span data-stu-id="ef834-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="ef834-104">在 Microsoft Teams 中，用户可以与组织内外的其他 Teams 用户共享内容。</span><span class="sxs-lookup"><span data-stu-id="ef834-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="ef834-105">在 Teams 中共享文件和文件夹基于 SharePoint 和 OneDrive 中配置的设置，因此为 SharePoint 和 OneDrive 设置的内容也会影响 Teams 中的共享。</span><span class="sxs-lookup"><span data-stu-id="ef834-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="ef834-106">概述</span><span class="sxs-lookup"><span data-stu-id="ef834-106">Overview</span></span>

<span data-ttu-id="ef834-107">用户可以从 OneDrive、他们有权访问的团队和网站以及他们的计算机共享文件。</span><span class="sxs-lookup"><span data-stu-id="ef834-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="ef834-108">若要共享文件，用户可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ef834-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="ef834-p103">在频道中，单击“**附加**”（曲别针图标），选择“**最近**”、“**浏览团队和频道**”、“**OneDrive**”或“**从我的计算机上传**”，然后选择要共享的文件。</span><span class="sxs-lookup"><span data-stu-id="ef834-p103">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share. </span></span><br> 
    <span data-ttu-id="ef834-110">![显示从频道共享文件的屏幕截图](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="ef834-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="ef834-p104">在聊天中，单击“**附加**”（曲别针图标），选择  或者“**OneDrive**”或“**从我的计算机上传**”，然后选择要共享的文件。</span><span class="sxs-lookup"><span data-stu-id="ef834-p104">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share. </span></span><br>
    <span data-ttu-id="ef834-112">![显示从聊天共享文件的屏幕截图](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="ef834-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="ef834-113">复制并在撰写框中粘贴共享链接。</span><span class="sxs-lookup"><span data-stu-id="ef834-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="ef834-114">![在撰写框中显示文件预览的屏幕截图](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="ef834-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="ef834-115">共享文件和共享链接的权限</span><span class="sxs-lookup"><span data-stu-id="ef834-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="ef834-116">当用户在 Teams 中共享文件时，他们可以设置谁可以访问该文件，就像在 Microsoft 365 中所做的那样。</span><span class="sxs-lookup"><span data-stu-id="ef834-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="ef834-117">他们可以向任何人、你组织中的人员、具有现有访问权限的人员或特定人员授予访问权限（可以将人员包括在一对一聊天、群组聊天或频道中）。</span><span class="sxs-lookup"><span data-stu-id="ef834-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="ef834-118">共享文件时，消息中将显示文件预览，同时还可执行所有文件操作，如“**在线打开**”、“**下载**”和“**复制链接**”。</span><span class="sxs-lookup"><span data-stu-id="ef834-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="ef834-119">默认情况下，该文件在 Teams 中打开。</span><span class="sxs-lookup"><span data-stu-id="ef834-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="ef834-120">当用户在聊天或频道中共享文件时，系统会通知他们是否有部分或全部收件人没有查看文件的权限。</span><span class="sxs-lookup"><span data-stu-id="ef834-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="ef834-121">他们可以单击消息中现在显示的文件预览旁边的箭头，在共享文件之前更改文件的权限。</span><span class="sxs-lookup"><span data-stu-id="ef834-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![收件人没有权限时的通知屏幕截图](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="ef834-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="ef834-123">Related topics</span></span>

[<span data-ttu-id="ef834-124">SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="ef834-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="ef834-125">更改网站的默认链接类型</span><span class="sxs-lookup"><span data-stu-id="ef834-125">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

[<span data-ttu-id="ef834-126">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="ef834-126">Collaborate with guests in a team</span></span>](/microsoft-365/solutions/collaborate-as-team)