---
title: 对直接路由进行监视和故障排除
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: 本文介绍如何监视和解决直接路由配置。
ms.openlocfilehash: 89cbf47433fb26867ff2546a98360e1fa715e349
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894242"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>对直接路由进行监视和故障排除

本文介绍如何监视和解决直接路由配置。 

发起和接收呼叫使用直接路由中的功能涉及以下组件： 

- 会话边界控制器 (Sbc) 
- Microsoft 云直接路由组件 
- 电信中继 

如果您有难题解决问题，请打开与您的 SBC 供应商或 Microsoft 支持案例。 

Microsoft 从事的故障排除与监视提供更多工具。 请检查定期更新的文档。 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用会话初始协议 (SIP) Options 消息的会话边界控制器的监控可用性

直接路由使用 SIP 的选项，发送的会话边界控制器来监视 SBC 运行状况。 没有要启用 SIP Options 监控租户管理员所需的操作。 收集的信息考虑时做出路由决定。 

例如，如果为某个特定用户，有几个可用于路由呼叫的 Sbc，直接路由认为收到来自每个 SBC 来确定路由的 SIP Options 信息。 

下图显示了配置的一个示例： 

![SIP 选项配置示例](media/sip-options-config-example.png)

当用户发出呼叫号码 +1 425\<直接路由任何七个 digits> 计算路由。 作为路由中有两个 SBCs: sbc1.contoso.com 和 sbc2.contoso.com。 这两个 SBCs 作为路由中具有相同的优先级。 选取 SBC 之前, 的路由机制计算 SBCs 基于 SBC 发送 SIP 选项时的运行状况上次时间。 

SBC 被视为正常运行，如果时刻发送呼叫的统计信息显示 SBC 发送定期的选项。  

直接路由计算的时间间隔定期 SBC 在发起呼叫和添加五分钟之前发送选项时，按照两次的平均值。 

例如，假定以下几点： 

- 配置 SBC 发送选项每分钟。 
- SBC 已配对在上午 11: 00。  
- SBC 发送选项在 11.01 AM、 11.02 AM，依此类推。  
- 在 11.15，用户发出呼叫和路由机制选择此 SBC。 

应用以下逻辑： 当 SBC plus 五分钟 = 七个分钟发送选项 （一个分钟再加上一个分钟 = 两分钟） 的两倍的平均时间间隔。 这是 SBC 的正则时间间隔的值。
 
如果在我们的示例 SBC 发送在上午 11: 08 11 15 上午: （建立呼叫的时间） 之间的任何时间段的选项，则被视为正常运行。 否则，将从路由降级 SBC。 

降级意味着不会在首次尝试 SBC。 例如，我们有 sbc1.contoso.com 和 sbc2.contoso.com 具有相同的优先级。  

如果 sbc1.contoso.com 不发送 SIP 定期的选项，如上面所述，它将被降级。 接下来，sbc2.contoso.com 尝试进行呼叫。 如果 sbc2.contoso.con 无法传送呼叫，才会生成失败 （降级） sbc1.contoso.com 将再次尝试。 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>监视呼叫质量分析仪表板和 SBC 日志 
 
在某些情况下，尤其是在初始配对，可能会出现与配置不正确的 Sbc 和/或直接路由服务相关的问题。 

您可以使用以下工具来监视您的配置：  
 
- 呼叫质量仪表板 
- SBC 日志 

直接路由服务已向呼叫分析或 SBC 日志报告非常描述性错误代码。 

呼叫质量仪表板提供有关呼叫质量和可靠性的信息。 若要了解有关如何使用调用分析的问题进行疑难解答的详细信息，请参阅[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和[使用呼叫分析解决质量欠佳的呼叫质量](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。 

呼叫失败时调用分析提供标准 SIP 代码，以帮助您进行疑难解答。 

![呼叫失败的示例 SIP 代码](media/failed-response-code.png)

但是，呼叫到达的直接路由的内部组件和失败时，仅可帮助呼叫的分析。 出现时 SBC 配对问题或 SIP"邀请"被拒绝 （例如，中继配置 FQDN 不正确的名称），其中的问题，将不帮助呼叫的分析。 在这种情况下，请参阅 SBC 日志。 直接路由将问题的详细的说明发送给 SBCs;可以从 SBC 日志读取这些问题。 
