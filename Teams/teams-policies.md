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
ms.openlocfilehash: ad7dadc60b1fb53a518ec5cab340739a89f6b044
ms.sourcegitcommit: 6f4928e9e7e67fe65320131ae9e7348b948d86ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48297368"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="2a232-103">管理 Microsoft 团队中的团队策略</span><span class="sxs-lookup"><span data-stu-id="2a232-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="2a232-104">作为管理员，你可以使用 Microsoft 团队中的团队策略控制你的组织中的哪些用户可以在团队和频道中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2a232-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="2a232-105">例如，您可以设置是否允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="2a232-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="2a232-106">通过转到**Teams**  >  Microsoft 团队管理中心中的团队**团队策略**管理团队策略。</span><span class="sxs-lookup"><span data-stu-id="2a232-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2a232-107">你可以使用全局 (组织范围默认) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2a232-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2a232-108">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="2a232-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="2a232-109">你可以编辑全局策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2a232-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="2a232-110">编辑全局策略或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="2a232-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="2a232-111">创建自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="2a232-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="2a232-112">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="2a232-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="2a232-113">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a232-113">Click **Add**.</span></span>
3. <span data-ttu-id="2a232-114">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2a232-114">Enter a name and description for the policy.</span></span>

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. <span data-ttu-id="2a232-116">打开或关闭 "**创建专用频道**"， <a name="createchannels"> </a>具体取决于是否希望允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="2a232-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="2a232-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2a232-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="2a232-118">编辑团队策略</span><span class="sxs-lookup"><span data-stu-id="2a232-118">Edit a teams policy</span></span>

<span data-ttu-id="2a232-119">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2a232-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="2a232-120">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="2a232-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="2a232-121">通过单击策略名称左侧，然后单击 " **编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="2a232-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2a232-122">打开或关闭所需设置，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2a232-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="2a232-123">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="2a232-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="2a232-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="2a232-124">Related topics</span></span>

[<span data-ttu-id="2a232-125">团队中的专用频道</span><span class="sxs-lookup"><span data-stu-id="2a232-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="2a232-126">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="2a232-126">Assign policies to your users in Teams</span></span>](assign-policies.md)
