---
title: Microsoft Teams 中的来宾访问
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
search.appverid: MET150
description: 利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: d8f5c5d0af754321770a47944d8f95db5ec573fd
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016818"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="5b62b-103">Microsoft Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="5b62b-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="5b62b-104">来宾访问在 Teams 中是新功能。</span><span class="sxs-lookup"><span data-stu-id="5b62b-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="5b62b-105">这是客户需求最强烈的的功能之一。</span><span class="sxs-lookup"><span data-stu-id="5b62b-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="5b62b-106">我们仍在努力增强其功能。</span><span class="sxs-lookup"><span data-stu-id="5b62b-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="5b62b-107">你可以按此处所述了解来宾访问功能的最新进展并将你的想法告诉我们：</span><span class="sxs-lookup"><span data-stu-id="5b62b-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="5b62b-108">如果你在使用来宾访问时遇到问题，请查看 [Microsoft Teams 的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="5b62b-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="5b62b-109">请在 [Teams 路线图](https://aka.ms/teamsroadmap)中了解即将发布的新功能或更新功能。</span><span class="sxs-lookup"><span data-stu-id="5b62b-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="5b62b-110">请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中将你想要的功能告诉我们。</span><span class="sxs-lookup"><span data-stu-id="5b62b-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="5b62b-111">在下面的“注释”部分中分享你的体验。</span><span class="sxs-lookup"><span data-stu-id="5b62b-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="5b62b-112">利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。</span><span class="sxs-lookup"><span data-stu-id="5b62b-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="5b62b-113">具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以参与作为来宾团队中具有到团队聊天、 会议和文件的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="5b62b-113">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="5b62b-114">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="5b62b-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="5b62b-115">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="5b62b-115">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="5b62b-116">来宾访问是 Microsoft Teams 中的租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="5b62b-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>



<span data-ttu-id="5b62b-117">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="5b62b-117">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="5b62b-118">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="5b62b-118">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="5b62b-119">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="5b62b-119">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="5b62b-120">任何人都可以作为来宾中的 Microsoft 团队添加。</span><span class="sxs-lookup"><span data-stu-id="5b62b-120">Anyone can be added as guest in Microsoft Teams.</span></span> <span data-ttu-id="5b62b-121">这意味着与业务 （使用 Azure Active Directory 帐户） 或使用者电子邮件帐户 （以及 Outlook.com、 Gmail.com 或其他） 的任何人都可以参与作为来宾团队中具有到团队聊天、 会议和文件的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="5b62b-121">This means that anyone with a business (with an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams with full access to teams chats, meetings and files.</span></span>
<span data-ttu-id="5b62b-122">团队中的所有来宾涵盖的相同的遵从性和审核保护 Office 365 的其余部分和 Azure AD 中可以安全地进行管理。</span><span class="sxs-lookup"><span data-stu-id="5b62b-122">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

> [!NOTE]
> <span data-ttu-id="5b62b-123">贵组织中具有独立 Office 365 订阅计划仅，例如 Exchange Online 计划 2，无法邀请用户为您的组织的来宾自从团队考虑这些用户属于同一组织。</span><span class="sxs-lookup"><span data-stu-id="5b62b-123">Users in your organization with standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guest to your organization since Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="5b62b-124">这些用户使用团队，它们必须分配 Office 365 企业高级版、 Office 365 Enterprise 和 Office 365 教育版订阅。</span><span class="sxs-lookup"><span data-stu-id="5b62b-124">For these users to use Teams, they must be assigned with Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span>  
      

<span data-ttu-id="5b62b-125">使用 Teams 的组织可以向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="5b62b-125">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="5b62b-126">团队中的所有来宾都涵盖的相同的遵从性和 Office 365 的其余部分的审核保护并来宾可以安全地管理 Azure Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="5b62b-126">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure Active Directory.</span></span>  

<span data-ttu-id="5b62b-127">Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。</span><span class="sxs-lookup"><span data-stu-id="5b62b-127">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="5b62b-128">Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="5b62b-128">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="5b62b-129">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="5b62b-129">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="5b62b-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="5b62b-130">More information</span></span>

 
  
    
  [<span data-ttu-id="5b62b-131">Microsoft Teams 的支持资源</span><span class="sxs-lookup"><span data-stu-id="5b62b-131">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="5b62b-132">深入了解来宾访问</span><span class="sxs-lookup"><span data-stu-id="5b62b-132">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="5b62b-133">在 Microsoft Teams 中启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="5b62b-133">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="5b62b-134">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="5b62b-134">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

