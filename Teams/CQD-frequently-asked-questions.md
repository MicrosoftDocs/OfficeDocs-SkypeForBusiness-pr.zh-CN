---
title: 'CQD (调用质量仪表板) 常见问题解答 (常见问题解答) '
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 阅读常见问题解答 (常见问题解答) 以及有关 Microsoft Teams 通话质量仪表板 (CQD) 的解答。
ms.openlocfilehash: 862967138321b1855f2fdc5b0c8b6ce6caca887f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789387"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>CQD (调用质量仪表板) 常见问题解答 (常见问题解答) 

## <a name="frequently-asked-questions"></a>常见问题解答

[如果一个或多个会议参与者体验不佳，为什么 CQD 会将呼叫标记为“良好”？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[为什么在度量值以及如何获取最准确的卷时，呼叫和用户计数值的差异高达 0.2%？ ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[为什么在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[我尝试将 CQD 用于使用情况类型的报表，发现某些数据不完整 - 为什么会这样？](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[为什么在仅针对 Teams 进行筛选时，在 CQD 中看到Skype for Business信息？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[为什么当我知道应该有更多的条目时，我的自定义报表最多只返回 10，000 行？](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[为什么Wi-Fi VPN 连接显示为有线而不是 Wi-Fi？](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[我在 Teams 中启用了基于策略的录制，现在对等呼叫被标记为会议 - 发生了什么？](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一个或多个会议参与者体验不佳，为什么 CQD 会将呼叫标记为“良好”？

查看 CQD 用于 [流分类](stream-classification-in-call-quality-dashboard.md)的规则。
 
对于音频流，根据调用) 的长度为平均值计算 (的五个分类器中的任何一个都可以在“良好”参数中。 这并不意味着用户没有遇到导致音频退出、静态或故障的原因。 

若要确定它是否是网络问题，请查看会话的平均值与最大值之间的增量。 最大值是会话期间检测和报告的最大值。
 
下面是一个有关如何排查这种情况的示例。 假设你在通话期间进行网络跟踪，前 20 分钟没有丢失的数据包，但随后有 1.5 秒的数据包间隙，然后适合通话的剩余部分。 即使在 Wireshark 跟踪 RTP 分析中，平均值将<10% (0.1) 数据包丢失。 最大数据包丢失情况是什么？ 5 秒内的 1.5 秒为 30% (0.3) 。 这是否发生在 5 秒采样期内 (，或者可以在采样期间) 进行拆分？
 
如果网络指标在平均值和最大值中看起来不错，请查看其他遥测数据： 
- 检查 CPU 事件比率不足，以查看检测到的可用 CPU 资源是否不足并导致质量不佳。 
- 音频设备是否处于半双工模式，以防止由于麦克风离扬声器太近而产生反馈？ 
- 检查设备半双工 AEC 事件比率。 插入中心或停靠站时，是否因为 USB 音频退出而从设备（如麦克风）发出噪音或静态？  
- 检查设备故障和麦克风故障事件比率。 设备本身是否正常运行？  
- 检查捕获和呈现设备未正常运行的事件比率。


有关 CQD 遥测中可用的维度和度量值的详细信息，请阅读 [通话质量仪表板中提供的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)值。

对于背景噪音，请检查静音事件比率，以查看参与者被静音的时间长度。
 
在 CQD 中创建详细报告并筛选会议 ID，查看会议中的所有用户和流，并添加感兴趣的字段。 报告此问题的用户可能不是有问题的用户。 他们只是报告体验。
 
遥测不一定能指出问题，但它可以帮助你更好地了解在何处查看和通知决策。 是网络、设备、驱动程序还是固件更新、使用情况或用户？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>为什么在度量值以及如何获取最准确的卷时，呼叫和用户计数值的差异高达 0.2%？ 

若要计算调用计数和用户计数度量值，对数据集中的调用或用户标识符执行不同的 countif 操作。 在大型数据集上，非重复 countif 操作固有最多 0.2% 的错误。 对于最准确的卷，应依赖流计数度量值，因为它们不依赖于此不同的 countif 操作。 筛选以减少数据量可能会减少错误，但可能无法在不同的调用和用户计数中消除此错误源。 请参阅 [通话质量仪表板中可用的度量值和度量](dimensions-and-measures-available-in-call-quality-dashboard.md) 值，这些度量值会受到影响。

  
### <a name="why-cant-i-see-euii-in-cqd"></a>为什么在 CQD 中看不到 EUII？

这些管理员角色可以访问 CQD，但无法查看 EUII (最终用户可识别信息) ：

- Microsoft 365 报表阅读器
- Teams 通信支持专家

若要详细了解可访问 CQD 的角色（包括 EUII），请阅读 [分配用于访问 CQD 的角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>我尝试将 CQD 用于使用情况类型的报表，发现某些数据不完整 - 为什么会这样？

CQD、呼叫分析、CallRecord 图形 API 和实时分析等呼叫质量管理工具基于诊断遥测数据。 我们在 Teams 呼叫质量管理工具中显示的信息仅与我们从参与呼叫的客户端收到的遥测数据一样完整。 我们可能无法收到完整的遥测数据（例如网络中断、 [防火墙或代理配置错误](/microsoft-365/enterprise/urls-and-ip-address-ranges)）的原因有多种。 我们将继续努力提高 Teams 客户端向服务提供遥测数据的可靠性和复原能力。

考虑到这一点，我们不支持使用调用质量管理工具进行使用情况报告。 它们不是为适应这些类型的报告方案而设计的，也不适用于这些类型的报告方案，而且许多使用情况统计信息在这些工具中不可用且不可用。 Teams 管理员中心提供一系列[使用情况报告](teams-analytics-and-reports/teams-reporting-reference.md)，并且可以直接从 Teams 客户端获得[会议出席情况报告](teams-analytics-and-reports/meeting-attendance-report.md)。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>为什么在仅针对 Teams 进行筛选时，在 CQD 中看到Skype for Business信息？

仅在 CQD 报表中筛选 Teams (isTeams = 1) 时，将筛选 *第一个终结点* 为 Teams 的所有调用。 如果Skype for Business第 *二个终结点*，则该信息将显示在 CQD 报表中。 根据客户的方案，在配置[呼叫数据连接器](/skypeforbusiness/hybrid/plan-call-data-connector)时，CQD 可能包括 2019 Skype for Business Server调用。 它可能还包括 Skype Bot 呼叫 (AA、CVI、VDI) 、实时事件和 PSTN 调用。

可以通过筛选第一个 *用户代理类别* 和第二个 *用户代理类别* 等维度，从查询中删除Skype for Business信息。 还可以使用将第一个和第二个维度合并为单个筛选器的 *用户代理类别对* 。

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>为什么当我知道应该有更多的条目时，我的自定义报表最多只返回 10，000 行？

CQD 专为汇总的数据查询而设计，并非为数据导出而设计。 建议尽可能重新调整报表，以防止超过 10，000 行限制。 首先，使用更广泛的低基数维度（如月份、年份、日期、区域、国家/地区等）查看 KPI。 可以从那里向下钻取到越来越高的基数维度。 Helpdesk 和 Location-Enhanced 报表都提供了此向下钻取工作流的良好示例。

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>为什么Wi-Fi VPN 连接显示为有线而不是 Wi-Fi？

这是预期行为。 VPN 供应商创建了一个虚拟以太网适配器，该适配器被视为有线连接。 由于未正确标记，因此操作系统不知道它是一个Wi-Fi连接，并将其报告为有线连接。

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>我在 Teams 中启用了基于策略的录制，现在对等呼叫被标记为会议 - 发生了什么？

在 Microsoft Teams 中启用基于策略的录制时，这是预期的行为。 基于策略的录制使用部署在 Microsoft Azure 中的 Teams 记录器机器人来捕获会议内容以实现符合性目的。 在呼叫质量管理中，“对等”是对媒体流量的描述，而不是用户之间的交互。 由于记录器机器人本身是呼叫的一方，因此调用不再是对等的，而是多方调用。 多方呼叫被 Microsoft Teams 分类为会议，因此在 CQD 和其他呼叫质量工具中查看这些呼叫时，会显示这些呼叫。

## <a name="related-articles"></a>相关文章

[改进和监视 Teams 的呼叫质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置呼叫质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上传租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
