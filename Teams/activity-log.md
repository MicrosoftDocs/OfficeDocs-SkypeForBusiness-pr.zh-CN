---
title: 在 Microsoft 团队管理中心的活动日志中查看你的策略分配
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft 团队管理中心的活动日志中查看策略分配活动。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374290"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>查看活动日志中的策略分配

向 Microsoft 团队管理中心中的用户分配策略时，可以在活动日志中查看这些策略分配的状态。 活动日志显示过去30天内通过 Microsoft 团队管理中心向超过20名用户批处理的策略分配。 请注意，活动日志未显示策略程序包分配、策略分配，可通过 Microsoft 团队管理中心的用户数少于20个用户，或通过 PowerShell 进行策略分配。

![活动日志页的屏幕截图](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>在活动日志中查看策略分配活动

要查看活动日志中的策略分配，请执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到**仪表板**，然后在 "**活动日志**" 下，选择 "**查看详细信息**"。
2. 你可以查看所有策略分配或按状态筛选列表，以仅显示**未开始**、**正在进行**或**已完成**的作业。 你将看到有关每个作业的以下信息：
    - **名称**：策略分配的名称。 单击链接以查看更多详细信息。 其中包括分配了该策略的用户数以及已完成的作业数、正在进行的作业数以及未开始的作业数。 你还将看到批中的用户列表，以及每个用户的状态和结果。 下面是一个示例：

        ![的屏幕截图](media/activity-log-policy-assignment-detail.png)

    - 已**提交**：提交策略分配的日期和时间。
    - **完成时间**：策略分配完成的日期和时间。
    - **影响**：批处理中的用户数。
    - **总体状态**：策略分配的状态。

> [!NOTE]
> 您也可以从 "**用户**" 页面访问活动日志。 单击 "**应用**" 以提交批量策略分配后，将在页面顶部看到横幅。 单击横幅中的 "**活动日志**" 链接。

## <a name="related-topics"></a>相关主题

- [为用户分配策略](assign-policies.md)
