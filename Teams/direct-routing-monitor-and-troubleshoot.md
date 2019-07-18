---
title: 对直接路由进行监视和故障排除
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 本文介绍如何监视直接路由配置并对其进行故障排除。
ms.openlocfilehash: d20a409c7a5e902149ff20e72dde90850f0f5d12
ms.sourcegitcommit: 9751f34318119991b1bd32b384b8e1479c83cb0e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2019
ms.locfileid: "35768153"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>对直接路由进行监视和故障排除

本文介绍如何监视直接路由配置并对其进行故障排除。 

使用直接路由拨打和接听电话的功能包括以下组件: 

- 会话边框控制器 (SBCs) 
- 在 Microsoft 云中直接路由组件 
- 电信中继 

如果您在解决问题时遇到困难, 请与 SBC 供应商或 Microsoft 打开支持案例。 

Microsoft 正在致力于为疑难解答和监视提供更多工具。 请定期查看文档以获取更新。 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用会话初始协议 (SIP) 选项消息监视会话边框控制器的可用性

直接路由使用由会话边界控制器发送的 SIP 选项监视 SBC 运行状况。 租户管理员无需执行任何操作即可启用 SIP 选项监视。 当做出路由决策时, 将考虑所收集的信息。 

例如, 如果对于特定用户, 有多种可用于路由呼叫的 SBCs, 直接路由将考虑从每个 SBC 收到的 SIP 选项信息来确定路由。 

下图显示了配置示例: 

![SIP 选项配置示例](media/sip-options-config-example.png)

当用户拨打号码 + 1 425 \<> 任何七位数字时, 直接路由会评估路由。 路由中有两个 SBCs: sbc1.contoso.com 和 sbc2.contoso.com。 两个 SBCs 在路由中具有同等优先级。 在选取 SBC 之前, 路由机制会根据 SBC 何时发送 SIP 选项来评估 SBCs 的运行状况。 

如果发出呼叫的统计信息显示 SBC 每分钟发送选项, 则该 SBC 被视为健康。  

进行调用时, 将应用以下逻辑:

- SBC 的配对时间为 11.00 AM。  
- SBC 在 11.01 AM、11.02 AM 等位置发送选项。  
- 在11.15 中, 用户进行呼叫, 路由机制将选择此 SBC。 

直接路由会将常规的间隔选项分为三次 (常规间隔为一分钟)。 如果在过去三分钟内发送选项, 则 SBC 被视为状态良好。

如果示例中的 SBC 在 11.12 AM 和 11.15 AM 之间的任何时间段内发送选项 (进行调用的时间), 则认为其状态良好。 如果不是, 则 SBC 将从路由降级。 

降级意味着不会首先尝试 SBC。 例如, 我们有具有同等优先级的 sbc1.contoso.com 和 sbc2.contoso.com。  

如果 sbc1.contoso.com 不按上述方式发送 SIP 选项, 则会将其降级。 接下来, sbc2.contoso.com 尝试通话。 如果 sbc2 无法送达呼叫, 则会在生成故障之前再次尝试 sbc1.contoso.com (已降级)。 

如果一个路线中的两个 (或更多) SBCs concidered 完好且相等, Fisher-Yates 的无序应用以 distrubute SBCs 之间的通话。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>监控通话质量分析仪表板和 SBC 日志 
 
在某些情况下, 特别是在初始配对过程中, 可能存在与 SBCs 和/或直接路由服务的错误配置相关的问题。 

可以使用以下工具监视配置:  
 
- 呼叫质量仪表板 
- SBC 日志 

直接路由服务有很高描述性错误代码报告给调用分析或 SBC 日志。 

通话质量仪表板提供有关通话质量和可靠性的信息。 若要了解有关如何使用呼叫分析解决问题的详细信息, 请参阅[打开和使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和[使用呼叫分析解决较差的通话质量](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。 

在呼叫失败的情况下, 呼叫分析提供标准 SIP 代码来帮助您进行故障排除。 

![通话失败的 SIP 代码示例](media/failed-response-code.png)

但是, 只有当呼叫到达直接路由的内部组件并失败时, 呼叫分析才会有所帮助。 如果 SBC 配对出现问题或出现 SIP "Invite" 被拒绝的问题 (例如, 中继 FQDN 的名称配置错误), 则呼叫分析将不会提供帮助。 在这种情况下, 请参阅 SBC 日志。 直接路由将问题的详细描述发送到 SBCs;可以从 SBC 日志中读取这些问题。 
