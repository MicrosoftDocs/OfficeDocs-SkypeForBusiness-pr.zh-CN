---
title: 开始使用 Teams 零售模板
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用工作组模板创建团队结构设计零售商需求。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245743"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="71bc8-103">开始使用 Teams 零售模板</span><span class="sxs-lookup"><span data-stu-id="71bc8-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="71bc8-104">工作组模板允许您快速和轻松创建团队提供的预定义的模板的设置、 通道和预安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="71bc8-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="71bc8-105">工作组模板具有预建的团队结构围绕零售商需求而设计的定义。</span><span class="sxs-lookup"><span data-stu-id="71bc8-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="71bc8-106">工作组模板可用于快速创建适用于零售商并将它们部署在整个组织的团队的类型。</span><span class="sxs-lookup"><span data-stu-id="71bc8-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="71bc8-107">您还可以扩展工作组模板创建适合您组织的特定需求的团队。</span><span class="sxs-lookup"><span data-stu-id="71bc8-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="71bc8-108">本文中，我们将介绍每个工作组模板和我们建议使用它们。</span><span class="sxs-lookup"><span data-stu-id="71bc8-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="71bc8-109">本文适用于您，如果您是负责规划、 部署和管理多个团队整个组织零售。</span><span class="sxs-lookup"><span data-stu-id="71bc8-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span>

<span data-ttu-id="71bc8-110">若要详细了解团队模板通常情况下，请参阅[入门工作组模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="71bc8-110">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="71bc8-111">存储模板</span><span class="sxs-lookup"><span data-stu-id="71bc8-111">Store template</span></span>

<span data-ttu-id="71bc8-112">存储模板非常适合于创建团队表示单个零售存储位置。</span><span class="sxs-lookup"><span data-stu-id="71bc8-112">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="71bc8-113">使用存储模板时，可以创建您的组织中的每个零售店铺团队。</span><span class="sxs-lookup"><span data-stu-id="71bc8-113">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="71bc8-114">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="71bc8-114">Base template type</span></span> | <span data-ttu-id="71bc8-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="71bc8-115">baseTemplateId</span></span> | <span data-ttu-id="71bc8-116">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="71bc8-116">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="71bc8-117">零售-</span><span class="sxs-lookup"><span data-stu-id="71bc8-117">Retail -</span></span> <br><span data-ttu-id="71bc8-118">存储</span><span class="sxs-lookup"><span data-stu-id="71bc8-118">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="71bc8-119">频道</span><span class="sxs-lookup"><span data-stu-id="71bc8-119">Channels</span></span> <ul><li><span data-ttu-id="71bc8-120">引进提交\*</span><span class="sxs-lookup"><span data-stu-id="71bc8-120">Shifts handoff\*</span></span></li><li><span data-ttu-id="71bc8-121">学习\*</span><span class="sxs-lookup"><span data-stu-id="71bc8-121">Learning\*</span></span></li></ul><span data-ttu-id="71bc8-122">\*自动 favorited 通道</span><span class="sxs-lookup"><span data-stu-id="71bc8-122">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="71bc8-123">团队属性</span><span class="sxs-lookup"><span data-stu-id="71bc8-123">Team properties</span></span> <ul><li><span data-ttu-id="71bc8-124">设置为 Public 工作组可见性</span><span class="sxs-lookup"><span data-stu-id="71bc8-124">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="71bc8-125">成员权限</span><span class="sxs-lookup"><span data-stu-id="71bc8-125">Member permissions</span></span> <ul><li><span data-ttu-id="71bc8-126">无法创建/更新/删除通道</span><span class="sxs-lookup"><span data-stu-id="71bc8-126">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="71bc8-127">无法添加/删除应用程序</span><span class="sxs-lookup"><span data-stu-id="71bc8-127">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="71bc8-128">无法创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="71bc8-128">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="71bc8-129">无法创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="71bc8-129">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="71bc8-130">建议使用自定义您的组织的存储区模板的方法：</span><span class="sxs-lookup"><span data-stu-id="71bc8-130">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="71bc8-131">如果您的组织内每个存储有部门，添加为每个部门的通道。</span><span class="sxs-lookup"><span data-stu-id="71bc8-131">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="71bc8-132">这将有助于通信和部门的协作。</span><span class="sxs-lookup"><span data-stu-id="71bc8-132">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="71bc8-133">如果您的组织有任何内部网站 （例如，SharePoint 网站），请考虑这些固定用作相关团队通道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="71bc8-133">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="71bc8-134">有关说明，请参阅[入门工作组模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="71bc8-134">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="71bc8-135">管理器协作模板</span><span class="sxs-lookup"><span data-stu-id="71bc8-135">Manager Collaboration template</span></span>

<span data-ttu-id="71bc8-136">另一个设计零售商周围的工作组模板需要的管理器协作模板。</span><span class="sxs-lookup"><span data-stu-id="71bc8-136">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="71bc8-137">管理器协作模板非常适合于创建一组管理跨存储/地区等协作的团队。例如，如果您的组织具有区域，您可能为加利福尼亚地区创建管理器协作工作组和包括在该区域中，所有存储区管理器，以及为该区域的区域管理器。</span><span class="sxs-lookup"><span data-stu-id="71bc8-137">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="71bc8-138">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="71bc8-138">Base template type</span></span> | <span data-ttu-id="71bc8-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="71bc8-139">baseTemplateId</span></span> | <span data-ttu-id="71bc8-140">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="71bc8-140">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="71bc8-141">零售-</span><span class="sxs-lookup"><span data-stu-id="71bc8-141">Retail -</span></span> <br><span data-ttu-id="71bc8-142">存储</span><span class="sxs-lookup"><span data-stu-id="71bc8-142">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="71bc8-143">频道</span><span class="sxs-lookup"><span data-stu-id="71bc8-143">Channels</span></span> <ul><li><span data-ttu-id="71bc8-144">运营\*</span><span class="sxs-lookup"><span data-stu-id="71bc8-144">Operations\*</span></span></li><li><span data-ttu-id="71bc8-145">学习\*</span><span class="sxs-lookup"><span data-stu-id="71bc8-145">Learning\*</span></span></li></ul><span data-ttu-id="71bc8-146">\*自动 favorited 通道</span><span class="sxs-lookup"><span data-stu-id="71bc8-146">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="71bc8-147">团队属性</span><span class="sxs-lookup"><span data-stu-id="71bc8-147">Team properties</span></span> <ul><li><span data-ttu-id="71bc8-148">设置为 Private 工作组可见性</span><span class="sxs-lookup"><span data-stu-id="71bc8-148">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="71bc8-149">成员权限</span><span class="sxs-lookup"><span data-stu-id="71bc8-149">Member permissions</span></span> <ul><li><span data-ttu-id="71bc8-150">可以创建/更新/删除通道</span><span class="sxs-lookup"><span data-stu-id="71bc8-150">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="71bc8-151">可以添加/删除应用程序</span><span class="sxs-lookup"><span data-stu-id="71bc8-151">Can add/remove apps</span></span> </li><li><span data-ttu-id="71bc8-152">可以创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="71bc8-152">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="71bc8-153">可以创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="71bc8-153">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="71bc8-154">建议使用自定义您的组织的管理器协作模板的方法：</span><span class="sxs-lookup"><span data-stu-id="71bc8-154">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="71bc8-155">如果您的组织相关经理任何内部网站 （例如，SharePoint 网站），请考虑这些固定用作相关团队通道中的选项卡 (参考文档[此处](get-started-with-teams-templates.md)的说明)。</span><span class="sxs-lookup"><span data-stu-id="71bc8-155">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>