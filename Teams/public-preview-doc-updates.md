---
title: Microsoft Teams 中的公共预览版
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Microsoft Teams 中的公共预览版。尝试新增功能并提供反馈。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0719e68dcbf1c73c15ee58e8c7d6be08f359aa5
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863253"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="715ab-104">Microsoft Teams 公共预览版</span><span class="sxs-lookup"><span data-stu-id="715ab-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="715ab-p102">预览版中包含的功能可能并不完整，在公开发布之前可能会发生更改。所提供的这些功能仅用于评估和探索目的。不支持Office 365 政府版社区云（GCC）。</span><span class="sxs-lookup"><span data-stu-id="715ab-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. Not supported in Office 365 Government Community Cloud (GCC).</span></span>

<span data-ttu-id="715ab-p103">Microsoft Teams 的公共预览版可让用户抢先体验 Teams 中的未发布功能。预览版允许探索和测试即将推出的功能。我们也欢迎大家对公共预览版中的任何功能提出反馈意见。公共预览版是为每个 Teams 用户单独启用的，因此不必担心影响整个组织。</span><span class="sxs-lookup"><span data-stu-id="715ab-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="715ab-112">有关 Teams 公共预览版中可用功能的列表，请访问 [Office 当前频道（预览）发行说明](/officeupdates/current-channel-preview)。</span><span class="sxs-lookup"><span data-stu-id="715ab-112">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="715ab-113">设置更新策略</span><span class="sxs-lookup"><span data-stu-id="715ab-113">Set the Update policy</span></span>

<span data-ttu-id="715ab-p104">为每个用户启用公共预览，并在管理策略中控制打开公共预览的选项。更新策略用于管理 Teams 和 Office 预览用户，这些用户将会在 Teams 应用中看到预发布或预览功能。你可以使用全局（Org-wide默认）策略并对其进行自定义，或者为用户创建一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="715ab-p104">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="715ab-118">登录到管理中心。</span><span class="sxs-lookup"><span data-stu-id="715ab-118">Sign in to the admin center.</span></span>
2. <span data-ttu-id="715ab-119">选择“**Teams**”>“**更新策略**”。</span><span class="sxs-lookup"><span data-stu-id="715ab-119">Select **Teams**>**Update policies**.</span></span>

   ![选择“更新策略”选项](media/updatePolicies.png)

3. <span data-ttu-id="715ab-121">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="715ab-121">Select **Add**.</span></span>
4. <span data-ttu-id="715ab-122">为更新策略命名，添加说明，然后打开“**显示预览功能**”。</span><span class="sxs-lookup"><span data-stu-id="715ab-122">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="715ab-123">你也可以用 PowerShell 的 `CsTeamsUpdateManagementPolicy`cmdlet 来设置策略。</span><span class="sxs-lookup"><span data-stu-id="715ab-123">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="715ab-124">启用公共预览版</span><span class="sxs-lookup"><span data-stu-id="715ab-124">Enable public preview</span></span>

<span data-ttu-id="715ab-125">若要在桌面或 Web 客户端上启用公共预览版，你需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="715ab-125">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="715ab-126">选择个人资料左侧的三个圆点，以显示 Teams 菜单。</span><span class="sxs-lookup"><span data-stu-id="715ab-126">Select the three dots to the left of your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="715ab-127">选择“**关于** > **公共预览版**”。</span><span class="sxs-lookup"><span data-stu-id="715ab-127">Select **About** > **Public preview**.</span></span>
3. <span data-ttu-id="715ab-128">选择“**切换到公共预览版**”。</span><span class="sxs-lookup"><span data-stu-id="715ab-128">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="715ab-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="715ab-129">Related topics</span></span>

[<span data-ttu-id="715ab-130">公共开发人员预览版</span><span class="sxs-lookup"><span data-stu-id="715ab-130">Public developer preview</span></span>](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
