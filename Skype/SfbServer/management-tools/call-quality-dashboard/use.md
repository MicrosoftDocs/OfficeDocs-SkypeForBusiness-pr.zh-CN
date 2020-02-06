---
title: 使用 Skype for business 服务器的呼叫质量仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要：了解如何使用通话质量仪表板。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 61b20062925f59474d387a022a92663e0ffcd6ba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816661"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="639d8-104">使用 Skype for business 服务器的呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="639d8-104">Use Call Quality Dashboard for Skype for Business Server</span></span>

<span data-ttu-id="639d8-105">**摘要：** 了解如何使用通话质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="639d8-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="639d8-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="639d8-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="639d8-107">通话质量仪表板（CQD）允许 IT 专业人员使用聚合数据通过比较用户组的统计信息来识别产生媒体质量问题的问题，从而确定趋势和模式。</span><span class="sxs-lookup"><span data-stu-id="639d8-107">Call Quality Dashboard (CQD) allows IT Pros to use aggregate data to identify problems creating media quality issues by  comparing statistics for groups of users to identify trends and patterns.</span></span> <span data-ttu-id="639d8-108">CQD 不专注于解决单个呼叫问题，而是确定适用于多个用户的问题和解决方案。</span><span class="sxs-lookup"><span data-stu-id="639d8-108">CQD is not focused on solving individual call issues, but on identifying problems and solutions that apply to many users.</span></span>

## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="639d8-109">呼叫质量仪表板用户指南</span><span class="sxs-lookup"><span data-stu-id="639d8-109">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="639d8-110">CQD 是一种 web 门户，用于快速创建和组织基于体验质量（QoE）数据的报表。</span><span class="sxs-lookup"><span data-stu-id="639d8-110">CQD is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data.</span></span> <span data-ttu-id="639d8-111">CQD 部署一个 SSAS 多维数据集以聚合 QoE 指标数据库中的数据，并允许管理员实时创建和修改报表或进行调查。</span><span class="sxs-lookup"><span data-stu-id="639d8-111">CQD deploys an SSAS cube to aggregate the data in the QoE Metrics database, and enables admins to create and modify reports or do investigations in real time.</span></span> <span data-ttu-id="639d8-112">虽然可以使用 Excel 直接连接到多维数据集，但门户已针对涉及 QoE 数据的几个工作流进行了优化。</span><span class="sxs-lookup"><span data-stu-id="639d8-112">While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data.</span></span> <span data-ttu-id="639d8-113">数据包括：</span><span class="sxs-lookup"><span data-stu-id="639d8-113">The data includes:</span></span>

- <span data-ttu-id="639d8-114">用于快速访问的缓存报表数据</span><span class="sxs-lookup"><span data-stu-id="639d8-114">Cached report data for fast access</span></span>
- <span data-ttu-id="639d8-115">指向信息共享和发布的报表页面的深层链接</span><span class="sxs-lookup"><span data-stu-id="639d8-115">Deep links to report pages for information sharing and publishing</span></span>
- <span data-ttu-id="639d8-116">简化的报表编辑和创建以及报表说明的可编辑元数据。</span><span class="sxs-lookup"><span data-stu-id="639d8-116">Streamlined report editing and creation, and editable metadata for report descriptions.</span></span>

<span data-ttu-id="639d8-117">此外，CQD 还会公开 web Api，该 Api 允许用户以编程方式访问多维数据集数据以在自定义仪表板中使用。</span><span class="sxs-lookup"><span data-stu-id="639d8-117">Also, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>

### <a name="feature-overview"></a><span data-ttu-id="639d8-118">功能概述</span><span class="sxs-lookup"><span data-stu-id="639d8-118">Feature Overview</span></span>

<span data-ttu-id="639d8-119">当您访问 "呼叫质量" 仪表板时，将看到以下屏幕：</span><span class="sxs-lookup"><span data-stu-id="639d8-119">When you visit the Call Quality Dashboard, you see the following screen:</span></span>

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. <span data-ttu-id="639d8-121">"摘要窗格" 是指可以找到 "报表集" （向右）的上下文。</span><span class="sxs-lookup"><span data-stu-id="639d8-121">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span>
2. <span data-ttu-id="639d8-122">单击摘要 PaneReport 中的 "编辑" 以设置级别属性（包括 Y 轴高度）。</span><span class="sxs-lookup"><span data-stu-id="639d8-122">Click "Edit" in the Summary PaneReport to set level properties (including Y-axis height).</span></span>
3. <span data-ttu-id="639d8-123">痕迹导航可帮助你在报表集层次结构中标识你的当前位置。</span><span class="sxs-lookup"><span data-stu-id="639d8-123">The Breadcrumb helps you identify your current location within the report set hierarchy.</span></span>
4. <span data-ttu-id="639d8-124">带有子报表的报表显示为蓝色链接。</span><span class="sxs-lookup"><span data-stu-id="639d8-124">Reports with subreports are shown with a blue link.</span></span> <span data-ttu-id="639d8-125">单击链接以向下钻取到子报表。</span><span class="sxs-lookup"><span data-stu-id="639d8-125">Click the link to drill down to the child reports.</span></span>

<span data-ttu-id="639d8-126">将鼠标移动到条形图和趋势线上以显示详细值。</span><span class="sxs-lookup"><span data-stu-id="639d8-126">Move the mouse over the bar charts and trend lines to show detailed values.</span></span> <span data-ttu-id="639d8-127">具有焦点的报表显示 "操作" 菜单： "编辑"、"克隆"、"删除" 和 "下载"。</span><span class="sxs-lookup"><span data-stu-id="639d8-127">The report that has focus shows the action menu: "Edit", "Clone", "Delete", and "Download".</span></span>

### <a name="default-reports"></a><span data-ttu-id="639d8-128">默认报告</span><span class="sxs-lookup"><span data-stu-id="639d8-128">Default Reports</span></span>

<span data-ttu-id="639d8-129">首次访问 "呼叫质量" 仪表板门户时，将自动创建一个默认报表集。</span><span class="sxs-lookup"><span data-stu-id="639d8-129">When you first access the Call Quality Dashboard portal, a default set of reports is automatically created.</span></span> <span data-ttu-id="639d8-130">这些报告有时称为系统报告。</span><span class="sxs-lookup"><span data-stu-id="639d8-130">These reports are sometimes referred to as system reports.</span></span> <span data-ttu-id="639d8-131">你可以通过创建新的同辈报表和子报表来自由修改或删除这些报表或对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="639d8-131">You are able to freely modify or delete these reports or extend them by creating new sibling and child reports.</span></span>

<span data-ttu-id="639d8-132">在顶级，"音频流每月趋势" 报表显示所有音频流的每月趋势。</span><span class="sxs-lookup"><span data-stu-id="639d8-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="639d8-133">将鼠标移动到条形图中的条形上，以显示条形图所表示的数据的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="639d8-133">Move the mouse over the bars in a bar chart to show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="639d8-134">单击音频流的 "每月趋势" 报表的标题以导航到 "托管和非托管音频流" 报表，其中的报表在托管和非托管调用之间拆分。</span><span class="sxs-lookup"><span data-stu-id="639d8-134">Click the title of the Audio Streams Monthly Trend report to navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="639d8-135">管理呼叫是从公司防火墙内通过有线连接进行的呼叫。</span><span class="sxs-lookup"><span data-stu-id="639d8-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="639d8-136">非托管通话包括从公司防火墙外部发出的呼叫以及通过 Wi-fi 发出的所有通话。</span><span class="sxs-lookup"><span data-stu-id="639d8-136">Unmanaged calls include calls made from outside the corporate firewall and all calls made over Wi-Fi.</span></span>

<span data-ttu-id="639d8-137">另一个顶级报表称为 "用户报告的通话质量评估直方图"。</span><span class="sxs-lookup"><span data-stu-id="639d8-137">The other top-level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="639d8-138">通话质量评级是 Skype for Business 用户在通话结束时给出的数字，用于指示呼叫的质量。</span><span class="sxs-lookup"><span data-stu-id="639d8-138">Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="639d8-139">分级号码的范围从1到5，1是最差，5是最佳。</span><span class="sxs-lookup"><span data-stu-id="639d8-139">The rating numbers range from 1 to 5, 1 is the worst and 5 is the best.</span></span> <span data-ttu-id="639d8-140">直方图显示一个月中具有指示评级的音频通话数。</span><span class="sxs-lookup"><span data-stu-id="639d8-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span>

<span data-ttu-id="639d8-141">单击任何报表的标题以导航到报表，其中包含数据的更多筛选器。</span><span class="sxs-lookup"><span data-stu-id="639d8-141">Click the title of any of the reports to navigate into reports with more filters on the data.</span></span> <span data-ttu-id="639d8-142">在系统报告中，每个子报告显示其父报告中的一部分数据。</span><span class="sxs-lookup"><span data-stu-id="639d8-142">In the system reports, each child report displays a subset of the data available in its parent report.</span></span> <span data-ttu-id="639d8-143">解决问题的模型很简单：调查哪些子报表的数据或趋势表明问题已被限制，并逐渐缩小问题空间。</span><span class="sxs-lookup"><span data-stu-id="639d8-143">The problem-solving model is simple: investigate which subreport the data or trend suggesting a problem is confined to, and gradually narrow down the problem space.</span></span> <span data-ttu-id="639d8-144">创建子报表的功能允许你调查有关特定数据趋势的原因的推测。</span><span class="sxs-lookup"><span data-stu-id="639d8-144">The ability to create subreports allows you to investigate your own guesses about the cause of specific data trends.</span></span>

### <a name="create-and-edit-reports"></a><span data-ttu-id="639d8-145">创建和编辑报表</span><span class="sxs-lookup"><span data-stu-id="639d8-145">Create and Edit Reports</span></span>

<span data-ttu-id="639d8-146">单击报表的 "操作" 菜单中的 "编辑" 以查看报表编辑器。</span><span class="sxs-lookup"><span data-stu-id="639d8-146">Click "Edit" in the action menu of a report to see the Report Editor.</span></span> <span data-ttu-id="639d8-147">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="639d8-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="639d8-148">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="639d8-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="639d8-149">报表编辑器可帮助你编辑报表的这些查询和显示选项。</span><span class="sxs-lookup"><span data-stu-id="639d8-149">The Report Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="639d8-150">当您打开 "报表编辑器" 时，将看到：</span><span class="sxs-lookup"><span data-stu-id="639d8-150">When you open the Report Editor, you  see:</span></span>

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="639d8-152">左侧窗格中选择了维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="639d8-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="639d8-153">将鼠标悬停在某个现有值上以显示 "x" 按钮，该按钮允许删除值。</span><span class="sxs-lookup"><span data-stu-id="639d8-153">Hover over one of the existing values to show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="639d8-154">单击标题旁边的 "加号" 按钮以打开对话框，您可以在其中添加新的维度、度量值或筛选器。</span><span class="sxs-lookup"><span data-stu-id="639d8-154">Click the "plus" button next to a heading to open the dialog where you can add a new dimension, measure, or filter.</span></span>
2. <span data-ttu-id="639d8-155">顶部显示了图表自定义选项。</span><span class="sxs-lookup"><span data-stu-id="639d8-155">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="639d8-156">报告编辑器中提供了报告预览。</span><span class="sxs-lookup"><span data-stu-id="639d8-156">A preview of the report is available in the Report Editor.</span></span>
4. <span data-ttu-id="639d8-157">可以使用底部的 "编辑" 框创建详细的报表说明。</span><span class="sxs-lookup"><span data-stu-id="639d8-157">A detailed report description can be created with the edit box at the bottom.</span></span>

### <a name="sparklines-in-tables"></a><span data-ttu-id="639d8-158">表中的迷你图</span><span class="sxs-lookup"><span data-stu-id="639d8-158">Sparklines in Tables</span></span>

<span data-ttu-id="639d8-159">将 StartDate.Month 添加为一个维度，且数据以表格形式呈现为趋势时，可以在表格单元格内显示条形图和迷你图。</span><span class="sxs-lookup"><span data-stu-id="639d8-159">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells.</span></span> <span data-ttu-id="639d8-160">将鼠标指针移动到条形图和迷你图上，以显示各个月份的值。</span><span class="sxs-lookup"><span data-stu-id="639d8-160">Move the mouse pointer over the bar chart and the sparklines to show the values for individual months.</span></span>

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

<span data-ttu-id="639d8-162">为了显示条形图和迷你图，必须选中报表编辑器顶部的 "显示迷你图" 复选框。</span><span class="sxs-lookup"><span data-stu-id="639d8-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="639d8-163">这将选择趋势选项，并将 Month 下移到最后一个维度，也可以通过单击月份并使用向上和向下箭头，将 "开始日期" 或 "向下键"。</span><span class="sxs-lookup"><span data-stu-id="639d8-163">This selects the Trend option and moves Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span>

### <a name="settings"></a><span data-ttu-id="639d8-164">设置</span><span class="sxs-lookup"><span data-stu-id="639d8-164">Settings</span></span>

<span data-ttu-id="639d8-165">"设置" 菜单包含指向有用页面（如 "系统运行状况" 和 "关于页面"）的链接，位于仪表板的右上角。</span><span class="sxs-lookup"><span data-stu-id="639d8-165">The settings menu contains links to useful pages like the System Health and About pages, and is located in the top-right corner of the dashboard.</span></span>

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

<span data-ttu-id="639d8-167">是否显示说明和时间戳由单个用户决定，并且这些设置仅影响个人的仪表板版本，不要修改报表集或其他用户所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="639d8-167">Whether to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, and do not modify the report set or what other users see.</span></span> <span data-ttu-id="639d8-168">清除缓存会导致所有查询从多维数据集中重新加载其数据，而还原默认值将删除所有用户创建或修改的报表，并重新创建系统报表集—用户首次登录时将看到的内容。</span><span class="sxs-lookup"><span data-stu-id="639d8-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when they log in for the first time.</span></span>

<span data-ttu-id="639d8-169">用户仪表板链接显示用户可以在其中查看 CQD 的其他用户并浏览其报告的页面。</span><span class="sxs-lookup"><span data-stu-id="639d8-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="639d8-170">若要共享报表集，请复制 URL 栏中的链接，并将其与另一个 CQD 用户共享。</span><span class="sxs-lookup"><span data-stu-id="639d8-170">To share a report set, copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="639d8-171">此链接与其他用户将在用户仪表板链接页面中的用户用户名下看到的链接相同。</span><span class="sxs-lookup"><span data-stu-id="639d8-171">This link is the same link other users would see in the Users Dashboard Link page under the user's username.</span></span>

### <a name="supplying-subnet-information"></a><span data-ttu-id="639d8-172">提供子网信息</span><span class="sxs-lookup"><span data-stu-id="639d8-172">Supplying Subnet Information</span></span>

<span data-ttu-id="639d8-173">如果将特定于站点的信息输入到存档数据库以提供子网间映射信息（例如，有线/无线呼叫质量，通过构建），则可能会泄漏其他信息。</span><span class="sxs-lookup"><span data-stu-id="639d8-173">Additional information can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (for example, wired/wireless call quality by building).</span></span>

<span data-ttu-id="639d8-174">至少，完成下表以创建这些报表：</span><span class="sxs-lookup"><span data-stu-id="639d8-174">At a minimum, complete the following tables to create these reports:</span></span>

- <span data-ttu-id="639d8-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="639d8-175">CqdBuilding</span></span>
- <span data-ttu-id="639d8-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="639d8-176">CqdNetwork</span></span>

<span data-ttu-id="639d8-177">可在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息以进行进一步的筛选和向下钻取。</span><span class="sxs-lookup"><span data-stu-id="639d8-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span>

<span data-ttu-id="639d8-178">用于这些表的数据定义如下：</span><span class="sxs-lookup"><span data-stu-id="639d8-178">The data used for these tables are defined as follows:</span></span>

<span data-ttu-id="639d8-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="639d8-179">**CqdBuilding**</span></span>

|<span data-ttu-id="639d8-180">列</span><span class="sxs-lookup"><span data-stu-id="639d8-180">Column</span></span>|<span data-ttu-id="639d8-181">数据类型</span><span class="sxs-lookup"><span data-stu-id="639d8-181">Data Type</span></span>|<span data-ttu-id="639d8-182">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="639d8-182">Allow Nulls?</span></span>|<span data-ttu-id="639d8-183">详细信息</span><span class="sxs-lookup"><span data-stu-id="639d8-183">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="639d8-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="639d8-184">BuildingKey</span></span> |<span data-ttu-id="639d8-185">int</span><span class="sxs-lookup"><span data-stu-id="639d8-185">int</span></span> |<span data-ttu-id="639d8-186">否</span><span class="sxs-lookup"><span data-stu-id="639d8-186">No</span></span> |<span data-ttu-id="639d8-187">CqdBuilding 表的主键。</span><span class="sxs-lookup"><span data-stu-id="639d8-187">Primary key for the CqdBuilding table.</span></span> |
|<span data-ttu-id="639d8-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="639d8-188">BuildingName</span></span> |<span data-ttu-id="639d8-189">varchar(80)</span><span class="sxs-lookup"><span data-stu-id="639d8-189">varchar(80)</span></span> |<span data-ttu-id="639d8-190">否</span><span class="sxs-lookup"><span data-stu-id="639d8-190">No</span></span> |<span data-ttu-id="639d8-191">大楼名称。</span><span class="sxs-lookup"><span data-stu-id="639d8-191">Building name.</span></span> |
|<span data-ttu-id="639d8-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="639d8-192">BuildingShortName</span></span> |<span data-ttu-id="639d8-193">varchar(10)</span><span class="sxs-lookup"><span data-stu-id="639d8-193">varchar(10)</span></span> |<span data-ttu-id="639d8-194">否</span><span class="sxs-lookup"><span data-stu-id="639d8-194">No</span></span> |<span data-ttu-id="639d8-195">大楼名称的简短版本。</span><span class="sxs-lookup"><span data-stu-id="639d8-195">Shorter version of the Building name.</span></span> |
|<span data-ttu-id="639d8-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="639d8-196">OwnershipTypeId</span></span> |<span data-ttu-id="639d8-197">int</span><span class="sxs-lookup"><span data-stu-id="639d8-197">int</span></span> |<span data-ttu-id="639d8-198">否</span><span class="sxs-lookup"><span data-stu-id="639d8-198">No</span></span> |<span data-ttu-id="639d8-199">外键，匹配 CqdBuildingOwners 表中的其中一个条目。</span><span class="sxs-lookup"><span data-stu-id="639d8-199">Foreign key, matches one of the entries in the CqdBuildingOwners table.</span></span> |
|<span data-ttu-id="639d8-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="639d8-200">BuildingTypeId</span></span> |<span data-ttu-id="639d8-201">int</span><span class="sxs-lookup"><span data-stu-id="639d8-201">int</span></span> |<span data-ttu-id="639d8-202">否</span><span class="sxs-lookup"><span data-stu-id="639d8-202">No</span></span> |<span data-ttu-id="639d8-203">外键，匹配 CqdBuildingType 表中的其中一个条目。</span><span class="sxs-lookup"><span data-stu-id="639d8-203">Foreign key, matches one of the entries in the CqdBuildingType table.</span></span> |
|<span data-ttu-id="639d8-204">纬度</span><span class="sxs-lookup"><span data-stu-id="639d8-204">Latitude</span></span> |<span data-ttu-id="639d8-205">float</span><span class="sxs-lookup"><span data-stu-id="639d8-205">float</span></span> |<span data-ttu-id="639d8-206">是</span><span class="sxs-lookup"><span data-stu-id="639d8-206">Yes</span></span> |<span data-ttu-id="639d8-207">大楼的纬度。</span><span class="sxs-lookup"><span data-stu-id="639d8-207">Latitude of the building.</span></span> |
|<span data-ttu-id="639d8-208">经度</span><span class="sxs-lookup"><span data-stu-id="639d8-208">Longitude</span></span> |<span data-ttu-id="639d8-209">float</span><span class="sxs-lookup"><span data-stu-id="639d8-209">float</span></span> |<span data-ttu-id="639d8-210">是</span><span class="sxs-lookup"><span data-stu-id="639d8-210">Yes</span></span> |<span data-ttu-id="639d8-211">大楼的经度。</span><span class="sxs-lookup"><span data-stu-id="639d8-211">Longitude of the building.</span></span> |
|<span data-ttu-id="639d8-212">CityName</span><span class="sxs-lookup"><span data-stu-id="639d8-212">CityName</span></span> |<span data-ttu-id="639d8-213">varchar(30)</span><span class="sxs-lookup"><span data-stu-id="639d8-213">varchar(30)</span></span> |<span data-ttu-id="639d8-214">是</span><span class="sxs-lookup"><span data-stu-id="639d8-214">Yes</span></span> |<span data-ttu-id="639d8-215">大楼所在的城市名称。</span><span class="sxs-lookup"><span data-stu-id="639d8-215">City name where the building is located.</span></span> |
|<span data-ttu-id="639d8-216">ZipCode</span><span class="sxs-lookup"><span data-stu-id="639d8-216">ZipCode</span></span> |<span data-ttu-id="639d8-217">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="639d8-217">varchar(25)</span></span> |<span data-ttu-id="639d8-218">是</span><span class="sxs-lookup"><span data-stu-id="639d8-218">Yes</span></span> |<span data-ttu-id="639d8-219">大楼所在的邮编。</span><span class="sxs-lookup"><span data-stu-id="639d8-219">Zip code where the building is located.</span></span> |
|<span data-ttu-id="639d8-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="639d8-220">CountryShortCode</span></span> |<span data-ttu-id="639d8-221">varchar(2)</span><span class="sxs-lookup"><span data-stu-id="639d8-221">varchar(2)</span></span> |<span data-ttu-id="639d8-222">是</span><span class="sxs-lookup"><span data-stu-id="639d8-222">Yes</span></span> |<span data-ttu-id="639d8-223">大楼所在的国家/地区的 ISO 3166-1 alpha-2 代码。</span><span class="sxs-lookup"><span data-stu-id="639d8-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span> |
|<span data-ttu-id="639d8-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="639d8-224">StateProvinceCode</span></span> |<span data-ttu-id="639d8-225">varchar(3)</span><span class="sxs-lookup"><span data-stu-id="639d8-225">varchar(3)</span></span> |<span data-ttu-id="639d8-226">是</span><span class="sxs-lookup"><span data-stu-id="639d8-226">Yes</span></span> |<span data-ttu-id="639d8-227">生成所在的州/省的三个字母的缩写。</span><span class="sxs-lookup"><span data-stu-id="639d8-227">Three-letter abbreviation for the State/Province where the building is located.</span></span> |
|<span data-ttu-id="639d8-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="639d8-228">InsideCorp</span></span> |<span data-ttu-id="639d8-229">bit</span><span class="sxs-lookup"><span data-stu-id="639d8-229">bit</span></span> |<span data-ttu-id="639d8-230">是</span><span class="sxs-lookup"><span data-stu-id="639d8-230">Yes</span></span> |<span data-ttu-id="639d8-231">位表示建筑物是否是企业网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="639d8-231">Bit indicates whether the building is part of the corporate network.</span></span> |
|<span data-ttu-id="639d8-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="639d8-232">BuildingOfficeType</span></span> |<span data-ttu-id="639d8-233">nvarchar(150)</span><span class="sxs-lookup"><span data-stu-id="639d8-233">nvarchar(150)</span></span> |<span data-ttu-id="639d8-234">是</span><span class="sxs-lookup"><span data-stu-id="639d8-234">Yes</span></span> |<span data-ttu-id="639d8-235">大楼办公室类型的说明。</span><span class="sxs-lookup"><span data-stu-id="639d8-235">Description of the building office type.</span></span> |
|<span data-ttu-id="639d8-236">区域</span><span class="sxs-lookup"><span data-stu-id="639d8-236">Region</span></span> |<span data-ttu-id="639d8-237">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="639d8-237">varchar(25)</span></span> |<span data-ttu-id="639d8-238">是</span><span class="sxs-lookup"><span data-stu-id="639d8-238">Yes</span></span> |<span data-ttu-id="639d8-239">大楼所在的地区。</span><span class="sxs-lookup"><span data-stu-id="639d8-239">Region where the building is located.</span></span> |
|||||

<span data-ttu-id="639d8-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="639d8-240">**CqdNetwork**</span></span>

|<span data-ttu-id="639d8-241">列</span><span class="sxs-lookup"><span data-stu-id="639d8-241">Column</span></span>|<span data-ttu-id="639d8-242">数据类型</span><span class="sxs-lookup"><span data-stu-id="639d8-242">Data Type</span></span>|<span data-ttu-id="639d8-243">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="639d8-243">Allow Nulls?</span></span>|<span data-ttu-id="639d8-244">详细信息</span><span class="sxs-lookup"><span data-stu-id="639d8-244">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="639d8-245">网络</span><span class="sxs-lookup"><span data-stu-id="639d8-245">Network</span></span> |<span data-ttu-id="639d8-246">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="639d8-246">varchar(25)</span></span> |<span data-ttu-id="639d8-247">否</span><span class="sxs-lookup"><span data-stu-id="639d8-247">No</span></span> |<span data-ttu-id="639d8-248">子网地址。</span><span class="sxs-lookup"><span data-stu-id="639d8-248">Subnet address.</span></span> |
|<span data-ttu-id="639d8-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="639d8-249">NetworkRange</span></span> |<span data-ttu-id="639d8-250">tinyint</span><span class="sxs-lookup"><span data-stu-id="639d8-250">tinyint</span></span> |<span data-ttu-id="639d8-251">是</span><span class="sxs-lookup"><span data-stu-id="639d8-251">Yes</span></span> |<span data-ttu-id="639d8-252">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="639d8-252">Subnet mask.</span></span> |
|<span data-ttu-id="639d8-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="639d8-253">NetworkNameID</span></span> |<span data-ttu-id="639d8-254">int</span><span class="sxs-lookup"><span data-stu-id="639d8-254">int</span></span> |<span data-ttu-id="639d8-255">是</span><span class="sxs-lookup"><span data-stu-id="639d8-255">Yes</span></span> |<span data-ttu-id="639d8-256">可选地映射到 CqdNetworkName 表中的一行。</span><span class="sxs-lookup"><span data-stu-id="639d8-256">Optionally maps to a row in CqdNetworkName table.</span></span> |
|<span data-ttu-id="639d8-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="639d8-257">BuildingKey</span></span> |<span data-ttu-id="639d8-258">int</span><span class="sxs-lookup"><span data-stu-id="639d8-258">int</span></span> |<span data-ttu-id="639d8-259">是</span><span class="sxs-lookup"><span data-stu-id="639d8-259">Yes</span></span> |<span data-ttu-id="639d8-260">外键，匹配 CqdBuilding 表中的其中一个条目。</span><span class="sxs-lookup"><span data-stu-id="639d8-260">Foreign key, matches one of the entries in the CqdBuilding table.</span></span> |
|<span data-ttu-id="639d8-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="639d8-261">UpdatedDate</span></span> |<span data-ttu-id="639d8-262">datetime</span><span class="sxs-lookup"><span data-stu-id="639d8-262">datetime</span></span> |<span data-ttu-id="639d8-263">否</span><span class="sxs-lookup"><span data-stu-id="639d8-263">No</span></span> |<span data-ttu-id="639d8-264">条目最后更新的日期时间。</span><span class="sxs-lookup"><span data-stu-id="639d8-264">Datetime for when the entry was last updated.</span></span> |
||||||

<span data-ttu-id="639d8-265">默认情况下，下一个表包含一个条目（0，"Unknown"）。</span><span class="sxs-lookup"><span data-stu-id="639d8-265">By default this next table has one entry (0, 'Unknown').</span></span>

<span data-ttu-id="639d8-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="639d8-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="639d8-267">列</span><span class="sxs-lookup"><span data-stu-id="639d8-267">Column</span></span>|<span data-ttu-id="639d8-268">数据类型</span><span class="sxs-lookup"><span data-stu-id="639d8-268">Data Type</span></span>|<span data-ttu-id="639d8-269">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="639d8-269">Allow Nulls?</span></span>|<span data-ttu-id="639d8-270">详细信息</span><span class="sxs-lookup"><span data-stu-id="639d8-270">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="639d8-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="639d8-271">BuildingTypeId</span></span> |<span data-ttu-id="639d8-272">int</span><span class="sxs-lookup"><span data-stu-id="639d8-272">int</span></span> |<span data-ttu-id="639d8-273">否</span><span class="sxs-lookup"><span data-stu-id="639d8-273">No</span></span> |<span data-ttu-id="639d8-274">CqdBuildingType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="639d8-274">Primary key for the CqdBuildingType table.</span></span> |
|<span data-ttu-id="639d8-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="639d8-275">BuildingTypeDesc</span></span> |<span data-ttu-id="639d8-276">char(18)</span><span class="sxs-lookup"><span data-stu-id="639d8-276">char(18)</span></span> |<span data-ttu-id="639d8-277">否</span><span class="sxs-lookup"><span data-stu-id="639d8-277">No</span></span> |<span data-ttu-id="639d8-278">大楼类型说明。</span><span class="sxs-lookup"><span data-stu-id="639d8-278">Building type description.</span></span> |
|||||

<span data-ttu-id="639d8-279">默认情况下，下一个表包含一个条目（0、"Unknown"、0、null）。</span><span class="sxs-lookup"><span data-stu-id="639d8-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="639d8-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="639d8-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="639d8-281">列</span><span class="sxs-lookup"><span data-stu-id="639d8-281">Column</span></span>|<span data-ttu-id="639d8-282">数据类型</span><span class="sxs-lookup"><span data-stu-id="639d8-282">Data Type</span></span>|<span data-ttu-id="639d8-283">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="639d8-283">Allow Nulls?</span></span>|<span data-ttu-id="639d8-284">详细信息</span><span class="sxs-lookup"><span data-stu-id="639d8-284">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="639d8-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="639d8-285">OwnershipTypeId</span></span> |<span data-ttu-id="639d8-286">int</span><span class="sxs-lookup"><span data-stu-id="639d8-286">int</span></span> |<span data-ttu-id="639d8-287">否</span><span class="sxs-lookup"><span data-stu-id="639d8-287">No</span></span> |<span data-ttu-id="639d8-288">CqdBuildingOwnershipType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="639d8-288">Primary key for the CqdBuildingOwnershipType table.</span></span> |
|<span data-ttu-id="639d8-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="639d8-289">OwnershipTypeDesc</span></span> |<span data-ttu-id="639d8-290">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="639d8-290">varchar(25)</span></span> |<span data-ttu-id="639d8-291">否</span><span class="sxs-lookup"><span data-stu-id="639d8-291">No</span></span> |<span data-ttu-id="639d8-292">所有权类型说明。</span><span class="sxs-lookup"><span data-stu-id="639d8-292">Ownership type description.</span></span> |
|<span data-ttu-id="639d8-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="639d8-293">LeaseInd</span></span> |<span data-ttu-id="639d8-294">tinyint</span><span class="sxs-lookup"><span data-stu-id="639d8-294">tinyint</span></span> |<span data-ttu-id="639d8-295">是</span><span class="sxs-lookup"><span data-stu-id="639d8-295">Yes</span></span> |<span data-ttu-id="639d8-296">引用 CqdBuildingOwnershipType 表中其他行的索引，用于确定租用的大楼。</span><span class="sxs-lookup"><span data-stu-id="639d8-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span> |
|<span data-ttu-id="639d8-297">所有者</span><span class="sxs-lookup"><span data-stu-id="639d8-297">Owner</span></span> |<span data-ttu-id="639d8-298">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="639d8-298">varchar(50)</span></span> |<span data-ttu-id="639d8-299">是</span><span class="sxs-lookup"><span data-stu-id="639d8-299">Yes</span></span> |<span data-ttu-id="639d8-300">大楼所有者。</span><span class="sxs-lookup"><span data-stu-id="639d8-300">Building owner.</span></span> |
|||||

<span data-ttu-id="639d8-301">默认情况下，下一个表包含一个条目（0、"Unknown"、0、null）。</span><span class="sxs-lookup"><span data-stu-id="639d8-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="639d8-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="639d8-302">**CqdBssid**</span></span>

|<span data-ttu-id="639d8-303">列</span><span class="sxs-lookup"><span data-stu-id="639d8-303">Column</span></span>|<span data-ttu-id="639d8-304">数据类型</span><span class="sxs-lookup"><span data-stu-id="639d8-304">Data Type</span></span>|<span data-ttu-id="639d8-305">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="639d8-305">Allow Nulls?</span></span>|<span data-ttu-id="639d8-306">详细信息</span><span class="sxs-lookup"><span data-stu-id="639d8-306">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="639d8-307">bss</span><span class="sxs-lookup"><span data-stu-id="639d8-307">bss</span></span> |<span data-ttu-id="639d8-308">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="639d8-308">nvarchar(50)</span></span> |<span data-ttu-id="639d8-309">否</span><span class="sxs-lookup"><span data-stu-id="639d8-309">No</span></span> |<span data-ttu-id="639d8-310">CqdBssid 表的主键。</span><span class="sxs-lookup"><span data-stu-id="639d8-310">Primary key for the CqdBssid table.</span></span> <span data-ttu-id="639d8-311">是 WiFi 接入点的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="639d8-311">Is the BSSID of the WiFi Access Point.</span></span> |
|<span data-ttu-id="639d8-312">ess</span><span class="sxs-lookup"><span data-stu-id="639d8-312">ess</span></span> |<span data-ttu-id="639d8-313">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="639d8-313">nvarchar(50)</span></span> |<span data-ttu-id="639d8-314">是</span><span class="sxs-lookup"><span data-stu-id="639d8-314">Yes</span></span> |<span data-ttu-id="639d8-315">WiFi 接入点控制器信息。</span><span class="sxs-lookup"><span data-stu-id="639d8-315">Wifi Access Point Controller information.</span></span> |
|<span data-ttu-id="639d8-316">phy</span><span class="sxs-lookup"><span data-stu-id="639d8-316">phy</span></span> |<span data-ttu-id="639d8-317">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="639d8-317">nvarchar(50)</span></span> |<span data-ttu-id="639d8-318">是</span><span class="sxs-lookup"><span data-stu-id="639d8-318">Yes</span></span> |<span data-ttu-id="639d8-319">Phy 信息。</span><span class="sxs-lookup"><span data-stu-id="639d8-319">Phy information.</span></span> |
|<span data-ttu-id="639d8-320">ap</span><span class="sxs-lookup"><span data-stu-id="639d8-320">ap</span></span> |<span data-ttu-id="639d8-321">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="639d8-321">nvarchar(50)</span></span> |<span data-ttu-id="639d8-322">是</span><span class="sxs-lookup"><span data-stu-id="639d8-322">Yes</span></span> |<span data-ttu-id="639d8-323">WiFi 接入点名称。</span><span class="sxs-lookup"><span data-stu-id="639d8-323">Wifi Access Point Name.</span></span> |
|<span data-ttu-id="639d8-324">大楼</span><span class="sxs-lookup"><span data-stu-id="639d8-324">Building</span></span> |<span data-ttu-id="639d8-325">nvarchar(500)</span><span class="sxs-lookup"><span data-stu-id="639d8-325">nvarchar(500)</span></span> |<span data-ttu-id="639d8-326">是</span><span class="sxs-lookup"><span data-stu-id="639d8-326">Yes</span></span> |<span data-ttu-id="639d8-327">WiFi 接入点所在的建筑物名称。</span><span class="sxs-lookup"><span data-stu-id="639d8-327">The Building Name the WiFi Access Point is located in.</span></span> |
||||

## <a name="cqd-streams"></a><span data-ttu-id="639d8-328">CQD 流</span><span class="sxs-lookup"><span data-stu-id="639d8-328">CQD Streams</span></span>

<span data-ttu-id="639d8-329">CQD 流被视为 "良好"、"差" 或 "未分类"。</span><span class="sxs-lookup"><span data-stu-id="639d8-329">A CQD stream is considered good, poor, or unclassified.</span></span> <span data-ttu-id="639d8-330">CQM 1.5 现在使用以下 CQD 定义：</span><span class="sxs-lookup"><span data-stu-id="639d8-330">CQM 1.5 now uses the following CQD definition:</span></span>

- <span data-ttu-id="639d8-331">较差的流是不超过阈值的较差调用指标的任意组合。</span><span class="sxs-lookup"><span data-stu-id="639d8-331">A poor stream is any combination of the poor call metrics beyond threshold.</span></span>
- <span data-ttu-id="639d8-332">当通话中的一个流较差时，两个通话流都被标记为差。</span><span class="sxs-lookup"><span data-stu-id="639d8-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="639d8-333">在会议中，每个参与者都计为唯一通话，并单独报告给所有其他参与者。</span><span class="sxs-lookup"><span data-stu-id="639d8-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
- <span data-ttu-id="639d8-334">未分类流是没有质量指标（即，合成事务或短调用）的数据流。</span><span class="sxs-lookup"><span data-stu-id="639d8-334">Unclassified streams are streams without quality metrics (that is, Synthetic Transactions or short calls).</span></span>
- <span data-ttu-id="639d8-335">有效流 = 非移动客户端</span><span class="sxs-lookup"><span data-stu-id="639d8-335">Valid Streams = non-mobile clients</span></span>
- <span data-ttu-id="639d8-336">分类器不能修改</span><span class="sxs-lookup"><span data-stu-id="639d8-336">Classifier cannot be modified</span></span>

<span data-ttu-id="639d8-337">**较差呼叫定义/分类器**</span><span class="sxs-lookup"><span data-stu-id="639d8-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="639d8-338">指标</span><span class="sxs-lookup"><span data-stu-id="639d8-338">Metric</span></span>|<span data-ttu-id="639d8-339">阈值</span><span class="sxs-lookup"><span data-stu-id="639d8-339">Threshold</span></span>|
|:-----|:-----|
|<span data-ttu-id="639d8-340">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="639d8-340">DegradationAvg</span></span> |<span data-ttu-id="639d8-341">大于 1.0（-1 网络 MOS）</span><span class="sxs-lookup"><span data-stu-id="639d8-341">Greater than 1.0 (-1 network MOS)</span></span> |
|<span data-ttu-id="639d8-342">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="639d8-342">RoundTrip</span></span> |<span data-ttu-id="639d8-343">大于 500 </span><span class="sxs-lookup"><span data-stu-id="639d8-343">Greater than 500</span></span> |
|<span data-ttu-id="639d8-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="639d8-344">PacketLossRate</span></span> |<span data-ttu-id="639d8-345">大于0.1 （10%）</span><span class="sxs-lookup"><span data-stu-id="639d8-345">Greater than 0.1 (10%)</span></span> |
|<span data-ttu-id="639d8-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="639d8-346">JitterInterArrival</span></span> |<span data-ttu-id="639d8-347">大于 30 </span><span class="sxs-lookup"><span data-stu-id="639d8-347">Greater than 30</span></span> |
|<span data-ttu-id="639d8-348">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="639d8-348">RatioConcealedSamplesAvg</span></span> |<span data-ttu-id="639d8-349">大于0.07</span><span class="sxs-lookup"><span data-stu-id="639d8-349">Greater than 0.07</span></span> |
|||

<span data-ttu-id="639d8-350">JPDR 定义 = 较差呼叫定义减去 RatioConcealedSamplesAvg </span><span class="sxs-lookup"><span data-stu-id="639d8-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span>

## <a name="where-is-callercallee"></a><span data-ttu-id="639d8-351">呼叫方/被呼叫方在哪里？</span><span class="sxs-lookup"><span data-stu-id="639d8-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="639d8-352">CQD 不使用 "调用方/被调用方" 字段，而是使用 "First" 和 "Second"，因为调用方和被调用方之间有介入的步骤。</span><span class="sxs-lookup"><span data-stu-id="639d8-352">CQD doesn't use Caller/Callee fields, instead it uses "First" and "Second" because there are intervening steps between the caller and callee.</span></span>

 <span data-ttu-id="639d8-353">**第一个**如果流中涉及服务器，则始终为服务器终结点（例如，AV MCU 或中介服务器）。</span><span class="sxs-lookup"><span data-stu-id="639d8-353">**First** Will always be the Server endpoint (for example, AV MCU or Mediation Server) if a Server is involved in the stream.</span></span>

 <span data-ttu-id="639d8-354">**第二个**将始终是客户端端点，除非是服务器-服务器流。</span><span class="sxs-lookup"><span data-stu-id="639d8-354">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>

<span data-ttu-id="639d8-355">**“第一个”和“第二个”分类示例**</span><span class="sxs-lookup"><span data-stu-id="639d8-355">**Example of First and Second classification**</span></span>

|<span data-ttu-id="639d8-356">端点 1 UAType </span><span class="sxs-lookup"><span data-stu-id="639d8-356">Endpoint 1 UAType</span></span>|<span data-ttu-id="639d8-357">端点 2 UUAType </span><span class="sxs-lookup"><span data-stu-id="639d8-357">Endpoint 2 UUAType</span></span>|<span data-ttu-id="639d8-358">第一个</span><span class="sxs-lookup"><span data-stu-id="639d8-358">First</span></span>|<span data-ttu-id="639d8-359">第二个</span><span class="sxs-lookup"><span data-stu-id="639d8-359">Second</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="639d8-360">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="639d8-360">2 (AVMCU)</span></span> |<span data-ttu-id="639d8-361">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="639d8-361">4 (Skype for Business)</span></span> |<span data-ttu-id="639d8-362">端点 1</span><span class="sxs-lookup"><span data-stu-id="639d8-362">Endpoint 1</span></span> |<span data-ttu-id="639d8-363">端点 2</span><span class="sxs-lookup"><span data-stu-id="639d8-363">Endpoint 2</span></span> |
|<span data-ttu-id="639d8-364">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="639d8-364">2 (AVMCU)</span></span> |<span data-ttu-id="639d8-365">1 (mMediationServer) </span><span class="sxs-lookup"><span data-stu-id="639d8-365">1 (mMediationServer)</span></span> |<span data-ttu-id="639d8-366">端点 2</span><span class="sxs-lookup"><span data-stu-id="639d8-366">Endpoint 2</span></span> |<span data-ttu-id="639d8-367">端点 1</span><span class="sxs-lookup"><span data-stu-id="639d8-367">Endpoint 1</span></span> |
|<span data-ttu-id="639d8-368">4 (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="639d8-368">4 (Skype for Business)</span></span> |<span data-ttu-id="639d8-369">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="639d8-369">4 (Skype for Business)</span></span> |<span data-ttu-id="639d8-370">MediaLine 中的呼叫方 </span><span class="sxs-lookup"><span data-stu-id="639d8-370">The Caller in MediaLine</span></span> |<span data-ttu-id="639d8-371">MMediaLine 中的被呼叫方 </span><span class="sxs-lookup"><span data-stu-id="639d8-371">The Callee in MMediaLine</span></span> |
|||||

<span data-ttu-id="639d8-372">如果两个终结点的类型相同，CQD 将使调用方条目成为第二个终结点和被调用方的条目。</span><span class="sxs-lookup"><span data-stu-id="639d8-372">If both endpoints are the same type, CQD makes the Caller entry First and the Callee Second.</span></span> <span data-ttu-id="639d8-373">有关终结点名称的详细信息，请参阅[此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。</span><span class="sxs-lookup"><span data-stu-id="639d8-373">For more information about endpoint names, see [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).</span></span>

## <a name="accounting-for-vpn"></a><span data-ttu-id="639d8-374">VPN 考虑事项</span><span class="sxs-lookup"><span data-stu-id="639d8-374">Accounting for VPN</span></span>

<span data-ttu-id="639d8-375">如果已知 VPN 解决方案能够准确地设置 VPN 标志，则您已经设置完毕。</span><span class="sxs-lookup"><span data-stu-id="639d8-375">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="639d8-376">否则，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="639d8-376">Otherwise, use one of the following methods:</span></span>

- <span data-ttu-id="639d8-377">创建名为 VPN 的网络类型（首选），然后将 VPN 子网与此新 VPN 网络类型关联。</span><span class="sxs-lookup"><span data-stu-id="639d8-377">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
- <span data-ttu-id="639d8-378">创建名为 VPN 的大楼，然后将 VPN 子网与此大楼关联。</span><span class="sxs-lookup"><span data-stu-id="639d8-378">Create a building called VPN, then Associate VPN Subnets with this building.</span></span>

## <a name="query-fundamentals"></a><span data-ttu-id="639d8-379">查询基础知识</span><span class="sxs-lookup"><span data-stu-id="639d8-379">Query Fundamentals</span></span>

<span data-ttu-id="639d8-380">格式正确的查询包含以下三个参数：</span><span class="sxs-lookup"><span data-stu-id="639d8-380">A well-formed query contains all three of these parameters:</span></span>

- <span data-ttu-id="639d8-381">度量</span><span class="sxs-lookup"><span data-stu-id="639d8-381">Measurement</span></span>
- <span data-ttu-id="639d8-382">维度</span><span class="sxs-lookup"><span data-stu-id="639d8-382">Dimension</span></span>
- <span data-ttu-id="639d8-383">筛选器</span><span class="sxs-lookup"><span data-stu-id="639d8-383">Filter</span></span>

<span data-ttu-id="639d8-384">例如，“按子网[维度]显示大楼 6 [筛选器]的较差流[度量]”是一个格式正确的查询。</span><span class="sxs-lookup"><span data-stu-id="639d8-384">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

## <a name="what-does-union-do"></a><span data-ttu-id="639d8-385">“联合”起什么作用？</span><span class="sxs-lookup"><span data-stu-id="639d8-385">What does UNION do?</span></span>

<span data-ttu-id="639d8-386">Union 允许你用 AND 运算符筛选条件。</span><span class="sxs-lookup"><span data-stu-id="639d8-386">Union allows you to filter conditions with the AND operator.</span></span> <span data-ttu-id="639d8-387">在某些情况下，你可以将多个筛选条件结合在一起以获得类似于 OR 操作的结果。</span><span class="sxs-lookup"><span data-stu-id="639d8-387">There are scenarios where you can combine multiple Filter conditions together to achieve a result similar to an OR operation.</span></span>

<span data-ttu-id="639d8-388">示例：若要从建筑物获取所有流，UNION 将提供合并数据集的独特视图。</span><span class="sxs-lookup"><span data-stu-id="639d8-388">Example: To get all streams from a building, UNION provides a distinct view of the merged dataset.</span></span> <span data-ttu-id="639d8-389">要使用“联合”，请在你要联合的两个筛选条件上的“联合”字段中插入普通文本。</span><span class="sxs-lookup"><span data-stu-id="639d8-389">To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span>

## <a name="default-report-breakdown"></a><span data-ttu-id="639d8-390">默认报告细分</span><span class="sxs-lookup"><span data-stu-id="639d8-390">Default Report Breakdown</span></span>

<span data-ttu-id="639d8-391">如果在内部管理无线，你可以在管理存储桶中重新创建“无线”报告。</span><span class="sxs-lookup"><span data-stu-id="639d8-391">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span>

![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a><span data-ttu-id="639d8-393">可选过程</span><span class="sxs-lookup"><span data-stu-id="639d8-393">Operational Processes</span></span>

<span data-ttu-id="639d8-394">先查看和修正托管流。</span><span class="sxs-lookup"><span data-stu-id="639d8-394">Review and remediate Managed Streams first.</span></span> <span data-ttu-id="639d8-395">此区域中的质量应该完全在你的控制范围内，因此最容易修复。</span><span class="sxs-lookup"><span data-stu-id="639d8-395">Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span>

### <a name="managed-streams"></a><span data-ttu-id="639d8-396">管理流 </span><span class="sxs-lookup"><span data-stu-id="639d8-396">Managed Streams</span></span>

<span data-ttu-id="639d8-397">按以下顺序查看并更正管理流：</span><span class="sxs-lookup"><span data-stu-id="639d8-397">Review and remediate managed streams in the following order:</span></span>

1. <span data-ttu-id="639d8-398">服务器-服务器 </span><span class="sxs-lookup"><span data-stu-id="639d8-398">Server-Server</span></span>
2. <span data-ttu-id="639d8-399"> 服务器-有线-内部</span><span class="sxs-lookup"><span data-stu-id="639d8-399">Server-Wired-Inside</span></span>
3. <span data-ttu-id="639d8-400">有线-有线-内部 </span><span class="sxs-lookup"><span data-stu-id="639d8-400">Wired-Wired-Inside</span></span>

### <a name="unmanaged-streams"></a><span data-ttu-id="639d8-401">非管理流</span><span class="sxs-lookup"><span data-stu-id="639d8-401">Unmanaged Streams</span></span>

<span data-ttu-id="639d8-402">按以下顺序查看并更正非管理流：</span><span class="sxs-lookup"><span data-stu-id="639d8-402">Review and remediate unmanaged streams in the following order:</span></span>

1. <span data-ttu-id="639d8-403">服务器-WiFi-内部</span><span class="sxs-lookup"><span data-stu-id="639d8-403">Server-Wifi-Inside</span></span>
2. <span data-ttu-id="639d8-404">服务器-有线-外部</span><span class="sxs-lookup"><span data-stu-id="639d8-404">Server-Wired-Outside</span></span>
3. <span data-ttu-id="639d8-405">服务器-WiFi-外部</span><span class="sxs-lookup"><span data-stu-id="639d8-405">Server-Wifi-Outside</span></span>
4. <span data-ttu-id="639d8-406">有线-外部-直接</span><span class="sxs-lookup"><span data-stu-id="639d8-406">Wired-Outside-Direct</span></span>
5. <span data-ttu-id="639d8-407">有线-外部-中继</span><span class="sxs-lookup"><span data-stu-id="639d8-407">Wired-Outside-Relay</span></span>
6. <span data-ttu-id="639d8-408">其他非管理</span><span class="sxs-lookup"><span data-stu-id="639d8-408">Other Unmanaged</span></span>
