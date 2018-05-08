---
title: 在 Skype for Business Server 2015 中配置 E9-1-1 语音路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在 Skype for Business Server 企业语音配置 E9-1-1 语音路由。
ms.openlocfilehash: c31ac7c264fb931c127375eca5a383d10998c3f1
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置 E9-1-1 语音路由
 
在 Skype for Business Server 企业语音配置 E9-1-1 语音路由。 
  
若要部署 E9-1-1，首先需配置紧急呼叫语音路由。 有关创建语音路由的详细信息，请参阅[创建或修改语音路由中的业务 2015 Skype](create-or-modify-a-voice-route.md)。 例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。 
  
> [!NOTE]
> 若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。 若要执行此操作，请对**Set-cstrunkconfiguration** cmdlet 为 True 设置 EnablePIDFLOSupport 标志。 EnablePIDFLOSupport 的默认值为 False。 例如： `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` ，无需为回退公共交换电话交换网 (PSTN) 网关和紧急位置识别号码 (ELIN) 网关启用接收位置。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>配置 E9-1-1 语音路由

1. 使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。
    
2.  启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 运行以下 cmdlet 以创建新的 PSTN 用法记录。 
    
    该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。 尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。 有关详细信息，请参阅[配置语音策略、 PSTN 用法记录和中的业务 2015 Skype 的语音路由](voice-and-pstn.md)。
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。
    
    该号码模式必须与位置策略中的“紧急拨号字符串”**** 设置中使用的号码模式相同。 "+"登录所需因为 for Business 的 Skype 添加"+"紧急呼叫。 “Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。 以下示例将“EmergencyRoute”用作语音路由的名称。
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

   ```

5. （可选） 对于 SIP 中继连接，我们建议您运行以下 cmdlet 以创建本地路由的 E9-1-1 服务提供商的 SIP 中继不会处理的呼叫。 如果 E9-1-1 服务提供商的连接不可用，则使用此路由。 
    
    以下示例假定用户的语音策略中具有“本地”用法。
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


