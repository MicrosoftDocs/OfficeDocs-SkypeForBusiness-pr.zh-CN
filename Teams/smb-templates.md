---
title: Teams Microsoft Graph 构建的中小型企业模板
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 使用Microsoft Teams Microsoft Graph构建的预定义模板，快速轻松地为中小型企业创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116990"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="31536-103">Teams Microsoft Graph 小型企业版中构建的模板</span><span class="sxs-lookup"><span data-stu-id="31536-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="31536-104">通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="31536-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="31536-105">对于中小型企业，模板可能特别强大，因为它们可帮助管理员快速Teams整个组织。</span><span class="sxs-lookup"><span data-stu-id="31536-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="31536-106">模板还有助于确定用户方向并开始有效地Teams模板。</span><span class="sxs-lookup"><span data-stu-id="31536-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="31536-107">如果你负责在整个组织中规划、部署和管理多个团队，则本文适合你。</span><span class="sxs-lookup"><span data-stu-id="31536-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="31536-108">我们目前提供三个可用于各种情况的第一方 SMB 模板。</span><span class="sxs-lookup"><span data-stu-id="31536-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="31536-109">所有模板 *都将创建专用* Teams。</span><span class="sxs-lookup"><span data-stu-id="31536-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="31536-110">创建应用程序Teams并准备好向组织推出后，可以适当地将隐私设置为 *"组织* 范围"或"公共"。 </span><span class="sxs-lookup"><span data-stu-id="31536-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="31536-111">要总体上了解有关团队模板的详细信息，请参阅 [开始使用 Teams 模板](get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="31536-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="31536-112">Company-Wide模板</span><span class="sxs-lookup"><span data-stu-id="31536-112">Company-Wide template</span></span>
<span data-ttu-id="31536-113">Company-Wide模板适用于与整个公司相关的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="31536-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="31536-114">您可以使用"常规"频道进行公司范围的公告、行业新闻或高管文章。</span><span class="sxs-lookup"><span data-stu-id="31536-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="31536-115">人力资源渠道是整合所有人力资源相关活动（如职位、新员工入职、培训和开发）的一个不错位置。</span><span class="sxs-lookup"><span data-stu-id="31536-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="31536-116">"有趣内容"频道提供一个社交平台，供所有随机和有趣的帖子使用。</span><span class="sxs-lookup"><span data-stu-id="31536-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="31536-117">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="31536-117">Base template type</span></span>  | <span data-ttu-id="31536-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="31536-118">baseTemplateId</span></span> | <span data-ttu-id="31536-119">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="31536-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="31536-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="31536-120">SMB -</span></span> <br><span data-ttu-id="31536-121">公司范围内</span><span class="sxs-lookup"><span data-stu-id="31536-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="31536-122">频道</span><span class="sxs-lookup"><span data-stu-id="31536-122">Channels</span></span> <ul><li><span data-ttu-id="31536-123">常规\*</span><span class="sxs-lookup"><span data-stu-id="31536-123">General\*</span></span></li><li><span data-ttu-id="31536-124">人力资源\*</span><span class="sxs-lookup"><span data-stu-id="31536-124">Human Resources\*</span></span></li><li><span data-ttu-id="31536-125">有趣的内容\*</span><span class="sxs-lookup"><span data-stu-id="31536-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="31536-126">应用</span><span class="sxs-lookup"><span data-stu-id="31536-126">Apps</span></span><ul><li><span data-ttu-id="31536-127">公司门户 (网站固定到 **人力资源** 频道) </span><span class="sxs-lookup"><span data-stu-id="31536-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="31536-128">团队属性</span><span class="sxs-lookup"><span data-stu-id="31536-128">Team properties</span></span> <ul><li><span data-ttu-id="31536-129">团队可见性设置为“专用”</span><span class="sxs-lookup"><span data-stu-id="31536-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="31536-130">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="31536-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="31536-131">若要通过Company-Wide模板中的默认值创建团队，在请求正文中提供团队对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="31536-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="31536-132">若要详细了解如何部署Teams模板，请参阅 Microsoft Graph[创建团队一文](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="31536-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="31536-133">请求</span><span class="sxs-lookup"><span data-stu-id="31536-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="31536-134">执行团队模板</span><span class="sxs-lookup"><span data-stu-id="31536-134">Executive Team template</span></span>

<span data-ttu-id="31536-135">"执行团队"模板非常适合创建一个团队，供公司主管就年度优先级、预算、战略计划以及顶级客户等公司计划进行沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="31536-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="31536-136">此模板附带一个 *专用* 通道，用于邀请特定主题的选定用户。</span><span class="sxs-lookup"><span data-stu-id="31536-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="31536-137">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="31536-137">Base template type</span></span>  | <span data-ttu-id="31536-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="31536-138">baseTemplateId</span></span> | <span data-ttu-id="31536-139">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="31536-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="31536-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="31536-140">SMB -</span></span> <br><span data-ttu-id="31536-141">高管团队</span><span class="sxs-lookup"><span data-stu-id="31536-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="31536-142">频道</span><span class="sxs-lookup"><span data-stu-id="31536-142">Channels</span></span> <ul><li><span data-ttu-id="31536-143">常规\*</span><span class="sxs-lookup"><span data-stu-id="31536-143">General\*</span></span></li><li><span data-ttu-id="31536-144">专用 \*</span><span class="sxs-lookup"><span data-stu-id="31536-144">Private \*</span></span></li></ul> <span data-ttu-id="31536-145">应用</span><span class="sxs-lookup"><span data-stu-id="31536-145">Apps</span></span><ul><li><span data-ttu-id="31536-146">OneNote (固定到专用 **频道)**</span><span class="sxs-lookup"><span data-stu-id="31536-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="31536-147">Planner (固定到"专用 **"** 频道) </span><span class="sxs-lookup"><span data-stu-id="31536-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="31536-148">团队属性</span><span class="sxs-lookup"><span data-stu-id="31536-148">Team properties</span></span> <ul><li><span data-ttu-id="31536-149">团队可见性设置为“专用”</span><span class="sxs-lookup"><span data-stu-id="31536-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="31536-150">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="31536-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="31536-151">若要通过采用预定义模板中的默认值创建高层团队，在请求正文中提供团队对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="31536-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="31536-152">若要详细了解如何部署Teams模板，请参阅 Microsoft Graph[创建团队一文](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="31536-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="31536-153">请求</span><span class="sxs-lookup"><span data-stu-id="31536-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="31536-154">部门团队模板</span><span class="sxs-lookup"><span data-stu-id="31536-154">Departmental Team template</span></span>

<span data-ttu-id="31536-155">部门团队模板可用于为各个部门或项目创建团队。</span><span class="sxs-lookup"><span data-stu-id="31536-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="31536-156">财务团队模板非常适合财务团队成员和高层团队成员内部的所有帖子、公告以及日常协作和通信。</span><span class="sxs-lookup"><span data-stu-id="31536-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="31536-157">该模板附带一个 *专用* 通道，用于邀请特定主题的选定用户。</span><span class="sxs-lookup"><span data-stu-id="31536-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="31536-158">我们还为财务团队提供以下脚本，该脚本可用于通过添加、删除或编辑来将模板扩展到其他部门或特定项目。</span><span class="sxs-lookup"><span data-stu-id="31536-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="31536-159">例如，如果您有 *营销部门，* 则可以通过将团队从 Finance 重命名为 *Marketing* 来修改脚本，以创建新的市场营销团队</span><span class="sxs-lookup"><span data-stu-id="31536-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="31536-160">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="31536-160">Base template type</span></span> | <span data-ttu-id="31536-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="31536-161">baseTemplateId</span></span> | <span data-ttu-id="31536-162">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="31536-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="31536-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="31536-163">SMB -</span></span> <br><span data-ttu-id="31536-164">财务</span><span class="sxs-lookup"><span data-stu-id="31536-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="31536-165">频道</span><span class="sxs-lookup"><span data-stu-id="31536-165">Channels</span></span> <ul><li><span data-ttu-id="31536-166">常规\*</span><span class="sxs-lookup"><span data-stu-id="31536-166">General\*</span></span></li><li><span data-ttu-id="31536-167">专用 \*</span><span class="sxs-lookup"><span data-stu-id="31536-167">Private \*</span></span></li></ul><br> <span data-ttu-id="31536-168">应用</span><span class="sxs-lookup"><span data-stu-id="31536-168">Apps</span></span><ul><li><span data-ttu-id="31536-169">OneNote (固定到专用 **频道)**</span><span class="sxs-lookup"><span data-stu-id="31536-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="31536-170">Planner (固定到"专用 **"** 频道) </span><span class="sxs-lookup"><span data-stu-id="31536-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="31536-171">团队属性</span><span class="sxs-lookup"><span data-stu-id="31536-171">Team properties</span></span> <ul><li><span data-ttu-id="31536-172">团队可见性设置为“专用”</span><span class="sxs-lookup"><span data-stu-id="31536-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="31536-173">\*自动收藏的频道</span><span class="sxs-lookup"><span data-stu-id="31536-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="31536-174">若要通过采用预定义模板中的默认值创建财务团队，在请求正文中提供团队对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="31536-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="31536-175">若要详细了解如何部署Teams模板，请参阅 Microsoft Graph[创建团队一文](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="31536-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="31536-176">请求</span><span class="sxs-lookup"><span data-stu-id="31536-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="31536-177">示例：财务团队模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="31536-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="31536-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="31536-178">Related topics</span></span>

- [<span data-ttu-id="31536-179">管理员控制台Teams模板入门</span><span class="sxs-lookup"><span data-stu-id="31536-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="31536-180">Teams 模板入门</span><span class="sxs-lookup"><span data-stu-id="31536-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="31536-181">[在预览](/graph/api/team-post?view=graph-rest-beta) (创建团队) </span><span class="sxs-lookup"><span data-stu-id="31536-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>