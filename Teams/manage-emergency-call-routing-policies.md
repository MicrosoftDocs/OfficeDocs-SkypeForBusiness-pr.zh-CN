---
title: 管理直接路由的紧急呼叫路由策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理紧急呼叫路由策略Microsoft Teams设置紧急号码并指定紧急呼叫的路由方式。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 86f73bed2e086efee666e5592ca3f42e9756096c
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354302"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a><span data-ttu-id="0b1e4-103">管理直接路由的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="0b1e4-103">Manage emergency call routing policies for Direct Routing</span></span>

<span data-ttu-id="0b1e4-104">如果已在你的组织中电话系统直接[](direct-routing-landing-page.md)路由，可以使用 Microsoft Teams 中的紧急呼叫路由策略来设置紧急号码并指定紧急呼叫的路由方式。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="0b1e4-105">紧急呼叫路由策略确定是否为分配了该策略的用户启用增强型紧急服务、用于呼叫紧急服务 (例如，美国) 的 911 号码，以及如何路由对紧急服务的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-105">An emergency call routing policy determines whether enhanced emergency services are enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="0b1e4-106">通过以下方法管理紧急呼叫路由策略：在 Microsoft Teams 管理中心中通过语音  >  Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="0b1e4-107">可以将策略分配给用户和网络 [站点](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="0b1e4-108">对于用户，可以使用全局策略 (组织范围内的默认) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="0b1e4-109">除非创建并分配自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="0b1e4-110">请记住，可以在全局策略中编辑设置，但不能重命名或删除设置。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="0b1e4-111">对于网络站点，请创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="0b1e4-112">如果将紧急呼叫路由策略分配给网络站点和用户，并且该用户位于该网络站点，则分配给网络站点的策略将覆盖分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="0b1e4-113">创建自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="0b1e4-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0b1e4-114">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="0b1e4-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0b1e4-115">在管理中心左侧导航Microsoft Teams，转到"**语音** 紧急策略  >  "，然后单击"呼叫 **路由策略"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="0b1e4-116">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-116">Click **Add**.</span></span>
3. <span data-ttu-id="0b1e4-117">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="0b1e4-118">若要启用动态紧急呼叫，请打开 **"动态紧急呼叫"。**</span><span class="sxs-lookup"><span data-stu-id="0b1e4-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="0b1e4-119">启用动态紧急呼叫后，Teams从服务检索策略和位置信息，并包含该信息作为紧急呼叫的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="0b1e4-120">定义一个或多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="0b1e4-121">为此，请在"紧急 **号码"下** 单击" **添加**"，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0b1e4-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="0b1e4-122">**紧急拨号字符串**：输入紧急拨号字符串。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="0b1e4-123">此拨号字符串指示呼叫是紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="0b1e4-124">对于直接路由，我们正在从发送紧急Teams呼叫的客户端过渡，紧急拨号字符串前面有一个"+"。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="0b1e4-125">在转换完成之前，与紧急拨号字符串匹配的语音路由模式应确保匹配具有和没有前面"+"的字符串，例如 911 和 +911。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="0b1e4-126">例如 \\ ^+？911 或 .\*。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="0b1e4-127">**紧急拨号掩码**：对于每个紧急号码，可以指定零个或多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="0b1e4-128">拨号掩码是您想要转换为紧急拨号字符串的值的号码。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="0b1e4-129">这允许拨打备用紧急号码，同时仍可让呼叫进入紧急服务。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="0b1e4-130">例如，添加 112 作为紧急拨号掩码，这是欧洲大多数国家/地区紧急服务号码，911 作为紧急拨号字符串。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="0b1e4-131">正在Teams欧洲的用户可能不知道 911 是美国的紧急号码，当他们拨打 112 时，呼叫将拨打 911。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="0b1e4-132">若要定义多个拨号掩码，请用分号分隔每个值。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="0b1e4-133">例如，112;212。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="0b1e4-134">**PSTN 使用记录**：选择 PSTN 公用电话交换 (PSTN) 使用记录。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="0b1e4-135">PSTN 使用记录用于确定使用哪种路由来路由有权使用紧急呼叫的用户的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="0b1e4-136">与此用法关联的路由应指向专用于紧急呼叫的会话启动协议 (SIP) 中继，或指向紧急位置标识号 (ELIN) 网关，该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b1e4-137">拨号字符串和拨号掩码在策略中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="0b1e4-138">这意味着，对于策略，可以定义多个紧急号码，也可以为拨号字符串设置多个拨号掩码，但每个拨号字符串和拨号掩码只能使用一次。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="0b1e4-139">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0b1e4-140">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1e4-140">Using PowerShell</span></span>

<span data-ttu-id="0b1e4-141">请参阅[New-CsTeamsEmergencyCallRoutingPolicy。](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="0b1e4-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="0b1e4-142">编辑紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="0b1e4-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0b1e4-143">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="0b1e4-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0b1e4-144">可以编辑全局策略或创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="0b1e4-145">在管理中心左侧导航Microsoft Teams，转到"**语音** 紧急策略  >  "，然后单击"呼叫 **路由策略"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="0b1e4-146">单击策略名称的左侧以选择用户，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0b1e4-147">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0b1e4-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0b1e4-148">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1e4-148">Using PowerShell</span></span>

<span data-ttu-id="0b1e4-149">请参阅[Set-CsTeamsEmergencyCallRoutingPolicy。](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="0b1e4-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="0b1e4-150">向用户分配自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="0b1e4-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="0b1e4-151">另请参阅 [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="0b1e4-152">向网络站点分配自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="0b1e4-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="0b1e4-153">使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫路由策略分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="0b1e4-154">此示例演示如何将名为"紧急呼叫路由策略 1"的策略分配到 Site1 站点。</span><span class="sxs-lookup"><span data-stu-id="0b1e4-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="0b1e4-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="0b1e4-155">Related topics</span></span>

[<span data-ttu-id="0b1e4-156">管理紧急呼叫策略Teams</span><span class="sxs-lookup"><span data-stu-id="0b1e4-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="0b1e4-157">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="0b1e4-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="0b1e4-158">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="0b1e4-158">Assign policies to your users in Teams</span></span>](assign-policies.md)