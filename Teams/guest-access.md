---
title: Microsoft Teams 中的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761238"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="513bc-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="513bc-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="513bc-104">利用来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问 Teams 中现有团队和频道的权限来与其协作。</span><span class="sxs-lookup"><span data-stu-id="513bc-104">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="513bc-105">任何拥有企业或消费者电子邮件帐户（例如 Microsoft 365、Outlook、Gmail 或其他人）的人都可以在团队中作为来宾参与团队聊天、会议和文件的完全访问。</span><span class="sxs-lookup"><span data-stu-id="513bc-105">Anyone with a business or consumer email account, such as Microsoft 365, Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="513bc-106">作为 Teams 管理员，你可以控制来宾可以（及不可）在 Teams 中使用的功能 - 请查看[管理来宾访问](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="513bc-106">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="513bc-107">要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="513bc-107">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="513bc-108">来宾访问是 Teams 组织范围内的设置且默认关闭。</span><span class="sxs-lookup"><span data-stu-id="513bc-108">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="513bc-109"> (您可以使用 [灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制对单个团队的来宾访问。 ) </span><span class="sxs-lookup"><span data-stu-id="513bc-109">(You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="513bc-110">如果你已准备好开始邀请团队加入团队，请阅读下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="513bc-110">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="513bc-111">若要为团队配置常规使用的来宾访问，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="513bc-111">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="513bc-112">若要与使用 Azure Active Directory 的合作伙伴组织进行协作，并允许来宾自行注册团队访问，请参阅 [使用托管来宾创建 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="513bc-112">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="513bc-113">来宾访问受到 Azure AD 和 Microsoft 365 或 Office 365 服务限制的约束。</span><span class="sxs-lookup"><span data-stu-id="513bc-113">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="513bc-114">来宾用户遵循 Teams 组织范围内的共存升级模式设置。</span><span class="sxs-lookup"><span data-stu-id="513bc-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="513bc-115">此选项无法更改。</span><span class="sxs-lookup"><span data-stu-id="513bc-115">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="513bc-116">来宾访问的许可</span><span class="sxs-lookup"><span data-stu-id="513bc-116">Licensing for guest access</span></span>

<span data-ttu-id="513bc-117">所有 Microsoft 365 商业标准版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="513bc-117">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="513bc-118">无需额外的 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="513bc-118">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="513bc-119">Teams 不对可添加的来宾数量进行限制。</span><span class="sxs-lookup"><span data-stu-id="513bc-119">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="513bc-120">但是，可添加到你的租户的来宾总数可能受到 Azure AD 的付费功能的限制。</span><span class="sxs-lookup"><span data-stu-id="513bc-120">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="513bc-121">有关详细信息，请参阅 [Azure AD B2B 协作授权](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="513bc-121">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="513bc-122">你组织中仅拥有独立Microsoft 365 或 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。</span><span class="sxs-lookup"><span data-stu-id="513bc-122">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="513bc-123">要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="513bc-123">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="513bc-124">来宾具体是什么？</span><span class="sxs-lookup"><span data-stu-id="513bc-124">Who is a guest?</span></span>

<span data-ttu-id="513bc-125">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="513bc-125">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="513bc-126">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="513bc-126">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="513bc-127">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="513bc-127">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="513bc-128">不属于你的组织的任何人都可作为来宾添加到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="513bc-128">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="513bc-129">这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。</span><span class="sxs-lookup"><span data-stu-id="513bc-129">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="513bc-130">要了解有关来宾可以操作和无法执行的操作的更多信息，请参阅[授权 Microsoft Teams 中的来宾访问](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="513bc-130">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="513bc-131">或查看[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。</span><span class="sxs-lookup"><span data-stu-id="513bc-131">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="513bc-132">最后，团队中的所有来宾均被与 Microsoft 365 的其余部分相同的合规性和审核保护涵盖，并且可以在 Azure AD 中托管。</span><span class="sxs-lookup"><span data-stu-id="513bc-132">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="513bc-133">为何要使用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="513bc-133">Why use guest access?</span></span>

<span data-ttu-id="513bc-134">借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="513bc-134">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> 

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="513bc-135">了解来宾的限制</span><span class="sxs-lookup"><span data-stu-id="513bc-135">Understand the limitations for guests</span></span>

<span data-ttu-id="513bc-136">来宾体验体验在设计上有限制。</span><span class="sxs-lookup"><span data-stu-id="513bc-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="513bc-137">确保你了解来宾体验，这样你就不会试图去解决一些不成问题的问题。</span><span class="sxs-lookup"><span data-stu-id="513bc-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="513bc-138">下面是 Microsoft 团队中的来宾无法使用的部分功能的列表：</span><span class="sxs-lookup"><span data-stu-id="513bc-138">Here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="513bc-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="513bc-139">OneDrive</span></span>
- <span data-ttu-id="513bc-140">在 Teams 外进行人员搜索</span><span class="sxs-lookup"><span data-stu-id="513bc-140">People search outside of Teams</span></span>
- <span data-ttu-id="513bc-141">日历、计划的会议或会议详细信息</span><span class="sxs-lookup"><span data-stu-id="513bc-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="513bc-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="513bc-142">PSTN</span></span>
- <span data-ttu-id="513bc-143">组织结构图</span><span class="sxs-lookup"><span data-stu-id="513bc-143">Organization chart</span></span>
- <span data-ttu-id="513bc-144">创建或修订团队</span><span class="sxs-lookup"><span data-stu-id="513bc-144">Create or revise a team</span></span>
- <span data-ttu-id="513bc-145">浏览团队</span><span class="sxs-lookup"><span data-stu-id="513bc-145">Browse for a team</span></span>
- <span data-ttu-id="513bc-146">将文件上传到个人对个人聊天</span><span class="sxs-lookup"><span data-stu-id="513bc-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="513bc-147">当前，团队仅支持 [状态1和状态2来宾用户类型](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="513bc-147">Currently, Teams supports only [State 1 and State 2 types of guest users](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="513bc-148">有关来宾在 Teams 中可以和不可执行的操作的完整列表，请参阅[团队成员和来宾功能比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表。</span><span class="sxs-lookup"><span data-stu-id="513bc-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="513bc-149">若要了解有关 Microsoft 365 级别的来宾访问的详细信息，请阅读 [与组织外部人员进行协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="513bc-149">To learn more about guest access at the Microsoft 365 level, read [Collaborating with people outside your organization](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span></span>


## <a name="related-topics"></a><span data-ttu-id="513bc-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="513bc-150">Related topics</span></span>

[<span data-ttu-id="513bc-151">联系商业版产品的支持人员 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="513bc-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="513bc-152">配置具有三层保护的团队</span><span class="sxs-lookup"><span data-stu-id="513bc-152">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
