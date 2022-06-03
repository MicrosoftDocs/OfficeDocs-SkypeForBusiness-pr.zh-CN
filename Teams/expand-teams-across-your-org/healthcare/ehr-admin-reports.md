---
title: Microsoft Teams EHR 连接器虚拟约会报告
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 了解如何使用 Microsoft Teams 管理中心中的 Teams EHR 连接器虚拟约会报告来概述组织中 EHR 集成的虚拟约会使用情况。
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883535"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Microsoft Teams EHR 连接器虚拟约会报告

Microsoft Teams 管理中心中的 Microsoft Teams 电子运行状况记录 (EHR) 连接器虚拟约会报表提供了一种快速且简单的方法来查看组织中 Teams EHR 集成的虚拟约会使用情况。

若要查看报表，必须是全局管理员、Teams 管理员、全局阅读器或报表阅读器。

## <a name="view-the-report"></a>查看报告

可通过两种方法在 Teams 管理中心访问和查看报表。

- 通过仪表板中的 [EHR 连接器使用情况卡](#the-ehr-connector-usage-card)
- 直接通过在分析中选择 [**EHR 连接器虚拟约会**](#the-teams-ehr-connector-virtual-appointments-report)**&报告** > **使用情况报告**

### <a name="the-ehr-connector-usage-card"></a>EHR 连接器使用情况卡

在 Microsoft Teams 管理中心的左侧导航中，选择 **仪表板**，然后转到 **EHR 连接器虚拟约会** 卡。

在这里，你将按月查看 Teams EHR 集成的虚拟约会活动，包括已完成的约会、剩余分配，以及是否已超出每月限制 (取决于你已) 的许可证。

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Teams 管理中心仪表板中 EHR 连接器使用情况卡的屏幕截图。" lightbox="../../media/ehr-connector-report-card.png":::

选择 **“查看详细信息** ”以查看报表详细信息。 若要购买更多许可证，请选择 **“购买更多**”。

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Teams EHR 连接器虚拟约会报告

1. 在 Teams 管理中心的左侧导航中，转到 **“分析”&报告** > **使用情况报告**。
1. 在 **“视图报表** ”选项卡上，选择 **“EHR 连接器虚拟约会** ”和“日期”范围。 然后，选择 **“运行”报表**。

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Teams 管理中心中 Teams EHR 连接器虚拟约会报表的屏幕截图。" lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表显示生成报表的日期和所选日期范围。|
|**2**   |该表提供有关在所选日期范围内发生的每个约会的详细信息。 请记住，你不会看到员工或患者未加入的约会条目。 <ul><li>**开始时间 (UTC)** 是工作人员和参与者参与约会的日期和时间。  </li> <li>**持续时间** 是开始时间和最后一个人离开约会的时间之间的时差。</li> <li>**主要** 名称是会议组织者的名称。 <li>**Primary 的电子邮件** 是会议组织者的电子邮件地址。</li> <li> **部门** 是约会的部门信息。 如果信息未正确显示，请联系 EHR 支持团队。 若要与 Epic 集成，请确保 ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` 是提供程序集成记录的一部分。 </li></li> <li>**助理** 是参加约会的工作人员和参与者的总数。</li> <li>**限制内** 指示约会是否在分配限制范围内。 </li> </ul> |
|**3**   |可以将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到 Excel** ”以下载报表。 |
|**4**   |选择 **“筛选器** ”以筛选报表详细信息视图。 |
|**5**   |选择 **“全屏** ”以全屏模式查看报表。 |
|**6**   |选择 **“编辑列** ”以添加或删除表中的列 |

> [!NOTE]
> 有关 Teams EHR 集成的虚拟约会的更多分析，请 [参阅虚拟访问使用情况报告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)。 使用虚拟访问使用情况报告，可以查看关键指标，例如总约会、大厅等待时间、约会持续时间和不显示。 使用此信息可深入了解使用趋势，帮助优化虚拟约会以提供更好的业务成果。

## <a name="related-articles"></a>相关文章

- [使用 Teams 进行虚拟约会 - 集成到 Cerner EHR](ehr-admin-cerner.md)
- [与 Teams 的虚拟约会 - 集成到 Epic EHR](ehr-admin.md) 
