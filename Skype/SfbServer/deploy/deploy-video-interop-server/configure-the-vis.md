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
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>在 Skype for Business Server 中配置视频互操作服务器
 
**摘要：** 在 Skype for Business Server 中 (VIS) 角色配置视频互操作服务器。
  
 配置 VIS 将通过使用视频中继与视频中继Windows PowerShell。 安装 VIS 服务后，将创建具有全局范围的视频中继配置。 VIS 将此视频中继配置应用于没有更具体范围的视频中继配置的所有中继。 请注意，视频中继配置是适用于视频中继的设置集合。
  
## <a name="configure-video-trunk-and-dial-plan"></a>配置视频中继和拨号计划

使用以下 Windows PowerShell 命令指定要与 VIS 与所有视频网关之间的拓扑文档中定义的新定义的中继 () 关联的视频中继配置和拨号计划。 所有这些设置都可以在全局、站点或服务级别 (视频网关) 级别。 
  
每个 Skype for Business Server 部署创建一个具有全局范围的拨号计划。 VIS 将此拨号计划应用于没有更具体作用域的任何拨号计划的所有中继。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>使用自定义配置 WINDOWS POWERSHELL

1. 使用以下 Windows PowerShell cmdlet 创建新的视频中继配置 (vis 和 Cisco 统一通信管理器 (CallManager 或 CUCM) 之间的中继使用的设置) 集合：
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    如果存在需要修改的现有视频中继，请使用以下 Windows PowerShell cmdlet：
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    若要查看与特定视频中继配置关联的设置，请使用以下 Windows PowerShell cmdlet：
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    若要删除特定视频中继配置，请使用以下 Windows PowerShell cmdlet (请注意，如果没有针对特定中继中继的更具体的视频中继配置，将应用全局范围的视频中继) ：
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 使用以下 cmdlet 建立与中继关联的拨号Windows PowerShell cmdlet：
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

**需要 Remove-CsVoiceNormalizationRule** 命令来替代将干扰预期 VIS 和 CUCM 交互的默认规则。
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) 可用于删除拨号计划。
  
对于来自视频网关（其请求 URI 包含非 E.164 号码）的视频 SIP 中继呼叫，VIS 将读取与关联中继关联的拨号计划的名称，并将拨号计划名称包含在 VIS 发送到前端的邀请中请求 URI 的电话上下文部分。 然后，前端上的转换应用程序提取与拨号计划关联的规范化规则，然后将这些规则应用于请求 URI。
## <a name="trunk-configuration-options"></a>中继配置选项

前面Windows PowerShell Skype for Business Server 2015 中新增的视频中继配置的 cmdlet。 与视频中继配置关联的设置需要简要说明。
  
 **GatewaySendsRtcpForActiveCalls** 此参数确定是否将 RTCP 数据包从 VTC 发送到 VIS 进行活动呼叫。 此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。 如果 GatewaySendsRtcpForActiveCalls 设置为 True，VIS 可以在 30 秒后未收到 RTCP 数据包时终止呼叫。 默认值为 **True** 。
  
 **GatewaySendsRtcpForCallsOnHold** 此参数确定是否继续通过中继为已置于保留状态且预计任何媒体数据包不会在任一方向流动的呼叫发送 RTCP 数据包。 如果呼叫保持时没有 RTCP 数据包从 VTC 流向 VIS，VIS 可以终止呼叫。 默认值为 **True** 。 SIPTransport 协议设置为 TCP 时，将忽略此设置。
  
 **EnableMediaEncryptionForSipOverTls** 当 SIPTransport 协议设置为 TLS 时，此参数启用或禁用媒体的 SRTP。 默认值为 **True** 。 SIPTransport 协议设置为 TCP 时，将忽略此设置。
  
 **EnableSessionTimer** 此参数为与视频 SIP 中继关联的每个 SIP 对话框启用或禁用 VIS 端上的会话计时器。 默认值为 **False**。
  
 **ForwardErrorCorrectionType** 此参数用于确定是否对视频流 (FEC) 在视频互操作服务器和视频网关之间的通道上应用前向错误更正。 将 ForwardErrorCorrectionType 设置为"None"将关闭 VIS 和视频网关/VTC 之间的 FEC。 将 ForwardErrorCorrectionType 设置为"Cisco"可使 FEC 与 Cisco 的视频网关兼容，例如 Cisco 统一通信管理器 (CUCM) 。 默认值为 **"无"。**
  
## <a name="see-also"></a>另请参阅

[配置 CUCM 以与 Skype for Business Server 进行互操作](configure-cucm-for-interoperation.md)
