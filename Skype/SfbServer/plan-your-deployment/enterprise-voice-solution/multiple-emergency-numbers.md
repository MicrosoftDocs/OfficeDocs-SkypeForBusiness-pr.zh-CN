---
title: 在 Skype for Business Server 中规划多个紧急号码
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
description: 阅读本主题，了解如何在 Skype for Business Server 中规划多个紧急号码。
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983017"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>在 Skype for Business Server 中规划多个紧急号码
 
阅读本主题，了解如何在 Skype for Business Server 中规划多个紧急号码。
  
Skype for Business Server 现在支持为客户端配置多个紧急号码。 "多个紧急号码" 是6月2016累积更新中引入的一项新功能。 虽然美国有一个紧急号码911，但许多国家/地区都支持多个紧急号码。 例如，英国支持999、特定于英国的紧急号码和112（欧盟的紧急号码）。 
  
此功能对于美国的卫生保健提供商也很有用，他们希望具有对多个代码蓝色紧急号码的漫游支持。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多个紧急号码和位置策略

通过创建定义如何实施紧急呼叫的位置策略来配置紧急呼叫。 可以使用位置策略定义发生紧急呼叫的号码，例如，美国的911。999和112在英国。 位置策略确定用户是否启用了紧急呼叫，以及紧急呼叫的行为。 您还可以定义是否应自动通知企业安全性，以及应如何路由呼叫。
  
有关定义和修改位置策略的详细信息，请参阅为[skype For Business Server 规划位置策略](location-policies.md)和[在 Skype for Business server 中创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。 这些主题介绍了有关位置策略的概念;但是，必须按照在[Skype For business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的说明配置多个紧急号码。
  
在规划多个紧急号码时，请记住以下几点：
  
- 在6月2016累积更新中，可以为给定位置策略定义最长5个紧急号码。 在11月2016累积更新中，此数字增加到100。
    
    > [!NOTE]
    > 如果尚未升级到2016年11月累积更新，请参阅[更新到 Skype For Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 对于每个紧急号码，可以指定零个或多个紧急拨号掩码，这对于给定的位置策略而言是唯一的。
    
    拨号掩码是在拨号时要转换为 "紧急拨号号码" 值的号码。 例如，假设您在此字段中输入值212，并且 "紧急拨号号码" 字段的值为911。 当用户拨打212时，该号码将转换为911。 这允许拨打备用紧急号码，并且仍然可以呼叫紧急服务（例如，如果来自不同紧急号码的国家或地区的人尝试拨打该国家或地区的号码，而不是电话号码当前所在的国家或地区）。 您可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212; 414。 拨号掩码的字符串限制为100个字符。 每个字符都必须为 0 到 9 的数字。
    
- 每个位置策略都有一个公共交换电话网络（PSTN）用法，用于确定使用此策略从客户端路由紧急呼叫时使用的语音路由。 使用情况可具有每个紧急号码的唯一路由。
    
- 如果某个位置策略同时定义了 EmergencyNumbers 和 DialString 参数，并且客户端支持多个紧急号码，则紧急号码优先。 如果客户端不支持多个紧急号码，则使用紧急拨号字符串。
    
- 有关哪些 Skype for Business 和 Lync 客户端支持接收多个紧急号码、拨号掩码和公用电话交换网（PSTN）用法的信息，请参阅[客户端支持](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 您不能使用 Skype for Business 控制面板配置多个紧急号码。 必须使用 PowerShell 配置多个紧急号码。 
  
在配置多个紧急号码之前，请记住以下几点：
  
- 若要配置多个紧急号码，必须使用 New-csemergencynumber cmdlet，并且必须通过在[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 中指定 EmergencyNumbers 参数来定义支持多个紧急号码的位置策略。
    
- 如果使用 New-cslocationpolicy 或带有 EmergencyDialString 和 EmergencyDialMask 参数的 New-cslocationpolicy cmdlet 定义了现有号码，则使用 EmergencyNumbers 参数指定的值将优先于旧值. 也就是说，EmergencyDialString 和 EmergencyDialMask 参数的值将被忽略。
    
- 如果使用 New-cslocationpolicy 或带有 EmergencyDialString 和 EmergencyDialMask 参数的 New-cslocationpolicy cmdlet 定义了现有号码，*但未配置新的紧急号码*，则将继续使用现有号码。
    
- 若要使多个紧急号码功能正常工作，您运行的客户端版本必须能够支持新功能。 较旧的客户端将继续使用 New-cslocationpolicy 或 New-cslocationpolicy cmdlet 指定的旧值和 EmergencyDialString 和 EmergencyDialMask 参数。 
    
- 如果用户要拨打的号码与拨号字符串相匹配，则无需拨号掩码。 例如，如果用户拨打的号码是911，则拨号字符串为911，并且不需要掩码。 
    
有关配置多个紧急号码的详细信息，请参阅[在 Skype For business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表显示了示例位置策略（出于示例的目的，并不显示所有属性）：
  

|**位置策略名称**|**已启用 E911**|**紧急拨号字符串**|**拨号掩码**|**紧急号码**|**PSTN 用法**|**必需的位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国  <br/> |是  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |是  <br/> |
|美国-医院  <br/> |是  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|南京  <br/> |是  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美国**—无需对多个紧急号码进行要求。 在美国，使用旧的紧急拨号字符串和拨号掩码配置。
  
 **美国-医院**—要求不要屏蔽 "450"。 对于尚不支持多个紧急号码的客户端，您可以使用旧的紧急拨号字符串和拨号掩码配置。 对于支持多个紧急号码的客户端，您可以为 "911" 和 "450" 而不是掩码450定义紧急号码。
  
 **伦敦**—对于尚不支持多个紧急号码的客户端，您可以使用旧的紧急拨号字符串和拨号掩码配置。 对于支持多个紧急号码的客户端，您可以为 "999" 和 "112" 定义一个紧急号码，其中每个都有掩码。
  
 **印度**—所有已部署的客户端都支持多个紧急号码。 在印度，您只需配置多个紧急号码。
  
## <a name="client-support"></a>客户端支持
<a name="BKMK_Clients"> </a>

下表显示了对多个紧急号码的客户端支持。 Microsoft 将继续测试并发布对其他客户端的支持。 请经常检查。

|**Windows**|**版本**|
|:-----|:-----|
|**即点即用** <br/> |在2016年5月10日发布的 CC （当前频道）-版本1604（内部版本6868.2062）  <br/> |
||2016年6月14日发布的 FRDC （第一版）-版本1605（内部版本6965.2058）  <br/> |
||2016年10月11日发布的 DC （延期频道）-版本1605（内部版本6965.2092）  <br/> |
|**MSI** <br/> |6月7日更新-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac 和 iOS** <br/> |**版本** <br/> |
||Skype for Business Mac 客户端版本16。9  <br/> Skype for Business iOS 客户端版本6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||Skype for Business Android 客户端版本6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip and Aastra 6725ip 电话-2016 年9月累积更新（内部版本7577.4512）-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 电话-9 月2016累积更新（内部版本7577.4512）-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600 和 Polycom CX3000 电话-2016 年9月累积更新（内部版本7577.4512）-[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

