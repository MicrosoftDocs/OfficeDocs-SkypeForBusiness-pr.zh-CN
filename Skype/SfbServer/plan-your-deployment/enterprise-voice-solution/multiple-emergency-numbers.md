---
title: 在 Skype for Business Server 中规划多个紧急号码
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: eb5fbc55bc7f2e783fbfa98c7bc7fb6db67ff748
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813862"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>在 Skype for Business Server 中规划多个紧急号码
 
阅读本主题，了解如何在 Skype for Business Server 中规划多个紧急号码。
  
Skype for Business Server 现在支持为客户端配置多个紧急号码。 多个紧急号码是 2016 年 6 月累积更新中引入的一项新功能。 尽管美国有一个紧急号码 911，但多个国家/地区支持多个紧急号码。 例如，英国支持 999（特定于英国紧急号码）和 112（欧盟紧急号码）。 
  
此功能还适用于希望对多个代码蓝色紧急号码提供漫游支持在美国的医疗保健提供商。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多个紧急号码和位置策略

通过创建定义如何实施紧急呼叫的位置策略来配置紧急呼叫。 使用位置策略定义构成紧急呼叫的号码，例如，美国的 911;英国为 999 和 112。 位置策略确定是否为用户启用紧急呼叫，如果是，则确定紧急呼叫的行为。 还可以定义是否应该自动通知公司安全，以及如何路由呼叫。
  
有关定义和修改位置策略详细信息，请参阅 Plan [location policies for Skype for Business Server](location-policies.md) and Create location policies in Skype for Business [Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md) 这些主题介绍有关位置策略的概念;但是，你必须按照在 Skype [for Business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 中的说明配置多个紧急号码。
  
规划多个紧急号码时，请记住以下事项：
  
- 通过 2016 年 6 月累积更新，您可以为给定位置策略定义最多 5 个紧急号码。 随着 2016 年 11 月累积更新，此数字将增长到 100。
    
    > [!NOTE]
    > 如果尚未升级到 2016 年 11 月累积更新，请参阅 [Skype for Business Server 2015 更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 
  
- 对于每个紧急号码，可以指定零个或多个紧急拨号掩码，这些掩码对于给定位置策略是唯一的。
    
    拨号掩码是拨号时要转换为紧急拨号号码值的值的号码。 例如，假定在此字段中输入值 212，紧急拨号号码字段的值为 911。 当用户拨打 212 时，该号码将转换为 911。 这样，可以拨打备用紧急号码，并且仍可将呼叫联系紧急服务 (例如，如果来自某个国家/地区或地区的用户尝试拨打该国家/地区或地区的号码，而不是当前位于) 中的某个国家/地区的号码。 您可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 拨号掩码的字符串限制为 100 个字符。 每个字符都必须为 0 到 9 的数字。
    
- 每个位置策略都有一个公用电话交换网 (PSTN) 用法，用于确定使用此策略路由来自客户端的紧急呼叫的语音路由。 该用法可以具有每个紧急号码的唯一路由。
    
- 如果位置策略同时定义了 EmergencyNumbers 和 DialString 参数，并且客户端支持多个紧急号码，则紧急号码优先。 如果客户端不支持多个紧急号码，则使用紧急拨号字符串。
    
- 有关哪些 Skype for Business 和 Lync 客户端支持接收多个紧急号码、拨号掩码和公用电话交换网 (PSTN) 的信息，请参阅客户端 [支持](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 不能使用 Skype for Business 控制面板配置多个紧急号码。 必须使用 PowerShell 配置多个紧急号码。 
  
配置多个紧急号码之前，请牢记以下事项：
  
- 若要配置多个紧急号码，必须使用 New-CsEmergencyNumber cmdlet，并且必须通过使用 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 和 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数来定义支持多个紧急号码的位置策略。
    
- 如果使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 定义了现有号码，则 EmergencyNumbers 参数指定的值将优先于旧值。 即，EmergencyDialString 和 EmergencyDialMask 参数的值将被忽略。
    
- 如果使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 定义了现有号码，并且未配置新的紧急号码，将继续使用现有号码。
    
- 若要使多个紧急号码功能正常工作，您正在运行的客户端版本必须能够支持新功能。 较旧的客户端将继续将 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 指定的旧值与 EmergencyDialString 和 EmergencyDialMask 参数一同使用。 
    
- 如果用户将拨打与拨号字符串匹配的号码，则不需要拨号掩码。 例如，如果用户拨打的号码为 911，则拨号串为 911，不需要掩码。 
    
有关配置多个紧急号码详细信息，请参阅在 Skype for Business 中配置 [多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。
  
下表显示了示例位置 (示例，并非所有属性都显示在示例中) ：
  

|**位置策略名称**|**E911 已启用**|**紧急拨号字符串**|**拨号掩码**|**紧急号码**|**PSTN 用法**|**所需位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国  <br/> |是  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |是  <br/> |
|US-Hospital  <br/> |是  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|伦敦  <br/> |是  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美国** — 不需要多个紧急号码。 在美国，使用旧的紧急拨号串和拨号掩码配置。
  
 **US-Hospital** - 要求不要掩盖"450"。 对于尚不支持多个紧急号码的客户端，可以使用旧的紧急拨号串和拨号掩码配置。 对于支持多个紧急号码的客户端，你可以为"911"和"450"定义紧急号码，而不是屏蔽 450。
  
 **London** — 对于尚不支持多个紧急号码的客户端，可以使用旧的紧急拨号串和拨号掩码配置。 对于支持多个紧急号码的客户端，你可以为"999"和"112"定义紧急号码，并为每个号码定义掩码。
  
 **印度** — 所有部署的客户端都支持多个紧急号码。 印度只需要配置多个紧急号码。
  
## <a name="client-support"></a>客户端支持
<a name="BKMK_Clients"> </a>

下表显示了对多个紧急号码的客户端支持。 Microsoft 将继续测试并发布对其他客户端的支持。 请经常检查。

|**Windows**|**版本**|
|:-----|:-----|
|**即点即用** <br/> |CC (Current Channel) 2016 年 5 月 10 日发布 - 版本 1604 (内部版本 6868.2062)   <br/> |
||FRDC (2016 年 6 月 14 日) 首次发布当前频道版本 - 版本 1605 (内部版本 6965.2058)   <br/> |
||DC (延期频道) 2016 年 10 月 11 日发布 - 版本 1605 (内部版本 6965.2092)   <br/> |
|**MSI** <br/> |6 月 7 日更新 - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac 和 iOS** <br/> |**版本** <br/> |
||Skype for Business Mac 客户端版本 16.9  <br/> Skype for Business iOS 客户端版本 6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||Skype for Business Android 客户端版本 6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip 和 Aastra 6725ip 电话 - 2016 年 9 月累积更新 (内部版本 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 电话 - 2016 年 9 月累积 (内部版本 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600 和 Polycom CX3000 电话 - 2016 年 9 月累积更新 (内部版本 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

