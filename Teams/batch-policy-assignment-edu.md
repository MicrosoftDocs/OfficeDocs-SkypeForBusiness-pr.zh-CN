---
title: 向学校的大型用户组分配策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: 了解如何使用 "批处理策略分配" 为远程学校（teleschool、长途）批量为您的教育机构中的大型用户分配策略。
f1keywords: ''
ms.openlocfilehash: 8dd771b27c1950cdce1590783bcfb3b4159c1c29
ms.sourcegitcommit: 891ba3670ccd16bf72adee5a5f82978dc144b9c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "42691182"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>向学校的大型用户组分配策略

您是否需要为学生和教育部门提供对 Microsoft 团队中的不同功能的访问权限？ 你可以按许可证类型快速标识组织中的用户，然后为其分配相应的策略。 本教程介绍如何使用批量[策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)来批量向用户分配会议策略。

请记住，在团队中，用户将自动获取团队策略类型的全局（组织范围默认）策略，除非你创建并分配自定义策略。 由于学生填充通常是最大的一组用户，并且通常会收到限制性最严格的设置，因此我们建议你执行以下操作：

- 编辑和应用全局（组织范围默认）策略以限制学生的功能。 
- 创建允许核心功能（如私人聊天和会议计划）的自定义策略，并向您的员工和教育部门分配策略。

请记住，全局策略将应用于你的学校中的所有用户，直到你创建自定义策略并将其分配给你的员工和教育版。

在本教程中，学生将获得全局会议策略，并使用 PowerShell 将名为 EducatorMeetingPolicy 的自定义会议策略分配给教职员工和教育批量。 我们假定你已编辑全局策略，以便为学生自定义会议设置，并创建定义教职员工和教育版会议体验的自定义策略。

![团队管理中心中的 "会议策略" 页面的屏幕截图](media/edu-batch-policy-assignment.png)

请按照以下步骤批量向员工和教育部门分配自定义会议策略。

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>连接到适用于 Graph 模块和团队 PowerShell 模块的 Azure AD PowerShell

在执行本文中的步骤之前，你需要安装并连接到 Azure AD PowerShell for Graph 模块（以通过其分配的许可证标识用户）和 Microsoft 团队 PowerShell 模块（将策略分配给这些用户）。

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>安装并连接到 Azure AD PowerShell for Graph 模块

打开提升了权限的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell），然后运行以下命令来安装适用于 Graph 模块的 Azure Active Directory PowerShell。

```powershell
Install-Module -Name AzureAD
```

运行以下操作以连接到 Azure AD。

```powershell
Connect-AzureAD
```

出现提示时，请使用管理员凭据登录。

若要了解详细信息，请参阅[连接到 Azure Active Directory PowerShell For Graph 模块](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安装并连接到 Microsoft 团队 PowerShell 模块

运行以下操作以安装[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。 请确保安装1.0.5 或更高版本。

```powershell
Install-Module -Name MicrosoftTeams
```

运行以下操作以连接到团队并启动会话。

```powershell
Connect-MicrosoftTeams
```
出现提示时，请使用您用于连接到 Azure AD 的相同管理员凭据登录。

## <a name="identify-your-users"></a>标识您的用户

首先，运行以下操作以通过许可证类型标识你的员工和教师。 这将告诉你组织中使用的 Sku。 然后，您可以识别已分配教职员 SKU 的职员和教师。

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

返回：

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

在此示例中，输出显示教职员许可证 SkuId 为 "e97c048c-37a4-45fb-ab50-922fbf07a370"。

> [!NOTE]
> 若要查看教育 Sku 和 SKU Id 的列表，请参阅[教育 sku 参考](sku-reference-edu.md)。

接下来，我们运行以下内容来确定拥有此许可证的用户，并将它们一起收集。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370")
```

## <a name="assign-a-policy-in-bulk"></a>批量分配策略

现在，我们会批量向用户分配适当的策略。 你可以为其分配或更新策略的最大用户数为每次20000。 例如，如果您有超过20000的员工和教育版，则需要提交多个批次。

> [!IMPORTANT]
> 我们当前建议你一次为每批5000用户分配策略。 在增加需求的这些时间内，你可能会遇到处理时间方面的延迟。 为了将这些增加的处理时间的影响降到最低，我们建议你向5000用户提交较小的批处理大小，并且仅在上一个批处理完成后再提交。 在正常工作时间内提交批还会有所帮助。

运行以下操作，将名为 EducatorMeetingPolicy 的会议策略分配给你的员工和教育版。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> 若要批量分配不同的策略类型（如 TeamsMessagingPolicy），你需要更改```PolicyType```为你分配的策略和```PolicyName```策略名称。

## <a name="get-the-status-of-a-bulk-assignment"></a>获取批量作业的状态

每个批量分配都将返回一个操作 ID，您可以使用该 ID 跟踪策略分配的进度，或标识可能出现的任何失败。 例如，运行以下内容：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

若要查看批处理操作中每个用户的作业状态，请运行以下。 每个用户的详细信息都```UserState```在该属性中。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>如果用户超过20000个用户，则批量分配策略

首先，运行以下内容查看您拥有的职员和教育人数：

```powershell
$faculty.count
```

请运行以下操作以指定第一个20000，然后再指定下一个20000，依此类推，而不是提供整个用户 Id 列表。

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

你可以更改用户 Id 的范围，直到到达用户的完整列表。 例如，输入```$faculty[0..19999```第一个批处理，为第二```$faculty[20000..39999```个批次使用，为```$faculty[40000..59999```第三个批处理输入，依此类推。

## <a name="get-the-policies-assigned-to-a-user"></a>获取分配给用户的策略

运行以下操作，查看分配给特定用户的所有策略。 下面的示例演示如何获取分配给 hannah@contoso.com 的策略。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>常见问题解答

**我想要确保学生、教职员工和教育版的所有用户都自动获得分配的许可证。如何执行此操作？**

团队产品团队正在执行工作以支持向安全组分配策略。 此时，你将能够为学生和教师创建组，然后为这些组创建相应的策略。 请注意，显式用户分配（如使用本教程分配的策略）将覆盖从组继承的策略。 如果支持此功能，我们将提供更多有关如何使用策略分配到组和更新用户的说明，以确保他们获得继承的组策略。

**我不熟悉 PowerShell for 团队。在哪里可以了解更多信息？**

请参阅[团队 Powershell 概述](teams-powershell-overview.md)。

## <a name="related-topics"></a>相关主题

- [为用户分配策略](assign-policies.md)
- [新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)