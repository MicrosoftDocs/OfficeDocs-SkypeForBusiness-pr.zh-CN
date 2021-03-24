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
description: 摘要：了解如何使用呼叫质量仪表板。 呼叫质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: d4787671955159d2bef0144872c50caccbbbb8eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098958"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="81a9e-104">使用 Skype for Business Server 的呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="81a9e-104">Use Call Quality Dashboard for Skype for Business Server</span></span>

<span data-ttu-id="81a9e-105">**摘要：** 了解如何使用呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="81a9e-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="81a9e-106">呼叫质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="81a9e-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="81a9e-107">呼叫质量仪表板 (CQD) 使 IT 专业人员可以使用聚合数据，通过比较用户组的统计信息来确定趋势和模式，从而发现产生媒体质量问题的问题。</span><span class="sxs-lookup"><span data-stu-id="81a9e-107">Call Quality Dashboard (CQD) allows IT Pros to use aggregate data to identify problems creating media quality issues by  comparing statistics for groups of users to identify trends and patterns.</span></span> <span data-ttu-id="81a9e-108">CQD 并非专注于解决单个呼叫问题，而是侧重于识别适用于许多用户的问题和解决方案。</span><span class="sxs-lookup"><span data-stu-id="81a9e-108">CQD is not focused on solving individual call issues, but on identifying problems and solutions that apply to many users.</span></span>

## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="81a9e-109">呼叫质量仪表板用户指南</span><span class="sxs-lookup"><span data-stu-id="81a9e-109">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="81a9e-110">CQD 是一个 Web 门户， (用于根据用户体验质量或 QoE) 数据快速创建和组织报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-110">CQD is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data.</span></span> <span data-ttu-id="81a9e-111">CQD 部署 SSAS 多维数据集以聚合 QoE 指标数据库中的数据，使管理员能够创建和修改报告或实时进行调查。</span><span class="sxs-lookup"><span data-stu-id="81a9e-111">CQD deploys an SSAS cube to aggregate the data in the QoE Metrics database, and enables admins to create and modify reports or do investigations in real time.</span></span> <span data-ttu-id="81a9e-112">虽然可以使用 Excel 直接连接到多维数据集，但门户针对涉及 QoE 数据的多个工作流进行了优化。</span><span class="sxs-lookup"><span data-stu-id="81a9e-112">While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data.</span></span> <span data-ttu-id="81a9e-113">数据包括：</span><span class="sxs-lookup"><span data-stu-id="81a9e-113">The data includes:</span></span>

- <span data-ttu-id="81a9e-114">用于快速访问的缓存报表数据</span><span class="sxs-lookup"><span data-stu-id="81a9e-114">Cached report data for fast access</span></span>
- <span data-ttu-id="81a9e-115">用于信息共享和发布的报告页面的深层链接</span><span class="sxs-lookup"><span data-stu-id="81a9e-115">Deep links to report pages for information sharing and publishing</span></span>
- <span data-ttu-id="81a9e-116">简化了报告编辑和创建，以及报表说明的可编辑元数据。</span><span class="sxs-lookup"><span data-stu-id="81a9e-116">Streamlined report editing and creation, and editable metadata for report descriptions.</span></span>

<span data-ttu-id="81a9e-117">此外，CQD 还公开 Web API，这些 API 允许用户以编程方式访问多维数据集数据以在自定义仪表板中使用。</span><span class="sxs-lookup"><span data-stu-id="81a9e-117">Also, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>

### <a name="feature-overview"></a><span data-ttu-id="81a9e-118">功能概述</span><span class="sxs-lookup"><span data-stu-id="81a9e-118">Feature Overview</span></span>

<span data-ttu-id="81a9e-119">当您访问呼叫质量仪表板时，将看到以下屏幕：</span><span class="sxs-lookup"><span data-stu-id="81a9e-119">When you visit the Call Quality Dashboard, you see the following screen:</span></span>

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. <span data-ttu-id="81a9e-121">"摘要窗格"是位于右侧"报告集" (的上下文) 位置。</span><span class="sxs-lookup"><span data-stu-id="81a9e-121">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span>
2. <span data-ttu-id="81a9e-122">单击摘要窗格报表中的"编辑"以设置级别属性 (包括 Y 轴高度) 。</span><span class="sxs-lookup"><span data-stu-id="81a9e-122">Click "Edit" in the Summary PaneReport to set level properties (including Y-axis height).</span></span>
3. <span data-ttu-id="81a9e-123">痕迹导航可帮助您标识报表集层次结构中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="81a9e-123">The Breadcrumb helps you identify your current location within the report set hierarchy.</span></span>
4. <span data-ttu-id="81a9e-124">包含子报表的报告将显示为蓝色链接。</span><span class="sxs-lookup"><span data-stu-id="81a9e-124">Reports with subreports are shown with a blue link.</span></span> <span data-ttu-id="81a9e-125">单击链接可向下钻取到子报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-125">Click the link to drill down to the child reports.</span></span>

<span data-ttu-id="81a9e-126">将鼠标移动到条形图和趋势线上以显示详细值。</span><span class="sxs-lookup"><span data-stu-id="81a9e-126">Move the mouse over the bar charts and trend lines to show detailed values.</span></span> <span data-ttu-id="81a9e-127">具有焦点的报告显示操作菜单："编辑"、"克隆"、"删除"和"下载"。</span><span class="sxs-lookup"><span data-stu-id="81a9e-127">The report that has focus shows the action menu: "Edit", "Clone", "Delete", and "Download".</span></span>

### <a name="default-reports"></a><span data-ttu-id="81a9e-128">默认报告</span><span class="sxs-lookup"><span data-stu-id="81a9e-128">Default Reports</span></span>

<span data-ttu-id="81a9e-129">首次访问呼叫质量仪表板门户时，将自动创建一组默认报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-129">When you first access the Call Quality Dashboard portal, a default set of reports is automatically created.</span></span> <span data-ttu-id="81a9e-130">这些报告有时称为系统报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-130">These reports are sometimes referred to as system reports.</span></span> <span data-ttu-id="81a9e-131">您可以自由修改或删除这些报告，或者通过创建新的同级和子报告来扩展它们。</span><span class="sxs-lookup"><span data-stu-id="81a9e-131">You are able to freely modify or delete these reports or extend them by creating new sibling and child reports.</span></span>

<span data-ttu-id="81a9e-132">在顶层，"音频流每月趋势"报告显示所有音频流的每月趋势。</span><span class="sxs-lookup"><span data-stu-id="81a9e-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="81a9e-133">将鼠标移动到条形图中的条形图上，以显示条形图所代表的数据的更详细的视图。</span><span class="sxs-lookup"><span data-stu-id="81a9e-133">Move the mouse over the bars in a bar chart to show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="81a9e-134">单击"音频流每月趋势"报告的标题以导航到"托管音频流与非托管音频流"报告，其中报告在托管呼叫和非托管呼叫之间拆分。</span><span class="sxs-lookup"><span data-stu-id="81a9e-134">Click the title of the Audio Streams Monthly Trend report to navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="81a9e-135">托管呼叫是在公司防火墙内通过有线连接拨打的呼叫。</span><span class="sxs-lookup"><span data-stu-id="81a9e-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="81a9e-136">非托管呼叫包括从公司防火墙外拨打的呼叫，以及通过 WI-Fi 进行的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="81a9e-136">Unmanaged calls include calls made from outside the corporate firewall and all calls made over Wi-Fi.</span></span>

<span data-ttu-id="81a9e-137">另一个顶级报告称为"用户报告的呼叫质量分级直方图"。</span><span class="sxs-lookup"><span data-stu-id="81a9e-137">The other top-level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="81a9e-138">通话质量评级是 Skype for Business 用户在呼叫结束时提供的数字，用于指示呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="81a9e-138">Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="81a9e-139">评分数字范围为 1 到 5，1 表示最差，5 表示最佳。</span><span class="sxs-lookup"><span data-stu-id="81a9e-139">The rating numbers range from 1 to 5, 1 is the worst and 5 is the best.</span></span> <span data-ttu-id="81a9e-140">直方图显示一个月内评级为指示的音频呼叫数。</span><span class="sxs-lookup"><span data-stu-id="81a9e-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span>

<span data-ttu-id="81a9e-141">单击任何报告的标题以导航到具有更多数据筛选器的报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-141">Click the title of any of the reports to navigate into reports with more filters on the data.</span></span> <span data-ttu-id="81a9e-142">在系统报告中，每个子报告都显示其父报告中可用数据的子集。</span><span class="sxs-lookup"><span data-stu-id="81a9e-142">In the system reports, each child report displays a subset of the data available in its parent report.</span></span> <span data-ttu-id="81a9e-143">问题解决模型很简单：调查将问题限制到的数据或趋势的子报告，并逐渐缩小问题空间。</span><span class="sxs-lookup"><span data-stu-id="81a9e-143">The problem-solving model is simple: investigate which subreport the data or trend suggesting a problem is confined to, and gradually narrow down the problem space.</span></span> <span data-ttu-id="81a9e-144">创建子报表的能力允许您调查自己对特定数据趋势的原因的猜测。</span><span class="sxs-lookup"><span data-stu-id="81a9e-144">The ability to create subreports allows you to investigate your own guesses about the cause of specific data trends.</span></span>

### <a name="create-and-edit-reports"></a><span data-ttu-id="81a9e-145">创建和编辑报告</span><span class="sxs-lookup"><span data-stu-id="81a9e-145">Create and Edit Reports</span></span>

<span data-ttu-id="81a9e-146">单击报表的操作菜单中的"编辑"以查看报告编辑器。</span><span class="sxs-lookup"><span data-stu-id="81a9e-146">Click "Edit" in the action menu of a report to see the Report Editor.</span></span> <span data-ttu-id="81a9e-147">每个报表都由多维数据集中的查询进行备份。</span><span class="sxs-lookup"><span data-stu-id="81a9e-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="81a9e-148">报表是查询返回的数据的可视化。</span><span class="sxs-lookup"><span data-stu-id="81a9e-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="81a9e-149">报表编辑器可帮助您编辑这些查询和报表的显示选项。</span><span class="sxs-lookup"><span data-stu-id="81a9e-149">The Report Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="81a9e-150">打开报告编辑器时，可以看到：</span><span class="sxs-lookup"><span data-stu-id="81a9e-150">When you open the Report Editor, you  see:</span></span>

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="81a9e-152">在左窗格中选择维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="81a9e-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="81a9e-153">将鼠标悬停在其中一个现有值上可显示允许删除该值的"x"按钮。</span><span class="sxs-lookup"><span data-stu-id="81a9e-153">Hover over one of the existing values to show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="81a9e-154">单击标题旁边的"加号"按钮，打开可在其中添加新维度、度量或筛选器的对话框。</span><span class="sxs-lookup"><span data-stu-id="81a9e-154">Click the "plus" button next to a heading to open the dialog where you can add a new dimension, measure, or filter.</span></span>
2. <span data-ttu-id="81a9e-155">图表自定义选项显示在顶部。</span><span class="sxs-lookup"><span data-stu-id="81a9e-155">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="81a9e-156">报告编辑器中提供了报告预览。</span><span class="sxs-lookup"><span data-stu-id="81a9e-156">A preview of the report is available in the Report Editor.</span></span>
4. <span data-ttu-id="81a9e-157">可以使用底部的编辑框创建详细的报告说明。</span><span class="sxs-lookup"><span data-stu-id="81a9e-157">A detailed report description can be created with the edit box at the bottom.</span></span>

### <a name="sparklines-in-tables"></a><span data-ttu-id="81a9e-158">表中的迷你图</span><span class="sxs-lookup"><span data-stu-id="81a9e-158">Sparklines in Tables</span></span>

<span data-ttu-id="81a9e-159">将 StartDate.Month 添加为维度并且数据以表格形式呈现为趋势时，条形图和迷你图可以在表格单元格内显示。</span><span class="sxs-lookup"><span data-stu-id="81a9e-159">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells.</span></span> <span data-ttu-id="81a9e-160">将鼠标指针移到条形图和迷你图上，以显示单个月份的值。</span><span class="sxs-lookup"><span data-stu-id="81a9e-160">Move the mouse pointer over the bar chart and the sparklines to show the values for individual months.</span></span>

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

<span data-ttu-id="81a9e-162">为了显示条形图和迷你图，必须选中报表编辑器顶部的"显示迷你图"复选框。</span><span class="sxs-lookup"><span data-stu-id="81a9e-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="81a9e-163">这将选择"趋势"选项，将"月"向下移动为最后一个维度，这也可通过单击"月"，然后使用向上和向下箭头向上或向下移动 StartDate.Month 来完成。</span><span class="sxs-lookup"><span data-stu-id="81a9e-163">This selects the Trend option and moves Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span>

### <a name="settings"></a><span data-ttu-id="81a9e-164">设置</span><span class="sxs-lookup"><span data-stu-id="81a9e-164">Settings</span></span>

<span data-ttu-id="81a9e-165">"设置"菜单包含指向有用页面（如"系统运行状况"和"关于"页面）的链接，位于仪表板的右上角。</span><span class="sxs-lookup"><span data-stu-id="81a9e-165">The settings menu contains links to useful pages like the System Health and About pages, and is located in the top-right corner of the dashboard.</span></span>

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

<span data-ttu-id="81a9e-167">是否显示说明和时间戳由单个用户决定，并且这些设置仅影响个人版本的仪表板，并且不会修改报告集或其他用户看到的信息。</span><span class="sxs-lookup"><span data-stu-id="81a9e-167">Whether to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, and do not modify the report set or what other users see.</span></span> <span data-ttu-id="81a9e-168">清除缓存会导致所有查询从多维数据集重新加载其数据，而还原默认值会删除用户创建或修改的所有报告，并重新创建系统报告集 - 用户首次登录时会看到的内容。</span><span class="sxs-lookup"><span data-stu-id="81a9e-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when they log in for the first time.</span></span>

<span data-ttu-id="81a9e-169">用户仪表板链接显示一个页面，用户可以在此页面查看 CQD 的其他用户并浏览他们的报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="81a9e-170">若要共享报告集，请复制 URL 栏中的链接，并与另一个 CQD 用户共享它。</span><span class="sxs-lookup"><span data-stu-id="81a9e-170">To share a report set, copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="81a9e-171">此链接是其他用户在用户用户名下的"用户仪表板链接"页面中看到的相同链接。</span><span class="sxs-lookup"><span data-stu-id="81a9e-171">This link is the same link other users would see in the Users Dashboard Link page under the user's username.</span></span>

### <a name="supplying-subnet-information"></a><span data-ttu-id="81a9e-172">提供子网信息</span><span class="sxs-lookup"><span data-stu-id="81a9e-172">Supplying Subnet Information</span></span>

<span data-ttu-id="81a9e-173">如果将特定于站点的信息输入到存档数据库中以提供子网到建筑物的映射信息 (例如，通过构建网络网络来提供有线/无线呼叫质量) 。</span><span class="sxs-lookup"><span data-stu-id="81a9e-173">Additional information can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (for example, wired/wireless call quality by building).</span></span>

<span data-ttu-id="81a9e-174">至少应填写下表以创建这些报告：</span><span class="sxs-lookup"><span data-stu-id="81a9e-174">At a minimum, complete the following tables to create these reports:</span></span>

- <span data-ttu-id="81a9e-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="81a9e-175">CqdBuilding</span></span>
- <span data-ttu-id="81a9e-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="81a9e-176">CqdNetwork</span></span>

<span data-ttu-id="81a9e-177">可以在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息，以允许进一步筛选和向下钻取。</span><span class="sxs-lookup"><span data-stu-id="81a9e-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span>

<span data-ttu-id="81a9e-178">用于这些表的数据定义如下：</span><span class="sxs-lookup"><span data-stu-id="81a9e-178">The data used for these tables are defined as follows:</span></span>

<span data-ttu-id="81a9e-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="81a9e-179">**CqdBuilding**</span></span>

|<span data-ttu-id="81a9e-180">Column</span><span class="sxs-lookup"><span data-stu-id="81a9e-180">Column</span></span>|<span data-ttu-id="81a9e-181">数据类型</span><span class="sxs-lookup"><span data-stu-id="81a9e-181">Data Type</span></span>|<span data-ttu-id="81a9e-182">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="81a9e-182">Allow Nulls?</span></span>|<span data-ttu-id="81a9e-183">详细信息</span><span class="sxs-lookup"><span data-stu-id="81a9e-183">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a9e-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="81a9e-184">BuildingKey</span></span> |<span data-ttu-id="81a9e-185">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-185">int</span></span> |<span data-ttu-id="81a9e-186">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-186">No</span></span> |<span data-ttu-id="81a9e-187">CqdBuilding 表的主键。</span><span class="sxs-lookup"><span data-stu-id="81a9e-187">Primary key for the CqdBuilding table.</span></span> |
|<span data-ttu-id="81a9e-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="81a9e-188">BuildingName</span></span> |<span data-ttu-id="81a9e-189">varchar (80) </span><span class="sxs-lookup"><span data-stu-id="81a9e-189">varchar(80)</span></span> |<span data-ttu-id="81a9e-190">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-190">No</span></span> |<span data-ttu-id="81a9e-191">大楼名称。</span><span class="sxs-lookup"><span data-stu-id="81a9e-191">Building name.</span></span> |
|<span data-ttu-id="81a9e-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="81a9e-192">BuildingShortName</span></span> |<span data-ttu-id="81a9e-193">varchar (10) </span><span class="sxs-lookup"><span data-stu-id="81a9e-193">varchar(10)</span></span> |<span data-ttu-id="81a9e-194">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-194">No</span></span> |<span data-ttu-id="81a9e-195">生成名称的更短版本。</span><span class="sxs-lookup"><span data-stu-id="81a9e-195">Shorter version of the Building name.</span></span> |
|<span data-ttu-id="81a9e-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="81a9e-196">OwnershipTypeId</span></span> |<span data-ttu-id="81a9e-197">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-197">int</span></span> |<span data-ttu-id="81a9e-198">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-198">No</span></span> |<span data-ttu-id="81a9e-199">外键，与 CqdBuildingOwners 表中的条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="81a9e-199">Foreign key, matches one of the entries in the CqdBuildingOwners table.</span></span> |
|<span data-ttu-id="81a9e-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="81a9e-200">BuildingTypeId</span></span> |<span data-ttu-id="81a9e-201">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-201">int</span></span> |<span data-ttu-id="81a9e-202">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-202">No</span></span> |<span data-ttu-id="81a9e-203">外键，与 CqdBuildingType 表中的条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="81a9e-203">Foreign key, matches one of the entries in the CqdBuildingType table.</span></span> |
|<span data-ttu-id="81a9e-204">Latitude</span><span class="sxs-lookup"><span data-stu-id="81a9e-204">Latitude</span></span> |<span data-ttu-id="81a9e-205">float</span><span class="sxs-lookup"><span data-stu-id="81a9e-205">float</span></span> |<span data-ttu-id="81a9e-206">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-206">Yes</span></span> |<span data-ttu-id="81a9e-207">大楼的纬度。</span><span class="sxs-lookup"><span data-stu-id="81a9e-207">Latitude of the building.</span></span> |
|<span data-ttu-id="81a9e-208">Longitude</span><span class="sxs-lookup"><span data-stu-id="81a9e-208">Longitude</span></span> |<span data-ttu-id="81a9e-209">float</span><span class="sxs-lookup"><span data-stu-id="81a9e-209">float</span></span> |<span data-ttu-id="81a9e-210">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-210">Yes</span></span> |<span data-ttu-id="81a9e-211">大楼的经度。</span><span class="sxs-lookup"><span data-stu-id="81a9e-211">Longitude of the building.</span></span> |
|<span data-ttu-id="81a9e-212">CityName</span><span class="sxs-lookup"><span data-stu-id="81a9e-212">CityName</span></span> |<span data-ttu-id="81a9e-213">varchar (30) </span><span class="sxs-lookup"><span data-stu-id="81a9e-213">varchar(30)</span></span> |<span data-ttu-id="81a9e-214">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-214">Yes</span></span> |<span data-ttu-id="81a9e-215">大楼所在的城市名称。</span><span class="sxs-lookup"><span data-stu-id="81a9e-215">City name where the building is located.</span></span> |
|<span data-ttu-id="81a9e-216">ZipCode</span><span class="sxs-lookup"><span data-stu-id="81a9e-216">ZipCode</span></span> |<span data-ttu-id="81a9e-217">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="81a9e-217">varchar(25)</span></span> |<span data-ttu-id="81a9e-218">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-218">Yes</span></span> |<span data-ttu-id="81a9e-219">大楼所在的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="81a9e-219">Zip code where the building is located.</span></span> |
|<span data-ttu-id="81a9e-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="81a9e-220">CountryShortCode</span></span> |<span data-ttu-id="81a9e-221">varchar (2) </span><span class="sxs-lookup"><span data-stu-id="81a9e-221">varchar(2)</span></span> |<span data-ttu-id="81a9e-222">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-222">Yes</span></span> |<span data-ttu-id="81a9e-223">大楼所在的国家/地区 ISO 3166-1 alpha-2 代码。</span><span class="sxs-lookup"><span data-stu-id="81a9e-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span> |
|<span data-ttu-id="81a9e-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="81a9e-224">StateProvinceCode</span></span> |<span data-ttu-id="81a9e-225">varchar (3) </span><span class="sxs-lookup"><span data-stu-id="81a9e-225">varchar(3)</span></span> |<span data-ttu-id="81a9e-226">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-226">Yes</span></span> |<span data-ttu-id="81a9e-227">大楼所在的省/市/市/县的三字母缩写。</span><span class="sxs-lookup"><span data-stu-id="81a9e-227">Three-letter abbreviation for the State/Province where the building is located.</span></span> |
|<span data-ttu-id="81a9e-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="81a9e-228">InsideCorp</span></span> |<span data-ttu-id="81a9e-229">bit</span><span class="sxs-lookup"><span data-stu-id="81a9e-229">bit</span></span> |<span data-ttu-id="81a9e-230">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-230">Yes</span></span> |<span data-ttu-id="81a9e-231">Bit 指示建筑物是否是企业网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="81a9e-231">Bit indicates whether the building is part of the corporate network.</span></span> |
|<span data-ttu-id="81a9e-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="81a9e-232">BuildingOfficeType</span></span> |<span data-ttu-id="81a9e-233">nvarchar (150) </span><span class="sxs-lookup"><span data-stu-id="81a9e-233">nvarchar(150)</span></span> |<span data-ttu-id="81a9e-234">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-234">Yes</span></span> |<span data-ttu-id="81a9e-235">大楼办公类型的说明。</span><span class="sxs-lookup"><span data-stu-id="81a9e-235">Description of the building office type.</span></span> |
|<span data-ttu-id="81a9e-236">地区</span><span class="sxs-lookup"><span data-stu-id="81a9e-236">Region</span></span> |<span data-ttu-id="81a9e-237">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="81a9e-237">varchar(25)</span></span> |<span data-ttu-id="81a9e-238">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-238">Yes</span></span> |<span data-ttu-id="81a9e-239">大楼所在的区域。</span><span class="sxs-lookup"><span data-stu-id="81a9e-239">Region where the building is located.</span></span> |
|||||

<span data-ttu-id="81a9e-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="81a9e-240">**CqdNetwork**</span></span>

|<span data-ttu-id="81a9e-241">Column</span><span class="sxs-lookup"><span data-stu-id="81a9e-241">Column</span></span>|<span data-ttu-id="81a9e-242">数据类型</span><span class="sxs-lookup"><span data-stu-id="81a9e-242">Data Type</span></span>|<span data-ttu-id="81a9e-243">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="81a9e-243">Allow Nulls?</span></span>|<span data-ttu-id="81a9e-244">详细信息</span><span class="sxs-lookup"><span data-stu-id="81a9e-244">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a9e-245">网络</span><span class="sxs-lookup"><span data-stu-id="81a9e-245">Network</span></span> |<span data-ttu-id="81a9e-246">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="81a9e-246">varchar(25)</span></span> |<span data-ttu-id="81a9e-247">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-247">No</span></span> |<span data-ttu-id="81a9e-248">子网地址。</span><span class="sxs-lookup"><span data-stu-id="81a9e-248">Subnet address.</span></span> |
|<span data-ttu-id="81a9e-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="81a9e-249">NetworkRange</span></span> |<span data-ttu-id="81a9e-250">tinyint</span><span class="sxs-lookup"><span data-stu-id="81a9e-250">tinyint</span></span> |<span data-ttu-id="81a9e-251">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-251">Yes</span></span> |<span data-ttu-id="81a9e-252">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="81a9e-252">Subnet mask.</span></span> |
|<span data-ttu-id="81a9e-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="81a9e-253">NetworkNameID</span></span> |<span data-ttu-id="81a9e-254">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-254">int</span></span> |<span data-ttu-id="81a9e-255">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-255">Yes</span></span> |<span data-ttu-id="81a9e-256">（可选）映射到 CqdNetworkName 表中的行。</span><span class="sxs-lookup"><span data-stu-id="81a9e-256">Optionally maps to a row in CqdNetworkName table.</span></span> |
|<span data-ttu-id="81a9e-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="81a9e-257">BuildingKey</span></span> |<span data-ttu-id="81a9e-258">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-258">int</span></span> |<span data-ttu-id="81a9e-259">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-259">Yes</span></span> |<span data-ttu-id="81a9e-260">外键，与 CqdBuilding 表中的条目之一匹配。</span><span class="sxs-lookup"><span data-stu-id="81a9e-260">Foreign key, matches one of the entries in the CqdBuilding table.</span></span> |
|<span data-ttu-id="81a9e-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="81a9e-261">UpdatedDate</span></span> |<span data-ttu-id="81a9e-262">datetime</span><span class="sxs-lookup"><span data-stu-id="81a9e-262">datetime</span></span> |<span data-ttu-id="81a9e-263">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-263">No</span></span> |<span data-ttu-id="81a9e-264">上次更新条目的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="81a9e-264">Datetime for when the entry was last updated.</span></span> |
||||||

<span data-ttu-id="81a9e-265">默认情况下，此下一个表具有一个 (0，"未知") 。</span><span class="sxs-lookup"><span data-stu-id="81a9e-265">By default this next table has one entry (0, 'Unknown').</span></span>

<span data-ttu-id="81a9e-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="81a9e-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="81a9e-267">Column</span><span class="sxs-lookup"><span data-stu-id="81a9e-267">Column</span></span>|<span data-ttu-id="81a9e-268">数据类型</span><span class="sxs-lookup"><span data-stu-id="81a9e-268">Data Type</span></span>|<span data-ttu-id="81a9e-269">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="81a9e-269">Allow Nulls?</span></span>|<span data-ttu-id="81a9e-270">详细信息</span><span class="sxs-lookup"><span data-stu-id="81a9e-270">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a9e-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="81a9e-271">BuildingTypeId</span></span> |<span data-ttu-id="81a9e-272">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-272">int</span></span> |<span data-ttu-id="81a9e-273">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-273">No</span></span> |<span data-ttu-id="81a9e-274">CqdBuildingType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="81a9e-274">Primary key for the CqdBuildingType table.</span></span> |
|<span data-ttu-id="81a9e-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="81a9e-275">BuildingTypeDesc</span></span> |<span data-ttu-id="81a9e-276">char (18) </span><span class="sxs-lookup"><span data-stu-id="81a9e-276">char(18)</span></span> |<span data-ttu-id="81a9e-277">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-277">No</span></span> |<span data-ttu-id="81a9e-278">大楼类型说明。</span><span class="sxs-lookup"><span data-stu-id="81a9e-278">Building type description.</span></span> |
|||||

<span data-ttu-id="81a9e-279">默认情况下，此下一个表具有一 (0、"Unknown"、0 和 null) 。</span><span class="sxs-lookup"><span data-stu-id="81a9e-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="81a9e-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="81a9e-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="81a9e-281">Column</span><span class="sxs-lookup"><span data-stu-id="81a9e-281">Column</span></span>|<span data-ttu-id="81a9e-282">数据类型</span><span class="sxs-lookup"><span data-stu-id="81a9e-282">Data Type</span></span>|<span data-ttu-id="81a9e-283">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="81a9e-283">Allow Nulls?</span></span>|<span data-ttu-id="81a9e-284">详细信息</span><span class="sxs-lookup"><span data-stu-id="81a9e-284">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a9e-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="81a9e-285">OwnershipTypeId</span></span> |<span data-ttu-id="81a9e-286">int</span><span class="sxs-lookup"><span data-stu-id="81a9e-286">int</span></span> |<span data-ttu-id="81a9e-287">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-287">No</span></span> |<span data-ttu-id="81a9e-288">CqdBuildingOwnershipType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="81a9e-288">Primary key for the CqdBuildingOwnershipType table.</span></span> |
|<span data-ttu-id="81a9e-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="81a9e-289">OwnershipTypeDesc</span></span> |<span data-ttu-id="81a9e-290">varchar (25) </span><span class="sxs-lookup"><span data-stu-id="81a9e-290">varchar(25)</span></span> |<span data-ttu-id="81a9e-291">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-291">No</span></span> |<span data-ttu-id="81a9e-292">所有权类型说明。</span><span class="sxs-lookup"><span data-stu-id="81a9e-292">Ownership type description.</span></span> |
|<span data-ttu-id="81a9e-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="81a9e-293">LeaseInd</span></span> |<span data-ttu-id="81a9e-294">tinyint</span><span class="sxs-lookup"><span data-stu-id="81a9e-294">tinyint</span></span> |<span data-ttu-id="81a9e-295">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-295">Yes</span></span> |<span data-ttu-id="81a9e-296">引用 CqdBuildingOwnershipType 表中另一行的索引，用于标识租用的大楼。</span><span class="sxs-lookup"><span data-stu-id="81a9e-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span> |
|<span data-ttu-id="81a9e-297">所有者</span><span class="sxs-lookup"><span data-stu-id="81a9e-297">Owner</span></span> |<span data-ttu-id="81a9e-298">varchar (50) </span><span class="sxs-lookup"><span data-stu-id="81a9e-298">varchar(50)</span></span> |<span data-ttu-id="81a9e-299">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-299">Yes</span></span> |<span data-ttu-id="81a9e-300">大楼所有者。</span><span class="sxs-lookup"><span data-stu-id="81a9e-300">Building owner.</span></span> |
|||||

<span data-ttu-id="81a9e-301">默认情况下，此下一个表具有一 (0、"Unknown"、0 和 null) 。</span><span class="sxs-lookup"><span data-stu-id="81a9e-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="81a9e-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="81a9e-302">**CqdBssid**</span></span>

|<span data-ttu-id="81a9e-303">Column</span><span class="sxs-lookup"><span data-stu-id="81a9e-303">Column</span></span>|<span data-ttu-id="81a9e-304">数据类型</span><span class="sxs-lookup"><span data-stu-id="81a9e-304">Data Type</span></span>|<span data-ttu-id="81a9e-305">是否允许 Null？</span><span class="sxs-lookup"><span data-stu-id="81a9e-305">Allow Nulls?</span></span>|<span data-ttu-id="81a9e-306">详细信息</span><span class="sxs-lookup"><span data-stu-id="81a9e-306">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a9e-307">bss</span><span class="sxs-lookup"><span data-stu-id="81a9e-307">bss</span></span> |<span data-ttu-id="81a9e-308">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="81a9e-308">nvarchar(50)</span></span> |<span data-ttu-id="81a9e-309">否</span><span class="sxs-lookup"><span data-stu-id="81a9e-309">No</span></span> |<span data-ttu-id="81a9e-310">CqdBssid 表的主键。</span><span class="sxs-lookup"><span data-stu-id="81a9e-310">Primary key for the CqdBssid table.</span></span> <span data-ttu-id="81a9e-311">是 WiFi 接入点的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="81a9e-311">Is the BSSID of the WiFi Access Point.</span></span> |
|<span data-ttu-id="81a9e-312">ess</span><span class="sxs-lookup"><span data-stu-id="81a9e-312">ess</span></span> |<span data-ttu-id="81a9e-313">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="81a9e-313">nvarchar(50)</span></span> |<span data-ttu-id="81a9e-314">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-314">Yes</span></span> |<span data-ttu-id="81a9e-315">Wifi 接入点控制器信息。</span><span class="sxs-lookup"><span data-stu-id="81a9e-315">Wifi Access Point Controller information.</span></span> |
|<span data-ttu-id="81a9e-316">phy</span><span class="sxs-lookup"><span data-stu-id="81a9e-316">phy</span></span> |<span data-ttu-id="81a9e-317">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="81a9e-317">nvarchar(50)</span></span> |<span data-ttu-id="81a9e-318">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-318">Yes</span></span> |<span data-ttu-id="81a9e-319">Phy 信息。</span><span class="sxs-lookup"><span data-stu-id="81a9e-319">Phy information.</span></span> |
|<span data-ttu-id="81a9e-320">ap</span><span class="sxs-lookup"><span data-stu-id="81a9e-320">ap</span></span> |<span data-ttu-id="81a9e-321">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="81a9e-321">nvarchar(50)</span></span> |<span data-ttu-id="81a9e-322">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-322">Yes</span></span> |<span data-ttu-id="81a9e-323">Wifi 接入点名称。</span><span class="sxs-lookup"><span data-stu-id="81a9e-323">Wifi Access Point Name.</span></span> |
|<span data-ttu-id="81a9e-324">生成</span><span class="sxs-lookup"><span data-stu-id="81a9e-324">Building</span></span> |<span data-ttu-id="81a9e-325">nvarchar (500) </span><span class="sxs-lookup"><span data-stu-id="81a9e-325">nvarchar(500)</span></span> |<span data-ttu-id="81a9e-326">是的。</span><span class="sxs-lookup"><span data-stu-id="81a9e-326">Yes</span></span> |<span data-ttu-id="81a9e-327">WiFi 访问点所在的建筑物名称。</span><span class="sxs-lookup"><span data-stu-id="81a9e-327">The Building Name the WiFi Access Point is located in.</span></span> |
||||

## <a name="cqd-streams"></a><span data-ttu-id="81a9e-328">CQD 流</span><span class="sxs-lookup"><span data-stu-id="81a9e-328">CQD Streams</span></span>

<span data-ttu-id="81a9e-329">CQD 流被视为良好、较差或未经分类。</span><span class="sxs-lookup"><span data-stu-id="81a9e-329">A CQD stream is considered good, poor, or unclassified.</span></span> <span data-ttu-id="81a9e-330">CQM 1.5 现在使用下面的 CQD 定义：</span><span class="sxs-lookup"><span data-stu-id="81a9e-330">CQM 1.5 now uses the following CQD definition:</span></span>

- <span data-ttu-id="81a9e-331">质量欠佳的流是超出阈值的差呼叫指标的任意组合。</span><span class="sxs-lookup"><span data-stu-id="81a9e-331">A poor stream is any combination of the poor call metrics beyond threshold.</span></span>
- <span data-ttu-id="81a9e-332">当呼叫中的一个流较差时，呼叫的两个流将被标记为差。</span><span class="sxs-lookup"><span data-stu-id="81a9e-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="81a9e-333">在会议中，每个参与者均算作唯一呼叫，并独立于所有其他参与者进行报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
- <span data-ttu-id="81a9e-334">未分类流是无质量指标 (，即综合事务或短时间) 。</span><span class="sxs-lookup"><span data-stu-id="81a9e-334">Unclassified streams are streams without quality metrics (that is, Synthetic Transactions or short calls).</span></span>
- <span data-ttu-id="81a9e-335">有效流 = 非移动客户端</span><span class="sxs-lookup"><span data-stu-id="81a9e-335">Valid Streams = non-mobile clients</span></span>
- <span data-ttu-id="81a9e-336">无法修改分类器</span><span class="sxs-lookup"><span data-stu-id="81a9e-336">Classifier cannot be modified</span></span>

<span data-ttu-id="81a9e-337">**较差的呼叫定义/分类器**</span><span class="sxs-lookup"><span data-stu-id="81a9e-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="81a9e-338">跃点数</span><span class="sxs-lookup"><span data-stu-id="81a9e-338">Metric</span></span>|<span data-ttu-id="81a9e-339">阈值</span><span class="sxs-lookup"><span data-stu-id="81a9e-339">Threshold</span></span>|
|:-----|:-----|
|<span data-ttu-id="81a9e-340">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="81a9e-340">DegradationAvg</span></span> |<span data-ttu-id="81a9e-341">大于 1.0 (-1 网络 MOS) </span><span class="sxs-lookup"><span data-stu-id="81a9e-341">Greater than 1.0 (-1 network MOS)</span></span> |
|<span data-ttu-id="81a9e-342">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="81a9e-342">RoundTrip</span></span> |<span data-ttu-id="81a9e-343">大于 500</span><span class="sxs-lookup"><span data-stu-id="81a9e-343">Greater than 500</span></span> |
|<span data-ttu-id="81a9e-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="81a9e-344">PacketLossRate</span></span> |<span data-ttu-id="81a9e-345">大于 0.1 (10%) </span><span class="sxs-lookup"><span data-stu-id="81a9e-345">Greater than 0.1 (10%)</span></span> |
|<span data-ttu-id="81a9e-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="81a9e-346">JitterInterArrival</span></span> |<span data-ttu-id="81a9e-347">大于 30</span><span class="sxs-lookup"><span data-stu-id="81a9e-347">Greater than 30</span></span> |
|<span data-ttu-id="81a9e-348">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="81a9e-348">RatioConcealedSamplesAvg</span></span> |<span data-ttu-id="81a9e-349">大于 0.07</span><span class="sxs-lookup"><span data-stu-id="81a9e-349">Greater than 0.07</span></span> |
|||

<span data-ttu-id="81a9e-350">JPDR 定义 = 质量欠佳的呼叫定义减去 RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="81a9e-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span>

## <a name="where-is-callercallee"></a><span data-ttu-id="81a9e-351">呼叫者/被叫方在哪里？</span><span class="sxs-lookup"><span data-stu-id="81a9e-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="81a9e-352">CQD 不使用呼叫方/被叫方字段，而是使用"First"和"Second"，因为呼叫者与被叫方之间存在干预步骤。</span><span class="sxs-lookup"><span data-stu-id="81a9e-352">CQD doesn't use Caller/Callee fields, instead it uses "First" and "Second" because there are intervening steps between the caller and callee.</span></span>

 <span data-ttu-id="81a9e-353">**First** 如果流中涉及 (AV MCU 或中介服务器) ，则始终为 Server 终结点。</span><span class="sxs-lookup"><span data-stu-id="81a9e-353">**First** Will always be the Server endpoint (for example, AV MCU or Mediation Server) if a Server is involved in the stream.</span></span>

 <span data-ttu-id="81a9e-354">**Second** 始终为客户端终结点，除非它是Server-Server流。</span><span class="sxs-lookup"><span data-stu-id="81a9e-354">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>

<span data-ttu-id="81a9e-355">**第一和第二分类的示例**</span><span class="sxs-lookup"><span data-stu-id="81a9e-355">**Example of First and Second classification**</span></span>

|<span data-ttu-id="81a9e-356">终结点 1 UAType</span><span class="sxs-lookup"><span data-stu-id="81a9e-356">Endpoint 1 UAType</span></span>|<span data-ttu-id="81a9e-357">终结点 2 UUAType</span><span class="sxs-lookup"><span data-stu-id="81a9e-357">Endpoint 2 UUAType</span></span>|<span data-ttu-id="81a9e-358">First</span><span class="sxs-lookup"><span data-stu-id="81a9e-358">First</span></span>|<span data-ttu-id="81a9e-359">秒</span><span class="sxs-lookup"><span data-stu-id="81a9e-359">Second</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a9e-360">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="81a9e-360">2 (AVMCU)</span></span> |<span data-ttu-id="81a9e-361">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="81a9e-361">4 (Skype for Business)</span></span> |<span data-ttu-id="81a9e-362">终结点 1</span><span class="sxs-lookup"><span data-stu-id="81a9e-362">Endpoint 1</span></span> |<span data-ttu-id="81a9e-363">终结点 2</span><span class="sxs-lookup"><span data-stu-id="81a9e-363">Endpoint 2</span></span> |
|<span data-ttu-id="81a9e-364">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="81a9e-364">2 (AVMCU)</span></span> |<span data-ttu-id="81a9e-365">1 (mMediationServer) </span><span class="sxs-lookup"><span data-stu-id="81a9e-365">1 (mMediationServer)</span></span> |<span data-ttu-id="81a9e-366">终结点 2</span><span class="sxs-lookup"><span data-stu-id="81a9e-366">Endpoint 2</span></span> |<span data-ttu-id="81a9e-367">终结点 1</span><span class="sxs-lookup"><span data-stu-id="81a9e-367">Endpoint 1</span></span> |
|<span data-ttu-id="81a9e-368">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="81a9e-368">4 (Skype for Business)</span></span> |<span data-ttu-id="81a9e-369">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="81a9e-369">4 (Skype for Business)</span></span> |<span data-ttu-id="81a9e-370">MediaLine 中的呼叫者</span><span class="sxs-lookup"><span data-stu-id="81a9e-370">The Caller in MediaLine</span></span> |<span data-ttu-id="81a9e-371">MMediaLine 中的被叫方</span><span class="sxs-lookup"><span data-stu-id="81a9e-371">The Callee in MMediaLine</span></span> |
|||||

<span data-ttu-id="81a9e-372">如果两个终结点的类型相同，则 CQD 将"呼叫者"条目"第一个"和"被叫方第二个"。</span><span class="sxs-lookup"><span data-stu-id="81a9e-372">If both endpoints are the same type, CQD makes the Caller entry First and the Callee Second.</span></span> <span data-ttu-id="81a9e-373">有关终结点名称详细信息，请参阅 [此博客](/archive/blogs/jenstr/call-quality-dashboard-tips-and-tricks)。</span><span class="sxs-lookup"><span data-stu-id="81a9e-373">For more information about endpoint names, see [this blog](/archive/blogs/jenstr/call-quality-dashboard-tips-and-tricks).</span></span>

## <a name="accounting-for-vpn"></a><span data-ttu-id="81a9e-374">VPN 会计</span><span class="sxs-lookup"><span data-stu-id="81a9e-374">Accounting for VPN</span></span>

<span data-ttu-id="81a9e-375">如果已知 VPN 解决方案能够准确设置 VPN 标志，则你已全部设置。</span><span class="sxs-lookup"><span data-stu-id="81a9e-375">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="81a9e-376">否则，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="81a9e-376">Otherwise, use one of the following methods:</span></span>

- <span data-ttu-id="81a9e-377">创建名为 VPN 网络类型 (首选) ，然后将 VPN 子网与这一新的 VPN NetworkType 关联。</span><span class="sxs-lookup"><span data-stu-id="81a9e-377">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
- <span data-ttu-id="81a9e-378">创建一个称为 VPN 的建筑物，然后将 VPN 子网与该建筑物关联。</span><span class="sxs-lookup"><span data-stu-id="81a9e-378">Create a building called VPN, then Associate VPN Subnets with this building.</span></span>

## <a name="query-fundamentals"></a><span data-ttu-id="81a9e-379">查询基础</span><span class="sxs-lookup"><span data-stu-id="81a9e-379">Query Fundamentals</span></span>

<span data-ttu-id="81a9e-380">格式良好的查询包含以下三个参数：</span><span class="sxs-lookup"><span data-stu-id="81a9e-380">A well-formed query contains all three of these parameters:</span></span>

- <span data-ttu-id="81a9e-381">度量</span><span class="sxs-lookup"><span data-stu-id="81a9e-381">Measurement</span></span>
- <span data-ttu-id="81a9e-382">Dimension</span><span class="sxs-lookup"><span data-stu-id="81a9e-382">Dimension</span></span>
- <span data-ttu-id="81a9e-383">筛选器</span><span class="sxs-lookup"><span data-stu-id="81a9e-383">Filter</span></span>

<span data-ttu-id="81a9e-384">一个格式良好的查询示例为"按子网 [Dimension] 显示质量欠佳的流 [度量]，以生成 6 [筛选器]"。</span><span class="sxs-lookup"><span data-stu-id="81a9e-384">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

## <a name="what-does-union-do"></a><span data-ttu-id="81a9e-385">UNION 有什么功能？</span><span class="sxs-lookup"><span data-stu-id="81a9e-385">What does UNION do?</span></span>

<span data-ttu-id="81a9e-386">Union 允许您使用 AND 运算符筛选条件。</span><span class="sxs-lookup"><span data-stu-id="81a9e-386">Union allows you to filter conditions with the AND operator.</span></span> <span data-ttu-id="81a9e-387">在某些情况下，可以将多个 Filter 条件组合在一起，以实现类似于 OR 操作的结果。</span><span class="sxs-lookup"><span data-stu-id="81a9e-387">There are scenarios where you can combine multiple Filter conditions together to achieve a result similar to an OR operation.</span></span>

<span data-ttu-id="81a9e-388">示例：为了从建筑物获取所有流，UNION 提供了合并数据集的一个独特视图。</span><span class="sxs-lookup"><span data-stu-id="81a9e-388">Example: To get all streams from a building, UNION provides a distinct view of the merged dataset.</span></span> <span data-ttu-id="81a9e-389">若要使用 UNION，请将常用文本插入到要联合的两个筛选条件的 UNION 字段中。</span><span class="sxs-lookup"><span data-stu-id="81a9e-389">To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span>

## <a name="default-report-breakdown"></a><span data-ttu-id="81a9e-390">默认报告细分</span><span class="sxs-lookup"><span data-stu-id="81a9e-390">Default Report Breakdown</span></span>

<span data-ttu-id="81a9e-391">如果无线是在内部管理的，可以在托管存储桶中重新创建无线报告。</span><span class="sxs-lookup"><span data-stu-id="81a9e-391">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span>

![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a><span data-ttu-id="81a9e-393">操作过程</span><span class="sxs-lookup"><span data-stu-id="81a9e-393">Operational Processes</span></span>

<span data-ttu-id="81a9e-394">首先查看并修正托管流。</span><span class="sxs-lookup"><span data-stu-id="81a9e-394">Review and remediate Managed Streams first.</span></span> <span data-ttu-id="81a9e-395">此区域中的质量应完全在你的控制范围内，因此最容易修正。</span><span class="sxs-lookup"><span data-stu-id="81a9e-395">Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span>

### <a name="managed-streams"></a><span data-ttu-id="81a9e-396">托管流</span><span class="sxs-lookup"><span data-stu-id="81a9e-396">Managed Streams</span></span>

<span data-ttu-id="81a9e-397">按以下顺序查看和修正托管流：</span><span class="sxs-lookup"><span data-stu-id="81a9e-397">Review and remediate managed streams in the following order:</span></span>

1. <span data-ttu-id="81a9e-398">Server-Server</span><span class="sxs-lookup"><span data-stu-id="81a9e-398">Server-Server</span></span>
2. <span data-ttu-id="81a9e-399">Server-Wired-Inside</span><span class="sxs-lookup"><span data-stu-id="81a9e-399">Server-Wired-Inside</span></span>
3. <span data-ttu-id="81a9e-400">有线-有线-内部</span><span class="sxs-lookup"><span data-stu-id="81a9e-400">Wired-Wired-Inside</span></span>

### <a name="unmanaged-streams"></a><span data-ttu-id="81a9e-401">非托管流</span><span class="sxs-lookup"><span data-stu-id="81a9e-401">Unmanaged Streams</span></span>

<span data-ttu-id="81a9e-402">按以下顺序查看和修正非托管流：</span><span class="sxs-lookup"><span data-stu-id="81a9e-402">Review and remediate unmanaged streams in the following order:</span></span>

1. <span data-ttu-id="81a9e-403">Server-Wifi-Inside</span><span class="sxs-lookup"><span data-stu-id="81a9e-403">Server-Wifi-Inside</span></span>
2. <span data-ttu-id="81a9e-404">Server-Wired-Outside</span><span class="sxs-lookup"><span data-stu-id="81a9e-404">Server-Wired-Outside</span></span>
3. <span data-ttu-id="81a9e-405">Server-Wifi-Outside</span><span class="sxs-lookup"><span data-stu-id="81a9e-405">Server-Wifi-Outside</span></span>
4. <span data-ttu-id="81a9e-406">有线-外-直接</span><span class="sxs-lookup"><span data-stu-id="81a9e-406">Wired-Outside-Direct</span></span>
5. <span data-ttu-id="81a9e-407">有线-外部-中继</span><span class="sxs-lookup"><span data-stu-id="81a9e-407">Wired-Outside-Relay</span></span>
6. <span data-ttu-id="81a9e-408">其他非托管</span><span class="sxs-lookup"><span data-stu-id="81a9e-408">Other Unmanaged</span></span>