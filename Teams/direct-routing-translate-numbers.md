---
title: 转换直接路由的电话号码
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
description: 了解如何配置 Microsoft Phone 系统直接路由。
ms.openlocfilehash: 2b675948153589c73fa545a95ac785b716b55265
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157939"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>将电话号码转换为备用格式

本文介绍如何将出站和入站通话的号码转换为备用格式。  以下是配置直接路由的步骤4：

- 第 1 步 [将 SBC 连接到 Microsoft Phone 系统并验证连接](direct-routing-connect-the-sbc.md) 
- 第 2 步 [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)   
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- **步骤4。将数字转换为备用格式**（本文）

有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。

有时，租户管理员可能希望根据其创建的模式更改出站和/或入站呼叫的号码，以确保与会话边界控制器（SBCs）的互操作性。 本文介绍如何指定 "数字翻译规则" 策略以将数字转换为备用格式。 

你可以使用 "数字翻译规则" 策略来翻译以下各项的数字：

- 入站呼叫：从 PSTN 终结点（呼叫方）到团队客户端（被呼叫方）的呼叫
- 出站呼叫：从团队客户端（呼叫者）到 PSTN 终结点（被呼叫方）的呼叫

该策略将应用于 SBC 级别。 你可以将多个翻译规则分配给 SBC，这些规则将按照在 PowerShell 中列出它们时的显示顺序进行应用。 您还可以更改策略中规则的顺序。

若要创建、修改、查看和删除数字操作规则，请使用[CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)和[Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) cmdlet。

若要在 SBCs 上分配、配置和列出数字操作规则，请使用[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)和[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) Cmdlet 以及 InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules、OutboundPSTNNumberTranslationRules、InboundTeamsNumberTranslationRulesList、InboundPSTNNumberTranslationRulesList、OutboundTeamsNumberTranslationRulesList 和 OutboundPSTNNumberTranslationRulesList实参.


## <a name="example-sbc-configuration"></a>SBC 配置示例

对于此方案，运行```New-CsOnlinePSTNGateway``` cmdlet 以创建以下 SBC 配置：

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

下表汇总了分配给 SBC 的转换规则：

|名称  |模式 |转换  |
|---------|---------|---------|
|AddPlus1     |^ （\d{10}） $          |+1$1          |
|AddE164SeattleAreaCode      |^ （\d{4}） $          | + 1206555 $ 1         |
|AddSeattleAreaCode    |^ （\d{4}） $          | 425555 $ 1         |
|StripPlus1    |^ + 1 （\d{10}） $          | $1         |

在以下示例中，有两个用户： Alice 和 Bob。 Alice 是其数字为 + 1 206 555 0100 的团队用户。 小明是指其号码为 + 1 425 555 0100 的 PSTN 用户。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>示例1：对十位数字的入站呼叫

小明使用非 E-164 10 位数字调用刘爱琳。 Bob 拨打2065550100以联系 Alice。
SBC 在 RequestURI 中使用2065550100，在 "来自" 头中使用 "页眉" 和 "4255550100"。


|接头  |源语言 |已翻译页眉 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:2065550100@sbc.contoso.com|邀请 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|自    |收件人： \<sip:2065550100@sbc.contoso.com>|收件人： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|从   |发件\<自： sip:4255550100@sbc.contoso.com>|发件\<自： sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>示例2：对四位数数字的入站呼叫

小明使用四位数字调用刘爱琳。 Bob 拨打0100以联系 Alice。
SBC 在 RequestURI 中使用0100，在 "来自" 头中使用 "页眉" 和 "4255550100"。


|接头  |源语言 |已翻译页眉 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:0100@sbc.contoso.com          |邀请 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|自    |收件人： \<sip:0100@sbc.contoso.com>|收件人： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|从   |发件\<自： sip:4255550100@sbc.contoso.com>|发件\<自： sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>示例3：使用10位非 E 的非 n 位数字的出站呼叫

Alice 使用十位数字呼叫 Bob。 Alice 拨打 425 555 0100 以联系 Bob。
对于团队和 PSTN 用户，SBC 配置为使用非 E. 164 10 位数字。

在这种情况下，拨号计划会在将数字发送到直接路由界面之前对其进行转换。 当 Alice 在团队客户端中输入 425 555 0100 时，将按国家/地区的拨号计划将该号码转换为 + 14255550100。 生成的数字是拨号计划规则和团队翻译规则的累积规范化。 团队翻译规则删除由拨号计划添加的 "+ 1"。


|接头  |源语言 |已翻译页眉 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:+14255550100@sbc.contoso.com          |邀请 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|自    |收件人： \<sip:+14255550100@sbc.contoso.com>|收件人： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|从   |发件\<自： sip:+12065550100@sbc.contoso.com>|发件\<自： sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>示例4：使用四位非 n 位数字的拨出电话

Alice 使用四位数字调用 Bob。 Alice 使用0100与来自呼叫或通过联系人的 Bob 联系。
SBC 配置为为团队用户使用非 E 的4位数字，对于 PSTN 用户使用10位数字。 这种情况下不会应用拨号计划。


|接头  |源语言 |已翻译页眉 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:0100@sbc.contoso.com           |邀请 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|自    |收件人： \<sip:0100@sbc.contoso.com>|收件人： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|从   |发件\<自： sip:+12065550100@sbc.contoso.com>|发件\<自： sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
