---
title: 在 Microsoft Teams 中管理来宾访问
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02faf85d91657c487c02503b69b08078b81c88de
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="ba000-103">在 Microsoft Teams 中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="ba000-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="ba000-104">**访客**是所包含的所有 Office 365 的业务津贴、 Office 365 企业和 Office 365 教育订阅 Microsoft 小组中的用户/许可证类型。</span><span class="sxs-lookup"><span data-stu-id="ba000-104">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ba000-105">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="ba000-105">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="ba000-106">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="ba000-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="ba000-107">有关如何启用 guest 访问的详细信息，请参阅[启用或禁用来宾访问 Microsoft 小组](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="ba000-107">For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="ba000-108">打开**来宾**用户/许可证类型后，可以配置客人通过所述[Office 365 提供组织中的管理 Microsoft 小组功能](enable-features-office-365.md#settings-by-userlicense-type)控制设置。</span><span class="sxs-lookup"><span data-stu-id="ba000-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md#settings-by-userlicense-type).</span></span>     
    
<span data-ttu-id="ba000-109">IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。</span><span class="sxs-lookup"><span data-stu-id="ba000-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="ba000-110">这些控制功能通过 Office 365 管理中心提供。</span><span class="sxs-lookup"><span data-stu-id="ba000-110">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="ba000-111">来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="ba000-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="ba000-112">团队所有者可以邀请新的客人，并将现有目录来宾用户添加到他们的团队。</span><span class="sxs-lookup"><span data-stu-id="ba000-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="ba000-113">此外，团队所有者可以为客人通过**管理团队**设置通道相关功能 > **来宾权限**，包括允许客人要创建，更新和删除的频道，如下面的屏幕快照中所示：</span><span class="sxs-lookup"><span data-stu-id="ba000-113">In addition, team owners can set channel-related capabilities for guests via **Manage teams** > **Guest permissions**, including allowing guests to create, update, and delete channels, as shown in the following screenshot:</span></span>

![在团队中的来宾权限设置。](media/view-guests-guest-permissions.png)
  

<span data-ttu-id="ba000-115">此外，你还可以使用 Azure Active Directory 门户管理来宾及其对 Office 365 和 Teams 资源的访问。</span><span class="sxs-lookup"><span data-stu-id="ba000-115">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="ba000-116">Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="ba000-116">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="ba000-117">要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="ba000-117">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
> [!NOTE]
> <span data-ttu-id="ba000-118">Microsoft 小组始终尊重 Azure Active Directory 外部设置，以允许或阻止访客用户添加到组织。</span><span class="sxs-lookup"><span data-stu-id="ba000-118">Microsoft Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> <span data-ttu-id="ba000-119">有关更多详细信息，请参阅[Microsoft 小组授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="ba000-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
