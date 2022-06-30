---
title: 团队的动态成员资格概述
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解 Microsoft Teams 如何使用动态成员身份支持与 Microsoft 365 组关联的团队。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff6a71978873d723f39a534f876696a0def2f756
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562571"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>团队的动态成员资格概述

Microsoft Teams 通过使用 *动态成员身份* 支持与 Microsoft 365 组关联的团队。 动态成员身份使团队的成员身份能够由一个或多个规则定义，这些规则检查 Azure Active Directory (Azure AD) 中的某些用户属性。 当用户属性更改或用户加入并离开租户时，用户会自动添加或删除到正确的团队。

使用动态成员身份，可以为组织中的某些用户群体设置团队。 可能的方案包括：
- 医院可以为护士、医生和外科医生创建不同的团队来广播通信。 如果医院依赖于临时员工，这一点尤其重要。
- 大学可以为特定学院内的所有教职员工创建一个团队，包括经常变化的辅助教职员工。
- 一家航空公司希望为每班航班创建一个团队， (像周二下午从芝加哥到亚特兰大的不停) ，并根据需要自动分配或撤换经常变化的机组人员。

使用此功能，给定团队的成员会根据一组特定的条件自动更新，而不是手动管理成员身份。 这样做需要Azure AD Premium P1许可证和团队成员身份可以[由租户管理员分配](/azure/active-directory/users-groups-roles/groups-dynamic-membership)给任何用户的 Azure AD 属性，前提是你有一个租户和一个管理员帐户。

Microsoft Teams 在团队的 Microsoft 365 组中生效后，可能需要几分钟到最多 2 小时的时间来反映动态成员身份更改。

将团队与动态组配合使用时：

- 规则可以定义谁是团队成员，但不能定义谁是团队所有者。
- 所有者将无法添加或删除用户作为团队成员，因为成员由动态组规则定义。
- Teams 客户端不允许团队的成员管理。 添加成员、编辑成员角色、发送和批准加入请求以及让团队处于隐藏状态的选项。

若要创建使用动态成员身份的团队，请首先 [创建一个动态 Microsoft 365 组](/azure/active-directory/users-groups-roles/groups-create-rule) ，然后 [从该组创建一个团队](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

可以将现有团队更改为具有动态成员身份。 有关信息，请参阅 [Azure Active Directory 中将静态组成员身份更改为动态](/azure/active-directory/users-groups-roles/groups-change-type) 。

## <a name="related-topics"></a>相关主题

[Microsoft Teams 的限制和规范](limits-specifications-teams.md)

[Azure Active Directory 中组的动态成员身份规则](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
