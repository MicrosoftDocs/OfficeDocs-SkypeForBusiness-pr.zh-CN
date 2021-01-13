---
title: 使用 Skype for Business Server 的呼叫质量仪表板
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要：了解如何使用呼叫质量仪表板。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: ed1e5563a4677dce33648280590530ca2a9b1b9b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803102"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="61636-104">使用 Skype for Business Server 的呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="61636-104">Use Call Quality Dashboard for Skype for Business Server</span></span>

<span data-ttu-id="61636-105">**摘要：** 了解如何使用呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="61636-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="61636-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="61636-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="61636-107">呼叫质量仪表板 (CQD) 允许 IT 专业人员使用聚合数据，通过比较用户组的统计信息来识别趋势和模式，从而发现产生媒体质量问题的问题。</span><span class="sxs-lookup"><span data-stu-id="61636-107">Call Quality Dashboard (CQD) allows IT Pros to use aggregate data to identify problems creating media quality issues by  comparing statistics for groups of users to identify trends and patterns.</span></span> <span data-ttu-id="61636-108">CQD 不专注于解决单个呼叫问题，而是确定适用于许多用户的问题和解决方案。</span><span class="sxs-lookup"><span data-stu-id="61636-108">CQD is not focused on solving individual call issues, but on identifying problems and solutions that apply to many users.</span></span>

## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="61636-109">通话质量仪表板用户指南</span><span class="sxs-lookup"><span data-stu-id="61636-109">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="61636-110">CQD 是一个 Web 门户，用于快速创建和组织基于 QoE (用户体验质量) 报告。</span><span class="sxs-lookup"><span data-stu-id="61636-110">CQD is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data.</span></span> <span data-ttu-id="61636-111">CQD 部署 SSAS 多维数据集以聚合 QoE 指标数据库中的数据，使管理员能够创建和修改报告或实时进行调查。</span><span class="sxs-lookup"><span data-stu-id="61636-111">CQD deploys an SSAS cube to aggregate the data in the QoE Metrics database, and enables admins to create and modify reports or do investigations in real time.</span></span> <span data-ttu-id="61636-112">虽然可以使用 Excel 直接连接到多维数据集，但门户已针对多个涉及 QoE 数据的工作流进行了优化。</span><span class="sxs-lookup"><span data-stu-id="61636-112">While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data.</span></span> <span data-ttu-id="61636-113">数据包括：</span><span class="sxs-lookup"><span data-stu-id="61636-113">The data includes:</span></span>

- <span data-ttu-id="61636-114">用于快速访问的缓存报表数据</span><span class="sxs-lookup"><span data-stu-id="61636-114">Cached report data for fast access</span></span>
- <span data-ttu-id="61636-115">指向用于信息共享和发布的报告页面的深层链接</span><span class="sxs-lookup"><span data-stu-id="61636-115">Deep links to report pages for information sharing and publishing</span></span>
- <span data-ttu-id="61636-116">简化了报告编辑和创建，以及报表说明的可编辑元数据。</span><span class="sxs-lookup"><span data-stu-id="61636-116">Streamlined report editing and creation, and editable metadata for report descriptions.</span></span>

<span data-ttu-id="61636-117">此外，CQD 还公开了 Web API，这些 API 允许用户以编程方式访问多维数据集数据，以用于自定义仪表板。</span><span class="sxs-lookup"><span data-stu-id="61636-117">Also, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>

### <a name="feature-overview"></a><span data-ttu-id="61636-118">功能概述</span><span class="sxs-lookup"><span data-stu-id="61636-118">Feature Overview</span></span>

<span data-ttu-id="61636-119">访问呼叫质量仪表板时，将看到以下屏幕：</span><span class="sxs-lookup"><span data-stu-id="61636-119">When you visit the Call Quality Dashboard, you see the following screen:</span></span>

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. <span data-ttu-id="61636-121">"摘要窗格"是"报告集"的 (位于右侧) 的上下文。</span><span class="sxs-lookup"><span data-stu-id="61636-121">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span>
2. <span data-ttu-id="61636-122">在摘要窗格报表中单击"编辑"以设置级别属性 (包括 Y 轴高度) 。</span><span class="sxs-lookup"><span data-stu-id="61636-122">Click "Edit" in the Summary PaneReport to set level properties (including Y-axis height).</span></span>
3. <span data-ttu-id="61636-123">痕迹导航可帮助您标识报告集层次结构中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="61636-123">The Breadcrumb helps you identify your current location within the report set hierarchy.</span></span>
4. <span data-ttu-id="61636-124">包含子报表的报告将显示为一个蓝色链接。</span><span class="sxs-lookup"><span data-stu-id="61636-124">Reports with subreports are shown with a blue link.</span></span> <span data-ttu-id="61636-125">单击链接可向下钻取到子报告。</span><span class="sxs-lookup"><span data-stu-id="61636-125">Click the link to drill down to the child reports.</span></span>

<span data-ttu-id="61636-126">将鼠标移到条形图和趋势线上以显示详细值。</span><span class="sxs-lookup"><span data-stu-id="61636-126">Move the mouse over the bar charts and trend lines to show detailed values.</span></span> <span data-ttu-id="61636-127">具有焦点的报告显示操作菜单："编辑"、"克隆"、"删除"和"下载"。</span><span class="sxs-lookup"><span data-stu-id="61636-127">The report that has focus shows the action menu: "Edit", "Clone", "Delete", and "Download".</span></span>

### <a name="default-reports"></a><span data-ttu-id="61636-128">默认报告</span><span class="sxs-lookup"><span data-stu-id="61636-128">Default Reports</span></span>

<span data-ttu-id="61636-129">首次访问呼叫质量仪表板门户时，将自动创建一组默认报告。</span><span class="sxs-lookup"><span data-stu-id="61636-129">When you first access the Call Quality Dashboard portal, a default set of reports is automatically created.</span></span> <span data-ttu-id="61636-130">这些报告有时称为系统报告。</span><span class="sxs-lookup"><span data-stu-id="61636-130">These reports are sometimes referred to as system reports.</span></span> <span data-ttu-id="61636-131">您可以自由修改或删除这些报告，或者通过创建新的同级和子报告来扩展它们。</span><span class="sxs-lookup"><span data-stu-id="61636-131">You are able to freely modify or delete these reports or extend them by creating new sibling and child reports.</span></span>

<span data-ttu-id="61636-132">在顶级，"音频流每月趋势"报告显示所有音频流的每月趋势。</span><span class="sxs-lookup"><span data-stu-id="61636-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="61636-133">将鼠标移到条形图中的条形图上，以显示条形图所代表的数据的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="61636-133">Move the mouse over the bars in a bar chart to show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="61636-134">单击"音频流每月趋势"报告的标题以导航到"托管音频流与非托管音频流"报告，其中报告在托管呼叫和未托管呼叫之间拆分。</span><span class="sxs-lookup"><span data-stu-id="61636-134">Click the title of the Audio Streams Monthly Trend report to navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="61636-135">托管呼叫是公司防火墙内部通过有线连接拨打的呼叫。</span><span class="sxs-lookup"><span data-stu-id="61636-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="61636-136">非托管呼叫包括从公司防火墙外拨打的呼叫，以及通过 WI-Fi 进行的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="61636-136">Unmanaged calls include calls made from outside the corporate firewall and all calls made over Wi-Fi.</span></span>

<span data-ttu-id="61636-137">另一个顶级报告称为"用户报告的呼叫质量分级直方图"。</span><span class="sxs-lookup"><span data-stu-id="61636-137">The other top-level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="61636-138">通话质量评级是 Skype for Business 用户在呼叫结束时提供的数字，用于指示呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="61636-138">Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="61636-139">评分数字范围为 1 到 5，1 是最差的，5 表示最佳。</span><span class="sxs-lookup"><span data-stu-id="61636-139">The rating numbers range from 1 to 5, 1 is the worst and 5 is the best.</span></span> <span data-ttu-id="61636-140">直方图显示一个月内评级为指示的音频呼叫数。</span><span class="sxs-lookup"><span data-stu-id="61636-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span>

<span data-ttu-id="61636-141">单击任何报告的标题以导航到具有更多数据筛选器的报表。</span><span class="sxs-lookup"><span data-stu-id="61636-141">Click the title of any of the reports to navigate into reports with more filters on the data.</span></span> <span data-ttu-id="61636-142">在系统报告中，每个子报告都显示其父报告中可用的数据的子集。</span><span class="sxs-lookup"><span data-stu-id="61636-142">In the system reports, each child report displays a subset of the data available in its parent report.</span></span> <span data-ttu-id="61636-143">问题解决模型很简单：调查将问题限制到的数据或趋势的子报告，并逐渐缩小问题空间。</span><span class="sxs-lookup"><span data-stu-id="61636-143">The problem-solving model is simple: investigate which subreport the data or trend suggesting a problem is confined to, and gradually narrow down the problem space.</span></span> <span data-ttu-id="61636-144">创建子报表的能力允许你调查自己对特定数据趋势原因的猜测。</span><span class="sxs-lookup"><span data-stu-id="61636-144">The ability to create subreports allows you to investigate your own guesses about the cause of specific data trends.</span></span>

### <a name="create-and-edit-reports"></a><span data-ttu-id="61636-145">创建和编辑报告</span><span class="sxs-lookup"><span data-stu-id="61636-145">Create and Edit Reports</span></span>

<span data-ttu-id="61636-146">单击报表的操作菜单中的"编辑"以查看报告编辑器。</span><span class="sxs-lookup"><span data-stu-id="61636-146">Click "Edit" in the action menu of a report to see the Report Editor.</span></span> <span data-ttu-id="61636-147">每个报表都由多维数据集中的查询进行备份。</span><span class="sxs-lookup"><span data-stu-id="61636-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="61636-148">报表是查询返回的数据的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="61636-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="61636-149">报表编辑器可帮助您编辑这些查询和报表的显示选项。</span><span class="sxs-lookup"><span data-stu-id="61636-149">The Report Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="61636-150">打开报告编辑器时，可以看到：</span><span class="sxs-lookup"><span data-stu-id="61636-150">When you open the Report Editor, you  see:</span></span>

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="61636-152">在左窗格中选择维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="61636-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="61636-153">将鼠标悬停在其中一个现有值上可显示允许删除值的"x"按钮。</span><span class="sxs-lookup"><span data-stu-id="61636-153">Hover over one of the existing values to show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="61636-154">单击标题旁边的"加号"按钮，打开可在其中添加新维度、度量值或筛选器的对话框。</span><span class="sxs-lookup"><span data-stu-id="61636-154">Click the "plus" button next to a heading to open the dialog where you can add a new dimension, measure, or filter.</span></span>
2. <span data-ttu-id="61636-155">图表自定义选项显示在顶部。</span><span class="sxs-lookup"><span data-stu-id="61636-155">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="61636-156">报告编辑器中提供了报表预览。</span><span class="sxs-lookup"><span data-stu-id="61636-156">A preview of the report is available in the Report Editor.</span></span>
4. <span data-ttu-id="61636-157">可以使用底部的编辑框创建详细的报告说明。</span><span class="sxs-lookup"><span data-stu-id="61636-157">A detailed report description can be created with the edit box at the bottom.</span></span>

### <a name="sparklines-in-tables"></a><span data-ttu-id="61636-158">表中的迷你图</span><span class="sxs-lookup"><span data-stu-id="61636-158">Sparklines in Tables</span></span>

<span data-ttu-id="61636-159">将 StartDate.Month 添加为维度并且数据以表格形式呈现为趋势时，条形图和迷你图可以在表格单元格内显示。</span><span class="sxs-lookup"><span data-stu-id="61636-159">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells.</span></span> <span data-ttu-id="61636-160">将鼠标指针移到条形图和迷你图上，以显示各个月份的值。</span><span class="sxs-lookup"><span data-stu-id="61636-160">Move the mouse pointer over the bar chart and the sparklines to show the values for individual months.</span></span>

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

<span data-ttu-id="61636-162">为了显示条形图和迷你图，必须选中报告编辑器顶部的"显示迷你图"复选框。</span><span class="sxs-lookup"><span data-stu-id="61636-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="61636-163">这将选择"趋势"选项，将 Month 向下移动为最后一个维度，这也可通过单击"月"，然后使用向上和向下箭头向上或向下移动 StartDate.Month 实现。</span><span class="sxs-lookup"><span data-stu-id="61636-163">This selects the Trend option and moves Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span>

### <a name="settings"></a><span data-ttu-id="61636-164">设置</span><span class="sxs-lookup"><span data-stu-id="61636-164">Settings</span></span>

<span data-ttu-id="61636-165">"设置"菜单包含指向有用页面（如"系统运行状况"和"关于"页面）的链接，位于仪表板的右上角。</span><span class="sxs-lookup"><span data-stu-id="61636-165">The settings menu contains links to useful pages like the System Health and About pages, and is located in the top-right corner of the dashboard.</span></span>

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

<span data-ttu-id="61636-167">是否显示说明和时间戳取决于单个用户，并且这些设置仅影响个人版本的仪表板，并且不会修改报告集或其他用户看到的信息。</span><span class="sxs-lookup"><span data-stu-id="61636-167">Whether to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, and do not modify the report set or what other users see.</span></span> <span data-ttu-id="61636-168">清除缓存会导致所有查询从多维数据集重新加载其数据，而还原默认值会删除用户创建或修改的所有报告，并重新创建系统报告集 —用户首次登录时会看到的内容。</span><span class="sxs-lookup"><span data-stu-id="61636-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when they log in for the first time.</span></span>

<span data-ttu-id="61636-169">用户仪表板链接显示一个页面，用户可以在此页面查看 CQD 的其他用户并浏览其报告。</span><span class="sxs-lookup"><span data-stu-id="61636-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="61636-170">若要共享报告集，请复制 URL 栏中的链接，并与另一个 CQD 用户共享它。</span><span class="sxs-lookup"><span data-stu-id="61636-170">To share a report set, copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="61636-171">此链接是其他用户在用户用户名下的"用户仪表板链接"页看到的相同链接。</span><span class="sxs-lookup"><span data-stu-id="61636-171">This link is the same link other users would see in the Users Dashboard Link page under the user's username.</span></span>

### <a name="supplying-subnet-information"></a><span data-ttu-id="61636-172">提供子网信息</span><span class="sxs-lookup"><span data-stu-id="61636-172">Supplying Subnet Information</span></span>

<span data-ttu-id="61636-173">如果存档数据库中输入了特定于站点的信息以提供子网到建筑物的映射信息， (例如，通过构建网络网络来提供有线/无线呼叫质量) 。</span><span class="sxs-lookup"><span data-stu-id="61636-173">Additional information can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (for example, wired/wireless call quality by building).</span></span>

<span data-ttu-id="61636-174">至少填写下表以创建这些报告：</span><span class="sxs-lookup"><span data-stu-id="61636-174">At a minimum, complete the following tables to create these reports:</span></span>

- <span data-ttu-id="61636-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="61636-175">CqdBuilding</span></span>
- <span data-ttu-id="61636-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="61636-176">CqdNetwork</span></span>

<span data-ttu-id="61636-177">可以在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息，以便进一步筛选和向下钻取。</span><span class="sxs-lookup"><span data-stu-id="61636-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span>

<span data-ttu-id="61636-178">用于这些表的数据定义如下：</span><span class="sxs-lookup"><span data-stu-id="61636-178">The data used for these tables are defined as follows:</span></span>

<span data-ttu-id="61636-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="61636-179">**CqdBuilding**</span></span>

|<span data-ttu-id="61636-180">列</span><span class="sxs-lookup"><span data-stu-id="61636-180">Column</span></span>|<span data-ttu-id="61636-181">数据类型</span><span class="sxs-lookup"><span data-stu-id="61636-181">Data Type</span></span>|<span data-ttu-id="61636-182">允许 Null？</span><span class="sxs-lookup"><span data-stu-id="61636-182">Allow Nulls?</span></span>|<span data-ttu-id="61636-183">详细信息</span><span class="sxs-lookup"><span data-stu-id="61636-183">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61636-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="61636-184">BuildingKey</span></span> |<span data-ttu-id="61636-185">int</span><span class="sxs-lookup"><span data-stu-id="61636-185">int</span></span> |<span data-ttu-id="61636-186">否</span><span class="sxs-lookup"><span data-stu-id="61636-186">No</span></span> |<span data-ttu-id="61636-187">CqdBuilding 表的主键。</span><span class="sxs-lookup"><span data-stu-id="61636-187">Primary key for the CqdBuilding table.</span></span> |
|<span data-ttu-id="61636-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="61636-188">BuildingName</span></span> |<span data-ttu-id="61636-189">varchar (80) </span><span class="sxs-lookup"><span data-stu-id="61636-189">varchar(80)</span></span> |<span data-ttu-id="61636-190">否</span><span class="sxs-lookup"><span data-stu-id="61636-190">No</span></span> |<span data-ttu-id="61636-191">建筑物名称。</span><span class="sxs-lookup"><span data-stu-id="61636-191">Building name.</span></span> |
|<span data-ttu-id="61636-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="61636-192">BuildingShortName</span></span> |<span data-ttu-id="61636-193">varchar (10) </span><span class="sxs-lookup"><span data-stu-id="61636-193">varchar(10)</span></span> |<span data-ttu-id="61636-194">否</span><span class="sxs-lookup"><span data-stu-id="61636-194">No</span></span> |<span data-ttu-id="61636-195">生成名称的更短版本。</span><span class="sxs-lookup"><span data-stu-id="61636-195">Shorter version of the Building name.</span></span> |
|<span data-ttu-id="61636-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="61636-196">OwnershipTypeId</span></span> |<span data-ttu-id="61636-197">int</span><span class="sxs-lookup"><span data-stu-id="61636-197">int</span></span> |<span data-ttu-id="61636-198">否</span><span class="sxs-lookup"><span data-stu-id="61636-198">No</span></span> |<span data-ttu-id="61636-199">外键，与 CqdBuildingOwners 表中的条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="61636-199">Foreign key, matches one of the entries in the CqdBuildingOwners table.</span></span> |
|<span data-ttu-id="61636-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="61636-200">BuildingTypeId</span></span> |<span data-ttu-id="61636-201">int</span><span class="sxs-lookup"><span data-stu-id="61636-201">int</span></span> |<span data-ttu-id="61636-202">否</span><span class="sxs-lookup"><span data-stu-id="61636-202">No</span></span> |<span data-ttu-id="61636-203">外键，与 CqdBuildingType 表中的条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="61636-203">Foreign key, matches one of the entries in the CqdBuildingType table.</span></span> |
|<span data-ttu-id="61636-204">Latitude</span><span class="sxs-lookup"><span data-stu-id="61636-204">Latitude</span></span> |<span data-ttu-id="61636-205">float</span><span class="sxs-lookup"><span data-stu-id="61636-205">float</span></span> |<span data-ttu-id="61636-206">是</span><span class="sxs-lookup"><span data-stu-id="61636-206">Yes</span></span> |<span data-ttu-id="61636-207">建筑物的纬度。</span><span class="sxs-lookup"><span data-stu-id="61636-207">Latitude of the building.</span></span> |
|<span data-ttu-id="61636-208">Longitude</span><span class="sxs-lookup"><span data-stu-id="61636-208">Longitude</span></span> |<span data-ttu-id="61636-209">float</span><span class="sxs-lookup"><span data-stu-id="61636-209">float</span></span> |<span data-ttu-id="61636-210">是</span><span class="sxs-lookup"><span data-stu-id="61636-210">Yes</span></span> |<span data-ttu-id="61636-211">大楼的经度。</span><span class="sxs-lookup"><span data-stu-id="61636-211">Longitude of the building.</span></span> |
|<span data-ttu-id="61636-212">CityName</span><span class="sxs-lookup"><span data-stu-id="61636-212">CityName</span></span> |<span data-ttu-id="61636-213">varchar (30) </span><span class="sxs-lookup"><span data-stu-id="61636-213">varchar(30)</span></span> |<span data-ttu-id="61636-214">是</span><span class="sxs-lookup"><span data-stu-id="61636-214">Yes</span></span> |<span data-ttu-id="61636-215">大楼所在的城市名称。</span><span class="sxs-lookup"><span data-stu-id="61636-215">City name where the building is located.</span></span> |
|<span data-ttu-id="61636-216">ZipCode</span><span class="sxs-lookup"><span data-stu-id="61636-216">ZipCode</span></span> |<span data-ttu-id="61636-217">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="61636-217">varchar(25)</span></span> |<span data-ttu-id="61636-218">是</span><span class="sxs-lookup"><span data-stu-id="61636-218">Yes</span></span> |<span data-ttu-id="61636-219">大楼所在的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="61636-219">Zip code where the building is located.</span></span> |
|<span data-ttu-id="61636-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="61636-220">CountryShortCode</span></span> |<span data-ttu-id="61636-221">varchar (2) </span><span class="sxs-lookup"><span data-stu-id="61636-221">varchar(2)</span></span> |<span data-ttu-id="61636-222">是</span><span class="sxs-lookup"><span data-stu-id="61636-222">Yes</span></span> |<span data-ttu-id="61636-223">大楼所在的国家/地区 ISO 3166-1 alpha-2 代码。</span><span class="sxs-lookup"><span data-stu-id="61636-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span> |
|<span data-ttu-id="61636-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="61636-224">StateProvinceCode</span></span> |<span data-ttu-id="61636-225">varchar (3) </span><span class="sxs-lookup"><span data-stu-id="61636-225">varchar(3)</span></span> |<span data-ttu-id="61636-226">是</span><span class="sxs-lookup"><span data-stu-id="61636-226">Yes</span></span> |<span data-ttu-id="61636-227">大楼所在的省/市/市/县的三字母缩写。</span><span class="sxs-lookup"><span data-stu-id="61636-227">Three-letter abbreviation for the State/Province where the building is located.</span></span> |
|<span data-ttu-id="61636-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="61636-228">InsideCorp</span></span> |<span data-ttu-id="61636-229">bit</span><span class="sxs-lookup"><span data-stu-id="61636-229">bit</span></span> |<span data-ttu-id="61636-230">是</span><span class="sxs-lookup"><span data-stu-id="61636-230">Yes</span></span> |<span data-ttu-id="61636-231">位指示大楼是否是企业网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="61636-231">Bit indicates whether the building is part of the corporate network.</span></span> |
|<span data-ttu-id="61636-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="61636-232">BuildingOfficeType</span></span> |<span data-ttu-id="61636-233">nvarchar (150) </span><span class="sxs-lookup"><span data-stu-id="61636-233">nvarchar(150)</span></span> |<span data-ttu-id="61636-234">是</span><span class="sxs-lookup"><span data-stu-id="61636-234">Yes</span></span> |<span data-ttu-id="61636-235">大楼办公类型的说明。</span><span class="sxs-lookup"><span data-stu-id="61636-235">Description of the building office type.</span></span> |
|<span data-ttu-id="61636-236">地区</span><span class="sxs-lookup"><span data-stu-id="61636-236">Region</span></span> |<span data-ttu-id="61636-237">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="61636-237">varchar(25)</span></span> |<span data-ttu-id="61636-238">是</span><span class="sxs-lookup"><span data-stu-id="61636-238">Yes</span></span> |<span data-ttu-id="61636-239">大楼所在的区域。</span><span class="sxs-lookup"><span data-stu-id="61636-239">Region where the building is located.</span></span> |
|||||

<span data-ttu-id="61636-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="61636-240">**CqdNetwork**</span></span>

|<span data-ttu-id="61636-241">列</span><span class="sxs-lookup"><span data-stu-id="61636-241">Column</span></span>|<span data-ttu-id="61636-242">数据类型</span><span class="sxs-lookup"><span data-stu-id="61636-242">Data Type</span></span>|<span data-ttu-id="61636-243">允许 Null？</span><span class="sxs-lookup"><span data-stu-id="61636-243">Allow Nulls?</span></span>|<span data-ttu-id="61636-244">详细信息</span><span class="sxs-lookup"><span data-stu-id="61636-244">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61636-245">Network</span><span class="sxs-lookup"><span data-stu-id="61636-245">Network</span></span> |<span data-ttu-id="61636-246">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="61636-246">varchar(25)</span></span> |<span data-ttu-id="61636-247">否</span><span class="sxs-lookup"><span data-stu-id="61636-247">No</span></span> |<span data-ttu-id="61636-248">子网地址。</span><span class="sxs-lookup"><span data-stu-id="61636-248">Subnet address.</span></span> |
|<span data-ttu-id="61636-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="61636-249">NetworkRange</span></span> |<span data-ttu-id="61636-250">tinyint</span><span class="sxs-lookup"><span data-stu-id="61636-250">tinyint</span></span> |<span data-ttu-id="61636-251">是</span><span class="sxs-lookup"><span data-stu-id="61636-251">Yes</span></span> |<span data-ttu-id="61636-252">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="61636-252">Subnet mask.</span></span> |
|<span data-ttu-id="61636-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="61636-253">NetworkNameID</span></span> |<span data-ttu-id="61636-254">int</span><span class="sxs-lookup"><span data-stu-id="61636-254">int</span></span> |<span data-ttu-id="61636-255">是</span><span class="sxs-lookup"><span data-stu-id="61636-255">Yes</span></span> |<span data-ttu-id="61636-256">（可选）映射到 CqdNetworkName 表中的行。</span><span class="sxs-lookup"><span data-stu-id="61636-256">Optionally maps to a row in CqdNetworkName table.</span></span> |
|<span data-ttu-id="61636-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="61636-257">BuildingKey</span></span> |<span data-ttu-id="61636-258">int</span><span class="sxs-lookup"><span data-stu-id="61636-258">int</span></span> |<span data-ttu-id="61636-259">是</span><span class="sxs-lookup"><span data-stu-id="61636-259">Yes</span></span> |<span data-ttu-id="61636-260">外键，与 CqdBuilding 表中的条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="61636-260">Foreign key, matches one of the entries in the CqdBuilding table.</span></span> |
|<span data-ttu-id="61636-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="61636-261">UpdatedDate</span></span> |<span data-ttu-id="61636-262">datetime</span><span class="sxs-lookup"><span data-stu-id="61636-262">datetime</span></span> |<span data-ttu-id="61636-263">否</span><span class="sxs-lookup"><span data-stu-id="61636-263">No</span></span> |<span data-ttu-id="61636-264">上次更新条目的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="61636-264">Datetime for when the entry was last updated.</span></span> |
||||||

<span data-ttu-id="61636-265">默认情况下，此下一个表具有一 (0，"未知") 。</span><span class="sxs-lookup"><span data-stu-id="61636-265">By default this next table has one entry (0, 'Unknown').</span></span>

<span data-ttu-id="61636-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="61636-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="61636-267">列</span><span class="sxs-lookup"><span data-stu-id="61636-267">Column</span></span>|<span data-ttu-id="61636-268">数据类型</span><span class="sxs-lookup"><span data-stu-id="61636-268">Data Type</span></span>|<span data-ttu-id="61636-269">允许 Null？</span><span class="sxs-lookup"><span data-stu-id="61636-269">Allow Nulls?</span></span>|<span data-ttu-id="61636-270">详细信息</span><span class="sxs-lookup"><span data-stu-id="61636-270">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61636-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="61636-271">BuildingTypeId</span></span> |<span data-ttu-id="61636-272">int</span><span class="sxs-lookup"><span data-stu-id="61636-272">int</span></span> |<span data-ttu-id="61636-273">否</span><span class="sxs-lookup"><span data-stu-id="61636-273">No</span></span> |<span data-ttu-id="61636-274">CqdBuildingType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="61636-274">Primary key for the CqdBuildingType table.</span></span> |
|<span data-ttu-id="61636-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="61636-275">BuildingTypeDesc</span></span> |<span data-ttu-id="61636-276">char (18) </span><span class="sxs-lookup"><span data-stu-id="61636-276">char(18)</span></span> |<span data-ttu-id="61636-277">否</span><span class="sxs-lookup"><span data-stu-id="61636-277">No</span></span> |<span data-ttu-id="61636-278">生成类型说明。</span><span class="sxs-lookup"><span data-stu-id="61636-278">Building type description.</span></span> |
|||||

<span data-ttu-id="61636-279">默认情况下，此下一个表具有一 (0、"Unknown"、0、null) 。</span><span class="sxs-lookup"><span data-stu-id="61636-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="61636-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="61636-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="61636-281">列</span><span class="sxs-lookup"><span data-stu-id="61636-281">Column</span></span>|<span data-ttu-id="61636-282">数据类型</span><span class="sxs-lookup"><span data-stu-id="61636-282">Data Type</span></span>|<span data-ttu-id="61636-283">允许 Null？</span><span class="sxs-lookup"><span data-stu-id="61636-283">Allow Nulls?</span></span>|<span data-ttu-id="61636-284">详细信息</span><span class="sxs-lookup"><span data-stu-id="61636-284">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61636-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="61636-285">OwnershipTypeId</span></span> |<span data-ttu-id="61636-286">int</span><span class="sxs-lookup"><span data-stu-id="61636-286">int</span></span> |<span data-ttu-id="61636-287">否</span><span class="sxs-lookup"><span data-stu-id="61636-287">No</span></span> |<span data-ttu-id="61636-288">CqdBuildingOwnershipType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="61636-288">Primary key for the CqdBuildingOwnershipType table.</span></span> |
|<span data-ttu-id="61636-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="61636-289">OwnershipTypeDesc</span></span> |<span data-ttu-id="61636-290">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="61636-290">varchar(25)</span></span> |<span data-ttu-id="61636-291">否</span><span class="sxs-lookup"><span data-stu-id="61636-291">No</span></span> |<span data-ttu-id="61636-292">所有权类型说明。</span><span class="sxs-lookup"><span data-stu-id="61636-292">Ownership type description.</span></span> |
|<span data-ttu-id="61636-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="61636-293">LeaseInd</span></span> |<span data-ttu-id="61636-294">tinyint</span><span class="sxs-lookup"><span data-stu-id="61636-294">tinyint</span></span> |<span data-ttu-id="61636-295">是</span><span class="sxs-lookup"><span data-stu-id="61636-295">Yes</span></span> |<span data-ttu-id="61636-296">引用 CqdBuildingOwnershipType 表中另一行的索引，用于标识租用的大楼。</span><span class="sxs-lookup"><span data-stu-id="61636-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span> |
|<span data-ttu-id="61636-297">所有者</span><span class="sxs-lookup"><span data-stu-id="61636-297">Owner</span></span> |<span data-ttu-id="61636-298">varchar (50) </span><span class="sxs-lookup"><span data-stu-id="61636-298">varchar(50)</span></span> |<span data-ttu-id="61636-299">是</span><span class="sxs-lookup"><span data-stu-id="61636-299">Yes</span></span> |<span data-ttu-id="61636-300">建筑物所有者。</span><span class="sxs-lookup"><span data-stu-id="61636-300">Building owner.</span></span> |
|||||

<span data-ttu-id="61636-301">默认情况下，此下一个表具有一 (0、"Unknown"、0、null) 。</span><span class="sxs-lookup"><span data-stu-id="61636-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="61636-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="61636-302">**CqdBssid**</span></span>

|<span data-ttu-id="61636-303">列</span><span class="sxs-lookup"><span data-stu-id="61636-303">Column</span></span>|<span data-ttu-id="61636-304">数据类型</span><span class="sxs-lookup"><span data-stu-id="61636-304">Data Type</span></span>|<span data-ttu-id="61636-305">允许 Null？</span><span class="sxs-lookup"><span data-stu-id="61636-305">Allow Nulls?</span></span>|<span data-ttu-id="61636-306">详细信息</span><span class="sxs-lookup"><span data-stu-id="61636-306">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61636-307">bss</span><span class="sxs-lookup"><span data-stu-id="61636-307">bss</span></span> |<span data-ttu-id="61636-308">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="61636-308">nvarchar(50)</span></span> |<span data-ttu-id="61636-309">否</span><span class="sxs-lookup"><span data-stu-id="61636-309">No</span></span> |<span data-ttu-id="61636-310">CqdBssid 表的主键。</span><span class="sxs-lookup"><span data-stu-id="61636-310">Primary key for the CqdBssid table.</span></span> <span data-ttu-id="61636-311">是 WiFi 接入点的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="61636-311">Is the BSSID of the WiFi Access Point.</span></span> |
|<span data-ttu-id="61636-312">ess</span><span class="sxs-lookup"><span data-stu-id="61636-312">ess</span></span> |<span data-ttu-id="61636-313">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="61636-313">nvarchar(50)</span></span> |<span data-ttu-id="61636-314">是</span><span class="sxs-lookup"><span data-stu-id="61636-314">Yes</span></span> |<span data-ttu-id="61636-315">Wifi 接入点控制器信息。</span><span class="sxs-lookup"><span data-stu-id="61636-315">Wifi Access Point Controller information.</span></span> |
|<span data-ttu-id="61636-316">phy</span><span class="sxs-lookup"><span data-stu-id="61636-316">phy</span></span> |<span data-ttu-id="61636-317">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="61636-317">nvarchar(50)</span></span> |<span data-ttu-id="61636-318">是</span><span class="sxs-lookup"><span data-stu-id="61636-318">Yes</span></span> |<span data-ttu-id="61636-319">Phy 信息。</span><span class="sxs-lookup"><span data-stu-id="61636-319">Phy information.</span></span> |
|<span data-ttu-id="61636-320">ap</span><span class="sxs-lookup"><span data-stu-id="61636-320">ap</span></span> |<span data-ttu-id="61636-321">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="61636-321">nvarchar(50)</span></span> |<span data-ttu-id="61636-322">是</span><span class="sxs-lookup"><span data-stu-id="61636-322">Yes</span></span> |<span data-ttu-id="61636-323">Wifi 接入点名称。</span><span class="sxs-lookup"><span data-stu-id="61636-323">Wifi Access Point Name.</span></span> |
|<span data-ttu-id="61636-324">生成</span><span class="sxs-lookup"><span data-stu-id="61636-324">Building</span></span> |<span data-ttu-id="61636-325">nvarchar (500) </span><span class="sxs-lookup"><span data-stu-id="61636-325">nvarchar(500)</span></span> |<span data-ttu-id="61636-326">是</span><span class="sxs-lookup"><span data-stu-id="61636-326">Yes</span></span> |<span data-ttu-id="61636-327">WiFi 接入点所在的建筑物名称。</span><span class="sxs-lookup"><span data-stu-id="61636-327">The Building Name the WiFi Access Point is located in.</span></span> |
||||

## <a name="cqd-streams"></a><span data-ttu-id="61636-328">CQD 流</span><span class="sxs-lookup"><span data-stu-id="61636-328">CQD Streams</span></span>

<span data-ttu-id="61636-329">CQD 流被视为良好、差或未经分类。</span><span class="sxs-lookup"><span data-stu-id="61636-329">A CQD stream is considered good, poor, or unclassified.</span></span> <span data-ttu-id="61636-330">CQM 1.5 现在使用以下 CQD 定义：</span><span class="sxs-lookup"><span data-stu-id="61636-330">CQM 1.5 now uses the following CQD definition:</span></span>

- <span data-ttu-id="61636-331">质量欠佳的流是超出阈值的较差呼叫指标的任意组合。</span><span class="sxs-lookup"><span data-stu-id="61636-331">A poor stream is any combination of the poor call metrics beyond threshold.</span></span>
- <span data-ttu-id="61636-332">当呼叫中的一个流较差时，呼叫的两个流都标记为差。</span><span class="sxs-lookup"><span data-stu-id="61636-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="61636-333">在会议中，每个参与者都计为唯一呼叫，并独立于所有其他参与者进行报告。</span><span class="sxs-lookup"><span data-stu-id="61636-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
- <span data-ttu-id="61636-334">未分类流是无质量指标的流 (即综合事务或短时间) 。</span><span class="sxs-lookup"><span data-stu-id="61636-334">Unclassified streams are streams without quality metrics (that is, Synthetic Transactions or short calls).</span></span>
- <span data-ttu-id="61636-335">有效流 = 非移动客户端</span><span class="sxs-lookup"><span data-stu-id="61636-335">Valid Streams = non-mobile clients</span></span>
- <span data-ttu-id="61636-336">无法修改分类器</span><span class="sxs-lookup"><span data-stu-id="61636-336">Classifier cannot be modified</span></span>

<span data-ttu-id="61636-337">**较差的呼叫定义/分类器**</span><span class="sxs-lookup"><span data-stu-id="61636-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="61636-338">跃点数</span><span class="sxs-lookup"><span data-stu-id="61636-338">Metric</span></span>|<span data-ttu-id="61636-339">阈值</span><span class="sxs-lookup"><span data-stu-id="61636-339">Threshold</span></span>|
|:-----|:-----|
|<span data-ttu-id="61636-340">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="61636-340">DegradationAvg</span></span> |<span data-ttu-id="61636-341">大于 1.0 (-1 网络 MOS) </span><span class="sxs-lookup"><span data-stu-id="61636-341">Greater than 1.0 (-1 network MOS)</span></span> |
|<span data-ttu-id="61636-342">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="61636-342">RoundTrip</span></span> |<span data-ttu-id="61636-343">大于 500</span><span class="sxs-lookup"><span data-stu-id="61636-343">Greater than 500</span></span> |
|<span data-ttu-id="61636-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="61636-344">PacketLossRate</span></span> |<span data-ttu-id="61636-345">大于 0.1 (10%) </span><span class="sxs-lookup"><span data-stu-id="61636-345">Greater than 0.1 (10%)</span></span> |
|<span data-ttu-id="61636-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="61636-346">JitterInterArrival</span></span> |<span data-ttu-id="61636-347">大于 30</span><span class="sxs-lookup"><span data-stu-id="61636-347">Greater than 30</span></span> |
|<span data-ttu-id="61636-348">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="61636-348">RatioConcealedSamplesAvg</span></span> |<span data-ttu-id="61636-349">大于 0.07</span><span class="sxs-lookup"><span data-stu-id="61636-349">Greater than 0.07</span></span> |
|||

<span data-ttu-id="61636-350">JPDR 定义 = 质量欠佳的呼叫定义减去 RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="61636-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span>

## <a name="where-is-callercallee"></a><span data-ttu-id="61636-351">呼叫者/被叫方在哪里？</span><span class="sxs-lookup"><span data-stu-id="61636-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="61636-352">CQD 不使用呼叫方/被叫方字段，而是使用"First"和"Second"，因为呼叫者与被叫方之间存在干预步骤。</span><span class="sxs-lookup"><span data-stu-id="61636-352">CQD doesn't use Caller/Callee fields, instead it uses "First" and "Second" because there are intervening steps between the caller and callee.</span></span>

 <span data-ttu-id="61636-353">**First** 始终为服务器终结点 (例如，AV MCU 或中介服务器) （如果流中涉及服务器）。</span><span class="sxs-lookup"><span data-stu-id="61636-353">**First** Will always be the Server endpoint (for example, AV MCU or Mediation Server) if a Server is involved in the stream.</span></span>

 <span data-ttu-id="61636-354">**Second** 始终为客户端终结点，除非它是一个Server-Server流。</span><span class="sxs-lookup"><span data-stu-id="61636-354">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>

<span data-ttu-id="61636-355">**第一和第二分类的示例**</span><span class="sxs-lookup"><span data-stu-id="61636-355">**Example of First and Second classification**</span></span>

|<span data-ttu-id="61636-356">终结点 1 UAType</span><span class="sxs-lookup"><span data-stu-id="61636-356">Endpoint 1 UAType</span></span>|<span data-ttu-id="61636-357">终结点 2 UUAType</span><span class="sxs-lookup"><span data-stu-id="61636-357">Endpoint 2 UUAType</span></span>|<span data-ttu-id="61636-358">First</span><span class="sxs-lookup"><span data-stu-id="61636-358">First</span></span>|<span data-ttu-id="61636-359">秒</span><span class="sxs-lookup"><span data-stu-id="61636-359">Second</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61636-360">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="61636-360">2 (AVMCU)</span></span> |<span data-ttu-id="61636-361">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="61636-361">4 (Skype for Business)</span></span> |<span data-ttu-id="61636-362">终结点 1</span><span class="sxs-lookup"><span data-stu-id="61636-362">Endpoint 1</span></span> |<span data-ttu-id="61636-363">终结点 2</span><span class="sxs-lookup"><span data-stu-id="61636-363">Endpoint 2</span></span> |
|<span data-ttu-id="61636-364">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="61636-364">2 (AVMCU)</span></span> |<span data-ttu-id="61636-365">1 (mMediationServer) </span><span class="sxs-lookup"><span data-stu-id="61636-365">1 (mMediationServer)</span></span> |<span data-ttu-id="61636-366">终结点 2</span><span class="sxs-lookup"><span data-stu-id="61636-366">Endpoint 2</span></span> |<span data-ttu-id="61636-367">终结点 1</span><span class="sxs-lookup"><span data-stu-id="61636-367">Endpoint 1</span></span> |
|<span data-ttu-id="61636-368">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="61636-368">4 (Skype for Business)</span></span> |<span data-ttu-id="61636-369">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="61636-369">4 (Skype for Business)</span></span> |<span data-ttu-id="61636-370">MediaLine 中的呼叫者</span><span class="sxs-lookup"><span data-stu-id="61636-370">The Caller in MediaLine</span></span> |<span data-ttu-id="61636-371">MMediaLine 中的被叫方</span><span class="sxs-lookup"><span data-stu-id="61636-371">The Callee in MMediaLine</span></span> |
|||||

<span data-ttu-id="61636-372">如果两个终结点的类型相同，则 CQD 将呼叫者条目"第一"和"被叫方第二"。</span><span class="sxs-lookup"><span data-stu-id="61636-372">If both endpoints are the same type, CQD makes the Caller entry First and the Callee Second.</span></span> <span data-ttu-id="61636-373">有关终结点名称详细信息，请参阅 [此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。</span><span class="sxs-lookup"><span data-stu-id="61636-373">For more information about endpoint names, see [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).</span></span>

## <a name="accounting-for-vpn"></a><span data-ttu-id="61636-374">VPN 会计</span><span class="sxs-lookup"><span data-stu-id="61636-374">Accounting for VPN</span></span>

<span data-ttu-id="61636-375">如果已知 VPN 解决方案能够准确设置 VPN 标志，则你已全部设置。</span><span class="sxs-lookup"><span data-stu-id="61636-375">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="61636-376">否则，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="61636-376">Otherwise, use one of the following methods:</span></span>

- <span data-ttu-id="61636-377">创建名为 VPN 的网络类型 (首选) ，然后将 VPN 子网与这个新 VPN NetworkType 关联。</span><span class="sxs-lookup"><span data-stu-id="61636-377">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
- <span data-ttu-id="61636-378">创建一个称为 VPN 的建筑物，然后将 VPN 子网与该建筑物关联。</span><span class="sxs-lookup"><span data-stu-id="61636-378">Create a building called VPN, then Associate VPN Subnets with this building.</span></span>

## <a name="query-fundamentals"></a><span data-ttu-id="61636-379">查询基础</span><span class="sxs-lookup"><span data-stu-id="61636-379">Query Fundamentals</span></span>

<span data-ttu-id="61636-380">格式良好的查询包含以下三个参数：</span><span class="sxs-lookup"><span data-stu-id="61636-380">A well-formed query contains all three of these parameters:</span></span>

- <span data-ttu-id="61636-381">度量</span><span class="sxs-lookup"><span data-stu-id="61636-381">Measurement</span></span>
- <span data-ttu-id="61636-382">Dimension</span><span class="sxs-lookup"><span data-stu-id="61636-382">Dimension</span></span>
- <span data-ttu-id="61636-383">筛选</span><span class="sxs-lookup"><span data-stu-id="61636-383">Filter</span></span>

<span data-ttu-id="61636-384">格式良好的查询示例为"按子网 [Dimension] 显示差流 [度量] 生成 6 [筛选器]。"</span><span class="sxs-lookup"><span data-stu-id="61636-384">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

## <a name="what-does-union-do"></a><span data-ttu-id="61636-385">UNION 有什么功能？</span><span class="sxs-lookup"><span data-stu-id="61636-385">What does UNION do?</span></span>

<span data-ttu-id="61636-386">Union 允许您使用 AND 运算符筛选条件。</span><span class="sxs-lookup"><span data-stu-id="61636-386">Union allows you to filter conditions with the AND operator.</span></span> <span data-ttu-id="61636-387">在某些情况下，可以将多个 Filter 条件组合在一起，以实现类似于 OR 操作的结果。</span><span class="sxs-lookup"><span data-stu-id="61636-387">There are scenarios where you can combine multiple Filter conditions together to achieve a result similar to an OR operation.</span></span>

<span data-ttu-id="61636-388">示例：为了从建筑物获取所有流，UNION 提供了合并数据集的一个独特视图。</span><span class="sxs-lookup"><span data-stu-id="61636-388">Example: To get all streams from a building, UNION provides a distinct view of the merged dataset.</span></span> <span data-ttu-id="61636-389">若要使用 UNION，请将常见文本插入到要联合的两个筛选条件的 UNION 字段中。</span><span class="sxs-lookup"><span data-stu-id="61636-389">To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span>

## <a name="default-report-breakdown"></a><span data-ttu-id="61636-390">默认报告细分</span><span class="sxs-lookup"><span data-stu-id="61636-390">Default Report Breakdown</span></span>

<span data-ttu-id="61636-391">如果无线在内部管理，可以在托管存储桶中重新创建无线报告。</span><span class="sxs-lookup"><span data-stu-id="61636-391">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span>

![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a><span data-ttu-id="61636-393">运营流程</span><span class="sxs-lookup"><span data-stu-id="61636-393">Operational Processes</span></span>

<span data-ttu-id="61636-394">首先查看并修正托管流。</span><span class="sxs-lookup"><span data-stu-id="61636-394">Review and remediate Managed Streams first.</span></span> <span data-ttu-id="61636-395">此区域中的质量应 100% 在你的控制范围内，因此最易于修正。</span><span class="sxs-lookup"><span data-stu-id="61636-395">Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span>

### <a name="managed-streams"></a><span data-ttu-id="61636-396">托管流</span><span class="sxs-lookup"><span data-stu-id="61636-396">Managed Streams</span></span>

<span data-ttu-id="61636-397">按以下顺序查看和修正托管流：</span><span class="sxs-lookup"><span data-stu-id="61636-397">Review and remediate managed streams in the following order:</span></span>

1. <span data-ttu-id="61636-398">Server-Server</span><span class="sxs-lookup"><span data-stu-id="61636-398">Server-Server</span></span>
2. <span data-ttu-id="61636-399">Server-Wired-Inside</span><span class="sxs-lookup"><span data-stu-id="61636-399">Server-Wired-Inside</span></span>
3. <span data-ttu-id="61636-400">有线-有线-内部</span><span class="sxs-lookup"><span data-stu-id="61636-400">Wired-Wired-Inside</span></span>

### <a name="unmanaged-streams"></a><span data-ttu-id="61636-401">非托管流</span><span class="sxs-lookup"><span data-stu-id="61636-401">Unmanaged Streams</span></span>

<span data-ttu-id="61636-402">按以下顺序查看和修正非托管流：</span><span class="sxs-lookup"><span data-stu-id="61636-402">Review and remediate unmanaged streams in the following order:</span></span>

1. <span data-ttu-id="61636-403">Server-Wifi-Inside</span><span class="sxs-lookup"><span data-stu-id="61636-403">Server-Wifi-Inside</span></span>
2. <span data-ttu-id="61636-404">Server-Wired-Outside</span><span class="sxs-lookup"><span data-stu-id="61636-404">Server-Wired-Outside</span></span>
3. <span data-ttu-id="61636-405">Server-Wifi-Outside</span><span class="sxs-lookup"><span data-stu-id="61636-405">Server-Wifi-Outside</span></span>
4. <span data-ttu-id="61636-406">有线-外部-直接</span><span class="sxs-lookup"><span data-stu-id="61636-406">Wired-Outside-Direct</span></span>
5. <span data-ttu-id="61636-407">有线-外中继</span><span class="sxs-lookup"><span data-stu-id="61636-407">Wired-Outside-Relay</span></span>
6. <span data-ttu-id="61636-408">其他非托管</span><span class="sxs-lookup"><span data-stu-id="61636-408">Other Unmanaged</span></span>
