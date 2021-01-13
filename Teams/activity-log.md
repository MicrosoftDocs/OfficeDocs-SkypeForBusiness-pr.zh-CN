---
title: 在 Microsoft Teams 管理中心的活动日志中查看策略分配
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心的活动日志中查看策略分配活动。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821312"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>在活动日志中查看策略分配

在 Microsoft Teams 管理中心向用户分配策略时，可以在活动日志中查看这些策略分配的状态。 活动日志显示过去 30 天内通过 Microsoft Teams 管理中心向超过 20 个用户批处理的策略分配。 请记住，活动日志不会通过 Microsoft Teams 管理中心向少于 20 名用户的批次显示策略包分配、策略分配，也不通过 PowerShell 显示策略分配。

!["活动日志"页的屏幕截图](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>在活动日志中查看策略分配活动

在活动日志中查看策略分配：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"** 仪表板"，然后在"活动日志"下选择 **"查看详细信息"。**
2. 可以查看所有策略分配或按状态筛选列表，以只显示未启动、正在进行或已完成 **的分配**。  你将看到有关每个作业的以下信息：
    - **名称**：策略分配的名称。 单击该链接可查看更多详细信息。 这包括策略分配到的用户数，以及已完成、进行中和未启动的分配数。 还将看到批处理中的用户列表，以及每个用户的状态和结果。 下面是一个示例：

        ![屏幕截图](media/activity-log-policy-assignment-detail.png)

    - **已提交**：提交策略分配的日期和时间。
    - **完成时间**：策略分配的完成日期和时间。
    - **影响**：批中的用户数。
    - **总体状态**：策略分配的状态。

> [!NOTE]
> 还可以从"用户"页访问 **活动** 日志。 单击" **应用** "提交批量策略分配后，页面顶部将会显示一个横幅。 单击 **横幅中的活动** 日志链接。

## <a name="related-topics"></a>相关主题

- [向用户分配策略](assign-policies.md)
