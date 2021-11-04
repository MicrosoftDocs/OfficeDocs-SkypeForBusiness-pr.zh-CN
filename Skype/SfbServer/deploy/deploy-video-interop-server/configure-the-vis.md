---
title: 在服务器中配置视频互操作Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要：配置视频互操作服务器 (VIS) 角色Skype for Business Server。
ms.openlocfilehash: 61ab8f8b5c6538491de63696d9445672ce9211cf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741298"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>在服务器中配置视频互操作Skype for Business Server
 
**摘要：** 配置视频互操作服务器 (VIS) 角色Skype for Business Server。
  
 配置 VIS 将通过使用视频中继与视频中继Windows PowerShell。 安装 VIS 服务后，将创建具有全局范围的视频中继配置。 VIS 将此视频中继配置应用于没有更具体的范围的视频中继配置的所有中继。 请注意，视频中继配置是适用于视频中继的设置集合。
  
## <a name="configure-video-trunk-and-dial-plan"></a>配置视频中继和拨号计划

使用以下 Windows PowerShell 命令指定要与 VIS 与所有视频网关之间的拓扑文档中定义的新定义的中继 () 关联的视频中继配置和拨号计划。 所有这些设置都可以在全局、站点或服务级别 (网关) 设置。 
  
每个部署将创建一个全局范围的Skype for Business Server计划。 VIS 将应用此拨号计划给没有更具体的拨号计划的所有中继。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>使用配置 VIS Windows PowerShell

1. 使用以下 Windows PowerShell cmdlet 创建新的视频中继配置 (用于 VIS 和 Cisco 统一通信管理器 (CallManager 或 CUCM) 之间的中继的设置) 集合：
    
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

    若要删除特定视频中继配置，请使用以下 Windows PowerShell cmdlet (请注意，如果特定中继服务器没有更具体的视频中继配置，将应用全局范围的视频中继) ：
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 使用下列 cmdlet 建立与中继关联的Windows PowerShell计划：
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

需要 **Remove-CsVoiceNormalizationRule** 命令来替代将干扰预期 VIS 和 CUCM 交互的默认规则。
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) 可用于删除拨号计划。
  
对于来自视频网关（其请求 URI 包含非 E.164 号码）的视频 SIP 中继呼叫，VIS 将读取与关联中继关联的拨号计划的名称，并将在 VIS 发送到前端的邀请中的请求 URI 的电话上下文部分包含拨号计划名称。 然后，前端上的转换应用程序提取与拨号计划关联的规范化规则，然后将这些规则应用于请求 URI。
## <a name="trunk-configuration-options"></a>中继配置选项

前面Windows PowerShell的视频中继配置的 cmdlet 是 2015 Skype for Business Server新增的。 与视频中继配置关联的设置需要简要说明。
  
 **GatewaySendsRtcpForActiveCalls** 此参数确定是否将 RTCP 数据包从 VTC 发送到 VIS 进行活动呼叫。 此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。 如果 GatewaySendsRtcpForActiveCalls 设置为 True，VIS 可以在 30 秒后未收到 RTCP 数据包时终止呼叫。 默认值为 **True** 。
  
 **GatewaySendsRtcpForCallsOnHold** 此参数确定是否继续通过中继发送 RTCP 数据包，以接收已置于呼叫等待状态且预期没有媒体数据包在任一方向上流动的呼叫。 如果呼叫保持时没有 RTCP 数据包从 VTC 流向 VIS，VIS 可以终止呼叫。 默认值为 **True** 。 SIPTransport 协议设置为 TCP 时，将忽略此设置。
  
 **EnableMediaEncryptionForSipOverTls** 当 SIPTransport 协议设置为 TLS 时，此参数启用或禁用媒体的 SRTP。 默认值为 **True** 。 SIPTransport 协议设置为 TCP 时，将忽略此设置。
  
 **EnableSessionTimer** 此参数为与视频 SIP 中继关联的每个 SIP 对话框启用或禁用 VIS 端上的会话计时器。 默认值为 **False**。
  
 **ForwardErrorCorrectionType** 此参数用于确定在视频互操作服务器和视频网关 (对视频流应用FEC) 前向错误更正。 将 ForwardErrorCorrectionType 设置为"None"将关闭 VIS 和视频网关/VTC 之间的 FEC。 将 ForwardErrorCorrectionType 设置为"Cisco"可使 FEC 与 Cisco 的视频网关兼容，例如 Cisco 统一通信管理器 (CUCM) 。 默认值为 **None**。
  
## <a name="see-also"></a>另请参阅

[配置 CUCM 以与 Skype for Business Server](configure-cucm-for-interoperation.md)