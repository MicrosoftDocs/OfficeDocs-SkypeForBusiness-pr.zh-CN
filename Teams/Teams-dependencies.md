---
title: 在 Microsoft Teams 中授权来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
description: 通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 846bc820e214f6d0468de46844ddca59392399f5
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567032"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="2f36a-103">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="2f36a-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="2f36a-104">为满足贵组织的要求，你可以通过四种不同级别的授权来管理 Microsoft Teams 来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="2f36a-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="2f36a-105">所有这些授权级别都适用于你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2f36a-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="2f36a-106">每个授权级别按如下所示控制来宾体验：</span><span class="sxs-lookup"><span data-stu-id="2f36a-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="2f36a-107">**Azure Active Directory**：Microsoft Teams 中的来宾体验依赖于 Azure AD 企业到企业 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="2f36a-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="2f36a-108">此授权级别控制目录、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-108">Controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="2f36a-109">**Microsoft Teams**：仅控制 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="2f36a-110">**Office 365 组**：控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="2f36a-111">**SharePoint Online 和 OneDrive for Business**：控制 SharePoint Online、OneDrive for Business、Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="2f36a-112">这些不同的授权级别可让你灵活选择为组织设置来宾访问的方式。</span><span class="sxs-lookup"><span data-stu-id="2f36a-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="2f36a-113">例如，如果你不想在 Microsoft Teams 组织中允许来宾用户，但想在组织中全面允许，只需在 Microsoft Teams 中关闭来宾访问即可。</span><span class="sxs-lookup"><span data-stu-id="2f36a-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="2f36a-114">其他示例：你可以在 Azure AD、Teams 和组级别启用来宾访问，然后对匹配一个或多个条件（如数据分类为机密）的选定团队禁用添加来宾用户的功能。</span><span class="sxs-lookup"><span data-stu-id="2f36a-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="2f36a-115">SharePoint Online 和 OneDrive for Business 具有自己的不依赖 Office 365 组的来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="2f36a-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="2f36a-116">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="2f36a-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="2f36a-117">下面的示意图显示了如何授予并在 Azure Active Directory、Microsoft Teams 和 Office 365 之间集成来宾访问授权相关性。</span><span class="sxs-lookup"><span data-stu-id="2f36a-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![用于来宾访问的授权相关性示意图。](media/teams_dependencies_image1.png)

<span data-ttu-id="2f36a-119">下一张示意图概括性地显示了用户体验如何通过典型的来宾访问邀请和兑换流程与权限模型结合使用。</span><span class="sxs-lookup"><span data-stu-id="2f36a-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![显示邀请和兑换流程的示意图](media/authorize-guest-image1.png)

<span data-ttu-id="2f36a-121">此处有必要注意的是，应用、机器人和连接器可能需要自己的一套特定于用户帐户的权限和/或同意。</span><span class="sxs-lookup"><span data-stu-id="2f36a-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="2f36a-122">这些可能需要单独授予。</span><span class="sxs-lookup"><span data-stu-id="2f36a-122">These might need to be granted separately.</span></span> <span data-ttu-id="2f36a-123">同样，SharePoint 可能针对特定用户、用户组，甚至在站点级别设置了额外的外部共享界限。</span><span class="sxs-lookup"><span data-stu-id="2f36a-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="2f36a-124">上两张示意图还可在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中查看。</span><span class="sxs-lookup"><span data-stu-id="2f36a-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="2f36a-125">控制 Azure Active Directory 中的条件访问</span><span class="sxs-lookup"><span data-stu-id="2f36a-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="2f36a-126">使用 Azure AD 来确定外部协作者能否受邀以来宾的身份加入你的租户以及如何加入。</span><span class="sxs-lookup"><span data-stu-id="2f36a-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="2f36a-127">有关 Azure B2B 来宾访问的详细信息，请参阅[什么是 Azure Active Directory B2B 中的来宾用户访问权限](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="2f36a-128">要了解 Azure AD 角色，请参阅[在 Azure Active Directory 租户中向来自合作伙伴组织的用户授予权限](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/add-guest-to-role)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="2f36a-129">邀请设置在租户级别应用，可控制目标、租户和应用程序级别的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="2f36a-130">要在 Azure 门户中配置这些设置，请转到“**Azure Active Directory**” > “**用户**” > “**用户设置**”，再在“**外部用户**”下选择“**管理外部协作设置**”。</span><span class="sxs-lookup"><span data-stu-id="2f36a-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="2f36a-131">Azure AD 包含用于配置外部用户的以下设置：</span><span class="sxs-lookup"><span data-stu-id="2f36a-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="2f36a-132">**限制来宾用户权限**：“**是**”表示来宾无权处理某些目录任务，例如枚举用户、组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="2f36a-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="2f36a-133">此外，未将来宾分配到你目录中的管理角色。</span><span class="sxs-lookup"><span data-stu-id="2f36a-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="2f36a-134">“**否**”表示来宾与目录中的常规用户具有相同的目录数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f36a-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="2f36a-135">**管理员和具有“来宾邀请者”角色的用户可以邀请**：“**是**”表示管理员和具有“来宾邀请者”角色的用户将能够邀请来宾加入租户。</span><span class="sxs-lookup"><span data-stu-id="2f36a-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="2f36a-136">“**否**”表示管理员和用户不可邀请来宾加入租户。</span><span class="sxs-lookup"><span data-stu-id="2f36a-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="2f36a-137">**成员可邀请**：“**是**”表示目录的非管理员成员可邀请来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="2f36a-137">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="2f36a-138">“**否**”表示只有管理员可邀请来宾到你的目录。</span><span class="sxs-lookup"><span data-stu-id="2f36a-138">**No** means that only admins can invite guests to your directory.</span></span></br>
      
    > [!NOTE]
    > <span data-ttu-id="2f36a-139">目前，Teams 不支持来宾邀请者角色。</span><span class="sxs-lookup"><span data-stu-id="2f36a-139">Currently, Teams doesn't support the guest inviter role.</span></span> <span data-ttu-id="2f36a-140">至少必须将“**成员可邀请**”开关设置为“**是**”，这样才能在 Teams 中使用来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="2f36a-140">at a minimum the **Members can invite** toggle must be set to **Yes** for guest access to work in Teams.</span></span>
- <span data-ttu-id="2f36a-141">**来宾可邀请**：“**是**”表示目录中的来宾可邀请其他来宾协作处理受到 Azure AD 保护的资源，例如 SharePoint 网站或 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="2f36a-141">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="2f36a-142">“**否**”表示来宾不可邀请其他来宾与你的组织协作。</span><span class="sxs-lookup"><span data-stu-id="2f36a-142">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 
<span data-ttu-id="2f36a-143">要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="2f36a-144">还可管理可以来宾身份邀请哪些域加入你的租户。</span><span class="sxs-lookup"><span data-stu-id="2f36a-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="2f36a-145">请参阅[允许/阻止对 Office 365 组的来宾访问](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-145">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="2f36a-146">无需将用户来宾帐户手动添加到 Azure AD B2B 中，因为在你向 Teams 添加来宾时，该帐户将自动添加到目录中。</span><span class="sxs-lookup"><span data-stu-id="2f36a-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

<span data-ttu-id="2f36a-147">通过 Azure AD 许可，每个许可证最多可添加 5 名来宾。</span><span class="sxs-lookup"><span data-stu-id="2f36a-147">Azure AD licensing allows you to add up to 5 guests per license.</span></span> <span data-ttu-id="2f36a-148">有关 Azure AD 许可的详细信息，请参阅 [Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-148">For more information about Azure AD licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="2f36a-149">控制 Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="2f36a-149">Control guest access in Teams</span></span>

<span data-ttu-id="2f36a-150">可在 Teams 中控制是否为组织来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-150">In Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="2f36a-151">此设置默认禁用且仅在 Teams 的租户级别应用。</span><span class="sxs-lookup"><span data-stu-id="2f36a-151">The setting is disabled by default and applies at the tenant level for Teams only.</span></span>

<span data-ttu-id="2f36a-152">你可通过 Microsoft Teams 管理中心管理 Teams 来宾访问设置。</span><span class="sxs-lookup"><span data-stu-id="2f36a-152">You can manage Teams guest access settings from the Microsoft Teams admin center.</span></span> <span data-ttu-id="2f36a-153">有关详细信息，请参阅[开启或关闭对 Microsoft Teams 的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-153">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-office-365-groups"></a><span data-ttu-id="2f36a-154">控制 Office 365 组中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="2f36a-154">Control guest access in Office 365 Groups</span></span>

<span data-ttu-id="2f36a-155">从 Office 365 组中，你可以控制向组织中的所有 Office 365 组和 Microsoft Teams 添加来宾用户和来宾访问。</span><span class="sxs-lookup"><span data-stu-id="2f36a-155">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="2f36a-156">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 处使用 Office 365 全局管理员帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="2f36a-156">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="2f36a-157">在导航菜单中，依次选择 **“设置”** 和 **“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="2f36a-157">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="2f36a-158">选择 **“Office 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="2f36a-158">Select **Office 365 Groups**.</span></span>

     ![“设置”中“Office 365 组”的屏幕截图](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="2f36a-160">在“Office 365 组”页面上，将开关设置为“**开**”或“**关**”，具体取决于你是否允许组织外部的团队和组所有者访问 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="2f36a-160">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="2f36a-161">单击或点击“**允许组所有者向组添加组织外部人员**”旁边的开关将其设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="2f36a-161">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="2f36a-162">如果将此开关设置为“**开**”，则会看到另一个选项，它用于控制你是否允许组和团队所有者将组织外的人员添加到 Office 365 组和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="2f36a-162">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="2f36a-163">如果你想让组和团队所有者添加来宾用户，请将此切换设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="2f36a-163">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![“Office 365 组”面板的屏幕截图，其中选项处于打开状态](media/authorize-guest-image3.png)

<span data-ttu-id="2f36a-165">这些设置在租户级别应用，并控制 Office 365 组和 Microsoft Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-165">These settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>

<span data-ttu-id="2f36a-166">要详细了解组中的来宾访问功能，例如来宾访问功能如何工作、如何管理来宾访问以及常见问题的解答，请参阅 [Office 365 组的来宾访问](https://support.office.com/zh-CN/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-166">See [Guest access in Office 365 Groups](https://support.office.com/zh-CN/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in Groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="2f36a-167">控制对 SharePoint Online 和 OneDrive for Business 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="2f36a-167">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="2f36a-168">Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="2f36a-168">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="2f36a-169">为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择 **“开启”**：</span><span class="sxs-lookup"><span data-stu-id="2f36a-169">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>

- <span data-ttu-id="2f36a-170">在 SharePoint Online 中：“现有来宾”\*\*\*\*、“新来宾和现有来宾”\*\*\*\* 或“任何人”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2f36a-170">In SharePoint Online: **Existing guests**, **New and existing guests**, or **Anyone**</span></span>

    <span data-ttu-id="2f36a-171">有关详细信息，请参阅[打开或关闭外部共享](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-171">For more information, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="2f36a-172">在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="2f36a-172">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="2f36a-173">有关详细信息，请参阅上面的[控制 Office 365 组中的来宾访问](#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-173">For more information, see [Control guest access in Office 365 Groups](#control-guest-access-in-office-365-groups), above.</span></span>
  
<span data-ttu-id="2f36a-174">这些设置在租户级别应用，并控制 SharePoint Online、OneDrive for Business、Office 365 组和 Teams 中的来宾体验。</span><span class="sxs-lookup"><span data-stu-id="2f36a-174">These settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups, and Teams.</span></span>

<span data-ttu-id="2f36a-175">你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="2f36a-175">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="2f36a-176">有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="2f36a-176">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="2f36a-177">来宾访问与外部访问（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="2f36a-177">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="2f36a-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="2f36a-178">Related topics</span></span>

- [<span data-ttu-id="2f36a-179">Microsoft 365 来宾共享设置参考</span><span class="sxs-lookup"><span data-stu-id="2f36a-179">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
