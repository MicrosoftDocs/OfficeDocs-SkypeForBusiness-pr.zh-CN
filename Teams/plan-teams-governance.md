---
title: 在 Teams 中规划管理 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，你将了解如何规划如何在团队中实施管理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea48b4df3313784cf129cf483aebac341917cb21
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656353"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="23d74-103">在 Teams 中规划管理</span><span class="sxs-lookup"><span data-stu-id="23d74-103">Plan for governance in Teams</span></span>

<span data-ttu-id="23d74-104">团队提供了一组丰富的工具来实施你的组织可能需要的任何监管功能。</span><span class="sxs-lookup"><span data-stu-id="23d74-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="23d74-105">本文指导 IT 专业人员提出正确的问题来确定他们对公司治理的要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="23d74-106">观看以下会话以了解有关 Microsoft 团队中的管理的详细信息： [Microsoft 团队中的管理、管理和生命周期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="23d74-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="23d74-107">组和团队创建、命名、分类和来宾访问</span><span class="sxs-lookup"><span data-stu-id="23d74-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="23d74-108">你的组织可能要求你实施严格的控制来控制团队的命名方式和分类方式，是否可以将来宾添加为团队成员以及谁可以创建团队。</span><span class="sxs-lookup"><span data-stu-id="23d74-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="23d74-109">你可以使用 Azure Active Directory (Azure AD) 配置这些区域中的每个区域。</span><span class="sxs-lookup"><span data-stu-id="23d74-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="23d74-110">决策点</span><span class="sxs-lookup"><span data-stu-id="23d74-110">Decision points</span></span>|<ul><li><span data-ttu-id="23d74-111">您的组织是否需要针对团队的特定命名约定？</span><span class="sxs-lookup"><span data-stu-id="23d74-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="23d74-112">团队创建者是否需要将组织特定的分类分配给团队的能力？</span><span class="sxs-lookup"><span data-stu-id="23d74-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="23d74-113">是否需要限制按团队为团队添加来宾的能力？</span><span class="sxs-lookup"><span data-stu-id="23d74-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="23d74-114">您的组织是否需要限制哪些人可以创建团队？</span><span class="sxs-lookup"><span data-stu-id="23d74-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="23d74-115">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23d74-115">Next steps</span></span>|<ul><li><span data-ttu-id="23d74-116">记录组织对团队创建、命名、分类和来宾访问的要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="23d74-117">计划在团队推出过程中实施这些要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="23d74-118">传达和发布你的策略以通知团队用户他们所期望的行为。</span><span class="sxs-lookup"><span data-stu-id="23d74-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="23d74-119">使用下表来捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="23d74-120">功能</span><span class="sxs-lookup"><span data-stu-id="23d74-120">Capability</span></span> |<span data-ttu-id="23d74-121">详细信息</span><span class="sxs-lookup"><span data-stu-id="23d74-121">Details</span></span> |<span data-ttu-id="23d74-122">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="23d74-122">Azure AD Premium</span></span> <br> <span data-ttu-id="23d74-123">需要许可证</span><span class="sxs-lookup"><span data-stu-id="23d74-123">license required</span></span> |<span data-ttu-id="23d74-124">作出</span><span class="sxs-lookup"><span data-stu-id="23d74-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="23d74-125">团队命名策略</span><span class="sxs-lookup"><span data-stu-id="23d74-125">Team naming policy</span></span> | <span data-ttu-id="23d74-126">使用基于前缀的后缀、自定义阻止的字词。</span><span class="sxs-lookup"><span data-stu-id="23d74-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="23d74-127">P1</span><span class="sxs-lookup"><span data-stu-id="23d74-127">P1</span></span> |<span data-ttu-id="23d74-128">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-128">TBD</span></span> |
|<span data-ttu-id="23d74-129">团队分类</span><span class="sxs-lookup"><span data-stu-id="23d74-129">Team classification</span></span> |<span data-ttu-id="23d74-130">为团队分配分类。</span><span class="sxs-lookup"><span data-stu-id="23d74-130">Assign classifications to teams.</span></span> |<span data-ttu-id="23d74-131">P1</span><span class="sxs-lookup"><span data-stu-id="23d74-131">P1</span></span> |<span data-ttu-id="23d74-132">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-132">TBD</span></span> |
|<span data-ttu-id="23d74-133">团队来宾访问</span><span class="sxs-lookup"><span data-stu-id="23d74-133">Team guest access</span></span> |<span data-ttu-id="23d74-134">允许或阻止将来宾添加到团队。</span><span class="sxs-lookup"><span data-stu-id="23d74-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="23d74-135">否</span><span class="sxs-lookup"><span data-stu-id="23d74-135">No</span></span> |<span data-ttu-id="23d74-136">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-136">TBD</span></span> |
|<span data-ttu-id="23d74-137">团队创建</span><span class="sxs-lookup"><span data-stu-id="23d74-137">Team creation</span></span> |<span data-ttu-id="23d74-138">将团队创建限制为管理员。</span><span class="sxs-lookup"><span data-stu-id="23d74-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="23d74-139">否</span><span class="sxs-lookup"><span data-stu-id="23d74-139">No</span></span> |<span data-ttu-id="23d74-140">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-140">TBD</span></span>|
|<span data-ttu-id="23d74-141">团队创建</span><span class="sxs-lookup"><span data-stu-id="23d74-141">Team creation</span></span> |<span data-ttu-id="23d74-142">将团队创建限制为安全组成员。</span><span class="sxs-lookup"><span data-stu-id="23d74-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="23d74-143">P1</span><span class="sxs-lookup"><span data-stu-id="23d74-143">P1</span></span> |<span data-ttu-id="23d74-144">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="23d74-145">为了帮助您提前计划，请[了解有关设置这些策略以及所需的许可证的详细信息](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="23d74-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="23d74-146">限制组和团队创建会降低用户的工作效率，因为许多 Microsoft 365 和 Office 365 服务都需要创建组才能使服务正常工作。</span><span class="sxs-lookup"><span data-stu-id="23d74-146">Limiting group and team creation can slow your users’ productivity, because many Microsoft 365 and Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="23d74-147">有关其他信息，请导航到并展开[控制创建 Microsoft 365 组的人员的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。</span><span class="sxs-lookup"><span data-stu-id="23d74-147">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="23d74-148">其他信息</span><span class="sxs-lookup"><span data-stu-id="23d74-148">Additional information</span></span>

<span data-ttu-id="23d74-149">确定你的要求后，你可以使用 Azure AD 控件实现它们。</span><span class="sxs-lookup"><span data-stu-id="23d74-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="23d74-150">有关如何实现这些设置的技术指南，请参阅：</span><span class="sxs-lookup"><span data-stu-id="23d74-150">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="23d74-151">[用于配置组设置的 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="23d74-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

- <span data-ttu-id="23d74-152">[在 Azure Active Directory 中强制使用 Microsoft 365 组的命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="23d74-152">[Enforce a naming policy for Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

- <span data-ttu-id="23d74-153">[Microsoft 365 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="23d74-153">[Microsoft 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="23d74-154">组和团队过期、保留和存档</span><span class="sxs-lookup"><span data-stu-id="23d74-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="23d74-155">你的组织可能对为过期、保留和存档团队和团队数据 (通道消息和频道) 文件设置策略的其他要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="23d74-156">你可以将组过期策略配置为自动管理组和保留策略的生命周期，以根据需要保留或删除信息，你可以将团队存档 (将其设置为只读模式) 以保留不再处于活动状态的团队的时间点视图。</span><span class="sxs-lookup"><span data-stu-id="23d74-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="23d74-158">决策点</span><span class="sxs-lookup"><span data-stu-id="23d74-158">Decision points</span></span>|<ul><li><span data-ttu-id="23d74-159">您的组织是否需要为团队指定到期日期？</span><span class="sxs-lookup"><span data-stu-id="23d74-159">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="23d74-160">您的组织是否需要向团队应用特定的数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="23d74-160">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="23d74-161">您的组织是否希望能够将非活动团队存档以使内容保持为只读状态？</span><span class="sxs-lookup"><span data-stu-id="23d74-161">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="23d74-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23d74-163">Next steps</span></span>|<ul><li><span data-ttu-id="23d74-164">记录组织对团队过期、数据保留和存档的要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-164">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="23d74-165">计划在团队推出过程中实现这些要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-165">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="23d74-166">传达和发布你的策略以通知团队用户他们所期望的行为。</span><span class="sxs-lookup"><span data-stu-id="23d74-166">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="23d74-167">使用下表来捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-167">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="23d74-168">功能</span><span class="sxs-lookup"><span data-stu-id="23d74-168">Capability</span></span> |<span data-ttu-id="23d74-169">详细信息</span><span class="sxs-lookup"><span data-stu-id="23d74-169">Details</span></span> |<span data-ttu-id="23d74-170">需要 Azure AD Premium 许可证</span><span class="sxs-lookup"><span data-stu-id="23d74-170">Azure AD Premium license required</span></span> |<span data-ttu-id="23d74-171">作出</span><span class="sxs-lookup"><span data-stu-id="23d74-171">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="23d74-172">过期策略</span><span class="sxs-lookup"><span data-stu-id="23d74-172">Expiration policy</span></span> |<span data-ttu-id="23d74-173">通过设置过期策略来管理 Microsoft 365 组的生命周期。</span><span class="sxs-lookup"><span data-stu-id="23d74-173">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="23d74-174">P1</span><span class="sxs-lookup"><span data-stu-id="23d74-174">P1</span></span> |<span data-ttu-id="23d74-175">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-175">TBD</span></span>|
|<span data-ttu-id="23d74-176">保留策略</span><span class="sxs-lookup"><span data-stu-id="23d74-176">Retention policy</span></span> |<span data-ttu-id="23d74-177">通过在安全 & 合规中心设置团队的保留策略来保留或删除特定时间段内的数据。</span><span class="sxs-lookup"><span data-stu-id="23d74-177">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="23d74-178">**注意**：使用此功能需要 Microsoft 365 或 Office 365 Enterprise E3 或更高版本的许可。</span><span class="sxs-lookup"><span data-stu-id="23d74-178">**Note**: Using this feature requires licensing of Microsoft 365 or Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="23d74-179">否</span><span class="sxs-lookup"><span data-stu-id="23d74-179">No</span></span> |<span data-ttu-id="23d74-180">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-180">TBD</span></span> |
|<span data-ttu-id="23d74-181">存档和还原</span><span class="sxs-lookup"><span data-stu-id="23d74-181">Archive and restore</span></span> |<span data-ttu-id="23d74-182">如果团队不再处于活动状态，而您想要保留它以供参考或在将来重新激活，请存档团队。</span><span class="sxs-lookup"><span data-stu-id="23d74-182">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="23d74-183">否</span><span class="sxs-lookup"><span data-stu-id="23d74-183">No</span></span> |<span data-ttu-id="23d74-184">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-184">TBD</span></span> |

> [!Note]
> <span data-ttu-id="23d74-185">组过期是 Azure AD Premium 功能。</span><span class="sxs-lookup"><span data-stu-id="23d74-185">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="23d74-186">为使此功能可用，你的租户必须对用于配置受影响组的设置和成员的管理员的 Azure AD Premium 和许可证进行订阅。</span><span class="sxs-lookup"><span data-stu-id="23d74-186">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="23d74-187">其他信息</span><span class="sxs-lookup"><span data-stu-id="23d74-187">Additional information</span></span>

<span data-ttu-id="23d74-188">有关如何实现这些设置的技术指南，请参阅：</span><span class="sxs-lookup"><span data-stu-id="23d74-188">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="23d74-189">[设置 Microsoft 365 组过期时间](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。</span><span class="sxs-lookup"><span data-stu-id="23d74-189">[Set up Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="23d74-190">[设置团队保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="23d74-190">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="23d74-191">[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="23d74-191">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>

## <a name="group-and-team-membership-management"></a><span data-ttu-id="23d74-192">组和团队成员身份管理</span><span class="sxs-lookup"><span data-stu-id="23d74-192">Group and team membership management</span></span>

<span data-ttu-id="23d74-193">对需要快速加入和脱离或用户和来宾的团队而言，一致地管理基于项目的成员或受限组是必需的。</span><span class="sxs-lookup"><span data-stu-id="23d74-193">Consistently managing members of project based, or restricted groups are necessary for teams that require rapid onboarding and offboarding or users and guests.</span></span> <span data-ttu-id="23d74-194">您的组织可能还需要确保所有当前成员在团队中具有业务理由。</span><span class="sxs-lookup"><span data-stu-id="23d74-194">Your organization may also need to make sure all current members have the business justification to be in a team.</span></span> <span data-ttu-id="23d74-195">管理成员可能很难，因为团队所有者可以离开，并且用户通常不会在项目结束或更改角色时退出组。</span><span class="sxs-lookup"><span data-stu-id="23d74-195">Managing members can be hard because team owners can leave and users don’t usually leave groups on their own accord when a project ends or when they change roles.</span></span> <span data-ttu-id="23d74-196">管理组成员身份的最佳方式允许用户在需要时获取访问权限，但确保组不会有不当的访问权限是通过两个地区流程：权利管理和访问评论。</span><span class="sxs-lookup"><span data-stu-id="23d74-196">The best way to manage group membership that allows users to get access when needed but ensure the group doesn't have a risk of inappropriate access is through two district processes: entitlement management and access reviews.</span></span>

<span data-ttu-id="23d74-197">[权利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)允许你委托给某人（如项目经理），以将所有需要的资源（包括团队成员）收集到单个程序包中。</span><span class="sxs-lookup"><span data-stu-id="23d74-197">[Entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) allows you to delegate to someone, such as a project manager, to collect all the resources that are needed, including teams memberships, into a single package.</span></span> <span data-ttu-id="23d74-198">他们还可以定义哪些人可以发出请求：租户中的用户或来自其他连接的组织的用户。</span><span class="sxs-lookup"><span data-stu-id="23d74-198">They can also define who can make requests: either users in your tenant or from other connected organizations.</span></span> <span data-ttu-id="23d74-199">项目经理将在其电子邮件中接收访问请求，并在 MyAccess 门户中批准或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="23d74-199">The project manager will receive access requests in their email and approve or deny requests in the MyAccess portal.</span></span> <span data-ttu-id="23d74-200">管理员可以将 access 的条件配置为包括过期日期或时间段，除非续订了 access，否则将从团队中删除用户或来宾。</span><span class="sxs-lookup"><span data-stu-id="23d74-200">Administrators can configure the conditions of access to include an expiry date or period by when the user or guest will be removed from the team unless access is renewed.</span></span> <span data-ttu-id="23d74-201">管理员还可以设置与团队相关联的组，以参与访问评论。</span><span class="sxs-lookup"><span data-stu-id="23d74-201">Administrators can also set up the groups associated with teams to take part in access reviews.</span></span> <span data-ttu-id="23d74-202">对于[access 审阅](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)，组所有者将收到定期提醒以查看团队成员。</span><span class="sxs-lookup"><span data-stu-id="23d74-202">For [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), the group owners will receive regular reminders to review the members of a team.</span></span> <span data-ttu-id="23d74-203">Access 评论包括建议，使组所有者可以更轻松地完成常规证明过程。</span><span class="sxs-lookup"><span data-stu-id="23d74-203">Access reviews include recommendations, which makes it easier for group owners to go through their regular attestation process.</span></span>

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | <span data-ttu-id="23d74-204">决策点</span><span class="sxs-lookup"><span data-stu-id="23d74-204">Decision points</span></span> | <span data-ttu-id="23d74-205">您的组织是否需要一个一致的流程来管理一个或多个团队的成员身份？</span><span class="sxs-lookup"><span data-stu-id="23d74-205">Does your organization require a consistent process for managing membership of one or more teams?</span></span> <br> <span data-ttu-id="23d74-206">您的组织是否需要所有者或成员自己来定期调整一个或多个团队的持续成员身份？</span><span class="sxs-lookup"><span data-stu-id="23d74-206">Does your organization require owners, or the members themselves, to justify their continued membership of one or more teams on a regular basis?</span></span> <br> <span data-ttu-id="23d74-207">你的组织是否需要批准用户和来宾请求对资源（包括团队、组、SharePoint 网站和应用）的访问权限？</span><span class="sxs-lookup"><span data-stu-id="23d74-207">Does your organization require approval for users and guests to request access to resources including teams, groups, SharePoint sites, and apps?</span></span> |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| <span data-ttu-id="23d74-208">后续步骤？</span><span class="sxs-lookup"><span data-stu-id="23d74-208">Next steps?</span></span> | <span data-ttu-id="23d74-209">为每个团队或特定团队的成员资格到期记录您的组织要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-209">Document your organizations requirements for each team or specific teams for membership expiry.</span></span><br><span data-ttu-id="23d74-210">规划你的组织可以如何将团队、组、SharePoint 网站和应用捆绑到 access 程序包中。</span><span class="sxs-lookup"><span data-stu-id="23d74-210">Plan how your organization can bundle teams, groups, SharePoint sites, and apps together in access packages.</span></span><br><span data-ttu-id="23d74-211">规划请求者的经理（如请求者的经理、项目经理、已连接组织的主办方或组织中的安全主管）将需要批准或拒绝访问请求。</span><span class="sxs-lookup"><span data-stu-id="23d74-211">Plan which people, such as the requestor's manager, a project manager, a sponsor for a connected organization or a security officer in your organization will need to approve or deny access requests.</span></span> |

> [!TIP]
> <span data-ttu-id="23d74-212">使用下表来捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-212">Use the following table to capture your organization’s requirements.</span></span>

| <span data-ttu-id="23d74-213">功能</span><span class="sxs-lookup"><span data-stu-id="23d74-213">Capability</span></span> | <span data-ttu-id="23d74-214">详细信息</span><span class="sxs-lookup"><span data-stu-id="23d74-214">Details</span></span> | <span data-ttu-id="23d74-215">需要 Azure AD Premium 许可证</span><span class="sxs-lookup"><span data-stu-id="23d74-215">Azure AD Premium license required</span></span> | <span data-ttu-id="23d74-216">作出</span><span class="sxs-lookup"><span data-stu-id="23d74-216">Decision</span></span> |
|:-|:-|:-|:-|
| <span data-ttu-id="23d74-217">访问评论</span><span class="sxs-lookup"><span data-stu-id="23d74-217">Access reviews</span></span> | <span data-ttu-id="23d74-218">设置访问权限审阅 recertify 特定团队的成员身份按固定间隔</span><span class="sxs-lookup"><span data-stu-id="23d74-218">Setup access reviews to recertify the membership of specific teams at regular interval</span></span> | <span data-ttu-id="23d74-219">又</span><span class="sxs-lookup"><span data-stu-id="23d74-219">P2</span></span> | <span data-ttu-id="23d74-220">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-220">TBD</span></span> |
| <span data-ttu-id="23d74-221">权利管理</span><span class="sxs-lookup"><span data-stu-id="23d74-221">Entitlement management</span></span> | <span data-ttu-id="23d74-222">设置访问程序包以允许用户和来宾请求对团队的访问权限</span><span class="sxs-lookup"><span data-stu-id="23d74-222">Setup access package to allow users and guests to request access to teams</span></span> | <span data-ttu-id="23d74-223">又</span><span class="sxs-lookup"><span data-stu-id="23d74-223">P2</span></span> | <span data-ttu-id="23d74-224">TBD</span><span class="sxs-lookup"><span data-stu-id="23d74-224">TBD</span></span> |

> [!NOTE]
> <span data-ttu-id="23d74-225">为了帮助您提前计划，请[了解有关他们需要哪些许可证的详细信息](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="23d74-225">To help you plan ahead, [learn more about what licenses they require](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="additional-information"></a><span data-ttu-id="23d74-226">其他信息</span><span class="sxs-lookup"><span data-stu-id="23d74-226">Additional information</span></span>

<span data-ttu-id="23d74-227">有关如何实现这些设置的技术指南，请参阅：</span><span class="sxs-lookup"><span data-stu-id="23d74-227">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="23d74-228">权利管理</span><span class="sxs-lookup"><span data-stu-id="23d74-228">Entitlement management</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [<span data-ttu-id="23d74-229">访问评论</span><span class="sxs-lookup"><span data-stu-id="23d74-229">Access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a><span data-ttu-id="23d74-230">团队功能管理</span><span class="sxs-lookup"><span data-stu-id="23d74-230">Teams feature management</span></span>

<span data-ttu-id="23d74-231">团队管理和生命周期管理的另一个重要方面是控制你的用户有权访问的功能的能力。</span><span class="sxs-lookup"><span data-stu-id="23d74-231">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="23d74-232">您可以在 Microsoft 365 或 Office 365 组织级别或按用户管理邮件、会议和呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="23d74-232">You can manage messaging, meeting, and calling features, either at the Microsoft 365 or Office 365 organization level or per-user.</span></span>


|         |         |
|---------|---------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="23d74-234">决策点</span><span class="sxs-lookup"><span data-stu-id="23d74-234">Decision points</span></span>|<ul><li><span data-ttu-id="23d74-235">您的组织是否需要针对您的整个租户限制团队功能？</span><span class="sxs-lookup"><span data-stu-id="23d74-235">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="23d74-236">您的组织是否需要针对特定用户限制团队功能？</span><span class="sxs-lookup"><span data-stu-id="23d74-236">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="23d74-238">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23d74-238">Next steps</span></span>|<ul><li><span data-ttu-id="23d74-239">记录组织在租户和用户级别限制团队功能的要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-239">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="23d74-240">计划在团队推出过程中实施特定要求。</span><span class="sxs-lookup"><span data-stu-id="23d74-240">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="23d74-241">传达和发布你的策略以通知团队用户他们所期望的行为。</span><span class="sxs-lookup"><span data-stu-id="23d74-241">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="23d74-242">团队功能管理重点领域</span><span class="sxs-lookup"><span data-stu-id="23d74-242">Teams feature management focus areas</span></span>

<span data-ttu-id="23d74-243">团队通过策略提供精确的功能，用于控制消息、会议、通话和实时事件功能等。</span><span class="sxs-lookup"><span data-stu-id="23d74-243">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="23d74-244">默认情况下，可根据组织的需要将不同的策略应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="23d74-244">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="23d74-245">有关所有设置的详细列表，包括有关如何为你的组织实施它们的技术指南，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="23d74-245">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="23d74-246">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="23d74-246">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="23d74-247">在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams</span><span class="sxs-lookup"><span data-stu-id="23d74-247">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="23d74-248">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="23d74-248">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="23d74-249">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="23d74-249">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)

<span data-ttu-id="23d74-250">此外，你可以为频道设置裁决，并向特定用户提供审阅者的功能，以便他们可以控制哪些人可以创建频道发布和答复他们。</span><span class="sxs-lookup"><span data-stu-id="23d74-250">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="23d74-251">有关详细信息，请参阅[在 Microsoft 团队中设置和管理通道裁决](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="23d74-251">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="23d74-252">安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="23d74-252">Security and compliance</span></span>

<span data-ttu-id="23d74-253">团队基于 Microsoft 365 和 Office 365 的高级安全和合规性功能构建，并支持审核和报告、合规性内容搜索、电子发现、法律封存和保留策略。</span><span class="sxs-lookup"><span data-stu-id="23d74-253">Teams is built on the advanced security and compliance capabilities of Microsoft 365 and Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span>

> [!Important]
> <span data-ttu-id="23d74-254">如果您的组织具有合规性和安全要求，请查看本文中提供的有关[Microsoft 团队安全性和合规性概述](security-compliance-overview.md)中的本主题的深入内容。</span><span class="sxs-lookup"><span data-stu-id="23d74-254">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="23d74-255">相关主题</span><span class="sxs-lookup"><span data-stu-id="23d74-255">Related topics</span></span>

[<span data-ttu-id="23d74-256">Teams 的管控快速入门</span><span class="sxs-lookup"><span data-stu-id="23d74-256">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
