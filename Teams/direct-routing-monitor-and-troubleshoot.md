---
title: 监视直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何监视和排查直接路由配置，包括会话边界控制器、直接路由组件和电信中继。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657242"
---
# <a name="monitor-direct-routing"></a>监视直接路由

本文介绍如何监视和排查直接路由配置问题。 

使用直接路由发出和接收呼叫的能力涉及以下组件： 

- 会话边框控制器 (SBC)  
- Microsoft 云中的直接路由组件 
- 电信中继 

如果疑难解答问题，可以向 SBC 供应商或 Microsoft 提出支持案例。 

Microsoft 正在努力提供更多用于故障排除和监视的工具。 定期检查文档以获取更新。 

## <a name="troubleshoot-direct-routing"></a>直接路由疑难解答

若要排查直接路由问题，请参阅 [诊断直接路由的问题](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues)。

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用会话启动协议 (SIP) 选项消息监视会话边框控制器的可用性

直接路由使用会话边框控制器发送的 SIP 选项来监视 SBC 运行状况。 租户管理员无需执行任何操作即可启用 SIP 选项监视。 在做出路由决策时，会考虑收集的信息。 

例如，如果对于特定用户，有多个 SBC 可用于路由呼叫，则直接路由会考虑从每个 SBC 接收的 SIP 选项信息来确定路由。 

下图显示了配置的示例： 

![SIP 选项配置示例。](media/sip-options-config-example.png)

当用户调用号码 +1 425 \<any seven digits>时，直接路由会评估路由。 路由中有两个 SBC：sbc1.contoso.com 和 sbc2.contoso.com。 这两个 SBC 在路由中具有同等优先级。 在选取 SBC 之前，路由机制会根据 SBC 上次发送 SIP 选项的时间来评估 SBC 的运行状况。 

如果发送呼叫时的统计信息显示 SBC 每分钟发送选项，则 SBC 被视为正常。  

调用时，将应用以下逻辑：

- SBC 于上午 11：00 配对。  
- SBC 在上午 11：01、上午 11：02 等发送选项。  
- 11：15 时，用户发出呼叫，路由机制选择此 SBC。 

直接路由采用常规间隔选项三次 (常规间隔为 1 分钟) 。 如果在过去三分钟内发送了选项，则 SBC 被视为正常。

如果示例中的 SBC 在调用) 时间 (上午 11：12 到上午 11：15 之间的任何时间段发送选项，则会被视为正常运行。 否则，SBC 将从路由降级。 

降级意味着不会先尝试 SBC。 例如，我们具有同等优先级的 sbc1.contoso.com 和 sbc2.contoso.com。  

如果 sbc1.contoso.com 未按前面所述的定期时间间隔发送 SIP 选项，则会降级。 接下来，sbc2.contoso.com 尝试调用。 如果 sbc2.contoso.con 无法传送调用，则会在生成故障之前再次尝试 sbc1.contoso.com (降级) 。 

如果一个路由中的两个 (或多个) SBC 被视为正常且相等，则应用Fisher-Yates洗牌以在 SBC 之间分配调用。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>监视呼叫质量分析仪表板和 SBC 日志 
 
在某些情况下，尤其是在初始配对期间，可能存在与 SBC 或直接路由服务配置错误相关的问题。 

可以使用以下工具监视配置：  
 
- 呼叫质量仪表板 
- SBC 日志 

直接路由服务具有报告给呼叫分析或 SBC 日志的描述性错误代码。

呼叫质量仪表板提供有关呼叫质量和可靠性的信息。 若要详细了解如何使用呼叫分析排查问题，请参阅[打开和使用 Microsoft Teams 的呼叫质量仪表板，并Skype for Business联机](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和[使用呼叫分析来排查通话质量不佳的问题](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。 

如果呼叫失败，呼叫分析会提供标准 SIP 代码来帮助你进行故障排除。 

![调用失败的示例 SIP 代码。](media/failed-response-code.png)

但是，调用分析只能在调用到达直接路由的内部组件并失败时提供帮助。 例如，如果 SBC 配对出现问题或 SIP“Invite”被拒绝 (，则中继 FQDN 的名称) 配置错误，则呼叫分析将不起作用。 在这种情况下，请参阅 SBC 日志。 直接路由向 SBC 发送问题的详细说明;可以从 SBC 日志中读取这些问题。
