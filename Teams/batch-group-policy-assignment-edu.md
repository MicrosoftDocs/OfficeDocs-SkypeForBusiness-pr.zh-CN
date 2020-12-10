---
title: 向学校的大型用户组分配策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何根据组成员身份或直接通过适用于远程学校 (teleschool、长途) 用途的批作业向你的教育机构中的大型用户分配策略。
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616936"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>向学校的大型用户组分配策略

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> 有关在 Microsoft 团队中分配策略的较大情景，请参阅为 [团队中的用户分配策略](assign-policies.md)。

## <a name="overview"></a>概述

您是否需要为学生和教育部门提供对 Microsoft 团队中的不同功能的访问权限？ 你可以按许可证类型快速标识组织中的用户，然后为其分配相应的策略。 本教程介绍如何为你的学校中的大型用户分配会议策略。 你可以使用 Microsoft 团队管理中心和 PowerShell 分配策略，我们将向你显示两种方法。

你可以将会议策略分配给用户是其成员的安全组，也可以通过批量策略分配将其直接分配给用户。 你将了解以下内容：

- **使用 [组策略分配](#assign-a-policy-to-a-group) 将会议策略分配到安全组 (推荐的)**。 此方法允许你根据组成员身份分配策略。 可以向安全组或通讯组列表分配策略。 将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。 我们建议你使用此方法，因为它减少了管理新用户的策略的时间或用户的角色更改时间。 此方法最适用于最多为50000用户的组，但也可用于更大的组。

- **使用批量 [策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users) 将会议策略直接分配给用户**。 你可以一次为多达5000用户分配一个策略。 如果您有超过5000的用户，则可以提交多个批次。 使用此方法时，当你拥有新用户时，你需要重新运行批处理分配以将策略分配给这些新用户。

请记住，在团队中，用户将自动获取团队策略类型的全局 (组织范围默认) 策略，除非你创建并分配自定义策略。 由于学生填充通常是最大的一组用户，并且通常会收到限制性最严格的设置，因此我们建议你执行以下操作：

- 创建允许核心功能（如私人聊天和会议计划）的自定义策略，并向您的员工和教育部门分配策略。
- 将自定义策略分配给教职员工和教育版。
- 编辑和应用全球 (组织范围默认) 策略以限制学生的功能。

请记住，全局策略将应用于你的学校中的所有用户，直到你创建自定义策略并将其分配给你的员工和教育版。

在本教程中，学生将获得全局会议策略，我们会将名为 EducatorMeetingPolicy 的自定义会议策略分配给教职员工和教育版。 我们假定你已编辑全局策略，以便为学生自定义会议设置，并创建定义教职员工和教育版会议体验的 [自定义策略](policy-packages-edu.md) 。

![团队管理中心中的 "会议策略" 页面的屏幕截图](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>为组分配策略

按照以下步骤为你的教职员工和教育版创建一个安全组，然后将名为 EducatorMeetingPolicy 的自定义会议策略分配给该安全组。

### <a name="before-you-get-started"></a>开始之前

> [!IMPORTANT]
> 向组分配策略时，将根据优先级规则将策略分配传播到该组的成员。 例如，如果直接向用户分配策略 (单独或通过批作业) ，则该策略优先于继承自组的策略。 这还意味着如果用户具有直接分配给他们的会议策略，则必须先删除该用户的会议策略，然后他们才能从安全组继承会议策略。

在开始之前，了解 [优先级规则](assign-policies.md#precedence-rules) 和 [组分配的排名](assign-policies.md#group-assignment-ranking)非常重要。 **请确保阅读并理解 [有关对组的策略分配所需了解](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)的概念**。

您需要完成所有这些步骤，让您的员工和教师从安全组继承会议策略。

1. [创建安全组](#create-security-groups)。
2. 向[安全组分配策略](#assign-a-policy-to-a-security-group)。
3. [删除直接分配给用户的策略](#remove-a-policy-that-was-directly-assigned-to-users)。

### <a name="create-security-groups"></a>创建安全组

首先，为您的教职员工和教育版创建一个安全组。

通过 [学校数据同步](https://docs.microsoft.com/SchoolDataSync/) (SDS) ，您可以轻松地在您的学校中 [创建教师和学生的安全组](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) 。 我们建议你使用 SDS 创建管理你的学校策略所需的安全组。

如果你无法在你的环境中部署 SDS，请使用 [此 PowerShell 脚本](scripts/powershell-script-security-groups-edu.md) 创建两个安全组，一个用于分配有教职员许可证的所有职员和教师，另一个用于分配有学生许可证的学生。 您需要定期运行此脚本以使组保持最新和最新状态。

### <a name="assign-a-policy-to-a-security-group"></a>向安全组分配策略

#### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

> [!NOTE]
> 目前，对使用 Microsoft 团队管理中心的组的策略分配仅适用于团队调用策略、团队呼叫驻留策略、团队策略、团队实时事件策略、团队会议策略和团队消息策略。 对于其他策略类型，请使用 PowerShell。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。
2. 选择 " **组策略分配** " 选项卡。
3. 选择 " **添加组**"，然后在 "向 **组分配策略** " 窗格中，执行下列操作：

    ![显示会议策略的 "编辑设置" 窗格的屏幕截图](media/batch-group-policy-assignment-edu-group.png)
    1. 在 " **选择组** " 框中，搜索并添加包含您的教职员工和教育版的安全组。
    2. 在 " **选择排名** " 框中，输入 **1**。
    3. 在 " **选择策略** " 框中，选择 " **EducatorMeetingPolicy**"。
    4. 选择 " **应用**"。

若要删除组策略分配，请在 "策略" 页面的 " **组策略分配** " 选项卡上，选择 "组分配"，然后选择 " **删除**"。

若要更改组分配的排名，必须首先删除组策略分配。 然后，按照上述步骤将策略分配给组。

#### <a name="using-powershell"></a>使用 PowerShell

> [!NOTE]
> 目前，对使用 PowerShell 的组的策略分配不可用于所有团队策略类型。 有关受支持的策略类型列表，请参阅 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安装并连接到 Microsoft 团队 PowerShell 模块

若要安装 [团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams) ，请执行以下操作以安装 (（如果尚未安装) ）。 请确保安装1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下操作以连接到团队并启动会话。

```powershell
Connect-MicrosoftTeams
```

出现提示时，请使用管理员凭据登录。

##### <a name="assign-a-policy-to-a-group"></a>为组分配策略

运行以下操作，将名为 EducatorMeetingPolicy 的会议策略分配给包含你的教职员工和教育版的安全组，并将工作分配排名设置为1。 你可以使用对象 Id、会话初始协议 (SIP) 地址或电子邮件地址来指定安全组。 在此示例中，我们使用 (staff-faculty@contoso.com) 的电子邮件地址。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>删除直接分配给用户的策略

请记住，如果用户直接分配策略 (或通过批作业) 分配策略，则该策略优先。 这意味着，如果用户具有直接分配给他们的会议策略，则必须先删除该用户的会议策略，然后他们才能从安全组继承会议策略。

若要了解详细信息，请参阅 [对组的策略分配需要了解的信息](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。

按照以下步骤删除直接分配给你的员工和教育版的会议策略。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安装并连接到 Microsoft 团队 PowerShell 模块

若要安装 [团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams) ，请执行以下操作以安装 (（如果尚未安装) ）。 请确保安装1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下操作以连接到团队并启动会话。

```powershell
Connect-MicrosoftTeams
```

出现提示时，请使用您用于连接到 Azure AD 的相同管理员凭据登录。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>取消分配直接分配给用户的策略

运行以下操作以删除直接分配该策略的用户的会议策略。 你可以通过电子邮件地址或对象 ID 指定用户。

在此示例中，将从由其电子邮件地址指定的用户中删除会议策略。

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

在此示例中，将从名为 user_ids.txt 的文本文件的用户列表中删除会议策略。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>获取组的策略分配

运行以下操作，查看分配给特定安全组的所有策略。 请注意，组始终按组 ID 列出，即使其 SIP 地址或电子邮件地址用于分配策略。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>获取分配给用户的策略

运行以下操作，查看分配给特定用户的所有策略。 下面的示例演示如何获取分配给 reda@contoso.com 的策略。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>为一批用户分配策略

请按照以下步骤将名为 EducatorMeetingPolicy 的自定义会议策略直接分配给你的员工并批量教育。

### <a name="using-powershell"></a>使用 PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>连接到适用于 Graph 模块和团队 PowerShell 模块的 Azure AD PowerShell

在执行本文中的步骤之前，你需要安装并连接到 Azure AD PowerShell for Graph 模块 (以通过其分配的许可证) 和 Microsoft 团队 PowerShell 模块 (将策略分配给这些用户) 。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>安装并连接到 Azure AD PowerShell for Graph 模块

打开提升了权限的 Windows PowerShell 命令提示符 (以管理员身份) 运行 Windows PowerShell，然后运行以下命令来安装适用于 Graph 模块的 Azure Active Directory PowerShell。

```powershell
Install-Module -Name AzureAD
```

运行以下操作以连接到 Azure AD。

```powershell
Connect-AzureAD
```

出现提示时，请使用管理员凭据登录。

若要了解详细信息，请参阅 [连接到 Azure Active Directory PowerShell For Graph 模块](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安装并连接到 Microsoft 团队 PowerShell 模块

若要安装 [团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams) ，请执行以下操作以安装 (（如果尚未安装) ）。 请确保安装1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下操作以连接到团队并启动会话。

```powershell
Connect-MicrosoftTeams
```

出现提示时，请使用您用于连接到 Azure AD 的相同管理员凭据登录。

#### <a name="identify-your-users"></a>标识您的用户

首先，运行以下操作以通过许可证类型标识你的员工和教师。 这将告诉你组织中使用的 Sku。 然后，您可以识别已分配教职员 SKU 的职员和教师。

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

返回：

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

在此示例中，输出显示教职员许可证 SkuId 为 "e97c048c-37a4-45fb-ab50-922fbf07a370"。

> [!NOTE]
> 若要查看教育 Sku 和 SKU Id 的列表，请参阅 [教育 sku 参考](sku-reference-edu.md)。

接下来，我们运行以下内容来确定拥有此许可证的用户，并将它们一起收集。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>批量分配策略

现在，我们会批量向用户分配适当的策略。 你可以为其分配或更新策略的最大用户数为每次5000。 例如，如果您有超过5000的员工和教育版，则需要提交多个批次。

运行以下操作，将名为 EducatorMeetingPolicy 的自定义会议策略分配给你的员工和教育版。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> 若要批量分配不同的策略类型（如 TeamsMessagingPolicy），你需要更改 ```PolicyType``` 为你分配的策略和 ```PolicyName``` 策略名称。

#### <a name="get-the-status-of-a-bulk-assignment"></a>获取批量作业的状态

每个批量分配都将返回一个操作 ID，您可以使用该 ID 跟踪策略分配的进度，或标识可能出现的任何失败。 例如，运行以下内容：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

若要查看批处理操作中每个用户的作业状态，请运行以下。 每个用户的详细信息都在该 ```UserState``` 属性中。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>如果用户超过5000个用户，则批量分配策略

首先，运行以下内容查看您拥有的职员和教育人数：

```powershell
$faculty.count
```

请运行以下操作以指定第一个5000，然后再指定下一个5000，依此类推，而不是提供整个用户 Id 列表。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

你可以更改用户 Id 的范围，直到到达用户的完整列表。 例如，输入 ```$faculty[0..4999``` 第一个批处理，为第二个批次使用， ```$faculty[5000..9999``` ```$faculty[10000..14999``` 为第三个批处理输入，依此类推。

#### <a name="get-the-policies-assigned-to-a-user"></a>获取分配给用户的策略

运行以下操作，查看分配给特定用户的所有策略。 下面的示例演示如何获取分配给 hannah@contoso.com 的策略。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>常见问题

**我不熟悉 PowerShell for 团队。在哪里可以了解更多信息？**

有关使用 PowerShell 管理团队的概述，请参阅 [团队 PowerShell 概述](teams-powershell-overview.md)。 有关本文中使用的 cmdlet 的详细信息，请参阅：

- [新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>相关主题

- [为用户分配策略](assign-policies.md)
- [用于教育的团队政策和政策包](policy-packages-edu.md)
- [管理团队中的会议策略](meeting-policies-in-teams.md)
