---
title: "Microsoft Teams 的 Office 365 相关性"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams 依赖 Office 365 组、SharePoint Online 和 OneDrive for Business。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a><span data-ttu-id="75a40-103">Microsoft Teams 的 Office 365 相关性</span><span class="sxs-lookup"><span data-stu-id="75a40-103">Office 365 dependencies for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="75a40-104">Microsoft Teams 依赖 Office 365 组存储团队的成员身份和其他属性，例如，团队数据分类设置。</span><span class="sxs-lookup"><span data-stu-id="75a40-104">Microsoft Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="75a40-105">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="75a40-105">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

<span data-ttu-id="75a40-106">Teams 还依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="75a40-106">Teams also relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="75a40-107">此外，Teams 还依赖 Office 365 组存储团队的成员身份和其他属性，例如，团队数据分类设置。</span><span class="sxs-lookup"><span data-stu-id="75a40-107">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="75a40-108">来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="75a40-108">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    
<span data-ttu-id="75a40-109">为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择**“开启”**：</span><span class="sxs-lookup"><span data-stu-id="75a40-109">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="75a40-110">在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**</span><span class="sxs-lookup"><span data-stu-id="75a40-110">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="75a40-111">有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)。</span><span class="sxs-lookup"><span data-stu-id="75a40-111">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="75a40-112">在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="75a40-112">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="75a40-113">有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。</span><span class="sxs-lookup"><span data-stu-id="75a40-113">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="75a40-114">你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="75a40-114">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="75a40-115">有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="75a40-115">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>