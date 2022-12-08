---
title: 在 Microsoft Teams 中管理虚拟约会应用
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
audience: admin
description: 了解如何为组织中的用户管理虚拟约会应用。
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a61c8f75ec8825671b5d9fb845b77fab71bf3cfe
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2022
ms.locfileid: "69308009"
---
# <a name="manage-the-virtual-appointments-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理组织的虚拟约会应用

[!INCLUDE [preview-feature](includes/preview-feature.md)]

虚拟约会应用为 Microsoft Teams 中的所有虚拟约会需求提供了一个中心。 该应用为企业到客户互动提供无缝的端到端体验，将 [Bookings 应用](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)、分析和管理选项中的计划集成在一个位置。

可以计划、查看和管理虚拟约会，在队列视图中获取实时状态更新，发送约会提醒，查看分析和报告以深入了解虚拟约会活动，以及配置日历、员工和预订页面设置。

使用任何 Microsoft 365 许可证，可以使用基本的虚拟约会功能来安排和加入企业到客户的会议。 例如，可以在 Bookings 日历中安排约会，外部与会者可以通过 [浏览器加入](/microsoft-365/frontline/browser-join) ，而无需下载 Teams。 [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (预览版) 解锁了组织可用于管理和个性化体验的高级虚拟约会功能。 其中包括计划约会和按需约会、短信通知、自定义候诊室和分析的队列视图。

## <a name="overview-of-the-virtual-appointments-app"></a>虚拟约会应用概述

虚拟约会应用具有以下选项卡。

- [主页](#home)
- [预订计划](#bookings-schedule)
- [队列](#queue)
- [分析](#analytics)
- [管理](#manage)

下面概述了每个选项卡上的内容。

### <a name="home"></a>主页

![信息图标](media/info.png) **队列和分析磁贴是 [Teams 高级](teams-add-on-licensing/licensing-enhance-teams.md) 版 (预览版) 的一部分。**

轻松访问关键操作和信息。 主页提供预订计划的快速视图、约会队列摘要、约会分析快照和管理选项。

:::image type="content" source="media/manage-virtual-appointments-app-home.png" alt-text="虚拟约会 应用中主页的屏幕截图。" lightbox="media/manage-virtual-appointments-app-home.png":::

### <a name="bookings-schedule"></a>预订计划

![信息图标](media/info.png)**短信通知现在是 [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (预览版) 的一部分。用户可以在预览期间继续使用此功能。预览版后，用户需要 Teams Premium 许可证。**

访问 Bookings 日历以安排虚拟约会，例如医疗保健访问、财务咨询、面试、虚拟配件和咨询等。 可以连接现有的 Bookings 日历或创建新日历。 若要了解详细信息，请参阅[使用 Teams 和 Bookings 应用虚拟约会](/microsoft-365/frontline/bookings-virtual-appointments)和[什么是 Bookings？](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)。

:::image type="content" source="media/manage-virtual-appointments-app-bookings-schedule.png" alt-text="虚拟约会 应用中“预订计划”页的屏幕截图。" lightbox="media/manage-virtual-appointments-app-bookings-schedule.png":::

### <a name="queue"></a>队列

![信息图标](media/info.png) **计划的队列视图和短信通知现在是 [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (预览版) 的一部分。用户可以在预览期间继续使用这些功能。预览版后，用户需要 Teams Premium 许可证。若要在预览期间访问按需队列，用户需要 Teams Premium 试用许可证。**

查看和监视固定的 Bookings 日历中的所有计划和按需虚拟约会，实时更新。

在这里，计划人员可以添加新的预订、查看相关的约会详细信息以及查看全天的约会状态。 他们还可以向分配的员工和与会者发送电子邮件提醒，并向与会者发送短信通知，以便安排约会。 员工可以直接从队列加入约会。

若要了解详细信息，请参阅 [监视约会并获取实时状态更新](/microsoft-365/frontline/bookings-virtual-appointments#monitor-appointments-and-get-real-time-status-updates-in-the-queue-view)。

:::image type="content" source="media/manage-virtual-appointments-app-queue.png" alt-text="虚拟约会应用中“队列”页的屏幕截图。" lightbox="media/manage-virtual-appointments-app-queue.png":::

### <a name="analytics"></a>分析

深入了解使用活动和趋势，以帮助优化虚拟约会并提供更好的业务成果。

Teams 虚拟约会使用情况报告为管理员、决策者和用户提供了组织中虚拟约会活动的概述。 报表提供关键指标，例如约会总数、约会持续时间、大厅等待时间以及未显示。

可以查看通过多个计划入口点计划和执行的虚拟约会的详细活动，并向下钻取到单个约会数据。

分析体验取决于用户角色。 管理员获取 [组织分析，](#organizational-analytics) 非管理员获取 [部门或个人分析](#departmental-and-individual-analytics)。

#### <a name="organizational-analytics"></a>组织分析

![信息图标](media/info.png) **此功能作为 [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (预览版) 的一部分提供。预览期过后，需要 Teams Premium 许可证。**

管理员会看到组织级别的报告，其中显示了组织内所有部门的聚合分析。

:::image type="content" source="media/manage-virtual-appointments-app-analytics-org.png" alt-text="虚拟约会 应用中“分析”页的屏幕截图，其中显示了管理员的虚拟约会使用情况报告。" lightbox="media/manage-virtual-appointments-app-analytics-org.png":::

若要了解详细信息，请参阅[虚拟约会使用情况报告](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

#### <a name="departmental-and-individual-analytics"></a>部门和个人分析

![信息图标](media/info.png) **若要在预览期间访问此功能，用户需要 [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) 试用版许可证。**

非管理员会看到为给定部门提供数据的部门级报表。

:::image type="content" source="media/manage-virtual-appointments-app-analytics-dept.png" alt-text="虚拟约会 应用中“分析”页的屏幕截图，其中显示了非管理员的虚拟约会使用情况报告。" lightbox="media/manage-virtual-appointments-app-analytics-dept.png":::

如果某个员工与部门没有关联，则报告会显示他们进行的约会的数据。

### <a name="manage"></a>管理

管理 Bookings 日历设置。 可以更新业务详细信息、自定义约会类型、添加员工和分配角色，以及配置预订页面设置。

:::image type="content" source="media/manage-virtual-appointments-app-manage.png" alt-text="虚拟约会应用中“管理”页的屏幕截图。" lightbox="media/manage-virtual-appointments-app-manage.png":::

## <a name="set-up-the-virtual-appointments-app"></a>设置虚拟约会应用

### <a name="enable-or-disable-the-virtual-appointments-app-in-your-organization"></a>启用或禁用组织中的虚拟约会应用

默认情况下，组织中所有 Teams 用户都启用了 虚拟约会 应用。 你可以在 Microsoft Teams 管理中心的[管理应用](manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 “**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索虚拟约会应用，将其选中，然后将 **“状态”** 切换开关切换为 **“已阻止**”或“**允许**”。

### <a name="enable-or-disable-the-virtual-appointments-app-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用虚拟约会应用

若要允许或阻止组织中的特定用户使用应用，请确保在“管理应用”页上为你的组织启用了 [该应用](manage-apps.md) 。 然后为应用权限创建自定义策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="use-an-app-setup-policy-to-pin-the-virtual-appointments-app-to-teams"></a>使用应用设置策略将虚拟约会应用固定到 Teams

应用设置策略让你自定义 Teams 来突出显示组织中对用户最重要的应用。 在策略中设置的应用将固定到应用栏（Teams 桌面客户端一侧和 Teams 移动客户端底部的栏），用户可以在其中快速轻松地访问它们。

若要为用户固定虚拟约会应用，可以编辑全局 (组织范围的默认) 策略。 或者，可以创建并分配自定义应用设置策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

## <a name="terms-of-service"></a>服务条款

请参阅 [服务条款](/legal/microsoft-365/virtual-appointments-app-terms-of-service)。

## <a name="related-articles"></a>相关文章

- [虚拟约会导游](https://guidedtour.microsoft.com/guidedtour/industry-longform/virtual-appointments/1/1)
- [Teams 高级版许可](teams-add-on-licensing/licensing-enhance-teams.md)
