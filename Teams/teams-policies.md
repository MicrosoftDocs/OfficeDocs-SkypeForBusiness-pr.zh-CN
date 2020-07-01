---
title: 管理 Microsoft 团队中的团队策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理组织中的团队策略，以控制用户可在团队和频道中执行的操作。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938141"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="02160-103">管理 Microsoft 团队中的团队策略</span><span class="sxs-lookup"><span data-stu-id="02160-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="02160-104">作为管理员，你可以使用 Microsoft 团队中的团队策略控制你的组织中的哪些用户可以在团队和频道中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="02160-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="02160-105">例如，你可以设置是否允许用户在搜索结果和团队库中发现专用团队以及是否允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="02160-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="02160-106">通过转到**Teams**  >  Microsoft 团队管理中心中的团队**团队策略**管理团队策略。</span><span class="sxs-lookup"><span data-stu-id="02160-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="02160-107">你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="02160-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="02160-108">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="02160-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="02160-109">你可以编辑全局策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="02160-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="02160-110">编辑全局策略或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="02160-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="02160-111">创建自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="02160-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="02160-112">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="02160-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="02160-113">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02160-113">Click **Add**.</span></span>
3. <span data-ttu-id="02160-114">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="02160-114">Enter a name and description for the policy.</span></span>

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. <span data-ttu-id="02160-116">选择所需的设置：</span><span class="sxs-lookup"><span data-stu-id="02160-116">Choose the settings that you want:</span></span>

- <span data-ttu-id="02160-117">**发现专用团队**（在私人预览版中）<a name="discoverteams"> </a> ：启用此设置可允许用户在搜索结果和团队库中发现个人团队。</span><span class="sxs-lookup"><span data-stu-id="02160-117">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="02160-118">**创建专用通道**： <a name="createchannels"> </a>启用此设置可允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="02160-118">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="02160-119">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="02160-119">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="02160-120">编辑团队策略</span><span class="sxs-lookup"><span data-stu-id="02160-120">Edit a teams policy</span></span>

<span data-ttu-id="02160-121">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="02160-121">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="02160-122">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="02160-122">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="02160-123">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="02160-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="02160-124">打开或关闭所需设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="02160-124">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="02160-125">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="02160-125">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="02160-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="02160-126">Related topics</span></span>

[<span data-ttu-id="02160-127">在 Teams 中管理私人团队的发现</span><span class="sxs-lookup"><span data-stu-id="02160-127">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)

[<span data-ttu-id="02160-128">团队中的专用频道</span><span class="sxs-lookup"><span data-stu-id="02160-128">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="02160-129">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="02160-129">Assign policies to your users in Teams</span></span>](assign-policies.md)
