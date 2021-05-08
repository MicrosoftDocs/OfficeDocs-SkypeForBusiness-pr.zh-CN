---
title: 在 Microsoft Teams 中管理呼叫方 ID 策略
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 了解如何使用和管理呼叫者 ID 策略Microsoft Teams更改或阻止组织中Teams用户的来电显示。
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102778"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="5e712-103">在 Microsoft Teams 中管理呼叫方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="5e712-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="5e712-104">作为管理员，可以使用呼叫者 ID 策略Microsoft Teams更改或阻止呼叫者 ID (也称为呼叫线路 ID) 。</span><span class="sxs-lookup"><span data-stu-id="5e712-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="5e712-105">默认情况下，呼叫 PSTN Teams时可以看到这些用户的电话号码，而 PSTN 呼叫者在呼叫 PSTN Teams时可以看到。</span><span class="sxs-lookup"><span data-stu-id="5e712-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="5e712-106">可以使用来电显示策略显示组织中用户Teams备用电话号码，或阻止显示传入号码。</span><span class="sxs-lookup"><span data-stu-id="5e712-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="5e712-107">例如，当用户进行呼叫时，你可以更改呼叫者 ID 以显示组织的主要电话号码，而不是用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5e712-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="5e712-108">通过访问管理中心中的"语音呼叫者  >  **ID"** 策略Microsoft Teams呼叫者 ID 策略。</span><span class="sxs-lookup"><span data-stu-id="5e712-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5e712-109">可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="5e712-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="5e712-110">除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="5e712-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="5e712-111">创建自定义来电显示策略</span><span class="sxs-lookup"><span data-stu-id="5e712-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="5e712-112">在管理中心左侧导航Microsoft Teams，转到 **"语音呼叫**  >  **者 ID 策略"。**</span><span class="sxs-lookup"><span data-stu-id="5e712-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="5e712-113">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="5e712-113">Click **Add**.</span></span> <br>
<span data-ttu-id="5e712-114">![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="5e712-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="5e712-115">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="5e712-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="5e712-116">从此处选择想要的设置：</span><span class="sxs-lookup"><span data-stu-id="5e712-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="5e712-117">**阻止来电** 显示：打开此设置，阻止显示传入呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="5e712-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="5e712-118">**替代呼叫者 ID** 策略：打开此设置，让用户覆盖策略中有关显示其号码以不向被呼叫者显示其号码的设置。</span><span class="sxs-lookup"><span data-stu-id="5e712-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="5e712-119">这意味着用户可以选择是否显示其来电显示。</span><span class="sxs-lookup"><span data-stu-id="5e712-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="5e712-120">有关详细信息，请参阅 [最终用户控制出站来电显示](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="5e712-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="5e712-121">**将呼叫方 ID 替换为**：通过选择下列选项之一，设置要显示给用户的来电显示：</span><span class="sxs-lookup"><span data-stu-id="5e712-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="5e712-122">**用户编号**：显示用户编号。</span><span class="sxs-lookup"><span data-stu-id="5e712-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="5e712-123">**服务号码**：用于设置要显示为呼叫方 ID 的服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="5e712-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="5e712-124">**匿名**：将来电显示为"匿名"。</span><span class="sxs-lookup"><span data-stu-id="5e712-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="5e712-125">**将来电显示替换为此服务号码**：选择服务号码以替换用户的来电显示。</span><span class="sxs-lookup"><span data-stu-id="5e712-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="5e712-126">如果在将呼叫方 ID 替换为 **中选择了** "服务号码 **"，则此选项可用**。</span><span class="sxs-lookup"><span data-stu-id="5e712-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="5e712-127">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5e712-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="5e712-128">编辑来电显示策略</span><span class="sxs-lookup"><span data-stu-id="5e712-128">Edit a caller ID policy</span></span>

<span data-ttu-id="5e712-129">可以编辑全局策略或创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="5e712-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="5e712-130">在管理中心左侧导航Microsoft Teams，转到 **"语音呼叫**  >  **者 ID 策略"。**</span><span class="sxs-lookup"><span data-stu-id="5e712-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="5e712-131">单击策略名称的左侧以选择用户，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="5e712-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="5e712-132">更改想要的设置，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="5e712-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="5e712-133">向用户分配自定义来电显示策略</span><span class="sxs-lookup"><span data-stu-id="5e712-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="5e712-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="5e712-134">Related topics</span></span>

[<span data-ttu-id="5e712-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="5e712-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="5e712-136">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="5e712-136">Assign policies to your users in Teams</span></span>](assign-policies.md)