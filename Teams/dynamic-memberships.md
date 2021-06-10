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
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856321"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="7083a-103">团队的动态成员资格概述</span><span class="sxs-lookup"><span data-stu-id="7083a-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="7083a-104">Microsoft Teams动态成员身份 支持与Microsoft 365组 *关联的团队*。</span><span class="sxs-lookup"><span data-stu-id="7083a-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="7083a-105">动态成员身份允许通过一个或多个规则定义团队的成员身份，这些规则在 Azure AD Azure Active Directory (中检查) 。</span><span class="sxs-lookup"><span data-stu-id="7083a-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7083a-106">用户属性更改或用户加入并离开租户时，会自动将用户添加到正确的团队或删除用户。</span><span class="sxs-lookup"><span data-stu-id="7083a-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="7083a-107">使用动态成员身份，你可以为组织中特定用户队列设置团队。</span><span class="sxs-lookup"><span data-stu-id="7083a-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="7083a-108">可能的方案包括：</span><span class="sxs-lookup"><span data-stu-id="7083a-108">Possible scenarios include:</span></span>
- <span data-ttu-id="7083a-109">医院可以创建不同的团队，让护士、医生和医生广播通信。</span><span class="sxs-lookup"><span data-stu-id="7083a-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="7083a-110">如果医院依赖于临时员工，这尤其重要。</span><span class="sxs-lookup"><span data-stu-id="7083a-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="7083a-111">大学可创建特定大学内所有教职员工（包括经常更改的教职员工）的团队。</span><span class="sxs-lookup"><span data-stu-id="7083a-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="7083a-112">航空公司想要为每个航班团队创建一个团队 (例如周二下午从芝加哥到亚特兰大) 并根据需要自动分配或删除经常更改的航班乘务员。</span><span class="sxs-lookup"><span data-stu-id="7083a-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="7083a-113">使用此功能，给定团队成员将基于一组特定条件自动更新，而不是手动管理成员身份。</span><span class="sxs-lookup"><span data-stu-id="7083a-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="7083a-114">执行此操作需要 Azure AD 高级版 P1 许可证，并且只要拥有[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)租户和管理员帐户，租户管理员就可以将团队成员身份分配给任何用户的 Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="7083a-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="7083a-115">Microsoft Teams可能需要几分钟到最多 2 小时才能反映动态成员身份更改，一旦这些更改在团队的 Microsoft 365 组中生效。</span><span class="sxs-lookup"><span data-stu-id="7083a-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="7083a-116">将团队与动态组一起使用时：</span><span class="sxs-lookup"><span data-stu-id="7083a-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="7083a-117">规则可以定义团队成员，但不能定义团队所有者。</span><span class="sxs-lookup"><span data-stu-id="7083a-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="7083a-118">所有者无法添加或删除作为团队成员的用户，因为成员由动态组规则定义。</span><span class="sxs-lookup"><span data-stu-id="7083a-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="7083a-119">Teams不允许对团队进行成员管理。</span><span class="sxs-lookup"><span data-stu-id="7083a-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="7083a-120">添加成员、编辑成员角色、发送和批准加入请求以及离开团队的选项全部处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="7083a-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="7083a-121">若要创建使用动态成员身份的团队，请首先创建动态Microsoft 365[组，](/azure/active-directory/users-groups-roles/groups-create-rule)然后[从该组创建团队](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。</span><span class="sxs-lookup"><span data-stu-id="7083a-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="7083a-122">可以将现有团队更改为动态成员身份。</span><span class="sxs-lookup"><span data-stu-id="7083a-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="7083a-123">有关[信息，请参阅将静态组成员身份](/azure/active-directory/users-groups-roles/groups-change-type)Azure Active Directory动态。</span><span class="sxs-lookup"><span data-stu-id="7083a-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7083a-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="7083a-124">Related topics</span></span>

[<span data-ttu-id="7083a-125">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="7083a-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="7083a-126">组中组的动态成员身份Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7083a-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
