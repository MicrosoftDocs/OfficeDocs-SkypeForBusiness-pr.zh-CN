---
title: Microsoft Teams 使用情况报告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 使用情况报告来概要了解组织中的 Teams 活动。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e2913093cfa45bb7e242dbe5452657cd74f9e187
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627244"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用情况报告

通过 Microsoft Teams 管理中心的 Teams 使用情况报告，可概要了解 Teams 中的活跃用户和频道数等使用活动，从而能快速查看组织中有多少用户正在使用 Teams 进行通信和协作。 你可查看团队的使用情况信息，包括每个团队中的活跃用户和频道数量、来宾数和消息数。

## <a name="view-the-usage-report"></a>查看使用情况报告

1. 在管理中心的左侧导航Microsoft Teams，单击 **"分析&报告**  >  **使用情况报告"。** 在"**查看报表"** 选项卡上的"报表 **"下**，Teams **使用情况"。**
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![屏幕截图：Teams管理中心内具有标注Teams使用情况报表](../media/teams-reports-teams-usage-with-callouts1.png "屏幕截图：Teams管理中心中带标注Teams使用情况报表")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看Teams活动报表，了解过去 7 天、30 天或 90 天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴表示活跃项目或活动的计数。</li> </ul>将鼠标悬停在表示给定日期中某项目或活动的点可查看该项目或活动在该给定日期的实例数量。|
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击"活动 **用户** 总数"，Teams &"频道活动用户"、"活动频道"或"消息 **"，** 仅查看与每个活动用户有关的信息。 更改此选项不会更改表格中的信息。 |
|**5**   |表格按团队细分显示了使用情况。 <ul><li>**团队** 名称是显示名称的名称。 可以单击团队名称，转到管理中心内团队Microsoft Teams页面。 </li> <li>“**隐私**”表示团队是私人团队还是公共团队。</li> <li>“**活跃用户数**”是指定时间段内活跃用户的数量。</li><li>“**来宾数**”是指定时间段内团队中来宾的数量。</li> <li>**活动通道** 是指定时段内至少有一个活动用户的通道数。</li> <li>**"发布** 消息"是指定时段内频道中所有发布消息的数量。</li> <li>**回复** 消息是指定时段内频道中所有回复消息的数量。</li> <li>**组织的** 会议是用户于指定时间段组织的计划会议和临时会议的数量。 </li><li>**紧急邮件** 是指定时段内所有紧急邮件的数量。</li><li>**"** 回应"是指定时段内对消息的所有反应数。</li><li>**提及** 是指定时段内邮件中使用的所有提及次数。</li><li>**频道** 消息是团队用户在指定的时段内在团队聊天中发布的唯一消息数。</li> </li> </ul>请注意，如果 Azure AD 中不再存在用户帐户，则用户名在表中显示为"--"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |可以将报表导出到 CSV 文件进行脱机分析。 单击 **"导出Excel"，** 然后在 **"下载"** 选项卡上单击"下载"，在报表准备就绪后下载报表。<br><br>![显示要下载的导出报表的"下载"选项卡的屏幕截图](../media/teams-reports-export-to-csv.png)|
|**8** |图中的时序数据点显示租户中聚合的不同使用情况指标|
|**9** |表格数据表示每个团队聚合的不同使用情况指标|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
