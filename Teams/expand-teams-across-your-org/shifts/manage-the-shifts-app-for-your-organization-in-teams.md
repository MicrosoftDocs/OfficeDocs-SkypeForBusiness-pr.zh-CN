---
title: 为组织管理“班次”应用
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: 了解如何在应用程序中为组织的一线Teams设置和管理 Shifts 应用。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d38af9f55f1620a1f38ad5860c71366201bb9444
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039900"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理“班次”应用

## <a name="overview-of-shifts"></a>“班次”概述

应用中的 Shifts Microsoft Teams一线员工保持连接和同步。它首先构建为移动版，用于快速高效的时间管理和团队通信。 轮班允许一线员工及其经理使用其移动设备管理日程安排并保持联系。

- 经理可创建、更新和管理团队的班次安排。 他们可以向一个人（“地板上洒了水”）或整个团队（“区域总经理将在 20 分钟后到达”）发送消息。 他们还可以发送政策文档、新闻公告和视频。
- 员工可查看即将到来的排班、查看当天还有谁的排班、申请调班或转班以及申请请假。

必须知道 Shifts 目前不支持来宾。 这意味着在 Teams 中启用来宾访问时，无法将团队中的来宾添加到排班计划，他们也无法使用排班计划。

> [!Note]
> 有关不同平台上的“班次”功能的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>“班次”可用性

Teams 可用的所有企业 SKU 中均提供“班次”。

> [!NOTE]
> 班次可用于政府社区云 (GCC) 环境，但不适用于GCC或 DoD 环境。

## <a name="location-of-shifts-data"></a>“班次”数据的位置

Shifts 数据当前存储在 Azure 中，数据中心位于亚太 (APAC) 、欧盟 () 和北美。 有关数据存储位置的详细信息，请参阅[我的数据在哪里？](http://o365datacentermap.azurewebsites.net/)。

若要详细了解 Shifts 数据，包括 Shifts 数据的存储、保留、检索和加密，请参阅 [Shifts 数据常见问题解答](shifts-data-faq.md)。

## <a name="set-up-shifts"></a>设置“班次”

### <a name="enable-or-disable-shifts-in-your-organization"></a>在你的组织中启用或禁用“班次”

默认情况下，将为你组织中的所有 Teams 用户启用“班次”。 你可以在 Microsoft Teams 管理中心的[管理应用](../../manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索"Shifts"应用，将其选中，然后将"状态"切换为 **"已阻止**"或"允许 **"**。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>为你的组织中的特定用户启用或禁用“班次”

若要允许或阻止组织中特定用户使用 Shifts，请确保在"管理应用"页面上为组织启用 [Shifts](../../manage-apps.md) 。 然后创建自定义应用权限策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](../../teams-app-permission-policies.md)。

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>使用应用设置策略将 Shifts 固定到Teams

应用设置策略让你自定义 Teams 来突出显示组织中对用户最重要的应用。 在策略中设置的应用会固定到应用栏（&mdash;Teams 桌面客户端的边栏以及 Teams 移动客户端的底栏&mdash;），用户可以快速方便地访问。

可以通过添加 Shifts [应用创建自定义](../../teams-app-setup-policies.md) 应用设置策略，然后将 [该策略分配给](../../assign-policies-users-and-groups.md) 用户。 或者，可以使用属于"前端辅助角色"和"前端管理器"策略包的应用设置策略。

Teams[策略](../../manage-policy-packages.md)包是预定义的策略和策略设置的集合，可以分配给组织中具有类似角色的用户。 前端辅助角色和前端管理器策略包中的策略集包括一个应用设置策略，该策略固定 Shifts 应用和支持该角色的通信和协作活动的其他应用。

我们建议使用一线辅助角色和前端管理器策略包，因为它们可简化、简化，并帮助在管理一线员工的策略时提供一致性。

## <a name="search-the-audit-log-for-shifts-events"></a>在审核日志中搜索“班次”事件

**（处于预览阶段）**

你可以搜索审核日志以查看贵组织的班次活动。  若要详细了解如何搜索审核日志并查看审核日志中记录的[班次活动](../../audit-log-events.md#shifts-in-teams-activities)列表，请参阅[在审核日志中搜索 Teams 事件](../../audit-log-events.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://protection.office.com)中启用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="related-articles"></a>相关文章

- [Teams 中的排班](../shifts-for-teams-landing-page.md)
- [班次数据常见问题解答](shifts-data-faq.md)
- [Shifts 连接线](shifts-connectors.md)
- [一线员工排班帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [向 Teams 中的用户分配策略](../../policy-assignment-overview.md)
