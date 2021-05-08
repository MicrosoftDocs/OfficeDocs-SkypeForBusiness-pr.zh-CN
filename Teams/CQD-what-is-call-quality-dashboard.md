---
title: 什么是调用质量仪表板 (CQD) ？
ms.author: serdars
author: SerdarSoysal
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
description: 了解呼叫质量仪表板 (CQD) 以及如何使用它来查看有关会议报告，以及如何在 Microsoft Teams。
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593830"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="638a4-103">什么是调用质量仪表板 (CQD) ？</span><span class="sxs-lookup"><span data-stu-id="638a4-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="638a4-104">Microsoft 呼叫质量仪表板 (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - 显示 2019 年Microsoft Teams、Skype for Business Online 和 Skype for Business Server 级别的呼叫和会议质量。</span><span class="sxs-lookup"><span data-stu-id="638a4-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="638a4-105">最新版本的 CQD 具有近实时 [ (NRT) ](CQD-data-and-reports.md)数据源，这意味着呼叫记录在通话结束后 30 分钟内在 CQD 中可用。</span><span class="sxs-lookup"><span data-stu-id="638a4-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="638a4-106">只要 CQD 包含来自[EUII](CQD-data-and-reports.md#euii-data) (标识) 信息，它在整个过程中以与[EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)相同的方式进行管理Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="638a4-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="638a4-107">CQD 旨在帮助管理员Teams管理员、Skype for Business管理员和网络工程师在组织范围内监视呼叫和会议质量。</span><span class="sxs-lookup"><span data-stu-id="638a4-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="638a4-108">你将使用 CQD 来帮助优化 **网络，** 以提升性能质量。</span><span class="sxs-lookup"><span data-stu-id="638a4-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="638a4-109">当需要查看特定用户的呼叫和会议信息 **时**，将 CQD 数据与按用户的呼叫 [分析结合使用](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="638a4-110">例如，使用 CQD，可以确定用户使用每用户调用分析 () 观察到的用户通话质量差) 是由于网络问题也影响许多其他用户。</span><span class="sxs-lookup"><span data-stu-id="638a4-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="638a4-111">CQD 捕获单个呼叫体验和使用 Teams 或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="638a4-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="638a4-112">使用 CQD 时，总体模式可能会变得明显，因此网络工程师可以就呼叫质量进行明智的评估。</span><span class="sxs-lookup"><span data-stu-id="638a4-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="638a4-113">CQD 提供呼叫质量指标报告，让你深入了解总体呼叫质量、服务器-客户端流、客户端流和语音质量[SLA。](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="638a4-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通话质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="638a4-115">在 CQD 中，建议上传建筑物和终结点信息，这样Location-Enhanced报表来分析用户建筑物内的呼叫质量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="638a4-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="638a4-116">可以评估数据，以确定问题是隔离给单个用户，还是影响较大用户段。</span><span class="sxs-lookup"><span data-stu-id="638a4-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="638a4-117">若要在 CQD 中启用建筑物或终结点特定的视图，管理员必须在[](CQD-upload-tenant-building-data.md)"CQD 租户数据"页上上传Upload信息。</span><span class="sxs-lookup"><span data-stu-id="638a4-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![呼叫质量仪表板的"呼叫质量"Location-Enhanced屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="638a4-119">不要错过我们的["管理](quality-of-experience-review-guide.md)呼叫和会议质量"一文，其中为负责管理会议服务质量的Teams管理员或支持工程师提供了深入Teams。</span><span class="sxs-lookup"><span data-stu-id="638a4-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="legacy-version-of-cqd-cqdlynccom"></a><span data-ttu-id="638a4-120">旧版 CQD (CQD.lync.com) </span><span class="sxs-lookup"><span data-stu-id="638a4-120">Legacy version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="638a4-121">当前版本的 CQD (https://CQD.Teams.microsoft.com) 已替换旧版 CQD https://CQD.lync.com) (。</span><span class="sxs-lookup"><span data-stu-id="638a4-121">The current version of CQD (https://CQD.Teams.microsoft.com) has replaced the legacy version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="638a4-122">你仍可以使用 CQD.lync.com (管理中心 Skype for Business 提供) ，但截至 2020 年 7 月 1 日，它使用的是 CQD 的数据。Teams.microsoft.com，你无法再查看或修改旧 CQD 模板中的建筑物或查询 (CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="638a4-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com and you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="638a4-123">如果尚未从数据库迁移此数据 CQD.lync.com，请记录支持票证。</span><span class="sxs-lookup"><span data-stu-id="638a4-123">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="638a4-124">自 2021 年 7 月 31 日起，我们将停用旧版 CQD (CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="638a4-124">As of July 31, 2021, we are retiring the legacy version of CQD (CQD.lync.com).</span></span> <span data-ttu-id="638a4-125">该日期之后，会自动重定向到 CQD。Teams.microsoft.com 访问任何 CQD.lync.com，任何未分配建筑物或查询数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="638a4-125">After that date, you will be automatically redirected to CQD.Teams.microsoft.com when attempting to access CQD.lync.com, and any unmigrated building or query data will be lost.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="638a4-126">使用Power BI分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="638a4-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="638a4-127">2020 年 1 月新增功能[：Power BI CQD 的查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="638a4-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="638a4-128">可Power BI模板，可用于分析和报告 CQD 数据。</span><span class="sxs-lookup"><span data-stu-id="638a4-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="638a4-129">请参阅[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="638a4-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="638a4-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="638a4-130">Related topics</span></span>

[<span data-ttu-id="638a4-131">改进和监视呼叫质量Teams</span><span class="sxs-lookup"><span data-stu-id="638a4-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="638a4-132">使用 CQD (设置呼叫质量) </span><span class="sxs-lookup"><span data-stu-id="638a4-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="638a4-133">Upload租户和建筑物数据</span><span class="sxs-lookup"><span data-stu-id="638a4-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="638a4-134">CQD 数据和报表</span><span class="sxs-lookup"><span data-stu-id="638a4-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="638a4-135">使用 CQD 管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="638a4-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="638a4-136">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="638a4-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="638a4-137">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="638a4-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="638a4-138">使用Power BI分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="638a4-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="638a4-139">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="638a4-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
