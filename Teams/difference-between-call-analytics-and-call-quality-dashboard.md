---
title: 通话分析和通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 了解有关呼叫分析和呼叫质量仪表板以及何时使用它们来监视和解决呼叫质量问题。
ms.openlocfilehash: c85bcecd31c978616e5394740efac6bb5c28c07c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199792"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="50139-103">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="50139-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="50139-104">Microsoft 团队和 for Business 的 Skype 提供两种方法可以监视和解决呼叫质量问题： 呼叫分析和呼叫质量仪表板 (CQD)。</span><span class="sxs-lookup"><span data-stu-id="50139-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="50139-105">本文介绍这两类，并告诉您何时使用每个。</span><span class="sxs-lookup"><span data-stu-id="50139-105">This article describes both and tells you when to use each one.</span></span>

<span data-ttu-id="50139-106">呼叫分析和 CQD 并行运行和可在独立或一起使用。</span><span class="sxs-lookup"><span data-stu-id="50139-106">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="50139-107">例如，假设 communications 支持专家确定所需解决呼叫问题的更多帮助。</span><span class="sxs-lookup"><span data-stu-id="50139-107">For example, say a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="50139-108">Communications 支持专家将传递对通信支持工程师，哪些人有权调用分析中的信息比通信支持专业人员的调用。</span><span class="sxs-lookup"><span data-stu-id="50139-108">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="50139-109">反过来，communications 支持工程师可以通知问题的网络工程师。</span><span class="sxs-lookup"><span data-stu-id="50139-109">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="50139-110">网络工程师可能会检查 CQD 以查看整个网站相关问题可能是参与呼叫问题的原因。</span><span class="sxs-lookup"><span data-stu-id="50139-110">The network engineer might check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>

## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="50139-111">什么是呼叫分析，我何时应使用它？</span><span class="sxs-lookup"><span data-stu-id="50139-111">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="50139-112">**呼叫分析现已推出[Microsoft 团队管理中心](https://admin.teams.microsoft.com)中。**</span><span class="sxs-lookup"><span data-stu-id="50139-112">**Call Analytics is now available in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).**</span></span> <span data-ttu-id="50139-113">若要查看的所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过仪表板用户可以搜索用户的配置文件页上查找或**用户**的左侧导航中查找用户执行此操作。</span><span class="sxs-lookup"><span data-stu-id="50139-113">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

<span data-ttu-id="50139-114">呼叫分析显示设备、 网络和与特定的呼叫和会议中每个用户的 Microsoft 团队或 Skype 业务帐户相关的连接的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="50139-114">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="50139-115">此用户未为什么必须质量欠佳的呼叫下午的？</span><span class="sxs-lookup"><span data-stu-id="50139-115">Why did this user have a poor call this afternoon?</span></span> <span data-ttu-id="50139-116">使用呼叫分析，Office 365 管理员或培训帮助台代理可以调查设备、 网络、 连接和解决的 Microsoft 团队和 Skype for Business 中的呼叫质量和连接问题其呼叫相关的其他因素。</span><span class="sxs-lookup"><span data-stu-id="50139-116">Using Call Analytics, an Office 365 admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to his call to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="50139-117">若要查看此信息的用户的 Microsoft 团队管理中心中，单击**呼叫历史记录**选项卡中的用户详细信息页，显示该用户参与 30 天内的所有呼叫和会议的用户。</span><span class="sxs-lookup"><span data-stu-id="50139-117">To see this information for a user in the Microsoft Teams admin center, click the **Call History** tab for that user in the user detail page, showing all the calls and meetings that user has participated in for the last 30 days.</span></span>

![调用分析用户数据。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="50139-119">要获取有关给定会话包括详细的媒体和网络统计信息的其他信息，请单击的会话，若要查看的详细信息。</span><span class="sxs-lookup"><span data-stu-id="50139-119">To get additional information about a given session including detailed media and networking statistics, click on a session to see the details.</span></span>

![调用分析用户会话数据。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

<span data-ttu-id="50139-121">如果您希望非管理员，例如从外部供应商，帮助台代理用于呼叫的分析，就可以分配权限，以便他们可以使用调用分析，但不是能访问的 Microsoft 团队管理中心的其余部分：</span><span class="sxs-lookup"><span data-stu-id="50139-121">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams admin center:</span></span> 
  
- <span data-ttu-id="50139-122">**通过通信帮助台代理支持专员权限**： 代理，请参阅一组有限的数据和呼叫分析中的个人身份信息 (PII)。</span><span class="sxs-lookup"><span data-stu-id="50139-122">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="50139-123">它们可以解决呼叫，但它们将交给会议问题的通信支持工程师。</span><span class="sxs-lookup"><span data-stu-id="50139-123">They can troubleshoot calls, but they will hand off problems with meetings to a communications support engineer.</span></span>
    
- <span data-ttu-id="50139-124">**通过通信帮助台代理支持工程师权限**： 代理，请参阅呼叫分析中的所有可用数据和解决呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="50139-124">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="50139-125">拥有完全访问呼叫日志和客户信息。</span><span class="sxs-lookup"><span data-stu-id="50139-125">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="50139-126">Communications 支持专家角色等效从预览门户第 1 层支持角色和 communications 支持工程师角色等效从预览门户第 2 层支持角色。</span><span class="sxs-lookup"><span data-stu-id="50139-126">The communications support specialist role is equivalent to tier 1 support role from the preview portal and the communications support engineer role is equivalent to tier 2 support role from the preview portal.</span></span>

<span data-ttu-id="50139-127">有关 communications 支持专家和通信支持工程师角色，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="50139-127">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50139-128">帮助台代理权限和网络拓扑上载在管理中心中的 Microsoft 团队是可用。</span><span class="sxs-lookup"><span data-stu-id="50139-128">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams admin center.</span></span> <span data-ttu-id="50139-129">Communications 支持专家和 Communications 支持工程师可以使用此门户访问呼叫分析和呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="50139-129">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>
    
<span data-ttu-id="50139-130">有关设置呼叫分析的详细信息，请参阅[Set up 商业调用分析的 Skype](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="50139-130">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="50139-131">有关帮助台代理与呼叫分析的工作原理的详细信息，请参阅[使用呼叫分析解决质量欠佳的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="50139-131">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="50139-132">什么是呼叫质量仪表板中，以及何时使用它？</span><span class="sxs-lookup"><span data-stu-id="50139-132">What's the Call Quality Dashboard, and when should I use it?</span></span>
  
<span data-ttu-id="50139-133">调用分析旨在帮助管理员，帮助台代理诊断与特定的呼叫的呼叫质量问题，而呼叫质量仪表板 (CQD) 旨在帮助团队 admins，对于业务管理员 Skype 和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="50139-133">Whereas Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Teams admins, Skype for Business admins, and network engineers optimize a network.</span></span> <span data-ttu-id="50139-134">CQD 从特定的用户将焦点移和改为查看聚合信息针对整个团队或 Skype 业务组织。</span><span class="sxs-lookup"><span data-stu-id="50139-134">CQD shifts focus from specific users and instead looks at aggregate information for an entire Teams or Skype for Business organization.</span></span> <span data-ttu-id="50139-135">有关详细信息，请参阅[呼叫质量仪表板个团队和 Skype 业务 online 的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。</span><span class="sxs-lookup"><span data-stu-id="50139-135">For more details, see [Features of the Call Quality Dashboard for Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="50139-136">也许用户的质量欠佳的呼叫质量是由于还影响多个其他用户的网络问题。</span><span class="sxs-lookup"><span data-stu-id="50139-136">Maybe the user's poor call quality is due to a network issue that's also affecting many other users.</span></span> <span data-ttu-id="50139-137">单个呼叫体验不显示在 CQD，但捕获 for Business 中使用的 Microsoft 团队或 Skype 所做的呼叫的总体质量。</span><span class="sxs-lookup"><span data-stu-id="50139-137">The individual call experience isn't visible in CQD, but the overall quality of calls made using Microsoft Teams or Skype for Business is captured.</span></span> <span data-ttu-id="50139-138">与 CQD，总体模式可能成为明显，允许网络工程师进行的呼叫质量的明智的评估。</span><span class="sxs-lookup"><span data-stu-id="50139-138">With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality.</span></span> <span data-ttu-id="50139-139">CQD 提供报告为您提供深入的呼叫质量指标的总体呼叫质量、 服务器到客户端流、 客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="50139-139">CQD provides reports of call quality metrics that give you insights into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>
  
![呼叫质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="50139-142">借助 CQD 的 Location-Enhanced 报告，可以评估聚合呼叫质量和可靠性中用户的构建以确定问题是否被隔离到单个用户，或者影响的用户更大条线段。</span><span class="sxs-lookup"><span data-stu-id="50139-142">With the help of CQD's Location-Enhanced Reports, aggregate call quality and reliability within the user's building can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span>

![呼叫质量仪表板位置增强报告的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> <span data-ttu-id="50139-146">若要启用 CQD 中构建或特定于终结点的视图，管理员必须在 CQD 的租户数据上载页上的[上载构建或终结点的信息](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。</span><span class="sxs-lookup"><span data-stu-id="50139-146">To enable building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) on CQD's Tenant Data Upload page.</span></span> 

<span data-ttu-id="50139-147">如果您希望非管理员，帮助台代理，如用于呼叫质量仪表板中，您可以分配这些用户的**团队 Communications 支持工程师**、**团队 Communications 支持专员**或**报告读者**角色。</span><span class="sxs-lookup"><span data-stu-id="50139-147">If you want non-admins, such as helpdesk agents, to use Call Quality Dashboard, you can assign those users the **Teams Communications Support Engineer**, **Teams Communications Support Specialist**, or **Reports Reader** role.</span></span> <span data-ttu-id="50139-148">具有以下角色的用户可以访问呼叫质量仪表板：</span><span class="sxs-lookup"><span data-stu-id="50139-148">Users with the following roles can access Call Quality Dashboard:</span></span>

- <span data-ttu-id="50139-149">全局管理员</span><span class="sxs-lookup"><span data-stu-id="50139-149">Global Administrator</span></span>
- <span data-ttu-id="50139-150">Skype 的业务管理员</span><span class="sxs-lookup"><span data-stu-id="50139-150">Skype for Business Administrator</span></span>
- <span data-ttu-id="50139-151">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="50139-151">Teams Service Administrator</span></span>
- <span data-ttu-id="50139-152">Teams 通信管理员</span><span class="sxs-lookup"><span data-stu-id="50139-152">Teams Communications Administrator</span></span>
- <span data-ttu-id="50139-153">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="50139-153">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="50139-154">团队 Communications 支持专家</span><span class="sxs-lookup"><span data-stu-id="50139-154">Teams Communications Support Specialist</span></span>
- <span data-ttu-id="50139-155">报告读者</span><span class="sxs-lookup"><span data-stu-id="50139-155">Reports Reader</span></span>

> [!NOTE]
> <span data-ttu-id="50139-156">团队 Communications 支持工程师、 团队 Communications 支持专家，和报告读者角色不能修改 CQD 的租户数据上载页面上的文件也不激活 CQD 租户。</span><span class="sxs-lookup"><span data-stu-id="50139-156">The Teams Communications Support Engineer, Teams Communications Support Specialist, and Reports Reader roles cannot modify files on CQD's Tenant Data Upload page nor activate CQD for a tenant.</span></span>

<span data-ttu-id="50139-157">有关这些角色的详细信息，请参阅[有关 Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="50139-157">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="50139-158">有关 CQD 的详细信息，请参阅[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)和[维度和度量值的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="50139-158">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="50139-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="50139-159">Related topics</span></span>

[<span data-ttu-id="50139-160">视频： 呼叫质量概述</span><span class="sxs-lookup"><span data-stu-id="50139-160">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="50139-161">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="50139-161">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="50139-162">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="50139-162">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="50139-163">打开和使用呼叫质量仪表板的 Microsoft 团队和 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="50139-163">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)
