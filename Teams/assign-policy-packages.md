---
title: 将策略包分配给用户和组
author: KarliStites
ms.author: kastites
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
localization_priority: Normal
search.appverid: MET150
description: 了解向用户和组中用户和组分配策略包Microsoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574292"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>将策略包分配给用户和组

本文介绍向用户和组中用户和组分配策略包Microsoft Teams。 在阅读之前，请确保已阅读在 "分配策略 " [Teams - 入门](policy-assignment-overview.md)。

## <a name="assign-a-policy-package-to-users"></a>向用户分配策略包

Teams策略包是预定义的策略和策略设置的集合，可以分配给组织中具有相同或类似角色的用户。 每个策略包围绕用户角色设计，包括预定义的策略和策略设置，这些策略设置支持该角色的典型活动。 策略包的一些示例包括教育 (教师) 包和医疗保健 (医疗) 包。 有关详细信息，请参阅在 中[管理策略Teams。](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>将策略包分配给一个用户

1. 在管理中心的左侧导航Microsoft Teams，转到"**用户"，** 然后选择该用户。
2. 在用户的页面上，选择"策略 **"，** 然后在"策略包"**旁边** 选择"编辑 **"。**
3. 在"**分配策略包"** 窗格中，选择要分配的包，然后选择"保存 **"。**

![Teams用户的策略包分配管理中心屏幕截图](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>将策略包分配给多个用户

1. 在管理Microsoft Teams左侧导航中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。
2. 选择“管理用户”。
3. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，选择"保存 **"。**

![Teams多个用户的策略包分配的管理中心屏幕截图](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a>将策略包分配给组。

通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。

建议最多包含 50，000 个用户组将策略包分配到组，但它也将适用于较大的组。

分配策略包时，会立即将其分配给组。 但是，将策略分配传播到组的成员以后台操作方式执行，可能需要一些时间，具体取决于组的大小。 从组取消分配策略时，或者将成员添加到组或从组中删除成员时，也是如此。

> [!IMPORTANT]
> 在开始使用之前，必须了解 (规则)  ([组分配) 。](assign-policies-users-and-groups.md#group-assignment-ranking) [](assign-policies-users-and-groups.md#precedence-rules) 请务必阅读并了解本文前面 (组的策略分配) 了解哪些信息[](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>将策略包分配给管理中心中的一组用户

1. 登录到 Teams 管理中心。
2. 在左侧导航栏中，转到策略包页。
3. 选择"组策略分配"选项卡。
4. 选择 **"添加组**"，然后在"将策略包分配到组"窗格中执行以下操作：

    a. 搜索并添加要为其分配策略包的组。

    b. 选择策略包。

    c. 设置每个策略类型的排名。

    d. 选择"**应用"。**

![显示组策略分配](media/group-pkg-assignment.png)

5. 若要管理特定策略类型的排名，请导航到特定策略页。
6. 若要将策略包重新分配到组，请首先删除组策略分配。 然后，按照上述步骤将策略包分配到组。

### <a name="work-with-powershell"></a>使用 PowerShell

#### <a name="get-the-teams-powershell-module"></a>获取 Teams PowerShell 模块

有关分步指南，请参阅安装[Teams PowerShell。](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>将策略包分配给一组用户

使用 [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet 将策略包分配给组。 可以使用对象 ID、SIP 地址或电子邮件地址指定组。 分配策略包时，请 ([策略包) ](assign-policies-users-and-groups.md#group-assignment-ranking) 策略类型的组分配排名。

本示例将 Education_Teacher 策略包分配给一个组，TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的分配排名为 1，TeamsMeetingPolicy 的排名为 2。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>将策略包分配给一批用户

使用批处理策略包分配，可以一次将策略包分配给大量用户，而无需使用脚本。 使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。 然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。

根据用户的对象 ID 或会话启动协议 (SIP) 地址。 用户的 SIP 地址通常与 UPN (或电子邮件地址 (用户名) 相同，但这不是必需的。 如果用户是使用其 UPN 或电子邮件指定的，但其值不同于其 SIP 地址，则策略分配将失败。 如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且只会为批中剩余的唯一用户提供状态。

一个批最多包含 5，000 个用户。 为获得最佳结果，不要一次提交多个批次。 允许批处理在提交更多批之前完成处理。

### <a name="use-the-teams-powershell-module"></a>使用 Teams PowerShell 模块

如果尚未安装[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) Microsoft Teams， (运行以下代码来) 。 请确保安装版本 1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下代码连接到Teams并启动会话。

```powershell
Connect-MicrosoftTeams
```

系统提示时，使用管理员凭据登录。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>将策略包分配给一批用户

本示例使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将 Education_PrimaryStudent 策略包分配给一批用户。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>查看批处理分配的状态

运行以下代码获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批返回的操作 ```New-CsBatchPolicyAssignmentOperation``` ID。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果输出显示发生错误，请运行以下命令，获取有关 属性中的错误 ```UserState``` 的详细信息。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

有关详细信息，请参阅[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>相关主题

- [使用Teams管理策略](manage-teams-with-policies.md)
- [管理策略包Microsoft Teams](manage-policy-packages.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Teams 中分配策略 - 入门](policy-assignment-overview.md)