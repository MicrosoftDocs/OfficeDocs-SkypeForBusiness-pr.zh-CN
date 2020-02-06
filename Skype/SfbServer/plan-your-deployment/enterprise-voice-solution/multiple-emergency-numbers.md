---
title: 在 Skype for Business 服务器中规划多个紧急号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 阅读本主题，了解如何在 Skype for Business 服务器中规划多个紧急号码。
ms.openlocfilehash: 6f10b5c22a26a42f33f2a3b453dd2e244c9f32ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815960"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划多个紧急号码
 
阅读本主题，了解如何在 Skype for Business 服务器中规划多个紧急号码。
  
Skype for business 服务器现支持客户端的多个紧急号码的配置。 多个紧急号码是2016年6月累积更新中引入的一项新功能。 虽然美国只有一个紧急号码，即 911，但很多国家支持多个紧急号码。 例如，英国支持999、特定于英国的紧急号码和112，即欧盟的紧急号码。 
  
此功能对美国境内希望为多代码蓝色紧急号码提供漫游支持的医疗保健提供商也很有用。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多个紧急号码和位置策略

通过创建定义如何实施紧急电话的位置策略来配置紧急电话。 您可以使用位置策略来定义哪个号码构成紧急呼叫（例如，美国911）;999和112（英国）。 位置策略确定用户是否已启用紧急呼叫，以及是否有紧急呼叫的行为。 您还可以定义是否应自动通知企业安全性以及如何路由呼叫。
  
有关定义和修改位置策略的详细信息，请参阅[为 skype for Business 服务器计划位置策略](location-policies.md)和[在 Skype for Business 服务器中创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。 以下主题介绍有关位置策略的概念;但是，您必须按照在[Skype For business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的说明来配置多个紧急号码。
  
规划多个紧急号码时，请牢记以下要求：
  
- 使用2016年6月累积更新，您最多可以为给定的位置策略定义5个紧急号码。 在2016年11月累积更新中，此数字增加到100。
    
    > [!NOTE]
    > 如果您尚未升级到2016年11月累积更新，请参阅[Skype for Business Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 对于每个紧急号码，您可以指定零个或多个紧急拨号掩码，它们对于给定的位置策略是唯一的。
    
    拨号掩码是指：在拨打该号码时，希望将其转换为紧急拨号号码的值。 例如，假设在此字段输入值 212，而紧急拨号号码字段的值为 911。 当用户拨打 212 时，号码将转换为 911。 这允许拨打备用紧急号码，并且仍然可以呼叫紧急服务（例如，如果某个国家或地区的某人使用不同的紧急号码，请尝试拨打该国家或地区的号码而不是电话号码当前所在的国家或地区）。 可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 拨号掩码的字符串限制为100个字符。 每个字符都必须为 0 到 9 的数字。
    
- 每个位置策略都具有一个公用电话交换网 (PSTN) 用法，用于确定路由使用此策略的客户端拨出的紧急呼叫所使用的语音路由。每个紧急号码可以拥有唯一的路由。
    
- 如果某个位置策略同时定义了 EmergencyNumbers 和 DialString 参数，并且客户端支持多个紧急号码，则紧急号码优先。 如果客户端不支持多个紧急号码，则使用紧急拨号串。
    
- 有关哪些 Skype for Business 和 Lync 客户端支持接收多个紧急号码、拨号掩码和公共交换电话网络（PSTN）用途的信息，请参阅[客户端支持](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 您不能使用 Skype for Business 控制面板配置多个紧急号码。 必须使用 PowerShell 来配置多个紧急号码。 
  
配置多个紧急号码之前，请牢记以下要求：
  
- 若要配置多个紧急号码，必须使用 CsEmergencyNumber cmdlet，并且你必须通过使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数来定义支持多个紧急号码的位置策略。
    
- 	如果你拥有使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 定义的号码，EmergencyNumbers 参数指定的值的优先级高于旧值。即，EmergencyDialString 和 EmergencyDialMask 参数的值将被忽略。
    
- 如果你已使用 CsLocationPolicy 或 CsLocationPolicy cmdlet 使用 EmergencyDialString 和 EmergencyDialMask 参数定义了现有数字，*但未配置新的紧急电话号码*，则将继续使用现有号码。
    
- 要使多个紧急号码功能起作用，你所运行的客户端版本必须支持新功能。 旧客户端将继续使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 指定的旧值。 
    
- 如果用户将拨打匹配拨号串的号码，则无需拨号掩码。 例如，如果用户拨打的号码是 911，则拨号串是 911，且无需掩码。 
    
有关配置多个紧急号码的详细信息，请参阅[在 Skype For business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表显示了位置策略示例（用于举例说明，并未显示所有属性）：
  

|**位置策略名称**|**是否启用 E911**|**紧急拨号串**|**拨号掩码**|**紧急电话号码**|**PSTN 用法**|**所需位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国  <br/> |是  <br/> |911  
  <br/> | 112;999 <br/> ||USEmergency  <br/> |是  <br/> |
|US-Hospital  <br/> |是  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|伦敦  <br/> |是  <br/> |999  
  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美国**-对多个紧急电话号码没有任何要求。 在美国，您使用旧的 "紧急拨号字符串" 和 "拨号掩码" 配置。
  
 **美国-医院**——要求不要屏蔽 "450"。 对于尚不支持多个紧急号码的客户端，您可以使用旧的 "紧急拨号字符串" 和 "拨号掩码" 配置。 对于支持多个紧急号码的客户端，你可以为 "911" 和 "450" （而不是屏蔽450）定义紧急号码。
  
 **伦敦**—对于尚不支持多个紧急号码的客户端，您可以使用旧的紧急拨号字符串和拨号掩码配置。 对于支持多个紧急号码的客户端，你可以为 "999" 和 "112" 定义一个紧急号码，每个都有掩码。
  
 **印度**—所有已部署的客户都支持多个紧急号码。 在印度，您只需配置多个紧急号码。
  
## <a name="client-support"></a>客户端支持
<a name="BKMK_Clients"> </a>

下表显示了支持多个紧急号码的客户端。Microsoft 将继续测试并发布对其他客户端的支持。请经常返回查看。

|**Windows**|**版本**|
|:-----|:-----|
|**即点即用** <br/> |2016-版本1604（内部版本6868.2062）发布的 CC （当前频道）  <br/> |
||发布于 2016 年 6 月 14 日的 FRDC（第一版当前频道） - 版本 1605（内部版本 6965.2058）  <br/> |
||发布于 2016 年 10 月 11 日的 DC（延期频道）- 版本 1605（内部版本 6965.2092）  <br/> |
|**MSI** <br/> |7月7日更新-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac 和 iOS** <br/> |**版本** <br/> |
||Skype for business Mac 客户端版本16。9  <br/> Skype for Business iOS 客户端版本6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||Skype for Business Android 客户端版本6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip 和 Aastra 6725ip 电话-2016 年9月累积更新（内部版本7577.4512）-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 电话-9 月2016累积更新（内部版本7577.4512）-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600 和 Polycom CX3000 电话-2016 年9月累积更新（内部版本7577.4512）-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

