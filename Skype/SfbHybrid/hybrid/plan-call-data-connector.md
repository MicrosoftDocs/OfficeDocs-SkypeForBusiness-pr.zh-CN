---
title: 规划呼叫数据连接器|呼叫质量仪表板监视混合分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Overview of using Skype for Business Online telemetry tools to monitor an on-premises implementation in a hybrid scenario.
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110548"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="25bd3-103">规划呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="25bd3-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="25bd3-104">概述</span><span class="sxs-lookup"><span data-stu-id="25bd3-104">Overview</span></span>

<span data-ttu-id="25bd3-105">本主题介绍实施 Skype for Business Server 呼叫数据连接器的好处、规划注意事项和要求。</span><span class="sxs-lookup"><span data-stu-id="25bd3-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="25bd3-106">有关配置呼叫数据连接器的信息，请参阅配置 [呼叫数据连接器](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="25bd3-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="25bd3-107">呼叫数据连接器极大地简化了混合环境中呼叫监控，因为不再需要使用不同的本地和联机工具集来监视所有用户的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="25bd3-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="25bd3-108">无论用户是在本地还是联机，都可以选择在线查看整个组织的通话质量。</span><span class="sxs-lookup"><span data-stu-id="25bd3-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="25bd3-109">使用呼叫数据连接器，可以使用单个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="25bd3-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="25bd3-110">监视 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 中的用户体验。</span><span class="sxs-lookup"><span data-stu-id="25bd3-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="25bd3-111">查看并排查整个网络的问题。</span><span class="sxs-lookup"><span data-stu-id="25bd3-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="25bd3-112">为呼叫分析分配支持人员角色和管理员角色，以便支持人员可以查看他们的责任领域并排除其故障。</span><span class="sxs-lookup"><span data-stu-id="25bd3-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="25bd3-113">通过呼叫数据连接器，Skype for Business Server 将呼叫数据推送到云服务，以便你可以利用 Skype for Business Online 呼叫分析 (CA) 和呼叫质量仪表板 (CQD) 工具，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="25bd3-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="25bd3-115">服务器将用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 数据推送到联机服务。</span><span class="sxs-lookup"><span data-stu-id="25bd3-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="25bd3-116">通话分析和 CQD 工具使你可以监视通话质量，并解决 Microsoft Teams 和 Skype for Business 服务的连接问题，如下所示：</span><span class="sxs-lookup"><span data-stu-id="25bd3-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="25bd3-117">通话分析侧重于特定通话的质量问题。</span><span class="sxs-lookup"><span data-stu-id="25bd3-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="25bd3-118">它显示有关 Skype for Business 帐户中每个用户的呼叫和会议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="25bd3-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="25bd3-119">借助通话分析，你可以向支持人员分配权限，支持人员可以监视呼叫，而无需访问 Skype for Business 管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="25bd3-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="25bd3-120">通话质量仪表板重点关注整个组织的网络性能和问题。</span><span class="sxs-lookup"><span data-stu-id="25bd3-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="25bd3-121">Skype for Business 管理员和网络工程师使用此工具对网络性能进行故障排除和优化。</span><span class="sxs-lookup"><span data-stu-id="25bd3-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="25bd3-122">有关详细信息，请参阅通话 [分析和通话质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="25bd3-122">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="25bd3-123">当然，你可能希望在本地保留一些通话质量数据。</span><span class="sxs-lookup"><span data-stu-id="25bd3-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="25bd3-124">例如，如果您将第三方解决方案与自定义报表和工作流一同使用，则可能会这样。</span><span class="sxs-lookup"><span data-stu-id="25bd3-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="25bd3-125">呼叫数据连接器允许你配置向联机服务发送数据，同时在本地服务器上保留数据副本，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="25bd3-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="25bd3-127">要求</span><span class="sxs-lookup"><span data-stu-id="25bd3-127">Requirements</span></span>

<span data-ttu-id="25bd3-128">以下要求假定你已在支持的拓扑中部署了 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="25bd3-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="25bd3-129">有关部署 Skype for Business Server 和支持的拓扑结构的信息，请参阅 [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="25bd3-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md).</span></span> <span data-ttu-id="25bd3-130">若要配置呼叫数据连接器，您必须：</span><span class="sxs-lookup"><span data-stu-id="25bd3-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="25bd3-131">启用混合连接。</span><span class="sxs-lookup"><span data-stu-id="25bd3-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="25bd3-132">如果你已部署 Skype for Business Server 并且想要启用呼叫数据连接器，则必须确保在本地环境和联机环境之间设置了混合连接。</span><span class="sxs-lookup"><span data-stu-id="25bd3-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="25bd3-133">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="25bd3-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="25bd3-134">有关详细信息，请参阅规划 Skype for Business Server 与 [Microsoft 365 或 Office 365](plan-hybrid-connectivity.md) 之间的混合连接和配置 Skype for Business Server 与 [Microsoft 365 或 Office 365](configure-hybrid-connectivity.md)之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="25bd3-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="25bd3-135">向 Microsoft 365 或 Office 365 组织进行身份验证，并确保已启用以下角色：</span><span class="sxs-lookup"><span data-stu-id="25bd3-135">Authenticate to your Microsoft 365 or Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="25bd3-136">Skype for Business Server 管理员</span><span class="sxs-lookup"><span data-stu-id="25bd3-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="25bd3-137">Microsoft 365 或 Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="25bd3-137">Microsoft 365 or Office 365 Global Administrator</span></span>

- <span data-ttu-id="25bd3-138">如果尚未打开，请打开通话质量仪表板，如打开和使用 Microsoft Teams 和 Skype for Business Online 的通话质量 [仪表板中所述](/microsoftteams/turning-on-and-using-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="25bd3-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="25bd3-139">使用本地 LCSCdr 和 QoEMetrics 数据库启用监控的前端池。</span><span class="sxs-lookup"><span data-stu-id="25bd3-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="25bd3-140">如果没有这一点，呼叫数据连接器将没有要处理的指标数据。</span><span class="sxs-lookup"><span data-stu-id="25bd3-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25bd3-141">如果未在前端池上启用监控，呼叫数据连接器将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="25bd3-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="25bd3-142">正确配置 [了服务器到服务器身份验证](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="25bd3-142">Properly configured [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="25bd3-143">本地和在线通话质量仪表板与 CQD (比较) 报告</span><span class="sxs-lookup"><span data-stu-id="25bd3-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="25bd3-144">功能报告</span><span class="sxs-lookup"><span data-stu-id="25bd3-144">Feature reports</span></span> | <span data-ttu-id="25bd3-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="25bd3-145">Skype for Business Online</span></span> | <span data-ttu-id="25bd3-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="25bd3-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="25bd3-147">应用程序共享指标</span><span class="sxs-lookup"><span data-stu-id="25bd3-147">Application sharing metric</span></span> |<span data-ttu-id="25bd3-148">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-148">Yes</span></span> | <span data-ttu-id="25bd3-149">受限</span><span class="sxs-lookup"><span data-stu-id="25bd3-149">Limited</span></span> |
| <span data-ttu-id="25bd3-150">客户构建信息</span><span class="sxs-lookup"><span data-stu-id="25bd3-150">Customer building information</span></span>| <span data-ttu-id="25bd3-151">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-151">Yes</span></span> | <span data-ttu-id="25bd3-152">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-152">Yes</span></span> |
| <span data-ttu-id="25bd3-153">向下钻取分析</span><span class="sxs-lookup"><span data-stu-id="25bd3-153">Drill-down analytics</span></span> | <span data-ttu-id="25bd3-154">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-154">Yes</span></span> | <span data-ttu-id="25bd3-155">否</span><span class="sxs-lookup"><span data-stu-id="25bd3-155">No</span></span> |
| <span data-ttu-id="25bd3-156">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="25bd3-156">Media reliability metrics</span></span> | <span data-ttu-id="25bd3-157">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-157">Yes</span></span> | <span data-ttu-id="25bd3-158">受限</span><span class="sxs-lookup"><span data-stu-id="25bd3-158">Limited</span></span> |
| <span data-ttu-id="25bd3-159">开箱后报告</span><span class="sxs-lookup"><span data-stu-id="25bd3-159">Out-of-the-box reports</span></span> | <span data-ttu-id="25bd3-160">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-160">Yes</span></span> | <span data-ttu-id="25bd3-161">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-161">Yes</span></span> |
| <span data-ttu-id="25bd3-162">概述报告</span><span class="sxs-lookup"><span data-stu-id="25bd3-162">Overview reports</span></span> | <span data-ttu-id="25bd3-163">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-163">Yes</span></span> | <span data-ttu-id="25bd3-164">否</span><span class="sxs-lookup"><span data-stu-id="25bd3-164">No</span></span> |
| <span data-ttu-id="25bd3-165">每用户报告</span><span class="sxs-lookup"><span data-stu-id="25bd3-165">Per user reports</span></span> | <span data-ttu-id="25bd3-166">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-166">Yes</span></span> | <span data-ttu-id="25bd3-167">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-167">Yes</span></span> |
| <span data-ttu-id="25bd3-168">报告集自定义</span><span class="sxs-lookup"><span data-stu-id="25bd3-168">Report set customization</span></span> <br> <span data-ttu-id="25bd3-169"> (、删除、修改报告) </span><span class="sxs-lookup"><span data-stu-id="25bd3-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="25bd3-170">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-170">Yes</span></span> | <span data-ttu-id="25bd3-171">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-171">Yes</span></span> |
| <span data-ttu-id="25bd3-172">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="25bd3-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="25bd3-173">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-173">Yes</span></span> | <span data-ttu-id="25bd3-174">否</span><span class="sxs-lookup"><span data-stu-id="25bd3-174">No</span></span> |
| <span data-ttu-id="25bd3-175">用于编程访问的数据 API</span><span class="sxs-lookup"><span data-stu-id="25bd3-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="25bd3-176">到 CQD</span><span class="sxs-lookup"><span data-stu-id="25bd3-176">to CQD</span></span> | <span data-ttu-id="25bd3-177">否</span><span class="sxs-lookup"><span data-stu-id="25bd3-177">No</span></span> | <span data-ttu-id="25bd3-178">是</span><span class="sxs-lookup"><span data-stu-id="25bd3-178">Yes</span></span> |
||||