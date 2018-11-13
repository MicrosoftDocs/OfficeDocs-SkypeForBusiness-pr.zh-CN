---
title: 工作组模板入门
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295004"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="74dee-103">工作组模板入门</span><span class="sxs-lookup"><span data-stu-id="74dee-103">Get started with Teams templates</span></span> 

<span data-ttu-id="74dee-104">工作组模板是预建的团队的结构围绕业务需要或项目设计的定义。</span><span class="sxs-lookup"><span data-stu-id="74dee-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="74dee-105">工作组模板可用于快速使用不同的主题的通道创建丰富的协作空格和预安装应用程序提取在任务关键型内容和服务。</span><span class="sxs-lookup"><span data-stu-id="74dee-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="74dee-106">工作组模板提供可帮助您轻松地在整个组织中创建一致的团队的预定义的团队结构。</span><span class="sxs-lookup"><span data-stu-id="74dee-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="74dee-107">本文中，我们将介绍可以在模板类型是，哪些基本模板定义的属性和如何使用了几个示例请求从模板创建工作组。</span><span class="sxs-lookup"><span data-stu-id="74dee-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="74dee-108">本文适用于您，如果您是：</span><span class="sxs-lookup"><span data-stu-id="74dee-108">This article is for you if you're:</span></span>

<span data-ttu-id="74dee-109">• 负责规划、 部署和管理跨组织 • 为开发人员的多个团队希望创建与工作组预定义通道和应用程序以编程方式</span><span class="sxs-lookup"><span data-stu-id="74dee-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="74dee-110">工作组模板功能</span><span class="sxs-lookup"><span data-stu-id="74dee-110">Team template capabilities</span></span>

<span data-ttu-id="74dee-111">包含和模板的支持团队中的大多数属性。</span><span class="sxs-lookup"><span data-stu-id="74dee-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="74dee-112">但是，有几个属性，当前不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="74dee-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="74dee-113">下表提供了包含的组件和工作组模板中不包含内容的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="74dee-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="74dee-114">**支持的工作组模板的团队属性**</span><span class="sxs-lookup"><span data-stu-id="74dee-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="74dee-115">**尚未支持的工作组模板的团队属性**</span><span class="sxs-lookup"><span data-stu-id="74dee-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="74dee-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="74dee-116">Base template type</span></span> | <span data-ttu-id="74dee-117">团队成员资格</span><span class="sxs-lookup"><span data-stu-id="74dee-117">Team membership</span></span> |
| <span data-ttu-id="74dee-118">团队名称</span><span class="sxs-lookup"><span data-stu-id="74dee-118">Team name</span></span> | <span data-ttu-id="74dee-119">团队图片</span><span class="sxs-lookup"><span data-stu-id="74dee-119">Team picture</span></span> |
| <span data-ttu-id="74dee-120">团队说明</span><span class="sxs-lookup"><span data-stu-id="74dee-120">Team description</span></span> | <span data-ttu-id="74dee-121">频道设置 （例如，自动收藏夹和隐私）</span><span class="sxs-lookup"><span data-stu-id="74dee-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="74dee-122">工作组可见性 （公共或专用）</span><span class="sxs-lookup"><span data-stu-id="74dee-122">Team visibility (public or private)</span></span> | <span data-ttu-id="74dee-123">连接器</span><span class="sxs-lookup"><span data-stu-id="74dee-123">Connectors</span></span> |
| <span data-ttu-id="74dee-124">团队设置 （例如，成员、 来宾，@ 提及）</span><span class="sxs-lookup"><span data-stu-id="74dee-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="74dee-125">文件和内容</span><span class="sxs-lookup"><span data-stu-id="74dee-125">Files and content</span></span> |
| <span data-ttu-id="74dee-126">自动收藏夹通道</span><span class="sxs-lookup"><span data-stu-id="74dee-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="74dee-127">已安装应用程序</span><span class="sxs-lookup"><span data-stu-id="74dee-127">Installed app</span></span> | |
| <span data-ttu-id="74dee-128">固定的选项卡</span><span class="sxs-lookup"><span data-stu-id="74dee-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="74dee-129">我们将为添加更多模板功能的将来版本中的 Microsoft 团队，因此检查返回有关支持的属性的最新信息。</span><span class="sxs-lookup"><span data-stu-id="74dee-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="74dee-130">基本模板类型是什么？</span><span class="sxs-lookup"><span data-stu-id="74dee-130">What are base template types?</span></span>

<span data-ttu-id="74dee-131">基本模板类型是 Microsoft 创建针对特定行业的特殊模板。</span><span class="sxs-lookup"><span data-stu-id="74dee-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="74dee-132">这些基本模板通常包含在尚未在工作组模板支持单独的存储和团队属性中不可用的专用应用程序。</span><span class="sxs-lookup"><span data-stu-id="74dee-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="74dee-133">定义基本模板类型后，您可以扩展或重写这些特殊模板与您想要指定的其他属性。</span><span class="sxs-lookup"><span data-stu-id="74dee-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="74dee-134">但是，某些基本模板类型包含不能重写的属性。</span><span class="sxs-lookup"><span data-stu-id="74dee-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="74dee-135">默认情况下基本模板设置为**标准**其不包含任何其他专用应用程序或特殊属性。</span><span class="sxs-lookup"><span data-stu-id="74dee-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="74dee-136">下面是可用的基本模板类型的当前列表。</span><span class="sxs-lookup"><span data-stu-id="74dee-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="74dee-137">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="74dee-137">Base template type</span></span> | <span data-ttu-id="74dee-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="74dee-138">baseTemplateId</span></span> | <span data-ttu-id="74dee-139">基本模板专用应用程序和特殊属性</span><span class="sxs-lookup"><span data-stu-id="74dee-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="74dee-140">Standard</span><span class="sxs-lookup"><span data-stu-id="74dee-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="74dee-141">没有其他应用程序和属性</span><span class="sxs-lookup"><span data-stu-id="74dee-141">No additional apps and properties</span></span> |
| <span data-ttu-id="74dee-142">医疗保健-护理协调</span><span class="sxs-lookup"><span data-stu-id="74dee-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="74dee-143">应用程序：</span><span class="sxs-lookup"><span data-stu-id="74dee-143">Apps:</span></span><br/> <span data-ttu-id="74dee-144">-患者应用程序 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="74dee-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="74dee-145">频道：</span><span class="sxs-lookup"><span data-stu-id="74dee-145">Channels:</span></span> <br/> <span data-ttu-id="74dee-146">-通知</span><span class="sxs-lookup"><span data-stu-id="74dee-146">- Announcements</span></span><br/> <span data-ttu-id="74dee-147">-糖尿病</span><span class="sxs-lookup"><span data-stu-id="74dee-147">- Diabetes</span></span><br/> <span data-ttu-id="74dee-148">-心血管</span><span class="sxs-lookup"><span data-stu-id="74dee-148">- Cardiovascular</span></span><br/> <span data-ttu-id="74dee-149">-已注册护理</span><span class="sxs-lookup"><span data-stu-id="74dee-149">- Registered nurses</span></span> |
| <span data-ttu-id="74dee-150">医疗保健-过程 huddle</span><span class="sxs-lookup"><span data-stu-id="74dee-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="74dee-151">频道：</span><span class="sxs-lookup"><span data-stu-id="74dee-151">Channels:</span></span><br/> <span data-ttu-id="74dee-152">-避免辅</span><span class="sxs-lookup"><span data-stu-id="74dee-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="74dee-153">-Mortality 审阅</span><span class="sxs-lookup"><span data-stu-id="74dee-153">- Mortality review</span></span> <br/> <span data-ttu-id="74dee-154">-阻止降到</span><span class="sxs-lookup"><span data-stu-id="74dee-154">- Preventing falls</span></span> <br/> <span data-ttu-id="74dee-155">-Sepsis 计划</span><span class="sxs-lookup"><span data-stu-id="74dee-155">- Sepsis plans</span></span> |
| <span data-ttu-id="74dee-156">教育-类工作组<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="74dee-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="74dee-157">应用程序：</span><span class="sxs-lookup"><span data-stu-id="74dee-157">Apps:</span></span><br/> <span data-ttu-id="74dee-158">-OneNote 类笔记本 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="74dee-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="74dee-159">-分配应用程序 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="74dee-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="74dee-160">团队属性</span><span class="sxs-lookup"><span data-stu-id="74dee-160">Team properties</span></span> <br/> <span data-ttu-id="74dee-161">团队可见性设置为**HiddenMembership** （不能重写）</span><span class="sxs-lookup"><span data-stu-id="74dee-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="74dee-162">培训-员工团队<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="74dee-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="74dee-163">应用</span><span class="sxs-lookup"><span data-stu-id="74dee-163">Apps</span></span><br/> <span data-ttu-id="74dee-164">-OneNote 员工笔记本 （固定到**常规**选项卡）</span><span class="sxs-lookup"><span data-stu-id="74dee-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="74dee-165"><sup>1</sup>出版物中后期年 10 月，2018</span><span class="sxs-lookup"><span data-stu-id="74dee-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="74dee-166">我们将添加更多基本模板类型在将来版本的 Microsoft 团队，因此请检查以便获得最新信息支持属性。</span><span class="sxs-lookup"><span data-stu-id="74dee-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="74dee-167">示例</span><span class="sxs-lookup"><span data-stu-id="74dee-167">Examples</span></span> 

<span data-ttu-id="74dee-168">您可以开始通过安装[Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview)中创建模板通过团队。</span><span class="sxs-lookup"><span data-stu-id="74dee-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="74dee-169">从模板创建工作组</span><span class="sxs-lookup"><span data-stu-id="74dee-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="74dee-170">请求</span><span class="sxs-lookup"><span data-stu-id="74dee-170">Requests</span></span>

<span data-ttu-id="74dee-171">**使用标准的基本模板创建团队的请求**</span><span class="sxs-lookup"><span data-stu-id="74dee-171">**Request to create a team with the standard base template**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

<span data-ttu-id="74dee-172">**请求创建额外的通道团队和禁止从删除通道的成员**</span><span class="sxs-lookup"><span data-stu-id="74dee-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

<span data-ttu-id="74dee-173">**请求创建工作组使用所有受支持的属性**</span><span class="sxs-lookup"><span data-stu-id="74dee-173">**Request to create a team with all supported properties**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a><span data-ttu-id="74dee-174">响应</span><span class="sxs-lookup"><span data-stu-id="74dee-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="74dee-175">获取状态</span><span class="sxs-lookup"><span data-stu-id="74dee-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="74dee-176">请求</span><span class="sxs-lookup"><span data-stu-id="74dee-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="74dee-177">响应</span><span class="sxs-lookup"><span data-stu-id="74dee-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="74dee-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="74dee-178">Related topics</span></span>

- <span data-ttu-id="74dee-179">[创建团队](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams)（在预览）</span><span class="sxs-lookup"><span data-stu-id="74dee-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="74dee-180">新团队</span><span class="sxs-lookup"><span data-stu-id="74dee-180">New-Team</span></span>](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="74dee-181">Microsoft Teams 管理培训</span><span class="sxs-lookup"><span data-stu-id="74dee-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)