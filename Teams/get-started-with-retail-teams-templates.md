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
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995140"
---
# <a name="create-a-team-using-teams-retail-templates"></a><span data-ttu-id="c3417-103">使用零售模板Teams团队</span><span class="sxs-lookup"><span data-stu-id="c3417-103">Create a team using Teams retail templates</span></span>

<span data-ttu-id="c3417-104">通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="c3417-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="c3417-105">Teams 模板具有预先构建的围绕零售商需求设计的团队结构定义。</span><span class="sxs-lookup"><span data-stu-id="c3417-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="c3417-106">可使用 Teams 模板快速创建适用于零售商的团队类型，并在整个组织中部署它们。</span><span class="sxs-lookup"><span data-stu-id="c3417-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="c3417-107">你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="c3417-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="c3417-108">在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="c3417-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="c3417-109">如果你负责在整个零售组织中规划、部署和管理多个团队，则本文非常适合你。</span><span class="sxs-lookup"><span data-stu-id="c3417-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="c3417-110">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="c3417-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="c3417-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3417-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="c3417-112">若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c3417-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="c3417-113">人员</span><span class="sxs-lookup"><span data-stu-id="c3417-113">Who</span></span> | <span data-ttu-id="c3417-114">使用方法：</span><span class="sxs-lookup"><span data-stu-id="c3417-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="c3417-115">管理员和 IT 专业人员</span><span class="sxs-lookup"><span data-stu-id="c3417-115">Admins and IT Professionals</span></span> | <span data-ttu-id="c3417-116">[使用Teams管理中心](#use-the-teams-templates-in-the-teams-admin-center)基于零售版模板创建Teams团队。</span><span class="sxs-lookup"><span data-stu-id="c3417-116">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the retail Teams templates.</span></span>|
| <span data-ttu-id="c3417-117">开发人员和系统整合者</span><span class="sxs-lookup"><span data-stu-id="c3417-117">Developers and systems integrators</span></span> | <span data-ttu-id="c3417-118">[使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph)基于零售模板创建Teams团队。</span><span class="sxs-lookup"><span data-stu-id="c3417-118">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the retail Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="c3417-119">使用 Teams 管理中心中的 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="c3417-119">Use the Teams templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="c3417-120">组织商店</span><span class="sxs-lookup"><span data-stu-id="c3417-120">Organize a store</span></span>

<span data-ttu-id="c3417-121">将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。</span><span class="sxs-lookup"><span data-stu-id="c3417-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="c3417-122">整合其他应用程序，以简化轮班开始和结束流程。</span><span class="sxs-lookup"><span data-stu-id="c3417-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="c3417-123">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="c3417-123">Base template type</span></span> |<span data-ttu-id="c3417-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c3417-124">baseTemplateId</span></span> | <span data-ttu-id="c3417-125">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="c3417-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="c3417-126">组织商店</span><span class="sxs-lookup"><span data-stu-id="c3417-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="c3417-127">频道：</span><span class="sxs-lookup"><span data-stu-id="c3417-127">Channels:</span></span> <ul><li><span data-ttu-id="c3417-128">常规</span><span class="sxs-lookup"><span data-stu-id="c3417-128">General</span></span><li><span data-ttu-id="c3417-129">换班</span><span class="sxs-lookup"><span data-stu-id="c3417-129">Shift handoff</span></span></li><li><span data-ttu-id="c3417-130">学习</span><span class="sxs-lookup"><span data-stu-id="c3417-130">Learning</span></span></li></ul> <span data-ttu-id="c3417-131">应用：</span><span class="sxs-lookup"><span data-stu-id="c3417-131">Apps:</span></span> <ul><li><span data-ttu-id="c3417-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="c3417-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="c3417-133">经理协作</span><span class="sxs-lookup"><span data-stu-id="c3417-133">Manager Collaboration</span></span>

<span data-ttu-id="c3417-134">管理器协作模板非常适合创建一个团队，供一组经理跨商店/区域等进行协作。例如，如果您的组织有区域，您可以为加利福尼亚州创建经理协作团队，并包括该区域的所有商店经理以及该区域的区域经理。</span><span class="sxs-lookup"><span data-stu-id="c3417-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="c3417-135">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="c3417-135">Base template type</span></span>| <span data-ttu-id="c3417-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c3417-136">baseTemplateId</span></span> | <span data-ttu-id="c3417-137">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="c3417-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="c3417-138">零售 - 经理协作</span><span class="sxs-lookup"><span data-stu-id="c3417-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="c3417-139">频道：</span><span class="sxs-lookup"><span data-stu-id="c3417-139">Channels:</span></span> <ul><li><span data-ttu-id="c3417-140">常规</span><span class="sxs-lookup"><span data-stu-id="c3417-140">General</span></span><li><span data-ttu-id="c3417-141">运营</span><span class="sxs-lookup"><span data-stu-id="c3417-141">Operations</span></span></li><li><span data-ttu-id="c3417-142">学习</span><span class="sxs-lookup"><span data-stu-id="c3417-142">Learning</span></span></li></ul> <span data-ttu-id="c3417-143">应用：</span><span class="sxs-lookup"><span data-stu-id="c3417-143">Apps:</span></span> <ul><li><span data-ttu-id="c3417-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="c3417-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="c3417-145">将 Teams 模板与 Microsoft Graph 一起使用</span><span class="sxs-lookup"><span data-stu-id="c3417-145">Use the Teams templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="c3417-146">商店模板</span><span class="sxs-lookup"><span data-stu-id="c3417-146">Store template</span></span>

<span data-ttu-id="c3417-147">商店模板非常适合用于创建一个团队来代表单个零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="c3417-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="c3417-148">通过使用商店模板，你可以为组织中的每个零售商店位置创建一个团队。</span><span class="sxs-lookup"><span data-stu-id="c3417-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="c3417-149">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="c3417-149">Base template type</span></span> | <span data-ttu-id="c3417-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c3417-150">baseTemplateId</span></span> | <span data-ttu-id="c3417-151">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="c3417-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="c3417-152">零售 -</span><span class="sxs-lookup"><span data-stu-id="c3417-152">Retail -</span></span> <br><span data-ttu-id="c3417-153">商店</span><span class="sxs-lookup"><span data-stu-id="c3417-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="c3417-154">频道</span><span class="sxs-lookup"><span data-stu-id="c3417-154">Channels</span></span> <ul><li><span data-ttu-id="c3417-155">换班\*</span><span class="sxs-lookup"><span data-stu-id="c3417-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="c3417-156">学习\*</span><span class="sxs-lookup"><span data-stu-id="c3417-156">Learning\*</span></span></li></ul><span data-ttu-id="c3417-157">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="c3417-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="c3417-158">团队属性</span><span class="sxs-lookup"><span data-stu-id="c3417-158">Team properties</span></span> <ul><li><span data-ttu-id="c3417-159">团队可见性设置为“公共”</span><span class="sxs-lookup"><span data-stu-id="c3417-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="c3417-160">成员权限</span><span class="sxs-lookup"><span data-stu-id="c3417-160">Member permissions</span></span> <ul><li><span data-ttu-id="c3417-161">无法创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="c3417-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="c3417-162">无法添加/删除应用</span><span class="sxs-lookup"><span data-stu-id="c3417-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="c3417-163">无法创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="c3417-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="c3417-164">无法创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="c3417-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="c3417-165">为组织自定义商店模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="c3417-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="c3417-166">如果你的组织在每个商店都有部门，请为每个部门添加一个频道。</span><span class="sxs-lookup"><span data-stu-id="c3417-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="c3417-167">添加频道可促进部门之间的沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="c3417-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="c3417-168">如果你的组织具有任何内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="c3417-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="c3417-169">有关说明，请参阅[开始使用 Teams 模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="c3417-169">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="c3417-170">经理协作模板</span><span class="sxs-lookup"><span data-stu-id="c3417-170">Manager Collaboration template</span></span>

<span data-ttu-id="c3417-171">经理协作模板是围绕零售商需求设计的另外一个 Teams 模板。</span><span class="sxs-lookup"><span data-stu-id="c3417-171">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="c3417-172">经理协作模板非常适合用于创建一个团队，供一组经理跨商店/地区进行协作等。</span><span class="sxs-lookup"><span data-stu-id="c3417-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="c3417-173">例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，并包括该地区的所有商店经理以及该地区的区域经理。</span><span class="sxs-lookup"><span data-stu-id="c3417-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="c3417-174">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="c3417-174">Base template type</span></span> | <span data-ttu-id="c3417-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c3417-175">baseTemplateId</span></span> | <span data-ttu-id="c3417-176">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="c3417-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="c3417-177">零售 -</span><span class="sxs-lookup"><span data-stu-id="c3417-177">Retail -</span></span> <br><span data-ttu-id="c3417-178">商店</span><span class="sxs-lookup"><span data-stu-id="c3417-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="c3417-179">频道</span><span class="sxs-lookup"><span data-stu-id="c3417-179">Channels</span></span> <ul><li><span data-ttu-id="c3417-180">运营\*</span><span class="sxs-lookup"><span data-stu-id="c3417-180">Operations\*</span></span></li><li><span data-ttu-id="c3417-181">学习\*</span><span class="sxs-lookup"><span data-stu-id="c3417-181">Learning\*</span></span></li></ul><span data-ttu-id="c3417-182">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="c3417-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="c3417-183">团队属性</span><span class="sxs-lookup"><span data-stu-id="c3417-183">Team properties</span></span> <ul><li><span data-ttu-id="c3417-184">团队可见性设置为“专用”</span><span class="sxs-lookup"><span data-stu-id="c3417-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="c3417-185">成员权限</span><span class="sxs-lookup"><span data-stu-id="c3417-185">Member permissions</span></span> <ul><li><span data-ttu-id="c3417-186">可创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="c3417-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="c3417-187">可添加/删除应用</span><span class="sxs-lookup"><span data-stu-id="c3417-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="c3417-188">可创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="c3417-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="c3417-189">可创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="c3417-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="c3417-190">为组织自定义经理协作模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="c3417-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="c3417-191">如果你的组织具有任何与经理相关的内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="c3417-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="c3417-192">可参考 [Microsoft Teams 模板文档](get-started-with-teams-templates.md)了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="c3417-192">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="c3417-193">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="c3417-193">How to use first party templates</span></span>

<span data-ttu-id="c3417-194">若要使用这些模板，请将请求正文中的“template@odata.bind”属性从“标准”更改为上述模板 ID。</span><span class="sxs-lookup"><span data-stu-id="c3417-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="c3417-195">若要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="c3417-195">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="c3417-196">模板中的频道将自动创建在“常规”选项卡下方。</span><span class="sxs-lookup"><span data-stu-id="c3417-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="c3417-197">示例：商店模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="c3417-197">Example: Store template extension script</span></span>

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
