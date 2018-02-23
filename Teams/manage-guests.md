---
title: "管理对 Microsoft Teams 的来宾访问"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: d665a5a837070eadbbd8d3f7e168da0ad97d642c
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="dd42b-103">管理对 Microsoft Teams 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="dd42b-103">Manage guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="dd42b-104">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="dd42b-104">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="dd42b-105">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="dd42b-105">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="dd42b-106">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="dd42b-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="dd42b-107">IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。</span><span class="sxs-lookup"><span data-stu-id="dd42b-107">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="dd42b-108">这些控制功能通过 Office 365 管理中心提供。</span><span class="sxs-lookup"><span data-stu-id="dd42b-108">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="dd42b-109">来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="dd42b-109">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="dd42b-110">Teams 来宾访问租户设置仅阻止来宾登录。</span><span class="sxs-lookup"><span data-stu-id="dd42b-110">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="dd42b-111">团队所有者将能够邀请新来宾以及向其各自团队添加现有目录来宾用户。</span><span class="sxs-lookup"><span data-stu-id="dd42b-111">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="dd42b-112">请注意，Teams 始终支持 Azure Active Directory 外部设置以允许或阻止向租户添加来宾用户。</span><span class="sxs-lookup"><span data-stu-id="dd42b-112">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="dd42b-113">此外，你还可以使用 Azure Active Directory 门户管理来宾及其对 Office 365 和 Teams 资源的访问。</span><span class="sxs-lookup"><span data-stu-id="dd42b-113">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="dd42b-114">Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="dd42b-114">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="dd42b-115">要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="dd42b-115">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  