---
title: 向团队添加来宾
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: 了解管理员可用于将新来宾用户添加到组织的工具，包括 Microsoft Teams 桌面客户端和 Web 客户端以及 Azure Active Directory B2B 协作门户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a176ccf4eb6a35b9a4cbff9dcd8be663f5630d8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418474"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="ce18d-103">向团队添加来宾</span><span class="sxs-lookup"><span data-stu-id="ce18d-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ce18d-104">拥有企业或消费者电子邮件帐户（如 Outlook、Gmail 或其他）的任何人都可以作为来宾参与 Teams。</span><span class="sxs-lookup"><span data-stu-id="ce18d-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="ce18d-105">作为管理员，你可以通过以下几种方式向组织添加新的来宾用户：</span><span class="sxs-lookup"><span data-stu-id="ce18d-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span>
- <span data-ttu-id="ce18d-106">身为团队所有者的全局管理员和团队所有者可以通过 Microsoft Teams 桌面客户端或 Web 客户端将来宾添加到团队。</span><span class="sxs-lookup"><span data-stu-id="ce18d-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="ce18d-107">有关更多详细信息，请参阅[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="ce18d-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>

> [!NOTE] 
> <span data-ttu-id="ce18d-108">这在启用**只有管理员和具有“来宾邀请者”角色的用户可以邀请**时不适用。</span><span class="sxs-lookup"><span data-stu-id="ce18d-108">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="ce18d-109">这是因为在 Teams 中不支持来宾邀请者角色。</span><span class="sxs-lookup"><span data-stu-id="ce18d-109">This is because the guest invitor role isn't supported in Teams.</span></span>

- <span data-ttu-id="ce18d-110">通过 Azure Active Directory (Azure AD) B2B 协作将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="ce18d-110">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="ce18d-111">利用 AD B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。</span><span class="sxs-lookup"><span data-stu-id="ce18d-111">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="ce18d-112">有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?linkid=826383)。</span><span class="sxs-lookup"><span data-stu-id="ce18d-112">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="ce18d-113">利用 AD B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。</span><span class="sxs-lookup"><span data-stu-id="ce18d-113">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="ce18d-114">可以在租户、应用或个人用户级别强制实施这些策略，与针对全职员工和组织成员启用这些策略的方式相同。</span><span class="sxs-lookup"><span data-stu-id="ce18d-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="ce18d-115">此类策略在资源组织上强制应用。</span><span class="sxs-lookup"><span data-stu-id="ce18d-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="ce18d-116">有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="ce18d-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="ce18d-117">无法阻止单个来宾用户。</span><span class="sxs-lookup"><span data-stu-id="ce18d-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="ce18d-118">你通过 Azure AD B2B、Office 365 组或 SharePoint Online 添加的来宾用户已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="ce18d-118">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="ce18d-119">Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。</span><span class="sxs-lookup"><span data-stu-id="ce18d-119">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="ce18d-120">如果某个团队已使用某个 Office 365 组，向该组添加来宾后，该来宾将有权访问该团队。</span><span class="sxs-lookup"><span data-stu-id="ce18d-120">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="ce18d-121">通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。</span><span class="sxs-lookup"><span data-stu-id="ce18d-121">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="ce18d-122">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="ce18d-122">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="ce18d-123">你可以在 Azure AD 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。</span><span class="sxs-lookup"><span data-stu-id="ce18d-123">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="ce18d-124">在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。</span><span class="sxs-lookup"><span data-stu-id="ce18d-124">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="ce18d-125">有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="ce18d-125">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="ce18d-126">来宾访问与外部访问（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="ce18d-126">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="ce18d-127">更多信息</span><span class="sxs-lookup"><span data-stu-id="ce18d-127">More information</span></span>

[<span data-ttu-id="ce18d-128">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="ce18d-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="ce18d-129">开启或关闭 Microsoft Teams 的来宾访问权</span><span class="sxs-lookup"><span data-stu-id="ce18d-129">Turn on or off guest access to Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="ce18d-130">使用 PowerShell 控制来宾对团队的访问</span><span class="sxs-lookup"><span data-stu-id="ce18d-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
