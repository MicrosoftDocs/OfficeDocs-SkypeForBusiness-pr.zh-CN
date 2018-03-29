---
title: 在 Skype for Business Server 2015 中规划多个紧急号码
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 阅读本主题，了解如何在 Skype for Business Server 2015 中规划多个紧急号码。
ms.openlocfilehash: f24f895a6d6b0fd5095ef0e03f487fcdf8a98dca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划多个紧急号码
 
阅读本主题，了解如何在 Skype for Business Server 2015 中规划多个紧急号码。
  
Skype 业务服务器现在支持的客户端配置的多个紧急号码。 多个紧急号码是 6 月的 2016 年引入的新功能累积更新。 虽然美国只有一个紧急号码，即 911，但很多国家支持多个紧急号码。 英国，例如，支持 999 紧急数具体到英国和 112，欧盟的紧急号码。 
  
此功能对美国境内希望为多代码蓝色紧急号码提供漫游支持的医疗保健提供商也很有用。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多个紧急号码和位置策略

您配置紧急调用通过创建将实现定义如何紧急调用策略的位置。 使用位置策略来定义哪个号码构成紧急呼叫 — — 例如，911 在美国;999，112 在大不列颠及北爱尔兰联合王国。 位置策略决定用户启用的紧急电话，以及如果是这样的行为属于紧急呼叫。 您还可以定义是否应自动通知公司的安全，并应如何路由呼叫。
  
关于定义和修改的位置策略的详细信息，请参阅[规划业务服务器 2015年的 Skype 的位置策略](location-policies.md)和[业务服务器 2015年的 Skype 的创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。 这些主题描述了概念有关的位置策略;但是，您必须按照中[配置多个紧急号码中业务 2015年的 Skype](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)的说明来配置多个紧急号码。
  
规划多个紧急号码时，请牢记以下要求：
  
- 与 6 月的 2016年累积更新，您可以定义给定的位置策略最多 5 个紧急号码。 与 11 月 2016年累积更新，此数字将增加到 100。
    
    > [!NOTE]
    > 如果您有尚未升级到 11 月 2016年累积更新，请参阅[更新业务服务器 2015年的 Skype](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 为每个紧急号码，您可以指定零个或更多紧急拨蒙版，特定于给定的位置策略。
    
    拨号掩码是指：在拨打该号码时，希望将其转换为紧急拨号号码的值。 例如，假设在此字段输入值 212，而紧急拨号号码字段的值为 911。 当用户拨打 212 时，号码将转换为 911。 这样就可以替代紧急号码拨打并且仍然有到达紧急服务的调用 (例如，如果有人从某个国家或地区具有不同的紧急号码试图拨打的国家或地区的数字而不是为数量国家或地区，他们目前在）。 可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 拨号掩码字符串限制为 100 个字符。 每个字符都必须为 0 到 9 的数字。
    
- 每个位置策略都具有一个公用电话交换网 (PSTN) 用法，用于确定路由使用此策略的客户端拨出的紧急呼叫所使用的语音路由。每个紧急号码可以拥有唯一的路由。
    
- 如果某个位置策略同时定义了 EmergencyNumbers 和 DialString 参数，并且客户端支持多个紧急号码，则紧急号码优先。 如果客户端不支持多个紧急号码，则使用紧急拨号串。
    
- 有关哪些 Skype 业务和 Lync 客户端支持接收多个紧急号码、 拨打掩码和公用交换的电话网络 (PSTN) 使用实例的信息，请参阅[支持的客户端](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 不能通过 Skype 业务控制面板中配置多个紧急号码。 必须使用 PowerShell 来配置多个紧急号码。 
  
配置多个紧急号码之前，请牢记以下要求：
  
- 若要配置多个紧急号码，您必须使用新建 CsEmergencyNumber cmdlet，和您必须定义通过使用[New CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)指定 EmergencyNumbers 参数来支持多个紧急电话号码的位置策略和[一组 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet。
    
- 	如果你拥有使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 定义的号码，EmergencyNumbers 参数指定的值的优先级高于旧值。即，EmergencyDialString 和 EmergencyDialMask 参数的值将被忽略。
    
- 如果您有现有数字定义的 EmergencyDialString 和 EmergencyDialMask 的参数，*并且未配置新的紧急号码*，使用集 CsLocationPolicy 或新建 CsLocationPolicy cmdlet 将继续现有的数字使用。
    
- 要使多个紧急号码功能起作用，你所运行的客户端版本必须支持新功能。 旧客户端将继续使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 指定的旧值。 
    
- 如果用户将拨打匹配拨号串的号码，则无需拨号掩码。 例如，如果用户拨打的号码是 911，则拨号串是 911，且无需掩码。 
    
有关配置多个紧急号码的详细信息，请参阅[的配置多个紧急情况中业务 2015年的 Skype 编号](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表显示了位置策略示例（用于举例说明，并未显示所有属性）：
  

|**位置策略名称**|**启用的 E911**|**紧急拨号字符串**|**拨号掩码**|**紧急号码**|**PSTN 用法**|**所需的位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国  <br/> |是  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |是  <br/> |
|US-Hospital  <br/> |是  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|伦敦  <br/> |是  <br/> |999  <br/> |144  <br/> |999 144  <br/> 112-911; 117 和 118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美国**— — 不需要为多个紧急号码。 在美国，使用旧的紧急拨号字符串和拨掩码配置。
  
 **美国医院**— — 要求不以屏蔽"450"。 对于客户端还不支持多个紧急号码，您可以使用旧的紧急拨号字符串和拨掩码配置。 对于支持多个紧急号码的客户端，您可以定义"911"和"450"而不是掩盖 450 的紧急号码。
  
 **伦敦**— — 对于客户端还不支持多个紧急号码，您可以使用旧紧急拨号字符串和拨掩码配置。 对于支持多个紧急号码的客户端，可以定义每个"999"和"112"使用蒙版的紧急号码。
  
 **印度**— — 所有已部署的客户端支持多个紧急号码。 在印度，您只需要配置多个紧急号码。
  
## <a name="client-support"></a>客户端支持
<a name="BKMK_Clients"> </a>

下表显示了支持多个紧急号码的客户端。Microsoft 将继续测试并发布对其他客户端的支持。请经常返回查看。

|**Windows**|**版本**|
|:-----|:-----|
|**即点即用** <br/> |抄送 （当前通道） 发布的 5 月 10，2016-版本 1604 (生成 6868.2062)  <br/> |
||发布于 2016 年 6 月 14 日的 FRDC（第一版当前频道） - 版本 1605（内部版本 6965.2058）  <br/> |
||发布于 2016 年 10 月 11 日的 DC（延期频道）- 版本 1605（内部版本 6965.2092）  <br/> |
|**MSI** <br/> |6 月 7 日更新的[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac 和 Io** <br/> |**版本** <br/> |
||Skype 业务 mac 客户端版本 16.9  <br/> Skype 的业务 iOS 客户端版本 6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||Skype 的 Android 业务客户端版本 6.17  <br/> |
|**Lync 电话版** <br/> |**版本** <br/> |
|| Aastra 6721ip 和 Aastra 6725ip 电话-9 月 2016 累积更新 (生成 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110，HP 4120 电话-9 月 2016年累积更新 (生成 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500、 Polycom CX600 和 Polycom CX3000 电话-9 月 2016年累积更新 (生成 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

