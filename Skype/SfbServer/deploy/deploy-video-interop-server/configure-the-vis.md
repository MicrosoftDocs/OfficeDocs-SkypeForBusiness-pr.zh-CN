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
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置视频互操作服务器
 
**摘要：**在 Skype 为业务服务器 2015年配置视频互操作服务器 (VIS) 角色。
  
 配置 VIS 将使用 Windows PowerShell 的视频中继与关联的设置。 安装 VIS 服务后，将创建全局范围的视频中继配置。 如果中继的视频中继配置不具有更加具体的范围，VIS 将对其应用此视频中继配置。 请注意，视频中继配置是一组适用于视频中继的设置。
  
## <a name="configure-video-trunk-and-dial-plan"></a>配置视频中继和拨号计划

使用下面的 Windows PowerShell 命令，指定视频中继配置和拨号计划要与新定义的 trunk(s) VIS 和所有视频网关之间拓扑文档中定义关联。 可在全局、站点或服务（视频网关）级别设置这些设置。 
  
每 Skype 业务服务器部署为创建具有全局作用域的拨号计划了。 如果中继的拨号计划不具有更加具体的范围，VIS 将对其应用此拨号计划。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>配置使用 Windows PowerShell VIS

1. 创建新的视频中继配置 （设置的集合） 使用 VIS 和 CUCM，使用下面的 Windows PowerShell cmdlet 之间干线上：
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    如果有需要修改现有视频中继，请使用下面的 Windows PowerShell cmdlet:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    若要查看与特定视频中继配置关联的设置，请使用下面的 Windows PowerShell cmdlet:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    若要移除特定视频中继配置，请使用下面的 Windows PowerShell cmdlet （请注意，是否没有特定的中继更加具体地指定了作用域的视频中继配置将应用全局作用域的视频中继配置）：
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 建立后备箱，使用下面的 Windows PowerShell cmdlet 相关联的拨号计划：
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

需要使用 **Remove-CsVoiceNormalizationRule** 命令来覆盖将干扰预期 VIS 和 CUCM 交互的默认规则。
> [!NOTE]
> [删除 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用于删除拨号计划。
  
从视频网关的请求 URI 包含非 E.164 号码视频 SIP 中继通话，VIS 将阅读名称相关联的后备箱，与关联的拨号计划，将包括在邀请该 VI 请求 URI 的电话上下文部分中的拨号计划名称S 将发送到前端。 然后前端的转换应用程序会提取与拨号计划关联的规范化规则并将其应用于请求 URI。
## <a name="trunk-configuration-options"></a>中继配置选项

对于前面提到的视频中继配置 Windows PowerShell cmdlet 是新手的业务服务器 2015 Skype。 需要对与视频中继配置关联的设置进行简要说明。
  
 **GatewaySendsRtcpForActiveCalls**此参数确定是否 RTCP 发送数据包从 VTC VIS 到活动调用。 此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。 如果 GatewaySendsRtcpForActiveCalls 设置为 True，VIS 可以终止呼叫，如果不能超过 30 秒期间接收 RTCP 包。 默认值为**True**。
  
 **GatewaySendsRtcpForCallsOnHold**此参数确定是否继续置于保留状态的电话干线通过发送 RTCP 数据包和任何媒体数据包会沿两个方向流动。 VIS 可以终止呼叫，如果流向从 VTC VIS 呼叫处于保持状态的同时没有 RTCP 包。 默认值为**True**。 当 SIPTransport 协议设置为 TCP 时，则忽略此设置。
  
 **EnableMediaEncryptionForSipOverTls**此参数启用或禁用 SRTP 介质设置到 TLS 的 SIPTransport 协议。 默认值为**True**。 当 SIPTransport 协议设置为 TCP 时，则忽略此设置。
  
 **EnableSessionTimer**此参数启用或禁用会话计时器 VIS 侧与视频的 SIP 中继的每个 SIP 对话。 默认值为**False**。
  
 **ForwardErrorCorrectionType**使用此参数来确定是否要应用于视频的互操作服务器和视频网关之间腿向前错误更正 (FEC) 的视频流。 将 ForwardErrorCorrectionType 设置为"无"时将关闭 FEC VIS 和视频网关/VTC 之间。 设置为"Cisco"ForwardErrorCorrectionType 使 FEC 通过 Cisco，例如 Cisco 统一通信管理器 (CUCM) 的视频网关与兼容。 默认值为**无**。
  
## <a name="see-also"></a>另请参阅

#### 

[将 CUCM 配置为与 Skype 业务服务器 2015年的互操作](configure-cucm-for-interoperation.md)

