---
title: Microsoft Teams PSTN 分钟池报表
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: 如何在 Microsoft Teams 管理中心使用 Teams PSTN 分钟池报表查看组织在当月内消耗的分钟数。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3aafc45cebab24f5524a4d3120dd0c03083d0c6c
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794350"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams PSTN 分钟池报表

Microsoft Teams 管理中心中的 Teams PSTN 分钟池报表通过显示当前月份使用的分钟数，概述了组织中的音频会议和通话活动。 可以看到活动细分，包括用于呼叫的许可证、可用总分钟数、已用分钟数以及按位置使用的许可证。

## <a name="view-the-pstn-minute-pools-report"></a>查看 PSTN 分钟池报表

在 Microsoft Teams 管理中心的左侧导航中，单击 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报** 表”下，选择 **“PSTN 分钟”和“短信” (预览) 池**，然后单击 **“运行报表**”。

![管理中心中 Teams PSTN 分钟池报表的屏幕截图。](../media/teams-reports-pstn-minute-pools-with-callouts.png "Microsoft Teams 管理中心中具有编号标注的 Teams PSTN 分钟池报表的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**2**   |单击功能 (许可证) 查看该功能的活动。 |
|**3**   |X 轴是国家/地区。 Y 轴是分钟数。 <br>将鼠标悬停在图表上的条形图上，以查看该使用位置的活动。  |
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 **“未使用**”、“ **国内用户**”、“ **无数据**”或 **“国际”，** 仅查看与每个用户相关的信息。 |
|**5**   |该表按功能和使用位置提供分钟池的细分。 <ul><li>**国家或地区** 是使用位置。 </li><li>**功能说明** 是用于调用的许可证的说明。  此报表中可能显示的功能说明包括： <ul><li>国内和国际通话套餐 (国内1200分钟) </li><li>国内和国际通话套餐 (国内3000分钟) </li><li>国内和国际通话计划 (600个国际分钟数) </li></ul></li><br><li>**总分钟数** 是当月可用的总分钟数。</li><li>**所用分钟** 数是每月使用的分钟数</li> <li>**可用分钟** 数是当月的剩余分钟数。</li><li>**功能** 是用于调用的许可证。 可能看到的许可证包括：<ul><li>**MCOPSTN1** - 国内通话计划 (3000分钟美国/1200分钟欧盟计划) </li><li>**MCOPSTN2** - 国际呼叫计划</li><li>**MCOPSTN5** - 国内通话套餐 (120分钟通话套餐) </li><li>**MCOPSTN6** - 国内通话套餐 (240 分钟通话套餐) </li><li>**MCOMEETADD** - 音频会议</li></ul></li> </ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |选择 **“全屏** ”以全屏模式查看报表。|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
