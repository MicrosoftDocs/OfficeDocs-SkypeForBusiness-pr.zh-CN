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
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="b36b0-103">团队的动态成员资格概述</span><span class="sxs-lookup"><span data-stu-id="b36b0-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="b36b0-104">Microsoft 团队支持团队使用动态成员身份的 Office 365 组相关联。</span><span class="sxs-lookup"><span data-stu-id="b36b0-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="b36b0-105">动态成员资格使团队的成员身份对于某些检查用户属性在 Azure Active Directory (AAD) 的一个或多个规则定义。</span><span class="sxs-lookup"><span data-stu-id="b36b0-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="b36b0-106">用户自动添加或更改用户属性或用户加入和离开租户中移除的正确的团队。</span><span class="sxs-lookup"><span data-stu-id="b36b0-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="b36b0-107">动态成员身份，您可以使用安装程序对于某些团队组织中用户的群体。</span><span class="sxs-lookup"><span data-stu-id="b36b0-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="b36b0-108">可能的方案包括：</span><span class="sxs-lookup"><span data-stu-id="b36b0-108">Possible scenarios include:</span></span>
- <span data-ttu-id="b36b0-109">医院可创建护理、 医生和 surgeons 广播 communications 不同的团队。</span><span class="sxs-lookup"><span data-stu-id="b36b0-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="b36b0-110">如果这一点尤其重要医院依赖临时员工。</span><span class="sxs-lookup"><span data-stu-id="b36b0-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="b36b0-111">大学可以创建特定大学，包括经常更改附属教职员工内的所有教职员工的工作组。</span><span class="sxs-lookup"><span data-stu-id="b36b0-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="b36b0-112">航空公司想要创建的 （如星期二下午不间断从芝加哥到 Atlanta） 每航班工作组和具有频繁变化的航班 crew 自动分配或删除根据需要。</span><span class="sxs-lookup"><span data-stu-id="b36b0-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="b36b0-113">使用此功能，给定的团队成员更新自动基于一组特定的条件，而不是手动管理成员资格。</span><span class="sxs-lookup"><span data-stu-id="b36b0-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="b36b0-114">执行此操作需要 Azure AD Premium P1 许可证，团队成员资格可以是任何用户的 AAD 属性[由租户管理员分配](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)提供您具有一个租户和管理帐户。</span><span class="sxs-lookup"><span data-stu-id="b36b0-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="b36b0-115">Microsoft 团队花几分钟到最多为 2 小时以反映动态成员身份更改之后生效的 Office 365 组的团队。</span><span class="sxs-lookup"><span data-stu-id="b36b0-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="b36b0-116">规则可以定义谁是团队成员，但不是谁团队所有者。</span><span class="sxs-lookup"><span data-stu-id="b36b0-116">Rules can define who is a team member, but not who is a team Owner.</span></span>
> - <span data-ttu-id="b36b0-117">当前工作组和频道大小限制，请参阅[限制和规格的 Microsoft 团队](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b36b0-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>
> - <span data-ttu-id="b36b0-118">所有者不能添加或删除用户作为团队的成员，因为由动态组规则定义成员。</span><span class="sxs-lookup"><span data-stu-id="b36b0-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="b36b0-119">成员不能让团队后盾动态组。</span><span class="sxs-lookup"><span data-stu-id="b36b0-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="b36b0-120">创建和管理 Office 365 组与动态成员身份</span><span class="sxs-lookup"><span data-stu-id="b36b0-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="b36b0-121">时以租户管理员身份登录，请按照[创建动态组并检查状态](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)中的说明。</span><span class="sxs-lookup"><span data-stu-id="b36b0-121">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="b36b0-122">根据需要请参阅[动态成员身份的 Azure Active Directory 组的规则](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)。</span><span class="sxs-lookup"><span data-stu-id="b36b0-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="b36b0-123">创建新工作组与 O365 组</span><span class="sxs-lookup"><span data-stu-id="b36b0-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="b36b0-124">现在允许时间成员资格才能使更改生效，并创建新的团队，[增强现有 Office 365 与 Microsoft 团队的组](enhance-office-365-groups.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="b36b0-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="b36b0-125">应用于现有团队的动态成员身份</span><span class="sxs-lookup"><span data-stu-id="b36b0-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="b36b0-126">您还可以采用现有团队，并更改其具有动态成员资格，[更改静态组成员身份为 Azure Active Directory 中动态](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)中所述。</span><span class="sxs-lookup"><span data-stu-id="b36b0-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="b36b0-127">客户端行为中的更改</span><span class="sxs-lookup"><span data-stu-id="b36b0-127">Changes in client behavior</span></span>

<span data-ttu-id="b36b0-128">一旦团队启用动态成员身份，团队客户端不再允许工作组成员管理。</span><span class="sxs-lookup"><span data-stu-id="b36b0-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="b36b0-129">所有隐藏添加成员、 编辑成员角色、 发送和批准加入请求和离开团队的选项。</span><span class="sxs-lookup"><span data-stu-id="b36b0-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
