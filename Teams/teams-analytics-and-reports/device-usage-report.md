---
title: Microsoft Teams 设备使用情况报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何使用 Microsoft 团队管理中心中的 "团队设备使用情况" 报表来查看组织中的用户如何连接到团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1da28ccda6394a2e88685132150516cfed2c7fc
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131621"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 设备使用情况报告

Microsoft 团队管理中心中的 "团队设备使用情况" 报表为你提供有关用户如何连接到团队的信息。 你可以使用报表查看你的组织中使用的设备，包括在旅途中使用的多个团队使用的移动设备。  

## <a name="view-the-report"></a>查看报告

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**团队设备使用情况**"。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    团队![管理员中心中使用标注的团队设备使用情况报告的屏幕截图]团队(../media/teams-reports-device-usage-with-callouts.png "管理员中心中使用标注的团队设备使用情况报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队设备使用情况" 报表，了解过去7天或28天的趋势。  |
|**2**   |每个报表都具有生成报表的日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示用于连接到团队的不同设备（**Windows**、 **Mac**、 **iOS**、 **Android 手机**）。 </li><li>Y 轴是在选定时间段内使用设备的用户数。</li> </ul>将鼠标悬停在表示设备的栏上，可查看使用设备连接到团队的用户数。|
|**4**   |此表提供了用户的设备使用情况的细目。 <ul><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。 </li><li>如果用户在基于 Windows 的计算机上的团队桌面客户端中处于活动状态，则选择 " **Windows** "。</li><li>如果用户在 macOS 计算机上的团队桌面客户端中处于活动状态，则会选择**Mac** 。 </li> <li>如果用户在 iOS 的团队移动客户端上处于活动状态，则选择**ios** 。</li><li>如果用户在 Android 的团队移动客户端上处于活动状态，则选择 " **Android 手机**"。 <li>"**上次活动**" 是用户参与团队活动的最后日期（UTC）。</li> </ul> 请注意，如果用户帐户在 Azure AD 中不再存在，则用户名在表中显示为 "-"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |你可以将报表导出到 CSV 文件，以便脱机分析。 单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。<br><br>![显示导出报表的 "下载" 选项卡的屏幕截图](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)