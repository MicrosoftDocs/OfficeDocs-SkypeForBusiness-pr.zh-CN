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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 阅读常见问题解答 (常见问题) 和有关 CQD Microsoft Teams呼叫质量 (的) 。
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718003"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>呼叫质量仪表板 (CQD) 常见问题解答 (常见问题) 

## <a name="frequently-asked-questions"></a>常见问题解答

[如果一个或多个会议参与者体验不佳，CQD 为何将通话标记为"良好"？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[为什么在度量值上，调用和用户计数值的差异最大为 0.2%，如何获取最准确的音量？ ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[为什么来自 Skype for Business 的 CQD 数据与来自 Teams 的 CQD 数据？](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[为什么我在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[为什么在仅Skype for Business筛选后，CQD 中Teams信息？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[为什么我的自定义报表最多只返回 10，000 行，当我知道应该有更多的条目时？](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[为什么 WiFi VPN 连接显示为"有线"而不是"WiFi"？](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一个或多个会议参与者体验不佳，CQD 为何将通话标记为"良好"？

查看 CQD 用于流分类 [的规则](stream-classification-in-call-quality-dashboard.md)。
 
对于音频流，根据调用长度计算平均值的五个分类器中的任意一个都可能是"良好"参数。 这并不意味着用户未遇到导致音频掉线、静态或故障的问题。 

若要确定它是网络问题，请看会话的平均值与最大值之间的增量。 最大值是会话期间检测到并报告的最大值。
 
下面是如何排查这种情况的示例。 假设你在调用期间进行网络跟踪，并且前 20 分钟没有丢失数据包，但随后你有 1.5 秒数据包的间隙，然后适合通话的其余部分。 即使在 Wireshark 跟踪 RTP 分析 (，平均丢包率<10%) 0.1。 最大数据包丢失是什么？ 5 秒的 1.5 秒为 0.3 (30%) 。 这是在 5 秒采样期内发生的 (，还是可以在采样期间拆分) ？
 
如果网络指标在平均值和最大值中看起来不错，则查看其他遥测数据： 
- 检查"CPU 不足事件比率"，查看检测到的可用 CPU 资源是否不足，导致质量差。 
- 音频设备是否由于麦克风接近扬声器而以半双工模式阻止反馈？ 
- 检查设备半双工 AEC 事件比率。 插入集线器或扩展坞时，设备故障或麦克风故障是否由于 USB 音频输出而引入噪音或静态？  
- 检查"设备故障"和"麦克风故障"事件比率。 设备本身是否正常运行？  
- 检查捕获和呈现设备无法正常工作的事件比率。


有关 CQD 遥测中可用的维度和度量的更多内容，请阅读呼叫质量仪表板中提供的维度 [和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

对于背景噪音，请检查静音事件比率以查看参与者静音的时间长度。
 
在 CQD 中创建详细报表，并筛选会议 ID，查看会议中的所有用户和流，并添加您感兴趣的字段。 报告该问题的用户可能不是遇到该问题的用户。 他们只是报告体验。
 
遥测数据不一定会指出问题，但可以帮助你更好地了解在何处查找和通知你的决策。 是网络、设备、驱动程序或固件更新、使用情况还是用户？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>为什么在度量值上，调用和用户计数值的差异最大为 0.2%，如何获取最准确的音量？ 
若要计算调用计数和用户计数度量值，请对数据集中的调用或用户标识符执行不同的 countif 操作。 在大型数据集上，非重复 countif 操作本身存在最多 0.2% 的错误。 对于最准确的卷，应依赖于流计数度量值，因为它们不依赖于此不同的 countif 操作。 减少数据量的筛选可以减少错误，但可能无法消除不同调用和用户计数中的此错误源。 请参阅 [呼叫质量仪表板](dimensions-and-measures-available-in-call-quality-dashboard.md) 中提供的维度和度量，这些度量值会受到影响。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>为什么来自 Skype for Business 的 CQD 数据与来自 Teams 的 CQD 数据？ 


> [!IMPORTANT]
> 从 2020 年 7 月 1 日开始，较旧的 CQD (CQD.lync.com) 使用来自最新 CQD (CQD 的数据。Teams.microsoft.com) 。 旧 CQD 数据不再可用，并且无法导出建筑物或报表数据。 你仍然可以使用 CQD.lync.com (管理中心Skype for Business的) ，但我们将很快关闭对 CQD.lync.com 的访问权限，因此应移动到 CQD。Teams.microsoft.com，如果尚未这样做。


如果尝试比较 Skype for Business 旧门户 (cqd.lync.com) 中较旧的 CQD 与 Teams 管理中心 (cqd.teams.microsoft.com) 的最新 CQD 之间的数据，则很快就会注意到数据不匹配。 这是因为最新的 CQD 报告有关许多其他调用方案。 如果仍在使用来自较旧 CQD 的报告，请使用本文来帮助解释这些报告：呼叫质量仪表板[Skype for Business Server。](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>为什么我在 CQD 中看不到 EUII？

这些管理员角色可以访问 CQD，但无法查看 EUII (最终用户可识别信息) ：
- Microsoft 365报表读者
- Teams通信支持专家

若要详细了解可以访问 CQD 的角色（包括 EUII），请阅读 [分配用于访问 CQD 的角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>为什么在仅Skype for Business筛选后，CQD 中Teams信息？

仅在 Teams isTeams = 1 (的 CQD 报告中筛选) 筛选第一终结点为第一终结点的所有Teams。  如果 *第二终结点* Skype for Business，该信息会显示在 CQD 报告中。

CQDv2 和 CQDv3 始终具有不同的总计计数，因为 CQDv3 将具有 CQDv2 不会具有的新方案。 正因如此，比较"汇总总计"或"聚合全部数字"（没有筛选器）将具有这些预期差异的原因。  

如果 SFB 2019 与数据连接器) 一起使用，则 CQDv3 将包括 SFB 2019 本地呼叫 (、Skype 机器人呼叫 (AA、CVI、VDI) 、实时事件和 PSTN 呼叫。 客户可用的方案/功能，但其数据不在 CQD V2 中。

例如，预期客户和你将看到 200，000 个音频流，CQD V2 摘要报告中有 5000 个失败;与 300，000 个音频流相比，5500 次失败 (来自 CQD V3 中的 2019 个就地呼叫、CVI 呼叫、PSTN 呼叫等 ) 。

若要确定如果存在任何意外的差异，则必须查看总体数据的各种细分。  与意向进行比较。  按用户代理类别对切片数据是建议的第一项操作之一。  *第一* 个 *产品和第二* 个产品也是很好的切片器。  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>为什么我的自定义报表最多只返回 10，000 行，当我知道应该有更多的条目时？

CQD 设计用于汇总数据查询，不用于数据导出。 我们建议尽可能重建报表，以防止超过 10，000 行的限制。 首先，使用更大、基数较低的维度（如月、年、日期、区域、国家/地区等）查看 KPI。从该维度中，可以向下钻取到基数越高的维度。 支持人员报表Location-Enhanced报表都提供了此向下钻取工作流的良好示例。

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a>为什么 WiFi VPN 连接显示为"有线"而不是"WiFi"？

这是正常情况。 VPN 供应商创建了一个虚拟以太网适配器，该适配器被视为有线连接。 由于未正确标记，操作系统不知道它是 WiFi 连接，并报告为有线连接。

## <a name="related-topics"></a>相关主题

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
