---
title: 规划呼叫数据连接器 |呼叫质量仪表板监控混合分析
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 使用业务联机遥测工具的 Skype 要监视的本地实现在混合方案的概述。
ms.openlocfilehash: 4e38f7d190cd30c1f0e39dc4cdfa5166ba6a929d
ms.sourcegitcommit: 183a2e40af762e6ab36f05ee8ed31a98e8b8be57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2019
ms.locfileid: "29690443"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="c977f-103">规划呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="c977f-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="c977f-104">概述</span><span class="sxs-lookup"><span data-stu-id="c977f-104">Overview</span></span>

<span data-ttu-id="c977f-105">本主题介绍优点、 规划注意事项和 Skype 实现业务服务器调用数据连接器的要求。</span><span class="sxs-lookup"><span data-stu-id="c977f-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="c977f-106">配置呼叫数据连接器的详细信息，请参阅[配置呼叫数据连接器](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="c977f-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c977f-107">在公共预览发布，只呼叫分析仪表板才可用。</span><span class="sxs-lookup"><span data-stu-id="c977f-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="c977f-108">调用数据连接器可大大简化呼叫监视混合环境中，因为您不再需要不同的内部部署和联机工具集用于监视所有您用户的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="c977f-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="c977f-109">驻留在本地或联机用户是否，您可以选择要查看为整个组织的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="c977f-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="c977f-110">与调用数据连接器，您可以使用一个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c977f-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="c977f-111">跨 Microsoft 团队、 业务 online Skype 和 Skype 业务 server 监视您的用户体验。</span><span class="sxs-lookup"><span data-stu-id="c977f-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="c977f-112">查看和解决跨网络问题。</span><span class="sxs-lookup"><span data-stu-id="c977f-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="c977f-113">为呼叫 Analytics 分配支持人员和管理员角色，以便可以为帮助台工作者可以查看和解决其责任范围提供强大功能。</span><span class="sxs-lookup"><span data-stu-id="c977f-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="c977f-114">使用呼叫数据连接器，业务服务器 Skype 调用将数据推送到云服务，以便您可以利用业务联机呼叫分析 (CA) 和呼叫质量仪表板 (CQD) 的工具，Skype 下图中所示：</span><span class="sxs-lookup"><span data-stu-id="c977f-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="c977f-116">服务器将用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 数据推送到联机服务。</span><span class="sxs-lookup"><span data-stu-id="c977f-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="c977f-117">调用分析和 CQD 工具，可以监视呼叫的质量和解决与 Microsoft 团队和 Skype 业务服务的连接问题，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c977f-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="c977f-118">与特定的呼叫的质量问题上调用分析焦点。</span><span class="sxs-lookup"><span data-stu-id="c977f-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="c977f-119">它业务帐户 Skype 中显示有关呼叫和会议的每个用户的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="c977f-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="c977f-120">与呼叫分析，就可以与用户然后可以呼叫监视没有访问权限的 Skype 其余业务管理中心的帮助台运算符分配权限。</span><span class="sxs-lookup"><span data-stu-id="c977f-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="c977f-121">呼叫质量仪表板着重于网络性能和跨组织问题。</span><span class="sxs-lookup"><span data-stu-id="c977f-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="c977f-122">为业务管理员和网络工程师 Skype 使用此工具来解决并优化网络性能。</span><span class="sxs-lookup"><span data-stu-id="c977f-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="c977f-123">有关详细信息，请参阅[呼叫分析和呼叫质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="c977f-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="c977f-124">当然，您可能想要保留在本地一些呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="c977f-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="c977f-125">例如，如果与自定义的报告和工作流使用第三方解决方案，这可能是这种情况。</span><span class="sxs-lookup"><span data-stu-id="c977f-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="c977f-126">调用数据连接器可以同时还在您的本地服务器上，保留一份数据，如下图中所示配置发送数据的联机服务：</span><span class="sxs-lookup"><span data-stu-id="c977f-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="c977f-128">要求</span><span class="sxs-lookup"><span data-stu-id="c977f-128">Requirements</span></span>

<span data-ttu-id="c977f-129">以下要求假定您已有 Skype 业务服务器部署中支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="c977f-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="c977f-130">有关部署 Skype 业务服务器和支持的拓扑的详细信息，请参阅[拓扑基础知识](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。</span><span class="sxs-lookup"><span data-stu-id="c977f-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="c977f-131">若要配置呼叫数据连接器，您必须：</span><span class="sxs-lookup"><span data-stu-id="c977f-131">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="c977f-132">启用混合连接性。</span><span class="sxs-lookup"><span data-stu-id="c977f-132">Enable Hybrid connectivity.</span></span> <span data-ttu-id="c977f-133">如果您已有 Skype 业务部署的服务器，并且您想要启用呼叫数据连接器，您必须确保已设置您的本地和联机环境之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="c977f-133">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="c977f-134">此有时也称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="c977f-134">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="c977f-135">有关详细信息，请参阅[规划之间 Skype Business Server 和 Office 365 的混合连接性](plan-hybrid-connectivity.md)和[Skype Business Server 和 Office 365 之间配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="c977f-135">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="c977f-136">对 Office 365 租户，并确保您拥有启用以下角色：</span><span class="sxs-lookup"><span data-stu-id="c977f-136">Authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="c977f-137">Skype 的业务服务器管理员</span><span class="sxs-lookup"><span data-stu-id="c977f-137">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="c977f-138">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="c977f-138">Office 365 Global Administrator</span></span>

- <span data-ttu-id="c977f-139">如果您未，打开呼叫质量仪表板[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述。</span><span class="sxs-lookup"><span data-stu-id="c977f-139">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="c977f-140">与本地 LcsCDR 和 QoEMetrics 数据库启用监控的前端池。</span><span class="sxs-lookup"><span data-stu-id="c977f-140">Enable the front end pool for Monitoring, with local LcsCDR and QoEMetrics databases.</span></span> <span data-ttu-id="c977f-141">没有它，调用数据连接器不具有要使用的度量数据。</span><span class="sxs-lookup"><span data-stu-id="c977f-141">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c977f-142">如果在前端池上没有启用监控，将无法正常呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="c977f-142">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="c977f-143">在本地和联机呼叫质量仪表板 (CQD) 的比较报告</span><span class="sxs-lookup"><span data-stu-id="c977f-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="c977f-144">功能报告</span><span class="sxs-lookup"><span data-stu-id="c977f-144">Feature reports</span></span> | <span data-ttu-id="c977f-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c977f-145">Skype for Business Online</span></span> | <span data-ttu-id="c977f-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c977f-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="c977f-147">应用程序共享指标</span><span class="sxs-lookup"><span data-stu-id="c977f-147">Application sharing metric</span></span> |<span data-ttu-id="c977f-148">是</span><span class="sxs-lookup"><span data-stu-id="c977f-148">Yes</span></span> | <span data-ttu-id="c977f-149">有限</span><span class="sxs-lookup"><span data-stu-id="c977f-149">Limited</span></span> |
| <span data-ttu-id="c977f-150">客户构建信息</span><span class="sxs-lookup"><span data-stu-id="c977f-150">Customer building information</span></span>| <span data-ttu-id="c977f-151">是 </span><span class="sxs-lookup"><span data-stu-id="c977f-151">Yes</span></span> | <span data-ttu-id="c977f-152">是</span><span class="sxs-lookup"><span data-stu-id="c977f-152">Yes</span></span> |
| <span data-ttu-id="c977f-153">深入分析</span><span class="sxs-lookup"><span data-stu-id="c977f-153">Drill-down analytics</span></span> | <span data-ttu-id="c977f-154">是</span><span class="sxs-lookup"><span data-stu-id="c977f-154">Yes</span></span> | <span data-ttu-id="c977f-155">否</span><span class="sxs-lookup"><span data-stu-id="c977f-155">No</span></span> |
| <span data-ttu-id="c977f-156">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="c977f-156">Media reliability metrics</span></span> | <span data-ttu-id="c977f-157">是</span><span class="sxs-lookup"><span data-stu-id="c977f-157">Yes</span></span> | <span data-ttu-id="c977f-158">有限</span><span class="sxs-lookup"><span data-stu-id="c977f-158">Limited</span></span> |
| <span data-ttu-id="c977f-159">即开报告</span><span class="sxs-lookup"><span data-stu-id="c977f-159">Out-of-the-box reports</span></span> | <span data-ttu-id="c977f-160">是 </span><span class="sxs-lookup"><span data-stu-id="c977f-160">Yes</span></span> | <span data-ttu-id="c977f-161">是</span><span class="sxs-lookup"><span data-stu-id="c977f-161">Yes</span></span> |
| <span data-ttu-id="c977f-162">概述报告</span><span class="sxs-lookup"><span data-stu-id="c977f-162">Overview reports</span></span> | <span data-ttu-id="c977f-163">是</span><span class="sxs-lookup"><span data-stu-id="c977f-163">Yes</span></span> | <span data-ttu-id="c977f-164">否</span><span class="sxs-lookup"><span data-stu-id="c977f-164">No</span></span> |
| <span data-ttu-id="c977f-165">每用户报告</span><span class="sxs-lookup"><span data-stu-id="c977f-165">Per user reports</span></span> | <span data-ttu-id="c977f-166">是 </span><span class="sxs-lookup"><span data-stu-id="c977f-166">Yes</span></span> | <span data-ttu-id="c977f-167">是</span><span class="sxs-lookup"><span data-stu-id="c977f-167">Yes</span></span> |
| <span data-ttu-id="c977f-168">设置自定义报表</span><span class="sxs-lookup"><span data-stu-id="c977f-168">Report set customization</span></span> <br> <span data-ttu-id="c977f-169">（添加、 删除、 修改报表）</span><span class="sxs-lookup"><span data-stu-id="c977f-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="c977f-170">是 </span><span class="sxs-lookup"><span data-stu-id="c977f-170">Yes</span></span> | <span data-ttu-id="c977f-171">是</span><span class="sxs-lookup"><span data-stu-id="c977f-171">Yes</span></span> |
| <span data-ttu-id="c977f-172">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="c977f-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="c977f-173">是</span><span class="sxs-lookup"><span data-stu-id="c977f-173">Yes</span></span> | <span data-ttu-id="c977f-174">否</span><span class="sxs-lookup"><span data-stu-id="c977f-174">No</span></span> |
| <span data-ttu-id="c977f-175">用于编程访问的数据 Api</span><span class="sxs-lookup"><span data-stu-id="c977f-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="c977f-176">到 CQD</span><span class="sxs-lookup"><span data-stu-id="c977f-176">to CQD</span></span> | <span data-ttu-id="c977f-177">否</span><span class="sxs-lookup"><span data-stu-id="c977f-177">No</span></span> | <span data-ttu-id="c977f-178">是</span><span class="sxs-lookup"><span data-stu-id="c977f-178">Yes</span></span> |
||||
