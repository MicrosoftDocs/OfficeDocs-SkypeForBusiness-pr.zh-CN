---
title: Microsoft Teams PSTN 分钟池报告
author: cichur
ms.author: v-cichur
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
description: 如何使用 Microsoft Teams 管理中心中的 Teams PSTN 分钟数池报告来查看组织内部当月消耗的分钟数。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809342"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams PSTN 分钟池报告

Microsoft Teams 管理中心中的 Teams PSTN 分钟池报告通过显示当月使用的分钟数，为你提供组织中音频会议和呼叫活动的概述。 可以看到活动的细分，包括用于通话的许可证、总可用分钟数、已用分钟数以及按位置划分的许可证使用情况。

## <a name="view-the-pstn-minute-pools-report"></a>查看 PSTN 分钟池报告

在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"分析&报告**  >  **使用情况报告**。 在"**查看报表"** 选项卡上的 **"报告"** 下，选择 **PSTN** 分钟池，然后单击"**运行报告"。**

![管理中心中的 Teams PSTN 分钟池报告的屏幕截图](../media/teams-reports-pstn-minute-pools-with-callouts.png "Microsoft Teams 管理中心中带编号标注的 Teams PSTN 分钟池报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**2**   |单击某个 (许可证) 查看该功能的活动。 |
|**3**   |X 轴是国家/地区。 Y 轴表示分钟数。 <br>将鼠标悬停在图表上的条形图上，查看该使用位置的活动。  |
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 **"未使用"、****国内用户****、"** 无数据"或"**国际**"，仅查看与每个数据相关的信息。 |
|**5**   |下表按功能与使用位置提供了分钟池的细分。 <ul><li>**国家/地区** 是使用位置。 </li><li>**功能** 说明是用于调用的许可证的说明。  可能会在此报告中看到的功能说明包括： <ul><li>国内和国际呼叫计划 (1200 分钟国内) </li><li>国内和国际呼叫计划 (3000 分钟) </li><li>国内和国际呼叫计划 (600 分钟) </li></ul></li><br><li>**总分钟** 数是当月可用的总分钟数。</li><li>**使用的分钟** 数是每月使用的分钟数</li> <li>**可用分钟** 数是当月的剩余分钟数。</li><li>**功能** 是用于调用的许可证。 你可能会看到的许可证包括：<ul><li>**MCOPSTNPP** - 通信信用额度</li><li>**MCOPSTN1** - 国内呼叫 (美国 3000 分钟/欧盟 1200 分钟) </li><li>**MCOPSTN2** - 国际呼叫计划</li><li>**MCOPSTN5** - 国内呼叫 (120 分钟通话套餐) </li><li>**MCOPSTN6** - 国内呼叫 (240 分钟通话套餐) </li><li>**MCOMEETADD** - 音频会议</li><li>**MCOMEETACPEA** - 按分钟支付音频会议</li></ul></li> </ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |选择 **"全屏** "以全屏模式查看报表。|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)