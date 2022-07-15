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
description: 了解如何在 Teams 中为组织中的一线工作人员设置和管理 Shifts 应用。
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
ms.openlocfilehash: e97e90a3a6e97bd2637d63cf3ee0d0bceb57dc15
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819407"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理“班次”应用

## <a name="overview-of-shifts"></a>“班次”概述

Microsoft Teams 中的 Shifts 应用使一线工作人员保持连接和同步。它首先构建了移动设备，用于快速有效的时间管理和团队通信。 轮班允许一线工作人员及其经理使用其移动设备来管理计划并保持联系。

- 经理可创建、更新和管理团队的班次安排。 他们可以向一个人（“地板上洒了水”）或整个团队（“区域总经理将在 20 分钟后到达”）发送消息。 他们还可以发送政策文档、新闻公告和视频。
- 员工可查看即将到来的排班、查看当天还有谁的排班、申请调班或转班以及申请请假。

请务必知道 Shifts 当前不支持来宾。 这意味着在 Teams 中启用来宾访问时，无法将团队中的来宾添加到排班计划，他们也无法使用排班计划。

> [!Note]
> 有关不同平台上的“班次”功能的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>“班次”可用性

Teams 可用的所有企业 SKU 中均提供“班次”。

> [!NOTE]
> 政府社区云 (GCC) 环境中提供班次，但在 GCC High 或 DoD 环境中不可用。

## <a name="location-of-shifts-data"></a>“班次”数据的位置

转移数据目前存储在 Azure 中，位于亚太地区的数据中心 (APAC) 、欧盟 (欧盟) 和北美。 有关数据存储位置的详细信息，请参阅[我的数据在哪里？](http://o365datacentermap.azurewebsites.net/)。

若要详细了解 Shifts 数据，包括存储、保留、检索和加密 Shifts 数据，请参阅 [Shifts 数据常见问题解答](shifts-data-faq.md)。

## <a name="set-up-shifts"></a>设置“班次”

### <a name="enable-or-disable-shifts-in-your-organization"></a>在你的组织中启用或禁用“班次”

默认情况下，将为你组织中的所有 Teams 用户启用“班次”。 你可以在 Microsoft Teams 管理中心的[管理应用](../../manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索 Shifts 应用，选择它，然后将 **“状态** ”切换为 **“已阻止** ”或 **“允许**”。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>为你的组织中的特定用户启用或禁用“班次”

若要允许或阻止组织中的特定用户使用 Shifts，请确保在 [“管理应用](../../manage-apps.md) ”页上为组织启用了 Shifts。 然后创建自定义应用权限策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](../../teams-app-permission-policies.md)。

### <a name="pin-shifts-to-teams"></a>固定到 Teams 的班次

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>使用定制的一线应用体验将 Shifts 和其他应用固定到 Teams

Teams 中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定 Teams 中最相关的应用。 固定应用包括 Shifts、Walkie Talkie、Tasks 和 Approvals。 默认情况下，此功能处于启用状态，为一线员工提供根据其需求定制的现新体验。

应用固定到应用栏（Teams 桌面客户端侧面和 Teams 移动客户端底部的栏），用户可在其中快速轻松地访问应用栏。

若要了解详细信息，包括体验如何与你设置的应用策略配合使用，请参阅 [一线员工的 Tailor Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>使用应用设置策略将 Shifts 固定到 Teams

通过应用设置策略，可以自定义 Teams 以固定对用户最重要的应用。

可以通过添加 Shifts [应用创建自定义应用设置策略](../../teams-app-setup-policies.md) ，然后将 [策略分配](../../assign-policies-users-and-groups.md) 给用户。 或者，可以使用属于一线辅助角色和一线管理器策略包的应用设置策略。

Teams 中的 [策略包](../../manage-policy-packages.md) 是预定义的策略和策略设置的集合，你可以将其分配给在组织中具有类似角色的用户。 一线工作者和一线管理器策略包中的一组策略包括一个应用设置策略，该策略固定 Shifts 应用和其他支持该角色的通信和协作活动的应用。

建议使用前线辅助角色和一线管理器策略包，以简化、简化和帮助在管理一线员工的策略时提供一致性。

## <a name="search-the-audit-log-for-shifts-events"></a>在审核日志中搜索“班次”事件

**(预览版)**

你可以搜索审核日志以查看贵组织的班次活动。  若要详细了解如何搜索审核日志并查看审核日志中记录的[班次活动](../../audit-log-events.md#shifts-in-teams-activities)列表，请参阅[在审核日志中搜索 Teams 事件](../../audit-log-events.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://protection.office.com)中启用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="related-articles"></a>相关文章

- [Teams 中的排班](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [转移数据常见问题解答](shifts-data-faq.md)
- [Shifts 连接器](/microsoft-365/frontline/shifts-connectors)
- [一线工人的轮班帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [向 Teams 中的用户分配策略](../../policy-assignment-overview.md)
