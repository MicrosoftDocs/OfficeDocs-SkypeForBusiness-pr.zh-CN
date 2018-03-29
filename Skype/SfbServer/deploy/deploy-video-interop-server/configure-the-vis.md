---
title: 在 Skype for Business Server 2015 中配置视频互操作服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要： 在 Skype 为业务服务器 2015年配置视频互操作服务器 (VIS) 角色。
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="da867-103">在 Skype for Business Server 2015 中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="da867-103">Configure the Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="da867-104">**摘要：**在 Skype 为业务服务器 2015年配置视频互操作服务器 (VIS) 角色。</span><span class="sxs-lookup"><span data-stu-id="da867-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="da867-105">配置 VIS 将使用 Windows PowerShell 的视频中继与关联的设置。</span><span class="sxs-lookup"><span data-stu-id="da867-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="da867-106">安装 VIS 服务后，将创建全局范围的视频中继配置。</span><span class="sxs-lookup"><span data-stu-id="da867-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="da867-107">如果中继的视频中继配置不具有更加具体的范围，VIS 将对其应用此视频中继配置。</span><span class="sxs-lookup"><span data-stu-id="da867-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="da867-108">请注意，视频中继配置是一组适用于视频中继的设置。</span><span class="sxs-lookup"><span data-stu-id="da867-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="da867-109">配置视频中继和拨号计划</span><span class="sxs-lookup"><span data-stu-id="da867-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="da867-110">使用下面的 Windows PowerShell 命令，指定视频中继配置和拨号计划要与新定义的 trunk(s) VIS 和所有视频网关之间拓扑文档中定义关联。</span><span class="sxs-lookup"><span data-stu-id="da867-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="da867-111">可在全局、站点或服务（视频网关）级别设置这些设置。</span><span class="sxs-lookup"><span data-stu-id="da867-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="da867-112">每 Skype 业务服务器部署为创建具有全局作用域的拨号计划了。</span><span class="sxs-lookup"><span data-stu-id="da867-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="da867-113">如果中继的拨号计划不具有更加具体的范围，VIS 将对其应用此拨号计划。</span><span class="sxs-lookup"><span data-stu-id="da867-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="da867-114">配置使用 Windows PowerShell VIS</span><span class="sxs-lookup"><span data-stu-id="da867-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="da867-115">创建新的视频中继配置 （设置的集合） 使用 VIS 和 CUCM，使用下面的 Windows PowerShell cmdlet 之间干线上：</span><span class="sxs-lookup"><span data-stu-id="da867-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and CUCM, using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="da867-116">如果有需要修改现有视频中继，请使用下面的 Windows PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da867-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="da867-117">若要查看与特定视频中继配置关联的设置，请使用下面的 Windows PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da867-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="da867-118">若要移除特定视频中继配置，请使用下面的 Windows PowerShell cmdlet （请注意，是否没有特定的中继更加具体地指定了作用域的视频中继配置将应用全局作用域的视频中继配置）：</span><span class="sxs-lookup"><span data-stu-id="da867-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="da867-119">建立后备箱，使用下面的 Windows PowerShell cmdlet 相关联的拨号计划：</span><span class="sxs-lookup"><span data-stu-id="da867-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="da867-120">需要使用 **Remove-CsVoiceNormalizationRule** 命令来覆盖将干扰预期 VIS 和 CUCM 交互的默认规则。</span><span class="sxs-lookup"><span data-stu-id="da867-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="da867-121">[删除 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用于删除拨号计划。</span><span class="sxs-lookup"><span data-stu-id="da867-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="da867-122">从视频网关的请求 URI 包含非 E.164 号码视频 SIP 中继通话，VIS 将阅读名称相关联的后备箱，与关联的拨号计划，将包括在邀请该 VI 请求 URI 的电话上下文部分中的拨号计划名称S 将发送到前端。</span><span class="sxs-lookup"><span data-stu-id="da867-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="da867-123">然后前端的转换应用程序会提取与拨号计划关联的规范化规则并将其应用于请求 URI。</span><span class="sxs-lookup"><span data-stu-id="da867-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="da867-124">中继配置选项</span><span class="sxs-lookup"><span data-stu-id="da867-124">Trunk configuration options</span></span>

<span data-ttu-id="da867-125">对于前面提到的视频中继配置 Windows PowerShell cmdlet 是新手的业务服务器 2015 Skype。</span><span class="sxs-lookup"><span data-stu-id="da867-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously are new to the Skype for Business Server 2015.</span></span> <span data-ttu-id="da867-126">需要对与视频中继配置关联的设置进行简要说明。</span><span class="sxs-lookup"><span data-stu-id="da867-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="da867-127">**GatewaySendsRtcpForActiveCalls**此参数确定是否 RTCP 发送数据包从 VTC VIS 到活动调用。</span><span class="sxs-lookup"><span data-stu-id="da867-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="da867-128">此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。</span><span class="sxs-lookup"><span data-stu-id="da867-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="da867-129">如果 GatewaySendsRtcpForActiveCalls 设置为 True，VIS 可以终止呼叫，如果不能超过 30 秒期间接收 RTCP 包。</span><span class="sxs-lookup"><span data-stu-id="da867-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="da867-130">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="da867-130">The default is **True**.</span></span>
  
 <span data-ttu-id="da867-131">**GatewaySendsRtcpForCallsOnHold**此参数确定是否继续置于保留状态的电话干线通过发送 RTCP 数据包和任何媒体数据包会沿两个方向流动。</span><span class="sxs-lookup"><span data-stu-id="da867-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="da867-132">VIS 可以终止呼叫，如果流向从 VTC VIS 呼叫处于保持状态的同时没有 RTCP 包。</span><span class="sxs-lookup"><span data-stu-id="da867-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="da867-133">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="da867-133">The default is **True**.</span></span> <span data-ttu-id="da867-134">当 SIPTransport 协议设置为 TCP 时，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="da867-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="da867-135">**EnableMediaEncryptionForSipOverTls**此参数启用或禁用 SRTP 介质设置到 TLS 的 SIPTransport 协议。</span><span class="sxs-lookup"><span data-stu-id="da867-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="da867-136">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="da867-136">The default is **True**.</span></span> <span data-ttu-id="da867-137">当 SIPTransport 协议设置为 TCP 时，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="da867-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="da867-138">**EnableSessionTimer**此参数启用或禁用会话计时器 VIS 侧与视频的 SIP 中继的每个 SIP 对话。</span><span class="sxs-lookup"><span data-stu-id="da867-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="da867-139">默认值为**False**。</span><span class="sxs-lookup"><span data-stu-id="da867-139">The default is **False**.</span></span>
  
 <span data-ttu-id="da867-140">**ForwardErrorCorrectionType**使用此参数来确定是否要应用于视频的互操作服务器和视频网关之间腿向前错误更正 (FEC) 的视频流。</span><span class="sxs-lookup"><span data-stu-id="da867-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="da867-141">将 ForwardErrorCorrectionType 设置为"无"时将关闭 FEC VIS 和视频网关/VTC 之间。</span><span class="sxs-lookup"><span data-stu-id="da867-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="da867-142">设置为"Cisco"ForwardErrorCorrectionType 使 FEC 通过 Cisco，例如 Cisco 统一通信管理器 (CUCM) 的视频网关与兼容。</span><span class="sxs-lookup"><span data-stu-id="da867-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="da867-143">默认值为**无**。</span><span class="sxs-lookup"><span data-stu-id="da867-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da867-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da867-144">See also</span></span>

#### 

[<span data-ttu-id="da867-145">将 CUCM 配置为与 Skype 业务服务器 2015年的互操作</span><span class="sxs-lookup"><span data-stu-id="da867-145">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)

