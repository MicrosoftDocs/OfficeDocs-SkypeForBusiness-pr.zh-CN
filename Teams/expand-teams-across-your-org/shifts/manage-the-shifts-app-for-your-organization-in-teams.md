---
title: 为组织管理“班次”应用
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
description: 了解如何在你的组织中设置和管理适合一线员工的 Teams 中的“班次”应用。
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
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909086"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理“班次”应用

> [!IMPORTANT]
> 从 2020 年 6 月 30 开始，Microsoft StaffHub 已停用。 我们正在将 StaffHub 功能集成到 Microsoft Teams 中。 如今，Teams 包含用于日程安排管理的“班次”应用，并且随着时间推移将推出其他功能。 StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。 尝试打开 StaffHub 的任何用户都会看到一则提示其下载 Teams 的消息。 若要了解详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview-of-shifts"></a>“班次”概述

Microsoft Teams 中的“班次”应用让一线员工能够保持联系和同步。它以移动优先为构建理念，以便为团队实现快速有效的时间管理和沟通。 “班次”让一线员工及其经理可以使用各自的移动设备管理日程安排并保持联系。

- 经理可创建、更新和管理团队的班次安排。 他们可以向一个人（“地板上洒了水”）或整个团队（“区域总经理将在 20 分钟后到达”）发送消息。 他们还可以发送政策文档、新闻公告和视频。 
- 员工可查看即将到来的排班、查看当天还有谁的排班、申请调班或转班以及申请请假。 

需要指出的是，“班次”当前不支持来宾用户。 这意味着在 Teams 中启用来宾访问时，无法将团队中的来宾添加到排班计划，他们也无法使用排班计划。 

> [!Note]
> 有关不同平台上的“班次”功能的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>“班次”可用性

Teams 可用的所有企业 SKU 中均提供“班次”。

## <a name="location-of-shifts-data"></a>“班次”数据的位置

“班次”数据当前存储在北美、西欧和亚太地区的数据中心中的 Azure 中。 有关数据存储位置的详细信息，请参阅[我的数据在哪里？](http://o365datacentermap.azurewebsites.net/)。

## <a name="set-up-shifts"></a>设置“班次”

### <a name="enable-or-disable-shifts-in-your-organization"></a>在你的组织中启用或禁用“班次”

默认情况下，将为你组织中的所有 Teams 用户启用“班次”。 你可以在 Microsoft Teams 管理中心的[管理应用](../../manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，执行下列操作之一：

    - 若要为你的组织禁用“班次”，请搜索“班次”应用，将其选中，然后选择“**阻止**”。
    - 若要为你的组织启用“班次”，请搜索“班次”应用，将其选中，然后选择“**允许**”。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>为你的组织中的特定用户启用或禁用“班次”

若要允许或阻止组织的特定用户使用“班次”，请确保在“[管理应用](../../manage-apps.md)”页面上为你的组织启用“班次”，然后创建自定义应用权限策略并将其分配给那些用户。 若要了解详细信息，请参阅[在 Teams 中管理应用权限策略](../../teams-app-permission-policies.md)。

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 FrontlineWorker 应用设置策略将“班次”固定到 Teams

利用应用设置策略，你可自定义 Teams 来突出显示组织中对用户最重要的应用。 在策略中设置的应用会固定到应用栏（&mdash;Teams 桌面客户端的边栏以及 Teams 移动客户端的底栏&mdash;），用户可以快速方便地访问。
 
Teams 包含内置的 FrontlineWorker 应用设置策略，可将其分配给组织中的一线员工。 默认情况下，该策略包括“活动”、“班次”、“聊天”和“通话”应用。 

若要查看 FrontlineWorker 策略，请在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**应用设置策略**”。

![FrontlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理中心中的 FrontlineWorker 应用设置策略的屏幕截图")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>将 FrontlineWorker 应用设置策略分配给用户

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>在审核日志中搜索“班次”事件

**（处于预览阶段）**

你可以搜索审核日志以查看贵组织的班次活动。  若要详细了解如何搜索审核日志并查看审核日志中记录的[班次活动](../../audit-log-events.md#shifts-in-teams-activities)列表，请参阅[在审核日志中搜索 Teams 事件](../../audit-log-events.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://protection.office.com)中启用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="related-topics"></a>相关主题

- [一线员工相关的班次帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [向 Teams 中的用户分配策略](../../assign-policies.md)
