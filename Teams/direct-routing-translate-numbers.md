---
title: 翻译直接路由的电话号码
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 电话直接路由。
ms.openlocfilehash: ff560ca9417e5386819a90961562520da94d5cfcd65bd5348bd7718601610bf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337410"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>将电话号码转换为备用格式

本文介绍如何将出站和入站呼叫的数字转换为备用格式。  这是配置直接路由的以下步骤的步骤 4：

- 第 1 步 [连接系统Microsoft 电话 SBC 并验证连接](direct-routing-connect-the-sbc.md) 
- 第 2 步 [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)   
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- **步骤 4.将数字转换为备用格式 (**   本文) 

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

有时，租户管理员可能希望基于创建的模式更改出站和/或入站调用的数量，以确保与会话边界控制器和 SDC (互操作性) 。 本文介绍如何指定数字翻译规则策略以将数字转换为备用格式。 

可以使用"数字翻译规则"策略来翻译以下各项的数字：

- 入站呼叫：呼叫者从 PSTN 终结点 (呼叫) 呼叫Teams呼叫方 (呼叫) 
- 出站呼叫：来自呼叫方客户端Teams呼叫 (呼叫) 呼叫方呼叫方 (PSTN) 

策略在 SBC 级别应用。 可以将多个翻译规则分配给 SBC，这些规则按在 PowerShell 中列出规则时的顺序应用。 还可以更改策略中规则的顺序。

若要创建、修改、查看和删除数字操作规则，请使用 New-CsTeamsTranslationRule、Set-CsTeamsTranslationRule、Get-CsTeamsTranslationRule 和[Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) cmdlet。 [](/powershell/module/skype/new-csteamstranslationrule) [](/powershell/module/skype/set-csteamstranslationrule) [](/powershell/module/skype/get-csteamstranslationrule)

若要在 SDC 上分配、配置和列出数字操作规则，请使用 [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) 和 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet 以及 InboundTeamsNumberTranslationRules， InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules、InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules 和 OutboundPSTNNumberTranslationRules 参数。

> [!NOTE]
> 翻译规则的最大总数为 400，最大翻译参数名称长度为 100 个符号，最大翻译参数模式长度为 1024 个符号，最大翻译参数翻译长度为 256 个符号。


## <a name="example-sbc-configuration"></a>示例 SBC 配置

对于此方案， ```New-CsOnlinePSTNGateway``` 运行 cmdlet 以创建以下 SBC 配置：

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

下表汇总了分配给 SBC 的翻译规则：

|名称  |模式 |转换  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d {4}) $          | +1206555$1         |
|AddSeattleAreaCode    |^ (\d {4}) $          | 425555$1         |
|StripPlus1    |^+1 (\d {10}) $          | $1         |

在下面的示例中，有两个用户：Alice 和 Bob。 Alice 是一Teams用户，其号码为 +1 206 555 0100。 Bob 是 PSTN 用户，其号码为 +1 425 555 0100。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>示例 1：对十位数号码的入站呼叫

Bob 使用非 E.164 十位数号码呼叫 Alice。 Bob 拨打2065550100联系 Alice。
SBC 在 requestURI 2065550100 和 To 标头中使用 4255550100 和 From 标头。


|标头  |源语言 |翻译的标头 |应用的参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:2065550100@sbc.contoso.com|邀请 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|自    |自： \<sip:2065550100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules "AddPlus1"|
|从   |从： \<sip:4255550100@sbc.contoso.com>|从： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>示例 2：对四位数号码的入站呼叫

Bob 使用四位数字呼叫 Alice。 Bob 拨打 0100 联系 Alice。
SBC 在 RequestURI 和 To 标头4255550100 0100。


|标头  |源语言 |翻译的标头 |应用的参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:0100@sbc.contoso.com          |邀请 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|从   |从： \<sip:4255550100@sbc.contoso.com>|从： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>示例 3：使用十位数非 E.164 号码的出站呼叫

Alice 使用十位数号码呼叫 Bob。 Alice 拨打 425 555 0100 联系 Bob。
SBC 配置为对用户和 PSTN 用户使用非 E.164 十Teams数字。

在此方案中，拨号计划先转换号码，然后再将其发送到直接路由接口。 当 Alice 在 Teams 客户端中输入 425 555 0100 时，该号码将14255550100国家/地区拨号计划转换为 +14255550100。 生成的号码是拨号计划规则和翻译规则的累积规范化Teams规则。 呼叫Teams规则删除拨号计划添加的"+1"。


|标头  |源语言 |翻译的标头 |应用的参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:+14255550100@sbc.contoso.com          |邀请 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|自    |自： \<sip:+14255550100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|从   |从： \<sip:+12065550100@sbc.contoso.com>|从： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules "StripPlus1"         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>示例 4：使用四位数非 E.164 号码的出站呼叫

Alice 使用四位数字呼叫 Bob。 Alice 使用 0100 通过"呼叫"或联系人联系 Bob。
SBC 配置为对用户使用非 E.164 四位数字Teams PSTN 用户使用十位数号码。 此方案未应用拨号计划。


|标头  |源语言 |翻译的标头 |应用的参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:0100@sbc.contoso.com           |邀请 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList "AddSeattleAreaCode"       |
|从   |从： \<sip:+12065550100@sbc.contoso.com>|从： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)