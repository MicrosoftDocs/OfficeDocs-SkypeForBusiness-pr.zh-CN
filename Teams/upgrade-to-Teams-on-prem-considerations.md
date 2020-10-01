---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c359b39707b57a653f35e75497672d306209ccd
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328211"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="8d9b2-103">针对 IT 管理员在本地 Skype for business 服务器的组织的升级注意事项 &mdash;</span><span class="sxs-lookup"><span data-stu-id="8d9b2-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="8d9b2-104">本文介绍本地 Skype for business Server 的组织的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="8d9b2-105">本文是介绍 IT 管理员的升级概念和实现的第四个。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="8d9b2-106">概述</span><span class="sxs-lookup"><span data-stu-id="8d9b2-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="8d9b2-107">升级方法</span><span class="sxs-lookup"><span data-stu-id="8d9b2-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="8d9b2-108">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="8d9b2-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="8d9b2-109"> (本文) 的**具有 Skype For business 内部部署的组织的其他注意事项**</span><span class="sxs-lookup"><span data-stu-id="8d9b2-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="8d9b2-110">实施升级</span><span class="sxs-lookup"><span data-stu-id="8d9b2-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="8d9b2-111"> (PSTN) 注意事项的公共交换电话网络</span><span class="sxs-lookup"><span data-stu-id="8d9b2-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="8d9b2-112">此外，以下文章介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="8d9b2-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="8d9b2-113">团队和 Skype for business 的共存</span><span class="sxs-lookup"><span data-stu-id="8d9b2-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="8d9b2-114">共存模式-参考</span><span class="sxs-lookup"><span data-stu-id="8d9b2-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="8d9b2-115">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="8d9b2-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="8d9b2-116">适用于本地 Skype for business 服务器的组织的注意事项</span><span class="sxs-lookup"><span data-stu-id="8d9b2-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="8d9b2-117">设置 Skype for business 混合是迁移到 TeamsOnly 模式的先决条件。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="8d9b2-118">虽然在不带混合的孤岛模式下可以使用团队，但在用户从本地 Skype for business Online (移动到 Skype for business Online 时，无法进行切换，直到使用 [move-csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="8d9b2-119">有关详细信息，请参阅 [配置混合连接](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="8d9b2-120">如果你的组织具有 Skype for business 服务器，但尚未配置混合连接，但你仍希望使用团队来管理团队功能，则必须使用具有 onmicrosoft.com 域的管理帐户。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="8d9b2-121">具有本地 Skype for Business 帐户的团队用户 (也就是说，他们尚未使用移动 Move-csuser) 移动到云，无法与任何 Skype for Business 用户进行互操作，也不能与外部用户联盟。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="8d9b2-122">此功能仅在用户被移动到云 (在 "孤岛" 模式下或 TeamsOnly 用户) 时才可用。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="8d9b2-123">如果你拥有本地 Skype for Business 帐户的任何用户，则无法在租户级别分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="8d9b2-124">必须先使用本地 Skype for Business 帐户将所有用户移到云 `Move-CsUser` ，然后 [禁用混合才能完成到云的迁移](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="8d9b2-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` 如果检测到的 lyncdiscover DNS 记录指向非 Office 365 的位置，则不会在租户级别工作。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="8d9b2-126">你必须确保你的用户与正确的 Skype for Business 属性正确同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="8d9b2-127">这些属性都是带有 "msRTCSIP-" 的所有前缀。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="8d9b2-128">如果用户未正确地与 Azure AD 同步，团队中的管理工具将无法管理这些用户。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="8d9b2-129"> (例如，你将无法向本地用户分配团队策略，除非你正确同步这些属性。 ) 有关详细信息，请参阅 [配置团队和 Skype for business 的 AZURE AD 连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="8d9b2-130">若要在混合组织中创建新的 TeamsOnly 或 Skype for business Online 用户， *必须先在本地 Skype for Business Server 中启用用户*，然后使用 move-csuser 将用户从本地移动到云。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="8d9b2-131">首先在本地创建用户可确保其他任何其他本地 Skype for business 用户能够路由到新创建的用户。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="8d9b2-132">在所有用户都已联机移动后，不再需要先在本地启用用户。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="8d9b2-133">当用户从本地移动到云时，按该用户组织的会议将迁移到 Skype for business Online 或团队中，具体取决于是否指定了-MoveToTeams 开关。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="8d9b2-134">如果你想要在本地用户的 Skype for Business 客户端中显示通知，则必须在本地工具集中使用 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="8d9b2-135">仅 NotifySfbUsers 参数对于本地用户是相关的。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="8d9b2-136">本地用户从 TeamsUpgradePolicy 的联机实例接收其模式。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="8d9b2-137">请参阅 [授权 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中的备注。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="8d9b2-138">2019在年9月3日之后创建的任何新租户均创建为 TeamsOnly 租户，除非该组织已有 Skype for Business Server 的内部部署。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="8d9b2-139">Microsoft 使用 DNS 记录来标识本地 Skype for Business 服务器组织。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="8d9b2-140">如果您的组织具有本地 Skype for Business 服务器，但没有公共 DNS 条目，则您需要致电 Microsoft 支持部门以使新租户降级。</span><span class="sxs-lookup"><span data-stu-id="8d9b2-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="8d9b2-141">相关链接</span><span class="sxs-lookup"><span data-stu-id="8d9b2-141">Related links</span></span>

[<span data-ttu-id="8d9b2-142">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="8d9b2-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="8d9b2-143">配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="8d9b2-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="8d9b2-144">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="8d9b2-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="8d9b2-145">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="8d9b2-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="8d9b2-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="8d9b2-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="8d9b2-147">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="8d9b2-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

