---
title: 规划呼叫数据连接器 |呼叫质量仪表板监控混合分析
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
description: 概述如何使用 Skype for Business Online 遥测工具监视混合方案中的本地实现。
ms.openlocfilehash: ad4d7ddb270bc4e4227eea7d33c37411ea96fa8c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779658"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="374e6-103">规划呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="374e6-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="374e6-104">概述</span><span class="sxs-lookup"><span data-stu-id="374e6-104">Overview</span></span>

<span data-ttu-id="374e6-105">本主题介绍了实现 Skype for Business Server 呼叫数据连接器的优点、规划注意事项和要求。</span><span class="sxs-lookup"><span data-stu-id="374e6-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="374e6-106">有关配置呼叫数据连接器的详细信息，请参阅[Configure Call Data connector](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="374e6-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="374e6-107">呼叫数据连接器极大地简化了混合环境中的呼叫监视，因为您不再需要使用不同的内部部署和联机工具来监视所有用户的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="374e6-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="374e6-108">无论您的用户是驻留在本地还是联机，您都可以选择查看整个组织的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="374e6-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="374e6-109">使用 "呼叫数据连接器"，您可以使用单个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="374e6-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="374e6-110">在 Microsoft 团队、Skype for Business Online 和 Skype for Business Server 中监视你的用户体验。</span><span class="sxs-lookup"><span data-stu-id="374e6-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="374e6-111">查看整个网络中的问题并进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="374e6-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="374e6-112">为呼叫分析分配帮助台和管理员角色，以便让帮助台工作人员能够查看和解决他们的责任领域。</span><span class="sxs-lookup"><span data-stu-id="374e6-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="374e6-113">使用呼叫数据连接器，Skype for Business 服务器将呼叫数据推送到云服务，以便您可以利用 Skype for Business Online 呼叫分析（CA）和通话质量仪表板（CQD）工具，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="374e6-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="374e6-115">服务器将体验质量（QoE）和呼叫详细信息记录（CDR）数据推送到在线服务。</span><span class="sxs-lookup"><span data-stu-id="374e6-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="374e6-116">通过呼叫分析和 CQD 工具，您可以监控呼叫的质量，并解决 Microsoft 团队和 Skype for business 服务的连接问题，如下所示：</span><span class="sxs-lookup"><span data-stu-id="374e6-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="374e6-117">呼叫分析重点关注特定呼叫的质量问题。</span><span class="sxs-lookup"><span data-stu-id="374e6-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="374e6-118">它显示有关 Skype for Business 帐户中每个用户的呼叫和会议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="374e6-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="374e6-119">使用呼叫分析，可以向支持人员操作员分配权限，然后可以在不访问 Skype for business 管理中心的其余部分的情况下监视呼叫。</span><span class="sxs-lookup"><span data-stu-id="374e6-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="374e6-120">呼叫质量仪表板侧重于整个组织中的网络性能和问题。</span><span class="sxs-lookup"><span data-stu-id="374e6-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="374e6-121">Skype for Business 管理员和网络工程师使用此工具对网络性能进行故障排除和优化。</span><span class="sxs-lookup"><span data-stu-id="374e6-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="374e6-122">有关详细信息，请参阅[Call Analytics And Call Quality 仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="374e6-122">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="374e6-123">当然，您可能希望在本地保留一些呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="374e6-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="374e6-124">例如，如果您使用的是具有自定义报告和工作流的第三方解决方案，则可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="374e6-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="374e6-125">呼叫数据连接器允许您配置将数据发送到联机服务，同时还在本地服务器上保留数据的副本，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="374e6-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="374e6-127">Requirements</span><span class="sxs-lookup"><span data-stu-id="374e6-127">Requirements</span></span>

<span data-ttu-id="374e6-128">以下要求假定您已在受支持的拓扑中部署了 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="374e6-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="374e6-129">有关部署 Skype for Business Server 和受支持的拓扑的详细信息，请参阅[拓扑基础](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。</span><span class="sxs-lookup"><span data-stu-id="374e6-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="374e6-130">若要配置呼叫数据连接器，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="374e6-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="374e6-131">启用混合连接。</span><span class="sxs-lookup"><span data-stu-id="374e6-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="374e6-132">如果已部署 Skype for Business Server，并且想要启用呼叫数据连接器，则必须确保在本地和联机环境之间设置混合连接。</span><span class="sxs-lookup"><span data-stu-id="374e6-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="374e6-133">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="374e6-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="374e6-134">有关详细信息，请参阅[规划 skype For Business server 和 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 和 office 365 之间的混合连接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="374e6-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="374e6-135">对 Office 365 组织进行身份验证，并确保已启用以下角色：</span><span class="sxs-lookup"><span data-stu-id="374e6-135">Authenticate to your Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="374e6-136">Skype for Business Server 管理员</span><span class="sxs-lookup"><span data-stu-id="374e6-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="374e6-137">全局管理员</span><span class="sxs-lookup"><span data-stu-id="374e6-137">Global Administrator</span></span>

- <span data-ttu-id="374e6-138">如果尚未执行此操作，请按照[打开和使用 Microsoft 团队和 Skype for Business Online 的通话质量仪表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述，打开呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="374e6-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="374e6-139">使用本地 LCSCdr 和 QoEMetrics 数据库启用用于监视的前端池。</span><span class="sxs-lookup"><span data-stu-id="374e6-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="374e6-140">如果不这样做，则调用数据连接器将不会有要使用的指标数据。</span><span class="sxs-lookup"><span data-stu-id="374e6-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="374e6-141">如果前端池上未启用监控，则呼叫数据连接器将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="374e6-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="374e6-142">正确配置了[服务器到服务器身份验证](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)。</span><span class="sxs-lookup"><span data-stu-id="374e6-142">Properly configured [server-to-server authentication](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="374e6-143">内部部署和在线通话质量仪表板（CQD）报告的比较</span><span class="sxs-lookup"><span data-stu-id="374e6-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="374e6-144">功能报告</span><span class="sxs-lookup"><span data-stu-id="374e6-144">Feature reports</span></span> | <span data-ttu-id="374e6-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="374e6-145">Skype for Business Online</span></span> | <span data-ttu-id="374e6-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="374e6-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="374e6-147">应用程序共享指标</span><span class="sxs-lookup"><span data-stu-id="374e6-147">Application sharing metric</span></span> |<span data-ttu-id="374e6-148">是</span><span class="sxs-lookup"><span data-stu-id="374e6-148">Yes</span></span> | <span data-ttu-id="374e6-149">范围</span><span class="sxs-lookup"><span data-stu-id="374e6-149">Limited</span></span> |
| <span data-ttu-id="374e6-150">客户建筑物信息</span><span class="sxs-lookup"><span data-stu-id="374e6-150">Customer building information</span></span>| <span data-ttu-id="374e6-151">是</span><span class="sxs-lookup"><span data-stu-id="374e6-151">Yes</span></span> | <span data-ttu-id="374e6-152">是</span><span class="sxs-lookup"><span data-stu-id="374e6-152">Yes</span></span> |
| <span data-ttu-id="374e6-153">深入分析</span><span class="sxs-lookup"><span data-stu-id="374e6-153">Drill-down analytics</span></span> | <span data-ttu-id="374e6-154">可访问</span><span class="sxs-lookup"><span data-stu-id="374e6-154">Yes</span></span> | <span data-ttu-id="374e6-155">否</span><span class="sxs-lookup"><span data-stu-id="374e6-155">No</span></span> |
| <span data-ttu-id="374e6-156">媒体可靠性指标</span><span class="sxs-lookup"><span data-stu-id="374e6-156">Media reliability metrics</span></span> | <span data-ttu-id="374e6-157">是</span><span class="sxs-lookup"><span data-stu-id="374e6-157">Yes</span></span> | <span data-ttu-id="374e6-158">范围</span><span class="sxs-lookup"><span data-stu-id="374e6-158">Limited</span></span> |
| <span data-ttu-id="374e6-159">开箱即用报告</span><span class="sxs-lookup"><span data-stu-id="374e6-159">Out-of-the-box reports</span></span> | <span data-ttu-id="374e6-160">是</span><span class="sxs-lookup"><span data-stu-id="374e6-160">Yes</span></span> | <span data-ttu-id="374e6-161">是</span><span class="sxs-lookup"><span data-stu-id="374e6-161">Yes</span></span> |
| <span data-ttu-id="374e6-162">概述报告</span><span class="sxs-lookup"><span data-stu-id="374e6-162">Overview reports</span></span> | <span data-ttu-id="374e6-163">可访问</span><span class="sxs-lookup"><span data-stu-id="374e6-163">Yes</span></span> | <span data-ttu-id="374e6-164">否</span><span class="sxs-lookup"><span data-stu-id="374e6-164">No</span></span> |
| <span data-ttu-id="374e6-165">每用户报告</span><span class="sxs-lookup"><span data-stu-id="374e6-165">Per user reports</span></span> | <span data-ttu-id="374e6-166">是</span><span class="sxs-lookup"><span data-stu-id="374e6-166">Yes</span></span> | <span data-ttu-id="374e6-167">是</span><span class="sxs-lookup"><span data-stu-id="374e6-167">Yes</span></span> |
| <span data-ttu-id="374e6-168">报表集自定义</span><span class="sxs-lookup"><span data-stu-id="374e6-168">Report set customization</span></span> <br> <span data-ttu-id="374e6-169">（添加、删除、修改报表）</span><span class="sxs-lookup"><span data-stu-id="374e6-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="374e6-170">是</span><span class="sxs-lookup"><span data-stu-id="374e6-170">Yes</span></span> | <span data-ttu-id="374e6-171">是</span><span class="sxs-lookup"><span data-stu-id="374e6-171">Yes</span></span> |
| <span data-ttu-id="374e6-172">基于视频的屏幕共享指标</span><span class="sxs-lookup"><span data-stu-id="374e6-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="374e6-173">可访问</span><span class="sxs-lookup"><span data-stu-id="374e6-173">Yes</span></span> | <span data-ttu-id="374e6-174">否</span><span class="sxs-lookup"><span data-stu-id="374e6-174">No</span></span> |
| <span data-ttu-id="374e6-175">用于编程访问的数据 Api</span><span class="sxs-lookup"><span data-stu-id="374e6-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="374e6-176">到 CQD</span><span class="sxs-lookup"><span data-stu-id="374e6-176">to CQD</span></span> | <span data-ttu-id="374e6-177">否</span><span class="sxs-lookup"><span data-stu-id="374e6-177">No</span></span> | <span data-ttu-id="374e6-178">是</span><span class="sxs-lookup"><span data-stu-id="374e6-178">Yes</span></span> |
||||
