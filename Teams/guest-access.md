---
title: Microsoft Teams 中的来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
localization_priority: Normal
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae1f3149ca915e2fd5a9ddf59fdb0bfad2be2ca2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235560"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="efd83-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="efd83-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="efd83-104">来宾访问概述</span><span class="sxs-lookup"><span data-stu-id="efd83-104">Guest access overview</span></span>

<span data-ttu-id="efd83-105">“来宾访问”是客户需求最强烈的的功能之一。</span><span class="sxs-lookup"><span data-stu-id="efd83-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="efd83-106">你可按此处所述了解来宾访问功能的最新进展并将你的想法告诉我们：</span><span class="sxs-lookup"><span data-stu-id="efd83-106">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>

- <span data-ttu-id="efd83-107">如果你在使用来宾访问时遇到问题，请查看 [Microsoft Teams 的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="efd83-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="efd83-108">请在 [Teams 路线图](https://aka.ms/teamsroadmap)中了解即将发布的新功能或更新功能。</span><span class="sxs-lookup"><span data-stu-id="efd83-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="efd83-109">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中将你想要的功能告诉我们。</span><span class="sxs-lookup"><span data-stu-id="efd83-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="efd83-110">在下面的“注释”部分中分享你的体验。</span><span class="sxs-lookup"><span data-stu-id="efd83-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="efd83-111">借助“来宾访问”功能，你组织中的团队可通过在你的一个或多个租户中向组织外部人员授予现有团队和频道的访问权限，与他们进行协作。</span><span class="sxs-lookup"><span data-stu-id="efd83-111">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="efd83-112">具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="efd83-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see Guest access in Microsoft Teams.</span></span>

<span data-ttu-id="efd83-113">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能（没有额外的许可要求）。</span><span class="sxs-lookup"><span data-stu-id="efd83-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="efd83-114">最多可租户上对每个许可用户添加 5 名来宾。</span><span class="sxs-lookup"><span data-stu-id="efd83-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="efd83-115">有关许可的详细信息，请参阅 [Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="efd83-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/zh-CN/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="efd83-116">来宾访问是 Microsoft Teams 中的租户级别设置且默认关闭。</span><span class="sxs-lookup"><span data-stu-id="efd83-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="efd83-117">来宾访问受制于 Azure AD 和 Office 365 服务限制。</span><span class="sxs-lookup"><span data-stu-id="efd83-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="efd83-118">你组织中仅拥有独立 Office 365 订阅计划（例如 Exchange Online 计划 2）的用户不可作为来宾被邀请加入你的组织，因为 Teams 将这些用户视为属于该组织。</span><span class="sxs-lookup"><span data-stu-id="efd83-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="efd83-119">要让这些用户使用 Teams，必须向他们分配 Office 365 商业高级版、Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="efd83-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="efd83-120">来宾具体是什么？</span><span class="sxs-lookup"><span data-stu-id="efd83-120">Who is a guest?</span></span>

<span data-ttu-id="efd83-121">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="efd83-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="efd83-122">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="efd83-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="efd83-123">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="efd83-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="efd83-124">不属于你的组织的任何人都可作为来宾添加到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="efd83-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="efd83-125">这意味着具有业务帐户（即 Azure Active Directory 帐户）或客户电子邮件帐户（带有 Outlook.com 和 Gmail.com 等）的任何人都可作为来宾参与 Teams，并且可完全访问团队和频道体验。</span><span class="sxs-lookup"><span data-stu-id="efd83-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="efd83-126">（有关来宾限制，可参阅[在 Microsoft Teams 中授予来宾访问权限](teams-dependencies.md)。）Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。</span><span class="sxs-lookup"><span data-stu-id="efd83-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="efd83-127">为何要使用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="efd83-127">Why use guest access?</span></span>
      
<span data-ttu-id="efd83-128">借助来宾访问权限，使用 Teams 的组织可向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="efd83-128">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="efd83-129">Teams 中的所有来宾与其他 Office 365 产品享受同样的合规性和审核保护，而且可在 Azure AD 中安全托管。</span><span class="sxs-lookup"><span data-stu-id="efd83-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="efd83-130">Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。</span><span class="sxs-lookup"><span data-stu-id="efd83-130">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="efd83-131">Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="efd83-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="efd83-132">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="efd83-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="efd83-133">与外部访问（联合身份验证）相比，来宾访问如何？</span><span class="sxs-lookup"><span data-stu-id="efd83-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="efd83-134">详细信息</span><span class="sxs-lookup"><span data-stu-id="efd83-134">More information</span></span>
    
<span data-ttu-id="efd83-135">[联系商业版产品的支持人员 - 管理员帮助](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="efd83-135">[Contact support for business products - Admin Help](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>  
<span data-ttu-id="efd83-136">
  [Office 365 组的来宾访问](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span><span class="sxs-lookup"><span data-stu-id="efd83-136">[Guest access in Office 365 Groups](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span></span> 
  
|  |  |
|---------|---------|
|<span data-ttu-id="efd83-137">来宾访问简介</span><span class="sxs-lookup"><span data-stu-id="efd83-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="efd83-138">深入了解来宾访问</span><span class="sxs-lookup"><span data-stu-id="efd83-138">Deep dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="efd83-139">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="efd83-139">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

