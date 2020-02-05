---
title: 在 Skype for Business 服务器中创建位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 阅读本主题，了解如何在 Skype for Business Server Enterprise Voice 中配置增强的紧急服务（E9-1）位置策略。
ms.openlocfilehash: d06e22850b1556e4c7d9143b49176aff23bb6640
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767935"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="f5ada-103">在 Skype for Business 服务器中创建位置策略</span><span class="sxs-lookup"><span data-stu-id="f5ada-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="f5ada-104">阅读本主题，了解如何在 Skype for Business Server Enterprise Voice 中配置增强的紧急服务（E9-1）位置策略。</span><span class="sxs-lookup"><span data-stu-id="f5ada-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="f5ada-105">在客户端注册期间，Skype for business 服务器使用位置策略为 E9 启用 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="f5ada-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="f5ada-106">位置策略包含定义 E9-1-1 实现方式的设置。</span><span class="sxs-lookup"><span data-stu-id="f5ada-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="f5ada-107">有关详细信息，请参阅为[Skype For Business 服务器计划位置策略](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ada-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="f5ada-108">通过使用 Skype for Business 控制面板或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 定义位置策略。</span><span class="sxs-lookup"><span data-stu-id="f5ada-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f5ada-109">Skype for business 服务器现支持客户端的多个紧急号码的配置。</span><span class="sxs-lookup"><span data-stu-id="f5ada-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="f5ada-110">如果想要配置多个紧急号码，您必须按照计划中的信息，在[skype For Business 服务器中输入多个紧急](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)号码，并[在 skype For business 中配置多个紧急号码](configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ada-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="f5ada-p103">可以编辑全局位置策略，并创建新的带标记的位置策略。客户端所在的子网没有关联位置策略，或没有直接为客户端分配位置策略时，客户端会获取全局策略。向子网或用户分配带标记的策略。</span><span class="sxs-lookup"><span data-stu-id="f5ada-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="f5ada-114">要创建位置策略，必须使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员的帐户，或者具有等效管理员权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="f5ada-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="f5ada-115">有关详细信息，请参阅为[Skype For Business 服务器计划位置策略](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ada-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="f5ada-116">此过程中的 Cmdlet 使用通过下列值定义的位置策略。</span><span class="sxs-lookup"><span data-stu-id="f5ada-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="f5ada-117">有关 cmdlet 参数和值的完整说明，请参阅[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f5ada-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="f5ada-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="f5ada-118">**Element**</span></span>                               | <span data-ttu-id="f5ada-119">**Value**</span><span class="sxs-lookup"><span data-stu-id="f5ada-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f5ada-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="f5ada-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="f5ada-121">**True**</span><span class="sxs-lookup"><span data-stu-id="f5ada-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="f5ada-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="f5ada-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="f5ada-123">**免责声明**</span><span class="sxs-lookup"><span data-stu-id="f5ada-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="f5ada-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="f5ada-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="f5ada-p105">您的公司策略要求您设置一个位置。如果不设置位置，紧急情况下，紧急服务将无法找到您。请设置一个位置。</span><span class="sxs-lookup"><span data-stu-id="f5ada-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="f5ada-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="f5ada-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="f5ada-129">**False**</span><span class="sxs-lookup"><span data-stu-id="f5ada-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="f5ada-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="f5ada-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="f5ada-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="f5ada-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="f5ada-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="f5ada-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="f5ada-133">**911**</span><span class="sxs-lookup"><span data-stu-id="f5ada-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="f5ada-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="f5ada-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="f5ada-135">**112**</span><span class="sxs-lookup"><span data-stu-id="f5ada-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="f5ada-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="f5ada-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="f5ada-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="f5ada-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="f5ada-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="f5ada-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="f5ada-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="f5ada-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="f5ada-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="f5ada-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="f5ada-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="f5ada-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="f5ada-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="f5ada-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="f5ada-143">**2**</span><span class="sxs-lookup"><span data-stu-id="f5ada-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="f5ada-144">创建位置策略</span><span class="sxs-lookup"><span data-stu-id="f5ada-144">To create location policies</span></span>

1. <span data-ttu-id="f5ada-145">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5ada-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5ada-146">如果 PstnUsages 的全局列表中还没有 **PstnUsage** 设置，则 CsLocationPolicy 会失败。</span><span class="sxs-lookup"><span data-stu-id="f5ada-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="f5ada-147">也可以选择运行以下 cmdlet 编辑全局位置策略：</span><span class="sxs-lookup"><span data-stu-id="f5ada-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="f5ada-148">运行以下命令创建带标记的位置策略。</span><span class="sxs-lookup"><span data-stu-id="f5ada-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="f5ada-149">运行以下 cmdlet 将步骤 3 中创建的带标记的位置策略应用于用户策略。</span><span class="sxs-lookup"><span data-stu-id="f5ada-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
