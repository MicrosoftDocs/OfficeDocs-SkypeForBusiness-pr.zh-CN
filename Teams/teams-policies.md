---
title: 在 Microsoft Teams 中管理团队策略
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: 了解如何在组织中使用和管理团队策略来控制用户可在团队和频道中执行哪些操作。
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094202"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="35b61-103">在 Microsoft Teams 中管理团队策略</span><span class="sxs-lookup"><span data-stu-id="35b61-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="35b61-104">作为管理员，可以使用 Microsoft Teams 中的团队策略来控制组织中用户可在团队和频道中执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="35b61-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="35b61-105">例如，可以设置是否允许用户创建专用通道。</span><span class="sxs-lookup"><span data-stu-id="35b61-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="35b61-106">通过访问 Microsoft Teams 管理中心 **中的 Teams**  >  **Teams** 策略来管理团队策略。</span><span class="sxs-lookup"><span data-stu-id="35b61-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="35b61-107">可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="35b61-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="35b61-108">除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="35b61-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="35b61-109">可以编辑全局策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="35b61-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="35b61-110">编辑全局策略或分配策略后，可能需要几个小时更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="35b61-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="35b61-111">创建自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="35b61-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="35b61-112">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams**  >  **Teams 策略"。**</span><span class="sxs-lookup"><span data-stu-id="35b61-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="35b61-113">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="35b61-113">Click **Add**.</span></span>
3. <span data-ttu-id="35b61-114">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="35b61-114">Enter a name and description for the policy.</span></span>

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. <span data-ttu-id="35b61-116">打开或关闭 **"创建专用通道**<a name="createchannels"></a>"，具体取决于是否要允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="35b61-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="35b61-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="35b61-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="35b61-118">编辑团队策略</span><span class="sxs-lookup"><span data-stu-id="35b61-118">Edit a teams policy</span></span>

<span data-ttu-id="35b61-119">可以编辑全局策略或创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="35b61-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="35b61-120">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams**  >  **Teams 策略"。**</span><span class="sxs-lookup"><span data-stu-id="35b61-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="35b61-121">单击策略名称的左侧以选择用户，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="35b61-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="35b61-122">打开或关闭想要的设置，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="35b61-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="35b61-123">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="35b61-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="35b61-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="35b61-124">Related topics</span></span>

[<span data-ttu-id="35b61-125">Teams 中的专用频道</span><span class="sxs-lookup"><span data-stu-id="35b61-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="35b61-126">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="35b61-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="35b61-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="35b61-127">New-CsTeamsChannelsPolicy</span></span>](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)