---
title: 在 Teams 中规划管理 - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: 了解如何规划团队中实现调控功能。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 072fc92184841be318e84e7891a204d1b7576215
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246167"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="22b37-103">在 Teams 中规划管理</span><span class="sxs-lookup"><span data-stu-id="22b37-103">Plan for governance in Teams</span></span>

<span data-ttu-id="22b37-104">团队提供了一组丰富的工具，以实现您的组织可能需要任何管理功能。</span><span class="sxs-lookup"><span data-stu-id="22b37-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="22b37-105">本文指导 IT 专业人员提出正确的问题，以确定他们的调控和如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="22b37-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="22b37-106">观看下面的会话，若要了解有关 Microsoft 团队中的治理的详细信息：[监管、 管理和生命周期中的 Microsoft 团队](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="22b37-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="22b37-107">组和团队创建、 命名、 分类和来宾访问</span><span class="sxs-lookup"><span data-stu-id="22b37-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="22b37-108">您的组织可能要求您实现严格控制如何命名和分类团队、 是否可以作为工作组成员添加来宾和谁可以创建团队。</span><span class="sxs-lookup"><span data-stu-id="22b37-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="22b37-109">您可以使用 Azure Active Directory (Azure AD) 配置每个区域。</span><span class="sxs-lookup"><span data-stu-id="22b37-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="22b37-110">决策点</span><span class="sxs-lookup"><span data-stu-id="22b37-110">Decision points</span></span>|<ul><li><span data-ttu-id="22b37-111">您的组织是否需要为团队的特定命名约定？</span><span class="sxs-lookup"><span data-stu-id="22b37-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="22b37-112">团队创建者是否需要能够向工作组分配特定于组织的分类？</span><span class="sxs-lookup"><span data-stu-id="22b37-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="22b37-113">您是否需要限制将来宾添加到每个团队基于团队的功能？</span><span class="sxs-lookup"><span data-stu-id="22b37-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="22b37-114">贵组织需要限制哪些人可以创建团队？</span><span class="sxs-lookup"><span data-stu-id="22b37-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="22b37-115">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22b37-115">Next steps</span></span>|<ul><li><span data-ttu-id="22b37-116">文档的团队创建、 命名、 分类和来宾访问组织的要求。</span><span class="sxs-lookup"><span data-stu-id="22b37-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="22b37-117">按计划实现这些要求作为您的团队推出的一部分。</span><span class="sxs-lookup"><span data-stu-id="22b37-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="22b37-118">通信和发布您的策略以向团队用户告知他们可以预期的行为。</span><span class="sxs-lookup"><span data-stu-id="22b37-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="22b37-119">下表用于捕获贵组织的要求。</span><span class="sxs-lookup"><span data-stu-id="22b37-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="22b37-120">功能</span><span class="sxs-lookup"><span data-stu-id="22b37-120">Capability</span></span> |<span data-ttu-id="22b37-121">详细信息</span><span class="sxs-lookup"><span data-stu-id="22b37-121">Details</span></span> |<span data-ttu-id="22b37-122">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="22b37-122">Azure AD Premium</span></span> <br> <span data-ttu-id="22b37-123">所需的许可证</span><span class="sxs-lookup"><span data-stu-id="22b37-123">license required</span></span> |<span data-ttu-id="22b37-124">决策</span><span class="sxs-lookup"><span data-stu-id="22b37-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="22b37-125">团队命名策略</span><span class="sxs-lookup"><span data-stu-id="22b37-125">Team naming policy</span></span> | <span data-ttu-id="22b37-126">使用基于前缀后缀、 自定义已阻止单词。</span><span class="sxs-lookup"><span data-stu-id="22b37-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="22b37-127">P1</span><span class="sxs-lookup"><span data-stu-id="22b37-127">P1</span></span> |<span data-ttu-id="22b37-128">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-128">TBD</span></span> |
|<span data-ttu-id="22b37-129">团队分类</span><span class="sxs-lookup"><span data-stu-id="22b37-129">Team classification</span></span> |<span data-ttu-id="22b37-130">向工作组分配分类。</span><span class="sxs-lookup"><span data-stu-id="22b37-130">Assign classifications to teams.</span></span> |<span data-ttu-id="22b37-131">P1</span><span class="sxs-lookup"><span data-stu-id="22b37-131">P1</span></span> |<span data-ttu-id="22b37-132">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-132">TBD</span></span> |
|<span data-ttu-id="22b37-133">团队来宾访问</span><span class="sxs-lookup"><span data-stu-id="22b37-133">Team guest access</span></span> |<span data-ttu-id="22b37-134">允许或阻止来宾添加到团队。</span><span class="sxs-lookup"><span data-stu-id="22b37-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="22b37-135">否</span><span class="sxs-lookup"><span data-stu-id="22b37-135">No</span></span> |<span data-ttu-id="22b37-136">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-136">TBD</span></span> |
|<span data-ttu-id="22b37-137">团队创建</span><span class="sxs-lookup"><span data-stu-id="22b37-137">Team creation</span></span> |<span data-ttu-id="22b37-138">限制向管理员团队创建。</span><span class="sxs-lookup"><span data-stu-id="22b37-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="22b37-139">否</span><span class="sxs-lookup"><span data-stu-id="22b37-139">No</span></span> |<span data-ttu-id="22b37-140">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-140">TBD</span></span>|
|<span data-ttu-id="22b37-141">团队创建</span><span class="sxs-lookup"><span data-stu-id="22b37-141">Team creation</span></span> |<span data-ttu-id="22b37-142">限制团队创建安全组成员。</span><span class="sxs-lookup"><span data-stu-id="22b37-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="22b37-143">P1</span><span class="sxs-lookup"><span data-stu-id="22b37-143">P1</span></span> |<span data-ttu-id="22b37-144">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="22b37-145">可帮助您规划提前，[了解更多有关这些策略设置和哪些所需的许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="22b37-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="22b37-146">限制组和团队创建会降低用户工作效率，因为许多 Office 365 服务需要服务的函数创建的组。</span><span class="sxs-lookup"><span data-stu-id="22b37-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="22b37-147">有关其他信息，导航到，展开[为什么控制谁创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。</span><span class="sxs-lookup"><span data-stu-id="22b37-147">For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="22b37-148">其他信息</span><span class="sxs-lookup"><span data-stu-id="22b37-148">Additional information</span></span>

<span data-ttu-id="22b37-149">您已确定您的要求后，您可以使用 Azure AD 控件来实现它们。</span><span class="sxs-lookup"><span data-stu-id="22b37-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="22b37-150">有关如何实施这些设置的技术指导信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="22b37-150">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="22b37-151">[配置组设置的 azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="22b37-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

-   <span data-ttu-id="22b37-152">[强制在 Azure Active Directory 中的 Office 365 组命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="22b37-152">[Enforce a naming policy for Office 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

-   <span data-ttu-id="22b37-153">[Office 365 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="22b37-153">[Office 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="22b37-154">组和团队过期、 保留和存档</span><span class="sxs-lookup"><span data-stu-id="22b37-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="22b37-155">您的组织可能已设置的到期日期保留策略的其他要求和存档团队团队需要数据 （通道消息和频道文件）。</span><span class="sxs-lookup"><span data-stu-id="22b37-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="22b37-156">可以配置组过期策略，以自动管理生命周期的组和保留策略保留或删除的信息，根据需要且可以存档团队 （将它们设置为只读模式） 若要保留的时间点视图的工作组的不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="22b37-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="22b37-157">决策点</span><span class="sxs-lookup"><span data-stu-id="22b37-157">Decision points</span></span>|<ul><li><span data-ttu-id="22b37-158">贵组织需要指定团队的到期日期？</span><span class="sxs-lookup"><span data-stu-id="22b37-158">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="22b37-159">贵组织需要的特定数据保留策略应用于工作组？</span><span class="sxs-lookup"><span data-stu-id="22b37-159">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="22b37-160">您的组织是否希望需要能够存档非活动团队保留只读状态中的内容？</span><span class="sxs-lookup"><span data-stu-id="22b37-160">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="22b37-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22b37-161">Next steps</span></span>|<ul><li><span data-ttu-id="22b37-162">文档团队过期、 数据保留和存档的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="22b37-162">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="22b37-163">按计划实现这些要求您的团队推出的一部分。</span><span class="sxs-lookup"><span data-stu-id="22b37-163">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="22b37-164">通信和发布您的策略以向团队用户告知他们可以预期的行为。</span><span class="sxs-lookup"><span data-stu-id="22b37-164">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="22b37-165">下表用于捕获贵组织的要求。</span><span class="sxs-lookup"><span data-stu-id="22b37-165">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="22b37-166">功能</span><span class="sxs-lookup"><span data-stu-id="22b37-166">Capability</span></span> |<span data-ttu-id="22b37-167">详细信息</span><span class="sxs-lookup"><span data-stu-id="22b37-167">Details</span></span> |<span data-ttu-id="22b37-168">所需的 azure AD Premium 许可证</span><span class="sxs-lookup"><span data-stu-id="22b37-168">Azure AD Premium license required</span></span> |<span data-ttu-id="22b37-169">决策</span><span class="sxs-lookup"><span data-stu-id="22b37-169">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="22b37-170">过期策略</span><span class="sxs-lookup"><span data-stu-id="22b37-170">Expiration policy</span></span> |<span data-ttu-id="22b37-171">通过设置过期策略管理 Office 365 组的生命周期。</span><span class="sxs-lookup"><span data-stu-id="22b37-171">Manage the lifecycle of Office 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="22b37-172">P1</span><span class="sxs-lookup"><span data-stu-id="22b37-172">P1</span></span> |<span data-ttu-id="22b37-173">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-173">TBD</span></span>|
|<span data-ttu-id="22b37-174">保留策略</span><span class="sxs-lookup"><span data-stu-id="22b37-174">Retention policy</span></span> |<span data-ttu-id="22b37-175">保留还是删除在特定时间段内的数据，通过为团队的保留策略设置在安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="22b37-175">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="22b37-176">**注意**： 使用此功能要求许可或以上的 Office 365 企业版 E3。</span><span class="sxs-lookup"><span data-stu-id="22b37-176">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="22b37-177">否</span><span class="sxs-lookup"><span data-stu-id="22b37-177">No</span></span> |<span data-ttu-id="22b37-178">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-178">TBD</span></span> |
|<span data-ttu-id="22b37-179">存档和还原</span><span class="sxs-lookup"><span data-stu-id="22b37-179">Archive and restore</span></span> |<span data-ttu-id="22b37-180">存档团队不再处于活动状态时，但您希望保留其周围的引用或将来重新激活。</span><span class="sxs-lookup"><span data-stu-id="22b37-180">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="22b37-181">否</span><span class="sxs-lookup"><span data-stu-id="22b37-181">No</span></span> |<span data-ttu-id="22b37-182">TBD</span><span class="sxs-lookup"><span data-stu-id="22b37-182">TBD</span></span> |

> [!Note]
> <span data-ttu-id="22b37-183">组到期时间是 Azure AD Premium 功能。</span><span class="sxs-lookup"><span data-stu-id="22b37-183">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="22b37-184">能够使用此功能，您的租户必须为配置的设置和受影响的组的成员的管理员具有订阅 Azure AD Premium 和许可证。</span><span class="sxs-lookup"><span data-stu-id="22b37-184">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="22b37-185">其他信息</span><span class="sxs-lookup"><span data-stu-id="22b37-185">Additional information</span></span>

<span data-ttu-id="22b37-186">有关如何实施这些设置的技术指导信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="22b37-186">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="22b37-187">[设置 Office 365 组过期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。</span><span class="sxs-lookup"><span data-stu-id="22b37-187">[Set up Office 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

-   <span data-ttu-id="22b37-188">[设置团队保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="22b37-188">[Set up Teams retention policies](retention-policies.md).</span></span>

-   <span data-ttu-id="22b37-189">[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="22b37-189">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="22b37-190">团队功能管理</span><span class="sxs-lookup"><span data-stu-id="22b37-190">Teams feature management</span></span>

<span data-ttu-id="22b37-191">治理和生命周期管理团队的另一个重要方面是控制哪些功能您的用户将可以访问的能力。</span><span class="sxs-lookup"><span data-stu-id="22b37-191">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="22b37-192">您可以管理消息、 会议、 和呼叫功能，可以在 Office 365 租户级别或每个用户。</span><span class="sxs-lookup"><span data-stu-id="22b37-192">You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="22b37-193">决策点</span><span class="sxs-lookup"><span data-stu-id="22b37-193">Decision points</span></span>|<ul><li><span data-ttu-id="22b37-194">贵组织需要整个租户限制团队功能？</span><span class="sxs-lookup"><span data-stu-id="22b37-194">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="22b37-195">贵组织需要限制为特定用户的工作组功能？</span><span class="sxs-lookup"><span data-stu-id="22b37-195">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="22b37-196">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22b37-196">Next steps</span></span>|<ul><li><span data-ttu-id="22b37-197">文档的限制团队功能在租户和用户级别的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="22b37-197">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="22b37-198">按计划实现您的特定要求您的团队推出的一部分。</span><span class="sxs-lookup"><span data-stu-id="22b37-198">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="22b37-199">通信和发布您的策略以向团队用户告知他们可以预期的行为。</span><span class="sxs-lookup"><span data-stu-id="22b37-199">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="22b37-200">团队功能管理会议状态中心区域</span><span class="sxs-lookup"><span data-stu-id="22b37-200">Teams feature management focus areas</span></span>

<span data-ttu-id="22b37-201">团队提供精细的控制消息、 会议、 呼叫，和实时事件功能及其他内容，通过策略功能。</span><span class="sxs-lookup"><span data-stu-id="22b37-201">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="22b37-202">默认情况下或每个用户根据您的组织的需要，可以向所有用户应用不同的策略。</span><span class="sxs-lookup"><span data-stu-id="22b37-202">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="22b37-203">所有设置，包括有关如何为您的组织，实现这些技术指南的详细列表，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="22b37-203">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

-   [<span data-ttu-id="22b37-204">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="22b37-204">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
-   [<span data-ttu-id="22b37-205">在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams</span><span class="sxs-lookup"><span data-stu-id="22b37-205">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
-   [<span data-ttu-id="22b37-206">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="22b37-206">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a><span data-ttu-id="22b37-207">安全性和遵从性</span><span class="sxs-lookup"><span data-stu-id="22b37-207">Security and compliance</span></span>

<span data-ttu-id="22b37-208">团队基于的高级的安全和 Office 365 合规性功能和支持审核和报告、 合规性内容搜索、 电子发现、 法律挂起和保留策略。</span><span class="sxs-lookup"><span data-stu-id="22b37-208">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="22b37-209">如果您的组织具有合规性和安全要求，查看有关本主题[概述安全性和合规性中的 Microsoft 团队](security-compliance-overview.md)一文中提供的深入内容。</span><span class="sxs-lookup"><span data-stu-id="22b37-209">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
