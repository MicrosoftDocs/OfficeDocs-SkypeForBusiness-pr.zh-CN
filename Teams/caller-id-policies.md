---
title: 管理 Microsoft 团队中的呼叫者 ID 策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的呼叫者 ID 策略更改或阻止组织中的团队用户的来电显示 ID。
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938461"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="23a69-103">管理 Microsoft 团队中的呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="23a69-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="23a69-104">作为管理员，你可以使用 Microsoft 团队中的来电显示策略来更改或阻止来电显示（也称为呼叫线路 ID）。</span><span class="sxs-lookup"><span data-stu-id="23a69-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="23a69-105">默认情况下，当用户呼叫 PSTN 电话时，可以看到团队用户的电话号码，并且在呼叫团队用户时可以看到 PSTN 呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="23a69-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="23a69-106">可以使用来电显示策略为组织中的团队用户显示备用电话号码，或阻止显示传入号码。</span><span class="sxs-lookup"><span data-stu-id="23a69-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="23a69-107">例如，当用户进行呼叫时，您可以更改来电显示以显示组织的主要电话号码，而不是用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="23a69-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="23a69-108">通过转到**Voice**  >  "Microsoft 团队管理中心" 中的 "语音来电显示"**策略**来管理呼叫者 id 策略。</span><span class="sxs-lookup"><span data-stu-id="23a69-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="23a69-109">你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="23a69-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="23a69-110">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="23a69-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="23a69-111">创建自定义呼叫方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="23a69-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="23a69-112">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。</span><span class="sxs-lookup"><span data-stu-id="23a69-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="23a69-113">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23a69-113">Click **Add**.</span></span> <br>
<span data-ttu-id="23a69-114">![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="23a69-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="23a69-115">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="23a69-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="23a69-116">在此处，选择所需的设置：</span><span class="sxs-lookup"><span data-stu-id="23a69-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="23a69-117">**阻止来电呼叫者 id**：启用此设置可阻止显示传入呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="23a69-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="23a69-118">**替代呼叫方 ID 策略**：启用此设置，让用户覆盖策略中的设置以将其号码显示为 callees。</span><span class="sxs-lookup"><span data-stu-id="23a69-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="23a69-119">这意味着用户可以选择是否要显示其呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="23a69-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="23a69-120">有关详细信息，请参阅[最终用户对出站呼叫程序 ID 的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="23a69-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="23a69-121">将**来电显示替换**为：通过选择下列操作之一，设置要为用户显示的呼叫者 id：</span><span class="sxs-lookup"><span data-stu-id="23a69-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="23a69-122">**用户号码**：显示用户的号码。</span><span class="sxs-lookup"><span data-stu-id="23a69-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="23a69-123">**服务号码**：允许您将服务电话号码设置为显示为呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="23a69-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="23a69-124">**匿名**：以匿名方式显示呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="23a69-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="23a69-125">**将呼叫方 Id 替换为此服务号码**：选择服务号码以替换用户的来电显示。</span><span class="sxs-lookup"><span data-stu-id="23a69-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="23a69-126">如果在 **"将呼叫方 ID 替换为**" 中选择了 "**服务编号**"，则此选项可用。</span><span class="sxs-lookup"><span data-stu-id="23a69-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="23a69-127">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="23a69-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="23a69-128">编辑呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="23a69-128">Edit a caller ID policy</span></span>

<span data-ttu-id="23a69-129">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="23a69-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="23a69-130">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。</span><span class="sxs-lookup"><span data-stu-id="23a69-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="23a69-131">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="23a69-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="23a69-132">更改所需的设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="23a69-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="23a69-133">为用户分配自定义呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="23a69-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="23a69-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="23a69-134">Related topics</span></span>

[<span data-ttu-id="23a69-135">新-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="23a69-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="23a69-136">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="23a69-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
