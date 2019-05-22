---
title: 在 Teams 中规划管理 - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: 了解如何规划团队中实施管理功能。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10fb80667a957ac4f4a7d9e25713a9232129b0b7
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344377"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="ea534-103">在 Teams 中规划管理</span><span class="sxs-lookup"><span data-stu-id="ea534-103">Plan for governance in Teams</span></span>

<span data-ttu-id="ea534-104">团队提供了一组丰富的工具来实施你的组织可能需要的任何监管功能。</span><span class="sxs-lookup"><span data-stu-id="ea534-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="ea534-105">本文指导 IT 专业人员提出正确的问题来确定他们对公司治理的要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="ea534-106">观看以下会话以了解有关 Microsoft 团队中的管理的详细信息: [Microsoft 团队中的管理、管理和生命周期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="ea534-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="ea534-107">组和团队创建、命名、分类和来宾访问</span><span class="sxs-lookup"><span data-stu-id="ea534-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="ea534-108">你的组织可能要求你实施严格的控制来控制团队的命名方式和分类方式, 是否可以将来宾添加为团队成员以及谁可以创建团队。</span><span class="sxs-lookup"><span data-stu-id="ea534-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="ea534-109">你可以使用 Azure Active Directory (Azure AD) 配置这些区域中的每个区域。</span><span class="sxs-lookup"><span data-stu-id="ea534-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="ea534-110">决策点</span><span class="sxs-lookup"><span data-stu-id="ea534-110">Decision points</span></span>|<ul><li><span data-ttu-id="ea534-111">您的组织是否需要针对团队的特定命名约定？</span><span class="sxs-lookup"><span data-stu-id="ea534-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="ea534-112">团队创建者是否需要将组织特定的分类分配给团队的能力？</span><span class="sxs-lookup"><span data-stu-id="ea534-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="ea534-113">是否需要限制按团队为团队添加来宾的能力？</span><span class="sxs-lookup"><span data-stu-id="ea534-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="ea534-114">您的组织是否需要限制哪些人可以创建团队？</span><span class="sxs-lookup"><span data-stu-id="ea534-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="ea534-115">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea534-115">Next steps</span></span>|<ul><li><span data-ttu-id="ea534-116">记录组织对团队创建、命名、分类和来宾访问的要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="ea534-117">计划在团队推出过程中实施这些要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="ea534-118">传达和发布你的策略以通知团队用户他们所期望的行为。</span><span class="sxs-lookup"><span data-stu-id="ea534-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="ea534-119">使用下表来捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="ea534-120">能</span><span class="sxs-lookup"><span data-stu-id="ea534-120">Capability</span></span> |<span data-ttu-id="ea534-121">详细信息</span><span class="sxs-lookup"><span data-stu-id="ea534-121">Details</span></span> |<span data-ttu-id="ea534-122">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="ea534-122">Azure AD Premium</span></span> <br> <span data-ttu-id="ea534-123">需要许可证</span><span class="sxs-lookup"><span data-stu-id="ea534-123">license required</span></span> |<span data-ttu-id="ea534-124">作出</span><span class="sxs-lookup"><span data-stu-id="ea534-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="ea534-125">团队命名策略</span><span class="sxs-lookup"><span data-stu-id="ea534-125">Team naming policy</span></span> | <span data-ttu-id="ea534-126">使用基于前缀的后缀、自定义阻止的字词。</span><span class="sxs-lookup"><span data-stu-id="ea534-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="ea534-127">P1</span><span class="sxs-lookup"><span data-stu-id="ea534-127">P1</span></span> |<span data-ttu-id="ea534-128">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-128">TBD</span></span> |
|<span data-ttu-id="ea534-129">团队分类</span><span class="sxs-lookup"><span data-stu-id="ea534-129">Team classification</span></span> |<span data-ttu-id="ea534-130">为团队分配分类。</span><span class="sxs-lookup"><span data-stu-id="ea534-130">Assign classifications to teams.</span></span> |<span data-ttu-id="ea534-131">P1</span><span class="sxs-lookup"><span data-stu-id="ea534-131">P1</span></span> |<span data-ttu-id="ea534-132">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-132">TBD</span></span> |
|<span data-ttu-id="ea534-133">团队来宾访问</span><span class="sxs-lookup"><span data-stu-id="ea534-133">Team guest access</span></span> |<span data-ttu-id="ea534-134">允许或阻止将来宾添加到团队。</span><span class="sxs-lookup"><span data-stu-id="ea534-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="ea534-135">否</span><span class="sxs-lookup"><span data-stu-id="ea534-135">No</span></span> |<span data-ttu-id="ea534-136">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-136">TBD</span></span> |
|<span data-ttu-id="ea534-137">团队创建</span><span class="sxs-lookup"><span data-stu-id="ea534-137">Team creation</span></span> |<span data-ttu-id="ea534-138">将团队创建限制为管理员。</span><span class="sxs-lookup"><span data-stu-id="ea534-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="ea534-139">否</span><span class="sxs-lookup"><span data-stu-id="ea534-139">No</span></span> |<span data-ttu-id="ea534-140">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-140">TBD</span></span>|
|<span data-ttu-id="ea534-141">团队创建</span><span class="sxs-lookup"><span data-stu-id="ea534-141">Team creation</span></span> |<span data-ttu-id="ea534-142">将团队创建限制为安全组成员。</span><span class="sxs-lookup"><span data-stu-id="ea534-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="ea534-143">P1</span><span class="sxs-lookup"><span data-stu-id="ea534-143">P1</span></span> |<span data-ttu-id="ea534-144">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="ea534-145">为了帮助您提前计划, 请[了解有关设置这些策略以及所需的许可证的详细信息](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="ea534-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="ea534-146">限制组和团队创建会降低用户的工作效率, 因为许多 Office 365 服务都需要创建组才能使服务正常工作。</span><span class="sxs-lookup"><span data-stu-id="ea534-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="ea534-147">有关其他信息, 请导航到并展开[控制创建 Office 365 组的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。</span><span class="sxs-lookup"><span data-stu-id="ea534-147">For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="ea534-148">其他信息</span><span class="sxs-lookup"><span data-stu-id="ea534-148">Additional information</span></span>

<span data-ttu-id="ea534-149">确定你的要求后, 你可以使用 Azure AD 控件实现它们。</span><span class="sxs-lookup"><span data-stu-id="ea534-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="ea534-150">有关如何实现这些设置的技术指南, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="ea534-150">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="ea534-151">[用于配置组设置的 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="ea534-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

-   <span data-ttu-id="ea534-152">[在 Azure Active Directory 中强制使用 Office 365 组的命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="ea534-152">[Enforce a naming policy for Office 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

-   <span data-ttu-id="ea534-153">[Office 365 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="ea534-153">[Office 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="ea534-154">组和团队过期、保留和存档</span><span class="sxs-lookup"><span data-stu-id="ea534-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="ea534-155">你的组织可能对为过期、保留和存档团队和团队数据 (频道消息和频道文件) 设置策略的其他要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="ea534-156">你可以将组过期策略配置为自动管理组和保留策略的生命周期, 以根据需要保留或删除信息, 并且可以将团队存档 (设置为只读模式) 以保留团队的时间点视图不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ea534-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ea534-158">决策点</span><span class="sxs-lookup"><span data-stu-id="ea534-158">Decision points</span></span>|<ul><li><span data-ttu-id="ea534-159">您的组织是否需要为团队指定到期日期？</span><span class="sxs-lookup"><span data-stu-id="ea534-159">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="ea534-160">您的组织是否需要向团队应用特定的数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="ea534-160">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="ea534-161">您的组织是否希望能够将非活动团队存档以使内容保持为只读状态？</span><span class="sxs-lookup"><span data-stu-id="ea534-161">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="ea534-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea534-163">Next steps</span></span>|<ul><li><span data-ttu-id="ea534-164">记录组织对团队过期、数据保留和存档的要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-164">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="ea534-165">计划在团队推出过程中实现这些要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-165">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="ea534-166">传达和发布你的策略以通知团队用户他们所期望的行为。</span><span class="sxs-lookup"><span data-stu-id="ea534-166">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="ea534-167">使用下表来捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-167">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="ea534-168">能</span><span class="sxs-lookup"><span data-stu-id="ea534-168">Capability</span></span> |<span data-ttu-id="ea534-169">详细信息</span><span class="sxs-lookup"><span data-stu-id="ea534-169">Details</span></span> |<span data-ttu-id="ea534-170">需要 Azure AD Premium 许可证</span><span class="sxs-lookup"><span data-stu-id="ea534-170">Azure AD Premium license required</span></span> |<span data-ttu-id="ea534-171">作出</span><span class="sxs-lookup"><span data-stu-id="ea534-171">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="ea534-172">过期策略</span><span class="sxs-lookup"><span data-stu-id="ea534-172">Expiration policy</span></span> |<span data-ttu-id="ea534-173">通过设置过期策略来管理 Office 365 组的生命周期。</span><span class="sxs-lookup"><span data-stu-id="ea534-173">Manage the lifecycle of Office 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="ea534-174">P1</span><span class="sxs-lookup"><span data-stu-id="ea534-174">P1</span></span> |<span data-ttu-id="ea534-175">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-175">TBD</span></span>|
|<span data-ttu-id="ea534-176">保留策略</span><span class="sxs-lookup"><span data-stu-id="ea534-176">Retention policy</span></span> |<span data-ttu-id="ea534-177">通过在安全 & 合规中心设置团队的保留策略来保留或删除特定时间段内的数据。</span><span class="sxs-lookup"><span data-stu-id="ea534-177">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="ea534-178">**注意**: 使用此功能需要 Office 365 企业版 E3 或更高版本的许可。</span><span class="sxs-lookup"><span data-stu-id="ea534-178">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="ea534-179">否</span><span class="sxs-lookup"><span data-stu-id="ea534-179">No</span></span> |<span data-ttu-id="ea534-180">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-180">TBD</span></span> |
|<span data-ttu-id="ea534-181">存档和还原</span><span class="sxs-lookup"><span data-stu-id="ea534-181">Archive and restore</span></span> |<span data-ttu-id="ea534-182">如果团队不再处于活动状态, 而您想要保留它以供参考或在将来重新激活, 请存档团队。</span><span class="sxs-lookup"><span data-stu-id="ea534-182">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="ea534-183">否</span><span class="sxs-lookup"><span data-stu-id="ea534-183">No</span></span> |<span data-ttu-id="ea534-184">TBD</span><span class="sxs-lookup"><span data-stu-id="ea534-184">TBD</span></span> |

> [!Note]
> <span data-ttu-id="ea534-185">组过期是 Azure AD Premium 功能。</span><span class="sxs-lookup"><span data-stu-id="ea534-185">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="ea534-186">为使此功能可用, 你的租户必须对用于配置受影响组的设置和成员的管理员的 Azure AD Premium 和许可证进行订阅。</span><span class="sxs-lookup"><span data-stu-id="ea534-186">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="ea534-187">其他信息</span><span class="sxs-lookup"><span data-stu-id="ea534-187">Additional information</span></span>

<span data-ttu-id="ea534-188">有关如何实现这些设置的技术指南, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="ea534-188">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="ea534-189">[设置 Office 365 组过期时间](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。</span><span class="sxs-lookup"><span data-stu-id="ea534-189">[Set up Office 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

-   <span data-ttu-id="ea534-190">[设置团队保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ea534-190">[Set up Teams retention policies](retention-policies.md).</span></span>

-   <span data-ttu-id="ea534-191">[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="ea534-191">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="ea534-192">团队功能管理</span><span class="sxs-lookup"><span data-stu-id="ea534-192">Teams feature management</span></span>

<span data-ttu-id="ea534-193">团队管理和生命周期管理的另一个重要方面是控制你的用户有权访问的功能的能力。</span><span class="sxs-lookup"><span data-stu-id="ea534-193">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="ea534-194">你可以在 Office 365 租户级别或按用户管理消息、会议和呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="ea534-194">You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ea534-196">决策点</span><span class="sxs-lookup"><span data-stu-id="ea534-196">Decision points</span></span>|<ul><li><span data-ttu-id="ea534-197">您的组织是否需要针对您的整个租户限制团队功能？</span><span class="sxs-lookup"><span data-stu-id="ea534-197">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="ea534-198">您的组织是否需要针对特定用户限制团队功能？</span><span class="sxs-lookup"><span data-stu-id="ea534-198">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="ea534-200">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea534-200">Next steps</span></span>|<ul><li><span data-ttu-id="ea534-201">记录组织在租户和用户级别限制团队功能的要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-201">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="ea534-202">计划在团队推出过程中实施特定要求。</span><span class="sxs-lookup"><span data-stu-id="ea534-202">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="ea534-203">传达和发布你的策略以通知团队用户他们所期望的行为。</span><span class="sxs-lookup"><span data-stu-id="ea534-203">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="ea534-204">团队功能管理重点领域</span><span class="sxs-lookup"><span data-stu-id="ea534-204">Teams feature management focus areas</span></span>

<span data-ttu-id="ea534-205">团队通过策略提供精确的功能, 用于控制消息、会议、通话和实时事件功能等。</span><span class="sxs-lookup"><span data-stu-id="ea534-205">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="ea534-206">默认情况下, 可根据组织的需要将不同的策略应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="ea534-206">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="ea534-207">有关所有设置的详细列表, 包括有关如何为你的组织实施它们的技术指南, 请参阅以下文章:</span><span class="sxs-lookup"><span data-stu-id="ea534-207">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

-   [<span data-ttu-id="ea534-208">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="ea534-208">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
-   [<span data-ttu-id="ea534-209">在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams</span><span class="sxs-lookup"><span data-stu-id="ea534-209">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
-   [<span data-ttu-id="ea534-210">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="ea534-210">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a><span data-ttu-id="ea534-211">安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="ea534-211">Security and compliance</span></span>

<span data-ttu-id="ea534-212">团队基于 Office 365 的高级安全和合规性功能构建, 并支持审核和报告、合规性内容搜索、电子发现、法律封存和保留策略。</span><span class="sxs-lookup"><span data-stu-id="ea534-212">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="ea534-213">如果您的组织具有合规性和安全要求, 请查看本文中提供的有关[Microsoft 团队安全性和合规性概述](security-compliance-overview.md)中的本主题的深入内容。</span><span class="sxs-lookup"><span data-stu-id="ea534-213">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
