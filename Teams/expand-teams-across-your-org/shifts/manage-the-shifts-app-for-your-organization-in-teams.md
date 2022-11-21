---
title: 为组织管理“班次”应用
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: 了解如何在 Teams 中为组织中的一线员工设置和管理排班应用。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 545c5af7411aa23bac7c7437d79d412914c7ad79
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69130971"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理“班次”应用

## <a name="overview-of-shifts"></a>“班次”概述

Microsoft Teams 中的排班应用使一线员工保持连接和同步。它以移动为先，为团队提供快速有效的时间管理和通信。 轮班让一线员工及其经理使用移动设备来管理日程安排并保持联系。

- 经理可创建、更新和管理团队的班次安排。 他们可以向一个人（“地板上洒了水”）或整个团队（“区域总经理将在 20 分钟后到达”）发送消息。 他们还可以发送政策文档、新闻公告和视频。
- 员工可查看即将到来的排班、查看当天还有谁的排班、申请调班或转班以及申请请假。

请务必知道排班当前不支持来宾。 这意味着在 Teams 中启用来宾访问时，无法将团队中的来宾添加到排班计划，他们也无法使用排班计划。

> [!Note]
> 有关不同平台上的“班次”功能的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>“班次”可用性

Teams 可用的所有企业 SKU 中均提供“班次”。

> [!NOTE]
> 班次在政府社区云 (GCC) 环境中可用，但在 GCC High 或 DoD 环境中不可用。

## <a name="location-of-shifts-data"></a>“班次”数据的位置

班次数据目前存储在 Azure 中，位于亚太地区 () 、欧盟 (欧盟) 和北美的数据中心。 有关数据存储位置的详细信息，请参阅[我的数据在哪里？](http://o365datacentermap.azurewebsites.net/)。

若要详细了解排班数据，包括排班数据的存储、保留、检索和加密，请参阅 [排班数据常见问题解答](shifts-data-faq.md)。

## <a name="set-up-shifts"></a>设置“班次”

### <a name="enable-or-disable-shifts-in-your-organization"></a>在你的组织中启用或禁用“班次”

默认情况下，将为你组织中的所有 Teams 用户启用“班次”。 你可以在 Microsoft Teams 管理中心的[管理应用](../../manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索“排班”应用，将其选中，然后将 **“状态”** 切换开关切换为 **“已阻止** ”或 **“允许**”。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>为你的组织中的特定用户启用或禁用“班次”

若要允许或阻止组织中的特定用户使用排班，请确保在 [“管理应用](../../manage-apps.md) ”页上为组织启用排班。 然后为应用权限创建自定义策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](../../teams-app-permission-policies.md)。

### <a name="pin-shifts-to-teams"></a>将班次固定到 Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>使用定制的一线应用体验将排班和其他应用固定到 Teams

Teams 中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定 Teams 中最相关的应用。 固定的应用包括排班、对讲机、任务和审批。 默认情况下，此功能处于打开状态，为一线员工提供适合其需求的开箱即用体验。

应用固定到应用栏（Teams 桌面客户端一侧和 Teams 移动客户端底部的栏），用户可以快速轻松地访问应用栏。

若要了解详细信息，包括体验如何与设置的应用策略配合使用，请参阅 [为一线员工定制 Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>使用应用设置策略将排班固定到 Teams

应用设置策略允许自定义 Teams，以固定对用户最重要的应用。

可以通过添加 Shifts 应用，然后将[策略分配给](../../assign-policies-users-and-groups.md)用户，[在应用设置策略中创建自定义](../../teams-app-setup-policies.md)策略。 或者，可以使用属于一线员工和一线经理策略包一部分的应用设置策略。

Teams 中的 [策略包](../../manage-policy-packages.md) 是预定义策略和策略设置的集合，你可以将其分配给组织中具有类似角色的用户。 一线员工和一线经理策略包中的策略集包括应用设置策略，该策略固定排班应用以及支持该角色的通信和协作活动的其他应用。

我们建议使用一线员工和一线经理策略包，因为它们在为一线员工管理策略时简化、简化并帮助提供一致性。

### <a name="enable-shift-based-tags-in-teams"></a>在 Teams 中启用基于班次的标记

Teams 中的[标记](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)使用户可以轻松地与团队中的一部分人员联系。 使用基于班次的标记时，会自动为人员分配与其排班时间和班次组名称匹配的标记。 该标记可用于聊天中“ **To** ”行的@mentions或团队任何标准频道上的帖子中。

基于班次的标记可让用户实时接触轮班人员。 通知仅发送给在聊天或频道帖子中使用标记时轮班的人。 例如：

- 商店经理使用 @Cashiers 标记向所有轮班出纳员的频道发布公告。
- 护士使用 @CardiologistsOnCall 标记开始与所有待命心脏病专家聊天。

可以在 Microsoft Teams 管理中心打开或关闭该功能。 若要了解详细信息，请参阅[管理 Teams 中的标记](../../manage-tags.md)。

## <a name="search-the-audit-log-for-shifts-events"></a>在审核日志中搜索“班次”事件

**(预览版)**

你可以搜索审核日志以查看贵组织的班次活动。  若要详细了解如何搜索审核日志并查看审核日志中记录的[班次活动](../../audit-log-events.md#shifts-in-teams-activities)列表，请参阅[在审核日志中搜索 Teams 事件](../../audit-log-events.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://protection.office.com)中用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="related-articles"></a>相关文章

- [Teams 中的排班](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [排班数据常见问题解答](shifts-data-faq.md)
- [排班连接器](/microsoft-365/frontline/shifts-connectors)
- [一线员工的排班帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [向 Teams 中的用户分配策略](../../policy-assignment-overview.md)
