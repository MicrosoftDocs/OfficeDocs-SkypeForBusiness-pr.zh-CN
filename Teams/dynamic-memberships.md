---
title: 团队的动态成员资格概述
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解基于 AAD 的动态团队成员资格。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 512ca6de74f5061976203b3467e7e17bdfe6a800
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408272"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>团队的动态成员资格概述

Microsoft 团队支持团队使用动态成员身份的 Office 365 组相关联。 动态成员资格使团队的成员身份对于某些检查用户属性在 Azure Active Directory (AAD) 的一个或多个规则定义。 用户自动添加或更改用户属性或用户加入和离开租户中移除的正确的团队。

动态成员身份，您可以使用安装程序对于某些团队组织中用户的群体。 可能的方案包括：
- 医院可创建护理、 医生和 surgeons 广播 communications 不同的团队。 如果这一点尤其重要医院依赖临时员工。
- 大学可以创建特定大学，包括经常更改附属教职员工内的所有教职员工的工作组。
- 航空公司想要创建的 （如星期二下午不间断从芝加哥到 Atlanta） 每航班工作组和具有频繁变化的航班 crew 自动分配或删除根据需要。

使用此功能，给定的团队成员更新自动基于一组特定的条件，而不是手动管理成员资格。 执行此操作需要 Azure AD Premium P1 许可证，团队成员资格可以是任何用户的 AAD 属性[由租户管理员分配](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)提供您具有一个租户和管理帐户。 

Microsoft 团队花几分钟到最多为 2 小时以反映动态成员身份更改之后生效的 Office 365 组的团队。 

> [!NOTE]
> - 规则可以定义谁是团队成员，但不是谁团队所有者。
> - 当前工作组和频道大小限制，请参阅[限制和规格的 Microsoft 团队](limits-specifications-teams.md)。
> - 所有者不能添加或删除用户作为团队的成员，因为由动态组规则定义成员。
> - 成员不能让团队后盾动态组。


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>创建和管理 Office 365 组与动态成员身份
时以租户管理员身份登录，请按照[创建动态组并检查状态](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)中的说明。 根据需要请参阅[动态成员身份的 Azure Active Directory 组的规则](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)。

## <a name="create-a-new-team-with-your-o365-group"></a>创建新工作组与 O365 组

现在允许时间成员资格才能使更改生效，并创建新的团队，[增强现有 Office 365 与 Microsoft 团队的组](enhance-office-365-groups.md)中所述。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>应用于现有团队的动态成员身份

您还可以采用现有团队，并更改其具有动态成员资格，[更改静态组成员身份为 Azure Active Directory 中动态](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)中所述。

## <a name="changes-in-client-behavior"></a>客户端行为中的更改

一旦团队启用动态成员身份，团队客户端不再允许工作组成员管理。 所有隐藏添加成员、 编辑成员角色、 发送和批准加入请求和离开团队的选项。
