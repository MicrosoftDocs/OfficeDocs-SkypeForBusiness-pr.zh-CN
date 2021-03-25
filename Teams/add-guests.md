---
title: 向团队添加来宾
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理员可以了解如何在 Microsoft Teams 桌面和 Web 客户端以及 Azure Active Directory B2B 协作门户中向组织添加新来宾。
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109078"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="7f151-103">向团队添加来宾</span><span class="sxs-lookup"><span data-stu-id="7f151-103">Add a guest to a team</span></span>

<span data-ttu-id="7f151-104">拥有企业或消费者电子邮件帐户（如 Outlook、Gmail 或其他）的任何人都可以作为来宾参与 Teams。</span><span class="sxs-lookup"><span data-stu-id="7f151-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="7f151-105">作为管理员，可以通过多种方式向组织添加新来宾：</span><span class="sxs-lookup"><span data-stu-id="7f151-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="7f151-106">全局管理员或 Teams 管理员和团队所有者在 Teams 客户端或 Teams 管理中心内团队添加来宾。</span><span class="sxs-lookup"><span data-stu-id="7f151-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="7f151-107">若要了解详细信息，请参阅[向团队添加来宾](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="7f151-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="7f151-108">如果尚未设置来宾访问权限，请按照“[在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)”的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="7f151-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="7f151-109">通过 Azure Active Directory (Azure AD) B2B 协作将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="7f151-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="7f151-110">有关详细信息，请参阅 [快速入门：在 Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)门户中将来宾添加到目录。</span><span class="sxs-lookup"><span data-stu-id="7f151-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="7f151-111">管理员还可以通过分配“来宾邀请者”角色来委派将来宾添加到组织中其他人的权限。</span><span class="sxs-lookup"><span data-stu-id="7f151-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="7f151-112">有关详细信息，请参阅[启用 B2B 外部协作并管理可邀请来宾的人员](/azure/active-directory/external-identities/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="7f151-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="7f151-113">利用 AD B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。</span><span class="sxs-lookup"><span data-stu-id="7f151-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="7f151-114">可以在租户、应用或个人用户级别强制实施这些策略，与针对全职员工和组织成员启用这些策略的方式相同。</span><span class="sxs-lookup"><span data-stu-id="7f151-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="7f151-115">此类策略在资源组织上强制应用。</span><span class="sxs-lookup"><span data-stu-id="7f151-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="7f151-116">有关详细信息，请参阅 [B2B 协作用户的条件访问](/azure/active-directory/external-identities/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="7f151-116">For more information, see  [Conditional access for B2B collaboration users](/azure/active-directory/external-identities/conditional-access).</span></span> <span data-ttu-id="7f151-117">无法阻止单个来宾。</span><span class="sxs-lookup"><span data-stu-id="7f151-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="7f151-118">已通过 Azure AD B2B、Microsoft 365 组或 SharePoint 添加的来宾已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="7f151-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="7f151-119">Microsoft 365 管理员或团队所有者可以将这些来宾添加到各自的团队。</span><span class="sxs-lookup"><span data-stu-id="7f151-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="7f151-120">如果将来宾直接添加到与团队关联的 Microsoft 365 组，则来宾将有权访问该团队，但 Microsoft 365 组不会生成给来宾的邀请电子邮件，因此团队中的人应通知来宾。</span><span class="sxs-lookup"><span data-stu-id="7f151-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="7f151-121">来宾受 [Microsoft 365 或 Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) 和 [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="7f151-121">Guests are subject to  [Microsoft 365 or Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) service limits.</span></span>

<span data-ttu-id="7f151-122">你可以在 Azure AD 或 Microsoft 365 安全中心中跟踪来宾添加情况。</span><span class="sxs-lookup"><span data-stu-id="7f151-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="7f151-123">在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。</span><span class="sxs-lookup"><span data-stu-id="7f151-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="7f151-124">有关详细信息，请参阅审核和报告 [B2B 协作用户和](/azure/active-directory/external-identities/auditing-and-reporting) 在审核日志 [中心中搜索用户](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="7f151-124">For more details, see [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="7f151-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f151-125">Related topics</span></span>

[<span data-ttu-id="7f151-126">在 Microsoft Teams 中授权来宾访问</span><span class="sxs-lookup"><span data-stu-id="7f151-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="7f151-127">开启或关闭 Microsoft Teams 的来宾访问权</span><span class="sxs-lookup"><span data-stu-id="7f151-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)