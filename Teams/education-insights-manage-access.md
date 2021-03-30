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
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145930"
---
# <a name="manage-user-access-to-education-insights"></a>管理用户对 Education Insights 的访问权限

本文档提供了管理用户对 [Microsoft Teams 中 Education Insights](class-insights.md) 的访问权限所需的步骤。

你需要为教育领导者、地区领导、学校校长、班主任、辅导员、学区主管、项目主管、社会工作者和心理学家提供权限。 如果教师拥有课堂团队，则会 *自动* 获得权限。

若要提供组织级别的见解，你必须[从学生信息系统 (SIS) 导入数据](education-insights-sis-data-sync.md)，以便 Insights 能够正确映射教育系统的层次结构。

> [!NOTE]
> 只有全局管理员才能管理用户对 Insights 的访问权限。

> [!TIP]
> 我们建议为所有教育领导者启用 Insights，以便他们能够获得了解每所学校所需的数据，并能够快速发现问题并为教师提供支持。 即使只是运行试点项目，为所有教育领导者启用 Insights 可能仍然很有帮助，但这只针对试点用户组的通信。



## <a name="grant-permissions"></a>授予权限

* 打开 Insights 应用，单击“**设置**”，然后选择“**用户权限**”

:::image type="content" source="media/insights-user-permissions.png" alt-text="设置":::

* 选择“**添加用户**”。
* 输入每个用户的用户名或电子邮件地址。
* 选择权限级别：
  * **对所有组织的访问权限** 意味着用户将能够看到所有级别的组织单位。
  * **对特定学校的访问权限** 意味着用户将能够看到所选学校。 开始键入，然后从列表中选择相应学校。 你可以将多所学校添加到一起。
* 单击“**添加新用户**”。

:::image type="content" source="media/insights-add-users.png" alt-text="授予权限":::

> [!NOTE]
> 仅向有需要的教育领导者和他们负责的组织单位提供权限。 如果你不确定是否需要特定组织的用户权限，请咨询机构的隐私主题专家，例如法律或人事部门人员。

## <a name="edit-permissions"></a>编辑权限
* 选择特定用户，然后选择“**编辑权限**”。
* 更新权限级别或学校列表，然后单击“**更新权限**”。

:::image type="content" source="media/insights-edit-users.png" alt-text="编辑权限":::

## <a name="remove-permissions"></a>删除权限
* 选择要删除的用户，然后选择“**删除用户**”。
* 这些用户将不再有权访问组织级别的见解，但如果他们拥有课堂团队，则将仍然有权访问课堂级别的见解。

:::image type="content" source="media/insights-remove-users.png" alt-text="删除权限":::
