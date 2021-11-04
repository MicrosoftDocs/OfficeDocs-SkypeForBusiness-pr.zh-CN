---
title: 在呼叫中规划多个紧急Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: 阅读本主题，了解如何在 Skype for Business Server 中规划多个紧急Skype for Business Server。
ms.openlocfilehash: 8e4761b22295d71c33af414e2a92dac7bf1210d6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741959"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>在呼叫中规划多个紧急Skype for Business Server
 
阅读本主题，了解如何在 Skype for Business Server 中规划多个紧急Skype for Business Server。
  
Skype for Business Server现在支持为客户端配置多个紧急号码。 多个紧急号码是 2016 年 6 月累积更新中引入的新功能。 尽管美国有一个紧急号码 911，但多个国家/地区支持多个紧急号码。 例如，英国支持 999（特定于英国紧急号码）和 112（欧盟紧急号码）。 
  
此功能还可用于美国境内希望具有对多个蓝色紧急号码的漫游支持的医疗保健提供商。
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>多个紧急号码和位置策略

通过创建定义如何实施紧急呼叫的位置策略来配置紧急呼叫。 使用位置策略定义构成紧急呼叫的号码，例如，美国的 911;英国为 999 和 112。 位置策略确定用户是否启用了紧急呼叫，如果是，则确定紧急呼叫的行为。 还可以定义是否应该自动通知公司安全，以及如何路由呼叫。
  
有关定义和修改位置策略的信息，请参阅在 Skype for Business Server[](location-policies.md)中规划位置策略[Skype for Business Server。](../../deploy/deploy-enterprise-voice/create-location-policies.md) 这些主题介绍有关位置策略的概念;但是，你必须按照在呼叫中配置[多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的Skype for Business配置多个紧急号码。
  
规划多个紧急号码时，请牢记以下事项：
  
- 使用 2016 年 6 月累积更新，你可以为给定位置策略定义最多 5 个紧急号码。 随着 2016 年 11 月累积更新，此数字将增长到 100。
    
    > [!NOTE]
    > 如果尚未升级到 2016 年 11 月累积更新，请参阅[2015 年 11](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)月Skype for Business Server更新。 
  
- 对于每个紧急号码，可以指定零个或多个紧急拨号掩码，这些掩码对于给定的位置策略是唯一的。
    
    拨号掩码是拨号时要转换为紧急拨号号码值的值的号码。 例如，假定在此字段中输入值 212，紧急拨号号码字段的值为 911。 当用户拨打 212 时，该号码将转换为 911。 这样，可以拨打备用紧急号码，但仍使呼叫到达紧急服务 (例如，如果来自具有不同紧急号码的某个国家/地区或地区的某人尝试拨打该国家/地区的号码，而不是当前位于) 中的某个国家/地区的号码。 您可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 拨号掩码的字符串限制为 100 个字符。 每个字符都必须为 0 到 9 的数字。
    
- 每个位置策略都有一个公用电话交换 (PSTN) 用法，用于确定使用此策略路由来自客户端的紧急呼叫的语音路由。 用法可以具有每个紧急号码的唯一路由。
    
- 如果位置策略同时定义了 EmergencyNumbers 和 DialString 参数，并且客户端支持多个紧急号码，则紧急号码优先。 如果客户端不支持多个紧急号码，则使用紧急拨号串。
    
- 有关哪些客户端Skype for Business Lync 客户端支持接收多个紧急号码、拨号掩码和公用电话交换网 (PSTN) 用法的信息，请参阅客户端[支持](multiple-emergency-numbers.md#BKMK_Clients)。
    
> [!NOTE]
> 不能使用"安全"控制面板配置Skype for Business紧急号码。 必须使用 PowerShell 配置多个紧急号码。 
  
配置多个紧急号码之前，请牢记以下事项：
  
- 若要配置多个紧急号码，必须使用 New-CsEmergencyNumber cmdlet，并且必须通过使用 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 和 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数来定义支持多个紧急号码的位置策略。
    
- 如果使用带 EmergencyDialString 和 EmergencyDialMask 参数的 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 定义了现有号码，则 EmergencyNumbers 参数指定的值将优先于旧值。 即，EmergencyDialString 和 EmergencyDialMask 参数的值将被忽略。
    
- 如果已使用 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet（带 EmergencyDialString 和 EmergencyDialMask 参数）定义现有号码，并且未配置新的紧急号码，将继续使用现有号码。
    
- 若要使多个紧急号码功能正常工作，您正在运行的客户端版本必须能够支持新功能。 较旧的客户端将继续使用由 Set-CsLocationPolicy 或 New-CsLocationPolicy cmdlet 指定的旧值以及 EmergencyDialString 和 EmergencyDialMask 参数。 
    
- 如果用户将拨打与拨号串匹配的号码，则不需要拨号掩码。 例如，如果用户拨打的号码是 911，则拨号串是 911，不需要掩码。 
    
有关配置多个紧急号码的信息，请参阅在 Skype for Business[中配置多个紧急Skype for Business。](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)
  
下表显示了用于示例 (策略的示例位置策略，并非所有属性都) ：
  

|**位置策略名称**|**E911 已启用**|**紧急拨号字符串**|**拨号掩码**|**紧急号码**|**PSTN 用法**|**所需位置**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国  <br/> |是  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |是  <br/> |
|US-Hospital  <br/> |是  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |是  <br/> |
|伦敦  <br/> |是  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |否  <br/> |
|印度  <br/> |是  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |否  <br/> |
   
 **美国** — 不需要多个紧急号码。 在美国，使用旧的紧急拨号串和拨号掩码配置。
  
 **US-Hospital** - 要求不要掩盖"450"。 对于尚不支持多个紧急号码的客户端，可以使用旧的紧急拨号串和拨号掩码配置。 对于支持多个紧急号码的客户端，你可以为"911"和"450"定义紧急号码，而不是掩盖 450。
  
 **London** — 对于尚不支持多个紧急号码的客户端，可以使用旧的紧急拨号串和拨号掩码配置。 对于支持多个紧急号码的客户端，你可以为"999"和"112"定义紧急号码，每个号码都有掩码。
  
 **印度** — 所有部署的客户端都支持多个紧急号码。 印度只需要配置多个紧急号码。
  
## <a name="client-support"></a>客户端支持
<a name="BKMK_Clients"> </a>

下表显示了对多个紧急号码的客户端支持。 Microsoft 将继续测试并发布对其他客户端的支持。 请经常检查。

|**Windows**|**版本**|
|:-----|:-----|
|**即点即用** <br/> |CC (Current Channel) 2016 年 5 月 10 日发布 - 版本 1604 (内部版本 6868.2062)   <br/> |
||FRDC (2016) 2016 年 6 月 14 日发布 - 版本 1605 (内部版本 6965.2058)   <br/> |
||DC (延期频道) 2016 年 10 月 11 日发布 - 版本 1605 (内部版本 6965.2092)   <br/> |
|**MSI** <br/> |6 月 7 日更新 - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac 和 iOS** <br/> |**版本** <br/> |
||Skype for BusinessMac 客户端版本 16.9  <br/> Skype for Business iOS 客户端版本 6.16  <br/> |
|**Android** <br/> |**版本** <br/> |
||Skype for BusinessAndroid 客户端版本 6.17  <br/> |
|**Lync Phone Edition** <br/> |**版本** <br/> |
|| Aastra 6721ip 和 Aastra 6725ip 电话 - 2016 年 9 月累积更新 (内部版本 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 和 HP 4120 电话 - 2016 年 9 月累积更新 (内部版本 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500、Polycom CX600 和 Polycom CX3000 电话 - 2016 年 9 月累积更新 (内部版本 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
