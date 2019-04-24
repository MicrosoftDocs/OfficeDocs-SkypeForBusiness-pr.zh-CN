---
title: 为业务 Server Skype 中配置视频互操作性服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要： 在 Skype for Business Server 配置视频互操作服务器 (VIS) 角色。
ms.openlocfilehash: 1cdc03fea116b5c41eaca13b4349ffc340dbc061
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219605"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>为业务 Server Skype 中配置视频互操作性服务器
 
**摘要：** 在 Skype for Business Server 配置视频互操作服务器 (VIS) 角色。
  
 配置 VIS 将将与使用 Windows PowerShell 的视频中继相关联的设置。 安装 VIS 服务后，将创建全局范围的视频中继配置。 如果中继的视频中继配置不具有更加具体的范围，VIS 将对其应用此视频中继配置。 请注意，视频中继配置是一组适用于视频中继的设置。
  
## <a name="configure-video-trunk-and-dial-plan"></a>配置视频中继和拨号计划

使用下面的 Windows PowerShell 命令，以指定的视频的中继配置和拨号计划要与新定义的 trunk(s) VIS 和视频的所有网关之间拓扑文档中定义关联。 可在全局、站点或服务（视频网关）级别设置这些设置。 
  
对于业务服务器部署每 Skype 创建具有全局作用域的拨号计划。 如果中继的拨号计划不具有更加具体的范围，VIS 将对其应用此拨号计划。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>配置使用 Windows PowerShell VIS

1. 创建新的视频的中继配置 （设置的集合） 用于 VIS 和 Cisco 统一通信管理器 （CallManager 或 CUCM） 之间的中继使用以下 Windows PowerShell cmdlet:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    如果没有需要修改现有视频中继，请使用以下 Windows PowerShell cmdlet:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    若要查看特定视频中继配置相关联的设置，请使用以下 Windows PowerShell cmdlet:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    若要删除的特定视频中继配置，请使用以下 Windows PowerShell cmdlet （请注意，是否没有更具体地说范围视频中继配置特定中继将应用全局作用域的视频中继配置）：
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 建立与中继，使用以下 Windows PowerShell cmdlet 相关联的拨号计划：
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

需要使用 **Remove-CsVoiceNormalizationRule** 命令来覆盖将干扰预期 VIS 和 CUCM 交互的默认规则。
> [!NOTE]
> [删除 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用于删除拨号计划。
  
从其请求 URI 包含非 E.164 号码视频网关视频 SIP 中继呼叫，VIS 将读取与关联的中继，相关联的拨号计划的名称，并将包括在邀请该 VI 请求 URI 的电话上下文部分中的拨号计划名称S 将发送到前端。 然后前端的转换应用程序会提取与拨号计划关联的规范化规则并将其应用于请求 URI。
## <a name="trunk-configuration-options"></a>中继配置选项

为前面提到的视频的中继配置的 Windows PowerShell cmdlet 已业务服务器 2015年的 Skype 的新增内容。 需要对与视频中继配置关联的设置进行简要说明。
  
 **GatewaySendsRtcpForActiveCalls**此参数确定是否 RTCP 数据包从发送 VTC 到 VIS 的活动呼叫。 此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。 如果 GatewaySendsRtcpForActiveCalls 设置为 True，则 VIS 可以终止呼叫，如果它不会收到超过 30 秒一段的 RTCP 数据包。 默认值为**True**。
  
 **GatewaySendsRtcpForCallsOnHold**此参数确定是否继续通过中继置于保持状态的呼叫发送的 RTCP 数据包和没有媒体数据包中，预计将流任一方向。 如果不有任何 RTCP 数据包从流 VTC 到 VIS 呼叫置于保持状态时，VIS 可以终止呼叫。 默认值为**True**。 当 SIPTransport 协议设置为 TCP 时，则将忽略此设置。
  
 **EnableMediaEncryptionForSipOverTls**此参数启用或禁用 SRTP 媒体 SIPTransport 协议设置为 TLS 时。 默认值为**True**。 当 SIPTransport 协议设置为 TCP 时，则将忽略此设置。
  
 **EnableSessionTimer**此参数启用或禁用会话计时器 VIS 侧的视频的 SIP 中继相关联的每个 SIP 对话。 默认值为**False**。
  
 **ForwardErrorCorrectionType**此参数用于确定是否要应用于视频互操作服务器和视频的网关之间的线路转接错误纠正 (FEC) 的视频流。 为"None"设置 ForwardErrorCorrectionType 关闭 FEC VIS 和视频网关/VTC 之间。 设置为"Cisco"ForwardErrorCorrectionType 使 FEC cisco，如 Cisco 统一通信管理器 (CUCM) 的视频网关与兼容。 默认值为**None**。
  
## <a name="see-also"></a>另请参阅

[为业务服务器与 Skype 的互操作配置 CUCM](configure-cucm-for-interoperation.md)
