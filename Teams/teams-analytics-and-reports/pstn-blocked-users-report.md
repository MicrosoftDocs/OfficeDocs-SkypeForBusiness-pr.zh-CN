---
title: Microsoft TeamsPSTN 阻止的用户报告
author: cichur
ms.author: v-cichur
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
description: 使用管理中心中的 PSTN Microsoft Teams报告，大致了解组织阻止Teams PSTN 呼叫的用户。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: da60a0005fbccd04e3257f3dd7466d5b1a32a544
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594464"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft TeamsPSTN 阻止的用户报告

"PSTN 阻止的用户"Microsoft Teams中心内显示组织中被阻止在 Teams 中拨打 PSTN 呼叫的用户。 可以查看有关每个被阻止用户的信息，包括其分配的电话号码以及阻止他们拨打电话的原因。

## <a name="view-the-pstn-blocked-users-report"></a>查看 PSTN 阻止的用户报告

在管理中心的左侧导航Microsoft Teams，单击 **"分析&报告**  >  **使用情况报告"。** 在"**查看报表"** 选项卡上的"报告 **"下**，选择 **"PSTN 阻止的用户"，** 然后单击"**运行报告"。**

![管理中心中 PSTN 阻止的用户报告报告的屏幕截图](../media/teams-reports-pstn-blocked-users-with-callouts.png "PSTN 阻止的用户报告的屏幕截图，Microsoft Teams带编号标注的用户")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有一个生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**2**   |X 轴是日期。 Y 轴表示用户数。 <br>将鼠标悬停在给定日期的点上，以查看该日期被阻止的用户数。 |
|**3**   |下表提供了阻止进行 PSTN 呼叫的所有用户的细分。  它显示分配电话系统音频会议的所有用户，并提供有关每个用户的信息。 <ul><li>**显示** 名称显示名称用户的名称。 可以单击显示名称转到管理中心中的用户设置Microsoft Teams页面。 </li> <li>**电话** 是分配给用户的数量。</li> <li>**被阻止** 的原因是阻止用户进行调用的原因。</li><li>**阻止的操作** 会告知用户被阻止还是未阻止在 Teams 中拨打 PSTN。</li> <li>**阻止时间** 是用户被 (UTC) 的日期和时间。</li></li> </ul>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**4**   |选择“**编辑列**”可在表格中添加或删除列。|
|**5**   |选择 **"全屏** "以全屏模式查看报表。|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)