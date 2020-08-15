---
title: 在 Microsoft Teams 中管理来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何创建你的第一个团队和通道、板载早期使用者、监视使用情况和反馈以及获取资源以规划组织范围内推出。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb7fe026e59bcefb6dc7fb5d586f5458e6b358f9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761158"
---
# <a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="86eb1-103">在 Microsoft Teams 中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="86eb1-103">Manage guest access in Microsoft Teams</span></span>

<span data-ttu-id="86eb1-104">**来宾** 是 microsoft 团队中的一种用户类型，其中包括所有 Microsoft 365 Business Standard、Office 365 企业版、Microsoft 365 Business Basic 和 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="86eb1-104">**Guest** is a user type in Microsoft Teams that is included with all Microsoft 365 Business Standard, Office 365 Enterprise, Microsoft 365 Business Basic, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="86eb1-105">不需要额外的 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="86eb1-105">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="86eb1-106">请阅读下面的有关 [来宾访问许可](#guest-access-licensing-limits) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="86eb1-106">Read more about [guest access licensing](#guest-access-licensing-limits) below.</span></span>

<span data-ttu-id="86eb1-107">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="86eb1-107">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="86eb1-108">有关如何启用来宾访问的详细信息，请参阅 [在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-108">For details about how to turn on guest access, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

<span data-ttu-id="86eb1-109">打开来宾访问后，您可以使用在组织的 " [管理团队设置](enable-features-office-365.md) " 中介绍的控件配置来宾的设置，并在 [切换到新的 Microsoft 团队管理中心时管理团队](manage-teams-skypeforbusiness-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-109">After guest access is turned on, you can configure settings for guests using the controls described in [Manage Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="86eb1-110">IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限，以及获取有关来宾用户活动的报告。</span><span class="sxs-lookup"><span data-stu-id="86eb1-110">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="86eb1-111">这些控件在团队管理中心中可用。</span><span class="sxs-lookup"><span data-stu-id="86eb1-111">These controls are available in the Teams admin center.</span></span> <span data-ttu-id="86eb1-112">来宾用户内容和活动与 Microsoft 365 的其余部分具有相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="86eb1-112">Guest user content and activities fall under the same compliance and auditing protection as the rest of Microsoft 365.</span></span>

<span data-ttu-id="86eb1-113">团队所有者可以邀请新来宾，并将现有的目录来宾用户添加到团队管理中心中的团队。</span><span class="sxs-lookup"><span data-stu-id="86eb1-113">Team owners can invite new guests and add existing directory guest users to their teams in the Teams admin center.</span></span> <span data-ttu-id="86eb1-114">在 "**团队**  >  **管理团队**" 页面上标识来宾用户，并在 "**组织范围设置**  >  **来宾访问**" 页面上为来宾设置与频道相关的功能。</span><span class="sxs-lookup"><span data-stu-id="86eb1-114">Identify guest users on the **Teams** > **Manage teams** page, and set channel-related capabilities for guests on the  **Org-wide settings** > **Guest access** page.</span></span> <span data-ttu-id="86eb1-115">设置包括允许来宾创建、更新和删除频道，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="86eb1-115">Settings include allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86eb1-116">您可能需要等待几个小时才能使所做的更改生效。</span><span class="sxs-lookup"><span data-stu-id="86eb1-116">You may have to wait a few hours for your changes to take effect.</span></span> 

![团队中的来宾权限设置](media/manage-guest-access-image1.png)
  
<span data-ttu-id="86eb1-118">你可以使用 Azure Active Directory (Azure AD) 门户管理来宾及其对 Microsoft 365 和团队资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="86eb1-118">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Microsoft 365 and Teams resources.</span></span> <span data-ttu-id="86eb1-119">团队来宾访问利用 Azure AD 企业到企业 (B2B) 协作功能，作为存储安全原则信息（如标识属性、成员身份和多重身份验证设置）的基础基础结构。</span><span class="sxs-lookup"><span data-stu-id="86eb1-119">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="86eb1-120">若要了解有关 Azure AD B2B 的详细信息，请参阅 [什么是 AZURE AD b2b 协作？](https://go.microsoft.com/fwlink/p/?linkid=853011) 和 [AZURE Active Directory b2b 协作常见问题解答](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-120">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="86eb1-121">Microsoft 团队始终采用 Azure AD 外部设置，以允许或阻止来宾用户对租户的添加。</span><span class="sxs-lookup"><span data-stu-id="86eb1-121">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="86eb1-122">有关更多详细信息，请参阅 [在 Microsoft 团队中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-122">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="guest-access-licensing-limits"></a><span data-ttu-id="86eb1-123">来宾访问许可限制</span><span class="sxs-lookup"><span data-stu-id="86eb1-123">Guest access licensing limits</span></span>

<span data-ttu-id="86eb1-124">Teams 不限制可添加的来宾数量。</span><span class="sxs-lookup"><span data-stu-id="86eb1-124">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="86eb1-125">但是，可添加到租户的来宾总数取决于 Azure AD 许可所允许的数量（通常为每个许可用户可添加 5 个来宾）。</span><span class="sxs-lookup"><span data-stu-id="86eb1-125">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="86eb1-126">有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-126">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="86eb1-127">由于这些许可限制 (并使你的租户保持最新) ，因此应定期查看来宾访问权限，以标识有权不再需要的用户。</span><span class="sxs-lookup"><span data-stu-id="86eb1-127">Because of these licensing limitations (and to keep your tenant up-to-date), you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="86eb1-128">你可以使用 Azure AD 为组成员或分配到应用程序的用户创建访问审核。</span><span class="sxs-lookup"><span data-stu-id="86eb1-128">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="86eb1-129">创建定期访问评论可节省您的时间。</span><span class="sxs-lookup"><span data-stu-id="86eb1-129">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="86eb1-130">如果需要定期查看有权访问应用程序或组成员的用户，您可以定义这些评论的频率。</span><span class="sxs-lookup"><span data-stu-id="86eb1-130">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="86eb1-131">你可以自行执行来宾访问检查、要求来宾查看其自己的成员身份，或者要求应用程序所有者或业务决策人执行访问权审核。</span><span class="sxs-lookup"><span data-stu-id="86eb1-131">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="86eb1-132">使用 Azure 门户执行来宾访问评论。</span><span class="sxs-lookup"><span data-stu-id="86eb1-132">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="86eb1-133">有关详细信息，请参阅 [使用 AZURE AD 访问审核管理来宾访问](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-133">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="lag-time-for-guest-access-settings-to-take-effect"></a><span data-ttu-id="86eb1-134">使来宾访问设置生效的延隔时间</span><span class="sxs-lookup"><span data-stu-id="86eb1-134">Lag time for guest access settings to take effect</span></span>

<span data-ttu-id="86eb1-135">对于 Azure Active Directory 中的来宾访问设置，需要几个小时才能使更改在 Microsoft 365 中生效。</span><span class="sxs-lookup"><span data-stu-id="86eb1-135">For the guest access settings in Azure Active Directory, it takes a few hours for the changes to take effect across Microsoft 365.</span></span> <span data-ttu-id="86eb1-136">如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾功能尚未打开，或者设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="86eb1-136">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been turned on or the settings aren't effective yet.</span></span> <span data-ttu-id="86eb1-137">有关设置来宾访问时出现问题的帮助，请阅读 [团队中的来宾访问的疑难解答](troubleshoot-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-137">For help with problems setting up guest access, read [Troubleshoot guest access in Teams](troubleshoot-guest-access.md).</span></span>
  
## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="86eb1-138">外部访问（联合身份验证）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="86eb1-138">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="86eb1-139">更多信息</span><span class="sxs-lookup"><span data-stu-id="86eb1-139">More information</span></span>

<span data-ttu-id="86eb1-140">有关使用 PowerShell 管理来宾访问权限的信息，请参阅 [使用 powershell 控制对团队的来宾访问](guest-access-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="86eb1-140">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


