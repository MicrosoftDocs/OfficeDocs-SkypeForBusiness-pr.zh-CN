---
title: 工作组模板入门
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: 了解如何使用团队模板来创建工作组使用预定义的通道。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801461"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="af485-103">工作组模板入门</span><span class="sxs-lookup"><span data-stu-id="af485-103">Get started with Teams templates</span></span> 

<span data-ttu-id="af485-104">工作组模板是预建的团队的结构围绕业务需要或项目设计的定义。</span><span class="sxs-lookup"><span data-stu-id="af485-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="af485-105">工作组模板可用于快速使用不同的主题的通道创建丰富的协作空格和预安装应用程序提取在任务关键型内容和服务。</span><span class="sxs-lookup"><span data-stu-id="af485-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="af485-106">工作组模板提供可帮助您轻松地在整个组织中创建一致的团队的预定义的团队结构。</span><span class="sxs-lookup"><span data-stu-id="af485-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="af485-107">本文中，我们将介绍可以在模板类型是，哪些基本模板定义的属性和如何使用了几个示例请求从模板创建工作组。</span><span class="sxs-lookup"><span data-stu-id="af485-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="af485-108">本文适用于您，如果您是：</span><span class="sxs-lookup"><span data-stu-id="af485-108">This article is for you if you're:</span></span>

- <span data-ttu-id="af485-109">负责规划、 部署和管理您的组织内的多个团队</span><span class="sxs-lookup"><span data-stu-id="af485-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="af485-110">开发人员希望以编程方式使用预定义的通道和应用程序创建团队</span><span class="sxs-lookup"><span data-stu-id="af485-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="af485-111">工作组模板功能</span><span class="sxs-lookup"><span data-stu-id="af485-111">Teams template capabilities</span></span>

<span data-ttu-id="af485-112">包含和模板的支持团队中的大多数属性。</span><span class="sxs-lookup"><span data-stu-id="af485-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="af485-113">但有一些属性，当前不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="af485-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="af485-114">下表提供了包含的组件和工作组模板中不包含内容的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="af485-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="af485-115">**支持的工作组模板的团队属性**</span><span class="sxs-lookup"><span data-stu-id="af485-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="af485-116">**尚未支持的工作组模板的团队属性**</span><span class="sxs-lookup"><span data-stu-id="af485-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="af485-117">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="af485-117">Base template type</span></span> | <span data-ttu-id="af485-118">团队成员资格</span><span class="sxs-lookup"><span data-stu-id="af485-118">Team membership</span></span> |
| <span data-ttu-id="af485-119">团队名称</span><span class="sxs-lookup"><span data-stu-id="af485-119">Team name</span></span> | <span data-ttu-id="af485-120">团队图片</span><span class="sxs-lookup"><span data-stu-id="af485-120">Team picture</span></span> |
| <span data-ttu-id="af485-121">团队说明</span><span class="sxs-lookup"><span data-stu-id="af485-121">Team description</span></span> | <span data-ttu-id="af485-122">通道设置</span><span class="sxs-lookup"><span data-stu-id="af485-122">Channel settings</span></span> |
| <span data-ttu-id="af485-123">工作组可见性 （公共或专用）</span><span class="sxs-lookup"><span data-stu-id="af485-123">Team visibility (public or private)</span></span> | <span data-ttu-id="af485-124">连接器</span><span class="sxs-lookup"><span data-stu-id="af485-124">Connectors</span></span> |
| <span data-ttu-id="af485-125">团队设置 （例如，成员、 来宾，@ 提及）</span><span class="sxs-lookup"><span data-stu-id="af485-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="af485-126">文件和内容</span><span class="sxs-lookup"><span data-stu-id="af485-126">Files and content</span></span> |
| <span data-ttu-id="af485-127">自动收藏夹通道</span><span class="sxs-lookup"><span data-stu-id="af485-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="af485-128">已安装应用程序</span><span class="sxs-lookup"><span data-stu-id="af485-128">Installed app</span></span> | |
| <span data-ttu-id="af485-129">固定的选项卡</span><span class="sxs-lookup"><span data-stu-id="af485-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="af485-130">我们将为添加更多模板功能的将来版本中的 Microsoft 团队，因此检查返回有关支持的属性的最新信息。</span><span class="sxs-lookup"><span data-stu-id="af485-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="af485-131">基本模板类型是什么？</span><span class="sxs-lookup"><span data-stu-id="af485-131">What are base template types?</span></span>

<span data-ttu-id="af485-132">基本模板类型是 Microsoft 创建针对特定行业的特殊模板。</span><span class="sxs-lookup"><span data-stu-id="af485-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="af485-133">这些基本模板通常包含在尚不支持分别在工作组模板中存储和团队属性中不可用的专用应用程序。</span><span class="sxs-lookup"><span data-stu-id="af485-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="af485-134">定义基本模板类型后，您可以扩展或重写这些特殊模板与您想要指定的其他属性。</span><span class="sxs-lookup"><span data-stu-id="af485-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="af485-135">但某些基本模板类型包含不能重写的属性。</span><span class="sxs-lookup"><span data-stu-id="af485-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="af485-136">默认情况下基本模板设置为**标准**其不包含任何其他专用应用程序或特殊属性。</span><span class="sxs-lookup"><span data-stu-id="af485-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="af485-137">下面是可用的基本模板类型的当前列表。</span><span class="sxs-lookup"><span data-stu-id="af485-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="af485-138">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="af485-138">Base template type</span></span> | <span data-ttu-id="af485-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="af485-139">baseTemplateId</span></span> | <span data-ttu-id="af485-140">基本模板专用应用程序和特殊属性</span><span class="sxs-lookup"><span data-stu-id="af485-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="af485-141">Standard</span><span class="sxs-lookup"><span data-stu-id="af485-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="af485-142">没有其他应用程序和属性</span><span class="sxs-lookup"><span data-stu-id="af485-142">No additional apps and properties</span></span> |
| <span data-ttu-id="af485-143">培训-</span><span class="sxs-lookup"><span data-stu-id="af485-143">Education -</span></span> <br><span data-ttu-id="af485-144">类工作组<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af485-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="af485-145">应用程序：</span><span class="sxs-lookup"><span data-stu-id="af485-145">Apps:</span></span><ul><li><span data-ttu-id="af485-146">OneNote 类笔记本 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="af485-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="af485-147">分配应用程序 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="af485-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="af485-148">团队属性：</span><span class="sxs-lookup"><span data-stu-id="af485-148">Team properties:</span></span><ul><li><span data-ttu-id="af485-149">工作组可见性设置为**HiddenMembership** （不能重写）</span><span class="sxs-lookup"><span data-stu-id="af485-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="af485-150">培训-</span><span class="sxs-lookup"><span data-stu-id="af485-150">Education -</span></span><br><span data-ttu-id="af485-151">员工工作组<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af485-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="af485-152">应用程序：</span><span class="sxs-lookup"><span data-stu-id="af485-152">Apps:</span></span><ul><li><span data-ttu-id="af485-153">OneNote 员工笔记本 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="af485-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="af485-154">培训-</span><span class="sxs-lookup"><span data-stu-id="af485-154">Education -</span></span><br><span data-ttu-id="af485-155">PLC 团队</span><span class="sxs-lookup"><span data-stu-id="af485-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="af485-156">应用程序：</span><span class="sxs-lookup"><span data-stu-id="af485-156">Apps:</span></span><ul><li><span data-ttu-id="af485-157">OneNote PLC 笔记本 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="af485-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="af485-158"><sup>1</sup>出版物中后期年 10 月，2018</span><span class="sxs-lookup"><span data-stu-id="af485-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="af485-159">我们将添加更多基本模板类型在将来版本的 Microsoft 团队，因此请检查以便获得最新信息支持属性。</span><span class="sxs-lookup"><span data-stu-id="af485-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="af485-160">示例</span><span class="sxs-lookup"><span data-stu-id="af485-160">Examples</span></span> 

<span data-ttu-id="af485-161">您可以开始使用模板创建工作组使用[Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="af485-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="af485-162">从模板创建工作组</span><span class="sxs-lookup"><span data-stu-id="af485-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="af485-163">请求</span><span class="sxs-lookup"><span data-stu-id="af485-163">Requests</span></span>

<span data-ttu-id="af485-164">**使用标准的基本模板创建团队的请求**</span><span class="sxs-lookup"><span data-stu-id="af485-164">**Request to create a team with the standard base template**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

<span data-ttu-id="af485-165">**请求创建额外的通道团队和禁止从删除通道的成员**</span><span class="sxs-lookup"><span data-stu-id="af485-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

<span data-ttu-id="af485-166">**请求创建工作组使用所有受支持的属性**</span><span class="sxs-lookup"><span data-stu-id="af485-166">**Request to create a team with all supported properties**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a><span data-ttu-id="af485-167">获取状态</span><span class="sxs-lookup"><span data-stu-id="af485-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="af485-168">请求</span><span class="sxs-lookup"><span data-stu-id="af485-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="af485-169">响应</span><span class="sxs-lookup"><span data-stu-id="af485-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="af485-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="af485-170">Related topics</span></span>

- <span data-ttu-id="af485-171">[创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在预览）</span><span class="sxs-lookup"><span data-stu-id="af485-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="af485-172">新团队</span><span class="sxs-lookup"><span data-stu-id="af485-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="af485-173">Microsoft Teams 管理培训</span><span class="sxs-lookup"><span data-stu-id="af485-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)