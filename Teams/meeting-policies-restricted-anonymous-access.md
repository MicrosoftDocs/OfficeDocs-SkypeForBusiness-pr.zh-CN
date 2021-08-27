---
title: 从用户删除 RestrictedAnonymousAccess Teams 会议策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 了解如何从组织中用户Teams RestrictedAnonymousAccess 会议策略。
ms.openlocfilehash: fbb34974c435db12880ab68b7af4372a17a6b63b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590776"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>从用户删除 RestrictedAnonymousAccess Teams 会议策略

[会议](meeting-policies-in-teams.md)Microsoft Teams用于控制组织中用户安排的会议的会议参与者可用的功能。 

Teams包括名为 RestrictedAnonymousAccess 的内置策略，其中包含预定义的设置，其中包括限制匿名用户启动会议。  (匿名用户是尚未经过身份验证的用户。) 管理员无法编辑或更改会议策略中的预定义设置。

本文演示如何使用 PowerShell 从分配了此策略的用户中删除 RestrictedAnonymousAccess 会议策略。 若要详细了解如何使用 PowerShell Teams，请参阅[powerShell](teams-powershell-overview.md)Teams概述 。

## <a name="before-you-start"></a>开始前

安装并连接到[Skype for Business PowerShell 模块](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。 有关分步指南，请参阅安装[Microsoft Teams PowerShell。](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>获取Teams组织的会议策略分配

运行以下代码，Teams组织的会议策略分配。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

本示例返回以下输出，其中显示为两个用户分配了 RestrictedAnonymousAccess 会议策略。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>从用户取消分配 RestrictedAnonymous 会议策略

若要从用户中删除 RestrictedAnonymous 会议策略，可以使用 [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet（如果用户数较少 (例如，少于 100 个用户) ）。 如果有大量用户 (例如，超过 100 个用户) ，则使用  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet 提交批处理操作会更有效。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>使用 Grant-CsTeamsMeeting Policy cmdlet

运行以下操作，从用户中删除 RestrictedAnonymous 会议策略。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>使用 New-CsBatchPolicyAssignmentOperation cmdlet

使用 [批处理策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)时，可以删除或更新策略的最大用户数是一次 5，000。 例如，如果用户数超过 5，000，则需要提交多个批次。 为获得最佳结果，请勿一次提交多个批。 允许批处理在提交更多批之前完成处理。

> [!NOTE]
> [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet 位于 powerShell Teams中。 在按照这些步骤操作之前，请安装并连接到 Teams [PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。 有关分步指南，请参阅安装[Microsoft Teams PowerShell。](teams-powershell-install.md)

运行以下命令，从一批用户中删除 RestrictedAnonymousAccess 会议策略。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>获取批处理分配的状态

每个批处理分配都返回一个操作 ID，可用于跟踪分配的进度和状态，并确定可能发生的任何故障。 例如，运行以下代码：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

确保 **ErrorCount** 为 **0** (零) **OverallStatus** 为 **"已完成"。**

## <a name="related-topics"></a>相关主题

- [管理 Teams 中的会议策略](meeting-policies-in-teams.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)