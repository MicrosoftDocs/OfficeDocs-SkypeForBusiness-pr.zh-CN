---
title: 在 Microsoft Teams 管理中心的活动日志中查看策略分配
ms.author: mabond
author: mkbond007
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心的活动日志中查看策略分配活动。
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562211"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>在活动日志中查看策略分配

在 Microsoft Teams 管理中心向用户分配策略时，可以在活动日志中查看这些策略分配的状态。 活动日志显示过去 30 天内通过 Microsoft Teams 管理中心向 20 多名用户批处理的策略分配。 请记住，活动日志不显示策略包分配、通过 Microsoft Teams 管理中心向少于 20 个用户的批次分配策略或通过 PowerShell 分配策略。

![“活动日志”页的屏幕截图。](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>在活动日志中查看策略分配活动

若要在活动日志中查看策略分配，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“开始**”，然后在 **“活动日志**”下选择 **“查看详细信息**”。
2. 可以查看所有策略分配或按状态筛选列表，以仅显示 **未启动**、 **正在进行** 或 **已完成** 的分配。 你将看到有关每个分配的以下信息：
    - **名称**：策略分配的名称。 单击链接可查看更多详细信息。 这包括策略分配给的用户数以及已完成、正在进行且未启动的分配数。 你还将看到批处理中的用户列表，以及每个用户的状态和结果。 下面是一个示例：

        ![屏幕截图。](media/activity-log-policy-assignment-detail.png)

    - **已提交**：提交策略分配的日期和时间。
    - **完成时间**：策略分配完成的日期和时间。
    - **影响**：批处理中的用户数。
    - **总体状态**：策略分配的状态。

> [!NOTE]
> 还可以从 **“用户** ”页访问活动日志。 单击“ **应用** ”提交批量策略分配后，页面顶部会显示横幅。 单击横幅中的 **“活动日志** ”链接。

## <a name="related-topics"></a>相关主题

- [向用户分配策略](policy-assignment-overview.md)
