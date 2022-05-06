---
title: 在管理中心管理团队模板
author: serdars
ms.author: serdars
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在管理中心管理团队模板
ms.openlocfilehash: c753a92205844ebade9a713a8442837039232339
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248934"
---
# <a name="manage-team-templates-in-the-admin-center"></a>在管理中心管理团队模板

通过在管理中心创建模板策略来管理最终用户看到的团队模板。 在每个模板策略中，可以指定显示或隐藏哪些模板。
将不同的用户分配到不同的模板策略，以便用户仅查看指定的团队模板的子集。

观看此简短视频，了解如何管理模板策略。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>创建模板策略并分配可用模板

1. 登录到 Teams 管理中心。

2. 转到 **Teams** >  **Templates 策略**。

3. 选择" **添加**"。

    ![已选择模板策略，并突出显示“添加”。](media/template-policies-1.png)

1. 为策略命名并添加简短说明。

2. 在 **“可查看模板** ”列表中，选择要隐藏的模板，然后选择 **“隐藏**”。

    ![所选模板，其中突出显示了隐藏。](media/template-policies-2.png)

    可以在 **“隐藏模板** ”列表中看到选择隐藏的模板。

1. 若要取消隐藏某些模板，请转到 **“隐藏模板** ”列表。

2. 选择要取消隐藏的模板，然后选择 **“显示**”。

   ![未隐藏的所选模板。](media/template-policies-3.png)

   所选模板将显示在 **可查看模板** 列表中。
3. 选择" **保存**"。

   新模板策略显示在 **模板策略** 列表中。

## <a name="assign-templates-policies-to-users"></a>向用户分配模板策略

可以通过批处理分配直接向用户单独或大规模分配模板策略。 请记住，新策略可能需要长达 24 小时才能对用户生效。

> [!Note]
> 目前不支持根据组成员身份（例如安全组中的所有用户）向用户分配模板策略。 此功能将来将可用。

有关如何在Teams中分配策略的概述，请参阅[Teams中的分配策略](policy-assignment-overview.md)。

### <a name="assign-a-templates-policy-to-individual-users"></a>向单个用户分配模板策略

可以使用Teams管理中心或 PowerShell 一次向单个用户或少量用户分配模板策略。 若要了解详细信息，请参阅 [为单个用户分配策略](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)。

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>向一批用户分配模板策略

可以使用 PowerShell 一次向大型用户集分配模板策略。 为此，请将 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 与 TeamsTemplatePermissionPolicy 一起用作 ```PolicyType``` 提交一批用户和要分配的模板策略。 例如：

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

作业将作为后台操作处理，并为每个批处理生成操作 ID。 然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。

若要了解详细信息，请参阅 [使用 PowerShell 向一批用户分配](assign-policies-users-and-groups.md#use-powershell-method)策略。

## <a name="size-limits-for-templates-policies"></a>模板策略的大小限制

每个策略最多可以隐藏 100 个模板。 如果给定的策略已隐藏 100 个模板，则禁用 **“隐藏** ”按钮。

## <a name="frequently-asked-questions"></a>常见问题解答

**问：如果创建了新模板，模板是否会包含在我的策略中？**

答：默认情况下，任何新模板都将可见。 可以选择在“模板策略”部分的管理中心隐藏模板。

**问：删除模板后会发生什么情况？**

答：任何已删除的模板将不再存在于任何模板策略中。

**问：是否可以在Teams管理中心将多个用户分配到模板策略？**

答：是的。

1. 在Teams管理中心，转到 **UsersManage** >  用户。
1. 在用户列表中，选择要分配给模板策略的用户。
1. 选择 **“编辑设置**”，然后在 **“模板”策略** 下，选择要分配的策略。
1. 选择 **“应用**”。

若要了解详细信息，请参阅 [为单个用户分配策略](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)。

**问：如何实现查看分配给特定策略的所有用户？**

答：在Teams管理中心：

1. 转到 **UsersManage** >  用户。
2. 选择 **“筛选器**”，为模板策略设置筛选器，然后选择 **“应用**”。

    ![所选模板策略并查看用户。](media/template-policies-5.png)

**问：是否可以通过 PowerShell 管理模板策略？**

答：不支持在 PowerShell 中管理模板策略。 但是，可以使用 PowerShell 向用户 [分配模板策略](#assign-templates-policies-to-users) 。

**问：模板策略适用于 EDU 吗？**

答：不支持 EDU 的模板策略。

## <a name="related-articles"></a>相关文章

- [在管理中心使用团队模板开始](./get-started-with-teams-templates-in-the-admin-console.md)

- [创建自定义团队模板](./create-a-team-template.md)

- [从现有团队创建模板](./create-template-from-existing-team.md)

- [从现有团队模板创建团队模板](./create-template-from-existing-template.md)

- [在Microsoft Teams中为用户分配策略 - Microsoft Teams \| Microsoft Docs](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
