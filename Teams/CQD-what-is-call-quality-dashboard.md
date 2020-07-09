---
title: 什么是通话质量仪表板（CQD）？
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
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
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解通话质量仪表板（CQD）以及如何使用它查看 Microsoft 团队中会议和通话质量的报告。
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088240"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="93135-103">什么是通话质量仪表板（CQD）？</span><span class="sxs-lookup"><span data-stu-id="93135-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="93135-104">Microsoft 通话质量仪表板（CQD）- [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 在**组织范围级别**、Microsoft 团队、Skype for Business Online 和 Skype for business Server 2019 中显示呼叫和会议质量。</span><span class="sxs-lookup"><span data-stu-id="93135-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="93135-105">最新版本的 CQD 具有[近乎实时（NRT）数据馈送](CQD-data-and-reports.md)，这意味着呼叫记录在通话结束后的30分钟内将在 CQD 中可用。</span><span class="sxs-lookup"><span data-stu-id="93135-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="93135-106">无论 CQD 包含[最终用户的可识别信息（EUII）数据](CQD-data-and-reports.md#euii-data)，其管理方式与在[Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)中的 EUII 一样。</span><span class="sxs-lookup"><span data-stu-id="93135-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="93135-107">CQD 旨在帮助团队管理员、Skype for Business 管理员和网络工程师在组织范围内监视呼叫和会议质量。</span><span class="sxs-lookup"><span data-stu-id="93135-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="93135-108">您将使用 CQD 帮助您优化您的**网络**以提高性能质量。</span><span class="sxs-lookup"><span data-stu-id="93135-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="93135-109">当你需要查看**特定用户**的调用和会议信息时，请将 CQD 数据与每用户[调用分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)结合使用。</span><span class="sxs-lookup"><span data-stu-id="93135-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="93135-110">例如，使用 CQD，你可以确定用户的通话质量不佳（使用每用户呼叫分析时看到的）是由于网络问题也会影响其他许多用户。</span><span class="sxs-lookup"><span data-stu-id="93135-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="93135-111">CQD 捕获个人通话体验和使用团队或 Skype for business 进行的总体通话质量。</span><span class="sxs-lookup"><span data-stu-id="93135-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="93135-112">通过 CQD，整体模式可能会变得显而易见，因此网络工程师可以及时了解通话质量。</span><span class="sxs-lookup"><span data-stu-id="93135-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="93135-113">CQD 提供了通话质量指标的报告，使你可以深入了解总通话质量、服务器客户端流、客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="93135-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通话质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="93135-115">在 CQD 中，我们鼓励你上载生成和终结点信息，使你可以使用位置增强的报表来分析用户建筑物内的通话质量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="93135-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="93135-116">可以对数据进行评估，以确定问题是独立于单个用户还是影响较大的用户段。</span><span class="sxs-lookup"><span data-stu-id="93135-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="93135-117">若要在 CQD 中启用生成或特定于终结点的视图，管理员必须在 CQD**租户数据上载**页面上[上载生成或终结点信息](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="93135-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![通话质量仪表板的位置增强的报表的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="93135-119">不要错过我们的 "[管理通话和会议质量](quality-of-experience-review-guide.md)" 文章，这些文章为负责管理团队中的服务质量的团队管理员或支持工程师提供了深入指导。</span><span class="sxs-lookup"><span data-stu-id="93135-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="93135-120">较早版本的 CQD （CQD.lync.com）</span><span class="sxs-lookup"><span data-stu-id="93135-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="93135-121">当前版本的 CQD （ https://CQD.Teams.microsoft.com) 替换较旧版本的 CQD （ https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="93135-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="93135-122">您仍然可以使用 CQD.lync.com （Skype for Business 管理中心提供），但从2020年7月1日起使用来自 CQD 的数据。Teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="93135-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="93135-123">我们将立即关闭对 CQD.lync.com 的访问，因此应转到 CQD。Teams.microsoft.com 如果还未执行此操作。</span><span class="sxs-lookup"><span data-stu-id="93135-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93135-124">从2020年7月1日起，你无法再从旧的 CQD （CQD.lync.com）查看或修改你的构建或查询数据。</span><span class="sxs-lookup"><span data-stu-id="93135-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="93135-125">如果尚未从 CQD.lync.com 迁移这些数据，但仍需要它，请记录支持票证。</span><span class="sxs-lookup"><span data-stu-id="93135-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="93135-126">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="93135-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="93135-127">2020年1月[的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="93135-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="93135-128">可用于分析和报告 CQD 数据的自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="93135-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="93135-129">已阅读 "[使用 POWER BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)" 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="93135-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="93135-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="93135-130">Related topics</span></span>

[<span data-ttu-id="93135-131">改善和监控团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="93135-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="93135-132">设置通话质量仪表板（CQD）</span><span class="sxs-lookup"><span data-stu-id="93135-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="93135-133">上载租户和生成数据</span><span class="sxs-lookup"><span data-stu-id="93135-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="93135-134">CQD 数据和报告</span><span class="sxs-lookup"><span data-stu-id="93135-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="93135-135">使用 CQD 管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="93135-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="93135-136">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="93135-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="93135-137">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="93135-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="93135-138">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="93135-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="93135-139">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="93135-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)