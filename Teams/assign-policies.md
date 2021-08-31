---
title: 向 Microsoft Teams 中的用户分配策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: 了解在不同位置向用户分配策略的不同Microsoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 858a28843fc883712ab12b868eca505069e5ab4f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727881"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>向 Microsoft Teams 中的用户分配策略

作为管理员，可以使用策略来控制Teams用户可用的功能。 例如，有调用策略、会议策略和消息传递策略，仅举几例。

组织具有不同类型的用户，具有独特的需求。 通过创建和分配的自定义策略，可以根据这些需求为不同的用户集定制策略设置。

若要轻松管理组织中策略，Teams多种方法将策略分配给用户。 将策略直接分配给用户，不管是单独分配还是大规模分配，或者用户作为其成员的组。 还可使用策略包将预设的策略集合分配给组织中具有类似角色的用户。 选择的选项取决于要管理的策略数以及要为其分配策略的用户数。 全局 (组织范围内的默认) 策略适用于组织中的最大用户数。 只需将策略分配给需要专用策略的用户。

本文介绍可以将策略分配给用户的不同方法，以及何时使用策略的建议方案。

## <a name="which-policy-takes-precedence"></a>哪些策略优先？

用户针对每种策略类型都有一个有效策略。 用户有可能直接分配策略，并且也是分配了相同类型的策略的一个或多个组的成员。 在这类方案中，哪一种策略优先？ 用户的有效策略根据优先级规则确定，如下所示。

如果直接为用户分配了一个策略 (单独分配，或者通过批处理分配) ，则该策略优先。 在下面的可视化示例中，用户的有效策略是直接分配给用户的"万网百元"会议策略。

![显示直接分配策略优先的示意图。](media/assign-policies-example-directly-assigned.png)

如果未直接为用户分配给定类型的策略，则分配给该用户是其中一个成员的组的策略优先。 如果用户是多个组的成员，则具有给定策略类型最高 [组分配排名](#group-assignment-ranking) 的策略优先。

在此可视示例中，用户的有效策略是 Exec Teams 和 HD 策略，相对于用户所参与的其他组，分配排名最高，并且还分配了相同策略类型的策略。  

![显示从组继承的策略如何优先的示意图。](media/assign-policies-example-group.png)

如果用户未直接分配策略或不是任何分配了策略的组的成员，该用户会获取该策略类型的全局 (组织范围默认) 策略。 下面是一个可视示例。

![显示全局策略如何优先的示意图。](media/assign-policies-example-global.png)

若要了解有关详细信息，请参阅 [优先级规则](#precedence-rules)。

## <a name="ways-to-assign-policies"></a>分配策略的方法

下面概述了可以如何向用户分配策略，以及为每个用户分配策略的建议方案。 选择链接以了解更多信息。

在将策略分配给单个用户或组之前，请首先设置全局 (组织范围的默认 [) 策略](#set-the-global-policies) ，以便它们适用于组织中的最多用户。  设置全局策略后，只需将策略分配给需要专用策略的用户。

|执行此操作  |如果...  | 使用...
|---------|---------|----|
|[向单个用户分配策略](#assign-a-policy-to-individual-users)    | 你刚Teams入门，或者只需向少量用户分配一个或多个策略。 |Microsoft Teams PowerShell 模块中的 Teams 管理中心或 PowerShell cmdlet
|[向组分配策略](#assign-a-policy-to-a-group) |根据用户的组成员身份分配策略。 例如，将策略分配给安全组或通讯组列表中的所有用户。| Microsoft Teams PowerShell 模块中的 Teams 管理中心或 PowerShell cmdlet|
|[向一批用户分配策略](#assign-a-policy-to-a-batch-of-users)   | 将策略分配给大量用户。 例如，一次向组织中数百或数千个用户分配策略。 |Microsoft Teams PowerShell 模块中的 Teams 管理中心或 PowerShell cmdlet|
| [向用户分配策略包](#assign-a-policy-package-to-users)  |将多个策略分配给组织中具有相同或类似角色的特定用户集。 例如，将教育 (教师) 策略包分配给学校的教师，让他们完全访问聊天、通话和会议。 将教育 (中学生) 策略包分配给中学生，以限制某些功能，例如私人通话。  |Microsoft Teams PowerShell 模块中的 Teams 管理中心或 PowerShell cmdlet|
| [在个人预览版中将策略包](#assign-a-policy-package-to-a-group) (组)    |将多个策略分配给组织中具有相同或类似角色的一组用户。 例如，将策略包分配给安全组或通讯组列表中的所有用户。 |Microsoft Teams PowerShell 模块 (powerShell) PowerShell cmdlet 即将推出 Teams 管理中心|
| [将策略包分配给一批用户](#assign-a-policy-package-to-a-batch-of-users)|将多个策略分配给组织中具有相同或类似角色的一批用户。 例如，使用批处理 ("教师) "策略包分配给学校的所有教师，让他们完全访问聊天、通话和会议。 将教育 (中学生) 策略包分配给一批辅助学生，以限制某些功能，例如私人通话。|PowerShell 模块Teams PowerShell cmdlet|

## <a name="set-the-global-policies"></a>设置全局策略

按照以下步骤设置每个策略 (组织范围的) 策略。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心Microsoft Teams导航中，转到要更新的策略类型的策略页。 例如 **，Teams Teams**  >  策略、**会议** 策略、  >  **消息** 策略或 **语音**  >  **呼叫策略**。
2. 选择 **"全局 (组织范围的默认)** 策略以查看当前设置。
3. 根据需要更新策略，然后选择"应用 **"。**

### <a name="using-powershell"></a>使用 PowerShell

若要使用 PowerShell 设置全局策略，请使用全局标识符。  首先查看当前全局策略，确定要更改的设置。

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

接下来，根据需要更新全局策略。  只需为要更改的设置指定值。

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>向单个用户分配策略

按照以下步骤将策略分配给单个用户或一次向少量用户分配策略。

### <a name="use-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

将策略分配给用户：

1. 在管理中心的左侧导航Microsoft Teams，转到"**用户"，** 然后选择该用户。
2. 单击用户名左侧选择用户，然后选择"编辑 **设置"。**
3. 选择要分配的策略，然后选择"应用 **"。**

或者，也可以执行以下操作：

1. 在管理中心Microsoft Teams导航中，转到策略页。
2. 单击策略名称左侧，选择要分配的策略。
3. 选择“管理用户”。
4. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
5. 添加完用户后，选择"应用 **"。**

### <a name="use-powershell"></a>使用 PowerShell

每个策略类型都有其自己的一组 cmdlet 用于管理它。 使用 ```Grant-``` 给定策略类型的 cmdlet 分配策略。 例如，使用 ```Grant-CsTeamsMeetingPolicy``` cmdlet 向用户Teams会议策略。 这些 cmdlet 包含在 powerShell Teams中，并记录在 Skype for Business [cmdlet 参考 中](/powershell/skype/intro?view=skype-ps)。

下载并Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (（如果尚未安装) ，然后运行以下代码进行连接。

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。
>
> 如果使用最新的[PowerShell Teams，](https://www.powershellgallery.com/packages/MicrosoftTeams/)则无需安装 Skype for Business Online 连接器。

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

本示例将名为"学生Teams策略"的会议策略分配给名为 Reda 的用户。

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

有关详细信息，请阅读通过 [PowerShell 管理策略](teams-powershell-managing-teams.md#manage-policies-via-powershell)。

## <a name="assign-a-policy-to-a-group"></a>向组分配策略

通过向组分配策略，可以将策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。

建议对最多 50，000 名用户的组分配组的策略分配，但也适用于较大的组。

分配策略时，会立即将其分配给组。 但是，将策略分配传播到组的成员以后台操作方式执行，可能需要一些时间，具体取决于组的大小。 从组取消分配策略时，或者将成员添加到组或从组中删除成员时，也是如此。

组策略分配仅传播给作为组的直接成员的用户。 分配不会传播到嵌套组的成员。

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>有关向组分配策略的需知信息

在开始使用之前，必须了解优先级规则和组分配排名。

#### <a name="precedence-rules"></a>优先级规则

对于给定的策略类型，根据以下条件确定用户的有效策略：

- 直接分配给用户的策略优先于分配给组的相同类型的其他任何策略。 换言之，如果直接为用户分配了给定类型的策略，该用户将不会从组继承相同类型的策略。 这也意味着，如果用户具有直接分配给他们的给定类型的策略，则你必须从用户中删除该策略，然后才能从组继承相同类型的策略。

- 如果用户没有直接为其分配策略，并且是两个或多个组的成员，并且每个组分配了相同类型的策略，则用户将继承排名最高的组分配策略。

- 如果用户不是分配有策略的任何组的成员，则适用于该策略类型的全局 (组织范围默认) 策略将应用于该用户。

根据以下规则更新用户的有效策略：

- 向分配了策略的组添加或删除用户时。
- 策略未从组分配。
- 将删除直接分配给用户的策略。

#### <a name="group-assignment-ranking"></a>组分配排名

将策略分配给组时，请为组分配指定排名。 这用于确定如果用户是两个或多个组的成员，并且为每个组分配了相同类型的策略，则该用户应继承哪个策略作为有效策略。

组分配排名相对于相同类型的其他组分配。 例如，如果要将呼叫策略分配给两个组，将一个作业的排名设置为 1，将另一个分配设置为 2，其中 1 是最高排名。 组分配排名指示哪个组成员身份比有关继承的其他组成员身份更重要或更相关。

例如，你有两个组："应用商店员工"和"应用商店经理"。 这两个组分别Teams"应用商店员工呼叫策略"和"应用商店经理呼叫策略"。 对于这两个组的应用商店经理，其经理角色比其员工角色更相关，因此分配给"应用商店经理"组的呼叫策略应具有更高的排名。

|组 |Teams调用策略名称  |等级|
|---------|---------|---|
|应用商店管理员   |应用商店管理员呼叫策略         |1|
|应用商店员工    |存储员工呼叫策略      |2|

如果未指定排名，则策略分配会获得最低排名。

### <a name="in-the-teams-admin-center"></a>在 Teams 管理中心

> [!NOTE]
> 目前，使用 Microsoft Teams 管理中心向组分配策略仅适用于 Teams 呼叫策略、Teams 呼叫公园策略、Teams 策略、Teams 实时事件策略、Teams 会议策略和 Teams 消息策略。 对于其他策略类型，请使用 PowerShell。

1. 在管理中心左侧导航Microsoft Teams，转到策略类型页面。 例如，转到"**会议**  >  **会议策略"。**

2. 选择" **组策略分配"** 选项卡。

3. 选择 **"添加组**"，然后在" **将策略分配到组"窗格中** 执行以下操作：
    1. 搜索并添加要为其分配策略的组。
    2. 设置组分配的排名。
    3. 选择要分配的策略。
    4. 选择"**应用"。**

若要删除组策略分配，请在策略页的"组 **策略** 分配"选项卡上，选择组分配，然后选择"删除 **"。**

若要更改组分配的排名，首先必须删除组策略分配。 然后，按照上述步骤将策略分配给组。

### <a name="use-the-powershell-option"></a>使用 PowerShell 选项

> [!NOTE]
> 目前，使用 PowerShell 向组分配策略不适用于所有Teams类型。 有关[支持的策略类型列表，请参阅 New-CsGroupPolicyAssignment。](/powershell/module/teams/new-csgrouppolicyassignment)

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安装并连接到 Microsoft Teams PowerShell 模块

有关分步指南，请参阅安装[Teams PowerShell。](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>向一组用户分配策略

使用 [New-CsGroupPolicyAssignment cmdlet](/powershell/module/teams/new-csgrouppolicyassignment) 将策略分配给组。 可以使用对象 ID、SIP 地址或电子邮件地址指定组。

本示例将名为"零售Teams会议策略"的会议策略分配给作业排名为 1 的组。

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>获取组的策略分配

使用 [Get-CsGroupPolicyAssignment cmdlet](/powershell/module/teams/get-csgrouppolicyassignment) 获取分配给组的所有策略。 请注意，组始终按组 ID 列出，即使其 SIP 地址或电子邮件地址用于分配策略。

本示例检索分配给特定组的所有策略。

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

本示例返回所有分配有会议Teams组。

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>从组中删除策略

使用 [Remove-CsGroupPolicyAssignment cmdlet](/powershell/module/teams/remove-csgrouppolicyassignment) 从组中删除策略。 从组中删除策略时，会更新分配给该组且排名较低的相同类型其他策略的优先级。 例如，如果删除排名为 2 的策略，则排名为 3 和 4 的策略会更新以反映其新排名。 以下两个表显示了此示例。

下面是会议策略的策略分配和Teams列表。

|组名称  |策略名称  |等级|
|---------|---------|---------|
|销售    |销售策略       | 1        |
|西部区域     |西部区域策略         |2         |
|除法    |部门策略         |3         |
|子公司   |子公司策略        |4         |

如果从"西部区域"组中删除"西部区域"策略，策略分配和优先级将更新如下。

|组名称  |策略名称  |等级|
|---------|---------|---------|
|销售    |销售策略       | 1        |
|除法    |部门策略         |2         |
|子公司   |子公司策略        |3        |

本示例从组中删除Teams会议策略。

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>更改组的策略分配

> [!NOTE]
> [即将推出 Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet。 在此期间，若要更改组策略分配，可以从组中删除当前策略分配，然后添加新的策略分配。

将策略分配到组后，可以使用 [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet 更改该组的策略分配，如下所示：

- 更改排名
- 更改给定策略类型的策略
- 更改给定策略类型和排名的策略

本示例将组的调用Teams策略更改为名为 SupportCallPark 的策略，将分配排名更改为 3。

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>更改用户的有效策略

以下示例演示了如何更改直接分配了策略的用户的有效策略。

首先，我们将[Get-CsUserPolicyAssignment cmdlet](/powershell/module/teams/get-csuserpolicyassignment)与 参数一起用于获取与用户关联的 `PolicySource` Teams 会议直播策略的详细信息。

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

输出显示，用户已直接分配到名为"员工事件"的 Teams 会议直播策略，该策略优先于分配给用户所属组的名为"供应商实时事件"的策略。

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

现在，我们从用户中删除"员工事件"策略。 这意味着用户不再具有直接分配给Teams直播策略，并将继承分配给用户所属组的供应商实时事件策略。

在 PowerShell 模块的 Skype for Business cmdlet 可完成此操作。

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

在 PowerShell 模块Teams以下 cmdlet，通过批处理策略分配（其中 $users是指定的用户列表）大规模地完成此操作。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>向一批用户分配策略

### <a name="use-the-admin-center"></a>使用管理中心

将策略批量分配给用户：

1. 在管理中心左侧导航Microsoft Teams，选择"用户 **"。**

2. 搜索要为其分配策略的用户，或筛选视图以显示想要的用户。

3. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。

4. 选择 **"编辑** 设置"，进行您需要的更改，然后选择"应用 **"。**

若要查看策略分配的状态，请在选择"应用"以提交策略分配后，在"用户"页面顶部出现的横幅中，选择"活动 **日志"。** 或者，在管理中心的左侧导航Microsoft Teams，转到"仪表板 **"，然后在**"活动日志"下，选择"查看 **详细信息"。** "活动日志"显示过去 30 天内通过 Microsoft Teams管理中心向超过 20 名用户的批次分配策略。 有关详细信息，请参阅 [在活动日志中查看策略分配](activity-log.md)。

### <a name="use-powershell-method"></a>使用 PowerShell 方法

> [!NOTE]
> 目前，使用 PowerShell 的批处理策略分配不可用于所有 Teams策略类型。 有关[支持的策略类型列表，请参阅 New-CsBatchPolicyAssignmentOperation。](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

使用批处理策略分配，可以一次向大量用户分配策略，而无需使用脚本。 使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略。 作业将作为后台操作处理，并为每个批处理生成操作 ID。 然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。

根据用户的对象 ID 或会话启动协议 (SIP) 地址。 用户的 SIP 地址通常与 UPN 或电子邮件地址 (用户主体名称) 相同，但这不是必需的。 如果用户是使用其 UPN 或电子邮件指定的，但其值不同于其 SIP 地址，则策略分配将失败。 如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且只会为批中剩余的唯一用户提供状态。

批处理最多可包含 5,000 个用户。 为获得最佳结果，不要一次提交多个批次。 允许批处理在提交更多批之前完成处理。

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>安装并连接到 Teams PowerShell 模块

运行以下代码以安装[Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。 请确保安装版本 1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下代码连接到Teams并启动会话。

```powershell
Connect-MicrosoftTeams
```

系统提示时，使用管理员凭据登录。

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>安装并连接到 Azure AD PowerShell for Graph 模块 (可选) 

如果尚未安装 Azure [AD PowerShell for Graph](/powershell/azure/active-directory/install-adv2)模块 (，可能还需要下载并) 并连接到 Azure AD，以便检索组织中用户的列表。

运行以下代码以连接到 Azure AD。

```powershell
Connect-AzureAD
```

系统提示时，使用用于连接到 Teams 的管理员凭据登录。

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>向一批用户分配设置策略

本示例使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将名为 HR 应用设置策略的应用设置策略分配给 Users_ids.txt 文件中列出的一批用户。

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

本示例连接到 Azure AD 以检索用户的集合，然后将名为"新员工消息策略"的消息传送策略分配给使用其 SIP 地址指定的一批用户。

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>获取批处理分配的状态

运行以下代码获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批返回的操作 `New-CsBatchPolicyAssignmentOperation` ID。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果输出显示发生错误，请运行以下命令，获取有关 属性中的错误 `UserState` 的详细信息。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

有关详细信息，请参阅[Get-CsBatchPolicyAssignmentOperation。](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>向用户分配策略包

Teams策略包是预定义的策略和策略设置的集合，可以分配给组织中具有相同或类似角色的用户。 每个策略包围绕用户角色设计，包括预定义的策略和策略设置，这些策略设置支持该角色的典型活动。 策略包的一些示例包括教育 (教师) 包和医疗保健 (医疗) 包。 有关详细信息，请参阅在 中[管理策略Teams。](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>将策略包分配给一个用户

1. 在管理中心的左侧导航Microsoft Teams，转到"**用户"，** 然后选择用户。

2. 在用户的页面上，选择"策略 **"，** 然后在"策略包"**旁边** 选择"编辑 **"。**

3. 在"**分配策略包"** 窗格中，选择要分配的包，然后选择"保存 **"。**

### <a name="assign-a-policy-package-to-multiple-users"></a>将策略包分配给多个用户

1. 在管理中心Microsoft Teams导航中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。

2. 选择“管理用户”。

3. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。

4. 添加完用户后，选择"保存 **"。**

## <a name="assign-a-policy-package-to-a-group"></a>将策略包分配给组。

通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。

建议最多包含 50，000 个用户组将策略包分配到组，但它也将适用于较大的组。

分配策略包时，会立即将其分配给组。 但是，将策略分配传播到组的成员以后台操作方式执行，可能需要一些时间，具体取决于组的大小。 从组取消分配策略时，或者将成员添加到组或从组中删除成员时，也是如此。

> [!IMPORTANT]
> 在开始使用之前，必须了解优先级[规则和](#precedence-rules)[组分配排名](#group-assignment-ranking)。 请务必阅读并理解本文前面有关组的策略分配需了解 [的信息中的概](#what-you-need-to-know-about-policy-assignment-to-groups) 念。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>将策略包分配给管理中心中的一组用户

1. 登录到 Teams 管理中心。

2. 在左侧导航栏中，转到策略包页。

3. 选择"组策略分配"选项卡。

4. 选择 **"添加组**"，然后在"将策略包分配到组"窗格中执行以下操作：

    1. 搜索并添加要为其分配策略包的组。
    
    1. 选择策略包。
    
    1. 设置每个策略类型的排名。
    
    1. 选择"**应用"。**
    
    ![显示组策略分配。](media/group-pkg-assignment.png)

5. 若要管理特定策略类型的排名，请导航到特定策略页。

6. 若要将策略包重新分配到组，请首先删除组策略分配。 然后，按照上述步骤将策略包分配到组。

### <a name="work-with-powershell"></a>使用 PowerShell

#### <a name="get-the-teams-powershell-module"></a>获取 Teams PowerShell 模块

有关分步指南，请参阅安装[Teams PowerShell。](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>将策略包分配给一组用户

使用 [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet 将策略包分配给组。 可以使用对象 ID、SIP 地址或电子邮件地址指定组。 分配策略包时，为策略 [包中的](#group-assignment-ranking) 每种策略类型指定组分配排名。

本示例将 Education_Teacher 策略包分配给一个组，TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的分配排名为 1，TeamsMeetingPolicy 的排名为 2。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>将策略包分配给一批用户

使用批处理策略包分配，可以一次向大量用户分配策略包，而无需使用脚本。 使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略包。 作业将作为后台操作处理，并为每个批处理生成操作 ID。 然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。

根据用户的对象 ID 或会话启动协议 (SIP) 地址。 用户的 SIP 地址通常具有与 UPN (或电子邮件地址) "用户主体名称"相同的值，但这不是必需的。 如果用户是使用其 UPN 或电子邮件指定的，但其值不同于其 SIP 地址，则策略分配将失败。 如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且只会为批中剩余的唯一用户提供状态。

一个批最多包含 5，000 个用户。 为获得最佳结果，不要一次提交多个批次。 允许批处理在提交更多批之前完成处理。

### <a name="use-the-teams-powershell-module"></a>使用 Teams PowerShell 模块

如果尚未安装[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) Microsoft Teams， (运行以下代码) 。 请确保安装版本 1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下代码连接到Teams并启动会话。

```powershell
Connect-MicrosoftTeams
```

系统提示时，使用管理员凭据登录。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>将策略包分配给一批用户

本示例使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将 Education_PrimaryStudent 策略包分配给一批用户。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>查看批处理分配的状态

运行以下代码获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批返回的操作 `New-CsBatchPolicyAssignmentOperation` ID。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果输出显示发生错误，请运行以下命令，获取有关 属性中的错误 `UserState` 的详细信息。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

有关详细信息，请参阅[Get-CsBatchPolicyAssignmentOperation。](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>相关主题

[Teams PowerShell 概览](teams-powershell-overview.md)
