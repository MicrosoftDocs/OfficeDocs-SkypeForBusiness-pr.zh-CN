---
title: Microsoft Teams 中的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
ms.openlocfilehash: cab51fd9cf0a81c849a0baf379150ccb2e08d818
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030278"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="93ed3-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="93ed3-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="93ed3-104">有了来宾访问权限，您可以为组织外部的人员提供对团队、频道、资源、聊天和应用程序的访问权限，同时保持对公司数据的控制。</span><span class="sxs-lookup"><span data-stu-id="93ed3-104">With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data.</span></span>

<span data-ttu-id="93ed3-105">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="93ed3-105">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="93ed3-106">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="93ed3-106">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="93ed3-107">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="93ed3-107">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="93ed3-108">不属于你的组织的任何人都可作为来宾添加到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="93ed3-108">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="93ed3-109">这意味着拥有商业帐户 (的任何人（如 Azure Active Directory 帐户) 或使用者电子邮件帐户 (具有 Outlook.com、Gmail.com 或其他) ）都可以通过访问团队和频道体验加入到团队中的来宾。</span><span class="sxs-lookup"><span data-stu-id="93ed3-109">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with access to teams and channel experiences.</span></span>

<span data-ttu-id="93ed3-110">作为团队管理员，你可以 [控制来宾可以 (和不能在团队中) 使用的功能](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-110">As the Teams admin, you [control which features guests can (and can't) use in Teams](manage-guests.md).</span></span> <span data-ttu-id="93ed3-111">团队中的来宾受与 Microsoft 365 其余部分相同的合规性和审核保护涵盖，并且可以在 Azure AD 中托管。</span><span class="sxs-lookup"><span data-stu-id="93ed3-111">Guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span> <span data-ttu-id="93ed3-112">来宾访问受到 Azure AD 和 Microsoft 365 或 Office 365 服务限制的约束。</span><span class="sxs-lookup"><span data-stu-id="93ed3-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

<span data-ttu-id="93ed3-113">来宾体验体验在设计上有限制。</span><span class="sxs-lookup"><span data-stu-id="93ed3-113">The guest experience has limitations by design.</span></span> <span data-ttu-id="93ed3-114">有关来宾可以和不能在团队中执行哪些操作的完整列表，请参阅 [团队成员和来宾功能的比较](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-114">For a full list of what a guest can and can't do in Teams, see [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93ed3-115">来宾用户遵循 Teams 组织范围内的共存升级模式设置。</span><span class="sxs-lookup"><span data-stu-id="93ed3-115">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="93ed3-116">此选项无法更改。</span><span class="sxs-lookup"><span data-stu-id="93ed3-116">This can't be changed.</span></span>

<span data-ttu-id="93ed3-117">要将外部访问（联合身份验证）与来宾访问进行比较（并决定应使用哪个），请阅读[与 Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-117">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="set-up-guest-access"></a><span data-ttu-id="93ed3-118">设置来宾访问</span><span class="sxs-lookup"><span data-stu-id="93ed3-118">Set up guest access</span></span>

<span data-ttu-id="93ed3-119">团队中的来宾访问需要在 Microsoft 365 中配置其他设置，包括 Azure AD、Microsoft 365 组和 SharePoint 中的设置。</span><span class="sxs-lookup"><span data-stu-id="93ed3-119">Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Azure AD, Microsoft 365 Groups, and SharePoint.</span></span> <span data-ttu-id="93ed3-120">如果你已准备好开始邀请团队加入团队，请阅读下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="93ed3-120">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="93ed3-121">若要为团队配置常规使用的来宾访问，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-121">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="93ed3-122">若要与使用 Azure Active Directory 的合作伙伴组织进行协作，并允许来宾自行注册团队访问，请参阅 [使用托管来宾创建 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-122">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="93ed3-123">团队中的来宾访问权限是组织范围的设置，默认情况下处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="93ed3-123">Guest access in Teams is an organization-wide setting and is turned off by default.</span></span> <span data-ttu-id="93ed3-124">您可以使用 [灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制对单个团队的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="93ed3-124">You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="how-a-guest-becomes-a-member-of-a-team"></a><span data-ttu-id="93ed3-125">来宾如何成为团队成员</span><span class="sxs-lookup"><span data-stu-id="93ed3-125">How a guest becomes a member of a team</span></span>

1. <span data-ttu-id="93ed3-126">团队所有者或 Microsoft 365 管理员 [将来宾添加到团队](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-126">A team owner or a Microsoft 365 admin [adds a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="93ed3-127">来宾会收到一封来自团队所有者的欢迎电子邮件，其中内附团队信息及其现在作为成员应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="93ed3-127">The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're a member.</span></span>
3. <span data-ttu-id="93ed3-128">来宾接受邀请。</span><span class="sxs-lookup"><span data-stu-id="93ed3-128">The guest accepts the invitation.</span></span>
  <span data-ttu-id="93ed3-129">在 Azure Active Directory 中拥有工作或学校帐户的来宾用户可以接受邀请并直接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="93ed3-129">Guest users who have an work or school account in Azure Active Directory can accept the invitation and authenticate directly.</span></span> <span data-ttu-id="93ed3-130">将向其他用户发送一次性传递代码，以验证其身份 () 所需的 [一次性密码验证](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 。</span><span class="sxs-lookup"><span data-stu-id="93ed3-130">Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) required).</span></span>
4. <span data-ttu-id="93ed3-131">接受邀请后，来宾可[参与团队和频道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收和答复频道消息、[访问频道中的文件](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)，还能参与聊天、加入会议并协作处理文档等等。</span><span class="sxs-lookup"><span data-stu-id="93ed3-131">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receive and respond to channel messages, [access files in channels](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.</span></span> 

<span data-ttu-id="93ed3-132">在 Teams 中，可清楚地识别来宾。</span><span class="sxs-lookup"><span data-stu-id="93ed3-132">In Teams, guests are clearly identified.</span></span> <span data-ttu-id="93ed3-133">来宾用户的姓名包含 **(来宾)** 标签，而频道中有一个图标来表示团队中存在来宾。</span><span class="sxs-lookup"><span data-stu-id="93ed3-133">A guest user's name includes the label **(Guest)** , and a channel includes an icon to indicate that there are guests on the team.</span></span> <span data-ttu-id="93ed3-134">有关更多详细信息，请参阅[来宾体验介绍](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-134">For more details, see [What the guest experience is like](guest-experience.md).</span></span>
  
<span data-ttu-id="93ed3-135">来宾可以随时在 Teams 中离开团队。</span><span class="sxs-lookup"><span data-stu-id="93ed3-135">Guests can leave the team at any time from within Teams.</span></span> <span data-ttu-id="93ed3-136">有关详细信息，请参阅[如何离开团队？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span><span class="sxs-lookup"><span data-stu-id="93ed3-136">For details, see  [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span></span>

> [!NOTE]
> <span data-ttu-id="93ed3-137">离开团队不会从你的组织的目录中删除来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="93ed3-137">Leaving the team doesn't remove the guest account from your organization's directory.</span></span> <span data-ttu-id="93ed3-138">这必须由 Microsoft 365 全局管理员或 Azure AD 管理员完成。</span><span class="sxs-lookup"><span data-stu-id="93ed3-138">This must be done by a Microsoft 365 global admin or an Azure AD admin.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="93ed3-139">来宾访问的许可</span><span class="sxs-lookup"><span data-stu-id="93ed3-139">Licensing for guest access</span></span>

<span data-ttu-id="93ed3-140">来宾访问包括在所有 Microsoft 365 商业标准、Microsoft 365 企业版和 Microsoft 365 教育版订阅中。</span><span class="sxs-lookup"><span data-stu-id="93ed3-140">Guest access is included with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions.</span></span> <span data-ttu-id="93ed3-141">不需要额外的 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="93ed3-141">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="93ed3-142">Teams 不对可添加的来宾数量进行限制。</span><span class="sxs-lookup"><span data-stu-id="93ed3-142">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="93ed3-143">但是，可添加到你的租户的来宾总数可能受到 Azure AD 的付费功能的限制。</span><span class="sxs-lookup"><span data-stu-id="93ed3-143">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="93ed3-144">有关详细信息，请参阅 [AZURE AD 外部标识的计费模型](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-144">For more information, see [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="93ed3-145">你的组织中仅有独立 Microsoft 365 订阅计划（如 Exchange Online 计划2）的用户不能被邀请加入你的组织的来宾，因为团队会将这些用户视为属于同一组织。</span><span class="sxs-lookup"><span data-stu-id="93ed3-145">Users in your organization who have standalone Microsoft 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="93ed3-146">要让这些用户使用 Teams，必须向他们分配 Microsoft 365 商业标准版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="93ed3-146">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="guest-access-reviews"></a><span data-ttu-id="93ed3-147">来宾访问评论</span><span class="sxs-lookup"><span data-stu-id="93ed3-147">Guest access reviews</span></span>

<span data-ttu-id="93ed3-148">你可以使用 Azure AD 为组成员或分配到应用程序的用户创建访问审核。</span><span class="sxs-lookup"><span data-stu-id="93ed3-148">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="93ed3-149">创建定期访问评论可节省您的时间。</span><span class="sxs-lookup"><span data-stu-id="93ed3-149">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="93ed3-150">如果需要定期查看有权访问应用程序、团队或组成员的用户，您可以定义这些评审的频率。</span><span class="sxs-lookup"><span data-stu-id="93ed3-150">If you need to routinely review users who have access to an application, a team, or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="93ed3-151">你可以自行执行来宾访问检查、要求来宾查看其自己的成员身份，或者要求应用程序所有者或业务决策人执行访问权审核。</span><span class="sxs-lookup"><span data-stu-id="93ed3-151">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="93ed3-152">使用 Azure 门户执行来宾访问评论。</span><span class="sxs-lookup"><span data-stu-id="93ed3-152">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="93ed3-153">有关详细信息，请参阅 [使用 AZURE AD 访问审核管理来宾访问](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="93ed3-153">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="related-topics"></a><span data-ttu-id="93ed3-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="93ed3-154">Related topics</span></span>

[<span data-ttu-id="93ed3-155">与组织外部的人员进行协作</span><span class="sxs-lookup"><span data-stu-id="93ed3-155">Collaborating with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[<span data-ttu-id="93ed3-156">阻止来自特定 Microsoft 365 组或 Microsoft 团队团队的来宾用户</span><span class="sxs-lookup"><span data-stu-id="93ed3-156">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="93ed3-157">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="93ed3-157">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[<span data-ttu-id="93ed3-158">联系商业版产品的支持人员 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="93ed3-158">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="93ed3-159">配置具有三层保护的团队</span><span class="sxs-lookup"><span data-stu-id="93ed3-159">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
