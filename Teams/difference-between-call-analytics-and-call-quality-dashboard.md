---
title: 通话分析和通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 了解 "呼叫分析" 和 "呼叫质量" 仪表板以及何时使用它们监视和解决呼叫质量问题。
ms.openlocfilehash: 70efd7f17189d9aac2236383a07cfc5fc0a37096
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972463"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="2e6b4-103">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="2e6b4-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="2e6b4-104">Microsoft 团队和 Skype for business 为你提供了两种监视和解决通话质量问题的方法：调用分析和通话质量仪表板（CQD）。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="2e6b4-105">本文介绍这两种情况，并告诉你何时使用每一个。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-105">This article describes both and tells you when to use each one.</span></span>

<span data-ttu-id="2e6b4-106">调用分析和 CQD 并行运行，并且可以独立使用，也可以一起使用。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-106">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="2e6b4-107">例如，假设通信支持专家确定他们需要更多帮助来解决呼叫问题。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-107">For example, say that a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="2e6b4-108">通信支持专家将呼叫传递到通信支持工程师，该工程师可以访问呼叫分析中的更多信息，而不是通信支持专家。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-108">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="2e6b4-109">反过来，通信支持工程师可以向网络工程师发出警报，以解决问题。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-109">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="2e6b4-110">网络工程师可以检查 CQD，以了解与网站相关的总体问题是否可能是导致呼叫问题的原因。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-110">The network engineer can check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>

## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="2e6b4-111">什么是呼叫分析，何时应使用它？</span><span class="sxs-lookup"><span data-stu-id="2e6b4-111">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="2e6b4-112">**"呼叫分析" 现在可在[Microsoft 团队管理中心](https://admin.teams.microsoft.com)中使用。**</span><span class="sxs-lookup"><span data-stu-id="2e6b4-112">**Call Analytics is now available in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).**</span></span> <span data-ttu-id="2e6b4-113">若要查看用户的所有呼叫信息和数据，请使用用户个人资料页面上的 "**通话记录**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-113">To see all call information and data for a user, use the **Call History** tab on a user's profile page.</span></span> <span data-ttu-id="2e6b4-114">若要查看该选项卡，请从仪表板中搜索用户，或从左侧导航栏中的 "**用户**" 选项卡查找用户。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-114">To see the tab, either search for the user from the dashboard or find the user from the **Users** tab in the left navigation bar.</span></span>

<span data-ttu-id="2e6b4-115">"呼叫分析" 显示有关与 Microsoft 团队或 Skype for business 租户帐户中的每个用户的呼叫和会议相关的设备、网络和连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-115">Call Analytics shows detailed information about the devices, networks, and connectivity related to the calls and meetings for each user in a Microsoft Teams or Skype for Business tenant account.</span></span> <span data-ttu-id="2e6b4-116">为什么此用户的通话不太好？</span><span class="sxs-lookup"><span data-stu-id="2e6b4-116">Why did this user have a poor call this afternoon?</span></span> <span data-ttu-id="2e6b4-117">使用呼叫分析，Office 365 管理员或训练有素的帮助台工程师可以调查与呼叫相关的设备、网络、连接和其他因素，以解决 Microsoft 团队和 Skype for business 中的呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-117">With Call Analytics, an Office 365 admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to a call to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="2e6b4-118">若要在 Microsoft 团队管理中心中查看用户的此信息，请单击用户详细信息页面中该用户的 "**通话记录**" 选项卡，查看过去30天内该用户的所有通话和会议。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-118">To see this information for a user in the Microsoft Teams admin center, click the **Call History** tab for that user in the user detail page to see all calls and meetings for that user in the last 30 days.</span></span>

![所有分析用户数据的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="2e6b4-120">若要获取有关给定会话的其他信息（包括详细媒体和网络统计信息），请单击某个会话查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-120">To get additional information about a given session including detailed media and networking statistics, click a session to see the details.</span></span>

![呼叫分析用户会话数据的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

<span data-ttu-id="2e6b4-122">如果您希望非管理员（例如来自外部供应商的支持人员的代理）使用呼叫分析，则可以分配权限，以便他们可以使用呼叫分析，但不能访问 Microsoft 团队管理中心的其余部分：</span><span class="sxs-lookup"><span data-stu-id="2e6b4-122">If you want non-admins (such as helpdesk agents from an external vendor) to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams admin center:</span></span>
  
- <span data-ttu-id="2e6b4-123">**支持通信的帮助台代理专业权限**：代理在 "调用分析" 中看到一组有限的数据和个人身份信息（PII）。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-123">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="2e6b4-124">他们可以对通话进行故障排除，但他们会将会议问题提升到通信支持工程师。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-124">They can troubleshoot calls, but they escalate problems with meetings to a communications support engineer.</span></span>
- <span data-ttu-id="2e6b4-125">**支持通信支持工程师权限的帮助台工程师**：工程师查看呼叫分析中的所有可用数据，并对通话和会议进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-125">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="2e6b4-126">他们拥有通话记录和客户信息的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-126">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="2e6b4-127">通信支持专家角色等效于预览门户中的第1层支持角色，并且通信支持工程师角色等同于预览门户中的第2层支持角色。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-127">The communications support specialist role is equivalent to tier 1 support role from the preview portal and the communications support engineer role is equivalent to tier 2 support role from the preview portal.</span></span>

<span data-ttu-id="2e6b4-128">有关通信支持专家和通信支持工程师角色的详细信息，请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-128">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e6b4-129">帮助台代理权限和网络拓扑上载在 Microsoft 团队管理中心中可用。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-129">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2e6b4-130">通信支持专家和通信支持工程师可使用此门户访问呼叫分析和通话质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-130">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>

<span data-ttu-id="2e6b4-131">有关呼叫分析的详细信息，请参阅[设置 Skype For Business 呼叫分析](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-131">For details about Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="2e6b4-132">有关帮助台代理如何与呼叫分析配合使用的详细信息，请参阅[使用呼叫分析解决通话质量不佳问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-132">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="2e6b4-133">什么是通话质量仪表板，何时应使用它？</span><span class="sxs-lookup"><span data-stu-id="2e6b4-133">What's the Call Quality Dashboard, and when should I use it?</span></span>
  
<span data-ttu-id="2e6b4-134">"呼叫分析" 旨在帮助管理员和帮助台工程师解决*特定通话*的通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-134">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with *specific calls*.</span></span> <span data-ttu-id="2e6b4-135">通话质量仪表板（CQD）旨在帮助团队管理员、Skype for Business 管理员和网络工程师*优化网络*。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-135">Call Quality Dashboard (CQD) is designed to help Teams admins, Skype for Business admins, and network engineers *optimize a network*.</span></span> <span data-ttu-id="2e6b4-136">CQD 将焦点从特定用户转移，而是查看整个团队或 Skype for business 组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-136">CQD shifts focus from specific users and instead looks at aggregate information for an entire Teams or Skype for Business organization.</span></span> <span data-ttu-id="2e6b4-137">有关详细信息，请参阅[适用于团队和 Skype for Business Online 的通话质量仪表板的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-137">For more information, see [Features of the Call Quality Dashboard for Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="2e6b4-138">假设用户的通话质量很差是由于网络问题也会影响其他许多用户。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-138">Suppose a user's poor call quality is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="2e6b4-139">个人通话体验在 CQD 中不可见，但捕获使用 Microsoft 团队或 Skype for business 进行的整体通话质量。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-139">The individual call experience isn't visible in CQD, but the overall quality of calls made using Microsoft Teams or Skype for Business is captured.</span></span> <span data-ttu-id="2e6b4-140">通过 CQD，整体模式可能会变得显而易见，因此网络工程师可以及时了解通话质量。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-140">With  CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="2e6b4-141">CQD 提供了通话质量指标的报告，使你可以深入了解总通话质量、服务器客户端流、客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-141">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>
  
![通话质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="2e6b4-143">CQD 的位置-增强的报表聚合用户建筑物内的通话质量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-143">CQD's Location-Enhanced Reports aggregate call quality and reliability within a user's building.</span></span> <span data-ttu-id="2e6b4-144">可以对数据进行评估，以确定问题是独立于单个用户还是影响较大的用户段。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-144">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span>

![通话质量仪表板的位置增强的报表的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> <span data-ttu-id="2e6b4-146">若要在 CQD 中启用生成或特定于终结点的视图，管理员必须在 CQD 租户数据上载页面上[上载生成或终结点信息](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-146">To enable building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) on CQD's Tenant Data Upload page.</span></span>

<span data-ttu-id="2e6b4-147">如果希望非管理员用户（如帮助台代理）使用呼叫质量仪表板，则可以为这些用户分配下列角色之一，这些角色还具有访问呼叫质量仪表板所需的权限：</span><span class="sxs-lookup"><span data-stu-id="2e6b4-147">If you want non-admin users (such as helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which also have permissions needed to access Call Quality Dashboard:</span></span>

- <span data-ttu-id="2e6b4-148">全局管理员</span><span class="sxs-lookup"><span data-stu-id="2e6b4-148">Global Administrator</span></span>
- <span data-ttu-id="2e6b4-149">全局阅读器</span><span class="sxs-lookup"><span data-stu-id="2e6b4-149">Global Reader</span></span>
- <span data-ttu-id="2e6b4-150">Skype for Business 管理员</span><span class="sxs-lookup"><span data-stu-id="2e6b4-150">Skype for Business Administrator</span></span>
- <span data-ttu-id="2e6b4-151">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="2e6b4-151">Teams Service Administrator</span></span>
- <span data-ttu-id="2e6b4-152">Teams 通信管理员</span><span class="sxs-lookup"><span data-stu-id="2e6b4-152">Teams Communications Administrator</span></span>
- <span data-ttu-id="2e6b4-153">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="2e6b4-153">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="2e6b4-154">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="2e6b4-154">Teams Communications Support Specialist</span></span>
- <span data-ttu-id="2e6b4-155">报表读者</span><span class="sxs-lookup"><span data-stu-id="2e6b4-155">Reports Reader</span></span>

> [!NOTE]
> <span data-ttu-id="2e6b4-156">团队通信支持工程师、团队通信支持专家和报表读者角色无法在 CQD 的租户数据上载页面上修改文件，也无法为租户激活 CQD。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-156">The Teams Communications Support Engineer, Teams Communications Support Specialist, and Reports Reader roles cannot modify files on CQD's Tenant Data Upload page nor activate CQD for a tenant.</span></span>

<span data-ttu-id="2e6b4-157">有关这些角色的详细信息，请参阅[关于 Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-157">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="2e6b4-158">有关 CQD 的详细信息，请参阅[打开和使用 Microsoft 团队和 skype for Business online 的呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)和[Microsoft 团队和 Skype for Business Online 的通话质量仪表板中提供](dimensions-and-measures-available-in-call-quality-dashboard.md)的 skype For business online 和维度和度量。</span><span class="sxs-lookup"><span data-stu-id="2e6b4-158">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2e6b4-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="2e6b4-159">Related topics</span></span>

[<span data-ttu-id="2e6b4-160">视频：通话质量概述</span><span class="sxs-lookup"><span data-stu-id="2e6b4-160">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="2e6b4-161">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="2e6b4-161">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="2e6b4-162">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="2e6b4-162">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="2e6b4-163">打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="2e6b4-163">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)
