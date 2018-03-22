---
title: Microsoft Teams 中的来宾访问
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ac614aa35e3aa453a7522559e6fda8045404ae9
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="daad7-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="daad7-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="daad7-104">来宾访问在 Teams 中是新功能。</span><span class="sxs-lookup"><span data-stu-id="daad7-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="daad7-105">这是客户需求最强烈的的功能之一。</span><span class="sxs-lookup"><span data-stu-id="daad7-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="daad7-106">我们仍在努力增强其功能。</span><span class="sxs-lookup"><span data-stu-id="daad7-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="daad7-107">你可以按此处所述了解来宾访问功能的最新进展并将你的想法告诉我们：</span><span class="sxs-lookup"><span data-stu-id="daad7-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="daad7-108">如果你在使用来宾访问时遇到问题，请查看 [Microsoft Teams 的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="daad7-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="daad7-109">请在 [Teams 路线图](https://aka.ms/teamsroadmap)中了解即将发布的新功能或更新功能。</span><span class="sxs-lookup"><span data-stu-id="daad7-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="daad7-110">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中将你想要的功能告诉我们。</span><span class="sxs-lookup"><span data-stu-id="daad7-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="daad7-111">在下面的“注释”部分中分享你的体验。</span><span class="sxs-lookup"><span data-stu-id="daad7-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="daad7-112">利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。</span><span class="sxs-lookup"><span data-stu-id="daad7-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="daad7-113">具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他人，任何人都可以参与以访客身份在团队中小组研讨、 会议和文件的完全访问。</span><span class="sxs-lookup"><span data-stu-id="daad7-113">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="daad7-114">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="daad7-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="daad7-115">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="daad7-115">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="daad7-116">来宾访问是 Microsoft Teams 中的租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="daad7-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>



<span data-ttu-id="daad7-117">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="daad7-117">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="daad7-118">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="daad7-118">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="daad7-119">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="daad7-119">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="daad7-120">任何人都可以添加以来宾身份在 Microsoft 小组。</span><span class="sxs-lookup"><span data-stu-id="daad7-120">Anyone can be added as guest in Microsoft Teams.</span></span> <span data-ttu-id="daad7-121">这意味着与业务 （使用 Azure Active Directory 帐户） 或使用者的电子邮件帐户 （使用 Outlook.com、 Gmail.com 或其他人） 的任何人都可以参与以访客身份在团队中具有完全访问权限的团队交谈、 会议和文件。</span><span class="sxs-lookup"><span data-stu-id="daad7-121">This means that anyone with a business (with an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams with full access to teams chats, meetings and files.</span></span>
<span data-ttu-id="daad7-122">在团队中的所有来宾受相同的法规遵从性和审核保护 Office 365 的其余部分，并可以在 Azure 广告内安全地管理。</span><span class="sxs-lookup"><span data-stu-id="daad7-122">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

  
      

<span data-ttu-id="daad7-123">使用 Teams 的组织可以向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="daad7-123">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="daad7-124">相同的法规遵从性和审核保护 Office 365 的其余部分被覆盖在团队中的所有客人，客人可以在 Azure Active Directory 中安全地管理。</span><span class="sxs-lookup"><span data-stu-id="daad7-124">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure Active Directory.</span></span>  

<span data-ttu-id="daad7-125">Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。</span><span class="sxs-lookup"><span data-stu-id="daad7-125">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="daad7-126">Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="daad7-126">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="daad7-127">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="daad7-127">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="daad7-128">更多信息</span><span class="sxs-lookup"><span data-stu-id="daad7-128">More information</span></span>

 
  
    
  [<span data-ttu-id="daad7-129">Microsoft Teams 的支持资源</span><span class="sxs-lookup"><span data-stu-id="daad7-129">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="daad7-130">深入了解来宾访问</span><span class="sxs-lookup"><span data-stu-id="daad7-130">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="daad7-131">在 Microsoft Teams 中启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="daad7-131">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="daad7-132">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="daad7-132">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

