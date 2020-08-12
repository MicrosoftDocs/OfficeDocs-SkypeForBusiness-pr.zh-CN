---
title: 从用户中删除 RestrictedAnonymousAccess 团队会议策略
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 了解如何从组织中的用户删除 RestrictedAnonymousAccess 团队会议策略。
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640971"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>从用户中删除 RestrictedAnonymousAccess 团队会议策略

Microsoft 团队中的[会议策略](meeting-policies-in-teams.md)用于控制会议参与者对由组织中的用户安排的会议参与者可用的功能。 

团队包含名为 RestrictedAnonymousAccess 的内置策略，其中包含预定义的设置，其中包括限制匿名用户启动会议的预定义设置。  (匿名用户是指没有经过身份验证的用户。 ) 无法通过管理员编辑或更改会议策略中的预定义设置。

本文介绍如何使用 PowerShell 从分配了此策略的用户中删除 RestrictedAnonymousAccess 会议策略。 若要了解有关如何使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

## <a name="before-you-start"></a>开始前

安装并连接到[Skype For Business PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)。 有关分步指南，请参阅[安装 Microsoft 团队 PowerShell](teams-powershell-install.md)。

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>为你的组织获取团队会议策略分配

运行以下操作，获取组织的团队会议策略分配。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

在此示例中，返回以下输出，这显示为两个用户分配了 RestrictedAnonymousAccess 会议策略。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>取消分配用户的 RestrictedAnonymous 会议策略

若要删除用户的 RestrictedAnonymous 会议策略，你可以使用[CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet （如果你有少量用户 (例如，小于100用户) 。 如果您有大量用户 (例如，超过100用户) ，则使用[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet 提交批处理操作将更高效。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>使用授权 CsTeamsMeeting 策略 cmdlet

运行以下操作以从用户中删除 RestrictedAnonymous 会议策略。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>使用 CsBatchPolicyAssignmentOperation cmdlet

通过[批处理策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)，您可以删除或更新策略的最大用户数为5000。 例如，如果您有超过5000的用户，则需要提交多个批次。 为获得最佳结果，请不要一次提交多个批次。 允许批完成处理，然后再提交更多批。

> [!NOTE]
> [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 位于团队 PowerShell 模块中。 在执行这些步骤之前，请安装并连接到[团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。 有关分步指南，请参阅[安装 Microsoft 团队 PowerShell](teams-powershell-install.md)。

运行以下命令以从一批用户中删除 RestrictedAnonymousAccess 会议策略。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>获取批处理作业的状态

每个批处理作业都将返回一个操作 ID，您可以使用该 ID 跟踪作业的进度和状态，并确定可能出现的任何故障。 例如，运行以下内容：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

请确保**ErrorCount**为**0** (零) 和**OverallStatus**已**完成**。

## <a name="related-topics"></a>相关主题

- [管理团队中的会议策略](meeting-policies-in-teams.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向团队中的用户分配策略](assign-policies.md)
