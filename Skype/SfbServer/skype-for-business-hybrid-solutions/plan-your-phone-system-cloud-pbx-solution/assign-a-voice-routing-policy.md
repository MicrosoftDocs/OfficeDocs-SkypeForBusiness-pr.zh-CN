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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '摘要: 阅读本主题, 了解如何使用本地 PSTN 连接为使用 Office 365 中的电话系统的用户分配语音策略。'
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294430"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="b0338-103">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b0338-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="b0338-104">**摘要:** 阅读本主题, 了解如何使用本地 PSTN 连接为使用 Office 365 中的电话系统的用户分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="b0338-105">一旦用户使用 Skype for Business Online 并在 Office 365 中使用 "电话系统" 与本地 PSTN 连接, 将对其应用两个语音策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="b0338-106">一个是您将在本地分配的本地语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="b0338-107">此策略可以是全局策略或特定于用户的, 并且定义了哪些 PSTN 使用记录与用户相关联。</span><span class="sxs-lookup"><span data-stu-id="b0338-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="b0338-108">本主题介绍了如何分配此策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="b0338-109">其他语音政策定义用户可以使用哪些通话功能;此语音政策由 Microsoft 定义, 对于 Office 365 中的所有电话系统, 与本地 PSTN 连接用户是相同的。</span><span class="sxs-lookup"><span data-stu-id="b0338-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="b0338-110">它会自动分配给 Office 365 用户中的电话系统。</span><span class="sxs-lookup"><span data-stu-id="b0338-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="b0338-111">**本地用户**</span><span class="sxs-lookup"><span data-stu-id="b0338-111">**On-premises user**</span></span>|<span data-ttu-id="b0338-112">**使用本地 PSTN 连接用户的 Office 365 中的电话系统**</span><span class="sxs-lookup"><span data-stu-id="b0338-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0338-113">定义的呼叫功能</span><span class="sxs-lookup"><span data-stu-id="b0338-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="b0338-114">语音策略</span><span class="sxs-lookup"><span data-stu-id="b0338-114">Voice policy</span></span>  <br/> |<span data-ttu-id="b0338-115">预定义的语音策略, 在用户使用 Office 365 中的电话系统授权时自动分配。</span><span class="sxs-lookup"><span data-stu-id="b0338-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="b0338-116">相关联的 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="b0338-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="b0338-117">语音策略</span><span class="sxs-lookup"><span data-stu-id="b0338-117">Voice policy</span></span>  <br/> |<span data-ttu-id="b0338-118">当用户仍驻留在本地时分配的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="b0338-119">使用本地部署执行以下步骤, 而用户仍托管在本地部署中。</span><span class="sxs-lookup"><span data-stu-id="b0338-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="b0338-120">使用全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b0338-120">Using a global voice routing policy</span></span>

<span data-ttu-id="b0338-121">在使用本地 PSTN 连接用户在 Office 365 中为您的电话系统使用全局语音路由策略之前, 必须将 PSTN 使用记录添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="b0338-122">向全局语音路由策略分配 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="b0338-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="b0338-123">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b0338-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0338-124">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0338-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b0338-125">将 PSTN 使用记录添加到策略:</span><span class="sxs-lookup"><span data-stu-id="b0338-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="b0338-126">例如：</span><span class="sxs-lookup"><span data-stu-id="b0338-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="b0338-127">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b0338-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="b0338-128">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b0338-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="b0338-129">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b0338-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0338-130">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0338-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b0338-131">创建新的语音路由策略：</span><span class="sxs-lookup"><span data-stu-id="b0338-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="b0338-132">例如：</span><span class="sxs-lookup"><span data-stu-id="b0338-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="b0338-133">此示例将创建名为 HybridVoice 的新语音路由策略，它有两个相关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="b0338-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="b0338-134">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b0338-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="b0338-135">无论您使用的是全局语音路由策略还是用户特定的语音路由策略，请按照以下步骤为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="b0338-136">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b0338-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="b0338-137">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b0338-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0338-138">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0338-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b0338-139">向用户分配现有语音策略：</span><span class="sxs-lookup"><span data-stu-id="b0338-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="b0338-140">例如：</span><span class="sxs-lookup"><span data-stu-id="b0338-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="b0338-141">在此示例中，向显示名称为 Bob Kelly 的用户分配之前创建的名为 HybridVoice 的语音策略。</span><span class="sxs-lookup"><span data-stu-id="b0338-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="b0338-142">有关语音路由策略的更多详细信息, 请参阅在 Skype for Business 2015、 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)[中创建或修改语音策略和配置 PSTN 使用记录](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="b0338-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

