---
title: 运行状况和使用情况报告
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 报告报表运行状况和使用情况的节点数据
f1keywords: ''
ms.openlocfilehash: 87a04860a69799bf00492691dc24498076bd4924
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271427"
---
# <a name="health-and-usage-reports"></a>运行状况和使用情况报告

报告节点包含有关 Microsoft 托管会议室和服务见解的运行状况和使用情况的数据。 **概述介绍了** 房间的租户范围的运行状况趋势。 “ **运行状况** ”选项卡显示包含相应运行状况数据的会议室列表。 基于日历信息和通话质量数据的房间使用情况在“ **使用** 情况”选项卡下可见。

## <a name="navigating-reports"></a>导航报表

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

概述部分提供会议室管理重要方面的图形表示形式。 图表将根据所选时间范围或所选组更改。 若要更改时间跨度，请单击下拉菜单。

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

若要更改组，请单击横幅中的组选择下拉菜单。

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>按类别排列的票证

该甜甜圈显示为所选时间跨度引发的总票证，组 (默认值为 7 天，所有组) 。 票证以其主要类别表示：音频、显示、外围设备、连接、版本控制和客户报告。

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

选中时会显示该类别票证的详细视图的浮出控件。

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

在浮出控件中，可以通过选择甜甜圈的相应部分，按子类别筛选票证列表。 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

若要导航回来，请单击圆环或单击左上角的痕迹。

若要导航到此列表视图中的特定票证，请单击 **“支持票证”库** 下的链接。

### <a name="ticket-history"></a>票证历史记录

票证历史记录图显示指定时间段内分配给你或 Microsoft 的事件的比较。

> [!NOTE]
> 如果票证在一天内更改了所有者，则无论谁拥有当天大部分时间的分配，都将将票证计入他们。 例如，如果在当天早期将票证分配给 Microsoft，则该票证将计入当天 **分配给 Microsoft** 的票证。

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>运行状况历史记录

此图显示了运行状况部分) 租户中所有房间的平均运行状况 (定义，以及所有 MMR 客户的日常运行状况。 最多可以查看 90 天的平均运行状况。

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>最可靠/最不可靠的房间

两个表根据运行状况显示最可靠、最不可靠的房间。 对于完整列表视图，请选择“运行状况”，然后按“运行状况”列对列表进行排序。

### <a name="rooms-history"></a>会议室历史记录

提供服务中注册的会议室的历史视图，并提供在同一时间段内正常或不受监视的房间的比较视图。

## <a name="health"></a>运行状况

若要导航到所有会议室的运行状况报告，请选择“报表”，然后选择  **“运行状况**”。

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

运行状况分数是一个指标，旨在显示最有可能导致最终用户沮丧的会议室。 一个房间在给定的一天可以是健康或不健康的。 如果票证或许多票证在非维护时段内影响房间超过 20 分钟，则会被视为不正常， (本地时间 5AM -9PM 计算机) 。 例如，如果票证在凌晨 5：00 打开，但在凌晨 5：15 关闭，则该房间仍被视为正常。 但是，如果第二张票发生在上午 09：00 到上午 9：10，则该房间将被视为当天不正常。 同样，如果票证发生在凌晨 5：00 到 5：21AM，则该日期被视为不正常。

> [!NOTE]
> 每天的运行状况在 UTC 时间上午 12：00 聚合一次。 对于接近国际日期线的客户，运行状况聚合可能会在工作日中间附近发生。

> [!NOTE]
> 载入的会议室隐藏在“运行状况”选项卡中的会议室列表中，不计入租户的平均运行状况。

单击此视图中列出的会议室会显示更多详细信息。

条形图显示每天的票证数。 当天打开的门票显示为蓝色。 当天之前打开的门票以橙色显示。 单击图形上的一天会将饼图和表格筛选到相关票证。 若要反转筛选器，请使用痕迹导航或单击图形。

票证分类在环形图中表示。 与此交互会筛选时间线图和表。 若要反转筛选器，请使用痕迹导航或单击图形。

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

会议影响视图显示计划的会议，在此期间，打开了严重性为“重要”或“严重”的票证。 此视图的目的是提供与会者可能遇到问题的会议的近似值。

会议影响视图显示计划的会议，在此期间，打开了严重性为“重要”或“严重”的票证。 此视图的目的是提供与会者可能遇到问题的会议的近似值。

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

“设置”选项卡显示会议室的元数据，例如硬件信息、设备设置、BIOS 信息、应用设置和位置。

## <a name="usage"></a>用法

若要查看所有会议室的使用情况报告，请选择 **“报表>使用情况**”。

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

头条新闻提供了一些见解：

- 租户中的总房间数
- 有多少人没有预订过任何会议，无论是脱机会议还是联机会议
- 租户中房间使用率的百分比
- 通过交换预订的会议总数
- 包含 Skype 或 Teams 链接的已预订会议百分比
- 参与会议室的总呼叫数
- 对所有调用使用“良好”质量分类的所有调用聚合调用性能分数。 

标题指标下方是具有相应指标的会议室表。 选择一个房间以查看更多使用情况详细信息。 下表描述了表中的指标。

|列|说明|
|---|---|
|利用|在所选时间内，在工作时间内预订房间的时间百分比。 前。 时间段设置为 7 天。 80% 的利用率超过预订了 32/40 小时的房间|
|联机预订|在已预订的会议中，使用 Teams 启用的百分比。 前。 预订了 10 次会议。 其中 8 个具有 Teams 链接。 已预订联机 = 80%|
|计划内会议|会议室中安排的会议的绝对数量|
|总呼叫数|以参与者身份与会议室通话的绝对次数。|
调用性能|具有“良好”分级的调用的百分比。 对每个调用进行评估，并收到“良好”、“差”、“未知”分级。 此指标是根据好调用/总调用数计算得出的|

使用情况计算在每天午夜 (00：00) 会议室设备的本地时间。 利用率是根据当天预订的总会议时间除以 8 小时计算的。

## <a name="usage-details-of-a-room"></a>会议室的使用情况详细信息

单击列表视图中的某个房间会提示浮出控件，其中包含更深入的信息。 浮出控件的“利用率”选项卡下是一个显示过去五个工作日使用小时数的图表。 每天有两个条形：蓝色表示已预订的会议时间：紫色表示已启用 Teams/Skype 的会议的计划时间。 在底部，计算过去五个工作日的平均会议预订和持续时间。

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

**“呼叫**”表显示会议室参与 Teams 呼叫的会议。 会议室音频质量仅针对会议室（而不是所有参与者）进行评估。 若要查看特定呼叫的所有参与者的呼叫质量，请单击“开始时间”选择呼叫。

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

若要查看会议室的流详细信息，请单击“会话开始时间”。
