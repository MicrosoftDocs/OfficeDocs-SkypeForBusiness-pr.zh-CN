---
title: 管理用户对 Education Insights 的访问权限
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 管理用户对 Microsoft Teams 中 Education Insights 的访问权限。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b69f885eee0b96b87b5f22d04abbd16d0389b904
ms.sourcegitcommit: e5e6c6c99296db8005451bcb08d727469f0ac984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2021
ms.locfileid: "58864192"
---
# <a name="manage-user-access-to-education-insights"></a>管理用户对 Education Insights 的访问权限

本文档提供了管理用户对 [Microsoft Teams 中 Education Insights](class-insights.md) 的访问权限所需的步骤。

你需要为教育领导者、地区领导、学校校长、班主任、辅导员、学区主管、项目主管、社会工作者和心理学家提供权限。 如果教师拥有课堂团队，则会 *自动* 获得权限。

若要提供组织级别的见解，你必须[从学生信息系统 (SIS) 导入数据](education-insights-sis-data-sync.md)，以便 Insights 能够正确映射教育系统的层次结构。

> [!NOTE]
> 只有全局管理员才能管理用户对 Insights 的访问权限。

> [!TIP]
> 我们建议为所有教育领导者启用 Insights，以便他们能够获得了解每所学校所需的数据，并能够快速发现问题并为教师提供支持。 即使只是运行试点项目，为所有教育领导者启用 Insights 可能仍然很有帮助，但这只针对试点用户组的通信。

## <a name="manange-permissions"></a>管理权限

* 打开 Insights 应用，单击“**设置**”，然后选择“**用户权限**”

:::image type="content" source="media/insights-user-permissions.png" alt-text="设置":::

> [!NOTE]
> 为组织级别提供权限时，用户可以看到其下所有组织单位。
> 
> 仅向有需要的教育领导者和他们负责的组织单位提供权限。 如果你不确定是否需要特定组织的用户权限，请咨询机构的隐私主题专家，例如法律或人事部门人员。

## <a name="role-based-permissions"></a>基于角色的权限

如果使用 [SDS V2.1 文件格式](/schooldatasync/sds-v2.1-csv-file-format)或 [SDS V2 文件格式](/schooldatasync/sds-v2-csv-file-format)，则可以在教育系统中导入所有角色和学校的完整层次结构。 通过此完整映射，可以向角色分配权限。 

> [!NOTE]
> 为用户分配角色时，他们将自动获得正确的权限，用以查看与他们相关的数据。
>
> 如果用户不再处于某个角色中，则会自动撤销他们该角色享有的权限（尽管他们可能仍然具有单个权限）。


* 如果需要，请单击 **基于角色的权限** 选项卡。

  你将看到教育组织中的角色列表、每个角色的层次结构中的级别、获得某角色的用户数以及角色的权限级别。 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="基于角色的权限。":::
  
  如果某个角色位于多个组织级别，则该角色会出现多次，每个级别显示一次。 在屏幕截图中，在学校、学区和部门级别都有主体，因此“主题”有三行。
  
* 对于每个角色，请单击铅笔图标以选择权限级别。 默认情况下，角色无权查看见解。
* 选择权限级别–**查看其组织的数据** 或 **无**。

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="基于角色的权限面板。":::
  
  如果在列表中看到需要更细微权限级别的用户，请在 [从 SIS 导入的数据](education-insights-sis-data-sync.md) 中调整其角色和/或组织，并 [向他们授予个人权限](#grant-individual-permission-to-a-user)（如果需要）。

* 单击 **保存更改**。

  此权限级别现在会自动分配给具有此角色和组织级别的任何新用户。 用户将能看到在其层次结构级别中及以下的所有组织单位的数据。  


## <a name="individual-permissions"></a>单个权限

如果尚未使用 SDS V2 为组织导入 SIS 数据，请使用单个权限调整用户的权限或为每个用户分配权限。

* 单击 **单个权限** 选项卡。
  
  你将会看到教育组织中被授予了单个权限的用户。 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="单个权限。":::
  
### <a name="grant-individual-permission-to-a-user"></a>向用户授予个人权限
* 单击屏幕左上角的 **授予单个权限**。
* 输入每个用户的用户名或电子邮件地址。
* 选择权限级别：
  * **所有** 意味着用户会看到所有级别的所有组织单位。 这很少使用。
  * **特定组织** 意味着用户会看到所选组织单位及其下的所有组织单位。 开始键入并从列表中选择组织单位。
* 单击 **授予权限** 来保存。

### <a name="change-the-individual-permission-of-a-user"></a>更改用户的单个权限
* 对于相关用户，请单击铅笔图标以选择单个权限级别。
* 选择权限级别：
  * **所有** 意味着用户会看到所有级别的所有组织单位。 这很少使用。
  * **特定组织** 意味着用户会看到所选组织单位及其下的所有组织单位。 开始键入并从列表中选择组织单位。
  * **无** 表示用户只能看到由其角色自动分配的组织单位（如果有）。
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="个人权限面板。":::

* 单击 **保存更改** 来保存。
