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
description: 了解 Microsoft Teams 如何使用动态成员身份支持与 Microsoft 365 组关联的团队。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120764"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>团队的动态成员资格概述

Microsoft Teams 通过使用动态成员身份 支持与 Microsoft 365 组 *关联的团队*。 动态成员身份允许通过一个或多个规则定义团队的成员身份，这些规则可在 Azure AD (Azure Active Directory) 。 用户属性更改或用户加入并离开租户时，会自动将用户添加到正确的团队或删除用户。

使用动态成员身份，你可以为组织中特定用户队列设置团队。 可能的方案包括：
- 医院可以创建不同的团队，让护士、医生和医生广播通信。 如果医院依赖于临时员工，这尤其重要。
- 大学可创建特定大学内所有教职员工（包括经常更改的教职员工）的团队。
- 航空公司想要为每个航班团队创建一个团队 (例如周二下午从芝加哥到亚特兰大) 并根据需要自动分配或删除经常更改的航班乘务员。

使用此功能，给定团队成员将基于一组特定条件自动更新，而不是手动管理成员身份。 执行此操作需要 Azure AD Premium P1 许可证，[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)并且只要拥有租户和管理员帐户，租户管理员就可以将团队成员身份分配给任何用户的 Azure AD 属性。

Microsoft Teams 可能需要几分钟到最多 2 小时才能反映团队在 Microsoft 365 组中生效的动态成员身份更改。

> [!NOTE]
> - 规则可以定义团队成员，但不能定义团队所有者。
> - 有关 [团队和频道大小的当前限制，](limits-specifications-teams.md) 请参阅 Microsoft Teams 的限制和规范。
> - 所有者无法添加或删除作为团队成员的用户，因为成员由动态组规则定义。
> -    成员将不能离开由动态组支持的团队。

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>创建和管理具有动态成员身份的 Microsoft 365 组

以租户管理员身份登录时，请遵循创建动态 [组中的说明并检查状态](/azure/active-directory/users-groups-roles/groups-create-rule)。 根据需要，请参阅 [Azure Active Directory 中的组的动态成员身份规则](/azure/active-directory/users-groups-roles/groups-dynamic-membership)。

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>使用 Microsoft 365 组创建新团队

现在，允许成员身份更改生效，并创建一个新团队，如从现有组创建 [团队中所述](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>将动态成员身份应用于现有团队

还可以将现有团队更改为动态成员身份，如在 [Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)中将静态组成员身份更改为动态中所述。

## <a name="changes-in-client-behavior"></a>客户端行为更改

为团队启用动态成员身份后，Teams 客户端将不再允许对团队进行成员管理。 添加成员、编辑成员角色、发送和批准加入请求以及离开团队的选项全部处于隐藏状态。