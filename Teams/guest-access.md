---
title: Microsoft Teams 中的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
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
ms.openlocfilehash: 5b1787d2f310ebf7ed0afafa41e8b730346a54ec
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37565104"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="72825-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="72825-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="72825-104">“来宾访问”是客户需求最强烈的的功能之一。</span><span class="sxs-lookup"><span data-stu-id="72825-104">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="72825-105">你可按此处所述了解来宾访问功能的最新进展并将你的想法告诉我们：</span><span class="sxs-lookup"><span data-stu-id="72825-105">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="72825-106">如果你在使用来宾访问时遇到问题，请查看 [Microsoft Teams 的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="72825-106">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="72825-107">请在 [Teams 路线图](https://aka.ms/teamsroadmap)中了解即将发布的新功能或更新功能。</span><span class="sxs-lookup"><span data-stu-id="72825-107">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="72825-108">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中将你想要的功能告诉我们。</span><span class="sxs-lookup"><span data-stu-id="72825-108">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="72825-109">在下面的“注释”部分中分享你的体验。</span><span class="sxs-lookup"><span data-stu-id="72825-109">Share your experience in the Comments section below.</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="72825-110">来宾访问概述</span><span class="sxs-lookup"><span data-stu-id="72825-110">Guest access overview</span></span>

<span data-ttu-id="72825-111">借助“来宾访问”功能，你组织中的团队可通过在你的一个或多个租户中向组织外部人员授予现有团队和频道的访问权限，与他们进行协作。</span><span class="sxs-lookup"><span data-stu-id="72825-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="72825-112">具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="72825-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="72825-113">许多 Office 365 订阅都包含来宾访问功能，而无额外的许可要求。</span><span class="sxs-lookup"><span data-stu-id="72825-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="72825-114">有关许可的详细信息，请参阅 [Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="72825-114">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="72825-115">来宾访问是 Microsoft Teams 中的租户级别设置且默认关闭。</span><span class="sxs-lookup"><span data-stu-id="72825-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="72825-116">来宾访问受制于 Azure AD 和 Office 365 服务限制。</span><span class="sxs-lookup"><span data-stu-id="72825-116">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="72825-117">你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。</span><span class="sxs-lookup"><span data-stu-id="72825-117">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="72825-118">要让这些用户使用 Teams，必须向他们分配 Office 365 商业高级版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="72825-118">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="72825-119">来宾具体是什么？</span><span class="sxs-lookup"><span data-stu-id="72825-119">Who is a guest?</span></span>

<span data-ttu-id="72825-120">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="72825-120">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="72825-121">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="72825-121">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="72825-122">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="72825-122">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="72825-123">不属于你的组织的任何人都可作为来宾添加到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="72825-123">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="72825-124">这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。</span><span class="sxs-lookup"><span data-stu-id="72825-124">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="72825-125">（有关来宾限制，可参阅[在 Microsoft Teams 中授予来宾访问权限](teams-dependencies.md)。）Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。</span><span class="sxs-lookup"><span data-stu-id="72825-125">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="72825-126">为何要使用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="72825-126">Why use guest access?</span></span>

<span data-ttu-id="72825-127">借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="72825-127">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="72825-128">Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。</span><span class="sxs-lookup"><span data-stu-id="72825-128">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="72825-129">Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。</span><span class="sxs-lookup"><span data-stu-id="72825-129">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="72825-130">Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="72825-130">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="72825-131">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="72825-131">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="72825-132">与外部访问（联合身份验证）相比，来宾访问如何？</span><span class="sxs-lookup"><span data-stu-id="72825-132">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="72825-133">详细信息</span><span class="sxs-lookup"><span data-stu-id="72825-133">More information</span></span>

[<span data-ttu-id="72825-134">联系商业版产品的支持人员 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="72825-134">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="72825-135">Office 365 组的来宾访问</span><span class="sxs-lookup"><span data-stu-id="72825-135">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
