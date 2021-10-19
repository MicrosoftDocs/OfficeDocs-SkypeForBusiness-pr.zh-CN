---
title: 对直接路由进行监视和故障排除
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
description: 了解如何监视和排查直接路由配置问题，包括会话边界控制器、直接路由组件和电信中继。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97bc8afb3645fca4e06b859b765dfbf1e3fe1859
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462316"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>对直接路由进行监视和故障排除

本文介绍如何监视和排查直接路由配置问题。 

使用直接路由进行和接收调用的能力涉及以下组件： 

- 会话边界控制器 (SDC)  
- Microsoft 云中的直接路由组件 
- 电信中继 

如果难以排查问题，可以与 SBC 供应商或 Microsoft 建立支持案例。 

Microsoft 正在努力提供更多用于故障排除和监视的工具。 请定期查看文档了解更新。 

## <a name="direct-routing-diagnostic-tool"></a>直接路由诊断工具

如果你是管理员，可以使用以下诊断工具验证是否正确为用户配置了直接路由：

1. 选择 **下面的"** 运行测试"，这将在 Microsoft 365 管理 中填充诊断。 

   > [!div class="nextstepaction"]
   > [运行测试：直接路由](https://aka.ms/TeamsDirectRoutingDiag)

2. 在"运行诊断"窗格中，在"用户名"或"电子邮件"字段中输入要测试的用户的电子邮件，然后选择"**运行测试"。**

3. 测试将返回解决任何租户、用户或策略配置的最佳下一步，以验证用户是否正确配置了直接路由Microsoft Teams。

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>使用会话启动协议监视会话边界控制器的可用性 (SIP) 选项消息

直接路由使用会话边界控制器发送的 SIP 选项来监视 SBC 运行状况。 租户管理员无需执行任何操作来启用 SIP 选项监视。 做出路由决策时，会考虑收集的信息。 

例如，对于特定用户，如果有几个 SBC 可用于路由呼叫，则直接路由会考虑从每个 SBC 收到的 SIP 选项信息来确定路由。 

下图显示了配置的示例： 

![SIP 选项配置示例。](media/sip-options-config-example.png)

当用户调用号码 +1 425 时 \<any seven digits> ，直接路由将评估路由。 路由中有两个 SDC：sbc1.contoso.com 和 sbc2.contoso.com。 这两个 SDC 在路由中具有相同的优先级。 在选取 SBC 之前，路由机制根据 SBC 上次发送 SIP 选项的时间评估 SBC 的运行状况。 

如果发送呼叫时的统计数据显示 SBC 每分钟发送一次选项，则认为 SBC 正常。  

进行调用时，将应用以下逻辑：

- SBC 在上午 11：00 配对。  
- SBC 在上午 11：01、上午 11：02 发送选项，等等。  
- 在 11：15，用户进行调用，路由机制选择此 SBC。 

直接路由采用常规间隔选项三次 (常规间隔为一分钟) 。 如果在过去三分钟内发送了选项，则 SBC 被视为正常。

如果示例中的 SBC 在上午 11：12 到上午 11：15 之间发送了选项 (则调用) 被视为正常。 如果没有，SBC 将从路由降级。 

降级意味着不会先尝试 SBC。 例如，我们有一 sbc1.contoso.com sbc2.contoso.com 优先级的优先级。  

如果 sbc1.contoso.com 如前面所述定期发送 SIP 选项，则将其降级。 接下来，sbc2.contoso.com 尝试进行调用。 如果 sbc2.contoso.con 无法传递调用，sbc1.contoso.com (降级) 重试，然后再生成失败。 

如果一 (两) 个 SDC 被视为正常且相等，Fisher-Yates随机选择以在 SDC 之间分配调用。

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>监视呼叫质量分析仪表板和 SBC 日志 
 
在某些情况下，尤其是在初始配对期间，可能会存在与 SDC 或直接路由服务配置错误相关的问题。 

可以使用以下工具监视配置：  
 
- 呼叫质量仪表板 
- SBC 日志 

直接路由服务具有向调用分析或 SBC 日志报告的非常描述性的错误代码。 

呼叫质量仪表板提供有关呼叫质量和可靠性的信息。 若要详细了解如何使用呼叫分析排查问题，请参阅为 Microsoft Teams 和[Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)启用和使用呼叫质量仪表板和使用呼叫分析来排查呼叫质量[不佳的问题](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。 

在呼叫失败时，呼叫分析提供标准 SIP 代码来帮助进行故障排除。 

![调用失败的示例 SIP 代码。](media/failed-response-code.png)

但是，只有当调用到达直接路由的内部组件并失败时，调用分析才能提供帮助。 如果 SBC 配对问题或 SIP"邀请"被拒绝的问题 (例如，中继 FQDN 的名称未正确配置) ，呼叫分析将无用。 在这种情况下，请参阅 SBC 日志。 直接路由向 SDC 发送问题的详细说明;这些问题可以从 SBC 日志中读取。
