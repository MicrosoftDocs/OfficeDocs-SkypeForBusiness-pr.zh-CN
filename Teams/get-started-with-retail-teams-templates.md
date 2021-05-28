---
title: 零售版团队模板入门
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
description: 了解如何通过提供预定义的设置、频道和预安装的应用，使用团队模板创建专为零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684550"
---
# <a name="create-a-team-using-retail-team-templates"></a><span data-ttu-id="7cfe9-103">使用零售团队模板创建团队</span><span class="sxs-lookup"><span data-stu-id="7cfe9-103">Create a team using retail team templates</span></span>

<span data-ttu-id="7cfe9-104">Microsoft 团队模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-104">Microsoft team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7cfe9-105">团队模板具有围绕零售商需求设计的团队结构的预构建定义。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-105">Team templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="7cfe9-106">可以使用团队模板快速创建适合零售商的团队类型，并在整个组织中部署它们。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-106">You can use team templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="7cfe9-107">还可以扩展团队模板，创建根据特定组织需求定制的团队。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-107">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="7cfe9-108">本文介绍每个团队模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-108">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="7cfe9-109">如果你负责在整个零售组织中规划、部署和管理多个团队，则本文非常适合你。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="7cfe9-110">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="7cfe9-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="7cfe9-112">若要了解有关团队模板的一般信息，请参阅 [团队模板入门](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-112">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="7cfe9-113">人员</span><span class="sxs-lookup"><span data-stu-id="7cfe9-113">Who</span></span> | <span data-ttu-id="7cfe9-114">使用方法：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="7cfe9-115">管理员和 IT 专业人员</span><span class="sxs-lookup"><span data-stu-id="7cfe9-115">Admins and IT Professionals</span></span> | <span data-ttu-id="7cfe9-116">[使用Teams管理中心](#use-the-team-templates-in-the-teams-admin-center)基于零售团队模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-116">[Use the Teams admin center](#use-the-team-templates-in-the-teams-admin-center) to create teams based on the retail team templates.</span></span>|
| <span data-ttu-id="7cfe9-117">开发人员和系统整合者</span><span class="sxs-lookup"><span data-stu-id="7cfe9-117">Developers and systems integrators</span></span> | <span data-ttu-id="7cfe9-118">[使用 Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph)基于零售团队模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-118">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create teams based on the retail team templates.</span></span> |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a><span data-ttu-id="7cfe9-119">使用管理中心中的Teams模板</span><span class="sxs-lookup"><span data-stu-id="7cfe9-119">Use the team templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="7cfe9-120">组织商店</span><span class="sxs-lookup"><span data-stu-id="7cfe9-120">Organize a store</span></span>

<span data-ttu-id="7cfe9-121">将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="7cfe9-122">整合其他应用程序，以简化轮班开始和结束流程。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="7cfe9-123">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7cfe9-123">Base template type</span></span> |<span data-ttu-id="7cfe9-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7cfe9-124">baseTemplateId</span></span> | <span data-ttu-id="7cfe9-125">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="7cfe9-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="7cfe9-126">组织商店</span><span class="sxs-lookup"><span data-stu-id="7cfe9-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="7cfe9-127">频道：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-127">Channels:</span></span> <ul><li><span data-ttu-id="7cfe9-128">常规</span><span class="sxs-lookup"><span data-stu-id="7cfe9-128">General</span></span><li><span data-ttu-id="7cfe9-129">换班</span><span class="sxs-lookup"><span data-stu-id="7cfe9-129">Shift handoff</span></span></li><li><span data-ttu-id="7cfe9-130">学习</span><span class="sxs-lookup"><span data-stu-id="7cfe9-130">Learning</span></span></li></ul> <span data-ttu-id="7cfe9-131">应用：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-131">Apps:</span></span> <ul><li><span data-ttu-id="7cfe9-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="7cfe9-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="7cfe9-133">经理协作</span><span class="sxs-lookup"><span data-stu-id="7cfe9-133">Manager Collaboration</span></span>

<span data-ttu-id="7cfe9-134">管理器协作模板非常适合创建一个团队，供一组经理跨商店/区域等进行协作。例如，如果您的组织有区域，您可以为加利福尼亚州创建经理协作团队，并包括该区域的所有商店经理以及该区域的区域经理。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="7cfe9-135">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7cfe9-135">Base template type</span></span>| <span data-ttu-id="7cfe9-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7cfe9-136">baseTemplateId</span></span> | <span data-ttu-id="7cfe9-137">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="7cfe9-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="7cfe9-138">零售 - 经理协作</span><span class="sxs-lookup"><span data-stu-id="7cfe9-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="7cfe9-139">频道：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-139">Channels:</span></span> <ul><li><span data-ttu-id="7cfe9-140">常规</span><span class="sxs-lookup"><span data-stu-id="7cfe9-140">General</span></span><li><span data-ttu-id="7cfe9-141">运营</span><span class="sxs-lookup"><span data-stu-id="7cfe9-141">Operations</span></span></li><li><span data-ttu-id="7cfe9-142">学习</span><span class="sxs-lookup"><span data-stu-id="7cfe9-142">Learning</span></span></li></ul> <span data-ttu-id="7cfe9-143">应用：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-143">Apps:</span></span> <ul><li><span data-ttu-id="7cfe9-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="7cfe9-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="7cfe9-145">将团队模板与 Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="7cfe9-145">Use the team templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="7cfe9-146">商店模板</span><span class="sxs-lookup"><span data-stu-id="7cfe9-146">Store template</span></span>

<span data-ttu-id="7cfe9-147">商店模板非常适合用于创建一个团队来代表单个零售商店位置。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="7cfe9-148">通过使用商店模板，你可以为组织中的每个零售商店位置创建一个团队。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="7cfe9-149">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7cfe9-149">Base template type</span></span> | <span data-ttu-id="7cfe9-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7cfe9-150">baseTemplateId</span></span> | <span data-ttu-id="7cfe9-151">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="7cfe9-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="7cfe9-152">零售 -</span><span class="sxs-lookup"><span data-stu-id="7cfe9-152">Retail -</span></span> <br><span data-ttu-id="7cfe9-153">商店</span><span class="sxs-lookup"><span data-stu-id="7cfe9-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="7cfe9-154">频道</span><span class="sxs-lookup"><span data-stu-id="7cfe9-154">Channels</span></span> <ul><li><span data-ttu-id="7cfe9-155">换班\*</span><span class="sxs-lookup"><span data-stu-id="7cfe9-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="7cfe9-156">学习\*</span><span class="sxs-lookup"><span data-stu-id="7cfe9-156">Learning\*</span></span></li></ul><span data-ttu-id="7cfe9-157">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="7cfe9-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="7cfe9-158">团队属性</span><span class="sxs-lookup"><span data-stu-id="7cfe9-158">Team properties</span></span> <ul><li><span data-ttu-id="7cfe9-159">团队可见性设置为“公共”</span><span class="sxs-lookup"><span data-stu-id="7cfe9-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="7cfe9-160">成员权限</span><span class="sxs-lookup"><span data-stu-id="7cfe9-160">Member permissions</span></span> <ul><li><span data-ttu-id="7cfe9-161">无法创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="7cfe9-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="7cfe9-162">无法添加/删除应用</span><span class="sxs-lookup"><span data-stu-id="7cfe9-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="7cfe9-163">无法创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="7cfe9-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="7cfe9-164">无法创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="7cfe9-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="7cfe9-165">为组织自定义商店模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="7cfe9-166">如果你的组织在每个商店都有部门，请为每个部门添加一个频道。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="7cfe9-167">添加频道可促进部门之间的沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="7cfe9-168">如果你的组织具有任何内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="7cfe9-169">有关 [说明，请参阅团队模板](get-started-with-teams-templates.md) 入门。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-169">Refer to [Get started with team templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="7cfe9-170">经理协作模板</span><span class="sxs-lookup"><span data-stu-id="7cfe9-170">Manager Collaboration template</span></span>

<span data-ttu-id="7cfe9-171">管理器协作模板是围绕零售商需求设计的另一个团队模板。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-171">The Manager Collaboration template is another one of the team templates designed around retailer needs.</span></span> <span data-ttu-id="7cfe9-172">经理协作模板非常适合用于创建一个团队，供一组经理跨商店/地区进行协作等。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="7cfe9-173">例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，并包括该地区的所有商店经理以及该地区的区域经理。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="7cfe9-174">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7cfe9-174">Base template type</span></span> | <span data-ttu-id="7cfe9-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7cfe9-175">baseTemplateId</span></span> | <span data-ttu-id="7cfe9-176">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="7cfe9-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="7cfe9-177">零售 -</span><span class="sxs-lookup"><span data-stu-id="7cfe9-177">Retail -</span></span> <br><span data-ttu-id="7cfe9-178">商店</span><span class="sxs-lookup"><span data-stu-id="7cfe9-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="7cfe9-179">频道</span><span class="sxs-lookup"><span data-stu-id="7cfe9-179">Channels</span></span> <ul><li><span data-ttu-id="7cfe9-180">运营\*</span><span class="sxs-lookup"><span data-stu-id="7cfe9-180">Operations\*</span></span></li><li><span data-ttu-id="7cfe9-181">学习\*</span><span class="sxs-lookup"><span data-stu-id="7cfe9-181">Learning\*</span></span></li></ul><span data-ttu-id="7cfe9-182">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="7cfe9-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="7cfe9-183">团队属性</span><span class="sxs-lookup"><span data-stu-id="7cfe9-183">Team properties</span></span> <ul><li><span data-ttu-id="7cfe9-184">团队可见性设置为“专用”</span><span class="sxs-lookup"><span data-stu-id="7cfe9-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="7cfe9-185">成员权限</span><span class="sxs-lookup"><span data-stu-id="7cfe9-185">Member permissions</span></span> <ul><li><span data-ttu-id="7cfe9-186">可创建/更新/删除频道</span><span class="sxs-lookup"><span data-stu-id="7cfe9-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="7cfe9-187">可添加/删除应用</span><span class="sxs-lookup"><span data-stu-id="7cfe9-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="7cfe9-188">可创建/更新/删除选项卡</span><span class="sxs-lookup"><span data-stu-id="7cfe9-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="7cfe9-189">可创建/更新/删除连接器</span><span class="sxs-lookup"><span data-stu-id="7cfe9-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="7cfe9-190">为组织自定义经理协作模板的建议方法：</span><span class="sxs-lookup"><span data-stu-id="7cfe9-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="7cfe9-191">如果你的组织具有任何与经理相关的内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="7cfe9-192">有关说明，请参阅 Microsoft [团队模板](get-started-with-teams-templates.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-192">You can take a look at the [Microsoft team Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="7cfe9-193">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="7cfe9-193">How to use first-party templates</span></span>

<span data-ttu-id="7cfe9-194">若要使用这些模板，请将请求正文中的“template@odata.bind”属性从“标准”更改为上述模板 ID。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="7cfe9-195">若要详细了解如何部署团队模板，请参阅 Microsoft Graph文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-195">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="7cfe9-196">模板中的频道将自动创建在“常规”选项卡下方。</span><span class="sxs-lookup"><span data-stu-id="7cfe9-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="7cfe9-197">示例：商店模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="7cfe9-197">Example: Store template extension script</span></span>

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
