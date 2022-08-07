---
title: Microsoft Teams PSTN 阻止用户报告
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
description: 使用 Microsoft Teams 管理中心中阻止的 PSTN 用户报告，获取阻止你组织的 Teams 用户进行 PSTN 调用的概述。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 8f723a9aca6cc57510aaf526297f60966a27bcda
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267377"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN 阻止用户报告

Microsoft Teams 管理中心中的 PSTN 阻止用户报表显示组织中阻止在 Teams 中进行 PSTN 调用的用户。 可以查看有关每个被阻止用户的详细信息，包括其分配的电话号码及其被阻止拨打电话的原因。

## <a name="view-the-pstn-blocked-users-report"></a>查看 PSTN 阻止的用户报告

在 Microsoft Teams 管理中心的左侧导航中，单击 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报** 表”下，选择 **“PSTN 阻止的用户**”，然后单击 **“运行报表**”。

![管理中心中 PSTN 阻止用户报表的屏幕截图。](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft Teams 管理中心中具有编号标注的 PSTN 阻止用户报表的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |每个报表都有生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**2**   |X 轴是日期。 Y 轴是用户数。 <br>将鼠标悬停在给定日期上的点上，以查看在该日期被阻止的用户数。 |
|**3**   |该表提供了阻止其进行 PSTN 调用的所有用户的细目。  它显示分配了电话系统或音频会议的所有用户，并提供有关每个用户的详细信息。 <ul><li>**显示名称** 是用户的显示名称。 可以单击显示名称，转到 Microsoft Teams 管理中心的用户设置页面。 </li> <li>**电话** 是分配给用户的号码。</li> <li>**阻止的原因是** 阻止用户进行呼叫的原因。</li><li>**阻止的操作**  会告知用户是被阻止还是阻止在 Teams 中进行 PSTN 调用。</li> <li>**阻止的时间** 是阻止用户拨打呼叫 (UTC) 的日期和时间。</li></li> </ul>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**4**   |选择“**编辑列**”可在表格中添加或删除列。|
|**5**   |选择 **“全屏** ”以全屏模式查看报表。|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)