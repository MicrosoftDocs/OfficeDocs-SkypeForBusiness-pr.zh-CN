---
title: 在 Skype for Business Server 中配置视频互操作服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要：在 Skype for Business Server (VIS) 角色配置视频互操作服务器。
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820692"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="44eba-103">在 Skype for Business Server 中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="44eba-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="44eba-104">**摘要：** 在 Skype for Business Server 中 (VIS) 角色配置视频互操作服务器。</span><span class="sxs-lookup"><span data-stu-id="44eba-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="44eba-105">配置 VIS 将通过使用视频中继与视频中继Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="44eba-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="44eba-106">安装 VIS 服务后，将创建具有全局范围的视频中继配置。</span><span class="sxs-lookup"><span data-stu-id="44eba-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="44eba-107">VIS 将此视频中继配置应用于没有更具体范围的视频中继配置的所有中继。</span><span class="sxs-lookup"><span data-stu-id="44eba-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="44eba-108">请注意，视频中继配置是适用于视频中继的设置集合。</span><span class="sxs-lookup"><span data-stu-id="44eba-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="44eba-109">配置视频中继和拨号计划</span><span class="sxs-lookup"><span data-stu-id="44eba-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="44eba-110">使用以下 Windows PowerShell 命令指定要与 VIS 与所有视频网关之间的拓扑文档中定义的新定义的中继 () 关联的视频中继配置和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="44eba-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="44eba-111">所有这些设置都可以在全局、站点或服务级别 (视频网关) 级别。</span><span class="sxs-lookup"><span data-stu-id="44eba-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="44eba-112">每个 Skype for Business Server 部署创建一个具有全局范围的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="44eba-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="44eba-113">VIS 将此拨号计划应用于没有更具体作用域的任何拨号计划的所有中继。</span><span class="sxs-lookup"><span data-stu-id="44eba-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="44eba-114">使用自定义配置 WINDOWS POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="44eba-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="44eba-115">使用以下 Windows PowerShell cmdlet 创建新的视频中继配置 (vis 和 Cisco 统一通信管理器 (CallManager 或 CUCM) 之间的中继使用的设置) 集合：</span><span class="sxs-lookup"><span data-stu-id="44eba-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="44eba-116">如果存在需要修改的现有视频中继，请使用以下 Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="44eba-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="44eba-117">若要查看与特定视频中继配置关联的设置，请使用以下 Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="44eba-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="44eba-118">若要删除特定视频中继配置，请使用以下 Windows PowerShell cmdlet (请注意，如果没有针对特定中继中继的更具体的视频中继配置，将应用全局范围的视频中继) ：</span><span class="sxs-lookup"><span data-stu-id="44eba-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="44eba-119">使用以下 cmdlet 建立与中继关联的拨号Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="44eba-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="44eba-120">**需要 Remove-CsVoiceNormalizationRule** 命令来替代将干扰预期 VIS 和 CUCM 交互的默认规则。</span><span class="sxs-lookup"><span data-stu-id="44eba-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="44eba-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) 可用于删除拨号计划。</span><span class="sxs-lookup"><span data-stu-id="44eba-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="44eba-122">对于来自视频网关（其请求 URI 包含非 E.164 号码）的视频 SIP 中继呼叫，VIS 将读取与关联中继关联的拨号计划的名称，并将拨号计划名称包含在 VIS 发送到前端的邀请中请求 URI 的电话上下文部分。</span><span class="sxs-lookup"><span data-stu-id="44eba-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="44eba-123">然后，前端上的转换应用程序提取与拨号计划关联的规范化规则，然后将这些规则应用于请求 URI。</span><span class="sxs-lookup"><span data-stu-id="44eba-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="44eba-124">中继配置选项</span><span class="sxs-lookup"><span data-stu-id="44eba-124">Trunk configuration options</span></span>

<span data-ttu-id="44eba-125">前面Windows PowerShell Skype for Business Server 2015 中新增的视频中继配置的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44eba-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="44eba-126">与视频中继配置关联的设置需要简要说明。</span><span class="sxs-lookup"><span data-stu-id="44eba-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="44eba-127">**GatewaySendsRtcpForActiveCalls** 此参数确定是否将 RTCP 数据包从 VTC 发送到 VIS 进行活动呼叫。</span><span class="sxs-lookup"><span data-stu-id="44eba-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="44eba-128">此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。</span><span class="sxs-lookup"><span data-stu-id="44eba-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="44eba-129">如果 GatewaySendsRtcpForActiveCalls 设置为 True，VIS 可以在 30 秒后未收到 RTCP 数据包时终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="44eba-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="44eba-130">默认值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="44eba-130">The default is **True**.</span></span>
  
 <span data-ttu-id="44eba-131">**GatewaySendsRtcpForCallsOnHold** 此参数确定是否继续通过中继为已置于保留状态且预计任何媒体数据包不会在任一方向流动的呼叫发送 RTCP 数据包。</span><span class="sxs-lookup"><span data-stu-id="44eba-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="44eba-132">如果呼叫保持时没有 RTCP 数据包从 VTC 流向 VIS，VIS 可以终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="44eba-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="44eba-133">默认值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="44eba-133">The default is **True**.</span></span> <span data-ttu-id="44eba-134">SIPTransport 协议设置为 TCP 时，将忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="44eba-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="44eba-135">**EnableMediaEncryptionForSipOverTls** 当 SIPTransport 协议设置为 TLS 时，此参数启用或禁用媒体的 SRTP。</span><span class="sxs-lookup"><span data-stu-id="44eba-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="44eba-136">默认值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="44eba-136">The default is **True**.</span></span> <span data-ttu-id="44eba-137">SIPTransport 协议设置为 TCP 时，将忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="44eba-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="44eba-138">**EnableSessionTimer** 此参数为与视频 SIP 中继关联的每个 SIP 对话框启用或禁用 VIS 端上的会话计时器。</span><span class="sxs-lookup"><span data-stu-id="44eba-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="44eba-139">默认值为 **False**。</span><span class="sxs-lookup"><span data-stu-id="44eba-139">The default is **False**.</span></span>
  
 <span data-ttu-id="44eba-140">**ForwardErrorCorrectionType** 此参数用于确定是否对视频流 (FEC) 在视频互操作服务器和视频网关之间的通道上应用前向错误更正。</span><span class="sxs-lookup"><span data-stu-id="44eba-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="44eba-141">将 ForwardErrorCorrectionType 设置为"None"将关闭 VIS 和视频网关/VTC 之间的 FEC。</span><span class="sxs-lookup"><span data-stu-id="44eba-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="44eba-142">将 ForwardErrorCorrectionType 设置为"Cisco"可使 FEC 与 Cisco 的视频网关兼容，例如 Cisco 统一通信管理器 (CUCM) 。</span><span class="sxs-lookup"><span data-stu-id="44eba-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="44eba-143">默认值为 **"无"。**</span><span class="sxs-lookup"><span data-stu-id="44eba-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44eba-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44eba-144">See also</span></span>

[<span data-ttu-id="44eba-145">配置 CUCM 以与 Skype for Business Server 进行互操作</span><span class="sxs-lookup"><span data-stu-id="44eba-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
