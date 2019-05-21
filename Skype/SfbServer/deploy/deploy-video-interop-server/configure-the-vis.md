---
title: 在 Skype for Business 服务器中配置视频互操作服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '摘要: 在 Skype for Business 服务器中配置视频互操作服务器 (VIS) 角色。'
ms.openlocfilehash: 3c0b211897afdde0fc0a01e255cdc14bc466f65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302740"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置视频互操作服务器
 
**摘要:** 在 Skype for Business 服务器中配置视频互操作服务器 (VIS) 角色。
  
 配置 VIS 将与使用 Windows PowerShell 的视频中继关联的设置。 安装 VIS 服务后，将创建全局范围的视频中继配置。 如果中继的视频中继配置不具有更加具体的范围，VIS 将对其应用此视频中继配置。 请注意，视频中继配置是一组适用于视频中继的设置。
  
## <a name="configure-video-trunk-and-dial-plan"></a>配置视频中继和拨号计划

使用以下 Windows PowerShell 命令指定要与在 VIS 和所有视频网关之间的拓扑结构中定义的新定义的主干相关联的视频中继配置和拨号计划。 可在全局、站点或服务（视频网关）级别设置这些设置。 
  
将为每个 Skype for business Server 部署创建一个具有全局作用域的拨号计划。 如果中继的拨号计划不具有更加具体的范围，VIS 将对其应用此拨号计划。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>使用 Windows PowerShell 配置 VIS

1. 使用以下 Windows PowerShell cmdlet 在 VIS 和 Cisco 统一通信管理器 (CallManager 或 CUCM) 之间的主干上创建新的视频中继配置 (设置的集合):
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    如果存在需要修改的现有视频主干, 请使用以下 Windows PowerShell cmdlet:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    若要查看与特定视频中继配置相关联的设置, 请使用以下 Windows PowerShell cmdlet:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    若要删除特定的视频中继配置, 请使用以下 Windows PowerShell cmdlet (请注意, 如果特定主干的视频中继配置更明确), 将应用全局范围的视频干线配置:
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 使用以下 Windows PowerShell cmdlet 建立与主干相关联的拨号计划:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

需要使用 **Remove-CsVoiceNormalizationRule** 命令来覆盖将干扰预期 VIS 和 CUCM 交互的默认规则。
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用于删除拨号计划。
  
对于来自视频网关的视频 SIP 中继呼叫, 其请求 URI 包含非 e. 164 个号码, VIS 将读取与关联主干相关联的拨号计划的名称, 并将拨号计划名称包含在邀请中的请求 URI 的电话上下文部分中, 这是 VIS 发送到前端。 然后前端的转换应用程序会提取与拨号计划关联的规范化规则并将其应用于请求 URI。
## <a name="trunk-configuration-options"></a>中继配置选项

以前提到的视频干线配置的 Windows PowerShell cmdlet 是 Skype for business Server 2015 的新增。 需要对与视频中继配置关联的设置进行简要说明。
  
 **GatewaySendsRtcpForActiveCalls**此参数确定是否将 RTCP 数据包从 VTC 发送到 VIS, 以进行活动呼叫。 此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。 如果 GatewaySendsRtcpForActiveCalls 设置为 True, 则 VIS 可以在超过30秒的时间段内收到 RTCP 数据包时终止呼叫。 默认值为**True**。
  
 **GatewaySendsRtcpForCallsOnHold**此参数确定 RTCP 数据包是否会继续在主干上发送, 以便呼叫已置于保持状态, 没有任何媒体数据包预期的方向。 如果通话处于暂停状态, 则 VIS 可以终止呼叫 (如果没有 RTCP 数据包从 VTC 流向 VIS。 默认值为**True**。 当 SIPTransport 协议设置为 TCP 时, 将忽略此设置。
  
 **EnableMediaEncryptionForSipOverTls**当 SIPTransport 协议设置为 TLS 时, 此参数启用或禁用媒体的 SRTP。 默认值为**True**。 当 SIPTransport 协议设置为 TCP 时, 将忽略此设置。
  
 **EnableSessionTimer**此参数为与视频 SIP 主干相关联的每个 SIP 对话框启用或禁用 VIS 端的会话计时器。 默认值为**False**。
  
 **ForwardErrorCorrectionType**此参数用于确定视频流的转发纠错 (FEC) 是否将应用于视频互操作服务器和视频网关之间的腿。 将 ForwardErrorCorrectionType 设置为 "None" 将关闭 VIS 和视频网关/VTC 之间的 FEC。 将 ForwardErrorCorrectionType 设置为 "Cisco" 可支持 Cisco 的 FEC 兼容视频网关, 如 Cisco 统一通信管理器 (CUCM)。 默认值为 "**无**"。
  
## <a name="see-also"></a>另请参阅

[为与 Skype for Business 服务器的互操作配置 CUCM](configure-cucm-for-interoperation.md)
