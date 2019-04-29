---
title: 在 Microsoft Teams 中授权来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 04/01/19
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcd6741f100ff7ad89127c4cc5f53008e9d3608a
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400543"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="ffea3-103">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="ffea3-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="ffea3-104">为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="ffea3-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="ffea3-105">所有这些授权级别都适用于你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="ffea3-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="ffea3-106">每个授权级别按如下所示控制来宾体验：</span><span class="sxs-lookup"><span data-stu-id="ffea3-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="ffea3-107">**Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="ffea3-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="ffea3-108">控制目录、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="ffea3-109">**Microsoft Teams**：仅控制 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ffea3-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="ffea3-110">**Office 365 组**：控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="ffea3-111">**SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="ffea3-112">这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。</span><span class="sxs-lookup"><span data-stu-id="ffea3-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="ffea3-113">例如，如果您不想要允许您的 Microsoft 团队的来宾用户，但希望允许整个组织中，只需关闭来宾访问中的 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="ffea3-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="ffea3-114">其他示例：你可以在 AAD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。</span><span class="sxs-lookup"><span data-stu-id="ffea3-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="ffea3-115">SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Office 365 组的来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="ffea3-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="ffea3-116">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="ffea3-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="ffea3-117">下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Office 365 之间集成来宾访问授权相关性。</span><span class="sxs-lookup"><span data-stu-id="ffea3-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)

<span data-ttu-id="ffea3-119">下图的高级别显示的用户体验具有此权限模型通过典型来宾访问邀请和 redemption 流程的工作方式。</span><span class="sxs-lookup"><span data-stu-id="ffea3-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![邀请和 redemption 流关系图](media/authorize-guest-image1.png)

<span data-ttu-id="ffea3-121">请务必注意下面的应用程序、 自动程序，和连接器可能需要其自己的权限集和/或 consent 特定于用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ffea3-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="ffea3-122">这些可能需要单独授予。</span><span class="sxs-lookup"><span data-stu-id="ffea3-122">These might need to be granted separately.</span></span> <span data-ttu-id="ffea3-123">同样，SharePoint 可能施加额外外部共享边界为某个特定用户的用户组，或甚至在网站级别。</span><span class="sxs-lookup"><span data-stu-id="ffea3-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="ffea3-124">以前的两个图也是在[Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)中可用。</span><span class="sxs-lookup"><span data-stu-id="ffea3-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="ffea3-125">Azure Active Directory 中的控件来宾访问</span><span class="sxs-lookup"><span data-stu-id="ffea3-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="ffea3-126">使用 Azure AD 以确定是否外部协作者可以邀请进入您的租户为来宾，并以何种方式。</span><span class="sxs-lookup"><span data-stu-id="ffea3-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="ffea3-127">关于 Azure B2B 来宾访问的详细信息，请参阅[什么是在 Azure Active Directory B2B 来宾用户访问](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="ffea3-128">关于 Azure AD 角色的信息，请参阅[Azure Active Directory 租户中的合作伙伴组织的用户授予权限](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="ffea3-129">用于邀请的设置在租户级别应用，并在目录、租户和应用程序级别控制来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="ffea3-130">若要在 Azure 门户中配置这些设置，请转到**Azure Active Directory** > **用户** > **用户设置**，并在**外部用户**，下选择**管理外部协作设置**。</span><span class="sxs-lookup"><span data-stu-id="ffea3-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="ffea3-131">Azure AD 包括以下设置来配置外部用户：</span><span class="sxs-lookup"><span data-stu-id="ffea3-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="ffea3-132">**来宾用户权限被限制**:**是**意味着来宾不具有某些目录任务权限，如枚举用户、 组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="ffea3-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="ffea3-133">此外，来宾无法分配给您的目录中的管理角色。</span><span class="sxs-lookup"><span data-stu-id="ffea3-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="ffea3-134">携带**无**意味着具有对目录数据的正则用户在您的目录中具有相同的访问。</span><span class="sxs-lookup"><span data-stu-id="ffea3-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="ffea3-135">**管理员和来宾邀请者角色中的用户可以邀请**:**是**意味着管理员和"来宾邀请者"角色中的用户将能够邀请到租户的来宾。</span><span class="sxs-lookup"><span data-stu-id="ffea3-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="ffea3-136">**无**意味着管理员和用户不能邀请到租户的来宾。</span><span class="sxs-lookup"><span data-stu-id="ffea3-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="ffea3-137">**成员可以邀请**:**是**意味着您的目录的非管理员成员可以邀请来宾进行协作的 Azure AD，如 SharePoint 站点或 Azure 资源安全的资源。</span><span class="sxs-lookup"><span data-stu-id="ffea3-137">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="ffea3-138">到您的目录携带**无**意味着只有管理员可以邀请。</span><span class="sxs-lookup"><span data-stu-id="ffea3-138">**No** means that only admins can invite guests to your directory.</span></span></br>
      
    > [!NOTE]
    > <span data-ttu-id="ffea3-139">目前，团队不支持的来宾邀请者角色。</span><span class="sxs-lookup"><span data-stu-id="ffea3-139">Currently, Teams doesn't support the guest inviter role.</span></span> <span data-ttu-id="ffea3-140">**成员可以邀请**至少切换必须设置为**是**为来宾访问以在团队。</span><span class="sxs-lookup"><span data-stu-id="ffea3-140">at a minimum the **Members can invite** toggle must be set to **Yes** for guest access to work in Teams.</span></span>
- <span data-ttu-id="ffea3-141">**来宾可以邀请**:**是**意味着，您的目录中的来宾本身也可以邀请其他来宾进行协作的 Azure AD，如 SharePoint 站点或 Azure 资源安全的资源。</span><span class="sxs-lookup"><span data-stu-id="ffea3-141">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="ffea3-142">携带**无**方法不能邀请其他来宾与您的组织进行协作。</span><span class="sxs-lookup"><span data-stu-id="ffea3-142">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 
<span data-ttu-id="ffea3-143">有关控制谁可以邀请来宾的详细信息，请参阅[Azure Active Directory B2B 协作的委托邀请](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="ffea3-144">您还可以管理哪些域可以作为来宾邀请到您的租户。</span><span class="sxs-lookup"><span data-stu-id="ffea3-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="ffea3-145">请参阅[Office 365 组允许/阻止来宾访问](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-145">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span> 

<span data-ttu-id="ffea3-146">手动将用户来宾帐户添加到 Azure AD B2B 不是必需的该帐户将添加到目录自动添加到团队来宾时。</span><span class="sxs-lookup"><span data-stu-id="ffea3-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span> 

<span data-ttu-id="ffea3-147">Azure AD 许可允许您要添加每个许可证的最多 5 来宾。</span><span class="sxs-lookup"><span data-stu-id="ffea3-147">Azure AD licensing allows you to add up to 5 guests per license.</span></span> <span data-ttu-id="ffea3-148">有关 Azure AD 许可的详细信息，请参阅[Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-148">For more information about Azure AD licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="ffea3-149">团队中的控件来宾访问</span><span class="sxs-lookup"><span data-stu-id="ffea3-149">Control guest access in Teams</span></span>

<span data-ttu-id="ffea3-150">在团队中，您可以控制是否启用或禁用组织的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-150">In Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="ffea3-151">设置默认情况下禁用，并且在租户级别的团队仅适用。</span><span class="sxs-lookup"><span data-stu-id="ffea3-151">The setting is disabled by default and applies at the tenant level for Teams only.</span></span>

<span data-ttu-id="ffea3-152">您可以从 Microsoft 团队管理中心管理团队来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="ffea3-152">You can manage Teams guest access settings from the Microsoft Teams admin center.</span></span> <span data-ttu-id="ffea3-153">有关更多信息，请参阅[开启或关闭 Microsoft Teams 的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-153">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-office-365-groups"></a><span data-ttu-id="ffea3-154">Office 365 组中的控件来宾访问</span><span class="sxs-lookup"><span data-stu-id="ffea3-154">Control guest access in Office 365 Groups</span></span>

<span data-ttu-id="ffea3-155">从 Office 365 组中，你可以控制向组织中的所有 Office 365 组和 Microsoft Teams 添加来宾用户和来宾访问。</span><span class="sxs-lookup"><span data-stu-id="ffea3-155">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="ffea3-156">使用 Office 365 全局管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-156">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="ffea3-157">在导航菜单中，依次选择 **“设置”** 和 **“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="ffea3-157">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
3. <span data-ttu-id="ffea3-158">选择 **“Office 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="ffea3-158">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 组](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="ffea3-160">在 Office 365 组页中，设置切换到**打开**或**关闭**，具体取决于是否要让您组织的 Office 365 的访问组之外的团队和组的所有者。</span><span class="sxs-lookup"><span data-stu-id="ffea3-160">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="ffea3-161">单击或点击 **“允许组所有者将组织外部的人员添加到组”** 旁边的切换将其设置为 **“开启”**。</span><span class="sxs-lookup"><span data-stu-id="ffea3-161">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="ffea3-162">如果您启用此切换到**上**，您将看到另一个控件选项是否希望让组和团队所有者将您的组织外部的人员添加到 Office 365 组和 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="ffea3-162">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="ffea3-163">如果您想让组和团队所有者添加来宾用户，请将此切换设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="ffea3-163">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/authorize-guest-image3.png)

<span data-ttu-id="ffea3-165">这些设置适用于租户级别，并控制 Office 365 组和 Microsoft 团队中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-165">These settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>

<span data-ttu-id="ffea3-166">有关在组中，包括来宾访问的工作原理、 如何管理来宾访问和常见问题的解答来宾访问的详细信息，请参阅[来宾访问 Office 365 组中](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-166">See [Guest access in Office 365 Groups](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in Groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="ffea3-167">SharePoint Online 和 OneDrive for Business 的控件来宾访问</span><span class="sxs-lookup"><span data-stu-id="ffea3-167">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="ffea3-168">Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="ffea3-168">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
   
<span data-ttu-id="ffea3-169">为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择 **“开启”**：</span><span class="sxs-lookup"><span data-stu-id="ffea3-169">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>

- <span data-ttu-id="ffea3-170">在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**</span><span class="sxs-lookup"><span data-stu-id="ffea3-170">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="ffea3-171">有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://docs.microsoft.com/sharepoint/external-sharing-overview)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-171">For more information, see [Manage external sharing for your SharePoint Online environment](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span></span>
    
- <span data-ttu-id="ffea3-172">在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="ffea3-172">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="ffea3-173">有关详细信息，请参阅上方的[Office 365 组中的控件来宾访问](#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-173">For more information, see [Control guest access in Office 365 Groups](#control-guest-access-in-office-365-groups), above.</span></span>
  
<span data-ttu-id="ffea3-174">这些设置适用于租户级别，并控制在 SharePoint Online、 OneDrive for Business、 Office 365 组和团队的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="ffea3-174">These settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups, and Teams.</span></span>

<span data-ttu-id="ffea3-175">你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="ffea3-175">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="ffea3-176">有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="ffea3-176">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="ffea3-177">来宾访问与外部访问 （联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="ffea3-177">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]