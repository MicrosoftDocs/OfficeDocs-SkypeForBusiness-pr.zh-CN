---
title: "在 Microsoft Teams 中授权来宾访问"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8faf2e13efb0c4c031fabea11185f1e3cdd353d1
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2017
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="9b6f8-103">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="9b6f8-103">Manage guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="9b6f8-104">为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="9b6f8-105">所有这些授权级别都适用于你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="9b6f8-106">每个授权级别按如下所示控制来宾体验：</span><span class="sxs-lookup"><span data-stu-id="9b6f8-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="9b6f8-107">**Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="9b6f8-108">控制目录、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="9b6f8-109">**Microsoft Teams**：仅控制 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="9b6f8-110">**Office 365 组**：控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="9b6f8-111">**SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="9b6f8-112">这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="9b6f8-113">例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，只需在 Microsoft Teams 中关闭来宾访问即可。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="9b6f8-114">其他示例：你可以在 AAD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="9b6f8-115">可能你不使用 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="9b6f8-116">SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Office 365 组的来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="9b6f8-117">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="9b6f8-118">下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Office 365 之间集成来宾访问授权相关性。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a><span data-ttu-id="9b6f8-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9b6f8-120">Azure Active Directory</span></span>

<span data-ttu-id="9b6f8-121">有了 Azure AD 企业到企业 (B2B) 协作，向潜在来宾用户发送邀请的操作将不局限于租户管理员。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="9b6f8-122">你可以使用策略将发送邀请的任务委派给角色允许其发送邀请的用户。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="9b6f8-123">用于邀请的设置在租户级别应用，并在目录、租户和应用程序级别控制来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span>


![Azure Active Directory 门户中用户设置的屏幕截图。](media/teams_dependencies_image2.png)


<span data-ttu-id="9b6f8-125">你可以设置以下邀请策略：</span><span class="sxs-lookup"><span data-stu-id="9b6f8-125">You can set the following parameters:</span></span>
- <span data-ttu-id="9b6f8-126">关闭邀请。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-126">Turn off invitations.</span></span>
- <span data-ttu-id="9b6f8-127">只有管理员和具有“来宾邀请者”角色的用户可以邀请。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-127">Only admins and users in the guest inviter role can invite.</span></span>
- <span data-ttu-id="9b6f8-128">管理员、“来宾邀请者”角色和成员可以邀请。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-128">Admins, the guest inviter role, and members can invite.</span></span>
- <span data-ttu-id="9b6f8-129">包括来宾在内的所有用户都可以邀请。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-129">All users, including guests, can invite.</span></span> <span data-ttu-id="9b6f8-130">（这是用于租户的默认策略。）</span><span class="sxs-lookup"><span data-stu-id="9b6f8-130">(This is the default policy for tenants.)</span></span>


##<a name="microsoft-teams"></a><span data-ttu-id="9b6f8-131">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b6f8-131">Microsoft Teams</span></span>

<span data-ttu-id="9b6f8-132">在 Microsoft Teams 中，你可以控制为组织启用还是禁用来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-132">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="9b6f8-133">该设置在默认情况下禁用，仅在租户级别应用于 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-133">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="9b6f8-134">你可以从 Office 365 管理中心管理 Microsoft Teams 来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-134">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="9b6f8-135">有关更多信息，请参阅[开启或关闭 Microsoft Teams 的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-135">For more details, see "Turn on or off guest access for Microsoft Teams."</span></span> 


##<a name="office-365-groups"></a><span data-ttu-id="9b6f8-136">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="9b6f8-136">Office 365 groups</span></span>

<span data-ttu-id="9b6f8-137">从 Office 365 组中，你可以控制向组织中的所有 Office 365 组和 Microsoft Teams 添加来宾用户和来宾访问。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-137">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="9b6f8-138">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-138">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="9b6f8-139">在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-139">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="9b6f8-140">选择**“Office 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-140">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="9b6f8-142">在“Office 365 组”页面上，将切换设置为**“开启”**或**“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-142">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="9b6f8-143">单击或点击**“允许组所有者将组织外部的人员添加到组”**旁边的切换将其设置为**“开启”**。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-143">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="9b6f8-144">如果将此切换设置为“开启”，则会看到另一个选项，用于控制你是否让组和团队所有者将组织外的人员添加到 Office 365 组和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-144">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="9b6f8-145">如果你想让组和团队所有者添加来宾用户，请将此切换设置为“开启”。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-145">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="9b6f8-146">![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="9b6f8-146">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="9b6f8-147">上述设置在租户级别应用，并控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-147">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


##<a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="9b6f8-148">SharePoint Online 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9b6f8-148">See How SharePoint Online and OneDrive for Business interact with Teams</span></span>

<span data-ttu-id="9b6f8-149">Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-149">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="9b6f8-150">为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择**“开启”**：</span><span class="sxs-lookup"><span data-stu-id="9b6f8-150">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="9b6f8-151">在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**</span><span class="sxs-lookup"><span data-stu-id="9b6f8-151">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="9b6f8-152">有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-152">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="9b6f8-153">在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="9b6f8-153">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="9b6f8-154">有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-154">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="9b6f8-155">上述设置在租户级别应用，并控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-155">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="9b6f8-156">你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-156">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="9b6f8-157">有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="9b6f8-157">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>