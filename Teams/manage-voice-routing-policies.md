---
title: 管理直接路由的语音路由策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在语音路由服务中创建和管理Microsoft Teams。
ms.openlocfilehash: 7023100850eb34d6adf61c99de5f3568afed6aeb
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354282"
---
# <a name="manage-voice-routing-policies-for-direct-routing"></a><span data-ttu-id="90ee0-103">管理直接路由的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="90ee0-103">Manage voice routing policies for Direct Routing</span></span>

<span data-ttu-id="90ee0-104">如果已在你的组织中部署了[电话系统 直接](direct-routing-landing-page.md)路由，则使用语音路由策略允许 Teams 和 Skype for Business Online 用户使用本地电话基础结构接收公用电话交换网 (PSTN) 并拨打电话。</span><span class="sxs-lookup"><span data-stu-id="90ee0-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="90ee0-105">语音路由策略是 PSTN 使用记录的容器。</span><span class="sxs-lookup"><span data-stu-id="90ee0-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="90ee0-106">可创建和管理语音路由策略，方法为在管理中心内Microsoft Teams语音路由策略  >  ，或者使用语音Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="90ee0-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="90ee0-107">可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="90ee0-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="90ee0-108">除非创建并分配自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="90ee0-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="90ee0-109">请记住，可以在全局策略中编辑设置，但不能重命名或删除设置。</span><span class="sxs-lookup"><span data-stu-id="90ee0-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="90ee0-110">请务必知道，向用户分配语音路由策略并不能让他们在呼叫中拨打 PSTN Teams。</span><span class="sxs-lookup"><span data-stu-id="90ee0-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="90ee0-111">还需要为用户启用直接路由电话系统完成其他配置步骤。</span><span class="sxs-lookup"><span data-stu-id="90ee0-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="90ee0-112">有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="90ee0-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="90ee0-113">创建自定义语音路由策略</span><span class="sxs-lookup"><span data-stu-id="90ee0-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="90ee0-114">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="90ee0-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="90ee0-115">在管理中心的左侧导航Microsoft Teams，转到 **"**  >  **语音语音路由策略**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="90ee0-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="90ee0-116">![管理中心内"添加语音路由策略"Microsoft Teams屏幕截图](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="90ee0-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="90ee0-117">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="90ee0-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="90ee0-118">在 **"PSTN 使用记录"** 下，单击"添加 **PSTN** 使用情况"，然后选择要添加的记录。</span><span class="sxs-lookup"><span data-stu-id="90ee0-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="90ee0-119">如果需要创建新的 PSTN 使用记录，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="90ee0-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="90ee0-120">如果添加了多个 PSTN 使用记录，请按您需要的顺序排列这些记录。</span><span class="sxs-lookup"><span data-stu-id="90ee0-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="90ee0-121">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="90ee0-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="90ee0-122">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="90ee0-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="90ee0-123">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ee0-123">Using PowerShell</span></span>

<span data-ttu-id="90ee0-124">请参阅 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="90ee0-124">See [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="90ee0-125">编辑语音路由策略</span><span class="sxs-lookup"><span data-stu-id="90ee0-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="90ee0-126">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="90ee0-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="90ee0-127">可以编辑全局策略或创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="90ee0-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="90ee0-128">在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **语音路由策略"。**</span><span class="sxs-lookup"><span data-stu-id="90ee0-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="90ee0-129">单击策略名称的左侧以选择用户，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="90ee0-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="90ee0-130">单击 **"添加/删除 PSTN 使用** 记录"，进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="90ee0-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="90ee0-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ee0-131">Using PowerShell</span></span>

<span data-ttu-id="90ee0-132">请参阅 [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="90ee0-132">See [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="90ee0-133">向用户分配自定义语音路由策略</span><span class="sxs-lookup"><span data-stu-id="90ee0-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="90ee0-134">另请参阅 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="90ee0-134">See also [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="90ee0-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="90ee0-135">Related topics</span></span>

[<span data-ttu-id="90ee0-136">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="90ee0-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="90ee0-137">为直接路由配置语音路由</span><span class="sxs-lookup"><span data-stu-id="90ee0-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="90ee0-138">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="90ee0-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="90ee0-139">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="90ee0-139">Assign policies to your users in Teams</span></span>](assign-policies.md)