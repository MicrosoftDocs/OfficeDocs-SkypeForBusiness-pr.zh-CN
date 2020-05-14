---
title: 分配语音路由策略
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要：阅读本主题，了解如何为使用具有本地 PSTN 连接的电话系统的用户分配语音策略。
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221856"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="078ef-103">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="078ef-104">**摘要：** 阅读本主题，了解如何为使用具有本地 PSTN 连接的电话系统的用户分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="078ef-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="078ef-105">一旦用户在 Skype for Business Online 中使用具有本地 PSTN 连接的电话系统，将对其应用两个语音策略。</span><span class="sxs-lookup"><span data-stu-id="078ef-105">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="078ef-106">一个是您将在本地分配的本地语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="078ef-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="078ef-107">此策略可以是全局策略，也可以是特定于用户的策略，并定义哪些 PSTN 用法记录与用户相关联。</span><span class="sxs-lookup"><span data-stu-id="078ef-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="078ef-108">本主题说明如何分配此策略。</span><span class="sxs-lookup"><span data-stu-id="078ef-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="078ef-109">其他语音策略定义了用户可以使用的呼叫功能;此语音策略由 Microsoft 定义，对于具有本地 PSTN 连接用户的所有电话系统都是相同的。</span><span class="sxs-lookup"><span data-stu-id="078ef-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="078ef-110">它将自动分配给电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="078ef-110">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="078ef-111">**本地用户**</span><span class="sxs-lookup"><span data-stu-id="078ef-111">**On-premises user**</span></span>|<span data-ttu-id="078ef-112">**具有本地 PSTN 连接用户的电话系统**</span><span class="sxs-lookup"><span data-stu-id="078ef-112">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="078ef-113">中定义的呼叫功能</span><span class="sxs-lookup"><span data-stu-id="078ef-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="078ef-114">语音策略</span><span class="sxs-lookup"><span data-stu-id="078ef-114">Voice policy</span></span>  <br/> |<span data-ttu-id="078ef-115">预定义的语音策略，在用户许可电话系统时自动分配。</span><span class="sxs-lookup"><span data-stu-id="078ef-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="078ef-116">与相关联的 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="078ef-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="078ef-117">语音策略</span><span class="sxs-lookup"><span data-stu-id="078ef-117">Voice policy</span></span>  <br/> |<span data-ttu-id="078ef-118">语音路由策略，在用户仍在本地托管的情况下进行分配。</span><span class="sxs-lookup"><span data-stu-id="078ef-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="078ef-119">您可以使用本地部署执行以下步骤，而用户仍驻留在本地部署中。</span><span class="sxs-lookup"><span data-stu-id="078ef-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="078ef-120">使用全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-120">Using a global voice routing policy</span></span>

<span data-ttu-id="078ef-121">在使用具有本地 PSTN 连接用户的电话系统的全局语音路由策略之前，必须向策略中添加 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="078ef-121">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="078ef-122">将 PSTN 用法记录分配给全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="078ef-123">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="078ef-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="078ef-124">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="078ef-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="078ef-125">将 PSTN 用法记录添加到策略：</span><span class="sxs-lookup"><span data-stu-id="078ef-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="078ef-126">例如：</span><span class="sxs-lookup"><span data-stu-id="078ef-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="078ef-127">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="078ef-128">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="078ef-129">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="078ef-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="078ef-130">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="078ef-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="078ef-131">创建新的语音路由策略：</span><span class="sxs-lookup"><span data-stu-id="078ef-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="078ef-132">例如：</span><span class="sxs-lookup"><span data-stu-id="078ef-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="078ef-133">本示例创建名为为 hybridvoice 的新的语音路由策略，该策略有两个与之关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="078ef-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="078ef-134">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="078ef-135">无论您使用的是全局语音路由策略还是特定于用户的策略，都可以使用以下步骤将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="078ef-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="078ef-136">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="078ef-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="078ef-137">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="078ef-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="078ef-138">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="078ef-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="078ef-139">向用户分配现有语音策略：</span><span class="sxs-lookup"><span data-stu-id="078ef-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="078ef-140">例如：</span><span class="sxs-lookup"><span data-stu-id="078ef-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="078ef-141">在此示例中，显示名称为小明凯利的用户分配给以前创建的名为为 hybridvoice 的语音策略。</span><span class="sxs-lookup"><span data-stu-id="078ef-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="078ef-142">有关语音路由策略的更多详细信息，请参阅[Create or modify a voice policy and CONFIGURE PSTN usage records In Skype For business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、 [Grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和[Grant set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="078ef-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

