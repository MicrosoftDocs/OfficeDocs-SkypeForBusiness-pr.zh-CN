---
title: 翻译直接路由的电话号码
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 电话系统直接路由。
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727764"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>将电话号码转换为备用格式

本文介绍如何将出站和入站呼叫的号码转换为备用格式。 这是配置直接路由的以下步骤中的步骤 4：

- 第 1 步 [将 SBC 与 Microsoft 电话系统连接并验证连接](direct-routing-connect-the-sbc.md) 
- 第 2 步 [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)   
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- **步骤 4.将数字转换为备用格式**   (本文) 

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

有时，租户管理员可能希望根据创建的模式更改出站和/或入站呼叫的数量，以确保与会话边界控制器 (SBC) 的互操作性。 本文介绍如何指定数字转换规则策略以将数字转换为备用格式。 

可以使用数字转换规则策略来翻译以下内容的数字：

- 入站呼叫：从 PSTN 终结点 (调用方) 到 Teams 客户端 (被调用方) 
- 出站呼叫：从 Teams 客户端 (调用方) 呼叫到 PSTN 终结点 (被调用方) 

策略在 SBC 级别应用。 可以将多个转换规则分配给 SBC，这些规则按照在 PowerShell 中列出这些规则时的顺序应用。 还可以更改策略中规则的顺序。

若要创建、修改、查看和删除数字操作规则，请使用 [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule)、 [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule)、 [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) 和 [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) cmdlet。

若要在 SBC 上分配、配置和列出编号操作规则，请使用 [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) 和 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet 以及 InboundTeamsNumberTranslationRules、InboundPSTNNumberTranslationRules、OutboundTeamsNumberTranslationRules 参数和 OutboundPSTNNumberTranslationRules 参数。

> [!NOTE]
> 转换规则的最大总数为 400，最大转换参数名称长度为 100 个符号，最大转换参数模式长度为 1024 个符号，最大转换参数转换长度为 256 个符号。


## <a name="example-sbc-configuration"></a>示例 SBC 配置

对于此方案，运行 New-CsOnlinePSTNGateway cmdlet 来创建以下 SBC 配置：

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

下表汇总了分配给 SBC 的转换规则：

|名称  |模式 |转换  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | +1206555$1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555$1         |
|StripPlus1    |^\+1 (\d{10}) $          | $1         |

在以下示例中，有两个用户：Alice 和 Bob。 Alice 是 Teams 用户，其号码为 +1 206 555 0100。 Bob 是 PSTN 用户，其号码为 +1 425 555 0100。

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>示例 1：对 10 位数号码的入站调用

Bob 使用非 E.164 十位数号码调用 Alice。 Bob 拨2065550100以到达 Alice。
SBC 在 RequestURI 和 To 标头中使用2065550100，在 From 标头中使用4255550100。


|头  |源语言 |已翻译的标头 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:2065550100@sbc.contoso.com|邀请 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|自    |自： \<sip:2065550100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|从   |从： \<sip:4255550100@sbc.contoso.com>|从： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>示例 2：对四位数号码的入站调用

Bob 使用四位数数字调用 Alice。 Bob 拨打 0100 以到达 Alice。
SBC 在 RequestURI 和 To 标头中使用 0100，在 From 标头中使用4255550100。


|头  |源语言 |已翻译的标头 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:0100@sbc.contoso.com          |邀请 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|从   |从： \<sip:4255550100@sbc.contoso.com>|从： \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>示例 3：使用 10 位非 E.164 号码的出站呼叫

Alice 使用 10 位数字调用 Bob。 Alice 拨打 425 555 0100 联系 Bob。
SBC 配置为对 Teams 和 PSTN 用户使用非 E.164 十位数数字。

在此方案中，拨号计划在将号码发送到直接路由接口之前进行转换。 当 Alice 在 Teams 客户端中输入 425 555 0100 时，国家/地区拨号计划会将号码转换为 +14255550100。 生成的数字是拨号计划规则和 Teams 转换规则的累积规范化。 Teams 翻译规则删除拨号计划添加的“+1”。


|头  |源语言 |已翻译的标头 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:+14255550100@sbc.contoso.com          |邀请 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|自    |自： \<sip:+14255550100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|从   |从： \<sip:+12065550100@sbc.contoso.com>|从： \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>示例 4：使用四位数非 E.164 号码的出站呼叫

Alice 使用四位数号码调用 Bob。 Alice 使用 0100 通过呼叫或联系人联系 Bob。
SBC 配置为对 Teams 用户使用非 E.164 四位数数字，对 PSTN 用户使用 10 位数字。 此方案中不应用拨号计划。


|头  |源语言 |已翻译的标头 |已应用参数和规则  |
|---------|---------|---------|---------|
|RequestURI  |邀请 sip:0100@sbc.contoso.com           |邀请 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|自    |自： \<sip:0100@sbc.contoso.com>|自： \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|从   |从： \<sip:+12065550100@sbc.contoso.com>|从： \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
