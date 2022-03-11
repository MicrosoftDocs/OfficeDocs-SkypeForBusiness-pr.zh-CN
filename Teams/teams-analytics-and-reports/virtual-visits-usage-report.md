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
description: 了解如何使用 Microsoft Teams 管理中心中的虚拟访问使用情况报告，获取组织中虚拟访问活动的概述。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b3432ea92ad89c5304d81b266fce61fb9b95d5b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435846"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams虚拟访问使用情况报告

管理中心中的虚拟Microsoft Teams使用情况报告概述了Teams虚拟访问活动。 可以查看通过 [Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) 应用安排的虚拟约会的详细活动，以及 [EHR Microsoft Teams连接器 (电子) 活动](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)。

若要查看报表，您必须是全局管理员或Teams管理员。

报表包含以下选项卡。 在报告中看到的信息取决于你是否拥有 Bookings 应用、Teams EHR 连接器的许可证。

|Tab |说明  |
|---------|---------|
|**[虚拟访问](#virtual-visits)**     |显示虚拟访问总数，并细分使用 Bookings 应用安排的访问数，以及从 EHR Teams EHR 集成会议。         |
|**[持续时间](#duration)**     |显示平均访问持续时间和参与者的平均大厅等待时间。         |
|**[Bookings](#bookings)**     |显示通过 Bookings 应用计划的访问数。         |
|**[EHR](#ehr)**     |显示从 EHR Teams EHR 集成的访问次数。         |  

使用此报告可以深入了解组织的虚拟访问活动和趋势。 这些信息可帮助优化虚拟访问，以提供更好的业务成果。

## <a name="view-the-virtual-visits-usage-report"></a>查看虚拟访问使用情况报告

1. 在管理中心的左侧导航Microsoft Teams，选择 **"分析&报表** > **""管理报表"**。 在" **查看报表"选项卡** 上的"报表 **"下**，选择" **虚拟访问使用情况"**。
2. 在 **"日期** 范围"下，选择 7 天、30 天或 90 天的日期范围。 然后选择"运行 **报表"**。

> [!NOTE]
> 默认情况下，虚拟访问分析已打开，并且报表可用。 使用此报告，你向 Microsoft 授予了收集组织中虚拟访问数据的权限。 有关数据保留策略的信息，请参阅数据[保留、删除](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)和销毁Microsoft 365。
>
>如果要为组织关闭报表，可以在页面右上角设置关闭报表。 此设置可能需要 0 到 0 (0) 2 小时才能在更改后生效。

## <a name="interpret-the-report"></a>解释报告

### <a name="virtual-visits"></a>虚拟访问

此处显示的图形取决于你是否拥有 Bookings 应用和/或 EHR 连接器Teams许可证。 若要了解详情，请参阅 [管理 Bookings 应用](../bookings-app-admin.md)和集成到 [Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 或 [集成到 Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md) 中。

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="显示编号标注的虚拟访问使用情况报告的"虚拟访问"选项卡的屏幕截图。" lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成报告的日期。 报告通常反映从活动时间到 24 到 48 小时的延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴表示访问次数。<br>将鼠标悬停在给定日期上的点上以查看该日期的访问次数。|
|**3**   |可以通过选择图例中的项目来筛选在图表上看到的项目。 例如，选择" **总预订虚拟访问数** "或" **EHR 虚拟访问** 总数"，仅查看与每项虚拟访问有关的信息。 更改此选项不会更改表格中的信息。 |
|**4**   |下表提供有关在所选日期范围内进行的每个访问的详细信息。 <ul><li>**开始时间 (UTC**) 是职员和参与者同时参加会议或第一个活动在会议发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间是** 参与者首次加入大厅到该同一参与者或其他参与者被职员获准参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间差。 如果职员和参与者都未加入会议，持续时间将显示为 0， (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个职员和参与者加入会议并且会议已结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **未显示**：如果一位职员加入会议，但其他人没有加入，并且会议已结束。 </li></ul> </li> <li>**会议** 类型指示虚拟约会是通过 Bookings 应用还是 EHR 连接器Teams计划。</li> <li>**与会者** 是会议中的职员和参与者总数。</li> <li>**短信** 发送指示是否已向与会者发送短信通知。 </li> </li> </ul> |
|**5**   |选择 **设置** 打开"**虚拟访问分析"** 窗格。 在此处，可以关闭或打开组织的虚拟访问报告，以及添加或删除表中的列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |可以将报表导出到 CSV 文件进行脱机分析。 选择 **"导出Excel**，然后在 **"下载"** 选项卡上选择"下载"，在报表准备就绪后下载报表。|

### <a name="duration"></a>持续时间

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="显示编号标注的虚拟访问使用情况报告的"持续时间"选项卡的屏幕截图。" lightbox="../media/virtual-visits-usage-report-duration.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成报告的日期。 报告通常反映从活动时间到 24 到 48 小时的延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴表示分钟数。<br>将鼠标悬停在给定日期的点上，查看给定日期的平均访问持续时间或大厅平均等待时间。  |
|**3**   |可以通过选择图例中的项目来筛选在图表上看到的项目。 例如，选择 **"平均虚拟访问持续时间** "或 **"平均大厅** 等待时间"，仅查看与每个虚拟访问持续时间相关的信息。 更改此选项不会更改表格中的信息。 |
|**4**   |下表提供有关在所选日期范围内进行的每个访问的详细信息。 <ul><li>**开始时间 (UTC**) 是职员和参与者同时参加会议或第一个活动在会议发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间是** 参与者首次加入大厅到该同一参与者或其他参与者被职员获准参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间差。 如果职员和参与者都未加入会议，持续时间将显示为 0， (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个职员和参与者加入会议并且会议已结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **未显示**：如果一位职员加入会议，但其他人没有加入，并且会议已结束。 </li></ul> </li> <li>**会议** 类型指示虚拟约会是通过 Bookings 应用还是 EHR 连接器Teams计划。</li> <li>**与会者** 是会议中的职员和参与者总数。</li> <li>**短信** 发送指示是否已向与会者发送短信通知。 </li> </li> </ul>|
|**5**   |选择 **设置** 打开"**虚拟访问分析"** 窗格。 在此处，可以关闭或打开组织的虚拟访问报告，以及添加或删除表中的列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |可以将报表导出到 CSV 文件进行脱机分析。 选择 **"导出Excel**，然后在 **"下载"** 选项卡上选择"下载"，在报表准备就绪后下载报表。|
### <a name="bookings"></a>Bookings

如果你的许可证包含 Bookings 应用，你将看到此选项卡。 若要了解详情，请参阅 [管理 Bookings 应用](../bookings-app-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="虚拟访问使用情况报表的"预订"选项卡的屏幕截图，显示编号标注。" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成报告的日期。 报告通常反映从活动时间到 24 到 48 小时的延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴表示 Bookings 访问次数。<br>将鼠标悬停在给定日期的点上，查看该日期发生的 Bookings 访问次数。|
|**3**   |下表提供有关在所选日期范围内进行的每个访问的详细信息。 <ul><li>**开始时间 (UTC**) 是职员和参与者同时参加会议或第一个活动在会议发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间是** 参与者首次加入大厅到该同一参与者或其他参与者被职员获准参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间差。 如果职员和参与者都未加入会议，持续时间将显示为 0， (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个职员和参与者加入会议并且会议已结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **未显示**：如果一位职员加入会议，但其他人没有加入，并且会议已结束。 </li></ul> </li> <li>**会议** 类型指示虚拟约会是通过 Bookings 应用还是 EHR 连接器Teams计划。</li> <li>**与会者** 是会议中的职员和参与者总数。</li> <li>**短信** 发送指示是否已向与会者发送短信通知。 </li> </li> </ul>|
|**4**   |选择 **设置** 打开"**虚拟访问分析"** 窗格。 在此处，可以关闭或打开组织的虚拟访问报告，以及添加或删除表中的列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |可以将报表导出到 CSV 文件进行脱机分析。 选择 **"导出Excel**，然后在 **"下载"** 选项卡上选择"下载"，在报表准备就绪后下载报表。|
### <a name="ehr"></a>EHR

如果拥有包含 EHR 连接器的许可证，Teams选项卡。 有关详细信息，请参阅集成到 [Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 或 [集成到长篇 EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md) 中。

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="虚拟访问使用情况报表的 EHR 选项卡的屏幕截图，显示编号标注。" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成报告的日期。 报告通常反映从活动时间到 24 到 48 小时的延迟。 |
|**2**   |X 轴是报表的选定日期范围。 Y 轴表示 EHR 访问次数。<br>将鼠标悬停在给定日期的点上以查看该日期的 EHR 访问次数。|
|**3**   |下表提供有关在所选日期范围内进行的每个访问的详细信息。 <ul><li>**开始时间 (UTC**) 是职员和参与者同时参加会议或第一个活动在会议发生的日期和时间。  </li> <li>**会议 ID** 是会议的唯一 ID。</li> <li>**大厅等待时间是** 参与者首次加入大厅到该同一参与者或其他参与者被职员获准参加会议之间的时间。</li><li>**持续时间** 是开始时间和最后一个人离开会议的时间差。 如果职员和参与者都未加入会议，持续时间将显示为 0， (零) 。</li> <li>**状态** 显示会议状态。 <ul><li>**已完成**：如果一个或多个职员和参与者加入会议并且会议已结束。 或者，如果一个或多个参与者加入会议并且会议已结束。</li> <li> **未显示**：如果一位职员加入会议，但其他人没有加入，并且会议已结束。 </li></ul> </li> <li>**会议** 类型指示虚拟约会是通过 Bookings 应用还是 EHR 连接器Teams计划。</li> <li>**与会者** 是会议中的职员和参与者总数。</li> <li>**短信** 发送指示是否已向与会者发送短信通知。 </li> </li> </ul>|
|**4**   |选择 **设置** 打开"**虚拟访问分析"** 窗格。 在此处，可以关闭或打开组织的虚拟访问报告，以及添加或删除表中的列。 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |可以将报表导出到 CSV 文件进行脱机分析。 选择 **"导出Excel**，然后在 **"下载"** 选项卡上选择"下载"，在报表准备就绪后下载报表。|

> [!NOTE]
> 如果您的组织希望非管理员用户（如业务决策者）参与个人预览版，以便访问和查看此报告， [请与我们联系](mailto:tapmwtanalytics@microsoft.com)。

## <a name="related-articles"></a>相关文章

- [Teams 分析和报告](teams-reporting-reference.md)
- [使用 Teams 和 Bookings 应用的虚拟访问](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [虚拟访问与 Teams - 集成到长篇 EHR 中](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [使用虚拟访问Teams - 集成到 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
