---
title: 开始使用 Teams 零售模板
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Teams 模板提供预定义的设置、频道和预安装的应用，从而创建针对零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101198"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="3f4c4-103">开始使用 Teams 零售模板</span><span class="sxs-lookup"><span data-stu-id="3f4c4-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="3f4c4-104">Teams 模板提供预定义的设置、频道和预安装的应用模板，让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3f4c4-105">Teams 模板具有预先构建的围绕零售商需求设计的团队结构定义。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="3f4c4-106">可使用 Teams 模板快速创建适用于零售商的团队类型，并在整个组织中部署它们。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="3f4c4-107">你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3f4c4-108">在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="3f4c4-109">如果你负责在整个零售组织中规划、部署和管理多个团队，则本文非常适合你。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="3f4c4-110">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="3f4c4-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="3f4c4-112">若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="3f4c4-113">商店模板</span><span class="sxs-lookup"><span data-stu-id="3f4c4-113">Store template</span></span>

<span data-ttu-id="3f4c4-114">商店模板非常适合用于创建一个团队来代表单个零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="3f4c4-115">通过使用商店模板，你可以为组织中的每个零售商店位置创建一个团队。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="3f4c4-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3f4c4-116">Base template type</span></span> | <span data-ttu-id="3f4c4-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3f4c4-117">baseTemplateId</span></span> | <span data-ttu-id="3f4c4-118">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="3f4c4-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="3f4c4-119">零售 -</span><span class="sxs-lookup"><span data-stu-id="3f4c4-119">Retail -</span></span> <br><span data-ttu-id="3f4c4-120">商店</span><span class="sxs-lookup"><span data-stu-id="3f4c4-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="3f4c4-121">频道</span><span class="sxs-lookup"><span data-stu-id="3f4c4-121">Channels</span></span> <ul><li><span data-ttu-id="3f4c4-122">换班\*</span><span class="sxs-lookup"><span data-stu-id="3f4c4-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="3f4c4-123">学习\*</span><span class="sxs-lookup"><span data-stu-id="3f4c4-123">Learning\*</span></span></li></ul><span data-ttu-id="3f4c4-124">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="3f4c4-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="3f4c4-125">团队属性</span><span class="sxs-lookup"><span data-stu-id="3f4c4-125">Team properties</span></span> <ul><li><span data-ttu-id="3f4c4-126">团队可见性设置为“公共”</span><span class="sxs-lookup"><span data-stu-id="3f4c4-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="3f4c4-127">成员权限</span><span class="sxs-lookup"><span data-stu-id="3f4c4-127">Member permissions</span></span> <ul><li><span data-ttu-id="3f4c4-128">无法创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="3f4c4-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="3f4c4-129">无法添加/删除应用</span><span class="sxs-lookup"><span data-stu-id="3f4c4-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="3f4c4-130">无法创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="3f4c4-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="3f4c4-131">无法创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="3f4c4-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="3f4c4-132">为组织自定义商店模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="3f4c4-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="3f4c4-133">如果你的组织在每个商店都有部门，请为每个部门添加一个频道。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="3f4c4-134">添加频道可促进部门之间的沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="3f4c4-135">如果你的组织具有任何内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="3f4c4-136">有关说明，请参阅[开始使用 Teams 模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="3f4c4-137">经理协作模板</span><span class="sxs-lookup"><span data-stu-id="3f4c4-137">Manager Collaboration template</span></span>

<span data-ttu-id="3f4c4-138">经理协作模板是围绕零售商需求设计的另外一个 Teams 模板。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="3f4c4-139">经理协作模板非常适合用于创建一个团队，供一组经理跨商店/地区进行协作等。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="3f4c4-140">例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，并包括该地区的所有商店经理以及该地区的区域经理。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="3f4c4-141">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3f4c4-141">Base template type</span></span> | <span data-ttu-id="3f4c4-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3f4c4-142">baseTemplateId</span></span> | <span data-ttu-id="3f4c4-143">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="3f4c4-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="3f4c4-144">零售 -</span><span class="sxs-lookup"><span data-stu-id="3f4c4-144">Retail -</span></span> <br><span data-ttu-id="3f4c4-145">商店</span><span class="sxs-lookup"><span data-stu-id="3f4c4-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="3f4c4-146">频道</span><span class="sxs-lookup"><span data-stu-id="3f4c4-146">Channels</span></span> <ul><li><span data-ttu-id="3f4c4-147">运营\*</span><span class="sxs-lookup"><span data-stu-id="3f4c4-147">Operations\*</span></span></li><li><span data-ttu-id="3f4c4-148">学习\*</span><span class="sxs-lookup"><span data-stu-id="3f4c4-148">Learning\*</span></span></li></ul><span data-ttu-id="3f4c4-149">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="3f4c4-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="3f4c4-150">团队属性</span><span class="sxs-lookup"><span data-stu-id="3f4c4-150">Team properties</span></span> <ul><li><span data-ttu-id="3f4c4-151">团队可见性设置为“专用”</span><span class="sxs-lookup"><span data-stu-id="3f4c4-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="3f4c4-152">成员权限</span><span class="sxs-lookup"><span data-stu-id="3f4c4-152">Member permissions</span></span> <ul><li><span data-ttu-id="3f4c4-153">可创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="3f4c4-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="3f4c4-154">可添加/删除应用</span><span class="sxs-lookup"><span data-stu-id="3f4c4-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="3f4c4-155">可创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="3f4c4-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="3f4c4-156">可创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="3f4c4-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="3f4c4-157">为组织自定义经理协作模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="3f4c4-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="3f4c4-158">如果你的组织具有任何与经理相关的内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="3f4c4-159">可参考 [Microsoft Teams 模板文档](get-started-with-teams-templates.md)了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="3f4c4-160">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="3f4c4-160">How to use first party templates</span></span>

<span data-ttu-id="3f4c4-161">若要使用这些模板，请将请求正文中的“template@odata.bind”属性从“标准”更改为上述模板 ID。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="3f4c4-162">若要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="3f4c4-163">模板中的频道将自动创建在“常规”选项卡下方。</span><span class="sxs-lookup"><span data-stu-id="3f4c4-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="3f4c4-164">示例：商店模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="3f4c4-164">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a><span data-ttu-id="3f4c4-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="3f4c4-165">Relate topic</span></span>

[<span data-ttu-id="3f4c4-166">开始在管理中心使用 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="3f4c4-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)