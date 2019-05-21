---
title: 在 Microsoft Teams 中管理对私人团队的发现
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何通过团队库和搜索结果控制 Microsoft 团队用户是否可以通过建议发现专用团队。
ms.openlocfilehash: 55f127ff4dc9e5e0926e606c141b78f65c799de0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304399"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="7b91a-103">在 Microsoft Teams 中管理对私人团队的发现</span><span class="sxs-lookup"><span data-stu-id="7b91a-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

<span data-ttu-id="7b91a-104">管理员和团队所有者可以控制你的组织中的 Microsoft 团队用户是否可以发现专用团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="7b91a-105">当私人团队可发现时, 它将显示在搜索结果中, 并包含在团队的团队库和团队中的公共团队的建议中。</span><span class="sxs-lookup"><span data-stu-id="7b91a-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="7b91a-106">这使用户可以轻松地搜索和查找他们想要加入的专用团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="7b91a-107">用户可以请求加入团队所有者可以批准或拒绝的专用团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="7b91a-108">团队中的公共团队、私人团队和发现概述</span><span class="sxs-lookup"><span data-stu-id="7b91a-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="7b91a-109">大多数组织都有以下类型的团队-公共团队、可发现的专用团队和不可发现的专用团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![团队库](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="7b91a-111">公共团队</span><span class="sxs-lookup"><span data-stu-id="7b91a-111">Public teams</span></span>

<span data-ttu-id="7b91a-112">公共团队可供组织中的所有用户加入。</span><span class="sxs-lookup"><span data-stu-id="7b91a-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="7b91a-113">公共团队对于团队库中的每个人都是可见的, 用户可以加入公共团队, 而无需从团队所有者获得批准。</span><span class="sxs-lookup"><span data-stu-id="7b91a-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="7b91a-114">公共团队的示例包括团队在技术中讨论新闻、团队可为你的产品提供 dogfood 反馈, 以及供人员 carpooling 工作的团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="7b91a-115">可发现的专用团队</span><span class="sxs-lookup"><span data-stu-id="7b91a-115">Discoverable private teams</span></span>

<span data-ttu-id="7b91a-116">只有当团队所有者将用户添加到可发现专用团队时, 才能将其加入。</span><span class="sxs-lookup"><span data-stu-id="7b91a-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="7b91a-117">当您使私人团队可发现时, 团队将包含在团队库中的建议团队和搜索结果列表中。</span><span class="sxs-lookup"><span data-stu-id="7b91a-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="7b91a-118">对你的组织中的项目和组使用可发现的专用团队, 每个人都知道, 并且需要对团队中的对话和文件的访问权限进行控制。</span><span class="sxs-lookup"><span data-stu-id="7b91a-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="7b91a-119">示例包括人力资源部门的团队、组织中所有经理的团队以及经理及其直接下属的团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="7b91a-120">不可发现的私人团队</span><span class="sxs-lookup"><span data-stu-id="7b91a-120">Non-discoverable private teams</span></span>

<span data-ttu-id="7b91a-121">不可发现的专用团队只能在团队所有者向他们添加用户时加入。</span><span class="sxs-lookup"><span data-stu-id="7b91a-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="7b91a-122">当您将某个私人团队设置为 "未发现" 时, 它将隐藏在建议的团队列表中, 并从团队库中的搜索结果中删除。</span><span class="sxs-lookup"><span data-stu-id="7b91a-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="7b91a-123">使用不可发现的团队协作处理敏感和高度机密的主题。</span><span class="sxs-lookup"><span data-stu-id="7b91a-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="7b91a-124">示例包括一个团队, 讨论即将进行的收购和团队讨论组织的战略方向的变化。</span><span class="sxs-lookup"><span data-stu-id="7b91a-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="7b91a-125">设置新的专用团队是否可发现</span><span class="sxs-lookup"><span data-stu-id="7b91a-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="7b91a-126">当团队所有者创建专用团队时, 他们可以通过配置团队的发现设置来选择使其可发现。</span><span class="sxs-lookup"><span data-stu-id="7b91a-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="7b91a-127">默认情况下, 新的专用团队是可搜索和可发现的。</span><span class="sxs-lookup"><span data-stu-id="7b91a-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="7b91a-128">如果团队所有者不希望私人团队显示在搜索结果和建议中, 可以通过选择**此团队**旁边的 "**更改" 设置**来关闭设置。</span><span class="sxs-lookup"><span data-stu-id="7b91a-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![新的专用团队的发现设置](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="7b91a-130">设置现有专用团队是否可发现</span><span class="sxs-lookup"><span data-stu-id="7b91a-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="7b91a-131">团队所有者可以直接在团队设置中设置现有专用团队的发现设置, 并且管理员可以通过使用 PowerShell 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b91a-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="7b91a-132">在团队设置中</span><span class="sxs-lookup"><span data-stu-id="7b91a-132">In team settings</span></span>

<span data-ttu-id="7b91a-133">在团队中, 转到专用团队, 单击 "**更多选项" ̇̇̇** > "**管理团队**"。</span><span class="sxs-lookup"><span data-stu-id="7b91a-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="7b91a-134">在 "**设置**" 选项卡上, 展开 "**团队发现**", 然后清除或选中 "**打开发现**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="7b91a-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![现有专用团队的发现设置](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a><span data-ttu-id="7b91a-136">使用 PowerShell (即将推出)</span><span class="sxs-lookup"><span data-stu-id="7b91a-136">Using PowerShell (coming soon)</span></span>

<span data-ttu-id="7b91a-137">使用 "**设置团队**cmdlet" 关闭或打开现有专用团队的发现设置。</span><span class="sxs-lookup"><span data-stu-id="7b91a-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="7b91a-138">下面是如何让团队易于发现的示例:</span><span class="sxs-lookup"><span data-stu-id="7b91a-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="7b91a-139">你可以在脚本中使用此 cmdlet 来批量设置现有专用团队的发现设置。</span><span class="sxs-lookup"><span data-stu-id="7b91a-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="7b91a-140">设置用户是否可以发现专用团队</span><span class="sxs-lookup"><span data-stu-id="7b91a-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="7b91a-141">作为管理员, 你还可以控制你的组织中的哪些用户可以在搜索结果和团队中的建议中发现专用团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="7b91a-142">使用**CsTeamsChannelsPolicy** cmdlet 创建策略, 然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="7b91a-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="7b91a-143">将**AllowPrivateTeamDiscovery**参数设置为**true** , 以允许分配了该策略的用户在搜索结果和建议中查看可发现的专用团队。</span><span class="sxs-lookup"><span data-stu-id="7b91a-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="7b91a-144">将**AllowPrivateTeamDiscovery**参数设置为**false**可从搜索结果中删除所有发现的专用团队, 并为分配了该策略的用户提出建议。</span><span class="sxs-lookup"><span data-stu-id="7b91a-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="7b91a-145">默认情况下, 对于组织中的所有用户, **AllowPrivateTeamDiscovery**设置为**true** 。</span><span class="sxs-lookup"><span data-stu-id="7b91a-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="7b91a-146">在此示例中, 我们创建一个名为 VendorPolicy 的策略, 该策略阻止用户发现任何已被发现的专用团队, 然后我们将该策略分配给名为 vendoruser1 的用户。</span><span class="sxs-lookup"><span data-stu-id="7b91a-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="7b91a-147">不能检测到的私有团队从不会显示在搜索结果和建议中, 而与策略设置无关。</span><span class="sxs-lookup"><span data-stu-id="7b91a-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="7b91a-148">例如, 如果你关闭了专用团队的发现设置, 则用户无法发现团队, 即使在这些用户的策略设置中**AllowPrivateTeamDiscovery**参数设置为 true 也是**如此**。</span><span class="sxs-lookup"><span data-stu-id="7b91a-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b91a-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b91a-149">Related topics</span></span>
- [<span data-ttu-id="7b91a-150">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="7b91a-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)