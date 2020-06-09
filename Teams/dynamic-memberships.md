---
title: 团队的动态成员资格概述
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解 Microsoft 团队如何通过使用动态成员资格支持与 Microsoft 365 组关联的团队。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc7e3124ec3ec97e3f3643412ccb4f990ab825cc
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638401"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>团队的动态成员资格概述

Microsoft 团队支持使用*动态成员身份*与 microsoft 365 组相关联的团队。 动态成员资格允许团队的成员身份由一个或多个在 Azure Active Directory （Azure AD）中检查特定用户属性的规则定义。 当用户属性发生更改或用户加入并离开租户时，用户将自动添加或删除到正确的团队。

利用动态成员身份，你可以为组织中的某些用户设置团队 cohorts。 可能的方案包括：
- 医院可以为护士、医生和 surgeons 创建独特的团队来广播通信。 如果医院依靠 temp 员工，这一点尤其重要。
- 大学可以为特定大学中的所有教职员创建团队，包括经常变动的附属教职员。
- 航空公司希望为每个航班（如星期二下午不停从芝加哥到亚特兰大）创建团队，并且经常更改的航班职员会根据需要自动分配或删除。

使用此功能时，给定团队的成员会根据一组特定条件自动更新，而不是手动管理成员身份。 执行此操作需要使用 Azure AD Premium P1 许可证，并且团队成员可以[由租户管理员分配](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)给任何用户的 Azure AD 属性（前提是你有租户和管理员帐户）。

Microsoft 团队可能会从几分钟到最多2小时的时间，以反映动态成员身份更改一旦在团队的 Microsoft 365 组中生效。

> [!NOTE]
> - 规则可定义团队成员，但不能定义团队所有者。
> - 有关工作组和频道大小的当前限制，请参阅[Microsoft 团队的限制和规范](limits-specifications-teams.md)。
> - 所有者将无法将用户添加或删除为团队成员，因为成员由动态组规则定义。
> -    成员将无法退出由动态组支持的团队。


## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>使用动态成员身份创建和管理 Microsoft 365 组
以租户管理员身份登录时，按照[创建动态组和检查状态](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)中的说明进行操作。 根据需要，请参阅[Azure Active Directory 中的组的动态成员身份规则](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)。

## <a name="create-a-new-team-with-your-o365-group"></a>使用 O365 组创建新团队

现在，允许成员身份更改生效，并创建新团队，如[使用 Microsoft 团队增强现有 Microsoft 365 组](enhance-office-365-groups.md)中所述。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>将动态成员身份应用于现有团队

你还可以获取现有团队并将其更改为拥有动态成员身份，如在[Azure Active Directory 中将静态组成员身份更改为动态的组成员身份](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)中所述。

## <a name="changes-in-client-behavior"></a>客户端行为的更改

为团队启用动态成员身份后，团队客户将不再允许团队的成员管理。 用于添加成员、编辑成员角色、发送和批准加入请求以及保持团队全部隐藏的选项。
