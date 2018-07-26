---
title: 在 Microsoft Teams 中授权来宾访问
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d31bb8eafdaa6a04fe34f8433e8484ec447e7c1
ms.sourcegitcommit: 2ce680aba13d1d781019b766a04e4e7d46d4f72c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "21136304"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="24613-103">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="24613-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="24613-104">为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="24613-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="24613-105">所有这些授权级别都适用于你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="24613-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="24613-106">每个授权级别按如下所示控制来宾体验：</span><span class="sxs-lookup"><span data-stu-id="24613-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="24613-107">**Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="24613-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="24613-108">控制目录、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="24613-109">**Microsoft Teams**：仅控制 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="24613-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="24613-110">**Office 365 组**：控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="24613-111">**SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="24613-112">这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。</span><span class="sxs-lookup"><span data-stu-id="24613-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="24613-113">例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，只需在 Microsoft Teams 中关闭来宾访问即可。</span><span class="sxs-lookup"><span data-stu-id="24613-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="24613-114">其他示例：你可以在 AAD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。</span><span class="sxs-lookup"><span data-stu-id="24613-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="24613-115">可能你不使用 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="24613-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="24613-116">SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Office 365 组的来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="24613-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="24613-117">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="24613-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="24613-118">下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Office 365 之间集成来宾访问授权相关性。</span><span class="sxs-lookup"><span data-stu-id="24613-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="24613-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="24613-120">Azure Active Directory</span></span>

<span data-ttu-id="24613-121">有了 Azure AD 企业到企业 (B2B) 协作，向潜在来宾用户发送邀请的操作将不局限于租户管理员。</span><span class="sxs-lookup"><span data-stu-id="24613-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="24613-122">你可以使用策略将发送邀请的任务委派给角色允许其发送邀请的用户。</span><span class="sxs-lookup"><span data-stu-id="24613-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="24613-123">用于邀请的设置在租户级别应用，并在目录、租户和应用程序级别控制来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="24613-124">至少支持来宾**成员可以邀请**必须设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="24613-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Azure Active Directory 门户中用户设置的屏幕截图。](media/teams_dependencies_image2.png)

<span data-ttu-id="24613-126">Azure AD 包括以下设置来配置外部用户：</span><span class="sxs-lookup"><span data-stu-id="24613-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="24613-127">**来宾用户权限被限制**:**是**意味着来宾不具有某些目录任务权限，如枚举用户、 组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="24613-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="24613-128">此外，来宾无法分配给您的目录中的管理角色。</span><span class="sxs-lookup"><span data-stu-id="24613-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="24613-129">携带**无**意味着具有对目录数据的正则用户在您的目录中具有相同的访问。</span><span class="sxs-lookup"><span data-stu-id="24613-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="24613-130">**管理员和来宾邀请者角色中的用户可以邀请**:**是**意味着管理员和"来宾邀请者"角色中的用户将能够邀请到租户的来宾。</span><span class="sxs-lookup"><span data-stu-id="24613-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="24613-131">**无**意味着管理员和用户不能邀请到租户的来宾。</span><span class="sxs-lookup"><span data-stu-id="24613-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="24613-132">**成员可以邀请**:**是**意味着您的目录的非管理员成员可以邀请来宾进行协作的 Azure AD，如 SharePoint 站点或 Azure 资源安全的资源。</span><span class="sxs-lookup"><span data-stu-id="24613-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="24613-133">到您的目录携带**无**意味着只有管理员可以邀请。</span><span class="sxs-lookup"><span data-stu-id="24613-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="24613-134">**来宾可以邀请**:**是**意味着，您的目录中的来宾本身也可以邀请其他来宾进行协作的 Azure AD，如 SharePoint 站点或 Azure 资源安全的资源。</span><span class="sxs-lookup"><span data-stu-id="24613-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="24613-135">携带**无**方法不能邀请其他来宾与您的组织进行协作。</span><span class="sxs-lookup"><span data-stu-id="24613-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="24613-136">您还可以管理哪些域可以作为来宾邀请到您的租户。</span><span class="sxs-lookup"><span data-stu-id="24613-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="24613-137">请参阅[Office 365 组允许/阻止来宾访问](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da)。</span><span class="sxs-lookup"><span data-stu-id="24613-137">See [Allow/Block guest access to Office 365 groups](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="24613-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24613-138">Microsoft Teams</span></span>
<span data-ttu-id="24613-139">在 Microsoft Teams 中，你可以控制为组织启用还是禁用来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="24613-140">该设置在默认情况下禁用，仅在租户级别应用于 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="24613-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="24613-141">你可以从 Office 365 管理中心管理 Microsoft Teams 来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="24613-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="24613-142">有关更多信息，请参阅[开启或关闭 Microsoft Teams 的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="24613-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="24613-143">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="24613-143">Office 365 Groups</span></span>

<span data-ttu-id="24613-144">从 Office 365 组中，你可以控制向组织中的所有 Office 365 组和 Microsoft Teams 添加来宾用户和来宾访问。</span><span class="sxs-lookup"><span data-stu-id="24613-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="24613-145">使用 Office 365 全局管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="24613-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="24613-146">在导航菜单中，依次选择 **“设置”** 和 **“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="24613-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="24613-147">选择 **“Office 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="24613-147">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="24613-149">在“Office 365 组”页面上，将切换设置为 **“开启”** 或 **“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="24613-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="24613-150">单击或点击 **“允许组所有者将组织外部的人员添加到组”** 旁边的切换将其设置为 **“开启”**。</span><span class="sxs-lookup"><span data-stu-id="24613-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="24613-151">如果将此切换设置为“开启”，则会看到另一个选项，用于控制你是否让组和团队所有者将组织外的人员添加到 Office 365 组和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="24613-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="24613-152">如果你想让组和团队所有者添加来宾用户，请将此切换设置为“开启”。</span><span class="sxs-lookup"><span data-stu-id="24613-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="24613-153">![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="24613-153">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="24613-154">上述设置在租户级别应用，并控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="24613-155">SharePoint Online 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="24613-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="24613-156">Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="24613-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="24613-157">为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择 **“开启”**：</span><span class="sxs-lookup"><span data-stu-id="24613-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="24613-158">在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**</span><span class="sxs-lookup"><span data-stu-id="24613-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="24613-159">有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)。</span><span class="sxs-lookup"><span data-stu-id="24613-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="24613-160">在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="24613-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="24613-161">有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。</span><span class="sxs-lookup"><span data-stu-id="24613-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="24613-162">上述设置在租户级别应用，并控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="24613-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="24613-163">你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="24613-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="24613-164">有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="24613-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
