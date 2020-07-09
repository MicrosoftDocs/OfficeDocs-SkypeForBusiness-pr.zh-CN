---
title: 为 Microsoft 团队设置呼叫分析
ms.author: lolaj
author: LolaJacobsen
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
description: 设置每用户呼叫分析以识别和解决 Microsoft 团队通话质量问题。
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085308"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="25307-103">为 Microsoft 团队设置呼叫分析</span><span class="sxs-lookup"><span data-stu-id="25307-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="25307-104">作为 Microsoft 团队管理员，你可以使用每用户调用分析来解决团队呼叫**单个用户**的质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="25307-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="25307-105">若要充分利用呼叫分析，请设置以下内容：</span><span class="sxs-lookup"><span data-stu-id="25307-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="25307-106">将专用支持角色分配给人员（如帮助台代理），让他们可以查看用户的呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="25307-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="25307-107">这些支持角色无法访问团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="25307-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="25307-108">通过上载 tsv 或 .csv 数据文件，将生成、网站和租户信息添加到每用户调用分析。</span><span class="sxs-lookup"><span data-stu-id="25307-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="25307-109">当您准备好开始使用每用户呼叫分析时，请参阅[使用每用户呼叫分析来解决较差的通话质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="25307-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="25307-110">向支持部门和帮助台人员提供权限</span><span class="sxs-lookup"><span data-stu-id="25307-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="25307-111">作为团队管理员，您拥有对所有用户的 "调用分析" 信息的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="25307-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="25307-112">我们创建了一些专用的 Azure Active Directory 角色，你可以将其分配给支持人员和帮助台代理，以便他们也可以访问每个用户的呼叫分析（无需访问团队管理中心的其他人员中心）。</span><span class="sxs-lookup"><span data-stu-id="25307-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="25307-113">将**团队通信支持专家**角色分配给应该具有受限视图的每用户调用分析的用户（第1层支持）。</span><span class="sxs-lookup"><span data-stu-id="25307-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="25307-114">将**团队通信支持工程师**角色分配给需要对每用户调用分析具有完全访问权限的用户（第2层支持）。</span><span class="sxs-lookup"><span data-stu-id="25307-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="25307-115">这两个角色都有权访问团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="25307-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="25307-116">若要了解每个角色的用途，请阅读[每个团队支持角色执行哪些操作](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？</span><span class="sxs-lookup"><span data-stu-id="25307-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="25307-117">有关团队管理员角色的详细信息，请参阅[使用团队管理员角色管理团队](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="25307-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="25307-118">若要了解如何在 Azure Active Directory 中分配管理员角色，请参阅[在 Azure Active directory 中查看和分配角色](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="25307-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="25307-119">若要了解如何在 Azure Active Directory 中分配管理角色，请参阅[在 Azure Active directory 中查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="25307-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="25307-120">上载 tsv 或 .csv 文件以添加建筑物、网站和租户信息</span><span class="sxs-lookup"><span data-stu-id="25307-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="25307-121">你可以通过上载 .csv 或 tsv 文件，将生成、网站和租户信息添加到每用户调用分析。</span><span class="sxs-lookup"><span data-stu-id="25307-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="25307-122">有了所有这些信息，呼叫分析可以将 IP 地址映射到物理位置。</span><span class="sxs-lookup"><span data-stu-id="25307-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="25307-123">管理员和帮助台工程师可以使用此信息来帮助发现通话问题的趋势。</span><span class="sxs-lookup"><span data-stu-id="25307-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="25307-124">例如，为什么同一建筑物中的用户有类似的通话质量问题？</span><span class="sxs-lookup"><span data-stu-id="25307-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="25307-125">如果你是团队或 Skype for business 管理员，则可以使用现有租户并通过 "团队" 或 "Skype for business 呼叫质量" 仪表板（CQD）构建数据文件。</span><span class="sxs-lookup"><span data-stu-id="25307-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="25307-126">首先，从 CQD 下载文件，然后将其上传到 "调用分析"。</span><span class="sxs-lookup"><span data-stu-id="25307-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="25307-127">若要下载现有数据文件，请转到**Microsoft 团队管理中心**  >  **呼叫质量仪表板**"  >  **立即上载**"。</span><span class="sxs-lookup"><span data-stu-id="25307-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="25307-128">在 "**我的上载**" 列表中，单击所需文件旁边的 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="25307-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="25307-129">若要上传新文件，请转到 " **Microsoft 团队管理中心**  >  "**位置**，然后选择 "**上载位置数据**" 或 "**替换位置数据**"。</span><span class="sxs-lookup"><span data-stu-id="25307-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="25307-130">如果要从头开始创建 tsv 或 .csv 文件，请参阅[上载租户和生成数据](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="25307-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="25307-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="25307-131">Related topics</span></span>

[<span data-ttu-id="25307-132">使用每用户呼叫分析解决较差的通话质量</span><span class="sxs-lookup"><span data-stu-id="25307-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="25307-133">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="25307-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
