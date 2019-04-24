---
title: 用于呼叫质量仪表板 Skype 业务服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要： 了解如何使用呼叫质量面板。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 856035642d1d8a818abe5f0a106c90270d706516
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217692"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="a8d69-104">用于呼叫质量仪表板 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="a8d69-104">Use Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="a8d69-105">**摘要：** 了解如何使用呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="a8d69-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="a8d69-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="a8d69-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a8d69-p103">CQD 允许 IT 专业人员使用聚合数据来识别其环境中遇到媒体质量问题的重点关注区域。它允许 IT 专业人员比较不同用户组的统计信息，并识别趋势和模式。它重点关注的不是单个通话问题，而是识别适用于给定环境中许多用户的问题和解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p103">CQD allows IT Pros to use aggregate data to identify focus areas in their environment experiencing media quality issues. It allows an IT Pro to compare statistics for different groups of users and identify trends and patterns. It is not focused on solving individual call issues, but on identifying problems and solutions that will apply to many users in a given environment.</span></span>
  
## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="a8d69-110">呼叫质量仪表板用户指南</span><span class="sxs-lookup"><span data-stu-id="a8d69-110">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="a8d69-p104">呼叫质量仪表板 (CQD) 是一个用于根据用户体验质量 (QoE) 数据快速创建并组织报告的 Web 门户。CQD 部署 SSAS 多维数据集以将数据聚合在 QoE 指标数据库中。这样，用户能够实时创建并修改报告，以及进行调查。虽然可以使用 Excel 直接连接到多维数据集，但门户已针对涉及 QoE 数据的几个工作流进行了优化。这些数据包括：用于实现快速访问的报告数据缓存、用于信息共享和发布的报告页面深层链接、简化的报告编辑和创建以及用于报告说明的可编辑元数据。此外，CQD 还提供 Web API，允许用户以编程方式访问多维数据集数据以用于自定义仪表板。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p104">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data. CQD deploys a SSAS cube to aggregate the data in the QoE Metrics database. This enables users to create and modify reports and do investigations in real-time. While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data. This data includes caching of report data for fast access, deep links to report pages for information sharing and publishing, streamlined report editing and creation, and editable metadata for report descriptions. Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span> 
  
### <a name="feature-overview"></a><span data-ttu-id="a8d69-117">功能概述</span><span class="sxs-lookup"><span data-stu-id="a8d69-117">Feature Overview</span></span>

<span data-ttu-id="a8d69-118">用户访问呼叫质量仪表板时，他/她将看见以下内容：</span><span class="sxs-lookup"><span data-stu-id="a8d69-118">When a user visits the Call Quality Dashboard, this is what s/he will see:</span></span>
  
![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. <span data-ttu-id="a8d69-120">"摘要"窗格是可以找到"报表设置"（右侧） 的上下文。</span><span class="sxs-lookup"><span data-stu-id="a8d69-120">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span> 
    
2. <span data-ttu-id="a8d69-121">报告设置级别属性 （包括 y 轴高度） 可以通过单击"编辑"，在摘要窗格上的设置。</span><span class="sxs-lookup"><span data-stu-id="a8d69-121">Report Set level properties (including Y-axis height) can be set by clicking on "Edit" in the Summary Pane.</span></span>
    
3. <span data-ttu-id="a8d69-122">痕迹导航可帮助用户确定其在报告集层次结构中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="a8d69-122">The Breadcrumb helps users identify their current location within the report set hierarchy.</span></span> 
    
4. <span data-ttu-id="a8d69-p105">有子报告的报告会显示一个蓝色链接。单击链接将向下钻取到子报告。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p105">Reports with sub-reports are shown with a blue link. Clicking on the link will drill down to the child reports.</span></span> 
    
<span data-ttu-id="a8d69-125">将光标移到条形图上时，趋势线将会显示详细值。</span><span class="sxs-lookup"><span data-stu-id="a8d69-125">Moving the mouse over the bar charts and trend lines will show detailed values.</span></span> <span data-ttu-id="a8d69-126">具有焦点的报告将显示操作菜单:"编辑"、"复制"、"删除"和"下载"。</span><span class="sxs-lookup"><span data-stu-id="a8d69-126">The report that has focus will show the action menu: "Edit", "Clone", "Delete", and "Download".</span></span> 
  
### <a name="default-reports"></a><span data-ttu-id="a8d69-127">默认报告</span><span class="sxs-lookup"><span data-stu-id="a8d69-127">Default Reports</span></span>

<span data-ttu-id="a8d69-p107">用户首次访问呼叫质量仪表板门户时，会自动创建一组默认的报告。这些报告有时称为系统报告。用户能够任意修改或删除这些报告。通常，用户通过创建新的同级报告和子报告来扩展这些报告。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p107">When a user first accesses the Call Quality Dashboard portal, a default set of reports is automatically created. These reports are sometimes referred to as system reports. The user is able to freely modify or delete these reports. Generally, users will extend them by creating new sibling and child reports.</span></span> 
  
<span data-ttu-id="a8d69-132">顶级，在"音频流每月走向"报告将显示的所有音频流的每月的趋势。</span><span class="sxs-lookup"><span data-stu-id="a8d69-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="a8d69-133">将光标移到条形图中的条形上时，将显示条形图所表示数据的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="a8d69-133">Moving the mouse over the bars in a bar chart will show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="a8d69-134">单击音频流每月的趋势报告的标题上将导航到"托管 vs 非托管的音频流"报表，报告分别驻留在托管和非托管的调用。</span><span class="sxs-lookup"><span data-stu-id="a8d69-134">Clicking on the title of the Audio Streams Monthly Trend report will navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="a8d69-135">管理呼叫是从公司防火墙内通过有线连接进行的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a8d69-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="a8d69-136">非管理呼叫包括从公司防火墙外进行的呼叫以及通过 Wi-Fi 进行的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="a8d69-136">Unmanaged calls include calls made from outside the corporate firewall as well as all calls made over Wi-Fi.</span></span>
  
<span data-ttu-id="a8d69-137">其他顶级报表称为"用户报告呼叫质量分级直方图。"</span><span class="sxs-lookup"><span data-stu-id="a8d69-137">The other top level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="a8d69-138">呼叫质量评级是 Skype for Business 用户在呼叫结束时提供用来指示通话质量的数字。</span><span class="sxs-lookup"><span data-stu-id="a8d69-138">The Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="a8d69-139">评级数字范围从 1 到 5，1 表示最差，5 表示最佳。</span><span class="sxs-lookup"><span data-stu-id="a8d69-139">The rating numbers range from 1 to 5, with 1 being the worst and 5 being the best.</span></span> <span data-ttu-id="a8d69-140">直方图显示一个月中具有指示评级的音频通话数。</span><span class="sxs-lookup"><span data-stu-id="a8d69-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span> 
  
<span data-ttu-id="a8d69-p110">通常，单击任何报告标题将导航到具有额外数据筛选器的报告。在系统报告中，每个子报告显示其父报告中的一部分数据。这提供了一个用于解决问题的概念简单的模式：通过调查有问题的数据或趋势所属的子报告来缩小问题范围。由于能够创建新的子报告，用户可以针对特定数据趋势的来源调查其自己的假设。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p110">In general, clicking on the title of any of the reports will navigate into reports with additional filters on the data. In the system reports, each child report displays a subset of the data available in its parent report. This provides a conceptually simple model for problem solving: narrow down the problem space by investigating which sub-report the problematic data or trend is confined to. The ability to create new sub-reports allows users to investigate their own hypotheses as to the provenance of specific data trends.</span></span>
  
### <a name="creating-and-editing-reports"></a><span data-ttu-id="a8d69-145">创建和编辑报告</span><span class="sxs-lookup"><span data-stu-id="a8d69-145">Creating and Editing Reports</span></span>

<span data-ttu-id="a8d69-146">当报表的操作菜单中单击"编辑"，用户将看到报告编辑器。</span><span class="sxs-lookup"><span data-stu-id="a8d69-146">When clicking on "Edit" in the action menu of a report, users will see the Report Editor.</span></span> <span data-ttu-id="a8d69-147">每个报告都可以通过对多维数据集进行查询得到。</span><span class="sxs-lookup"><span data-stu-id="a8d69-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="a8d69-148">报告是其查询返回的数据的可视化形式。</span><span class="sxs-lookup"><span data-stu-id="a8d69-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="a8d69-149">报告编辑器是用于编辑这些查询的用户界面，并包含报告的显示选项。</span><span class="sxs-lookup"><span data-stu-id="a8d69-149">The Report Editor is a user interface for editing these queries, as well as the display options of the report.</span></span> <span data-ttu-id="a8d69-150">用户打开报告编辑器时，他/她将看见以下内容：</span><span class="sxs-lookup"><span data-stu-id="a8d69-150">When a user opens the Report Editor, this is what s/he will see:</span></span>
  
![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. <span data-ttu-id="a8d69-152">左侧窗格中选择了维度、度量和筛选器。</span><span class="sxs-lookup"><span data-stu-id="a8d69-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="a8d69-153">悬停在某个现有的值将显示"x"按钮，允许要移除的值。</span><span class="sxs-lookup"><span data-stu-id="a8d69-153">Hovering over one of the existing values will show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="a8d69-154">单击一个标题旁边的"加号"按钮将打开添加新的维度、 度量值或筛选器对话框。</span><span class="sxs-lookup"><span data-stu-id="a8d69-154">Clicking on the "plus" button next to a heading will open the dialog for adding a new dimension, measure or filter.</span></span> 
    
2. <span data-ttu-id="a8d69-155">顶部显示了图表自定义选项。</span><span class="sxs-lookup"><span data-stu-id="a8d69-155">Options for chart customization are displayed at the top.</span></span>
    
3. <span data-ttu-id="a8d69-156">报告编辑器中提供了报告预览。</span><span class="sxs-lookup"><span data-stu-id="a8d69-156">A preview of the report is available in the Report Editor.</span></span> 
    
4. <span data-ttu-id="a8d69-157">可使用底部的编辑框创建详细报告说明。</span><span class="sxs-lookup"><span data-stu-id="a8d69-157">A detailed report description can be created using the edit box at the bottom.</span></span> 
    
### <a name="sparklines-in-tables"></a><span data-ttu-id="a8d69-158">表中的迷你图</span><span class="sxs-lookup"><span data-stu-id="a8d69-158">Sparklines in Tables</span></span>

<span data-ttu-id="a8d69-p113">将 StartDate.Month 添加为一个维度，且数据以表格形式呈现为趋势时，可以在表格单元格内显示条形图和迷你图。将鼠标指针移到条形图和迷你图上将显示单个月的值。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p113">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells. Moving the mouse pointer over the bar chart and the sparklines will show values for individual months.</span></span> 
  
![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
<span data-ttu-id="a8d69-162">为了显示条形图和迷你图，必须检查顶部的报告编辑器中的"显示迷你图"复选框。</span><span class="sxs-lookup"><span data-stu-id="a8d69-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="a8d69-163">这将选中“趋势”选项，并将“月份”下移为最后一个维度，这也可以通过单击“月份”并使用向上和向下箭头上移或下移 StartDate.Month 来完成。</span><span class="sxs-lookup"><span data-stu-id="a8d69-163">This will select the Trend option and move Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span> 
  
### <a name="settings"></a><span data-ttu-id="a8d69-164">设置</span><span class="sxs-lookup"><span data-stu-id="a8d69-164">Settings</span></span>

<span data-ttu-id="a8d69-165">设置菜单位于仪表板的右上角，其包含了有用页面（比如“系统运行状况”和“关于”页面）的链接。</span><span class="sxs-lookup"><span data-stu-id="a8d69-165">Located in the top right corner of the dashboard, the settings menu contains links to useful pages like the System Health and About pages.</span></span>
  
![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
<span data-ttu-id="a8d69-167">要显示说明和时间戳为最多为各个用户，这些设置仅影响的仪表板的个人的版本，不会修改和设置报表或哪些其他用户查看。</span><span class="sxs-lookup"><span data-stu-id="a8d69-167">Whether or not to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, not does not modify the report set or what other users see.</span></span> <span data-ttu-id="a8d69-168">清除缓存会导致所有查询从多维数据集重新加载其数据，而恢复默认设置将删除用户创建或修改的所有报告，并重新创建系统报告集 - 用户首次登录时看到的内容。</span><span class="sxs-lookup"><span data-stu-id="a8d69-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when logging in for the first time.</span></span>
  
<span data-ttu-id="a8d69-169">用户仪表板链接显示用户可以在其中查看 CQD 的其他用户并浏览其报告的页面。</span><span class="sxs-lookup"><span data-stu-id="a8d69-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="a8d69-170">共享报告集时，只需复制 URL 栏中的链接并与另一个 CQD 用户共享该链接即可。</span><span class="sxs-lookup"><span data-stu-id="a8d69-170">When sharing a report set, simply copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="a8d69-171">一个用户会看到在用户的用户名下的用户仪表板链接页中，此链接将相同。</span><span class="sxs-lookup"><span data-stu-id="a8d69-171">This link will be the same as the one other users would see in the Users Dashboard Link page under the user's username.</span></span>
  
### <a name="supplying-subnet-information"></a><span data-ttu-id="a8d69-172">提供子网信息</span><span class="sxs-lookup"><span data-stu-id="a8d69-172">Supplying Subnet Information</span></span>

<span data-ttu-id="a8d69-173">如果在存档数据库中输入了特定于站点的信息以提供子网到大楼的映射信息（例如，按大楼的有线/无线呼叫质量），则可以显示其他分析内容。</span><span class="sxs-lookup"><span data-stu-id="a8d69-173">Additional insights can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (e.g. wired/wireless call quality by building).</span></span> 
  
<span data-ttu-id="a8d69-174">至少，需要填写以下表格才能创建这些报告：</span><span class="sxs-lookup"><span data-stu-id="a8d69-174">At a minimum, the following tables need to be populated to create these reports:</span></span>
  
- <span data-ttu-id="a8d69-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="a8d69-175">CqdBuilding</span></span>
    
- <span data-ttu-id="a8d69-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="a8d69-176">CqdNetwork</span></span>
    
<span data-ttu-id="a8d69-177">可在 CqdBuildingType 和 CqdBuildingOwnershipType 表中提供其他信息以进行进一步的筛选和向下钻取。</span><span class="sxs-lookup"><span data-stu-id="a8d69-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span> 
  
<span data-ttu-id="a8d69-178">这些表的架构采用如下定义：</span><span class="sxs-lookup"><span data-stu-id="a8d69-178">The schema for these tables are defined as follows:</span></span>
  
<span data-ttu-id="a8d69-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="a8d69-179">**CqdBuilding**</span></span>

|<span data-ttu-id="a8d69-180">**列**</span><span class="sxs-lookup"><span data-stu-id="a8d69-180">**Column**</span></span>|<span data-ttu-id="a8d69-181">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a8d69-181">**Data Type**</span></span>|<span data-ttu-id="a8d69-182">**是否允许 Null？**</span><span class="sxs-lookup"><span data-stu-id="a8d69-182">**Allow Nulls?**</span></span>|<span data-ttu-id="a8d69-183">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a8d69-183">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8d69-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="a8d69-184">BuildingKey</span></span>  <br/> |<span data-ttu-id="a8d69-185">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-185">int</span></span>  <br/> |<span data-ttu-id="a8d69-186">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-186">No</span></span>  <br/> |<span data-ttu-id="a8d69-187">CqdBuilding 表的主键。</span><span class="sxs-lookup"><span data-stu-id="a8d69-187">Primary key for the CqdBuilding table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="a8d69-188">BuildingName</span></span>  <br/> |<span data-ttu-id="a8d69-189">varchar(80)</span><span class="sxs-lookup"><span data-stu-id="a8d69-189">varchar(80)</span></span>  <br/> |<span data-ttu-id="a8d69-190">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-190">No</span></span>  <br/> |<span data-ttu-id="a8d69-191">大楼名称。</span><span class="sxs-lookup"><span data-stu-id="a8d69-191">Building name.</span></span>  <br/> |
|<span data-ttu-id="a8d69-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="a8d69-192">BuildingShortName</span></span>  <br/> |<span data-ttu-id="a8d69-193">varchar(10)</span><span class="sxs-lookup"><span data-stu-id="a8d69-193">varchar(10)</span></span>  <br/> |<span data-ttu-id="a8d69-194">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-194">No</span></span>  <br/> |<span data-ttu-id="a8d69-195">大楼名称的简短版本。</span><span class="sxs-lookup"><span data-stu-id="a8d69-195">Shorter version of the Building name.</span></span>  <br/> |
|<span data-ttu-id="a8d69-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="a8d69-196">OwnershipTypeId</span></span>  <br/> |<span data-ttu-id="a8d69-197">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-197">int</span></span>  <br/> |<span data-ttu-id="a8d69-198">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-198">No</span></span>  <br/> |<span data-ttu-id="a8d69-199">外键，应与 CqdBuildingOwners 表中的其中一个条目匹配。</span><span class="sxs-lookup"><span data-stu-id="a8d69-199">Foreign key, should match one of the entreis in the CqdBuildingOwners table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="a8d69-200">BuildingTypeId</span></span>  <br/> |<span data-ttu-id="a8d69-201">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-201">int</span></span>  <br/> |<span data-ttu-id="a8d69-202">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-202">No</span></span>  <br/> |<span data-ttu-id="a8d69-203">外键，应与 CqdBuildingType 表中的其中一个条目匹配。</span><span class="sxs-lookup"><span data-stu-id="a8d69-203">Foreign key, should match one of the entries in the CqdBuildingType table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-204">纬度</span><span class="sxs-lookup"><span data-stu-id="a8d69-204">Latitutde</span></span>  <br/> |<span data-ttu-id="a8d69-205">float</span><span class="sxs-lookup"><span data-stu-id="a8d69-205">float</span></span>  <br/> |<span data-ttu-id="a8d69-206">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-206">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-207">大楼的纬度。</span><span class="sxs-lookup"><span data-stu-id="a8d69-207">Latitude of the building.</span></span>  <br/> |
|<span data-ttu-id="a8d69-208">经度</span><span class="sxs-lookup"><span data-stu-id="a8d69-208">Longitude</span></span>  <br/> |<span data-ttu-id="a8d69-209">float</span><span class="sxs-lookup"><span data-stu-id="a8d69-209">float</span></span>  <br/> |<span data-ttu-id="a8d69-210">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-210">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-211">大楼的经度。</span><span class="sxs-lookup"><span data-stu-id="a8d69-211">Longitude of the building.</span></span>  <br/> |
|<span data-ttu-id="a8d69-212">CityName</span><span class="sxs-lookup"><span data-stu-id="a8d69-212">CityName</span></span>  <br/> |<span data-ttu-id="a8d69-213">varchar(30)</span><span class="sxs-lookup"><span data-stu-id="a8d69-213">varchar(30)</span></span>  <br/> |<span data-ttu-id="a8d69-214">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-214">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-215">大楼所在的城市名称。</span><span class="sxs-lookup"><span data-stu-id="a8d69-215">City name where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a8d69-216">ZipCode</span><span class="sxs-lookup"><span data-stu-id="a8d69-216">ZipCode</span></span>  <br/> |<span data-ttu-id="a8d69-217">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="a8d69-217">varchar(25)</span></span>  <br/> |<span data-ttu-id="a8d69-218">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-218">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-219">大楼所在的邮编。</span><span class="sxs-lookup"><span data-stu-id="a8d69-219">Zip code where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a8d69-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="a8d69-220">CountryShortCode</span></span>  <br/> |<span data-ttu-id="a8d69-221">varchar(2)</span><span class="sxs-lookup"><span data-stu-id="a8d69-221">varchar(2)</span></span>  <br/> |<span data-ttu-id="a8d69-222">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-222">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-223">大楼所在的国家/地区的 ISO 3166-1 alpha-2 代码。</span><span class="sxs-lookup"><span data-stu-id="a8d69-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a8d69-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="a8d69-224">StateProvinceCode</span></span>  <br/> |<span data-ttu-id="a8d69-225">varchar(3)</span><span class="sxs-lookup"><span data-stu-id="a8d69-225">varchar(3)</span></span>  <br/> |<span data-ttu-id="a8d69-226">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-226">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-227">大楼所在的省/市/自治区的 3 字母缩写。</span><span class="sxs-lookup"><span data-stu-id="a8d69-227">3-letter abbreviation for the State/Province where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a8d69-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="a8d69-228">InsideCorp</span></span>  <br/> |<span data-ttu-id="a8d69-229">bit</span><span class="sxs-lookup"><span data-stu-id="a8d69-229">bit</span></span>  <br/> |<span data-ttu-id="a8d69-230">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-230">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-231">指明大楼是否是企业网络一部分的 bit（位）。</span><span class="sxs-lookup"><span data-stu-id="a8d69-231">Bit indicating whether the building is part of the corporate network.</span></span>  <br/> |
|<span data-ttu-id="a8d69-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="a8d69-232">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="a8d69-233">nvarchar(150)</span><span class="sxs-lookup"><span data-stu-id="a8d69-233">nvarchar(150)</span></span>  <br/> |<span data-ttu-id="a8d69-234">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-234">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-235">大楼办公室类型的说明。</span><span class="sxs-lookup"><span data-stu-id="a8d69-235">Description of the building office type.</span></span>  <br/> |
|<span data-ttu-id="a8d69-236">区域</span><span class="sxs-lookup"><span data-stu-id="a8d69-236">Region</span></span>  <br/> |<span data-ttu-id="a8d69-237">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="a8d69-237">varchar(25)</span></span>  <br/> |<span data-ttu-id="a8d69-238">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-238">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-239">大楼所在的地区。</span><span class="sxs-lookup"><span data-stu-id="a8d69-239">Region where the building is located.</span></span>  <br/> |
   
<span data-ttu-id="a8d69-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="a8d69-240">**CqdNetwork**</span></span>

|<span data-ttu-id="a8d69-241">**列**</span><span class="sxs-lookup"><span data-stu-id="a8d69-241">**Column**</span></span>|<span data-ttu-id="a8d69-242">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a8d69-242">**Data Type**</span></span>|<span data-ttu-id="a8d69-243">**是否允许 Null？**</span><span class="sxs-lookup"><span data-stu-id="a8d69-243">**Allow Nulls?**</span></span>|<span data-ttu-id="a8d69-244">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a8d69-244">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8d69-245">网络</span><span class="sxs-lookup"><span data-stu-id="a8d69-245">Network</span></span>  <br/> |<span data-ttu-id="a8d69-246">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="a8d69-246">varchar(25)</span></span>  <br/> |<span data-ttu-id="a8d69-247">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-247">No</span></span>  <br/> |<span data-ttu-id="a8d69-248">子网地址。</span><span class="sxs-lookup"><span data-stu-id="a8d69-248">Subnet address.</span></span>  <br/> |
|<span data-ttu-id="a8d69-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="a8d69-249">NetworkRange</span></span>  <br/> |<span data-ttu-id="a8d69-250">tinyint</span><span class="sxs-lookup"><span data-stu-id="a8d69-250">tinyint</span></span>  <br/> |<span data-ttu-id="a8d69-251">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-251">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-252">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="a8d69-252">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="a8d69-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="a8d69-253">NetworkNameID</span></span>  <br/> |<span data-ttu-id="a8d69-254">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-254">int</span></span>  <br/> |<span data-ttu-id="a8d69-255">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-255">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-256">可选地映射到 CqdNetworkName 表中的一行。</span><span class="sxs-lookup"><span data-stu-id="a8d69-256">Optionally maps to a row in CqdNetworkName table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="a8d69-257">BuildingKey</span></span>  <br/> |<span data-ttu-id="a8d69-258">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-258">int</span></span>  <br/> |<span data-ttu-id="a8d69-259">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-259">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-260">外键，应与 CqdBuilding 表中的其中一个条目匹配。</span><span class="sxs-lookup"><span data-stu-id="a8d69-260">Foreign key, should match one of the entries in the CqdBuilding table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="a8d69-261">UpdatedDate</span></span>  <br/> |<span data-ttu-id="a8d69-262">datetime</span><span class="sxs-lookup"><span data-stu-id="a8d69-262">datetime</span></span>  <br/> |<span data-ttu-id="a8d69-263">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-263">No</span></span>  <br/> |<span data-ttu-id="a8d69-264">条目最后更新的日期时间。</span><span class="sxs-lookup"><span data-stu-id="a8d69-264">Datetime for when the entry was last updated.</span></span>  <br/> |
   
<span data-ttu-id="a8d69-265">默认情况下一步该表有一个条目 (0，未知)。</span><span class="sxs-lookup"><span data-stu-id="a8d69-265">By default this next table has one entry (0, 'Unknown').</span></span>
  
<span data-ttu-id="a8d69-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="a8d69-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="a8d69-267">**列**</span><span class="sxs-lookup"><span data-stu-id="a8d69-267">**Column**</span></span>|<span data-ttu-id="a8d69-268">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a8d69-268">**Data Type**</span></span>|<span data-ttu-id="a8d69-269">**是否允许 Null？**</span><span class="sxs-lookup"><span data-stu-id="a8d69-269">**Allow Nulls?**</span></span>|<span data-ttu-id="a8d69-270">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a8d69-270">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8d69-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="a8d69-271">BuildingTypeId</span></span>  <br/> |<span data-ttu-id="a8d69-272">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-272">int</span></span>  <br/> |<span data-ttu-id="a8d69-273">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-273">No</span></span>  <br/> |<span data-ttu-id="a8d69-274">CqdBuildingType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="a8d69-274">Primary key for the CqdBuildingType table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="a8d69-275">BuildingTypeDesc</span></span>  <br/> |<span data-ttu-id="a8d69-276">char(18)</span><span class="sxs-lookup"><span data-stu-id="a8d69-276">char(18)</span></span>  <br/> |<span data-ttu-id="a8d69-277">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-277">No</span></span>  <br/> |<span data-ttu-id="a8d69-278">大楼类型说明。</span><span class="sxs-lookup"><span data-stu-id="a8d69-278">Building type description.</span></span>  <br/> |
   
<span data-ttu-id="a8d69-279">默认情况下一步该表具有一个条目 （0，未知，0，空）。</span><span class="sxs-lookup"><span data-stu-id="a8d69-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>
  
<span data-ttu-id="a8d69-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="a8d69-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="a8d69-281">**列**</span><span class="sxs-lookup"><span data-stu-id="a8d69-281">**Column**</span></span>|<span data-ttu-id="a8d69-282">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a8d69-282">**Data Type**</span></span>|<span data-ttu-id="a8d69-283">**是否允许 Null？**</span><span class="sxs-lookup"><span data-stu-id="a8d69-283">**Allow Nulls?**</span></span>|<span data-ttu-id="a8d69-284">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a8d69-284">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8d69-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="a8d69-285">OwnershipTypeId</span></span>  <br/> |<span data-ttu-id="a8d69-286">int</span><span class="sxs-lookup"><span data-stu-id="a8d69-286">int</span></span>  <br/> |<span data-ttu-id="a8d69-287">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-287">No</span></span>  <br/> |<span data-ttu-id="a8d69-288">CqdBuildingOwnershipType 表的主键。</span><span class="sxs-lookup"><span data-stu-id="a8d69-288">Primary key for the CqdBuildingOwnershipType table.</span></span>  <br/> |
|<span data-ttu-id="a8d69-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="a8d69-289">OwnershipTypeDesc</span></span>  <br/> |<span data-ttu-id="a8d69-290">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="a8d69-290">varchar(25)</span></span>  <br/> |<span data-ttu-id="a8d69-291">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-291">No</span></span>  <br/> |<span data-ttu-id="a8d69-292">所有权类型说明。</span><span class="sxs-lookup"><span data-stu-id="a8d69-292">Ownership type description.</span></span>  <br/> |
|<span data-ttu-id="a8d69-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="a8d69-293">LeaseInd</span></span>  <br/> |<span data-ttu-id="a8d69-294">tinyint</span><span class="sxs-lookup"><span data-stu-id="a8d69-294">tinyint</span></span>  <br/> |<span data-ttu-id="a8d69-295">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-295">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-296">引用 CqdBuildingOwnershipType 表中其他行的索引，用于确定租用的大楼。</span><span class="sxs-lookup"><span data-stu-id="a8d69-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span>  <br/> |
|<span data-ttu-id="a8d69-297">所有者</span><span class="sxs-lookup"><span data-stu-id="a8d69-297">Owner</span></span>  <br/> |<span data-ttu-id="a8d69-298">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="a8d69-298">varchar(50)</span></span>  <br/> |<span data-ttu-id="a8d69-299">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-299">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-300">大楼所有者。</span><span class="sxs-lookup"><span data-stu-id="a8d69-300">Building owner.</span></span>  <br/> |
   
<span data-ttu-id="a8d69-301">默认情况下一步该表具有一个条目 （0，未知，0，空）。</span><span class="sxs-lookup"><span data-stu-id="a8d69-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>
  
<span data-ttu-id="a8d69-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="a8d69-302">**CqdBssid**</span></span>

|<span data-ttu-id="a8d69-303">**列**</span><span class="sxs-lookup"><span data-stu-id="a8d69-303">**Column**</span></span>|<span data-ttu-id="a8d69-304">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a8d69-304">**Data Type**</span></span>|<span data-ttu-id="a8d69-305">**是否允许 Null？**</span><span class="sxs-lookup"><span data-stu-id="a8d69-305">**Allow Nulls?**</span></span>|<span data-ttu-id="a8d69-306">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a8d69-306">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8d69-307">bss</span><span class="sxs-lookup"><span data-stu-id="a8d69-307">bss</span></span>  <br/> |<span data-ttu-id="a8d69-308">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="a8d69-308">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a8d69-309">否</span><span class="sxs-lookup"><span data-stu-id="a8d69-309">No</span></span>  <br/> |<span data-ttu-id="a8d69-p117">CqdBssid 表的主键。是 WiFi 接入点的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p117">Primary key for the CqdBssid table. Is the BSSID of the Wifi Access Point.</span></span>  <br/> |
|<span data-ttu-id="a8d69-312">ess</span><span class="sxs-lookup"><span data-stu-id="a8d69-312">ess</span></span>  <br/> |<span data-ttu-id="a8d69-313">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="a8d69-313">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a8d69-314">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-314">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-315">WiFi 接入点控制器信息。</span><span class="sxs-lookup"><span data-stu-id="a8d69-315">Wifi Access Point Controller information.</span></span>  <br/> |
|<span data-ttu-id="a8d69-316">phy</span><span class="sxs-lookup"><span data-stu-id="a8d69-316">phy</span></span>  <br/> |<span data-ttu-id="a8d69-317">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="a8d69-317">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a8d69-318">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-318">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-319">Phy 信息。</span><span class="sxs-lookup"><span data-stu-id="a8d69-319">Phy information.</span></span>  <br/> |
|<span data-ttu-id="a8d69-320">ap</span><span class="sxs-lookup"><span data-stu-id="a8d69-320">ap</span></span>  <br/> |<span data-ttu-id="a8d69-321">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="a8d69-321">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a8d69-322">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-322">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-323">WiFi 接入点名称。</span><span class="sxs-lookup"><span data-stu-id="a8d69-323">Wifi Access Point Name.</span></span>  <br/> |
|<span data-ttu-id="a8d69-324">大楼</span><span class="sxs-lookup"><span data-stu-id="a8d69-324">Building</span></span>  <br/> |<span data-ttu-id="a8d69-325">nvarchar(500)</span><span class="sxs-lookup"><span data-stu-id="a8d69-325">nvarchar(500)</span></span>  <br/> |<span data-ttu-id="a8d69-326">是</span><span class="sxs-lookup"><span data-stu-id="a8d69-326">Yes</span></span>  <br/> |<span data-ttu-id="a8d69-327">WiFi 接入点所在大楼名称。</span><span class="sxs-lookup"><span data-stu-id="a8d69-327">The Building Name the Wifi Access Point is located in.</span></span>  <br/> |
   
## <a name="cqd-streams"></a><span data-ttu-id="a8d69-328">CQD 流</span><span class="sxs-lookup"><span data-stu-id="a8d69-328">CQD Streams</span></span>

<span data-ttu-id="a8d69-p118">CQD 流将为良好、较差或未分类。CQM 1.5 现在使用以下 CQD 定义：</span><span class="sxs-lookup"><span data-stu-id="a8d69-p118">A CQD stream will be good, poor or unclassified. CQM 1.5 now uses the following CQD definition:</span></span> 
  
- <span data-ttu-id="a8d69-331">较差流是超过阈值的较差呼叫指标的任意组合。</span><span class="sxs-lookup"><span data-stu-id="a8d69-331">A poor stream is any combination of the poor call metrics going beyond threshold.</span></span>
    
- <span data-ttu-id="a8d69-332">质量欠佳的调用中的一个流时，呼叫两个流是已标记的差。</span><span class="sxs-lookup"><span data-stu-id="a8d69-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="a8d69-333">在会议中每个参与者被视为唯一呼叫和独立于其他所有报告。</span><span class="sxs-lookup"><span data-stu-id="a8d69-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
    
- <span data-ttu-id="a8d69-334">未分类流是没有质量指标（即综合事务、短时间通话）的流。</span><span class="sxs-lookup"><span data-stu-id="a8d69-334">Unclassified streams are streams without quality metrics (i.e. Synthetic Transactions, short calls).</span></span>
    
- <span data-ttu-id="a8d69-335">有效流 = 非移动客户端</span><span class="sxs-lookup"><span data-stu-id="a8d69-335">Valid Streams = non-mobile clients</span></span>
    
- <span data-ttu-id="a8d69-336">分类器不能修改</span><span class="sxs-lookup"><span data-stu-id="a8d69-336">Classifier cannot be modified</span></span>
    
<span data-ttu-id="a8d69-337">**较差呼叫定义/分类器**</span><span class="sxs-lookup"><span data-stu-id="a8d69-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="a8d69-338">**指标**</span><span class="sxs-lookup"><span data-stu-id="a8d69-338">**Metric**</span></span>|<span data-ttu-id="a8d69-339">**阈值**</span><span class="sxs-lookup"><span data-stu-id="a8d69-339">**Threshold**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8d69-340">DDegradationAvg</span><span class="sxs-lookup"><span data-stu-id="a8d69-340">DDegradationAvg</span></span>  <br/> |<span data-ttu-id="a8d69-341">大于 1.0（-1 网络 MOS）</span><span class="sxs-lookup"><span data-stu-id="a8d69-341">Greater than 1.0 (-1 network MOS)</span></span>  <br/> |
|<span data-ttu-id="a8d69-342">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="a8d69-342">RoundTrip</span></span>  <br/> |<span data-ttu-id="a8d69-343">大于 500 </span><span class="sxs-lookup"><span data-stu-id="a8d69-343">Greater than 500</span></span>  <br/> |
|<span data-ttu-id="a8d69-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="a8d69-344">PacketLossRate</span></span>  <br/> |<span data-ttu-id="a8d69-345">大于 .1 (10%) </span><span class="sxs-lookup"><span data-stu-id="a8d69-345">Greater than .1 (10%)</span></span>  <br/> |
|<span data-ttu-id="a8d69-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="a8d69-346">JitterInterArrival</span></span>  <br/> |<span data-ttu-id="a8d69-347">大于 30 </span><span class="sxs-lookup"><span data-stu-id="a8d69-347">Greater than 30</span></span>  <br/> |
|<span data-ttu-id="a8d69-348">RRatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="a8d69-348">RRatioConcealedSamplesAvg</span></span>  <br/> |<span data-ttu-id="a8d69-349">大于 .07 </span><span class="sxs-lookup"><span data-stu-id="a8d69-349">Greater than .07</span></span>  <br/> |
   
<span data-ttu-id="a8d69-350">JPDR 定义 = 较差呼叫定义减去 RatioConcealedSamplesAvg </span><span class="sxs-lookup"><span data-stu-id="a8d69-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span> 
  
## <a name="where-is-callercallee"></a><span data-ttu-id="a8d69-351">呼叫方/被呼叫方在哪里？</span><span class="sxs-lookup"><span data-stu-id="a8d69-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="a8d69-352">CQD 不使用呼叫者/被叫方字段。</span><span class="sxs-lookup"><span data-stu-id="a8d69-352">CQD doesn't use Caller/Callee fields.</span></span> <span data-ttu-id="a8d69-353">由于存在且之间的呼叫者和被叫方的步骤，这些都已重命名"第一个"和"第二个"。</span><span class="sxs-lookup"><span data-stu-id="a8d69-353">These have been renamed "First" and "Second" because there are intervening steps between the caller and callee.</span></span>
  
 <span data-ttu-id="a8d69-354">
            如果流中涉及服务器，则\*\*第一个\*\*将始终是服务器端点（例如 AV MCU；中介服务器）。</span><span class="sxs-lookup"><span data-stu-id="a8d69-354">**First** Will always be the Server endpoint (e.g. AV MCU; Mediation Server) if a Server is involved in the stream.</span></span>
  
 <span data-ttu-id="a8d69-355">**第二个**将始终是客户端端点，除非是服务器-服务器流。</span><span class="sxs-lookup"><span data-stu-id="a8d69-355">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>
  
<span data-ttu-id="a8d69-356">**“第一个”和“第二个”分类示例**</span><span class="sxs-lookup"><span data-stu-id="a8d69-356">**Example of First and Second classification**</span></span>

|<span data-ttu-id="a8d69-357">\*\*端点 1 UAType \*\*</span><span class="sxs-lookup"><span data-stu-id="a8d69-357">**Endpoint 1 UAType**</span></span>|<span data-ttu-id="a8d69-358">\*\*端点 2 UUAType \*\*</span><span class="sxs-lookup"><span data-stu-id="a8d69-358">**Endpoint 2 UUAType**</span></span>|<span data-ttu-id="a8d69-359">**第一个**</span><span class="sxs-lookup"><span data-stu-id="a8d69-359">**First**</span></span>|<span data-ttu-id="a8d69-360">**第二个**</span><span class="sxs-lookup"><span data-stu-id="a8d69-360">**Second**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8d69-361">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="a8d69-361">2 (AVMCU)</span></span>  <br/> |<span data-ttu-id="a8d69-362">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="a8d69-362">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="a8d69-363">端点 1</span><span class="sxs-lookup"><span data-stu-id="a8d69-363">Endpoint 1</span></span>  <br/> |<span data-ttu-id="a8d69-364">端点 2</span><span class="sxs-lookup"><span data-stu-id="a8d69-364">Endpoint 2</span></span>  <br/> |
|<span data-ttu-id="a8d69-365">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="a8d69-365">2 (AVMCU)</span></span>  <br/> |<span data-ttu-id="a8d69-366">1 (mMediationServer) </span><span class="sxs-lookup"><span data-stu-id="a8d69-366">1 (mMediationServer)</span></span>  <br/> |<span data-ttu-id="a8d69-367">端点 2</span><span class="sxs-lookup"><span data-stu-id="a8d69-367">Endpoint 2</span></span>  <br/> |<span data-ttu-id="a8d69-368">端点 1</span><span class="sxs-lookup"><span data-stu-id="a8d69-368">Endpoint 1</span></span>  <br/> |
|<span data-ttu-id="a8d69-369">4 (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="a8d69-369">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="a8d69-370">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="a8d69-370">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="a8d69-371">MediaLine 中的呼叫方 </span><span class="sxs-lookup"><span data-stu-id="a8d69-371">The Caller in MediaLine</span></span>  <br/> |<span data-ttu-id="a8d69-372">MMediaLine 中的被呼叫方</span><span class="sxs-lookup"><span data-stu-id="a8d69-372">The Callee in MMediaLine</span></span>  <br/> |
   
<span data-ttu-id="a8d69-373">如果两个端点是相同类型，CQD 将“呼叫方”条目设为“第一个”，而“被呼叫方”则为“第二个”。</span><span class="sxs-lookup"><span data-stu-id="a8d69-373">If both endpoints are the same type, CQD will make the Caller entry First and Callee will become Second.</span></span> <span data-ttu-id="a8d69-374">请参阅[此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8d69-374">See [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx) for more information.</span></span>
  
## <a name="accounting-for-vpn"></a><span data-ttu-id="a8d69-375">VPN 考虑事项</span><span class="sxs-lookup"><span data-stu-id="a8d69-375">Accounting for VPN</span></span>

<span data-ttu-id="a8d69-376">VPN 解决方案已知准确设置 VPN 标志，如果您所有设置。</span><span class="sxs-lookup"><span data-stu-id="a8d69-376">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="a8d69-377">否则，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="a8d69-377">Otherwise, use one of the methods below:</span></span>
  
- <span data-ttu-id="a8d69-378">创建名为 VPN 的网络类型（首选），然后将 VPN 子网与此新 VPN 网络类型关联。</span><span class="sxs-lookup"><span data-stu-id="a8d69-378">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
    
- <span data-ttu-id="a8d69-379">创建名为 VPN 的大楼，然后将 VPN 子网与此大楼关联。</span><span class="sxs-lookup"><span data-stu-id="a8d69-379">Create a building called VPN, then Associate VPN Subnets with this building.</span></span> 
    
## <a name="query-fundamentals"></a><span data-ttu-id="a8d69-380">查询基础知识</span><span class="sxs-lookup"><span data-stu-id="a8d69-380">Query Fundamentals</span></span>

<span data-ttu-id="a8d69-381">格式正确的查询包含以下三个参数：</span><span class="sxs-lookup"><span data-stu-id="a8d69-381">A well-formed query contains all three of these parameters:</span></span> 
  
- <span data-ttu-id="a8d69-382">度量</span><span class="sxs-lookup"><span data-stu-id="a8d69-382">Measurement</span></span>
    
- <span data-ttu-id="a8d69-383">维度</span><span class="sxs-lookup"><span data-stu-id="a8d69-383">Dimension</span></span>
    
- <span data-ttu-id="a8d69-384">筛选器</span><span class="sxs-lookup"><span data-stu-id="a8d69-384">Filter</span></span>
    
<span data-ttu-id="a8d69-385">例如，“按子网[维度]显示大楼 6 [筛选器]的较差流[度量]”是一个格式正确的查询。</span><span class="sxs-lookup"><span data-stu-id="a8d69-385">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>
  
## <a name="what-does-union-do"></a><span data-ttu-id="a8d69-386">“联合”起什么作用？</span><span class="sxs-lookup"><span data-stu-id="a8d69-386">What does UNION do?</span></span>

<span data-ttu-id="a8d69-p123">通过“联合”可以使用“与”运算符筛选条件。在一些方案中，你需要将多个筛选条件组合在一起来获得类似“或”的结果。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p123">Union allows you to filter conditions using the AND operator. There are scenarios where you need to combine multiple Filter conditions together to achieve an OR like result</span></span>
  
<span data-ttu-id="a8d69-p124">例如，当你需要从大楼获取所有流时，“联合”将提供合并数据集的独特视图。要使用“联合”，请在你要联合的两个筛选条件上的“联合”字段中插入普通文本。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p124">Example: When you need to get all streams from a building UNION will provide a distinct view of the merged dataset. To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span> 
  
## <a name="default-report-breakdown"></a><span data-ttu-id="a8d69-391">默认报告细分</span><span class="sxs-lookup"><span data-stu-id="a8d69-391">Default Report Breakdown</span></span>

<span data-ttu-id="a8d69-392">如果在内部管理无线，你可以在管理存储桶中重新创建“无线”报告。</span><span class="sxs-lookup"><span data-stu-id="a8d69-392">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span> 
  
![CQD 报告细分](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a><span data-ttu-id="a8d69-394">可选过程</span><span class="sxs-lookup"><span data-stu-id="a8d69-394">Operational Processes</span></span>

<span data-ttu-id="a8d69-p125">首先查看并更正管理流。此区域中的质量应该完全在你的控制范围内，因此最容易修复。</span><span class="sxs-lookup"><span data-stu-id="a8d69-p125">Start by reviewing and remediating Managed Streams. Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span> 
  
### <a name="managed-streams"></a><span data-ttu-id="a8d69-397">管理流 </span><span class="sxs-lookup"><span data-stu-id="a8d69-397">Managed Streams</span></span>

<span data-ttu-id="a8d69-398">按以下顺序查看并更正管理流：</span><span class="sxs-lookup"><span data-stu-id="a8d69-398">Review and remediate managed streams in the following order:</span></span> 
  
1. <span data-ttu-id="a8d69-399">服务器-服务器 </span><span class="sxs-lookup"><span data-stu-id="a8d69-399">Server-Server</span></span> 
    
2.  <span data-ttu-id="a8d69-400"> 服务器-有线-内部</span><span class="sxs-lookup"><span data-stu-id="a8d69-400">Server-Wired-Inside</span></span>
    
3. <span data-ttu-id="a8d69-401">有线-有线-内部 </span><span class="sxs-lookup"><span data-stu-id="a8d69-401">Wired-Wired-Inside</span></span> 
    
### <a name="unmanaged-streams"></a><span data-ttu-id="a8d69-402">非管理流</span><span class="sxs-lookup"><span data-stu-id="a8d69-402">Unmanaged Streams</span></span>

<span data-ttu-id="a8d69-403">按以下顺序查看并更正非管理流：</span><span class="sxs-lookup"><span data-stu-id="a8d69-403">Review and remediate unmanaged streams in the following order:</span></span> 
  
1. <span data-ttu-id="a8d69-404">服务器-WiFi-内部</span><span class="sxs-lookup"><span data-stu-id="a8d69-404">Server-Wifi-Inside</span></span>
    
2. <span data-ttu-id="a8d69-405">服务器-有线-外部</span><span class="sxs-lookup"><span data-stu-id="a8d69-405">Server-Wired-Outside</span></span>
    
3. <span data-ttu-id="a8d69-406">服务器-WiFi-外部</span><span class="sxs-lookup"><span data-stu-id="a8d69-406">Server-Wifi-Outside</span></span>
    
4. <span data-ttu-id="a8d69-407">有线-外部-直接</span><span class="sxs-lookup"><span data-stu-id="a8d69-407">Wired-Outside-Direct</span></span>
    
5. <span data-ttu-id="a8d69-408">有线-外部-中继</span><span class="sxs-lookup"><span data-stu-id="a8d69-408">Wired-Outside-Relay</span></span>
    
6. <span data-ttu-id="a8d69-409">其他非管理</span><span class="sxs-lookup"><span data-stu-id="a8d69-409">Other Unmanaged</span></span>
    

