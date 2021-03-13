---
title: 在 Teams 中规划管理 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 本文将了解如何规划在 Teams 中实现治理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e51b85e7ecf8efc61c6ca78ca16e4366372885
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756228"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="11c4c-103">在 Teams 中规划管理</span><span class="sxs-lookup"><span data-stu-id="11c4c-103">Plan for governance in Teams</span></span>

<span data-ttu-id="11c4c-104">Teams 提供了一组丰富的工具，用于实现组织可能需要的任何管理功能。</span><span class="sxs-lookup"><span data-stu-id="11c4c-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="11c4c-105">本文指导 IT 专业人员提出正确的问题，以确定其监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="11c4c-106">观看以下会话，详细了解 Microsoft Teams 中的治理[：Microsoft Teams](https://aka.ms/teams-governance)中的治理、管理和生命周期</span><span class="sxs-lookup"><span data-stu-id="11c4c-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="11c4c-107">组和团队创建、命名、分类和来宾访问</span><span class="sxs-lookup"><span data-stu-id="11c4c-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="11c4c-108">组织可能要求对团队的命名和分类方式、来宾是否可以添加为团队成员以及可以创建团队的严格控制。</span><span class="sxs-lookup"><span data-stu-id="11c4c-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="11c4c-109">可以使用 Azure Active Directory 和 Azure AD (和敏感度) 配置这些区域。</span><span class="sxs-lookup"><span data-stu-id="11c4c-109">You can configure these areas by using Azure Active Directory (Azure AD) and sensitivity labels.</span></span> 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="11c4c-110">决策点</span><span class="sxs-lookup"><span data-stu-id="11c4c-110">Decision points</span></span>|<ul><li><span data-ttu-id="11c4c-111">组织是否需要团队的特定命名约定？</span><span class="sxs-lookup"><span data-stu-id="11c4c-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="11c4c-112">团队创建者是否需要能够将组织特定的分类分配给团队？</span><span class="sxs-lookup"><span data-stu-id="11c4c-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="11c4c-113">是否需要限制按团队将来宾添加到团队的能力？</span><span class="sxs-lookup"><span data-stu-id="11c4c-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="11c4c-114">组织是否需要限制可以创建团队的人？</span><span class="sxs-lookup"><span data-stu-id="11c4c-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="11c4c-115">后续步骤</span><span class="sxs-lookup"><span data-stu-id="11c4c-115">Next steps</span></span>|<ul><li><span data-ttu-id="11c4c-116">记录组织对团队创建、命名、分类和来宾访问的要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="11c4c-117">计划在 Teams 推出过程中实施这些要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="11c4c-118">沟通并发布策略，告知 Teams 用户他们预期的行为。</span><span class="sxs-lookup"><span data-stu-id="11c4c-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!NOTE]
> <span data-ttu-id="11c4c-119">为帮助你提前规划， [请详细了解如何设置这些策略及其需要哪些许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="11c4c-119">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="11c4c-120">限制组和团队创建可能会降低用户的工作效率，因为许多 Microsoft 365 和 Office 365 服务要求创建组才能让服务正常工作。</span><span class="sxs-lookup"><span data-stu-id="11c4c-120">Limiting group and team creation can slow your users’ productivity, because many Microsoft 365 and Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="11c4c-121">有关其他信息，请导航到 并展开["为什么控制谁创建 Microsoft 365 组"。](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)</span><span class="sxs-lookup"><span data-stu-id="11c4c-121">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="11c4c-122">其他信息</span><span class="sxs-lookup"><span data-stu-id="11c4c-122">Additional information</span></span>

<span data-ttu-id="11c4c-123">确定要求后，可以使用 Azure AD 控件实现它们。</span><span class="sxs-lookup"><span data-stu-id="11c4c-123">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="11c4c-124">有关如何实现这些设置的技术指南，请参阅：</span><span class="sxs-lookup"><span data-stu-id="11c4c-124">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="11c4c-125">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="11c4c-125">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [<span data-ttu-id="11c4c-126">对 Azure Active Directory 中的 Microsoft 365 组强制实施命名策略</span><span class="sxs-lookup"><span data-stu-id="11c4c-126">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [<span data-ttu-id="11c4c-127">Microsoft 365 组命名策略</span><span class="sxs-lookup"><span data-stu-id="11c4c-127">Microsoft 365 Groups naming policy</span></span>](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [<span data-ttu-id="11c4c-128">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="11c4c-128">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [<span data-ttu-id="11c4c-129">组、团队和 Yammer 的生命周期结束选项</span><span class="sxs-lookup"><span data-stu-id="11c4c-129">End of lifecycle options for groups, teams, and Yammer</span></span>](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="11c4c-130">组和团队过期、保留和存档</span><span class="sxs-lookup"><span data-stu-id="11c4c-130">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="11c4c-131">组织可能还需要设置过期、保留和存档团队的策略，以及将团队数据 (频道消息和频道) 。</span><span class="sxs-lookup"><span data-stu-id="11c4c-131">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="11c4c-132">可以将组过期策略配置为自动管理组的生命周期和保留策略以根据需要保留或删除信息，也可以存档团队 (将其设置为只读模式) 以保留不再处于活动状态的团队的时间点视图。</span><span class="sxs-lookup"><span data-stu-id="11c4c-132">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span> <span data-ttu-id="11c4c-133">请注意，存档的团队将继续应用过期策略，除非排除或续订，否则可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="11c4c-133">Note that teams that are archived continue to have the expiration policy applied and may be deleted unless excluded or renewed.</span></span>

|-          |-           |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="11c4c-135">决策点</span><span class="sxs-lookup"><span data-stu-id="11c4c-135">Decision points</span></span>|<ul><li><span data-ttu-id="11c4c-136">组织是否需要为团队指定到期日期？</span><span class="sxs-lookup"><span data-stu-id="11c4c-136">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="11c4c-137">组织是否需要对团队应用特定的数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="11c4c-137">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="11c4c-138">您的组织是否期望能够存档非活动团队，以将内容保留为只读状态？</span><span class="sxs-lookup"><span data-stu-id="11c4c-138">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="11c4c-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="11c4c-140">Next steps</span></span>|<ul><li><span data-ttu-id="11c4c-141">记录组织对团队过期、数据保留和存档的要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-141">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="11c4c-142">计划在 Teams 推出过程中实施这些要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-142">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="11c4c-143">沟通并发布策略，告知 Teams 用户他们预期的行为。</span><span class="sxs-lookup"><span data-stu-id="11c4c-143">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="11c4c-144">使用下表捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-144">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="11c4c-145">功能</span><span class="sxs-lookup"><span data-stu-id="11c4c-145">Capability</span></span> |<span data-ttu-id="11c4c-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="11c4c-146">Details</span></span> |<span data-ttu-id="11c4c-147">需要 Azure AD Premium 许可证</span><span class="sxs-lookup"><span data-stu-id="11c4c-147">Azure AD Premium license required</span></span> |<span data-ttu-id="11c4c-148">决定</span><span class="sxs-lookup"><span data-stu-id="11c4c-148">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="11c4c-149">过期策略</span><span class="sxs-lookup"><span data-stu-id="11c4c-149">Expiration policy</span></span> |<span data-ttu-id="11c4c-150">通过设置过期策略来管理 Microsoft 365 组的生命周期。</span><span class="sxs-lookup"><span data-stu-id="11c4c-150">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="11c4c-151">P1</span><span class="sxs-lookup"><span data-stu-id="11c4c-151">P1</span></span> |<span data-ttu-id="11c4c-152">TBD</span><span class="sxs-lookup"><span data-stu-id="11c4c-152">TBD</span></span>|
|<span data-ttu-id="11c4c-153">保留策略</span><span class="sxs-lookup"><span data-stu-id="11c4c-153">Retention policy</span></span> |<span data-ttu-id="11c4c-154">在安全与合规中心为 Teams 设置保留策略，保留&删除数据。</span><span class="sxs-lookup"><span data-stu-id="11c4c-154">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="11c4c-155">**注意**：使用此功能需要获得 Microsoft 365 或 Office 365 企业版 E3 或以上版的许可。</span><span class="sxs-lookup"><span data-stu-id="11c4c-155">**Note**: Using this feature requires licensing of Microsoft 365 or Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="11c4c-156">否</span><span class="sxs-lookup"><span data-stu-id="11c4c-156">No</span></span> |<span data-ttu-id="11c4c-157">TBD</span><span class="sxs-lookup"><span data-stu-id="11c4c-157">TBD</span></span> |
|<span data-ttu-id="11c4c-158">存档和还原</span><span class="sxs-lookup"><span data-stu-id="11c4c-158">Archive and restore</span></span> |<span data-ttu-id="11c4c-159">当团队不再处于活动状态，但你想要保留该团队供参考或将来重新激活时，请将其存档。</span><span class="sxs-lookup"><span data-stu-id="11c4c-159">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="11c4c-160">否</span><span class="sxs-lookup"><span data-stu-id="11c4c-160">No</span></span> |<span data-ttu-id="11c4c-161">TBD</span><span class="sxs-lookup"><span data-stu-id="11c4c-161">TBD</span></span> |

> [!Note]
> <span data-ttu-id="11c4c-162">组过期是一项 Azure AD Premium 功能。</span><span class="sxs-lookup"><span data-stu-id="11c4c-162">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="11c4c-163">若要提供此功能，租户必须具有 Azure AD Premium 订阅，以及配置设置和受影响组成员的管理员的许可证。</span><span class="sxs-lookup"><span data-stu-id="11c4c-163">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="11c4c-164">其他信息</span><span class="sxs-lookup"><span data-stu-id="11c4c-164">Additional information</span></span>

<span data-ttu-id="11c4c-165">有关如何实现这些设置的技术指南，请参阅：</span><span class="sxs-lookup"><span data-stu-id="11c4c-165">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="11c4c-166">[设置 Microsoft 365 组过期 。](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)</span><span class="sxs-lookup"><span data-stu-id="11c4c-166">[Set up Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="11c4c-167">[设置 Teams 保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="11c4c-167">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="11c4c-168">[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="11c4c-168">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>

## <a name="group-and-team-membership-management"></a><span data-ttu-id="11c4c-169">组和团队成员身份管理</span><span class="sxs-lookup"><span data-stu-id="11c4c-169">Group and team membership management</span></span>

<span data-ttu-id="11c4c-170">对于需要快速载入和下载或用户和来宾的团队来说，必须一致地管理基于项目的成员或受限组的成员。</span><span class="sxs-lookup"><span data-stu-id="11c4c-170">Consistently managing members of project based, or restricted groups are necessary for teams that require rapid onboarding and offboarding or users and guests.</span></span> <span data-ttu-id="11c4c-171">您的组织可能还需要确保所有当前成员都有在团队中的业务理由。</span><span class="sxs-lookup"><span data-stu-id="11c4c-171">Your organization may also need to make sure all current members have the business justification to be in a team.</span></span> <span data-ttu-id="11c4c-172">管理成员可能比较困难，因为团队所有者可以离开，并且用户在项目结束时或更改角色时通常不会自行离开组。</span><span class="sxs-lookup"><span data-stu-id="11c4c-172">Managing members can be hard because team owners can leave and users don’t usually leave groups on their own accord when a project ends or when they change roles.</span></span> <span data-ttu-id="11c4c-173">管理组成员身份（允许用户根据需要获取访问权限，但确保组没有不当访问风险）最好的方法是通过两个区域流程：权利管理和访问评审。</span><span class="sxs-lookup"><span data-stu-id="11c4c-173">The best way to manage group membership that allows users to get access when needed but ensure the group doesn't have a risk of inappropriate access is through two district processes: entitlement management and access reviews.</span></span>

<span data-ttu-id="11c4c-174">[权利](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 管理允许您委派给项目经理等人员，以将所需的所有资源（包括团队成员身份）收集到单个包中。</span><span class="sxs-lookup"><span data-stu-id="11c4c-174">[Entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) allows you to delegate to someone, such as a project manager, to collect all the resources that are needed, including teams memberships, into a single package.</span></span> <span data-ttu-id="11c4c-175">他们还可以定义谁可以提出请求：租户中的用户或其他连接的组织的用户。</span><span class="sxs-lookup"><span data-stu-id="11c4c-175">They can also define who can make requests: either users in your tenant or from other connected organizations.</span></span> <span data-ttu-id="11c4c-176">项目经理将在电子邮件中收到访问请求，在 MyAccess 门户中批准或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-176">The project manager will receive access requests in their email and approve or deny requests in the MyAccess portal.</span></span> <span data-ttu-id="11c4c-177">管理员可以配置访问条件，以包括过期日期或期限，除非续订访问权限，否则将用户或来宾从团队中删除。</span><span class="sxs-lookup"><span data-stu-id="11c4c-177">Administrators can configure the conditions of access to include an expiry date or period by when the user or guest will be removed from the team unless access is renewed.</span></span> <span data-ttu-id="11c4c-178">管理员还可以设置与团队关联的组，以参与访问评审。</span><span class="sxs-lookup"><span data-stu-id="11c4c-178">Administrators can also set up the groups associated with teams to take part in access reviews.</span></span> <span data-ttu-id="11c4c-179">对于 [访问评审](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)，组所有者将收到定期提醒，提醒他们审阅团队成员。</span><span class="sxs-lookup"><span data-stu-id="11c4c-179">For [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), the group owners will receive regular reminders to review the members of a team.</span></span> <span data-ttu-id="11c4c-180">访问评审包括建议，使组所有者可以更轻松地完成其常规证明过程。</span><span class="sxs-lookup"><span data-stu-id="11c4c-180">Access reviews include recommendations, which makes it easier for group owners to go through their regular attestation process.</span></span>

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | <span data-ttu-id="11c4c-181">决策点</span><span class="sxs-lookup"><span data-stu-id="11c4c-181">Decision points</span></span> | <span data-ttu-id="11c4c-182">组织是否需要一致的流程来管理一个或多个团队的成员身份？</span><span class="sxs-lookup"><span data-stu-id="11c4c-182">Does your organization require a consistent process for managing membership of one or more teams?</span></span> <br> <span data-ttu-id="11c4c-183">组织是否需要所有者或成员本身定期证明他们持续成为一个或多个团队的成员身份的理由？</span><span class="sxs-lookup"><span data-stu-id="11c4c-183">Does your organization require owners, or the members themselves, to justify their continued membership of one or more teams on a regular basis?</span></span> <br> <span data-ttu-id="11c4c-184">您的组织是否需要审批用户和来宾来请求访问团队、组、SharePoint 网站和应用等资源？</span><span class="sxs-lookup"><span data-stu-id="11c4c-184">Does your organization require approval for users and guests to request access to resources including teams, groups, SharePoint sites, and apps?</span></span> |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| <span data-ttu-id="11c4c-185">下一步？</span><span class="sxs-lookup"><span data-stu-id="11c4c-185">Next steps?</span></span> | <span data-ttu-id="11c4c-186">记录每个团队或特定团队的成员资格到期的组织要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-186">Document your organizations requirements for each team or specific teams for membership expiry.</span></span><br><span data-ttu-id="11c4c-187">规划组织如何在访问包中将团队、组、SharePoint 网站和应用捆绑在一起。</span><span class="sxs-lookup"><span data-stu-id="11c4c-187">Plan how your organization can bundle teams, groups, SharePoint sites, and apps together in access packages.</span></span><br><span data-ttu-id="11c4c-188">规划哪些人员（例如请求者经理、项目经理、已连接组织的发起人或组织中安全主管）需要批准或拒绝访问请求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-188">Plan which people, such as the requestor's manager, a project manager, a sponsor for a connected organization or a security officer in your organization will need to approve or deny access requests.</span></span> |

> [!TIP]
> <span data-ttu-id="11c4c-189">使用下表捕获组织的要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-189">Use the following table to capture your organization’s requirements.</span></span>

| <span data-ttu-id="11c4c-190">功能</span><span class="sxs-lookup"><span data-stu-id="11c4c-190">Capability</span></span> | <span data-ttu-id="11c4c-191">详细信息</span><span class="sxs-lookup"><span data-stu-id="11c4c-191">Details</span></span> | <span data-ttu-id="11c4c-192">需要 Azure AD Premium 许可证</span><span class="sxs-lookup"><span data-stu-id="11c4c-192">Azure AD Premium license required</span></span> | <span data-ttu-id="11c4c-193">决定</span><span class="sxs-lookup"><span data-stu-id="11c4c-193">Decision</span></span> |
|:-|:-|:-|:-|
| <span data-ttu-id="11c4c-194">访问评审</span><span class="sxs-lookup"><span data-stu-id="11c4c-194">Access reviews</span></span> | <span data-ttu-id="11c4c-195">设置访问评审，定期重新认证特定团队的成员身份</span><span class="sxs-lookup"><span data-stu-id="11c4c-195">Setup access reviews to recertify the membership of specific teams at regular interval</span></span> | <span data-ttu-id="11c4c-196">P2</span><span class="sxs-lookup"><span data-stu-id="11c4c-196">P2</span></span> | <span data-ttu-id="11c4c-197">TBD</span><span class="sxs-lookup"><span data-stu-id="11c4c-197">TBD</span></span> |
| <span data-ttu-id="11c4c-198">权利管理</span><span class="sxs-lookup"><span data-stu-id="11c4c-198">Entitlement management</span></span> | <span data-ttu-id="11c4c-199">设置访问包以允许用户和来宾请求访问团队</span><span class="sxs-lookup"><span data-stu-id="11c4c-199">Setup access package to allow users and guests to request access to teams</span></span> | <span data-ttu-id="11c4c-200">P2</span><span class="sxs-lookup"><span data-stu-id="11c4c-200">P2</span></span> | <span data-ttu-id="11c4c-201">TBD</span><span class="sxs-lookup"><span data-stu-id="11c4c-201">TBD</span></span> |

> [!NOTE]
> <span data-ttu-id="11c4c-202">为帮助你提前规划 [，请详细了解他们需要哪些许可证](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="11c4c-202">To help you plan ahead, [learn more about what licenses they require](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="additional-information"></a><span data-ttu-id="11c4c-203">其他信息</span><span class="sxs-lookup"><span data-stu-id="11c4c-203">Additional information</span></span>

<span data-ttu-id="11c4c-204">有关如何实现这些设置的技术指南，请参阅：</span><span class="sxs-lookup"><span data-stu-id="11c4c-204">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="11c4c-205">权利管理</span><span class="sxs-lookup"><span data-stu-id="11c4c-205">Entitlement management</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [<span data-ttu-id="11c4c-206">访问评审</span><span class="sxs-lookup"><span data-stu-id="11c4c-206">Access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a><span data-ttu-id="11c4c-207">Teams 功能管理</span><span class="sxs-lookup"><span data-stu-id="11c4c-207">Teams feature management</span></span>

<span data-ttu-id="11c4c-208">Teams 治理和生命周期管理的另一个重要方面是能够控制用户有权访问的功能。</span><span class="sxs-lookup"><span data-stu-id="11c4c-208">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="11c4c-209">可在 Microsoft 365 或 Office 365 组织级别或每个用户管理消息传递、会议以及呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="11c4c-209">You can manage messaging, meeting, and calling features, either at the Microsoft 365 or Office 365 organization level or per-user.</span></span>


|-        |-        |
|---------|---------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="11c4c-211">决策点</span><span class="sxs-lookup"><span data-stu-id="11c4c-211">Decision points</span></span>|<ul><li><span data-ttu-id="11c4c-212">组织是否需要限制整个租户的 Teams 功能？</span><span class="sxs-lookup"><span data-stu-id="11c4c-212">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="11c4c-213">组织是否需要限制特定用户的 Teams 功能？</span><span class="sxs-lookup"><span data-stu-id="11c4c-213">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="11c4c-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="11c4c-215">Next steps</span></span>|<ul><li><span data-ttu-id="11c4c-216">记录组织在租户和用户级别限制 Teams 功能的要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-216">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="11c4c-217">计划在 Teams 推出过程中实现特定要求。</span><span class="sxs-lookup"><span data-stu-id="11c4c-217">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="11c4c-218">沟通并发布策略，告知 Teams 用户他们预期的行为。</span><span class="sxs-lookup"><span data-stu-id="11c4c-218">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="11c4c-219">Teams 功能管理重点区域</span><span class="sxs-lookup"><span data-stu-id="11c4c-219">Teams feature management focus areas</span></span>

<span data-ttu-id="11c4c-220">Teams 通过策略提供精细的功能来控制消息传递、会议、通话和实时事件功能等。</span><span class="sxs-lookup"><span data-stu-id="11c4c-220">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="11c4c-221">默认情况下，可以按组织要求将不同的策略应用到所有用户或按用户应用。</span><span class="sxs-lookup"><span data-stu-id="11c4c-221">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="11c4c-222">有关所有设置的详细列表，包括有关如何为组织实施这些设置的技术指南，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="11c4c-222">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="11c4c-223">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="11c4c-223">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="11c4c-224">在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams</span><span class="sxs-lookup"><span data-stu-id="11c4c-224">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="11c4c-225">Microsoft Teams 中的私人频道</span><span class="sxs-lookup"><span data-stu-id="11c4c-225">Private channels in Microsoft Teams</span></span>](private-channels.md)
- [<span data-ttu-id="11c4c-226">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="11c4c-226">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="11c4c-227">在 Teams 中管理消息传递策略</span><span class="sxs-lookup"><span data-stu-id="11c4c-227">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
- [<span data-ttu-id="11c4c-228">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="11c4c-228">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)

<span data-ttu-id="11c4c-229">此外，您可以为频道设置审查，并授予特定用户的审查方功能，以便他们可以控制谁可以创建频道帖子并回复他们。</span><span class="sxs-lookup"><span data-stu-id="11c4c-229">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="11c4c-230">有关详细信息 [，请参阅在 Microsoft Teams 中](manage-channel-moderation-in-teams.md) 设置和管理频道审核。</span><span class="sxs-lookup"><span data-stu-id="11c4c-230">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="11c4c-231">安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="11c4c-231">Security and compliance</span></span>

<span data-ttu-id="11c4c-232">Teams 基于 Microsoft 365 和 Office 365 的高级安全性和符合性功能构建，支持审核和报告、符合性内容搜索、电子发现、法定保留和保留策略。</span><span class="sxs-lookup"><span data-stu-id="11c4c-232">Teams is built on the advanced security and compliance capabilities of Microsoft 365 and Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span>

> [!Important]
> <span data-ttu-id="11c4c-233">如果你的组织有合规性和安全性要求，请查看 Microsoft Teams 中的安全性和符合性概述一文中提供的有关此主题 [的深入内容](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="11c4c-233">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="11c4c-234">相关主题</span><span class="sxs-lookup"><span data-stu-id="11c4c-234">Related topics</span></span>

[<span data-ttu-id="11c4c-235">Teams 的管控快速入门</span><span class="sxs-lookup"><span data-stu-id="11c4c-235">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)

[<span data-ttu-id="11c4c-236">Microsoft 365 安全与合规&指南</span><span class="sxs-lookup"><span data-stu-id="11c4c-236">Microsoft 365 licensing guidance for security & compliance</span></span>](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
