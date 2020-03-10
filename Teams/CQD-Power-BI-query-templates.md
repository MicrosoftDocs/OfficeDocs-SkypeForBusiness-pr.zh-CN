---
title: 使用 Power BI 分析 Microsoft 团队的 CQD 数据
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 Power BI 分析 Microsoft 团队的 CQD 数据。
ms.openlocfilehash: 155bde0373880befc770d745ca246b76d4c63eec
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572890"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a><span data-ttu-id="7e2e1-103">使用 Power BI 分析 Microsoft 团队的 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="7e2e1-103">Use Power BI to analyze CQD data for Microsoft Teams</span></span>

<span data-ttu-id="7e2e1-104">2020年1月[的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-104">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="7e2e1-105">可用于分析和报告 CQD 数据的自定义 Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-105">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="7e2e1-106">对于团队中的 CQD 报表，如果你希望使用 Power BI 查询和报告数据，请下载我们的 CQD Power BI 模板。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-106">For CQD reports in Teams, if you’d rather use Power BI to query and report your data, download our CQD Power BI templates.</span></span> <span data-ttu-id="7e2e1-107">打开 Power BI 中的模板时，系统将提示你通过 CQD 管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-107">When you open the templates in Power BI, you’ll be prompted to sign in with your CQD admin credentials.</span></span> <span data-ttu-id="7e2e1-108">你可以自定义这些查询模板，并将其分发给你组织中具有 Power BI 许可证和 CQD 管理员权限的任何人。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-108">You can customize these query templates and distribute them to anyone in your organization who has a Power BI license and CQD admin permissions.</span></span>

<span data-ttu-id="7e2e1-109">在你可以使用这些 .PBIX 文件之前，你需要使用[下载](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的*MicrosoftCallQuality Pqx*文件[安装 Microsoft CQD 的 Power BI Connector](CQD-Power-BI-connector.md) 。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-109">Before you can use these PBIX files, you’ll need to [Install the Power BI Connector for Microsoft CQD](CQD-Power-BI-connector.md) using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


|  |  |
|---------|---------|
|<span data-ttu-id="7e2e1-110">CQD 帮助台报表 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-110">CQD Helpdesk Report.pbix</span></span>     |<span data-ttu-id="7e2e1-111">集成生成和 EUII 数据时，此报表旨在让你从单个用户向上钻取，以查找该用户的不良通话质量的上游根本原因（例如，用户在遇到网络问题的建筑物中）。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-111">Integrating building and EUII data, this report is designed to let you drill up from a single user to find the upstream root cause of poor call quality for that user (for example, the user is in a building that’s experiencing network problems).</span></span>         |
|<span data-ttu-id="7e2e1-112">CQD 位置增强的报表 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-112">CQD Location Enhanced Report.pbix</span></span>     | <span data-ttu-id="7e2e1-113">Imagining CQD SPD 位置报告。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-113">Re-imagining CQD SPD location reports.</span></span> <span data-ttu-id="7e2e1-114">包括9个报表，提供呼叫质量、建筑物 WiFi、可靠性，以及通过通过构建或用户进行额外的钻取来评价我的呼叫（RMC）信息。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-114">Includes 9 reports, providing Call Quality, Building WiFi, Reliability, and Rate My Call (RMC) information with additional drill-thrus by Building or by User.</span></span>        |
|<span data-ttu-id="7e2e1-115">CQD 移动设备报表 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-115">CQD Mobile Device Report.pbix</span></span>     | <span data-ttu-id="7e2e1-116">提供专门针对移动设备用户进行调整的见解，包括通话质量、可靠性和费率我的通话。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-116">Provides insights specifically tuned towards mobile device users, including Call Quality, Reliability, and Rate My Call.</span></span> <span data-ttu-id="7e2e1-117">查看移动网络、WiFi 网络和移动操作系统报告（Android、iOS）。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-117">View mobile network, WiFi network, and mobile operating system reports (Android, iOS).</span></span>        |
|<span data-ttu-id="7e2e1-118">CQD PSTN 直接路由报告 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-118">CQD PSTN Direct Routing Report.pbix</span></span>     |<span data-ttu-id="7e2e1-119">为通过直接路由进行的 PSTN 呼叫提供特定的见解。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-119">Provides insights specific for PSTN calls that go through Direct Routing.</span></span> <span data-ttu-id="7e2e1-120">若要了解详细信息，请[使用 CQD PSTN 直接路由报告](CQD-PSTN-report.md)进行阅读。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-120">To learn more, read [Using the CQD PSTN Direct Routing Report](CQD-PSTN-report.md).</span></span>         |
|<span data-ttu-id="7e2e1-121">CQD 摘要报表 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-121">CQD Summary Report.pbix</span></span>     |<span data-ttu-id="7e2e1-122">更好的可视化效果、改进的演示文稿、增加的信息密度和滚动日期。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-122">Better visualizations, improved presentation, increased information density, and rolling dates.</span></span> <span data-ttu-id="7e2e1-123">这些报表使标识符离群离群更容易。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-123">These reports make it easier to identifier outliers.</span></span> <span data-ttu-id="7e2e1-124">通过易于使用的交互式地图按位置深化通话质量。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-124">Drill into call quality by location with an easy-to-use interactive map.</span></span> <span data-ttu-id="7e2e1-125">9个新报表：</span><span class="sxs-lookup"><span data-stu-id="7e2e1-125">9 new reports:</span></span></p><span data-ttu-id="7e2e1-126">-整体质量</span><span class="sxs-lookup"><span data-stu-id="7e2e1-126">- Quality Overall</span></span><br><span data-ttu-id="7e2e1-127">-整体可靠性</span><span class="sxs-lookup"><span data-stu-id="7e2e1-127">- Reliability Overall</span></span><br><span data-ttu-id="7e2e1-128">-RMC （费率我的通话）-整体</span><span class="sxs-lookup"><span data-stu-id="7e2e1-128">- RMC (Rate My Call) Overall</span></span><br><span data-ttu-id="7e2e1-129">-会议质量</span><span class="sxs-lookup"><span data-stu-id="7e2e1-129">- Conference Quality</span></span><br><span data-ttu-id="7e2e1-130">-P2P 质量</span><span class="sxs-lookup"><span data-stu-id="7e2e1-130">- P2P Quality</span></span><br><span data-ttu-id="7e2e1-131">-会议可靠性</span><span class="sxs-lookup"><span data-stu-id="7e2e1-131">- Conference Reliability</span></span><br><span data-ttu-id="7e2e1-132">-P2P 可靠性</span><span class="sxs-lookup"><span data-stu-id="7e2e1-132">- P2P Reliability</span></span><br><span data-ttu-id="7e2e1-133">-会议 RMC</span><span class="sxs-lookup"><span data-stu-id="7e2e1-133">- Conference RMC</span></span><br><span data-ttu-id="7e2e1-134">-P2P RMC</span><span class="sxs-lookup"><span data-stu-id="7e2e1-134">- P2P RMC</span></span>         |
|<span data-ttu-id="7e2e1-135"><strong>（新增！）</strong>CQD 团队使用情况报表 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-135"><strong>(New!)</strong>CQD Teams Utilization Report.pbix</span></span>     | <span data-ttu-id="7e2e1-136">显示组织中的用户使用团队的方式和数量。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-136">Shows how users in your organization are using Teams and how much.</span></span> <span data-ttu-id="7e2e1-137">若要了解详细信息，请参阅[使用 CQD POWER BI 报表查看 Microsoft 团队的利用率](CQD-teams-utilization-report.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-137">To learn more, read [Use CQD Power BI report to view Microsoft Teams utilization](CQD-teams-utilization-report.md).</span></span>        |
|<span data-ttu-id="7e2e1-138">CQD 用户反馈（费率我的通话）报告 .pbix</span><span class="sxs-lookup"><span data-stu-id="7e2e1-138">CQD User Feedback (Rate My Call) Report.pbix</span></span>     | <span data-ttu-id="7e2e1-139">显示使用一种可轻松地帮助支持组织通话的方式对我的通话数据进行评级。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-139">Shows Rate My Call data in a way that you can easily use to help support calling for your organization.</span></span> <span data-ttu-id="7e2e1-140">与 verbatims 的交叉参考以识别最终用户教育机会。</span><span class="sxs-lookup"><span data-stu-id="7e2e1-140">Cross reference with verbatims to identify end user education opportunities.</span></span>        |


## <a name="related-topics"></a><span data-ttu-id="7e2e1-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e2e1-141">Related topics</span></span>

[<span data-ttu-id="7e2e1-142">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="7e2e1-142">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="7e2e1-143">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="7e2e1-143">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="7e2e1-144">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="7e2e1-144">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="7e2e1-145">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="7e2e1-145">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="7e2e1-146">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="7e2e1-146">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 