---
title: 管理组织的 Shifts 应用
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何在组织的 Teams 中为一线员工设置和管理 Shifts 应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc6f3047a74fda332e945558a243f40b714e8730
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821132"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理 Shifts 应用

> [!IMPORTANT]
> 自 2020 年 6 月 30 起，Microsoft StaffHub 已停用。 我们正在将 StaffHub 功能构建到 Microsoft Teams 中。 目前，Teams 包含用于计划管理的 Shifts 应用，其他功能将随着时间的推移而推出。 StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。 尝试打开 StaffHub 的任何人都会显示一条消息，指示他们下载 Teams。 有关详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview-of-shifts"></a>班次概述

Microsoft Teams 中的 Shifts 应用可使一线员工保持连接和同步。它首先构建为移动版，为团队提供快速高效的时间管理和通信。 排班可让一线员工及其经理使用其移动设备管理日程安排并保持联系。

- 经理为团队创建、更新和管理排班计划。 他们可以向一个人发送消息 ("楼层溢出") 或整个团队 ("区域 GM 在 20 分钟内到达") 。 他们还可以发送策略文档、新闻公告和视频。 
- 员工可查看即将到来的排班、查看安排当天的其他人、调班或调班的请求，以及请求请假。 

必须知道 Shifts 当前不支持来宾用户。 这意味着在 Teams 中启用来宾访问时，无法将团队中的来宾添加到或使用排班计划。 

> [!Note]
> 有关不同平台上的 Shifts 功能的详细信息，请参阅["按平台显示 Teams 功能"。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>班次的可用性

班次在 Teams 可用的所有企业 SK 单位中可用。

## <a name="location-of-shifts-data"></a>Shifts 数据的位置

Shifts 数据当前存储在 Azure 中，位于北美、西欧和亚太的数据中心。 有关在何处存储数据，请参阅" [我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？"

## <a name="set-up-shifts"></a>设置班次

### <a name="enable-or-disable-shifts-in-your-organization"></a>在组织中启用或禁用 Shifts

默认情况下，为组织的所有 Teams 用户启用班次。 可以在 Microsoft Teams 管理中心的"管理应用"页面上关闭或[](../../manage-apps.md)打开组织级别的应用。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**
2. 在应用列表中，执行下列操作之一：

    - 若要为组织关闭 Shifts，请搜索 Shifts 应用，将其选中，然后单击"阻止 **"。**
    - 若要为组织启用 Shifts，请搜索 Shifts 应用，将其选中，然后单击"允许 **"。**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>为组织中特定用户启用或禁用 Shifts

若要允许或阻止组织中特定用户使用 Shifts，请确保在"管理应用"页面上为组织启用 Shifts，然后创建自定义[](../../manage-apps.md)应用权限策略并将其分配给这些用户。 若要了解有关详细信息，请参阅["在 Teams 中管理应用权限策略"。](../../teams-app-permission-policies.md)

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 FirstlineWorker 应用设置策略将 Shifts 固定到 Teams

应用设置策略可让你自定义 Teams，突出显示对组织中用户最重要的应用。 在策略中设置的应用将固定到 Teams 桌面客户端一侧的应用栏和 Teams 移动客户端的底部，用户可以在这里快速 &mdash; &mdash; 轻松地访问它们。
 
Teams 包括内置 FirstlineWorker 应用设置策略，可将其分配给组织中一线员工。 默认情况下，该策略包括活动、Shifts、聊天和呼叫应用。 

若要查看 FirstlineWorker 策略，在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams 应用**  >  **应用设置策略**。

![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理中心中 FirstlineWorker 应用设置策略的屏幕截图")

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>将 FirstlineWorker 应用设置策略分配给用户

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>在审核日志搜索 Shifts 事件

**（处于预览阶段）**

可以搜索审核日志查看组织中 Shifts 活动。  若要详细了解如何搜索 审核日志并查看记录在 审核日志 中的 [Shifts](../../audit-log-events.md#shifts-in-teams-activities) 活动列表，请参阅"在 审核日志 中搜索 [活动](../../audit-log-events.md)。

在搜索安全中心审核日志，首先在安全与合规中心& [审核](https://protection.office.com)。 若要了解有关详细信息，请参阅 [审核日志打开或关闭搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 请记住，只有启用审核时，审核数据才可用。

## <a name="related-topics"></a>相关主题

- [一线员工班次帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [在 Teams 中向用户分配策略](../../assign-policies.md)
