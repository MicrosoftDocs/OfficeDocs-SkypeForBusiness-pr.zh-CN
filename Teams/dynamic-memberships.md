---
title: 团队的动态成员资格概述
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何Microsoft Teams动态成员身份支持Microsoft 365组关联的团队。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a18e2cbe1a34fe78f5e84b4df4ae9a95c46fd9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613631"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>团队的动态成员资格概述

Microsoft Teams使用动态成员身份 支持Microsoft 365组 *关联的团队*。 动态成员身份允许通过一个或多个规则定义团队的成员身份，这些规则在 Azure AD Azure Active Directory (中) 。 用户属性更改或用户加入并离开租户时，会自动将用户添加到正确的团队或删除用户。

使用动态成员身份，你可以为组织中特定队列的用户设置团队。 可能的方案包括：
- 医院可以创建不同的团队，让护士、医生和医生广播通信。 如果医院依赖于临时员工，这尤其重要。
- 大学可创建特定大学内所有教职员工（包括经常更改的教职员工）的团队。
- 航空公司希望为每个航班团队创建一个团队 (例如周二下午从芝加哥到亚特兰大的不) 并根据需要自动分配或删除经常更改的航班乘务员。

使用此功能，给定团队的成员会基于一组特定条件自动更新，而不是手动管理成员身份。 执行此操作需要Azure AD Premium P1拥有租户和管理员帐户，租户管理员可以将许可证[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)和团队成员身份分配给任何用户的 Azure AD 属性。

Microsoft Teams在团队的组组生效后，可能需要几分钟到最多 2 小时Microsoft 365反映动态成员身份更改。

将团队与动态组一起使用时：

- 规则可以定义团队成员，但不能定义团队所有者。
- 所有者无法添加或删除作为团队成员的用户，因为成员由动态组规则定义。
- Teams不允许对团队进行成员管理。 添加成员、编辑成员角色、发送和批准加入请求以及离开团队的选项全部处于隐藏状态。

若要创建使用动态成员身份的团队，请首先创建动态Microsoft 365[组，](/azure/active-directory/users-groups-roles/groups-create-rule)然后[从该组创建团队](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

可以将现有团队更改为动态成员身份。 有关[信息，请参阅在 Azure Active Directory中将静态组成员身份](/azure/active-directory/users-groups-roles/groups-change-type)更改为动态。

## <a name="related-topics"></a>相关主题

[Microsoft Teams 的限制和规范](limits-specifications-teams.md)

[组中组的动态成员身份Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
