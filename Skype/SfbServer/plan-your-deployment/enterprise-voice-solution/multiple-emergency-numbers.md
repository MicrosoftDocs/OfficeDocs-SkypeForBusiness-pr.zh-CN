---
title: 规划业务服务器 Skype 中的多个紧急号码
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 阅读本主题可了解如何规划业务 Server Skype 中的多个紧急号码。
ms.openlocfilehash: e3ecbc039dac510a1ebc5eb989773c1f32c3b6ac
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214157"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>规划业务服务器 Skype 中的多个紧急号码
 
阅读本主题可了解如何规划业务 Server Skype 中的多个紧急号码。
  
Skype 业务服务器现在支持的客户端的多个紧急号码的配置。 多个紧急号码是年 6 月 2016年中引入的新功能累积更新。 虽然美国只有一个紧急号码，即 911，但很多国家支持多个紧急号码。 英国，例如，支持 999，特定发往 United Kingdom，紧急号码和 112，欧盟的紧急号码。 
  
此功能对美国境内希望为多代码蓝色紧急号码提供漫游支持的医疗保健提供商也很有用。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多个紧急号码和位置策略

您配置的创建的位置策略定义如何紧急呼叫将实现紧急呼叫。 位置策略用于定义哪个号码构成紧急呼叫 — 例如，美国; 911999 和英国 112。 位置策略确定是否为用户启用用于紧急呼叫，如果是这样的行为的紧急呼叫的是。 您还可以定义是否应自动收到公司安全，并且应如何路由呼叫。
  
有关定义和修改位置策略的详细信息，请参阅[Plan for Business Server Skype 的位置策略](location-policies.md)和[Skype 业务服务器中的创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。 这些主题描述了位置策略; 有关的概念但是，您必须按照中[配置多个紧急号码 Skype for Business 中](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)的说明配置多个紧急号码。
  
规划多个紧急号码时，请牢记以下要求：
  
- 与年 6 月 2016年累积更新，您可以定义为给定的位置策略的最多 5 紧急号码。 用 11 月 2016年累积更新，此号码将增加到 100。
    
    > [!NOTE]
    > 如果您具有尚未升级到年 11 月 2016年累积更新，请参阅[业务服务器 2015年的 Skype 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 为每个紧急号码，您可以指定零个或多个紧急拨号掩码，都是唯一到给定的位置策略。
    
    拨号掩码是指：在拨打该号码时，希望将其转换为紧急拨号号码的值。 例如，假设在此字段输入值 212，而紧急拨号号码字段的值为 911。 当用户拨打 212 时，号码将转换为 911。 这样的备用紧急号码拨打和仍具有获得紧急服务呼叫 (例如，如果某人的国家或地区包含不同紧急号码尝试拨号国家或地区的号码而不是从的编号国家或地区他们当前正在）。 可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 拨号掩码字符串上限是 100 个字符。 每个字符都必须为 0 到 9 的数字。
    
- 每个位置策略都具有一个公用电话交换网 (PSTN) 用法，用于确定路由使用此策略的客户端拨出的紧急呼叫所使用的语音路由。每个紧急号码可以拥有唯一的路由。
    
- 如果某个位置策略同时定义了 EmergencyNumbers 和 DialString 参数，并且客户端支持多个紧急号码，则紧急号码优先。 如果客户端不支持多个紧急号码，则使用紧急拨号串。
    
- 有关商业和 Lync 的 Skype 客户端支持接收多个紧急号码、 拨号掩码和公用电话交换网 (pstn) 用法的信息，请参阅[支持的客户端](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 不能使用 Skype 业务控制面板配置多个紧急号码。 必须使用 PowerShell 来配置多个紧急号码。 
  
配置多个紧急号码之前，请牢记以下要求：
  
- 若要配置多个紧急号码，您必须使用新建 CsEmergencyNumber cmdlet，并必须定义通过 EmergencyNumbers 参数指定与[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)支持多个紧急号码的位置策略和[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet。
    
- 	如果你拥有使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 定义的号码，EmergencyNumbers 参数指定的值的优先级高于旧值。即，EmergencyDialString 和 EmergencyDialMask 参数的值将被忽略。
    
- 如果必须使用 EmergencyDialString 和 EmergencyDialMask 参数，*并不配置新的紧急号码*，请使用集 CsLocationPolicy 或 New-cslocationpolicy cmdlet 定义的现有号码的现有号码将继续使用。
    
- 要使多个紧急号码功能起作用，你所运行的客户端版本必须支持新功能。 旧客户端将继续使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 指定的旧值。 
    
- 如果用户将拨打匹配拨号串的号码，则无需拨号掩码。 例如，如果用户拨打的号码是 911，则拨号串是 911，且无需掩码。 
    
有关配置多个紧急号码的详细信息，请参阅[Skype for Business 中的多个紧急号码的配置](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表显示了位置策略示例（用于举例说明，并未显示所有属性）：
  

|**位置策略名称**|**是否启用 E911**|**紧急拨号串**|**拨号掩码**|**紧急号码**|**PSTN 用法**|**所需位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国  <br/> |是  <br/> |911  
  <br/> | 112;999 <br/> ||USEmergency  <br/> |是  <br/> |
|US-Hospital  <br/> |是  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|伦敦  <br/> |是  <br/> |999  
  <br/> |144  <br/> |999 144  <br/> 112 911; 117; 118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100 911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美国**— 不要求使用多个紧急号码。 在美国，您将使用的旧的紧急拨号串和拨号掩码配置。
  
 **美国医院**— 要求无法屏蔽"450"。 对于还不支持多个紧急号码的客户端，您可以使用的旧的紧急拨号串和拨号掩码配置。 支持多个紧急号码的客户端，您可以定义为"911"和"450"而不是屏蔽 450 紧急号码。
  
 **伦敦**— 对于尚不支持多个紧急号码的客户端，您可以使用的旧的紧急拨号串和拨号掩码配置。 对于支持多个紧急号码的客户端，您可以为每个定义"999"和"112"掩码与紧急号码。
  
 **印度**— 所有部署客户端支持多个紧急号码。 在印度，仅需要配置多个紧急号码。
  
## <a name="client-support"></a>客户端支持
<a name="BKMK_Clients"> </a>

下表显示了支持多个紧急号码的客户端。Microsoft 将继续测试并发布对其他客户端的支持。请经常返回查看。

|**Windows**|**版本**|
|:-----|:-----|
|**即点即用** <br/> |抄送 （当前通道） 发布的 2016-年 5 月 10，版本 1604 (生成 6868.2062)  <br/> |
||发布于 2016 年 6 月 14 日的 FRDC（第一版当前频道） - 版本 1605（内部版本 6965.2058）  <br/> |
||发布于 2016 年 10 月 11 日的 DC（延期频道）- 版本 1605（内部版本 6965.2092）  <br/> |
|**MSI** <br/> |6 月 7 日更新-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac 和 iOS** <br/> |**版本** <br/> |
||用于业务 Mac 客户端版本 16.9 Skype  <br/> 适用于业务 iOS 客户端版本 6.16 Skype  <br/> |
|**Android** <br/> |**版本** <br/> |
||Skype 的业务 Android 客户端版本 6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip 和 Aastra 6725ip 电话-年 9 月 2016 累积更新 (生成 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 电话-年 9 月 2016年累积更新 (生成 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500、 Polycom CX600 和 Polycom CX3000 电话-年 9 月 2016年累积更新 (生成 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

