---
title: 在 Microsoft Teams 中管理来宾访问
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: rramesan
search.appverid: MET150
description: IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 091215e37af012c2e2203b451e3df4dd9cf6480f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016722"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="cc91c-103">在 Microsoft Teams 中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="cc91c-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="cc91c-104">**来宾**是随所有 Office 365 企业高级版、 Office 365 Enterprise 和 Office 365 教育版订阅的 Microsoft 团队中的用户/许可证类型。</span><span class="sxs-lookup"><span data-stu-id="cc91c-104">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="cc91c-105">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="cc91c-105">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="cc91c-106">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="cc91c-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="cc91c-107">有关如何启用来宾访问的详细信息，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="cc91c-107">For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="cc91c-108">**来宾**用户/许可证类型已打开后，您可以配置设置的来宾通过控件中所述[在 Office 365 组织中管理 Microsoft 团队功能](enable-features-office-365.md)和[管理团队转换为新的 Microsoft 的过程工作组和业务管理中心的 Skype](manage-teams-skypeforbusiness-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cc91c-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams and Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="cc91c-109">IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。</span><span class="sxs-lookup"><span data-stu-id="cc91c-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="cc91c-110">这些控制功能通过 Office 365 管理中心提供。</span><span class="sxs-lookup"><span data-stu-id="cc91c-110">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="cc91c-111">来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="cc91c-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="cc91c-112">团队所有者可以邀请新的来宾，并将现有目录来宾用户添加到他们的团队。</span><span class="sxs-lookup"><span data-stu-id="cc91c-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="cc91c-113">此外，团队所有者可为来宾通过**管理团队**设置通道相关功能 > **来宾权限**，包括允许来宾创建、 更新和删除通道，如以下屏幕截图中所示：</span><span class="sxs-lookup"><span data-stu-id="cc91c-113">In addition, team owners can set channel-related capabilities for guests via **Manage teams** > **Guest permissions**, including allowing guests to create, update, and delete channels, as shown in the following screenshot:</span></span>

![团队中的来宾权限设置。](media/view-guests-guest-permissions.png)
  

<span data-ttu-id="cc91c-115">此外，你还可以使用 Azure Active Directory 门户管理来宾及其对 Office 365 和 Teams 资源的访问。</span><span class="sxs-lookup"><span data-stu-id="cc91c-115">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="cc91c-116">Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="cc91c-116">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="cc91c-117">要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="cc91c-117">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
> [!NOTE]
> <span data-ttu-id="cc91c-118">Microsoft 团队始终采用 Azure Active Directory 外部设置，以允许或阻止来宾用户添加到租户。</span><span class="sxs-lookup"><span data-stu-id="cc91c-118">Microsoft Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> <span data-ttu-id="cc91c-119">有关详细信息，请参阅[Microsoft 团队中的授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc91c-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
