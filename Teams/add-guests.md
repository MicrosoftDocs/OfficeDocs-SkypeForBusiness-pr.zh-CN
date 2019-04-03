---
title: 向团队添加来宾
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
description: 了解管理员可用于将新来宾用户添加到组织的工具，包括 Microsoft Teams 桌面客户端和 Web 客户端以及 Azure Active Directory B2B 协作门户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27f1f344313111561c9f1c3a5e57dc1bd0ae20cb
ms.sourcegitcommit: 7ca70e8a2108462afd505258b455169ead30f33f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31041899"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="ed51a-103">向团队添加来宾</span><span class="sxs-lookup"><span data-stu-id="ed51a-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ed51a-104">具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以作为来宾团队中参与。</span><span class="sxs-lookup"><span data-stu-id="ed51a-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="ed51a-105">作为管理员，你可以采用多种方式将新来宾用户添加到组织：</span><span class="sxs-lookup"><span data-stu-id="ed51a-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="ed51a-106">身为团队所有者的全局管理员和团队所有者可以通过 Microsoft Teams 桌面客户端或 Web 客户端将来宾添加到团队。</span><span class="sxs-lookup"><span data-stu-id="ed51a-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="ed51a-107">有关详细信息，请查看[添加到团队的来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="ed51a-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>
- <span data-ttu-id="ed51a-108">通过 Azure Active Directory B2B 协作将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="ed51a-108">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="ed51a-109">利用 Azure Active Directory B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。</span><span class="sxs-lookup"><span data-stu-id="ed51a-109">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="ed51a-110">有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?linkid=826383)。</span><span class="sxs-lookup"><span data-stu-id="ed51a-110">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="ed51a-111">利用 Azure Active Directory B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。</span><span class="sxs-lookup"><span data-stu-id="ed51a-111">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="ed51a-112">可以在租户、应用或单个用户级别强制应用这些策略，方式与对组织的全职员工和成员启用它们一样。</span><span class="sxs-lookup"><span data-stu-id="ed51a-112">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="ed51a-113">此类策略在资源组织上强制应用。</span><span class="sxs-lookup"><span data-stu-id="ed51a-113">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="ed51a-114">有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="ed51a-114">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="ed51a-115">无法阻止单个来宾用户。</span><span class="sxs-lookup"><span data-stu-id="ed51a-115">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="ed51a-116">来宾通过 Azure Active Directory B2B、 Office 365 组或 SharePoint Online 已添加的用户便准备好转。</span><span class="sxs-lookup"><span data-stu-id="ed51a-116">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="ed51a-117">Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。</span><span class="sxs-lookup"><span data-stu-id="ed51a-117">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="ed51a-118">如果某个团队已使用某个 Office 365 组，向该组添加来宾后，该来宾将有权访问该团队。</span><span class="sxs-lookup"><span data-stu-id="ed51a-118">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="ed51a-119">通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。</span><span class="sxs-lookup"><span data-stu-id="ed51a-119">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="ed51a-120">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="ed51a-120">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="ed51a-121">你可以在 Azure Active Directory 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。</span><span class="sxs-lookup"><span data-stu-id="ed51a-121">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="ed51a-122">在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。</span><span class="sxs-lookup"><span data-stu-id="ed51a-122">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="ed51a-123">有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="ed51a-123">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="ed51a-124">来宾访问与外部访问 （联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="ed51a-124">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="ed51a-125">更多信息</span><span class="sxs-lookup"><span data-stu-id="ed51a-125">More information</span></span>

[<span data-ttu-id="ed51a-126">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="ed51a-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="ed51a-127">打开或关闭来宾访问中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="ed51a-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="ed51a-128">使用 PowerShell 控制来宾对团队的访问</span><span class="sxs-lookup"><span data-stu-id="ed51a-128">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
