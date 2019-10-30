---
title: Microsoft Teams 中的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a0bba0c8893ee706061b989f95d4e22619fa4f9
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753277"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="8299d-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="8299d-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="8299d-104">通过来宾访问，可将组织外部的单个用户添加到 Microsoft Teams 中的团队和频道。</span><span class="sxs-lookup"><span data-stu-id="8299d-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="8299d-105">要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="8299d-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="8299d-106">如果你已准备好在组织中启用来宾访问，请从[来宾访问清单](guest-access-checklist.md)开始。</span><span class="sxs-lookup"><span data-stu-id="8299d-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="8299d-107">来宾访问概述</span><span class="sxs-lookup"><span data-stu-id="8299d-107">Guest access overview</span></span>

<span data-ttu-id="8299d-108">利用来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问 Teams 中现有团队和频道的权限来与其协作。</span><span class="sxs-lookup"><span data-stu-id="8299d-108">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="8299d-109">具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="8299d-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="8299d-110">作为 Teams 管理员，你可以控制来宾可以（及不可）在 Teams 中使用的功能 - 请查看[管理来宾访问](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="8299d-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="8299d-111">来宾访问是 Teams 组织范围内的设置且默认关闭。</span><span class="sxs-lookup"><span data-stu-id="8299d-111">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="8299d-112">来宾访问受制于 Azure AD 和 Office 365 服务限制。</span><span class="sxs-lookup"><span data-stu-id="8299d-112">Guest access is subject to Azure AD and Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8299d-113">来宾用户遵循 Teams 组织范围内的共存升级模式设置。</span><span class="sxs-lookup"><span data-stu-id="8299d-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="8299d-114">此选项无法更改。</span><span class="sxs-lookup"><span data-stu-id="8299d-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="8299d-115">来宾访问的许可</span><span class="sxs-lookup"><span data-stu-id="8299d-115">Licensing for guest access</span></span>

<span data-ttu-id="8299d-116">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="8299d-116">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="8299d-117">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="8299d-117">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="8299d-118">Teams 不限制可添加的来宾数量。</span><span class="sxs-lookup"><span data-stu-id="8299d-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="8299d-119">但是，可添加到租户的来宾总数取决于 Azure AD 许可所允许的数量（通常为每个许可用户可添加 5 个来宾）。</span><span class="sxs-lookup"><span data-stu-id="8299d-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="8299d-120">有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="8299d-120">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="8299d-121">你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。</span><span class="sxs-lookup"><span data-stu-id="8299d-121">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="8299d-122">要让这些用户使用 Teams，必须向他们分配 Office 365 商业高级版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="8299d-122">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="8299d-123">来宾具体是什么？</span><span class="sxs-lookup"><span data-stu-id="8299d-123">Who is a guest?</span></span>

<span data-ttu-id="8299d-124">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="8299d-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="8299d-125">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="8299d-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="8299d-126">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="8299d-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="8299d-127">不属于你的组织的任何人都可作为来宾添加到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="8299d-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="8299d-128">这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。</span><span class="sxs-lookup"><span data-stu-id="8299d-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="8299d-129">要了解有关来宾可以操作和无法执行的操作的更多信息，请参阅[授权 Microsoft Teams 中的来宾访问](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="8299d-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="8299d-130">或查看[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。</span><span class="sxs-lookup"><span data-stu-id="8299d-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="8299d-131">最后，Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。</span><span class="sxs-lookup"><span data-stu-id="8299d-131">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="8299d-132">为何要使用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="8299d-132">Why use guest access?</span></span>

<span data-ttu-id="8299d-133">借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="8299d-133">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="8299d-134">Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。</span><span class="sxs-lookup"><span data-stu-id="8299d-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="8299d-135">了解来宾的限制</span><span class="sxs-lookup"><span data-stu-id="8299d-135">Understand the limitations for guests</span></span>

<span data-ttu-id="8299d-136">来宾体验体验在设计上有限制。</span><span class="sxs-lookup"><span data-stu-id="8299d-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="8299d-137">确保你了解来宾体验，这样你就不会试图去解决一些不成问题的问题。</span><span class="sxs-lookup"><span data-stu-id="8299d-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="8299d-138">例如，下面列出了一些 Microsoft Teams 中来宾无法使用的功能：</span><span class="sxs-lookup"><span data-stu-id="8299d-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="8299d-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="8299d-139">Access OneDrive for Business storage</span></span>
- <span data-ttu-id="8299d-140">在 Teams 外进行人员搜索</span><span class="sxs-lookup"><span data-stu-id="8299d-140">People search outside of Teams</span></span>
- <span data-ttu-id="8299d-141">日历、计划的会议或会议详细信息</span><span class="sxs-lookup"><span data-stu-id="8299d-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="8299d-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="8299d-142">PSTN</span></span>
- <span data-ttu-id="8299d-143">组织结构图</span><span class="sxs-lookup"><span data-stu-id="8299d-143">Organization Chart</span></span>
- <span data-ttu-id="8299d-144">创建或修订团队</span><span class="sxs-lookup"><span data-stu-id="8299d-144">Create or revise a team</span></span>
- <span data-ttu-id="8299d-145">浏览团队</span><span class="sxs-lookup"><span data-stu-id="8299d-145">Browse for a team</span></span>
- <span data-ttu-id="8299d-146">将文件上传到个人对个人聊天</span><span class="sxs-lookup"><span data-stu-id="8299d-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="8299d-147">如果来宾知道用户的完整电子邮件 ID，则他们仍可搜索和查找（其团队之外的）用户。</span><span class="sxs-lookup"><span data-stu-id="8299d-147">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="8299d-148">为了防止发生这种情况，IT 管理员可以使用[范围目录搜索](teams-scoped-directory-search.md)之类的模式，以能够将来宾限制到自己的虚拟 GAL 的模式。</span><span class="sxs-lookup"><span data-stu-id="8299d-148">To prevent this, IT admins can use patterns like [scoped directory search](teams-scoped-directory-search.md) that have the ability to restrict guests to their own virtual GAL.</span></span>

<span data-ttu-id="8299d-149">有关来宾在 Teams 中可以和不可执行的操作的完整列表，请参阅[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。</span><span class="sxs-lookup"><span data-stu-id="8299d-149">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="8299d-150">要了解有关 Office 365 级别的来宾访问的更多信息，请参阅[将来宾添加到 Office 365 组](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="8299d-150">To learn more about guest access at the Office 365 level, read [Adding guests to Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

## <a name="how-does-external-access-federation-compare-to-guest-access"></a><span data-ttu-id="8299d-151">外部访问（联合身份验证）与来宾访问有何区别？</span><span class="sxs-lookup"><span data-stu-id="8299d-151">How does external access (federation) compare to guest access?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="8299d-152">更多信息</span><span class="sxs-lookup"><span data-stu-id="8299d-152">More information</span></span>

[<span data-ttu-id="8299d-153">联系商业版产品的支持人员 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="8299d-153">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="8299d-154">Office 365 组的来宾访问</span><span class="sxs-lookup"><span data-stu-id="8299d-154">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
