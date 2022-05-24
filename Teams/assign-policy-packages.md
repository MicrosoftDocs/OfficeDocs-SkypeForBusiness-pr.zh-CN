---
title: 将策略包分配给用户和组
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解在Microsoft Teams中为用户和组分配策略包的不同方法。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 48391db005ca7d40081c0aeb22f71be58fcc9f9f
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646521"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>将策略包分配给用户和组

本文介绍将策略包分配给Microsoft Teams中的用户和组的不同方法。 阅读前，请确保已[阅读 Teams 中的分配策略 - 入门](policy-assignment-overview.md)。

> [!NOTE]
> 为了接受自定义策略包分配，每位用户都需要高级通信加载附加产品。 有关详细信息，请参阅 [Microsoft Teams 高级通信附加产品](/microsoftteams/teams-add-on-licensing/advanced-communications)。

## <a name="assign-a-policy-package-to-users"></a>向用户分配策略包

Teams中的策略包是预定义的策略和策略设置的集合，你可以将其分配给在组织中具有相同或类似角色的用户。 每个策略包都是围绕用户角色设计的，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型活动。 一些策略包示例包括教育 (教师) 包和医疗保健 (临床工作者) 包。 若要了解详细信息，请参阅[Teams中的管理策略包](manage-policy-packages.md)。

### <a name="assign-a-policy-package-to-one-user"></a>将策略包分配给一个用户

1. 在Microsoft Teams管理中心的左侧导航中，转到 **“用户**”，然后选择用户。

2. 在用户的页面上，选择“ **策略**”，然后在“ **策略”包** 旁边选择 **“编辑**”。

3. 在 **“分配策略包** ”窗格中，选择要分配的包，然后选择 **“保存**”。

![Teams管理中心屏幕截图，用于向用户分配策略包。](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>将策略包分配给多个用户

1. 在Microsoft Teams管理中心的左侧导航中，转到“策略 **”包**，然后单击包名称左侧，选择要分配的策略包。

2. 选择“管理用户”。

3. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。

4. 添加完用户后，选择 **“保存**”。


![Teams管理中心屏幕截图，用于向多个用户分配策略包。](media/assign-policypackages-multipleusers.png)


## <a name="assign-a-policy-package-to-a-group"></a>将策略包分配给组。

通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。

对于最多 50，000 个用户的组，建议将策略包分配给组，但它也适用于较大的组。

分配策略包时，会立即将其分配给组。 但是，将策略分配传播到组的成员将作为后台操作执行，并且可能需要一些时间，具体取决于组的大小。 当未从组中分配策略，或者将成员添加到组或从组中删除时，也是如此。

> [!IMPORTANT]
> 在开始之前，请务必了解 ([优先规则](assign-policies-users-and-groups.md#precedence-rules)) 和 ([组分配排名](assign-policies-users-and-groups.md#group-assignment-ranking)) 。 请确保阅读并理解 (本文前面) [组的策略分配需要了解](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups) 的概念。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>将策略包分配给管理中心内的一组用户

1. 登录到 Teams 管理中心。

2. 在左侧导航栏中，转到策略包页。

3. 选择“组策略分配”选项卡。

4. 选择 **“添加组**”，然后在“将策略包分配到组”窗格中，执行以下操作：

    1. 搜索并添加要将策略包分配到的组。

    1. 选择策略包。

    1. 设置每个策略类型的排名。

    1. 选择 **“应用**”。


       ![显示组策略分配。](media/group-pkg-assignment.png)

5. 若要管理特定策略类型的排名，请导航到特定策略页。

6. 若要将策略包重新分配到组，请先删除组策略分配。 然后，按照上述步骤将策略包分配给组。

### <a name="work-with-powershell"></a>使用 PowerShell

#### <a name="get-the-teams-powershell-module"></a>获取 Teams PowerShell 模块

有关分步指南，请[参阅安装Teams PowerShell](teams-powershell-install.md)。

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>将策略包分配给一组用户

使用 [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet 将策略包分配给组。 可以使用对象 ID、SIP 地址或电子邮件地址指定组。 分配策略包时，请为策略包中的每个策略类型指定 ([组分配排名](assign-policies-users-and-groups.md#group-assignment-ranking)) 。

在此示例中，我们将Education_Teacher策略包分配给 TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的分配排名为 1 的组，TeamsMeetingPolicy 的排名为 2。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>将策略包分配给一批用户

通过批处理策略包分配，可以一次向大量用户分配策略包，而无需使用脚本。 使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。 然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。

根据用户的对象 ID 或会话启动协议 (SIP) 地址指定用户。 用户的 SIP 地址通常具有与 UPN) 或电子邮件地址 (用户主体名称相同的值，但这不是必需的。 如果用户是使用其 UPN 或电子邮件指定的，但其值与其 SIP 地址不同，则该用户的策略分配将失败。 如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且仅为该批处理中剩余的唯一用户提供状态。

批处理最多包含 5，000 个用户。 为了获得最佳结果，请不要一次提交多个批次。 允许批处理完成，然后再提交更多批处理。

### <a name="use-the-teams-powershell-module"></a>使用 Teams PowerShell 模块

如果尚未) ，请运行以下命令安装 [Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams) (。 请确保安装版本 1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下命令以连接到Teams并启动会话。

```powershell
Connect-MicrosoftTeams
```

出现提示时，请使用管理员凭据登录。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>将策略包分配给一批用户

在此示例中，我们使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将Education_PrimaryStudent策略包分配给一批用户。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>查看批处理分配的状态

运行以下命令以获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批处理返回 `New-CsBatchPolicyAssignmentOperation` 的操作 ID。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果输出显示出错，请运行以下命令以获取有关属性中的错误的 `UserState` 详细信息。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

若要了解详细信息，请参阅 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)。

## <a name="related-topics"></a>相关主题

- [使用策略管理Teams](manage-teams-with-policies.md)
- [在Microsoft Teams中管理策略包](manage-policy-packages.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在Teams中分配策略 - 入门](policy-assignment-overview.md)
