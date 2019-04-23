---
title: 在 Microsoft Teams 中管理来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 601582953136b982245bc7f4b2976c64d37424e7
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959241"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="b1379-103">在 Microsoft Teams 中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="b1379-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="b1379-104">**来宾**是随所有 Office 365 企业高级版、 Office 365 Enterprise 和 Office 365 教育版订阅的 Microsoft 团队中的用户/许可证类型。</span><span class="sxs-lookup"><span data-stu-id="b1379-104">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="b1379-105">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="b1379-105">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="b1379-106">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="b1379-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="b1379-107">有关如何启用来宾访问的详细信息，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="b1379-107">For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="b1379-108">**来宾**用户/许可证类型已打开后，您可以配置设置的来宾通过控件中所述[为您的组织的管理 Microsoft 团队设置](enable-features-office-365.md)和[管理团队转换为新的 Microsoft 团队的过程管理中心](manage-teams-skypeforbusiness-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b1379-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="b1379-109">IT 管理员可以在租户级别添加来宾、 设置和管理来宾用户策略和权限，并纳入有关来宾用户活动报告。</span><span class="sxs-lookup"><span data-stu-id="b1379-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="b1379-110">这些控件是可通过 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="b1379-110">These controls are available through the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1379-111">来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="b1379-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="b1379-112">团队所有者可以邀请新的来宾，并将现有目录来宾用户添加到他们的团队。</span><span class="sxs-lookup"><span data-stu-id="b1379-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="b1379-113">团队所有者可以标识来宾用户通过**团队** > **管理团队**和设置通过**组织范围的设置**的来宾通道相关功能 > **来宾访问**，包括允许来宾来创建、 更新和删除通道，如以下屏幕截图中所示。</span><span class="sxs-lookup"><span data-stu-id="b1379-113">Team owners can identify guest users via **Teams** > **Manage teams**, and set channel-related capabilities for guests via **Org-wide settings** > **Guest access**, including allowing guests to create, update, and delete channels, as shown in the following screenshot.</span></span>

![团队中的来宾权限设置](media/manage-guest-access-image1.png)
  
<span data-ttu-id="b1379-115">您可以使用 Azure Active Directory 门户管理来宾和其访问 Office 365 和团队资源。</span><span class="sxs-lookup"><span data-stu-id="b1379-115">You can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="b1379-116">Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="b1379-116">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="b1379-117">要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="b1379-117">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="b1379-118">Microsoft 团队始终采用 Azure Active Directory 外部设置，以允许或阻止来宾用户添加到租户。</span><span class="sxs-lookup"><span data-stu-id="b1379-118">Microsoft Teams always honors Azure Active Directory external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="b1379-119">有关详细信息，请参阅[Microsoft 团队中的授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="b1379-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="b1379-120">来宾访问与外部访问 （联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="b1379-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a><span data-ttu-id="b1379-121">定期查看来宾访问</span><span class="sxs-lookup"><span data-stu-id="b1379-121">Review guest access periodically</span></span>

<span data-ttu-id="b1379-122">在团队中，您可以添加 5 个来宾的每个许可用户。</span><span class="sxs-lookup"><span data-stu-id="b1379-122">In Teams, you can add 5 guests for each licensed user.</span></span> <span data-ttu-id="b1379-123">由于此限制，或您希望用于保存您的租户最新，因为您应当查看来宾访问定期确定具有不再需要它们的访问权的用户。</span><span class="sxs-lookup"><span data-stu-id="b1379-123">Because of this limitation, or because you want to keep your tenant up to date, you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="b1379-124">Azure Active Directory (Azure AD) 可用于创建访问查看组成员或分配给应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="b1379-124">You can use Azure Active Directory (Azure AD) to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="b1379-125">创建定期访问评论可以节省时间。</span><span class="sxs-lookup"><span data-stu-id="b1379-125">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="b1379-126">如果您需要定期查看用户有权访问应用程序用户或组的成员，您可以定义这些评论的频率。</span><span class="sxs-lookup"><span data-stu-id="b1379-126">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="b1379-127">可以自己执行来宾访问回顾、 提出来宾若要查看其自己的成员身份，或提出的应用程序所有者或业务决策者执行访问评审。</span><span class="sxs-lookup"><span data-stu-id="b1379-127">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="b1379-128">使用 Azure 门户执行来宾访问评论。</span><span class="sxs-lookup"><span data-stu-id="b1379-128">You use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="b1379-129">有关详细信息，请参阅[管理使用 Azure AD 访问的来宾访问审阅](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="b1379-129">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites"></a><span data-ttu-id="b1379-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="b1379-130">Prerequisites</span></span>

<span data-ttu-id="b1379-131">访问评论所具有的 Azure AD，包括在 Microsoft 企业移动 + 安全性、 E5 Premium P2 版本。</span><span class="sxs-lookup"><span data-stu-id="b1379-131">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="b1379-132">有关详细信息，请参阅在[Azure Active Directory 版本](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)中的"选择 edition"。</span><span class="sxs-lookup"><span data-stu-id="b1379-132">For more information, see "Choose an edition" in [Azure Active Directory editions](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="b1379-133">每个用户交互具有该功能通过创建回顾、 填写回顾，或确认他们的访问，都必须有许可证。</span><span class="sxs-lookup"><span data-stu-id="b1379-133">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span> 

<span data-ttu-id="b1379-134">团队不会限制您可以添加的来宾数。</span><span class="sxs-lookup"><span data-stu-id="b1379-134">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="b1379-135">但是，可以添加到您的租户的来宾总数取决于哪些您 AAD 许可允许。</span><span class="sxs-lookup"><span data-stu-id="b1379-135">However, the total number of guests that can be added to your tenant is based on what your AAD licensing allows.</span></span> <span data-ttu-id="b1379-136">有关详细信息，请参阅[Azure AD B2B 协作授权](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="b1379-136">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="guest-access-latencies"></a><span data-ttu-id="b1379-137">来宾访问延迟</span><span class="sxs-lookup"><span data-stu-id="b1379-137">Guest access latencies</span></span>

<span data-ttu-id="b1379-138">在 Azure Active Directory 中设置来宾设置后，</span><span class="sxs-lookup"><span data-stu-id="b1379-138">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="b1379-139">更改在 Office 365 组织中生效需要 2 小时到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="b1379-139">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="b1379-140">如果用户会看到"请与管理员联系"的邮件如果他们尝试将来宾添加到其工作组，，则可能的来宾功能尚未启用或设置尚未有效。</span><span class="sxs-lookup"><span data-stu-id="b1379-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

## <a name="more-information"></a><span data-ttu-id="b1379-141">更多信息</span><span class="sxs-lookup"><span data-stu-id="b1379-141">More information</span></span>

<span data-ttu-id="b1379-142">有关使用 PowerShell 管理来宾访问信息，请参阅[使用 PowerShell 来控制对团队的来宾访问](guest-access-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b1379-142">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


