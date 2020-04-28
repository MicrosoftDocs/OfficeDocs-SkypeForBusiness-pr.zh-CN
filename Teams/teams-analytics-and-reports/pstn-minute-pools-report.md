---
title: Microsoft 团队 PSTN 分钟池报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 如何使用 Microsoft 团队管理中心中的 "团队 PSTN 分钟池" 报表查看当前月内组织内消耗的分钟数。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d00e6f76258caad7899ddd589e037718928741e0
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904894"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft 团队 PSTN 分钟池报告

Microsoft 团队管理中心中的 "团队 PSTN 分钟池" 报表通过显示在当前月份内消耗的分钟数，为你提供有关你的组织中的音频会议和通话活动的概述。 你可以看到活动的细目，包括用于通话的许可证、可用总分钟数、已用分钟数以及按位置的许可证使用情况。

## <a name="view-the-pstn-minute-pools-report"></a>查看 PSTN 分钟池报告

在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 " **PSTN 分钟池**"，然后单击 "**运行报告**"。

![管理中心中的 "团队 PSTN 分钟池" 报表的屏幕截图](../media/teams-reports-pstn-minute-pools-with-callouts.png "Microsoft 团队管理中心中具有编号标注的团队 PSTN 分钟池报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成日期的日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**2**   |单击功能（许可证）查看该功能的活动。 |
|**3**   |X 轴为国家或地区。 Y 轴表示分钟数。 <br>将鼠标悬停在图表上的条形上可查看该使用位置的活动。  |
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 "**未使用**"、"**国内用户**"、"**无数据**" 或 "**国际**专用" 以仅查看与每个用户相关的信息。 |
|**5**   |该表提供按功能和使用位置对分钟池的细分。 <ul><li>**国家或地区**是使用位置。 </li><li>**功能说明**是用于呼叫的许可证的说明。  您可能会在此报告中看到的功能说明包括： <ul><li>国内和国际通话计划（1200国内分钟）</li><li>国内和国际通话计划（3000国内分钟）</li><li>国内和国际通话计划（600国际分钟）</li></ul></li><br><li>"**总分钟**数" 表示当月可用的总分钟数。</li><li>**使用的分钟**数表示每个月使用的分钟数</li> <li>"**可用分钟**数" 表示表示月份剩余的分钟数。</li><li>**功能**是用于通话的许可证。 您可能看到的许可证包括：<ul><li>**MCOPSTNPP** -通讯信用点数</li><li>**MCOPSTN1** -国内通话计划（3000，美国/1200 最少欧盟计划）</li><li>**MCOPSTN2** -国际通话计划</li><li>**MCOPSTN5** -国内通话计划（120分钟通话计划）</li><li>**MCOPSTN6** -国内通话计划（240分钟通话计划）</li><li>**MCOMEETADD** -音频会议</li><li>**MCOMEETACPEA** -每分钟支付的音频会议</li></ul></li> </ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |选择 "**全屏**" 以全屏模式查看报表。|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)