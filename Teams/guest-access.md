---
title: Microsoft Teams 中的来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59cd4e06d3a5a98298d67fcfbb785efb371fe0f0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458825"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="13955-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="13955-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="13955-104">来宾访问概述</span><span class="sxs-lookup"><span data-stu-id="13955-104">Guest access overview</span></span>

<span data-ttu-id="13955-105">来宾访问是最客户要求的功能之一。</span><span class="sxs-lookup"><span data-stu-id="13955-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="13955-106">下面是如何及时来宾访问我们的进度并告诉我们您的想法：</span><span class="sxs-lookup"><span data-stu-id="13955-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="13955-107">如果你在使用来宾访问时遇到问题，请查看 [Microsoft Teams 的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="13955-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="13955-108">请在 [Teams 路线图](https://aka.ms/teamsroadmap)中了解即将发布的新功能或更新功能。</span><span class="sxs-lookup"><span data-stu-id="13955-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="13955-109">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中将你想要的功能告诉我们。</span><span class="sxs-lookup"><span data-stu-id="13955-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="13955-110">在下面的“注释”部分中分享你的体验。</span><span class="sxs-lookup"><span data-stu-id="13955-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="13955-111">来宾访问允许组织中要向其授予对现有团队和上一个或多个租户的频道的访问通过与组织外部的人员进行协作的团队。</span><span class="sxs-lookup"><span data-stu-id="13955-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="13955-112">具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="13955-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="13955-113">来宾访问随所有 Office 365 企业高级版、 Office 365 Enterprise 和 Office 365 教育版订阅与任何其他的许可要求。</span><span class="sxs-lookup"><span data-stu-id="13955-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="13955-114">每个许可用户最多 5 来宾会对您的租户。</span><span class="sxs-lookup"><span data-stu-id="13955-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="13955-115">有关许可的详细信息，请参阅[Azure Active Directory B2B 协作许可指南](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="13955-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="13955-116">来宾访问是 Microsoft Teams 中的租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="13955-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="13955-117">来宾访问受 Azure AD 和 Office 365 服务限制。</span><span class="sxs-lookup"><span data-stu-id="13955-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="13955-118">组织中的拥有独立 Office 365 订阅计划仅，例如 Exchange Online 计划 2，用户不能为您的组织的来宾邀请，因为团队考虑这些用户属于同一组织。</span><span class="sxs-lookup"><span data-stu-id="13955-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="13955-119">这些用户使用团队，它们必须分配的 Office 365 企业高级版、 Office 365 企业版或 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="13955-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="13955-120">谁是来宾？</span><span class="sxs-lookup"><span data-stu-id="13955-120">Who is a guest?</span></span>

<span data-ttu-id="13955-121">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="13955-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="13955-122">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="13955-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="13955-123">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="13955-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="13955-124">不属于您的组织的任何人都可以作为来宾团队中添加。</span><span class="sxs-lookup"><span data-stu-id="13955-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="13955-125">这意味着与业务帐户 （即，Azure Active Directory 帐户） 或使用者电子邮件帐户 （以及 Outlook.com、 Gmail.com 或其他） 的任何人都可以参与作为来宾团队中具有完全访问权限的团队和通道体验。</span><span class="sxs-lookup"><span data-stu-id="13955-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="13955-126">（您可以了解有关[授权来宾访问中的 Microsoft 团队](teams-dependencies.md)中的来宾限制。）团队中的所有来宾涵盖的相同的遵从性和审核保护 Office 365 的其余部分和 Azure AD 中可以安全地进行管理。</span><span class="sxs-lookup"><span data-stu-id="13955-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="13955-127">为什么使用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="13955-127">Why use guest access?</span></span>
      
<span data-ttu-id="13955-128">使用来宾访问使用团队的组织可以同时维护自己公司数据的完全控制提供对团队、 文档中的通道、 资源、 聊天和到他们的合作伙伴应用程序的外部访问。</span><span class="sxs-lookup"><span data-stu-id="13955-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="13955-129">团队中的所有来宾都涵盖的相同的遵从性和 Office 365 的其余部分的审核保护并来宾可以安全地管理 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="13955-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="13955-130">团队基于 Office 365 组，并提供访问 Office 365 组共享的资产的新方法。</span><span class="sxs-lookup"><span data-stu-id="13955-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="13955-131">Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="13955-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="13955-132">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="13955-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="13955-133">来宾访问比较外部访问 （联合身份验证）？</span><span class="sxs-lookup"><span data-stu-id="13955-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="13955-134">更多信息</span><span class="sxs-lookup"><span data-stu-id="13955-134">More information</span></span>
    
[<span data-ttu-id="13955-135">Microsoft Teams 的支持资源</span><span class="sxs-lookup"><span data-stu-id="13955-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="13955-136">Office 365 组中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="13955-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="13955-137">来宾访问简介</span><span class="sxs-lookup"><span data-stu-id="13955-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="13955-138">深入了解来宾访问</span><span class="sxs-lookup"><span data-stu-id="13955-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="13955-139">在 Microsoft 团队中添加来宾</span><span class="sxs-lookup"><span data-stu-id="13955-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

