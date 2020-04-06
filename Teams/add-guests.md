---
title: 向团队添加来宾
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 管理员可以在 Microsoft Teams 桌面和 Web 客户端以及 Azure Active Directory B2B协作门户中了解如何向组织添加新来宾用户。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60538383021028d043cb47197dd41ee89f8a4d37
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139361"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="0abb3-103">向团队添加来宾</span><span class="sxs-lookup"><span data-stu-id="0abb3-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0abb3-104">拥有企业或消费者电子邮件帐户（如 Outlook、Gmail 或其他）的任何人都可以作为来宾参与 Teams。</span><span class="sxs-lookup"><span data-stu-id="0abb3-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="0abb3-105">作为管理员，你可以通过以下几种方式向组织添加新的来宾用户：</span><span class="sxs-lookup"><span data-stu-id="0abb3-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="0abb3-106">全局管理员或 Teams 管理员和团队所有者在 Teams 客户端或 Teams 管理中心内团队添加来宾。</span><span class="sxs-lookup"><span data-stu-id="0abb3-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="0abb3-107">若要了解详细信息，请参阅[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="0abb3-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="0abb3-108">如果尚未设置来宾访问权限，请按照[来宾访问清单](guest-access-checklist.md)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="0abb3-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="0abb3-109">这在启用“**管理员和具有“来宾邀请者”角色的用户可以邀请**”的情况下不适用。</span><span class="sxs-lookup"><span data-stu-id="0abb3-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="0abb3-110">这是因为在 Teams 中不支持来宾邀请者角色。</span><span class="sxs-lookup"><span data-stu-id="0abb3-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="0abb3-111">通过 Azure Active Directory (Azure AD) B2B 协作将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="0abb3-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="0abb3-112">利用 AD B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。</span><span class="sxs-lookup"><span data-stu-id="0abb3-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="0abb3-113">有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?linkid=826383)。</span><span class="sxs-lookup"><span data-stu-id="0abb3-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="0abb3-114">利用 AD B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。</span><span class="sxs-lookup"><span data-stu-id="0abb3-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="0abb3-115">可以在租户、应用或个人用户级别强制实施这些策略，与针对全职员工和组织成员启用这些策略的方式相同。</span><span class="sxs-lookup"><span data-stu-id="0abb3-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="0abb3-116">此类策略在资源组织上强制应用。</span><span class="sxs-lookup"><span data-stu-id="0abb3-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="0abb3-117">有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="0abb3-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="0abb3-118">无法阻止单个来宾用户。</span><span class="sxs-lookup"><span data-stu-id="0abb3-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="0abb3-119">你通过 Azure AD B2B、Office 365 组或 SharePoint Online 添加的来宾用户已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="0abb3-119">Guest users you have already added via Azure AD B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="0abb3-120">Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。</span><span class="sxs-lookup"><span data-stu-id="0abb3-120">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="0abb3-121">如果某个团队已使用某个 Office 365 组，向该组添加来宾后，该来宾将有权访问该团队。</span><span class="sxs-lookup"><span data-stu-id="0abb3-121">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="0abb3-122">通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。</span><span class="sxs-lookup"><span data-stu-id="0abb3-122">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="0abb3-123">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="0abb3-123">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="0abb3-124">你可以在 Azure AD 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。</span><span class="sxs-lookup"><span data-stu-id="0abb3-124">You can track guest additions in Azure AD or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="0abb3-125">在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。</span><span class="sxs-lookup"><span data-stu-id="0abb3-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="0abb3-126">有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="0abb3-126">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="0abb3-127">更多信息</span><span class="sxs-lookup"><span data-stu-id="0abb3-127">More information</span></span>

[<span data-ttu-id="0abb3-128">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="0abb3-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="0abb3-129">开启或关闭 Microsoft Teams 的来宾访问权</span><span class="sxs-lookup"><span data-stu-id="0abb3-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="0abb3-130">使用 PowerShell 控制来宾对团队的访问</span><span class="sxs-lookup"><span data-stu-id="0abb3-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
