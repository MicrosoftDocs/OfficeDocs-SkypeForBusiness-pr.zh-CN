---
title: 在 Microsoft Teams 中管理来宾访问
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
search.appverid: MET150
description: IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41630c14c7d1aa9233f53df3c83bd36081d18682
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753287"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="1a18a-103">在 Microsoft Teams 中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="1a18a-103">Manage guest access in Microsoft Teams</span></span>
======================================

> [!IMPORTANT]
> <span data-ttu-id="1a18a-104">您可能需要等待24小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="1a18a-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="1a18a-105">**来宾**是 Microsoft 团队中的一种用户类型，包含在所有 Office 365 Business Premium、Office 365 企业版和 Office 365 教育版订阅中。</span><span class="sxs-lookup"><span data-stu-id="1a18a-105">**Guest** is a user type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="1a18a-106">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="1a18a-106">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="1a18a-107">请阅读下面的有关[来宾访问许可](#guest-access-licensing-limits)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1a18a-107">Read more about [guest access licensing](#guest-access-licensing-limits) below.</span></span>

<span data-ttu-id="1a18a-108">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="1a18a-108">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="1a18a-109">有关如何启用来宾访问的详细信息，请参阅[打开或关闭对团队的来宾访问](set-up-guests.md)，或使用[来宾访问清单](guest-access-checklist.md)引导你完成设置。</span><span class="sxs-lookup"><span data-stu-id="1a18a-109">For details about how to turn on guest access, see [Turn on or turn off guest access to Teams](set-up-guests.md), or use the [Guest access checklist ](guest-access-checklist.md) to walk you through the setup.</span></span>

<span data-ttu-id="1a18a-110">打开来宾访问后，您可以使用在组织的 "[管理团队设置](enable-features-office-365.md)" 中介绍的控件配置来宾的设置，并在[切换到新的 Microsoft 团队管理中心时管理团队](manage-teams-skypeforbusiness-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-110">After guest access is turned on, you can configure settings for guests using the controls described in [Manage Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="1a18a-111">IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限，以及获取有关来宾用户活动的报告。</span><span class="sxs-lookup"><span data-stu-id="1a18a-111">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="1a18a-112">这些控件在团队管理中心中可用。</span><span class="sxs-lookup"><span data-stu-id="1a18a-112">These controls are available in the Teams admin center.</span></span> <span data-ttu-id="1a18a-113">来宾用户内容和活动与 Office 365 的其余部分具有相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="1a18a-113">Guest user content and activities fall under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="1a18a-114">团队所有者可以邀请新来宾，并将现有的目录来宾用户添加到团队管理中心中的团队。</span><span class="sxs-lookup"><span data-stu-id="1a18a-114">Team owners can invite new guests and add existing directory guest users to their teams in the Teams admin center.</span></span> <span data-ttu-id="1a18a-115">在 "**团队** > **管理团队**" 页面上标识来宾用户，并在 "**组织范围设置** > **来宾访问**" 页面上为来宾设置与频道相关的功能。</span><span class="sxs-lookup"><span data-stu-id="1a18a-115">Identify guest users on the **Teams** > **Manage teams** page, and set channel-related capabilities for guests on the  **Org-wide settings** > **Guest access** page.</span></span> <span data-ttu-id="1a18a-116">设置包括允许来宾创建、更新和删除频道，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="1a18a-116">Settings include allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![团队中的来宾权限设置](media/manage-guest-access-image1.png)
  
<span data-ttu-id="1a18a-118">你可以使用 Azure Active Directory （Azure AD）门户管理来宾及其对 Office 365 和团队资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1a18a-118">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="1a18a-119">团队来宾访问利用 Azure AD 企业对企业（B2B）协作功能，作为存储安全原则信息（如标识属性、成员身份和多重身份验证设置）的基础基础结构。</span><span class="sxs-lookup"><span data-stu-id="1a18a-119">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="1a18a-120">若要了解有关 Azure AD B2B 的详细信息，请参阅[什么是 AZURE AD b2b 协作？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[AZURE Active Directory b2b 协作常见问题解答](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-120">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="1a18a-121">Microsoft 团队始终采用 Azure AD 外部设置，以允许或阻止来宾用户对租户的添加。</span><span class="sxs-lookup"><span data-stu-id="1a18a-121">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="1a18a-122">有关更多详细信息，请参阅[在 Microsoft 团队中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-122">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="guest-access-licensing-limits"></a><span data-ttu-id="1a18a-123">来宾访问许可限制</span><span class="sxs-lookup"><span data-stu-id="1a18a-123">Guest access licensing limits</span></span>

<span data-ttu-id="1a18a-124">团队不会限制可添加的来宾数量。</span><span class="sxs-lookup"><span data-stu-id="1a18a-124">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="1a18a-125">但是，可添加到租户的来宾的总数基于你的 Azure AD 授权所允许的数量-通常是每个许可用户的5位来宾。</span><span class="sxs-lookup"><span data-stu-id="1a18a-125">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="1a18a-126">有关详细信息，请参阅[AZURE AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-126">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="1a18a-127">由于这些许可限制（并使你的租户保持最新），你应定期查看来宾访问权限，以确定具有不再需要的访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="1a18a-127">Because of these licensing limitations (and to keep your tenant up-to-date), you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="1a18a-128">你可以使用 Azure AD 为组成员或分配到应用程序的用户创建访问审核。</span><span class="sxs-lookup"><span data-stu-id="1a18a-128">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="1a18a-129">创建定期访问评论可节省您的时间。</span><span class="sxs-lookup"><span data-stu-id="1a18a-129">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="1a18a-130">如果需要定期查看有权访问应用程序或组成员的用户，您可以定义这些评论的频率。</span><span class="sxs-lookup"><span data-stu-id="1a18a-130">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="1a18a-131">你可以自行执行来宾访问检查、要求来宾查看其自己的成员身份，或者要求应用程序所有者或业务决策人执行访问权审核。</span><span class="sxs-lookup"><span data-stu-id="1a18a-131">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="1a18a-132">使用 Azure 门户执行来宾访问评论。</span><span class="sxs-lookup"><span data-stu-id="1a18a-132">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="1a18a-133">有关详细信息，请参阅[使用 AZURE AD 访问审核管理来宾访问](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-133">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites-for-azure-ad-access-reviews"></a><span data-ttu-id="1a18a-134">Azure AD 访问评论的先决条件</span><span class="sxs-lookup"><span data-stu-id="1a18a-134">Prerequisites for Azure AD access reviews</span></span>

<span data-ttu-id="1a18a-135">Access 评论适用于 Azure AD 高级 P2 版本，它包含在 Microsoft 企业移动性 + 安全性，E5 中。</span><span class="sxs-lookup"><span data-stu-id="1a18a-135">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="1a18a-136">有关详细信息，请参阅[Azure Active Directory 版本](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-136">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="1a18a-137">通过创建评论、填写评论或确认其访问来与此功能交互的每个用户都必须有许可证。</span><span class="sxs-lookup"><span data-stu-id="1a18a-137">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a><span data-ttu-id="1a18a-138">使来宾访问设置生效的延隔时间</span><span class="sxs-lookup"><span data-stu-id="1a18a-138">Lag time for guest access settings to take effect</span></span>

<span data-ttu-id="1a18a-139">对于 Azure Active Directory 中的来宾访问设置，更改会在你的 Office 365 组织中生效2-24 小时。</span><span class="sxs-lookup"><span data-stu-id="1a18a-139">For the guest access settings in Azure Active Directory, it takes 2-24 hours for the changes to take effect across your Office 365 organization.</span></span> <span data-ttu-id="1a18a-140">如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾功能尚未打开，或者设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="1a18a-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been turned on or the settings aren't effective yet.</span></span> <span data-ttu-id="1a18a-141">有关设置来宾访问时出现问题的帮助，请阅读[团队中的来宾访问的疑难解答](troubleshoot-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-141">For help with problems setting up guest access, read [Troubleshoot guest access in Teams](troubleshoot-guest-access.md).</span></span>

  
## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="1a18a-142">外部访问（联盟）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="1a18a-142">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="1a18a-143">更多信息</span><span class="sxs-lookup"><span data-stu-id="1a18a-143">More information</span></span>

<span data-ttu-id="1a18a-144">有关使用 PowerShell 管理来宾访问权限的信息，请参阅[使用 powershell 控制对团队的来宾访问](guest-access-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="1a18a-144">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


