---
title: 在呼叫中配置 E9-1-1 语音Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在语音通道中配置 E9-1-1 Skype for Business Server 企业语音。
ms.openlocfilehash: efab6698aef0c212bb6a52f6f50e2b2bbbe47141
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605581"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>在呼叫中配置 E9-1-1 语音Skype for Business Server
 
在语音通道中配置 E9-1-1 Skype for Business Server 企业语音。 
  
若要部署 E9-1-1，首先需配置紧急呼叫语音路由。 有关创建语音路由的详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。 例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。 
  
> [!NOTE]
> 若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。 为此，请在 **Set-CsTrunkConfiguration** cmdlet 上将 EnablePIDFLOSupport 标志设置为 True。 EnablePIDFLOSupport 的默认值为 False。 例如：不需要为回退公用电话交换网 (PSTN) 网关和 ELIN) 网关启用紧急位置标识号 (接收位置。 `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.`
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>配置 E9-1-1 语音路由

1. 使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。
    
2.  启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 运行以下 cmdlet 以创建新的 PSTN 用法记录。 
    
    该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。 尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。 有关详细信息，请参阅 Configure [voice policies， PSTN usage records， and voice routes in Skype for Business](voice-and-pstn.md)。
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。
    
    该号码模式必须与位置策略中的“紧急拨号字符串”设置中使用的号码模式相同。 需要"+"符号，Skype for Business紧急呼叫添加"+"。 “Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。 以下示例将“EmergencyRoute”用作语音路由的名称。
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 或者，对于 SIP 中继连接，建议您运行以下 cmdlet，为 E9-1-1 服务提供商的 SIP 中继未处理的呼叫创建本地路由。 如果 E9-1-1 服务提供商的连接不可用，则使用此路由。 
    
    以下示例假定用户的语音策略中具有“本地”用法。
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


