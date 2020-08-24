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
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6bf763caf0b44490ee578f0bf130a1d4db56a3b
ms.sourcegitcommit: 294b32fb06c56a6eefd1cc44cc5bc93555b6503b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845564"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="e5db0-103">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="e5db0-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="e5db0-104">为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="e5db0-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="e5db0-105">所有这些授权级别都将应用于你的 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="e5db0-105">All the authorization levels apply to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="e5db0-106">每个授权级别按如下所示控制来宾体验：</span><span class="sxs-lookup"><span data-stu-id="e5db0-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="e5db0-107">**Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="e5db0-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="e5db0-108">此授权级别控制目录、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="e5db0-109">**Microsoft Teams**：仅控制 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="e5db0-110">**Microsoft 365 组**：控制 Microsoft 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-110">**Microsoft 365 Groups**: Controls the guest experience in Microsoft 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="e5db0-111">**SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Microsoft 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Microsoft 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="e5db0-112">这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。</span><span class="sxs-lookup"><span data-stu-id="e5db0-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="e5db0-113">例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，但想在组织中全面允许，只需在 Microsoft Teams 中关闭来宾访问即可。</span><span class="sxs-lookup"><span data-stu-id="e5db0-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="e5db0-114">其他示例：你可以在 Azure AD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。</span><span class="sxs-lookup"><span data-stu-id="e5db0-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="e5db0-115">SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Microsoft 365 组的来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="e5db0-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="e5db0-116">来宾应遵守 [Microsoft 365 和 Office 365 服务说明](https://go.microsoft.com/fwlink/p/?linkid=282347)和 [Azure AD B2B 协作限制](https://go.microsoft.com/fwlink/p/?linkid=853019)中描述的服务限制。</span><span class="sxs-lookup"><span data-stu-id="e5db0-116">Guests are subject to the service limits described in [Microsoft 365 and Office 365 service descriptions](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Limitations of Azure AD B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=853019).</span></span> 

<span data-ttu-id="e5db0-117">下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Microsoft 365 或 Office 365 之间集成来宾访问授权相关性。</span><span class="sxs-lookup"><span data-stu-id="e5db0-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Microsoft 365 or Office 365.</span></span>

![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)

<span data-ttu-id="e5db0-119">下一张示意图概括性地显示了用户体验如何通过典型的来宾访问邀请和兑换流程与权限模型结合使用。</span><span class="sxs-lookup"><span data-stu-id="e5db0-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![显示邀请和兑换流程的示意图](media/authorize-guest-image1.png)

<span data-ttu-id="e5db0-121">此处有必要注意的是，应用、机器人和连接器可能需要自己的一套特定于用户帐户的权限和/或同意。</span><span class="sxs-lookup"><span data-stu-id="e5db0-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="e5db0-122">这些可能需要单独授予。</span><span class="sxs-lookup"><span data-stu-id="e5db0-122">These might need to be granted separately.</span></span> <span data-ttu-id="e5db0-123">同样，SharePoint 可能针对特定用户、用户组，甚至在站点级别设置了额外的外部共享界限。</span><span class="sxs-lookup"><span data-stu-id="e5db0-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="e5db0-124">上两张示意图还可在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中查看。</span><span class="sxs-lookup"><span data-stu-id="e5db0-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="e5db0-125">控制 Azure Active Directory 中的条件访问</span><span class="sxs-lookup"><span data-stu-id="e5db0-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="e5db0-126">使用 Azure AD 来确定外部协作者能否受邀以来宾的身份加入你的租户以及如何加入。</span><span class="sxs-lookup"><span data-stu-id="e5db0-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="e5db0-127">有关 Azure B2B 来宾访问的详细信息，请参阅[什么是 Azure Active Directory B2B 中的来宾用户访问权限](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="e5db0-128">要了解 Azure AD 角色，请参阅[在 Azure Active Directory 租户中向来自合作伙伴组织的用户授予权限](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="e5db0-129">邀请设置在租户级别应用，可控制目标、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="e5db0-130">要在 Azure 门户中配置这些设置，请转到“**Azure Active Directory**” > “**用户**” > “**用户设置**”，再在“**外部用户**”下选择“**管理外部协作设置**”。</span><span class="sxs-lookup"><span data-stu-id="e5db0-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="e5db0-131">Azure AD 包含用于配置外部用户的以下设置：</span><span class="sxs-lookup"><span data-stu-id="e5db0-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="e5db0-132">“**来宾用户访问限制**”：这个策略决定在你目录中来宾的权限。</span><span class="sxs-lookup"><span data-stu-id="e5db0-132">**Guest user access restrictions**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="e5db0-133">有三种政策选择。</span><span class="sxs-lookup"><span data-stu-id="e5db0-133">There are three policy options.</span></span>

    - <span data-ttu-id="e5db0-134">"**来宾用户拥有与成员（最包容）相同的访问权限**"设置表示来宾与目录中的普通用户一样具有相同的目录数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="e5db0-134">The **Guest users have the same access as members (most inclusive)** setting means guests have the same access to directory data as regular users in your directory.</span></span>
    - <span data-ttu-id="e5db0-135">"**来宾用户对目录对象的属性和成员身份拥有有限的访问权限** "设置表示来宾对某些目录任务没有权限，如枚举用户、组或其他使用 Microsoft Graph的目录资源。</span><span class="sxs-lookup"><span data-stu-id="e5db0-135">The **Guest users have limited access to properties and membership of directory objects** settings means that guests don't have permissions for certain directory tasks, such as enumerating users, groups, or other directory resources using Microsoft Graph.</span></span>
    - <span data-ttu-id="e5db0-136">"**来宾用户访问权限仅限于其自己的目录对象属性和成员身份（最严格）**"设置表示来宾仅可访问自己的目录对象。</span><span class="sxs-lookup"><span data-stu-id="e5db0-136">The **Guest user access is restricted to properties and memberships of their own directory objects (most restrictive)** setting means guests can only access their own directory objects.</span></span>
    
  <span data-ttu-id="e5db0-137">要了解详细信息，请参阅[Azure Active Directory 中的默认用户权限是什么？?](https://go.microsoft.com/fwlink/?linkid=2135493)</span><span class="sxs-lookup"><span data-stu-id="e5db0-137">To learn more, see [What are the default user permissions in Azure Active Directory?](https://go.microsoft.com/fwlink/?linkid=2135493)</span></span>
- <span data-ttu-id="e5db0-138">**管理员和具有“来宾邀请者”角色的用户可以邀请**：“**是**”表示管理员和具有“来宾邀请者”角色的用户将能够邀请来宾加入租户。</span><span class="sxs-lookup"><span data-stu-id="e5db0-138">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="e5db0-139">“**否**”表示管理员和用户不可邀请来宾加入租户。</span><span class="sxs-lookup"><span data-stu-id="e5db0-139">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="e5db0-140">**成员可邀请**：要允许目录的非管理员成员邀请来宾，请将此策略设置为**是**（建议设置）。</span><span class="sxs-lookup"><span data-stu-id="e5db0-140">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="e5db0-141">如果你希望仅管理员能够添加来宾，可以将此策略设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="e5db0-141">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="e5db0-142">请记住，设置为**否**将会限制非管理员团队所有者的来宾体验；他们只能向管理员已在 AAD 中添加的团队添加来宾。</span><span class="sxs-lookup"><span data-stu-id="e5db0-142">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="e5db0-143">**来宾可邀请**：“**是**”表示目录中的来宾可邀请其他来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="e5db0-143">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="e5db0-144">“**否**”表示来宾不可邀请其他来宾与你的组织协作。</span><span class="sxs-lookup"><span data-stu-id="e5db0-144">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="e5db0-145">目前，Teams 不支持来宾邀请者角色，因此即使你将“**来宾可邀请**”设置为“**是**”，来宾也不能邀请 Teams 中的其他来宾。</span><span class="sxs-lookup"><span data-stu-id="e5db0-145">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="e5db0-146">要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-146">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="e5db0-147">还可管理可以来宾身份邀请哪些域加入你的租户。</span><span class="sxs-lookup"><span data-stu-id="e5db0-147">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="e5db0-148">请参阅[允许/阻止对 Microsoft 365 组的来宾访问](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-148">See [Allow/Block guest access to Microsoft 365 Groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="e5db0-149">无需将用户来宾帐户手动添加到 Azure AD B2B 中，因为在你向 Teams 添加来宾时，该帐户将自动添加到目录中。</span><span class="sxs-lookup"><span data-stu-id="e5db0-149">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="e5db0-150">来宾访问的许可</span><span class="sxs-lookup"><span data-stu-id="e5db0-150">Licensing for guest access</span></span>
<span data-ttu-id="e5db0-151">来宾访问许可是 Azure AD 许可的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5db0-151">Guest access licensing is part of Azure AD licensing.</span></span> <span data-ttu-id="e5db0-152">所有 Microsoft 365 商业标准版、Office 365 企业版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="e5db0-152">Guest access is included with all Microsoft 365 Business Standard and Office 365 Enterprise subscriptions.</span></span> <span data-ttu-id="e5db0-153">有关许可的详细信息，请参阅 [Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-153">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="e5db0-154">你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。</span><span class="sxs-lookup"><span data-stu-id="e5db0-154">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="e5db0-155">要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="e5db0-155">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="e5db0-156">控制 Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="e5db0-156">Control guest access in Teams</span></span>

<span data-ttu-id="e5db0-157">默认情况下，Teams 中的来宾访问处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="e5db0-157">Guest access is turned off by default in Teams.</span></span> <span data-ttu-id="e5db0-158">要启用来宾访问，请参阅[开启或关闭对 Microsoft Teams 的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-158">To turn on guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="e5db0-159">控制 Microsoft 365 组中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="e5db0-159">Control guest access in Microsoft 365 Groups</span></span>

<span data-ttu-id="e5db0-160">从 Microsoft 365 组中，你可以控制向组织中的所有 Microsoft 365 组和 Microsoft Teams 团队添加来宾用户和来宾访问。</span><span class="sxs-lookup"><span data-stu-id="e5db0-160">From Microsoft 365 Groups, you can control adding guest users and guest access to all Microsoft 365 Groups and Microsoft Teams teams in your organization.</span></span>

1. <span data-ttu-id="e5db0-161">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 处使用全局管理员帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="e5db0-161">Sign in with your global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="e5db0-162">在左侧，依次选择“**设置**”和“**服务 &amp; 外接程序**”。</span><span class="sxs-lookup"><span data-stu-id="e5db0-162">On the left, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="e5db0-163">选择 **Microsoft 365 组**。</span><span class="sxs-lookup"><span data-stu-id="e5db0-163">Select **Microsoft 365 Groups**.</span></span>

     ![“设置”中“Microsoft 365 组”的屏幕截图](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="e5db0-165">在“Microsoft 365 组”页面上，将开关设置为“**开**”或“**关**”，具体取决于你是否允许组织外部的团队和组所有者访问 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="e5db0-165">On the Microsoft 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Microsoft 365 Groups.</span></span> <span data-ttu-id="e5db0-166">单击或点击“**允许组所有者向组添加组织外部人员**”旁边的开关将其设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="e5db0-166">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="e5db0-167">如果将此开关设置为“**开**”，则会看到另一个选项，它用于控制你是否允许组和团队所有者将组织外的人员添加到 Microsoft 365 组和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e5db0-167">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Microsoft 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="e5db0-168">如果你想让组和团队所有者添加来宾用户，请将此切换设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="e5db0-168">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![“Microsoft 365 组”面板的屏幕截图，其中选项处于打开状态](media/authorize-guest-image3.png)

<span data-ttu-id="e5db0-170">这些设置应用于租户级别，并控制 Microsoft 365 组和 Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-170">These settings apply at the tenant level and control the guest experience in Microsoft 365 Groups and Teams.</span></span>

<span data-ttu-id="e5db0-171">要详细了解组中的来宾访问功能，例如来宾访问功能如何工作、如何管理来宾访问以及常见问题的解答，请参阅[在 Microsoft 365 中管理来宾访问](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#manage-groups-guest-access)和 [Microsoft 365 组的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-171">See [Manage guest access in Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#manage-groups-guest-access) and [Guest access in Microsoft 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="e5db0-172">控制对 SharePoint Online 和 OneDrive for Business 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="e5db0-172">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="e5db0-173">Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="e5db0-173">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="e5db0-174">为了获得完整的 Teams 来宾访问体验，Microsoft 365 和 Office 365 管理员需要对以下设置进行配置：</span><span class="sxs-lookup"><span data-stu-id="e5db0-174">For the full Teams guest access experience, Microsoft 365 and Office 365 admins need to configure the following settings:</span></span>

- <span data-ttu-id="e5db0-175">在 SharePoint Online 中：选择“**现有来宾**”、“**新来宾和现有来宾**”或“**任何人**”。</span><span class="sxs-lookup"><span data-stu-id="e5db0-175">In SharePoint Online: Select **Existing guests**, **New and existing guests**, or **Anyone**.</span></span>

    <span data-ttu-id="e5db0-176">有关详细信息，请参阅[打开或关闭外部共享](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-176">For more information, see [Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="e5db0-177">在 Microsoft 365 组中：启用**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="e5db0-177">In Microsoft 365 Groups: Turn on **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="e5db0-178">有关详细信息，请参阅上面的[控制 Microsoft 365 组中的来宾访问](#control-guest-access-in-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-178">For more information, see [Control guest access in Microsoft 365 Groups](#control-guest-access-in-microsoft-365-groups), above.</span></span>
  
<span data-ttu-id="e5db0-179">这些设置应用于租户级别，并控制 SharePoint Online、OneDrive for Business、Microsoft 365 组和 Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="e5db0-179">These settings apply at the tenant level and control the guest experience in SharePoint Online, OneDrive for Business, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="e5db0-180">你可以管理与 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="e5db0-180">You can manage SharePoint Online external user settings for the team sites connected to Teams.</span></span> <span data-ttu-id="e5db0-181">要了解详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="e5db0-181">To learn more, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="e5db0-182">外部访问（联合身份验证）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="e5db0-182">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="e5db0-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5db0-183">Related topics</span></span>

- [<span data-ttu-id="e5db0-184">Microsoft 365 来宾共享设置参考</span><span class="sxs-lookup"><span data-stu-id="e5db0-184">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
