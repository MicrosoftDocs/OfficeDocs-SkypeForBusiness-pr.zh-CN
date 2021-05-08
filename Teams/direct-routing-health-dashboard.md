---
title: 直接路由的运行状况仪表板
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用运行状况仪表板监视会话边界控制器和直接路由之间的连接。
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122226"
---
# <a name="health-dashboard-for-direct-routing"></a>直接路由的运行状况仪表板

使用直接路由的运行状况仪表板可以监视会话边界控制器与 SBC (与) 路由接口之间的连接。  使用运行状况仪表板，可以监视有关 SBC、电话服务和 SBC 与直接路由接口之间的网络参数的信息。 此信息可帮助你识别问题，包括通话中断的原因。 例如，如果 SBC 上的证书已过期或存在网络问题，SBC 可能会停止发送调用。 请参阅 [管理员角色](using-admin-roles.md) ，了解谁有权访问运行状况仪表板。

运行状况仪表板监视两个级别的信息：

- 连接的 SDC 的总体运行状况
- 有关连接的 SDC 的详细信息

可以在管理中心内查看Microsoft Teams Skype for Business仪表板。

## <a name="overall-health"></a>总体运行状况

运行状况仪表板提供与连接的 SDC 的总体运行状况相关的以下信息：

 ![显示运行状况仪表板统计信息](media/direct-routing-dashboard-stats1.png)

- **直接路由摘要** - 显示系统中注册的 SDC 总数。 注册意味着租户管理员使用 New-CsOnlinePSTNGateway 添加了 SBC。 如果 SBC 已添加到 PowerShell 中，但从未连接，则运行状况仪表板会显示它处于不正常状态。

- **SBC** - 已配对 SBC 的 FQDN。

- **网络有效性 (NER)** - NER 通过测量发送的呼叫数与发送给收件人的呼叫数来测量网络传送呼叫的能力。  

   NER 度量网络向远端终端传送调用的能力，不包括导致呼叫拒绝的用户操作。  如果收件人拒绝了呼叫或将呼叫发送到语音邮件，该呼叫将计为成功的送达。 这意味着，应答消息、繁忙信号或没有应答的铃声都被视为成功的呼叫。
  
   例如，假设直接路由向 SBC 发送了调用，并且 SBC 返回 SIP 代码"504 服务器时间过长 - 服务器尝试访问另一台服务器，尝试处理请求时未收到提示响应"。 此响应表明 SBC 端存在问题，这会降低此 SBC 的运行状况仪表板上的 NER。
  
   由于你采取的操作可能取决于受影响的调用数，因此运行状况仪表板显示已分析多少个调用来计算参数。 如果调用数小于 100，则 NER 可能相当低，但仍为正常。

   用于计算 NER 的公式为：

   NER = 100 x (应答呼叫 + 用户忙 + 无应答 + 终端拒绝) /总呼叫数

- **平均呼叫持续时间** - 有关平均呼叫持续时间的信息可以帮助你监视呼叫质量。 1：1 PSTN 呼叫的平均持续时间为 4 到 5 分钟。  但是，对于每个公司，此平均值可能不同。  Microsoft 建议为贵公司的平均通话持续时间建立基线。 如果此参数明显低于基线，它可能表示用户遇到呼叫质量或可靠性问题，并且比平时挂断时间更早。 如果平均呼叫持续时间（例如 15 秒）开始极低，则呼叫者可能会挂断，因为服务未可靠执行。

   由于你采取的操作可能取决于受影响的调用数，因此运行状况仪表板显示已分析多少个调用来计算参数。

- **TLS 连接状态** - TLS (传输层安全性) 连接显示直接路由和 SBC 之间的 TLS 连接状态。 运行状况仪表板还会分析证书到期日期，如果证书设置为在 30 天内过期，则发出警告，以便管理员可以在服务中断之前续订证书。

   通过单击"警告"消息，可以在右侧弹出窗口中查看详细的问题说明，以及解决问题的建议。

- **SIP 选项状态** - 默认情况下，SBC 每分钟发送一次选项消息。 此配置可能因不同的 SBC 供应商而异。 如果未发送或未配置 SIP 选项，直接路由会发出警告。 有关 SIP 选项监视以及 SBC 可标记为无法正常工作的条件的详细信息，请参阅监视和排查直接 [路由问题](direct-routing-monitor-and-troubleshoot.md)。

- **详细 SIP 选项状态** - 除了显示 SIP 选项流存在问题外，运行状况仪表板还提供错误的详细说明。 可以通过单击"警告"消息访问说明。 右侧弹出窗口会显示详细的错误说明。

   SIP 选项状态消息的可能值如下所示：

    - 活动 - SBC 处于活动状态 -- Microsoft Direct Routing 服务会定期看到选项流动。

    - 警告，无 SIP 选项 - 使用 New-CsOnlinePSTNGateway 命令创建的数据库 (会话边界控制器) 。 它配置为发送 SIP 选项，但直接路由服务从未看到从此 SBC 返回的 SIP 选项。

    - 警告，未配置 SIP 消息 - 未打开使用 SIP 选项的中继监视。 Microsoft 呼叫系统使用 SIP 选项和传输层安全性 (TLS) 握手监视来检测应用程序级别连接的会话边界控制器 (SDC) 的运行状况。 如果可以通过 ping) 在网络级别访问此 (，但证书已过期或 SIP 堆栈不起作用，则你将遇到问题。 为了帮助尽早识别此类问题，Microsoft 建议启用发送 SIP 选项。 请查看 SBC 制造商文档以配置发送 SIP 选项。

- **并发调用容量** - 可以通过将 New- 或 Set-CsOnlinePSTNGateway 命令与 -MaxConcurrentSessions 参数一起指定 SBC 可以处理的并发调用的限制。 此参数计算直接路由使用特定 SBC 发送或接收的调用数，并将其与限制集进行比较。 注意：如果 SBC 还处理对不同 PBX 的调用，此数字不会显示实际并发调用。

## <a name="detailed-information-for-each-sbc"></a>每个 SBC 的详细信息

还可以查看特定 SBC 的详细信息，如以下屏幕截图所示：

![运行状况仪表板 SBC 详细信息](media/direct-routing-dashboard-SBC-detail1.png)

详细视图显示以下附加参数：

- **TLS 连接状态** – 这是与"总体运行状况"页上相同的指标;

- **TLS 连接上次状态** – 显示 SBC 与直接路由服务建立 TLS 连接的时间;

- **SIP 选项状态** - 与"总体运行状况"页上的指标相同。

- **上次检查的 SIP 选项** – 上次收到 SIP 选项的时间。

- **SBC 状态** - 基于所有受监视参数的 SBC 总体状态。

- **并发调用**- 显示 SBC 处理的并发调用数。 此信息可用于预测所需的并发通道数并查看趋势。 可以按天数滑动数据，并按入站/出 (/所有流的呼叫) 。

- **网络参数** - 从直接路由接口到会话边界控制器测量所有网络参数。 有关建议值的信息，请参阅[准备](./prepare-network.md)组织的网络以Microsoft Teams，并查看 Customer Edge Microsoft Edge值。

   - 抖动 - 是使用 RTCP 和 RTP 控制协议在两个终结点之间计算的网络传播延迟 (毫秒) 。

   - 数据包丢失 – 是未能到达的数据包的度量值;它是在两个终结点之间计算的。

   - 延迟 - (往返时间) 是发送信号所花的时间长度加上接收该信号的确认所花的时间长度。 此时间延迟由信号的两个点之间的传播时间组成。

   可以按天数滑动数据，并按入站/出 (/所有流的呼叫) 。

**网络有效性比率** - 此参数与"总体运行状况"仪表板上显示的参数相同，但可以选择按时序或调用方向对数据进行切片。