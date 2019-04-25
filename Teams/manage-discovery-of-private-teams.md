---
title: 管理中的 Microsoft 团队的专用工作组的发现
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何控制是否可以发现的 Microsoft 团队用户通过团队库和搜索结果中的建议的专用工作组。
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262743"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="2cbcc-103">管理中的 Microsoft 团队的专用工作组的发现</span><span class="sxs-lookup"><span data-stu-id="2cbcc-103">Manage discovery of private teams in Microsoft Teams</span></span>

<span data-ttu-id="2cbcc-104">管理员和团队所有者可以控制是否可以发现您的组织中的 Microsoft 团队用户的专用工作组。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="2cbcc-105">可供搜索的专用工作组后，它显示在搜索结果中，并包含在公共 リ モ ・ 团队旁的工作组库中的建议。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="2cbcc-106">这样，用户可以方便地搜索和查找要加入的 private 团队。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="2cbcc-107">用户可以请求加入该团队所有者可以然后批准或拒绝的专用工作组。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="2cbcc-108">公共团队、 专用团队和团队中的发现的概述</span><span class="sxs-lookup"><span data-stu-id="2cbcc-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="2cbcc-109">大多数组织都有以下几种团队-公共团队、 可供搜索专用团队和非可供搜索的专用工作组。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![团队库](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="2cbcc-111">公共团队</span><span class="sxs-lookup"><span data-stu-id="2cbcc-111">Public teams</span></span>

<span data-ttu-id="2cbcc-112">公共团队是可用于加入您的组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="2cbcc-113">公共团队团队库中的所有人都可见，用户可以加入而无需获得团队所有者批准的公共团队。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="2cbcc-114">公共团队的例子包括团队讨论技术、 团队以获取您的产品，试用反馈和人员拼车工作团队的新闻。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="2cbcc-115">可供搜索的专用工作组</span><span class="sxs-lookup"><span data-stu-id="2cbcc-115">Discoverable private teams</span></span>

<span data-ttu-id="2cbcc-116">可供搜索的专用工作组只能团队所有者将用户添加到其时联接。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="2cbcc-117">当您进行专用团队可供搜索时，团队包含的建议的团队和团队库中的搜索结果列表中。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="2cbcc-118">使用可供搜索的专用工作组的项目和组织中的所有人了解与其中访问对话，团队中的文件需要对其进行控制的组。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="2cbcc-119">示例管理器和其直接下属包括贵公司人力资源部门团队、 团队的所有在您的组织，经理和团队。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="2cbcc-120">非可供搜索的专用工作组</span><span class="sxs-lookup"><span data-stu-id="2cbcc-120">Non-discoverable private teams</span></span>

<span data-ttu-id="2cbcc-121">非可供搜索的专用工作组只能团队所有者将用户添加到其时联接。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="2cbcc-122">时使专用团队不可被发现，它有隐藏建议团队列表中，从工作组库中的搜索结果中删除。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="2cbcc-123">使用非可供搜索团队协作敏感和高度机密主题。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="2cbcc-124">示例包括工作组讨论即将开始的获取和团队讨论在贵组织的战略方向更改。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="2cbcc-125">设置新的专用工作组是否可供搜索</span><span class="sxs-lookup"><span data-stu-id="2cbcc-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="2cbcc-126">当团队所有者创建专用团队时，他们可以选择以使其通过配置团队的发现设置发现。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="2cbcc-127">默认情况下，新的专用团队可搜索和可供搜索。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="2cbcc-128">如果团队所有者不希望显示在搜索结果和建议的专用团队，他们可以通过选择**更改设置**旁边**此团队是可搜索和发现**关闭设置。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![发现新的专用工作组设置](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="2cbcc-130">设置现有专用团队是否可供搜索</span><span class="sxs-lookup"><span data-stu-id="2cbcc-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="2cbcc-131">团队所有者可以直接在团队设置中设置现有的专用工作组的发现设置，管理员可以使用 PowerShell 执行操作。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="2cbcc-132">在工作组设置。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-132">In team settings</span></span>

<span data-ttu-id="2cbcc-133">在工作组中，转到专用工作组中，单击**多个选项 ˙˙˙** > **管理团队**。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="2cbcc-134">在**设置**选项卡中，展开**团队发现**，然后清除或选中**开启可发现性**复选框。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![现有的专用工作组的发现设置](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="2cbcc-136">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cbcc-136">Using PowerShell</span></span>

<span data-ttu-id="2cbcc-137">使用**设置团队**cmdlet 可以关闭或打开现有的专用工作组的发现设置。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="2cbcc-138">下面是如何使团队可检测到的一个示例：</span><span class="sxs-lookup"><span data-stu-id="2cbcc-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="2cbcc-139">您可以在脚本中使用此 cmdlet 批量设置的现有专用团队发现设置。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="2cbcc-140">设置是否用户可以发现专用团队</span><span class="sxs-lookup"><span data-stu-id="2cbcc-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="2cbcc-141">作为一名管理员，您可以控制允许组织中的哪些用户可以发现搜索结果中的专用工作组和团队中的建议。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="2cbcc-142">使用**新建 CsTeamsChannelsPolicy** cmdlet，创建策略，然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="2cbcc-143">**AllowPrivateTeamDiscovery**参数设置为**true**以允许用户分配有该策略以查看可供搜索专用 リ モ ・ 搜索结果和建议。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="2cbcc-144">**AllowPrivateTeamDiscovery**参数设置为**false**可删除所有可检测到的专用工作组搜索结果和建议的分配策略的用户。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="2cbcc-145">默认情况下**AllowPrivateTeamDiscovery**是设置为**true**的组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="2cbcc-146">本示例中，我们将创建名为防止用户发现所做可供搜索，任何专用团队的 VendorPolicy 的策略，然后我们将策略分配给名为 vendoruser1 的用户。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="2cbcc-147">不是可供搜索的专用工作组永远不会显示在搜索结果和建议，而不考虑的策略设置。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="2cbcc-148">例如，如果要关闭的专用工作组的发现设置，用户将无法发现团队，即使**AllowPrivateTeamDiscovery**参数设置为**true**这些用户的策略设置。</span><span class="sxs-lookup"><span data-stu-id="2cbcc-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2cbcc-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="2cbcc-149">Related topics</span></span>
- [<span data-ttu-id="2cbcc-150">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="2cbcc-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)