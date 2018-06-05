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
description: 摘要： 在 Skype for Business Server 2015 配置视频互操作服务器 (VIS) 角色。
ms.openlocfilehash: 783900004d4f3ed9b060e7f237a62dfc5cf124f1
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501929"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="71615-103">在 Skype for Business Server 2015 中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="71615-103">Configure the Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="71615-104">**摘要：** 为业务服务器 2015 Skype 中配置视频互操作服务器 (VIS) 角色。</span><span class="sxs-lookup"><span data-stu-id="71615-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="71615-105">配置 VIS 将将与使用 Windows PowerShell 的视频中继相关联的设置。</span><span class="sxs-lookup"><span data-stu-id="71615-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="71615-106">安装 VIS 服务后，将创建全局范围的视频中继配置。</span><span class="sxs-lookup"><span data-stu-id="71615-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="71615-107">如果中继的视频中继配置不具有更加具体的范围，VIS 将对其应用此视频中继配置。</span><span class="sxs-lookup"><span data-stu-id="71615-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="71615-108">请注意，视频中继配置是一组适用于视频中继的设置。</span><span class="sxs-lookup"><span data-stu-id="71615-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="71615-109">配置视频中继和拨号计划</span><span class="sxs-lookup"><span data-stu-id="71615-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="71615-110">使用下面的 Windows PowerShell 命令，以指定的视频的中继配置和拨号计划要与新定义的 trunk(s) VIS 和视频的所有网关之间拓扑文档中定义关联。</span><span class="sxs-lookup"><span data-stu-id="71615-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="71615-111">可在全局、站点或服务（视频网关）级别设置这些设置。</span><span class="sxs-lookup"><span data-stu-id="71615-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="71615-112">对于业务服务器部署每 Skype 创建具有全局作用域的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="71615-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="71615-113">如果中继的拨号计划不具有更加具体的范围，VIS 将对其应用此拨号计划。</span><span class="sxs-lookup"><span data-stu-id="71615-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="71615-114">配置使用 Windows PowerShell VIS</span><span class="sxs-lookup"><span data-stu-id="71615-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="71615-115">创建新的视频的中继配置 （设置的集合） 用于 VIS 和 CUCM，使用以下 Windows PowerShell cmdlet 之间中继：</span><span class="sxs-lookup"><span data-stu-id="71615-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and CUCM, using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="71615-116">如果没有需要修改现有视频中继，请使用以下 Windows PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="71615-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="71615-117">若要查看特定视频中继配置相关联的设置，请使用以下 Windows PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="71615-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="71615-118">若要删除的特定视频中继配置，请使用以下 Windows PowerShell cmdlet （请注意，是否没有更具体地说范围视频中继配置特定中继将应用全局作用域的视频中继配置）：</span><span class="sxs-lookup"><span data-stu-id="71615-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="71615-119">建立与中继，使用以下 Windows PowerShell cmdlet 相关联的拨号计划：</span><span class="sxs-lookup"><span data-stu-id="71615-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="71615-120">需要使用 **Remove-CsVoiceNormalizationRule** 命令来覆盖将干扰预期 VIS 和 CUCM 交互的默认规则。</span><span class="sxs-lookup"><span data-stu-id="71615-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="71615-121">[删除 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用于删除拨号计划。</span><span class="sxs-lookup"><span data-stu-id="71615-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="71615-122">从其请求 URI 包含非 E.164 号码视频网关视频 SIP 中继呼叫，VIS 将读取与关联的中继，相关联的拨号计划的名称，并将包括在邀请该 VI 请求 URI 的电话上下文部分中的拨号计划名称S 将发送到前端。</span><span class="sxs-lookup"><span data-stu-id="71615-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="71615-123">然后前端的转换应用程序会提取与拨号计划关联的规范化规则并将其应用于请求 URI。</span><span class="sxs-lookup"><span data-stu-id="71615-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="71615-124">中继配置选项</span><span class="sxs-lookup"><span data-stu-id="71615-124">Trunk configuration options</span></span>

<span data-ttu-id="71615-125">为前面提到的视频的中继配置的 Windows PowerShell cmdlet 的业务服务器 2015 Skype 过。</span><span class="sxs-lookup"><span data-stu-id="71615-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously are new to the Skype for Business Server 2015.</span></span> <span data-ttu-id="71615-126">需要对与视频中继配置关联的设置进行简要说明。</span><span class="sxs-lookup"><span data-stu-id="71615-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="71615-127">**GatewaySendsRtcpForActiveCalls**此参数确定是否 RTCP 数据包从发送 VTC 到 VIS 的活动呼叫。</span><span class="sxs-lookup"><span data-stu-id="71615-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="71615-128">此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。</span><span class="sxs-lookup"><span data-stu-id="71615-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="71615-129">如果 GatewaySendsRtcpForActiveCalls 设置为 True，则 VIS 可以终止呼叫，如果它不会收到超过 30 秒一段的 RTCP 数据包。</span><span class="sxs-lookup"><span data-stu-id="71615-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="71615-130">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="71615-130">The default is **True**.</span></span>
  
 <span data-ttu-id="71615-131">**GatewaySendsRtcpForCallsOnHold**此参数确定是否继续通过中继置于保持状态的呼叫发送的 RTCP 数据包和没有媒体数据包中，预计将流任一方向。</span><span class="sxs-lookup"><span data-stu-id="71615-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="71615-132">如果不有任何 RTCP 数据包从流 VTC 到 VIS 呼叫置于保持状态时，VIS 可以终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="71615-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="71615-133">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="71615-133">The default is **True**.</span></span> <span data-ttu-id="71615-134">当 SIPTransport 协议设置为 TCP 时，则将忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="71615-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="71615-135">**EnableMediaEncryptionForSipOverTls**此参数启用或禁用 SRTP 媒体 SIPTransport 协议设置为 TLS 时。</span><span class="sxs-lookup"><span data-stu-id="71615-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="71615-136">默认值为**True**。</span><span class="sxs-lookup"><span data-stu-id="71615-136">The default is **True**.</span></span> <span data-ttu-id="71615-137">当 SIPTransport 协议设置为 TCP 时，则将忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="71615-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="71615-138">**EnableSessionTimer**此参数启用或禁用会话计时器 VIS 侧的视频的 SIP 中继相关联的每个 SIP 对话。</span><span class="sxs-lookup"><span data-stu-id="71615-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="71615-139">默认值为**False**。</span><span class="sxs-lookup"><span data-stu-id="71615-139">The default is **False**.</span></span>
  
 <span data-ttu-id="71615-140">**ForwardErrorCorrectionType**此参数用于确定是否要应用于视频互操作服务器和视频的网关之间的线路转接错误纠正 (FEC) 的视频流。</span><span class="sxs-lookup"><span data-stu-id="71615-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="71615-141">为"None"设置 ForwardErrorCorrectionType 关闭 FEC VIS 和视频网关/VTC 之间。</span><span class="sxs-lookup"><span data-stu-id="71615-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="71615-142">设置为"Cisco"ForwardErrorCorrectionType 使 FEC cisco，如 Cisco 统一通信管理器 (CUCM) 的视频网关与兼容。</span><span class="sxs-lookup"><span data-stu-id="71615-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="71615-143">默认值为**None**。</span><span class="sxs-lookup"><span data-stu-id="71615-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71615-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71615-144">See also</span></span>

[<span data-ttu-id="71615-145">为业务服务器 2015年与 Skype 的互操作配置 CUCM</span><span class="sxs-lookup"><span data-stu-id="71615-145">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)