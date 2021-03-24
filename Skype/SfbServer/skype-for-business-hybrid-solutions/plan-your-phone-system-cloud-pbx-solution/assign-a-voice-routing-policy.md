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
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092960"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="4b406-103">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="4b406-104">Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。</span><span class="sxs-lookup"><span data-stu-id="4b406-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="4b406-105">此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="4b406-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="4b406-106">了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="4b406-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4b406-107">**摘要：** 阅读本主题，了解如何为使用具有本地 PSTN 连接的电话系统的用户分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="4b406-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="4b406-108">一旦用户位于 Skype for Business Online 上，并且将电话系统与本地 PSTN 连接一同使用，两个语音策略将应用于他们。</span><span class="sxs-lookup"><span data-stu-id="4b406-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="4b406-109">一种是您将在本地分配本地语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="4b406-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="4b406-110">此策略可以是全局策略或特定于用户的策略，并定义与用户关联的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="4b406-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="4b406-111">本主题介绍如何分配此策略。</span><span class="sxs-lookup"><span data-stu-id="4b406-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="4b406-112">另一个语音策略定义哪些呼叫功能可供用户使用;此语音策略由 Microsoft 定义，对于具有本地 PSTN 连接用户的所有电话系统是相同的。</span><span class="sxs-lookup"><span data-stu-id="4b406-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="4b406-113">它会自动分配给电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="4b406-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="4b406-114">**本地用户**</span><span class="sxs-lookup"><span data-stu-id="4b406-114">**On-premises user**</span></span>|<span data-ttu-id="4b406-115">**具有本地 PSTN 连接用户的电话系统**</span><span class="sxs-lookup"><span data-stu-id="4b406-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b406-116">中定义的调用功能</span><span class="sxs-lookup"><span data-stu-id="4b406-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="4b406-117">语音策略</span><span class="sxs-lookup"><span data-stu-id="4b406-117">Voice policy</span></span>  <br/> |<span data-ttu-id="4b406-118">预定义的语音策略，在用户获得电话系统许可时自动分配。</span><span class="sxs-lookup"><span data-stu-id="4b406-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="4b406-119">关联的 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="4b406-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="4b406-120">语音策略</span><span class="sxs-lookup"><span data-stu-id="4b406-120">Voice policy</span></span>  <br/> |<span data-ttu-id="4b406-121">语音路由策略，在用户仍位于本地时分配。</span><span class="sxs-lookup"><span data-stu-id="4b406-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="4b406-122">使用本地部署执行以下步骤，同时用户仍位于本地部署中。</span><span class="sxs-lookup"><span data-stu-id="4b406-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="4b406-123">使用全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-123">Using a global voice routing policy</span></span>

<span data-ttu-id="4b406-124">在将电话系统的全局语音路由策略用于本地 PSTN 连接用户之前，必须将 PSTN 用法记录添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="4b406-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="4b406-125">将 PSTN 用法记录分配给全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="4b406-126">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4b406-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b406-127">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="4b406-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4b406-128">将 PSTN 用法记录添加到策略：</span><span class="sxs-lookup"><span data-stu-id="4b406-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="4b406-129">例如：</span><span class="sxs-lookup"><span data-stu-id="4b406-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="4b406-130">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="4b406-131">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="4b406-132">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4b406-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b406-133">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="4b406-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4b406-134">创建新的语音路由策略：</span><span class="sxs-lookup"><span data-stu-id="4b406-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="4b406-135">例如：</span><span class="sxs-lookup"><span data-stu-id="4b406-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="4b406-136">此示例创建名为 HybridVoice 的新语音路由策略，该策略具有两个与之关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="4b406-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="4b406-137">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="4b406-138">无论您使用全局语音路由策略还是特定于用户的语音路由策略，都请使用以下步骤将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="4b406-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="4b406-139">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4b406-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="4b406-140">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4b406-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4b406-141">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="4b406-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4b406-142">向用户分配现有语音策略：</span><span class="sxs-lookup"><span data-stu-id="4b406-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="4b406-143">例如：</span><span class="sxs-lookup"><span data-stu-id="4b406-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="4b406-144">本示例中，将具有 显示名称 Bob Kelly 的用户分配给先前创建的语音策略，其名称为 HybridVoice。</span><span class="sxs-lookup"><span data-stu-id="4b406-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="4b406-145">有关语音路由策略的更多详细信息，请参阅 Create [or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和 [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4b406-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
