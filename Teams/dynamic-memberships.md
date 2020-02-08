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
description: 了解基于 AAD 的动态团队成员身份。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44b7a87a003b59543c37feb278462e839d83bd1e
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863303"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="c70cf-103">团队的动态成员资格概述</span><span class="sxs-lookup"><span data-stu-id="c70cf-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="c70cf-104">Microsoft 团队支持使用*动态成员身份*与 Office 365 组相关联的团队。</span><span class="sxs-lookup"><span data-stu-id="c70cf-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="c70cf-105">动态成员资格允许团队的成员身份由一个或多个在 Azure Active Directory （Azure AD）中检查特定用户属性的规则定义。</span><span class="sxs-lookup"><span data-stu-id="c70cf-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c70cf-106">当用户属性发生更改或用户加入并离开租户时，用户将自动添加或删除到正确的团队。</span><span class="sxs-lookup"><span data-stu-id="c70cf-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="c70cf-107">利用动态成员身份，你可以为组织中的某些用户设置团队 cohorts。</span><span class="sxs-lookup"><span data-stu-id="c70cf-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="c70cf-108">可能的方案包括：</span><span class="sxs-lookup"><span data-stu-id="c70cf-108">Possible scenarios include:</span></span>
- <span data-ttu-id="c70cf-109">医院可以为护士、医生和 surgeons 创建独特的团队来广播通信。</span><span class="sxs-lookup"><span data-stu-id="c70cf-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="c70cf-110">如果医院依靠 temp 员工，这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="c70cf-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="c70cf-111">大学可以为特定大学中的所有教职员创建团队，包括经常变动的附属教职员。</span><span class="sxs-lookup"><span data-stu-id="c70cf-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="c70cf-112">航空公司希望为每个航班（如星期二下午不停从芝加哥到亚特兰大）创建团队，并且经常更改的航班职员会根据需要自动分配或删除。</span><span class="sxs-lookup"><span data-stu-id="c70cf-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="c70cf-113">使用此功能时，给定团队的成员会根据一组特定条件自动更新，而不是手动管理成员身份。</span><span class="sxs-lookup"><span data-stu-id="c70cf-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="c70cf-114">执行此操作需要使用 Azure AD Premium P1 许可证，并且团队成员可以[由租户管理员分配](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)给任何用户的 Azure AD 属性（前提是你有租户和管理员帐户）。</span><span class="sxs-lookup"><span data-stu-id="c70cf-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="c70cf-115">在团队的 Office 365 组中，Microsoft 团队可能会从几分钟到最多2小时的时间来反映动态成员身份更改。</span><span class="sxs-lookup"><span data-stu-id="c70cf-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="c70cf-116">规则可定义团队成员，但不能定义团队所有者。</span><span class="sxs-lookup"><span data-stu-id="c70cf-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="c70cf-117">有关工作组和频道大小的当前限制，请参阅[Microsoft 团队的限制和规范](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c70cf-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="c70cf-118">所有者将无法将用户添加或删除为团队成员，因为成员由动态组规则定义。</span><span class="sxs-lookup"><span data-stu-id="c70cf-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="c70cf-119">成员将无法退出由动态组支持的团队。</span><span class="sxs-lookup"><span data-stu-id="c70cf-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="c70cf-120">使用动态成员身份创建和管理 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="c70cf-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="c70cf-121">以租户管理员身份登录时，按照[创建动态组和检查状态](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c70cf-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="c70cf-122">根据需要，请参阅[Azure Active Directory 中的组的动态成员身份规则](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)。</span><span class="sxs-lookup"><span data-stu-id="c70cf-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="c70cf-123">使用 O365 组创建新团队</span><span class="sxs-lookup"><span data-stu-id="c70cf-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="c70cf-124">现在，允许成员身份更改生效，并创建新团队，如[使用 Microsoft 团队增强现有 Office 365 组](enhance-office-365-groups.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="c70cf-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="c70cf-125">将动态成员身份应用于现有团队</span><span class="sxs-lookup"><span data-stu-id="c70cf-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="c70cf-126">你还可以获取现有团队并将其更改为拥有动态成员身份，如在[Azure Active Directory 中将静态组成员身份更改为动态的组成员身份](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)中所述。</span><span class="sxs-lookup"><span data-stu-id="c70cf-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="c70cf-127">客户端行为的更改</span><span class="sxs-lookup"><span data-stu-id="c70cf-127">Changes in client behavior</span></span>

<span data-ttu-id="c70cf-128">为团队启用动态成员身份后，团队客户将不再允许团队的成员管理。</span><span class="sxs-lookup"><span data-stu-id="c70cf-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="c70cf-129">用于添加成员、编辑成员角色、发送和批准加入请求以及保持团队全部隐藏的选项。</span><span class="sxs-lookup"><span data-stu-id="c70cf-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
