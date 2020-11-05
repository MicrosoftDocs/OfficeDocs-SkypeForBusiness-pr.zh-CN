---
title: 在 Microsoft Teams 中授权来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
ms.openlocfilehash: 1040d548140d0fbb781e9cc9296be3d374b7b314
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48918984"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="65548-103">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="65548-103">Authorize guest access in Microsoft Teams</span></span>

<span data-ttu-id="65548-104">为了满足组织的要求，您可以通过四种不同的授权级别管理团队来宾访问功能和功能。</span><span class="sxs-lookup"><span data-stu-id="65548-104">To satisfy your organization's requirements, you can manage Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="65548-105">所有授权级别均适用于您的 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="65548-105">All the authorization levels apply to your Microsoft 365 organization.</span></span> <span data-ttu-id="65548-106">每个授权级别按如下所示控制来宾体验：</span><span class="sxs-lookup"><span data-stu-id="65548-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="65548-107">**Azure Active Directory** ：团队中的来宾访问依赖于 Azure AD 企业到企业 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="65548-107">**Azure Active Directory** : Guest access in Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="65548-108">此授权级别控制目录、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="65548-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="65548-109">**团队** ：仅在团队中控制来宾体验。</span><span class="sxs-lookup"><span data-stu-id="65548-109">**Teams** : Controls the guest experience in Teams only.</span></span>
- <span data-ttu-id="65548-110">**Microsoft 365 组** ：控制 Microsoft 365 组和团队中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="65548-110">**Microsoft 365 Groups** : Controls the guest experience in Microsoft 365 Groups and Teams.</span></span>
- <span data-ttu-id="65548-111">**Sharepoint 和 onedrive** ：控制 SharePoint、OneDrive、Microsoft 365 组和团队中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="65548-111">**SharePoint and OneDrive** : Controls the guest experience in SharePoint, OneDrive, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="65548-112">这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。</span><span class="sxs-lookup"><span data-stu-id="65548-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="65548-113">例如，如果你不想允许团队中的来宾用户，但想要允许组织在你的组织中整体，只需关闭团队中的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="65548-113">For example, if you don't want to allow guest users in Teams but want to allow it overall in your organization, just turn off guest access in Teams.</span></span> <span data-ttu-id="65548-114">另一个示例：您可以在 Azure AD、团队和组级别启用来宾访问，但随后 [禁用与一个或多个条件匹配的选定团队的来宾用户，如数据分类等于机密](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="65548-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then [disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="65548-115">SharePoint 和 OneDrive 具有自己的不依赖于 Microsoft 365 组的来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="65548-115">SharePoint and OneDrive have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

<span data-ttu-id="65548-116">有关端到端来宾访问配置说明，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="65548-116">For end-to-end guest access configuration instructions, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

> [!NOTE]
> <span data-ttu-id="65548-117">来宾应遵守 [Microsoft 365 和 Office 365 服务说明](https://go.microsoft.com/fwlink/p/?linkid=282347)和 [Azure AD B2B 协作限制](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)中描述的服务限制。</span><span class="sxs-lookup"><span data-stu-id="65548-117">Guests are subject to the service limits described in [Microsoft 365 and Office 365 service descriptions](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Limitations of Azure AD B2B collaboration](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations).</span></span> 

<span data-ttu-id="65548-118">下图显示了如何在 Azure Active Directory、团队和 Microsoft 365 之间授予和集成来宾访问授权相关性。</span><span class="sxs-lookup"><span data-stu-id="65548-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Teams, and Microsoft 365.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="65548-119">![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)</span><span class="sxs-lookup"><span data-stu-id="65548-119">![Diagram of authorization dependencies for guest access.](media/teams_dependencies_image1.png)</span></span>

<span data-ttu-id="65548-120">下一张示意图概括性地显示了用户体验如何通过典型的来宾访问邀请和兑换流程与权限模型结合使用。</span><span class="sxs-lookup"><span data-stu-id="65548-120">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="65548-121">![显示邀请和兑换流程的示意图](media/authorize-guest-image1.png)</span><span class="sxs-lookup"><span data-stu-id="65548-121">![Diagram of invitation and redemption flows](media/authorize-guest-image1.png)</span></span>

<span data-ttu-id="65548-122">请务必注意，应用、bot 和连接器可能需要自己的一组特定于用户帐户的权限和/或同意。</span><span class="sxs-lookup"><span data-stu-id="65548-122">It's important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="65548-123">这些可能需要单独授予。</span><span class="sxs-lookup"><span data-stu-id="65548-123">These might need to be granted separately.</span></span> <span data-ttu-id="65548-124">同样，SharePoint 可能针对特定用户、用户组，甚至在站点级别设置了额外的外部共享界限。</span><span class="sxs-lookup"><span data-stu-id="65548-124">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="65548-125">上两张示意图还可在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中查看。</span><span class="sxs-lookup"><span data-stu-id="65548-125">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="65548-126">控制 Azure Active Directory 中的条件访问</span><span class="sxs-lookup"><span data-stu-id="65548-126">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="65548-127">使用 Azure AD 来确定外部协作者能否受邀以来宾的身份加入你的租户以及如何加入。</span><span class="sxs-lookup"><span data-stu-id="65548-127">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="65548-128">有关 Azure B2B 来宾访问的详细信息，请参阅[什么是 Azure Active Directory B2B 中的来宾用户访问权限](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="65548-128">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="65548-129">要了解 Azure AD 角色，请参阅[在 Azure Active Directory 租户中向来自合作伙伴组织的用户授予权限](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。</span><span class="sxs-lookup"><span data-stu-id="65548-129">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="65548-130">邀请的设置适用于组织级别，并控制目录和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="65548-130">The settings for invitations apply at the organization level and control the guest experience at the directory and application level.</span></span> <span data-ttu-id="65548-131">可以在 [外部协作设置](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)中配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="65548-131">You can configure these settings in [External collaboration settings](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).</span></span>

<span data-ttu-id="65548-132">Azure AD 包含用于配置外部用户的以下设置：</span><span class="sxs-lookup"><span data-stu-id="65548-132">Azure AD includes the following settings to configure external users:</span></span>

- [<span data-ttu-id="65548-133">来宾用户访问限制</span><span class="sxs-lookup"><span data-stu-id="65548-133">Guest user access restrictions</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- <span data-ttu-id="65548-134">**管理员和具有“来宾邀请者”角色的用户可以邀请** ：“ **是** ”表示管理员和具有“来宾邀请者”角色的用户将能够邀请来宾加入租户。</span><span class="sxs-lookup"><span data-stu-id="65548-134">**Admins and users in the guest inviter role can invite** : **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="65548-135">“ **否** ”表示管理员和用户不可邀请来宾加入租户。</span><span class="sxs-lookup"><span data-stu-id="65548-135">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="65548-136">**成员可邀请** ：要允许目录的非管理员成员邀请来宾，请将此策略设置为 **是** （建议设置）。</span><span class="sxs-lookup"><span data-stu-id="65548-136">**Members can invite** : To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="65548-137">如果你希望仅管理员能够添加来宾，可以将此策略设置为 **否** 。</span><span class="sxs-lookup"><span data-stu-id="65548-137">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="65548-138">请记住，设置为 **否** 将会限制非管理员团队所有者的来宾体验；他们只能向管理员已在 AAD 中添加的团队添加来宾。</span><span class="sxs-lookup"><span data-stu-id="65548-138">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="65548-139">**来宾可邀请** ：“ **是** ”表示目录中的来宾可邀请其他来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="65548-139">**Guests can invite** : **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="65548-140">“ **否** ”表示来宾不可邀请其他来宾与你的组织协作。</span><span class="sxs-lookup"><span data-stu-id="65548-140">**No** means that guests can't invite other guests to collaborate with your organization.</span></span> <span data-ttu-id="65548-141">即使设置为 **"是"** ，来宾也无法邀请团队中的其他来宾。</span><span class="sxs-lookup"><span data-stu-id="65548-141">Even if set to **Yes** , guest cannot invite other guests in Teams.</span></span>
 
<span data-ttu-id="65548-142">有关控制哪些人可以邀请来宾的详细信息，请参阅 [启用 B2B 外部协作和管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="65548-142">For more information about controlling who can invite guests, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="65548-143">还可管理可以来宾身份邀请哪些域加入你的租户。</span><span class="sxs-lookup"><span data-stu-id="65548-143">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="65548-144">请参阅 [允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="65548-144">See [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).</span></span>

<span data-ttu-id="65548-145">无需将用户来宾帐户手动添加到 Azure AD B2B 中，因为在你向 Teams 添加来宾时，该帐户将自动添加到目录中。</span><span class="sxs-lookup"><span data-stu-id="65548-145">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="65548-146">来宾访问的许可</span><span class="sxs-lookup"><span data-stu-id="65548-146">Licensing for guest access</span></span>

<span data-ttu-id="65548-147">来宾访问许可使用 Azure AD 外部标识定价，并且基于每月活动来宾。</span><span class="sxs-lookup"><span data-stu-id="65548-147">Guest access licensing uses Azure AD External Identities pricing and is based on monthly active guests.</span></span> <span data-ttu-id="65548-148">有关详细信息，请参阅 [AZURE AD 外部标识的计费模型](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 。</span><span class="sxs-lookup"><span data-stu-id="65548-148">See [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) for details.</span></span>

> [!NOTE]
> <span data-ttu-id="65548-149">你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。</span><span class="sxs-lookup"><span data-stu-id="65548-149">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="65548-150">要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="65548-150">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="65548-151">外部访问（联合身份验证）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="65548-151">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="65548-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="65548-152">Related topics</span></span>

- [<span data-ttu-id="65548-153">Microsoft 365 来宾共享设置参考</span><span class="sxs-lookup"><span data-stu-id="65548-153">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[<span data-ttu-id="65548-154">与 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="65548-154">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
