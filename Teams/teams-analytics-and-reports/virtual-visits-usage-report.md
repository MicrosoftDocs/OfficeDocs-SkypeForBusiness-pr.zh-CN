---
title: Microsoft Teams虚拟访问使用情况报告
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在Microsoft Teams管理中心使用虚拟访问使用情况报告来获取组织中虚拟约会活动的概述。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853213"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams虚拟访问使用情况报告

Microsoft Teams管理中心的“虚拟访问”使用情况报告概述了组织中的Teams虚拟约会活动。 可以通过[Bookings应用](../expand-teams-across-your-org/bookings-virtual-visits.md)和[Microsoft Teams电子运行状况记录 (EHR) 连接器](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration)查看计划的虚拟约会的详细活动。

若要查看报表，必须是全局管理员或Teams管理员。

报表包含以下选项卡。 将在报表中看到的信息取决于你是否拥有Bookings应用、Teams EHR 连接器的许可证，或者两者兼有。

|选项 卡 |说明  |
|---------|---------|
|**[虚拟访问](#virtual-visits)**     |显示虚拟约会总数，其中列出了使用Bookings应用安排的约会数，并Teams EHR 系统进行的 EHR 集成会议。         |
|**[持续时间](#duration)**     |显示约会的平均持续时间和参与者的平均大厅等待时间。         |
|**[Bookings](#bookings)**     |显示通过Bookings应用安排的约会数。         |
|**[EHR](#ehr)**     |显示从 EHR 系统进行的Teams EHR 集成约会的数量。         |  

使用此报告可以深入了解组织的虚拟约会活动和趋势。 这些信息可以帮助你优化虚拟约会，以提供更好的业务成果。

## <a name="view-the-virtual-visits-usage-report"></a>查看虚拟访问使用情况报告

1. 在Microsoft Teams管理中心的左侧导航中，选择 **“分析”& reportsUsage** >  **报表**。 在 **“查看报表** ”选项卡上的 **“报** 表”下，选择 **“虚拟访问使用情况**”。
2. 在 **“日期”范围** 下，选择日期范围为 7 天、30 天或 90 天。 然后，选择 **“运行报表**”。

> [!NOTE]
> 默认情况下，虚拟访问分析处于打开状态，报表可用。 通过使用此报表，你将授予 Microsoft 在组织中收集有关虚拟约会的数据的权限。 有关数据保留策略的信息，请参阅[Microsoft 365中的数据保留、删除和销毁](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。
>
>如果要关闭组织的报表，可以在页面右上角 **的设置** 中执行此操作。 此设置在更改后可能需要 0 (零) 到 2 小时才能生效。

## <a name="interpret-the-report"></a>解释报告

### <a name="virtual-visits"></a>虚拟访问

你将在此处看到的图形取决于你是否拥有Bookings应用、Teams EHR 连接器的许可证，或者两者兼有。 若要了解详细信息，请参阅[“管理Bookings应用](../bookings-app-admin.md)，并[集成到 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 或[集成到 Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="“虚拟访问”使用情况报告的“虚拟访问”选项卡的屏幕截图，其中显示了编号标注。" lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有生成报表的日期。 报告通常反映活动时间的 24 到 48 小时延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴是约会数。<br>将鼠标悬停在给定日期上的点上，以查看该日期的约会数。|
|**3**   |可以通过选择图例中的项来筛选在图表上看到的内容。 例如，选择 **“虚拟访问总数 Bookings”或**“**EHR 虚拟访问总数**”，以仅查看与每个访问相关的信息。 更改此选项不会更改表格中的信息。 |
|**4**   |该表提供有关在所选日期范围内发生的每个约会的详细信息。 <ul><li>**开始时间 (UTC)** 是工作人员和参与者参加会议的日期和时间，或者是会议中第一个活动发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间** 是参与者第一次加入大厅到同一参与者或其他参与者被工作人员接纳参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间之间的时差。 如果工作人员和参与者均未加入会议，则持续时间显示为 0 (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个工作人员和参与者加入会议，会议已经结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **无显示**：如果一名工作人员加入会议，但没有其他人加入，会议已经结束。 </li></ul> </li> <li>**会议类型** 指示是通过Bookings应用还是Teams EHR 连接器计划虚拟约会。</li> <li>**与会者** 是会议工作人员和参与者的总数。</li> <li>**发送的短信** 指示是否向与会者发送了短信通知。 </li> </li> </ul> |
|**5**   |选择 **设置** 打开 **“虚拟访问分析**”窗格。 在此处，可以关闭或打开组织的虚拟访问报告，并在表中添加或删除列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |可以将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到Excel**”，然后在 **“下载**”选项卡上选择“**下载**”以在报表准备就绪时下载报表。|

### <a name="duration"></a>持续时间

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="显示编号标注的“虚拟访问使用情况”报表的“持续时间”选项卡的屏幕截图。" lightbox="../media/virtual-visits-usage-report-duration.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有生成报表的日期。 报告通常反映活动时间的 24 到 48 小时延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴是分钟数。<br>将鼠标悬停在给定日期的点上，查看给定日期的平均约会持续时间或平均大厅等待时间。  |
|**3**   |可以通过选择图例中的项来筛选在图表上看到的内容。 例如，选择 **“平均虚拟访问持续时间** ”或“ **平均大厅等待时间** ”，以仅查看与每个访问时间相关的信息。 更改此选项不会更改表格中的信息。 |
|**4**   |该表提供有关在所选日期范围内发生的每个约会的详细信息。 <ul><li>**开始时间 (UTC)** 是工作人员和参与者参加会议的日期和时间，或者是会议中第一个活动发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间** 是参与者第一次加入大厅到同一参与者或其他参与者被工作人员接纳参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间之间的时差。 如果工作人员和参与者均未加入会议，则持续时间显示为 0 (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个工作人员和参与者加入会议，会议已经结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **无显示**：如果一名工作人员加入会议，但没有其他人加入，会议已经结束。 </li></ul> </li> <li>**会议类型** 指示是通过Bookings应用还是Teams EHR 连接器计划虚拟约会。</li> <li>**与会者** 是会议工作人员和参与者的总数。</li> <li>**发送的短信** 指示是否向与会者发送了短信通知。 </li> </li> </ul>|
|**5**   |选择 **设置** 打开 **“虚拟访问分析**”窗格。 在此处，可以关闭或打开组织的虚拟访问报告，并在表中添加或删除列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |可以将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到Excel**”，然后在 **“下载**”选项卡上选择“**下载**”以在报表准备就绪时下载报表。|
### <a name="bookings"></a>Bookings

如果你有包含Bookings应用的许可证，你将看到此选项卡。 若要了解详细信息，请参阅[“管理Bookings应用](../bookings-app-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="“虚拟访问使用情况”报表的“Bookings”选项卡的屏幕截图，其中显示了编号标注。" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有生成报表的日期。 报告通常反映活动时间的 24 到 48 小时延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴是Bookings约会的数量。<br>将鼠标悬停在给定日期的点上，查看该日期发生的Bookings约会数。|
|**3**   |该表提供有关在所选日期范围内发生的每个约会的详细信息。 <ul><li>**开始时间 (UTC)** 是工作人员和参与者参加会议的日期和时间，或者是会议中第一个活动发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间** 是参与者第一次加入大厅到同一参与者或其他参与者被工作人员接纳参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间之间的时差。 如果工作人员和参与者均未加入会议，则持续时间显示为 0 (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个工作人员和参与者加入会议，会议已经结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **无显示**：如果一名工作人员加入会议，但没有其他人加入，会议已经结束。 </li></ul> </li> <li>**会议类型** 指示是通过Bookings应用还是Teams EHR 连接器计划虚拟约会。</li> <li>**与会者** 是会议工作人员和参与者的总数。</li> <li>**发送的短信** 指示是否向与会者发送了短信通知。 </li> </li> </ul>|
|**4**   |选择 **设置** 打开 **“虚拟访问分析**”窗格。 在此处，可以关闭或打开组织的虚拟访问报告，并在表中添加或删除列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |可以将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到Excel**”，然后在 **“下载**”选项卡上选择“**下载**”以在报表准备就绪时下载报表。|
### <a name="ehr"></a>EHR

如果许可证包含 Teams EHR 连接器，则会看到此选项卡。 若要了解详细信息，请参阅 [与 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 集成或 [集成到 Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="显示编号标注的“虚拟访问使用情况”报表的“EHR”选项卡的屏幕截图。" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有生成报表的日期。 报告通常反映活动时间的 24 到 48 小时延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴是 EHR 约会的数量。<br>将鼠标悬停在给定日期上的点上，以查看该日期的 EHR 约会数。|
|**3**   |该表提供有关在所选日期范围内发生的每个约会的详细信息。 <ul><li>**开始时间 (UTC)** 是工作人员和参与者参加会议的日期和时间，或者是会议中第一个活动发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间** 是参与者第一次加入大厅到同一参与者或其他参与者被工作人员接纳参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间之间的时差。 如果工作人员和参与者均未加入会议，则持续时间显示为 0 (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个工作人员和参与者加入会议，会议已经结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **无显示**：如果一名工作人员加入会议，但没有其他人加入，会议已经结束。 </li></ul> </li> <li>**会议类型** 指示是通过Bookings应用还是Teams EHR 连接器计划虚拟约会。</li> <li>**与会者** 是会议工作人员和参与者的总数。</li> <li>**发送的短信** 指示是否向与会者发送了短信通知。 </li> </li> </ul>|
|**4**   |选择 **设置** 打开 **“虚拟访问分析**”窗格。 在此处，可以关闭或打开组织的虚拟访问报告，并在表中添加或删除列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |可以将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到Excel**”，然后在 **“下载**”选项卡上选择“**下载**”以在报表准备就绪时下载报表。|

> [!NOTE]
> 如果你的组织希望参与非管理员用户（例如业务决策者）访问和查看此报告的专用预览版，请 [联系我们](mailto:tapmwtanalytics@microsoft.com)。

## <a name="related-articles"></a>相关文章

- [Teams 分析和报告](teams-reporting-reference.md)
- [使用Teams和Bookings应用进行虚拟约会](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [使用 Teams 的虚拟约会 - 集成到 Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [使用 Teams 的虚拟约会 - 集成到 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
