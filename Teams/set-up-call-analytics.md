---
title: 为 Microsoft Teams 设置呼叫分析
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 为 设置按用户通话分析，以识别和排查 Microsoft Teams 通话质量问题。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117130"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="cde72-103">为 Microsoft Teams 设置呼叫分析</span><span class="sxs-lookup"><span data-stu-id="cde72-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="cde72-104">作为 Microsoft Teams 管理员，可以使用按用户的呼叫分析来排查单个用户的 Teams 通话质量和 **连接问题**。</span><span class="sxs-lookup"><span data-stu-id="cde72-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="cde72-105">若要充分利用呼叫分析，请设置以下各项：</span><span class="sxs-lookup"><span data-stu-id="cde72-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="cde72-106">向人员（例如支持人员代理）分配专门的支持角色，让他们查看用户的呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="cde72-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="cde72-107">这些支持角色无法访问 Teams 管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cde72-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="cde72-108">通过上传 .tsv 或 .csv 数据文件，将建筑物、站点和租户信息添加到每个用户的调用分析。</span><span class="sxs-lookup"><span data-stu-id="cde72-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="cde72-109">当你准备开始使用按用户的呼叫分析时，请阅读使用每用户呼叫分析来 [排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="cde72-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="cde72-110">授予支持和支持人员的权限</span><span class="sxs-lookup"><span data-stu-id="cde72-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="cde72-111">作为 Teams 管理员，你可以完全访问所有用户的呼叫分析信息。</span><span class="sxs-lookup"><span data-stu-id="cde72-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="cde72-112">我们创建了一些专门的 Azure Active Directory 角色，你可以将其分配给支持人员和支持人员代理，以便他们还可以访问每个用户的呼叫分析 (而无需访问 Teams 管理中心) 的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cde72-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="cde72-113">将 **Teams 通信支持专家** 角色分配给应具有按用户呼叫分析的有限视图的用户， (第 1 层支持) 。</span><span class="sxs-lookup"><span data-stu-id="cde72-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="cde72-114">将 **Teams 通信支持工程师** 角色分配给需要完全访问每用户呼叫分析的用户 (第 2 层支持) 。</span><span class="sxs-lookup"><span data-stu-id="cde72-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="cde72-115">两个角色都无法访问 Teams 管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cde72-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="cde72-116">若要了解每个角色的作用，请阅读 [每个 Teams 支持角色的作用](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)是什么？</span><span class="sxs-lookup"><span data-stu-id="cde72-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="cde72-117">有关 Teams 管理员角色的信息，请参阅[使用 Teams 管理员角色管理 Teams。](using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cde72-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="cde72-118">若要了解如何在 Azure Active Directory 中分配管理员角色，请参阅在 [Azure Active Directory 中查看和分配角色](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="cde72-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="cde72-119">若要了解如何在 Azure Active Directory 中分配管理角色，请参阅在 [Azure Active Directory 中查看和分配角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="cde72-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="cde72-120">上传 .tsv 或 .csv 文件以添加建筑物、站点和租户信息</span><span class="sxs-lookup"><span data-stu-id="cde72-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="cde72-121">可以通过上传 .csv 或 .tsv 文件，将建筑物、站点和租户信息添加到每个用户的调用分析。</span><span class="sxs-lookup"><span data-stu-id="cde72-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="cde72-122">使用所有这些信息，调用分析可以将 IP 地址映射到物理位置。</span><span class="sxs-lookup"><span data-stu-id="cde72-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="cde72-123">管理员和技术支持代理可以使用此信息来帮助发现呼叫问题的趋势。</span><span class="sxs-lookup"><span data-stu-id="cde72-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="cde72-124">例如，为什么同一大楼中的用户遇到类似的呼叫质量问题？</span><span class="sxs-lookup"><span data-stu-id="cde72-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="cde72-125">如果你是 Teams 或 Skype for Business 管理员，可以使用现有租户，然后从 Teams 或 Skype for Business 呼叫质量仪表板 (CQD) 。</span><span class="sxs-lookup"><span data-stu-id="cde72-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="cde72-126">首先，从 CQD 下载文件，然后上传它以调用分析。</span><span class="sxs-lookup"><span data-stu-id="cde72-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="cde72-127">若要下载现有数据文件，请转到 Microsoft **Teams** 管理中心"立即  >  **调用质量仪表板**  >  **上传"。**</span><span class="sxs-lookup"><span data-stu-id="cde72-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="cde72-128">在"**我的上传"列表中\*\*\*\*，单击文件** 旁边的"下载"。</span><span class="sxs-lookup"><span data-stu-id="cde72-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="cde72-129">若要上传新文件，请转到 **Microsoft Teams 管理** 中心  >  **"** 位置"，然后选择"**上传位置** 数据"或"**替换位置数据"。**</span><span class="sxs-lookup"><span data-stu-id="cde72-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="cde72-130">如果要从头开始创建 .tsv 或 .csv 文件，请参阅 [上传租户和生成数据](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="cde72-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cde72-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="cde72-131">Related topics</span></span>

[<span data-ttu-id="cde72-132">使用每个用户的呼叫分析来排查通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="cde72-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="cde72-133">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="cde72-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)