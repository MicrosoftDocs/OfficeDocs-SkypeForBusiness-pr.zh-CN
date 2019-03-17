---
title: 分配语音路由策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
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
description: 摘要： 阅读本主题可了解如何分配 Office 365 中的电话系统使用内部部署 PSTN 连接的用户的语音策略。
ms.openlocfilehash: 12e74a6ea4a0adf652cc4e9477d20f91b4e13732
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657438"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="73b46-103">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="73b46-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="73b46-104">**摘要：** 阅读本主题可了解如何分配 Office 365 中的电话系统使用内部部署 PSTN 连接的用户的语音策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="73b46-105">Skype 业务 Online 和 Office 365 中的电话系统使用内部部署 PSTN 连接上用户后，两个语音策略将应用于它们。</span><span class="sxs-lookup"><span data-stu-id="73b46-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="73b46-106">一个是在本地将分配给内部部署语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="73b46-107">此策略可以是全局或特定于用户并定义与用户关联的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="73b46-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="73b46-108">本主题介绍了如何分配此策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="73b46-109">其他语音策略定义了哪些呼叫功能可供用户;此语音策略定义由 Microsoft，相同的 Office 365 中的所有电话系统与内部部署 PSTN 连接用户。</span><span class="sxs-lookup"><span data-stu-id="73b46-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="73b46-110">它是自动分配给电话系统中的 Office 365 用户。</span><span class="sxs-lookup"><span data-stu-id="73b46-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="73b46-111">**本地用户**</span><span class="sxs-lookup"><span data-stu-id="73b46-111">**On-premises user**</span></span>|<span data-ttu-id="73b46-112">**与内部部署 PSTN 连接用户的 Office 365 中的电话系统**</span><span class="sxs-lookup"><span data-stu-id="73b46-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73b46-113">定义的呼叫功能</span><span class="sxs-lookup"><span data-stu-id="73b46-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="73b46-114">语音策略</span><span class="sxs-lookup"><span data-stu-id="73b46-114">Voice policy</span></span>  <br/> |<span data-ttu-id="73b46-115">预定义用户许可 Office 365 中的电话系统时自动分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="73b46-116">相关联的 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="73b46-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="73b46-117">语音策略</span><span class="sxs-lookup"><span data-stu-id="73b46-117">Voice policy</span></span>  <br/> |<span data-ttu-id="73b46-118">当用户仍驻留在本地时分配的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="73b46-119">执行以下步骤时用户仍驻留在本地部署中使用您的本地部署。</span><span class="sxs-lookup"><span data-stu-id="73b46-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="73b46-120">使用全局语音路由策略</span><span class="sxs-lookup"><span data-stu-id="73b46-120">Using a global voice routing policy</span></span>

<span data-ttu-id="73b46-121">内部部署 PSTN 连接用户与电话系统 Office 365 中使用全局语音路由策略之前, 必须向策略中添加 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="73b46-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="73b46-122">向全局语音路由策略分配 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="73b46-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="73b46-123">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="73b46-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="73b46-124">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73b46-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73b46-125">向策略中添加 PSTN 用法记录：</span><span class="sxs-lookup"><span data-stu-id="73b46-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="73b46-126">例如：</span><span class="sxs-lookup"><span data-stu-id="73b46-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="73b46-127">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="73b46-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="73b46-128">创建新的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="73b46-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="73b46-129">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="73b46-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="73b46-130">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73b46-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73b46-131">创建新的语音路由策略：</span><span class="sxs-lookup"><span data-stu-id="73b46-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="73b46-132">例如：</span><span class="sxs-lookup"><span data-stu-id="73b46-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="73b46-133">此示例将创建名为 HybridVoice 的新语音路由策略，它有两个相关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="73b46-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="73b46-134">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="73b46-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="73b46-135">无论您使用的是全局语音路由策略还是用户特定的语音路由策略，请按照以下步骤为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="73b46-136">分配语音路由策略</span><span class="sxs-lookup"><span data-stu-id="73b46-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="73b46-137">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="73b46-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="73b46-138">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73b46-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73b46-139">向用户分配现有语音策略：</span><span class="sxs-lookup"><span data-stu-id="73b46-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="73b46-140">例如：</span><span class="sxs-lookup"><span data-stu-id="73b46-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="73b46-141">在此示例中，向显示名称为 Bob Kelly 的用户分配之前创建的名为 HybridVoice 的语音策略。</span><span class="sxs-lookup"><span data-stu-id="73b46-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="73b46-142">有关语音路由策略的详细信息，请参阅[创建或修改语音策略和配置 PSTN 用法记录中的业务 2015 Skype](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)， [New-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)和[Grant-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="73b46-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

