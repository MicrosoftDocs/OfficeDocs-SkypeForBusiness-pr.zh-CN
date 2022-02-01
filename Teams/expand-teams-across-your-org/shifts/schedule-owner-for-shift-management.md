---
title: 管理班次管理的计划所有者
author: lanachin
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
description: 了解如何管理排班所有者进行日程安排管理。 可以设置策略，将团队成员的权限提升为计划所有者。
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
ms.openlocfilehash: 12cf33f193e7f1d1a976e5cde8612df19108cb69
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288630"
---
# <a name="schedule-owner-for-shift-management"></a>排班管理计划所有者

## <a name="overview"></a>概述

使用"计划所有者"功能可以提升团队成员的权限，以便他们无需将员工成为团队所有者即可管理日程安排。 使用计划所有者权限，员工可以管理其团队的日程，而无需修改任何其他团队属性，例如更新、编辑或删除团队频道。

具有计划所有者权限的用户可以执行哪些操作？

- 创建、编辑和发布日程安排，以管理团队的班次分配。
- 查看和批准调班请求，包括调班和调班的请求。
- 管理 Shifts 中的设置，为团队启用某些功能。
- 查看和修改其团队的时间表，以处理员工工资单。

## <a name="why-schedule-owner"></a>为什么计划所有者？

如果没有"计划所有者"功能，日常业务功能可能会中断。 虽然团队所有者可帮助运行团队，但他们不一定是负责日常日程安排的人。 在这种情况下，仅将计划管理责任转移到另一个团队成员可简化团队内的日常操作，并消除两个拥有相同访问权限的团队成员的混淆。

## <a name="scenario"></a>使用场景

下面是组织如何使用"计划所有者"功能的示例。

在大型组织中工作，部门经理直接向应用商店经理报告。 应用商店经理在公司内拥有更多权限，是 Shifts 中的团队所有者。 另一方面，部门经理仅作为团队成员添加到班次。 虽然商店经理比部门经理具有更多的职位，但部门经理处理团队员工日常日程安排更合理。

*如果没有计划* 所有者，部门经理必须获得与团队所有者完全相同的权限。 最近，部门经理一直在移动信息并更改频道名称，这导致了商店经理工作的复杂性。 商店经理希望部门经理能够组织其日程安排，但不希望他们能够在班次之外更改团队中任何其他内容。

*使用计划* 所有者，可以授予部门经理计划权限，而无需任何其他团队所有者特权。

## <a name="manage-schedule-ownership"></a>管理计划所有权

作为管理员，可以使用策略来控制组织中计划管理所有权。 可以使用以下 PowerShell cmdlet 管理这些策略：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>示例 1

在此处，我们将创建名为 ScheduleOwnerPolicy 的新策略，并启用"计划所有者"功能。

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>示例 2

本示例将名为 ScheduleOwnerPolicy 的策略分配给名为 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>相关文章

- [在 Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [管理工作电话中一线员工基于排班Teams](manage-shift-based-access-flw.md) 
