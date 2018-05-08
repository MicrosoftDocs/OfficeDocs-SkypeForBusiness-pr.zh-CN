---
title: 在 Skype for Business Server 2015 中创建位置策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 阅读本主题可了解如何配置 Business Server 企业语音的增强型紧急服务 (E9-1-1) 在 Skype 的位置策略。
ms.openlocfilehash: 2bb2d7fad7906d78d5118f219b0b85d92dd97b23
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="6e83d-103">在 Skype for Business Server 2015 中创建位置策略</span><span class="sxs-lookup"><span data-stu-id="6e83d-103">Create location policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e83d-104">阅读本主题可了解如何配置 Business Server 企业语音的增强型紧急服务 (E9-1-1) 在 Skype 的位置策略。</span><span class="sxs-lookup"><span data-stu-id="6e83d-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="6e83d-105">Skype 业务服务器使用位置策略 Skype 启用客户端注册期间业务客户端 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="6e83d-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="6e83d-106">位置策略包含定义 E9-1-1 实现方式的设置。</span><span class="sxs-lookup"><span data-stu-id="6e83d-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="6e83d-107">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 的位置策略](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6e83d-107">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>
  
<span data-ttu-id="6e83d-108">使用适用于业务 Control Panel Skype 或使用[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 定义位置策略。</span><span class="sxs-lookup"><span data-stu-id="6e83d-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e83d-109">Skype 业务服务器现在支持的客户端的多个紧急号码的配置。</span><span class="sxs-lookup"><span data-stu-id="6e83d-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="6e83d-110">如果您想要配置多个紧急号码，则必须按照中[规划中的业务服务器 2015 Skype 的多个紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)和[配置中的业务 2015 Skype 的多个紧急号码](configure-multiple-emergency-numbers.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="6e83d-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business 2015](configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="6e83d-p103">可以编辑全局位置策略，并创建新的带标记的位置策略。客户端所在的子网没有关联位置策略，或没有直接为客户端分配位置策略时，客户端会获取全局策略。向子网或用户分配带标记的策略。</span><span class="sxs-lookup"><span data-stu-id="6e83d-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 
  
<span data-ttu-id="6e83d-114">要创建位置策略，必须使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员的帐户，或者具有等效管理员权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="6e83d-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>
  
<span data-ttu-id="6e83d-115">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 的位置策略](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6e83d-115">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="6e83d-116">此过程中的 Cmdlet 使用通过下列值定义的位置策略。</span><span class="sxs-lookup"><span data-stu-id="6e83d-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="6e83d-117">Cmdlet 参数和值的完整说明，请参阅[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6e83d-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>
  
|<span data-ttu-id="6e83d-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="6e83d-118">**Element**</span></span>|<span data-ttu-id="6e83d-119">**值**</span><span class="sxs-lookup"><span data-stu-id="6e83d-119">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e83d-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="6e83d-120">EnhancedEmergencyServicesEnabled</span></span>  <br/> |<span data-ttu-id="6e83d-121">**True**</span><span class="sxs-lookup"><span data-stu-id="6e83d-121">**True**</span></span> <br/> |
|<span data-ttu-id="6e83d-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="6e83d-122">LocationRequired</span></span>  <br/> |<span data-ttu-id="6e83d-123">**免责声明**</span><span class="sxs-lookup"><span data-stu-id="6e83d-123">**Disclaimer**</span></span> <br/> |
|<span data-ttu-id="6e83d-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="6e83d-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> |<span data-ttu-id="6e83d-p105">您的公司策略要求您设置一个位置。如果不设置位置，紧急情况下，紧急服务将无法找到您。请设置一个位置。</span><span class="sxs-lookup"><span data-stu-id="6e83d-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
|<span data-ttu-id="6e83d-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="6e83d-128">UseLocationForE911Only</span></span>  <br/> |<span data-ttu-id="6e83d-129">**False**</span><span class="sxs-lookup"><span data-stu-id="6e83d-129">**False**</span></span> <br/> |
|<span data-ttu-id="6e83d-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="6e83d-130">PstnUsage</span></span>  <br/> |<span data-ttu-id="6e83d-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="6e83d-131">**EmergencyUsage**</span></span> <br/> |
|<span data-ttu-id="6e83d-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="6e83d-132">EmergencyDialString</span></span>  <br/> |<span data-ttu-id="6e83d-133">**911**</span><span class="sxs-lookup"><span data-stu-id="6e83d-133">**911**</span></span> <br/> |
|<span data-ttu-id="6e83d-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="6e83d-134">EmergencyDialMask</span></span>  <br/> |<span data-ttu-id="6e83d-135">**112**</span><span class="sxs-lookup"><span data-stu-id="6e83d-135">**112**</span></span> <br/> |
|<span data-ttu-id="6e83d-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="6e83d-136">NotificationUri</span></span>  <br/> |<span data-ttu-id="6e83d-137">**sip:security@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="6e83d-137">**sip:security@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="6e83d-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="6e83d-138">ConferenceUri</span></span>  <br/> |<span data-ttu-id="6e83d-139">**sip:+14255550123@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="6e83d-139">**sip:+14255550123@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="6e83d-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="6e83d-140">ConferenceMode</span></span>  <br/> |<span data-ttu-id="6e83d-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="6e83d-141">**twoway**</span></span> <br/> |
|<span data-ttu-id="6e83d-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="6e83d-142">LocationRefreshInterval</span></span>  <br/> |<span data-ttu-id="6e83d-143">**2**</span><span class="sxs-lookup"><span data-stu-id="6e83d-143">**2**</span></span> <br/> |
   
### <a name="to-create-location-policies"></a><span data-ttu-id="6e83d-144">创建位置策略</span><span class="sxs-lookup"><span data-stu-id="6e83d-144">To create location policies</span></span>

1. <span data-ttu-id="6e83d-145">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="6e83d-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e83d-146">如果 PstnUsages 的全局列表中还没有 **PstnUsage** 设置，则 CsLocationPolicy 会失败。</span><span class="sxs-lookup"><span data-stu-id="6e83d-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>
  
2. <span data-ttu-id="6e83d-147">也可以选择运行以下 cmdlet 编辑全局位置策略：</span><span class="sxs-lookup"><span data-stu-id="6e83d-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

   ```

3. <span data-ttu-id="6e83d-148">运行以下命令创建带标记的位置策略。</span><span class="sxs-lookup"><span data-stu-id="6e83d-148">Run the following to create a tagged Location Policy.</span></span>
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

   ```

4. <span data-ttu-id="6e83d-149">运行以下 cmdlet 将步骤 3 中创建的带标记的位置策略应用于用户策略。</span><span class="sxs-lookup"><span data-stu-id="6e83d-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```


