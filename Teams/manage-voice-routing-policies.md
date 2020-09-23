---
title: 管理 Microsoft 团队中的语音路由策略
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队中创建和管理语音路由策略。
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217653"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="fcc52-103">管理 Microsoft 团队中的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="fcc52-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="fcc52-104">如果你已在组织中部署了 [手机系统直接路由](direct-routing-landing-page.md) ，则使用 "语音路由策略" 允许团队和 Skype For business Online 用户使用本地电话基础结构接收和拨打电话给公共交换电话网络 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="fcc52-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="fcc52-105">"语音路由策略" 是 PSTN 使用记录的容器。</span><span class="sxs-lookup"><span data-stu-id="fcc52-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="fcc52-106">通过转到**Voice**  >  Microsoft 团队管理中心或使用 Windows PowerShell 中的语音**语音路由策略**来创建和管理语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="fcc52-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="fcc52-107">你可以使用全局 (组织范围默认) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="fcc52-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="fcc52-108">除非你创建并分配自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="fcc52-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="fcc52-109">请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="fcc52-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="fcc52-110">请务必知道，向用户分配语音路由策略不会使其能够在团队中进行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="fcc52-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="fcc52-111">您还需要为用户启用 "电话系统直接路由"，并完成其他配置步骤。</span><span class="sxs-lookup"><span data-stu-id="fcc52-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="fcc52-112">若要了解详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc52-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="fcc52-113">创建自定义语音路由策略</span><span class="sxs-lookup"><span data-stu-id="fcc52-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fcc52-114">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="fcc52-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fcc52-115">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="fcc52-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="fcc52-116">![Microsoft 团队管理中心中 "添加语音路由策略" 页面的屏幕截图 ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="fcc52-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="fcc52-117">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="fcc52-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="fcc52-118">在 " **PSTN 使用记录**" 下，单击 " **添加 PSTN 使用情况**"，然后选择要添加的记录。</span><span class="sxs-lookup"><span data-stu-id="fcc52-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="fcc52-119">如果需要创建新的 PSTN 使用记录，请单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="fcc52-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="fcc52-120">如果您添加了多个 PSTN 使用记录，请按所需顺序排列它们。</span><span class="sxs-lookup"><span data-stu-id="fcc52-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="fcc52-121">完成后，单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="fcc52-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="fcc52-122">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fcc52-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fcc52-123">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcc52-123">Using PowerShell</span></span>

<span data-ttu-id="fcc52-124">请参阅 [新-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fcc52-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="fcc52-125">编辑语音路由策略</span><span class="sxs-lookup"><span data-stu-id="fcc52-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fcc52-126">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="fcc52-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="fcc52-127">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="fcc52-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="fcc52-128">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"。</span><span class="sxs-lookup"><span data-stu-id="fcc52-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="fcc52-129">通过单击策略名称左侧，然后单击 " **编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="fcc52-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="fcc52-130">单击 " **添加/删除 PSTN 使用记录**"，进行所需的更改，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="fcc52-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fcc52-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcc52-131">Using PowerShell</span></span>

<span data-ttu-id="fcc52-132">请参阅 [设置-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fcc52-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="fcc52-133">为用户分配自定义语音路由策略</span><span class="sxs-lookup"><span data-stu-id="fcc52-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="fcc52-134">另请参阅 [授权 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fcc52-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fcc52-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="fcc52-135">Related topics</span></span>

[<span data-ttu-id="fcc52-136">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="fcc52-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="fcc52-137">为直接路由配置语音路由</span><span class="sxs-lookup"><span data-stu-id="fcc52-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="fcc52-138">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="fcc52-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="fcc52-139">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="fcc52-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
