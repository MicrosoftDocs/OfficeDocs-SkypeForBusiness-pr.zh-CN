---
title: 将策略分配给用户和组
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
description: 了解向 Microsoft Teams 中的用户和组分配策略的不同方法。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: a57c038242c06f4305410e68cff907aef6889841
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396646"
---
# <a name="assign-policies-to-users-and-groups"></a>将策略分配给用户和组

本文探讨了向 Microsoft Teams 中的用户和组分配策略的不同方法。 阅读前，请确保已 [阅读 Teams 中的分配策略 - 入门](policy-assignment-overview.md)。

## <a name="assign-a-policy-to-individual-users"></a>向单个用户分配策略

按照以下步骤一次向单个用户或几个用户分配策略。

### <a name="use-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

若要将策略分配给用户，请执行以下操作：

1. 在 [Microsoft Teams 管理中心的](https://admin.teams.microsoft.com)左侧导航中，转到 **“用户** > **管理用户**”。
2. 单击用户名左侧选择用户，然后选择 **“编辑设置**”。
3. 选择要分配的策略，然后选择 **“应用**”。

    :::image type="content" source="media/assign-policies-users-edit-settings.png"  alt-text="“管理用户”下的“编辑设置”窗格的屏幕截图。" lightbox="media/assign-policies-users-edit-settings-expanded.png":::

> [!NOTE]
> 若要取消向用户分配专用策略，可以将每个策略设置为 **全局 (组织范围的默认)**。 还可以为直接分配给策略的所有用户批量删除策略分配。 若要了解详细信息，请 [批量阅读 Unassign 策略](#unassign-policies-in-bulk)。

还可以执行以下操作，将策略分配给用户：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到策略页。
2. 单击策略名称左侧，选择要分配的策略。
3. 选择 **“分配用户**”。
4. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
5. 添加完用户后，选择 **“应用**”。

    :::image type="content" source="media/assign-policies-user-example.png" alt-text="显示如何通过第二种方法在 Teams 管理中心向用户分配策略的屏幕截图。" lightbox="media/assign-policies-user-example-expanded.png":::

### <a name="use-powershell"></a>使用 PowerShell

每个策略类型都有自己的 cmdlet 集用于管理它。 `Grant-`使用给定策略类型的 cmdlet 来分配策略。 例如，使用 `Grant-CsTeamsMeetingPolicy` cmdlet 向用户分配 Teams 会议策略。 这些 cmdlet 包含在 Teams PowerShell 模块中，并记录在[Skype for Business cmdlet 参考](/powershell/skype)中。

 如果尚未) ，请下载并安装 [Teams PowerShell 公开发布](https://www.powershellgallery.com/packages/MicrosoftTeams/) (，然后运行以下命令进行连接。

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。
>
> 如果使用的是最新的 [Teams PowerShell 公开版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装Skype for Business联机连接器。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

在此示例中，我们将名为“学生会议策略”的 Teams 会议策略分配给名为 Reda 的用户。

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

若要了解详细信息，请 [阅读通过 PowerShell 管理策略](teams-powershell-managing-teams.md#manage-policies-via-powershell)。

## <a name="assign-a-policy-to-a-group"></a>将策略分配给组

通过向组分配策略，可以将策略分配给一组用户，例如安全组、组织单位或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。

对于最多 50，000 个用户的组，建议将策略分配给组，但它也适用于较大的组。

分配策略时，会立即将其分配给组。 但是，将策略分配传播到组的成员将作为后台操作执行，并且可能需要一些时间，具体取决于组的大小。 当未从组中分配策略，或者将成员添加到组或从组中删除时，也是如此。

组策略分配仅传播给属于组的直接成员的用户。 分配不会传播到嵌套组的成员。

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>需要了解的有关向组分配策略的信息

在开始之前，请务必了解优先规则和组分配排名。

#### <a name="precedence-rules"></a>优先级规则

对于给定的策略类型，根据以下内容确定用户的有效策略：

- 直接分配给用户的策略优先于分配给组的相同类型的任何其他策略。 换句话说，如果直接为用户分配给定类型的策略，则该用户不会从组继承相同类型的策略。 这也意味着，如果用户具有直接分配给他们的给定类型的策略，则必须先从用户中删除该策略，然后才能从组中继承相同类型的策略。
- 如果用户没有直接分配给他们的策略，并且是两个或多个组的成员，并且每个组的策略分配的类型相同，则用户将继承排名最高的组分配的策略。
- 如果用户不是分配了策略的任何组的成员，则该策略类型的全局 (组织范围的默认) 策略将应用于用户。

根据以下规则更新用户的有效策略：

- 将用户添加到或从分配了策略的组中删除时。
- 策略是从组中取消分配的。
- 将删除直接分配给用户的策略。

#### <a name="group-assignment-ranking"></a>组分配排名

> [!NOTE]
> 给定策略类型可分配给该类型的策略实例中最多 64 个组。

将策略分配给组时，请为组分配指定排名。 如果用户是两个或更多组的成员，并且为每个组分配了相同类型的策略，则此排名用于确定用户应作为其有效策略继承的策略。

组分配排名相对于相同类型的其他组分配。 例如，如果要将调用策略分配给两个组，请将一个分配的排名设置为 1，另一个分配的排名设置为 2，其中 1 个是排名最高的。 组分配排名指示哪些组成员身份比其他组成员身份在继承方面更重要或更相关。

例如，有两个组：Store Employees 和 Store Manager。 这两个组分别分配有 Teams 呼叫策略、应用商店员工呼叫策略和应用商店经理呼叫策略。 对于属于这两个组的商店经理来说，他们作为经理的角色比他们作为员工的角色更相关，因此分配给 Store Manager 组的调用策略应具有更高的排名。

|组 |调用策略名称的 Teams  |等级|
|---------|---------|---|
|Store Manager   |应用商店经理呼叫策略         |1|
|应用商店员工    |应用商店员工呼叫策略      |2|

如果未指定排名，则策略分配的排名最低。

### <a name="in-the-teams-admin-center"></a>在 Teams 管理中心

> [!NOTE]
> 目前，使用 Microsoft Teams 管理中心的组的策略分配仅适用于 Teams 呼叫策略、Teams 呼叫寄存策略、Teams 策略、Teams 实时事件策略、Teams 会议策略和 Teams 消息传送策略。 对于其他策略类型，请使用 PowerShell。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到策略类型页。 例如，转到 **会议** > **会议策略**。
2. 选择“ **组策略分配** ”选项卡。
3. 选择 **“添加组**”，然后在 **“将策略分配到组** ”窗格中执行以下操作：
    1. 搜索并添加要将策略分配到的组。
    2. 设置组分配的排名。
    3. 选择要分配的策略。
    4. 选择“**应用**”。

        :::image type="content" source="media/assign-policies-groups-messaging.png" alt-text="显示如何将策略分配给 Teams 管理中心中的组的屏幕截图。" lightbox="media/assign-policies-groups-messaging-expanded.png":::

若要删除组策略分配，请在策略页的“ **组策略分配** ”选项卡上选择组分配，然后选择 **“删除**”。

若要更改组分配的排名，需要先删除组策略分配。 然后，按照上述步骤将策略分配给组。

此视频演示创建自定义会议策略并将其分配给组的步骤。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53Ws0?autoplay=false]

### <a name="use-the-powershell-option"></a>使用 PowerShell 选项

> [!NOTE]
> 目前，使用 PowerShell 的组的策略分配不适用于所有 Teams 策略类型。 有关支持的策略类型的列表，请参阅 [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) 。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安装并连接到 Microsoft Teams PowerShell 模块

有关分步指南，请 [参阅安装 Teams PowerShell](teams-powershell-install.md)。

#### <a name="assign-a-policy-to-a-group-of-users"></a>将策略分配给一组用户

使用 [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet 将策略分配给组。 可以使用对象 ID、SIP 地址或电子邮件地址指定组。

在此示例中，我们将名为“零售经理会议策略”的 Teams 会议策略分配给分配排名为 1 的组。

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>获取组的策略分配

使用 [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet 获取分配给组的所有策略。 组始终按其组 ID 列出，即使其 SIP 地址或电子邮件地址用于分配策略。

在此示例中，我们检索分配给特定组的所有策略。

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

在此示例中，我们将返回分配有 Teams 会议策略的所有组。

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>从组中删除策略

使用 [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet 从组中删除策略。 从组中删除策略时，将更新分配给该组且排名较低的相同类型的其他策略的优先级。 例如，如果删除排名为 2 的策略，则将更新排名为 3 和 4 的策略以反映其新排名。 以下两个表显示了此示例。

下面列出了 Teams 会议策略的策略分配和优先级。

|组名称  |策略名称  |等级|
|---------|---------|---------|
|销售    |销售策略       | 1        |
|西部区域     |西部区域策略         |2         |
|划分    |除法策略         |3         |
|附属   |辅助策略        |4         |

如果从“西部区域”组中删除“西部区域”策略，则策略分配和优先级将按如下所示更新。

|组名称  |策略名称  |等级|
|---------|---------|---------|
|销售    |销售策略       | 1        |
|划分    |除法策略         |2         |
|附属   |辅助策略        |3        |

在此示例中，我们将从组中删除 Teams 会议策略。

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>更改组的策略分配

> [!NOTE]
> [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet 将很快推出。 同时，若要更改组策略分配，可以从组中删除当前策略分配，然后添加新的策略分配。

将策略分配给组后，可以使用 [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet 更改该组的策略分配，如下所示：

- 更改排名
- 更改给定策略类型的策略
- 更改给定策略类型的策略和排名

在此示例中，我们将组的 Teams 调用寄存策略更改为名为 SupportCallPark 的策略，并将分配排名更改为 3。

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>更改用户的有效策略

下面是一个示例，说明如何更改直接分配策略的用户的有效策略。

首先，我们将 [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet 与参数一起 `PolicySource` 使用，以获取与用户关联的 Teams 会议广播策略的详细信息。

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

输出显示，用户直接分配了名为 **“员工事件**”的 Teams 会议广播策略，该策略优先于分配给用户所属组的名为 **“供应商直播事件** ”的策略。

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

现在，我们将从用户中删除“员工事件”策略。 这意味着用户不再具有直接分配给他们的 Teams 会议广播策略，并将继承分配给用户所属组的供应商实时事件策略。

在 Skype for Business PowerShell 模块中使用以下 cmdlet 执行此操作。

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

在 Teams PowerShell 模块中使用以下 cmdlet 通过批处理策略分配大规模执行此操作，其中$users是指定的用户列表。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>将策略分配给一批用户

### <a name="use-the-admin-center"></a>使用管理中心

若要批量向用户分配策略，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，选择 **“用户**”。
2. 搜索要将策略分配给或筛选视图以显示所需用户的用户。
3. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请选择表顶部) &#x2713; (复选标记。
4. 选择 **“编辑设置**”，进行所需的更改，然后选择“ **应用**”。

若要查看策略分配的状态，请在选择“**应用**”以提交策略分配后显示在 **“用户**”页面顶部的横幅中，选择 **“活动日志**”。 或者，在 Microsoft Teams 管理中心的左侧导航中，转到 **仪表板**，然后在 **活动日志** 下选择 **“查看详细信息**”。 活动日志显示过去 30 天内通过 Microsoft Teams 管理中心向 20 多名用户批处理的策略分配。 若要了解详细信息，请参[阅活动日志中的策略分配。](activity-log.md)

### <a name="use-powershell-method"></a>使用 PowerShell 方法

> [!NOTE]
> 目前，使用 PowerShell 的批处理策略分配不适用于所有 Teams 策略类型。 有关支持的策略类型的列表，请参阅 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。

通过批处理策略分配，可以一次向大型用户集分配策略，而无需使用脚本。 使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略。 作业将作为后台操作处理，并为每个批处理生成操作 ID。 然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。

根据用户的对象 ID 或会话启动协议 (SIP) 地址指定用户。 用户的 SIP 地址通常具有与 UPN) 或电子邮件地址 (用户主体名称相同的值，但这不是必需的。 如果用户是使用其 UPN 或电子邮件指定的，但其值与其 SIP 地址不同，则该用户的策略分配将失败。 如果批处理包含重复用户，则重复项将在处理前从批处理中删除，并且仅为该批处理中剩余的唯一用户提供状态。

批处理最多可包含 5,000 个用户。 为了获得最佳结果，请不要一次提交多个批次。 允许批处理完成，然后再提交更多批处理。

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>安装并连接到 Teams PowerShell 模块

运行以下命令以安装 [Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。 请确保安装版本 1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下命令以连接到 Teams 并启动会话。

```powershell
Connect-MicrosoftTeams
```

出现提示时，请使用管理员凭据登录。

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>安装并连接到 Azure AD PowerShell for Graph 模块 (可选) 

如果尚未) 并连接到 [Azure AD，则可能还需要下载并安装 Azure AD PowerShell for Graph 模块](/powershell/azure/active-directory/install-adv2) (，以便可以检索组织中的用户列表。

运行以下命令以连接到 Azure AD。

```powershell
Connect-AzureAD
```

出现提示时，请使用用于连接到 Teams 的相同管理员凭据登录。

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>将安装策略分配给一批用户

在此示例中，我们使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 向 users_ids.text 文件中列出的一批用户分配名为 HR 应用安装策略的应用设置策略。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $user_ids -OperationName "Example 1 batch"
```

在此示例中，我们连接到 Azure AD 以检索用户集合，然后使用其 SIP 地址将名为“新建雇佣消息传送策略”的消息传送策略分配给一批用户。

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>获取批处理分配的状态

运行以下命令以获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批处理返回 `New-CsBatchPolicyAssignmentOperation` 的操作 ID。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果输出显示出错，请运行以下命令以获取有关属性中的错误的 `UserState` 详细信息。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

若要了解详细信息，请参阅 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)。

## <a name="unassign-policies-in-bulk"></a>批量取消分配策略

批量取消分配策略时，将删除通过直接分配分配给单个用户的策略分配。 这在以下方案中非常有用：

1. **若要使全局 (组织范围的默认) 或组策略分配生效：** 由于 [优先规则](policy-assignment-overview.md#which-policy-takes-precedence)，全局 (组织范围的默认) 或组策略分配不会对具有直接策略分配的使用者生效。 作为管理员，可以批量取消分配策略以删除直接分配，以便全局 (组织范围的默认) 或组策略分配生效。
1. **从 Teams 教育向导中清理策略分配：** Teams 教育策略向导为学生应用全局策略默认值，并使用组策略分配为一组员工分配自定义策略集。 管理员需要清理全局 (组织范围内默认) 和组作业的学生和教职员工个人策略才能生效。
1. **删除不正确的策略分配：** 如果有大量单个用户通过直接分配分配了错误的策略，则可以批量使用未分配的策略来删除这些分配。

 可以从 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)批量取消分配策略。

1. 转到 **“用户** > **管理用户**”。
2. 在页面右上角，从 **“操作**”下拉菜单 **中批量选择“取消分配** 策略”。

    ![在 Teams 管理中心管理用户页面。](media/manage-users-unassign-policies.png)

    > [!NOTE]
    > 还可以通过选择策略并选择 **“管理用户**”，从单个策略页中取消分配策略。

3. 选择策略类型。

    ![在 Teams 管理中心批量页中取消分配策略。](media/unassign-policies-page.png)

4. 选择要重新分配的策略，然后选择 **“加载数据** ”以获取当前分配给该策略的用户数。

    > [!IMPORTANT]
    > 选择策略时，将从该策略中删除 **所有** 单独分配的用户。

5. 选择 **“取消分配”策略**。

取消分配策略后，可以在 [活动日志](https://admin.teams.microsoft.com/activity-log)中查看操作详细信息。

## <a name="related-topics"></a>相关主题

- [使用策略管理 Teams](manage-teams-with-policies.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Teams 中分配策略 - 入门](policy-assignment-overview.md)
