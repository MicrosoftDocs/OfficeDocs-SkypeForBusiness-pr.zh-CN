---
title: '呼叫质量仪表板 (CQD) 常见问题解答 (常见问题) '
ms.author: serdars
author: SerdarSoysal
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
description: 阅读常见问题解答 (常见问题) 和有关Microsoft Teams呼叫质量仪表板 (CQD) 。
ms.openlocfilehash: 81c6478147e0959ca97b67ee0f01632478c0eb38
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401896"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>呼叫质量仪表板 (CQD) 常见问题解答 (常见问题) 

## <a name="frequently-asked-questions"></a>常见问题解答

[如果一个或多个会议参与者体验不佳，CQD 为何将通话标记为"良好"？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[为什么在度量值上，调用和用户计数值的差异最大为 0.2%，如何获取最准确的音量？ ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[为什么我在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[我正在尝试使用 CQD 进行使用情况类型报告，发现某些数据不完整 - 为什么？](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[为什么在仅Skype for Business筛选了 CQD 中Teams信息？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[为什么我的自定义报表在我知道应该存在更多条目时最多返回 10，000 行？](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[为什么Wi-Fi VPN 连接显示为"有线"而不是"Wlan"？](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[我打开基于策略的录制Teams现在对等呼叫被标记为会议 -- 发生了什么情况？](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一个或多个会议参与者体验不佳，CQD 为何将通话标记为"良好"？

查看 CQD 用于流分类 [的规则](stream-classification-in-call-quality-dashboard.md)。
 
对于音频流，根据调用长度计算平均值的五个分类器中的任意一个都可能是"良好"参数。 这并不意味着用户未遇到导致音频掉线、静态或故障的问题。 

若要确定它是网络问题，请看会话的平均值与最大值之间的增量。 最大值是会话期间检测到并报告的最大值。
 
下面是如何排查这种情况的示例。 假设你在调用期间进行网络跟踪，并且前 20 分钟没有丢失数据包，但随后你有 1.5 秒数据包的间隙，然后适合通话的其余部分。 即使在 Wireshark <跟踪 RTP 分析 (0.1) ，平均丢包率也只有 10%。 最大数据包丢失是什么？ 5 秒的 1.5 秒为 0.3 (30%) 。 这是在 5 秒采样期内发生的 (，还是可以在采样期间拆分) ？
 
如果网络指标在平均值和最大值中看起来不错，则查看其他遥测数据： 
- 检查"CPU 不足事件比率"，查看检测到的可用 CPU 资源是否不足，导致质量差。 
- 音频设备是否由于麦克风太靠近扬声器而以半双工模式阻止反馈？ 
- 检查设备半双工 AEC 事件比率。 插入集线器或扩展坞时，设备故障或麦克风故障是否由于 USB 音频拖放而引入噪音或静态？  
- 检查"设备故障"和"麦克风故障"事件比率。 设备本身是否正常运行？  
- 检查捕获和呈现设备无法正常工作的事件比率。


有关 CQD 遥测中可用的维度和度量值的更多内容，请阅读呼叫质量仪表板中提供的维度 [和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

对于背景噪音，请检查静音事件比率以查看参与者静音的时间长度。
 
在 CQD 中创建详细报表，并筛选会议 ID，查看会议中的所有用户和流，并添加您感兴趣的字段。 报告该问题的用户可能不是遇到该问题的用户。 他们只是报告体验。
 
遥测数据不一定会指出问题，但可以帮助你更好地了解在何处查找和通知你的决策。 是网络、设备、驱动程序或固件更新、使用情况还是用户？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>为什么在度量值上，调用和用户计数值的差异最大为 0.2%，如何获取最准确的音量？ 

若要计算调用计数和用户计数度量值，请对数据集中的调用或用户标识符执行不同的 countif 操作。 在大型数据集上，非重复 countif 操作本身存在最多 0.2% 的错误。 对于最准确的卷，应依赖于流计数度量值，因为它们不依赖于此不同的 countif 操作。 减少数据量的筛选可以减少错误，但可能无法消除不同调用和用户计数中的此错误源。 请参阅 [呼叫质量仪表板中](dimensions-and-measures-available-in-call-quality-dashboard.md) 提供的维度和度量，这些度量值会受到影响。

  
### <a name="why-cant-i-see-euii-in-cqd"></a>为什么我在 CQD 中看不到 EUII？

这些管理员角色可以访问 CQD，但无法查看 EUII (最终用户可识别信息) ：

- Microsoft 365报表读者
- Teams通信支持专家

若要详细了解可以访问 CQD 的角色（包括 EUII），请阅读 [分配用于访问 CQD 的角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>我正在尝试使用 CQD 进行使用情况类型报告，发现某些数据不完整 - 为什么？

调用质量管理工具（如 CQD、调用分析、CallRecord Graph API 和实时分析）基于诊断遥测。 在呼叫质量管理工具Teams显示的信息与从参与呼叫的客户端收到的遥测数据一样完整。 可能收到完整的遥测数据的原因有多种，例如网络中断、防火墙或代理 [配置错误](/microsoft-365/enterprise/urls-and-ip-address-ranges.md)。 我们一直努力提高客户端向服务Teams遥测数据的可靠性与复原能力。

因此，建议不要依赖呼叫质量管理工具进行使用情况报告。 Teams管理中心提供一系列使用情况[报告，会议](teams-analytics-and-reports/teams-reporting-reference.md)出席情况报告可直接从Teams[](teams-analytics-and-reports/meeting-attendance-report.md)提供。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>为什么在仅Skype for Business筛选了 CQD 中Teams信息？

如果仅在 Teams isTeams = 1) 的 CQD 报告中筛选 (，则筛选第一终结点为第一终结点的所有Teams。  如果 *第二终结点* Skype for Business，该信息会显示在 CQD 报告中。 配置呼叫数据连接器时，CQD Skype for Business Server 2019[调用，](/skypeforbusiness/hybrid/plan-call-data-connector.md)具体取决于客户的方案。 它还可能包括机器人Skype AA (CVI、VDI) 、实时事件和 PSTN 呼叫。

通过筛选第一用户代理类别Skype for Business第二用户代理类别等维度，从查询中删除 *用户信息*。  也可使用将 *第一个维度* 和第二个维度合并成单个筛选器的用户代理类别对。

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>为什么我的自定义报表在我知道应该存在更多条目时最多返回 10，000 行？

CQD 设计用于汇总数据查询，不用于数据导出。 我们建议尽可能重建报表，以防止超过 10，000 行的限制。 首先，使用更大、基数较低的维度（如月、年、日期、区域、国家/地区等）查看 KPI。 从该维度中，可以向下钻取到基数越高的维度。 支持人员报表Location-Enhanced报表都提供了此向下钻取工作流的良好示例。

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>为什么Wi-Fi VPN 连接显示为"有线"而不是"Wlan"？

这是预期行为。 VPN 供应商创建了一个被视为有线连接的虚拟以太网适配器。 由于未正确标记，操作系统不知道它是一个连接Wi-Fi报告为有线连接。

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>我打开基于策略的录制Teams现在对等呼叫被标记为会议 -- 发生了什么情况？

在启用基于策略的录制功能后，这是预期Microsoft Teams。 基于策略的录制使用Teams录制器机器人Microsoft Azure捕获会议内容，以便符合要求。 在呼叫质量管理中，"对等"是媒体流量流的描述，而不是用户之间的交互。 由于记录器机器人本身是呼叫的一方，因此该调用不再是对等调用，而是多方调用。 多方呼叫按Microsoft Teams分类为会议，因此在 CQD 和其他呼叫质量工具中查看这些呼叫时，将指示这些呼叫。

## <a name="related-articles"></a>相关文章

[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[使用 CQD (设置呼叫质量) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
