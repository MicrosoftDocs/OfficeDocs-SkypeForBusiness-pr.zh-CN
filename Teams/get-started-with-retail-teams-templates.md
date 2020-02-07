---
title: 开始使用 Teams 零售模板
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用团队模板创建针对零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31c6b04531b21996f897b3d668fdb6515f1e953f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836812"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="2518a-103">开始使用 Teams 零售模板</span><span class="sxs-lookup"><span data-stu-id="2518a-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="2518a-104">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="2518a-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="2518a-105">团队模板具有围绕零售商需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="2518a-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="2518a-106">你可以使用团队模板快速创建适用于零售商的团队类型，并在组织中部署这些团队。</span><span class="sxs-lookup"><span data-stu-id="2518a-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="2518a-107">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="2518a-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="2518a-108">在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="2518a-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="2518a-109">本文适用于您负责在您的零售组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="2518a-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="2518a-110">我们假定你的组织中已部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="2518a-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="2518a-111">如果尚未推出团队，请先阅读[如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2518a-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="2518a-112">若要深入了解有关团队模板的详细信息，请参阅[团队模板入门](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2518a-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="2518a-113">存储模板</span><span class="sxs-lookup"><span data-stu-id="2518a-113">Store template</span></span>

<span data-ttu-id="2518a-114">应用商店模板是创建团队以表示单个零售商店位置的理想之选。</span><span class="sxs-lookup"><span data-stu-id="2518a-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="2518a-115">使用应用商店模板，您可以为您的组织中的每个零售商店位置创建一个团队。</span><span class="sxs-lookup"><span data-stu-id="2518a-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="2518a-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="2518a-116">Base template type</span></span> | <span data-ttu-id="2518a-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2518a-117">baseTemplateId</span></span> | <span data-ttu-id="2518a-118">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="2518a-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="2518a-119">面向</span><span class="sxs-lookup"><span data-stu-id="2518a-119">Retail -</span></span> <br><span data-ttu-id="2518a-120">储存</span><span class="sxs-lookup"><span data-stu-id="2518a-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="2518a-121">频道</span><span class="sxs-lookup"><span data-stu-id="2518a-121">Channels</span></span> <ul><li><span data-ttu-id="2518a-122">班次切换\*</span><span class="sxs-lookup"><span data-stu-id="2518a-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="2518a-123">培训\*</span><span class="sxs-lookup"><span data-stu-id="2518a-123">Learning\*</span></span></li></ul><span data-ttu-id="2518a-124">\*自动收藏频道</span><span class="sxs-lookup"><span data-stu-id="2518a-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="2518a-125">团队属性</span><span class="sxs-lookup"><span data-stu-id="2518a-125">Team properties</span></span> <ul><li><span data-ttu-id="2518a-126">将团队可见性设置为公共</span><span class="sxs-lookup"><span data-stu-id="2518a-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="2518a-127">成员权限</span><span class="sxs-lookup"><span data-stu-id="2518a-127">Member permissions</span></span> <ul><li><span data-ttu-id="2518a-128">无法创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="2518a-128">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="2518a-129">无法添加/删除应用程序</span><span class="sxs-lookup"><span data-stu-id="2518a-129">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="2518a-130">无法创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="2518a-130">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="2518a-131">无法创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="2518a-131">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="2518a-132">为你的组织自定义应用商店模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="2518a-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="2518a-133">如果您的组织在每个商店中都有部门，请为每个部门添加一个频道。</span><span class="sxs-lookup"><span data-stu-id="2518a-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="2518a-134">这将促进部门内的沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="2518a-134">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="2518a-135">如果您的组织具有任何内部网站（例如，SharePoint 网站），请考虑将它们固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="2518a-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="2518a-136">有关说明，请参阅[团队模板入门](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2518a-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="2518a-137">经理协作模板</span><span class="sxs-lookup"><span data-stu-id="2518a-137">Manager Collaboration template</span></span>

<span data-ttu-id="2518a-138">经理协作模板是围绕零售商的需求而设计的另一个团队模板。</span><span class="sxs-lookup"><span data-stu-id="2518a-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="2518a-139">经理协作模板非常适合为一组经理创建团队，以便在商店/地区等协作。例如，如果您的组织拥有区域，则可以为加利福尼亚地区创建经理协作团队，并包括该地区的所有商店经理以及该地区的地区经理。</span><span class="sxs-lookup"><span data-stu-id="2518a-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="2518a-140">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="2518a-140">Base template type</span></span> | <span data-ttu-id="2518a-141">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2518a-141">baseTemplateId</span></span> | <span data-ttu-id="2518a-142">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="2518a-142">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="2518a-143">面向</span><span class="sxs-lookup"><span data-stu-id="2518a-143">Retail -</span></span> <br><span data-ttu-id="2518a-144">储存</span><span class="sxs-lookup"><span data-stu-id="2518a-144">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="2518a-145">频道</span><span class="sxs-lookup"><span data-stu-id="2518a-145">Channels</span></span> <ul><li><span data-ttu-id="2518a-146">运营\*</span><span class="sxs-lookup"><span data-stu-id="2518a-146">Operations\*</span></span></li><li><span data-ttu-id="2518a-147">培训\*</span><span class="sxs-lookup"><span data-stu-id="2518a-147">Learning\*</span></span></li></ul><span data-ttu-id="2518a-148">\*自动收藏频道</span><span class="sxs-lookup"><span data-stu-id="2518a-148">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="2518a-149">团队属性</span><span class="sxs-lookup"><span data-stu-id="2518a-149">Team properties</span></span> <ul><li><span data-ttu-id="2518a-150">将团队可见性设置为私密</span><span class="sxs-lookup"><span data-stu-id="2518a-150">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="2518a-151">成员权限</span><span class="sxs-lookup"><span data-stu-id="2518a-151">Member permissions</span></span> <ul><li><span data-ttu-id="2518a-152">可以创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="2518a-152">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="2518a-153">可以添加/删除应用程序</span><span class="sxs-lookup"><span data-stu-id="2518a-153">Can add/remove apps</span></span> </li><li><span data-ttu-id="2518a-154">可以创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="2518a-154">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="2518a-155">可以创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="2518a-155">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="2518a-156">为你的组织自定义经理协作模板的推荐方法：</span><span class="sxs-lookup"><span data-stu-id="2518a-156">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="2518a-157">如果您的组织具有与经理相关的任何内部网站（例如 SharePoint 网站），请考虑将它们固定为相关团队频道中的选项卡（有关说明，请参阅[此处](get-started-with-teams-templates.md)的文档）。</span><span class="sxs-lookup"><span data-stu-id="2518a-157">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>
