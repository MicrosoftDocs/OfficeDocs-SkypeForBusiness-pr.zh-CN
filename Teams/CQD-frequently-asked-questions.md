---
title: 通话质量仪表板（CQD）常见问题（FAQ）
ms.author: lolaj
author: LolaJacobsen
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
description: 阅读常见问题（FAQ）和有关 Microsoft 团队通话质量仪表板（CQD）的解答。
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086168"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通话质量仪表板（CQD）常见问题（FAQ）

## <a name="frequently-asked-questions"></a>常见问题解答

[如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[为什么在度量值和用户计数值上看到最多0.2% 的差异以及如何获取最准确的卷？](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[为什么 Skype for Business 中的 CQD 数据与来自团队的 CQD 数据不同？](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[为什么我在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？

查看[流分类](stream-classification-in-call-quality-dashboard.md)CQD 使用的规则。
 
对于音频流，任何5个分类器（根据调用的平均长度计算）都可能位于 "良好" 参数中。 这并不意味着用户不会遇到对音频的丢弃、静态或故障的内容。 

若要确定是否是网络问题，请查看会话平均值与最大值之间的增量。 最大值是会话期间检测和报告的最大值。
 
下面是如何解决这种情况的示例。 假设你在呼叫过程中获取网络跟踪，并且前20分钟，没有丢失数据包，但你的数据包的间隔为1.5 秒，然后就可以在通话的其余部分中使用。 平均 <10% （0.1）数据包丢失，即使在 Wireshark 跟踪 RTP 分析中也是如此。 最大数据包丢失程度是多少？ 5秒内的1.5 秒将是30% （0.3）。 在五秒的采样周期内发生（也许还是可以在采样周期内拆分）？
 
如果网络指标在平均值和最大值中看起来很好，请查看其他遥测数据： 
- 检查 CPU 的事件比率不足，查看检测到的 CPU 资源是否不足，导致质量较差。 
- 音频设备是否处于半双工模式下，以防止因麦克风接近扬声器而导致的反馈？ 
- 检查 Device 半双工 AEC 事件比率。 当插入集线器或坞站时，设备 glitching 或麦克风 glitching 引入噪音或静态信号的原因如下：  
- 检查设备故障和麦克风故障事件比率。 设备本身是否正常工作？  
- 检查捕获和呈现设备无法正常工作的事件比率。


有关 CQD 遥测中可用的维度和度量值的详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

对于背景噪音，请选中 "静音事件比率" 以查看参与者静音的时间长度。
 
在 CQD 中创建详细报表，并筛选会议 ID 以查看会议中的所有用户和流并添加感兴趣的字段。 报告问题的用户可能不是遇到该问题的用户。 他们只是报告体验。
 
遥测不一定会解决该问题，但它可以帮助您更好地了解在何处查看和通知您的决策。 是网络、设备、驱动程序还是固件更新、使用或用户？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>为什么在度量值和用户计数值上看到最多0.2% 的差异以及如何获取最准确的卷？ 
若要计算 "呼叫计数" 和 "用户计数" 度量值，请对数据集中的调用或用户标识符执行不同的 countif 操作。 在大型数据集上，具有不同的 countif 操作固有的最大0.2% 错误。 对于最准确的卷，你应该依赖流计数度量值，因为它们不依赖于此不同的 countif 操作。 筛选以减少数据量可能会减少错误，但可能无法在不同的调用和用户计数中消除此错误来源。 请参阅["呼叫质量" 仪表板中可用的尺寸和测量](dimensions-and-measures-available-in-call-quality-dashboard.md)值，这些测量受影响。

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？ 

如果你看到 CQD v2 和 v3 之间的数据差异，请确保在 "苹果" 和 "窄" 级别（而不是聚合级别）上执行数据比较或验证。 例如，如果你筛选 MSIT "建筑物 30" WiFi 团队桌面客户端数据的两个报表，则 v2 和 v3 的低质量百分比应该相同。

CallSetup 失败的 CQDv2 分类仅考虑 "音频" 模态，在 CQDv3 中，对每个模态（音频、视频和应用共享）进行分类，并在各自的模态流中表示。 

对于团队，CQDv2 将相同的用户反馈应用到所有形式 CQDv3 应用针对团队的模态的反馈基础。

CQD V3 包括 
1. Skype for Business Server 2019 通话， 
2. Skype 机器人呼叫，例如：自动助理、呼叫队列、会议通知服务 
3. 虚拟桌面界面，
4. 会议视频互操作，
3. 实时事件发布者和演示者通话，以及 
4. PSTN 呼叫。 

若要了解如何使用这些 Power BI 模板分析和报告你的 CQD 数据，请参阅[使用 POWER BI FOR CQD 报表](cqd-power-bi-query-templates.md)。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>为什么 Skype for Business 中的 CQD 数据与来自团队的 CQD 数据不同？ 


> [!IMPORTANT]
> 从2020年7月1日起，较早的 CQD 访问最新 CQD 中的数据。 较旧的 CQD 数据不再可用，并且您不能导出您的建筑物或报表数据。


如果您尝试比较旧 CQD 之间的数据与 Skype for Business 旧式门户（cqd.lync.com）和团队管理中心（cqd.teams.microsoft.com）中的最新 CQD，您将很快发现数据不匹配。 这是因为最新的 CQD 报告了许多额外的通话方案。 如果您仍在使用来自较旧 CQD 的报表，请使用本文帮助解释这些报表： " [Skype for business" 服务器的 "呼叫质量" 仪表板](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)。



下面是一个应用特定筛选器以比较 CQD v2 和 CQD v3 数据的示例：

1. QoE 记录可用 = True

2. Add 是服务器对筛选器，其值：客户端：客户端和客户端：服务器。 大多数租户更喜欢排除服务器：服务器调用。

3. 为用户代理类别添加筛选器并筛选出自动助理、呼叫队列、Bot、房间系统、MediationServer、会议公告服务、VDI 等。

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="在 CQD v3 中应用特定筛选器的屏幕截图":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="在 CQD v2 中应用特定筛选器的屏幕截图":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>CQD v2 和 CQD v3 之间的其他预期差异

若要了解有关旧的和最新 CQD 之间的差异的详细信息，请阅读2019年11月5日的 "[高级通话质量" 仪表板博客简介](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586)。


> [!IMPORTANT]
> 从2020年7月1日起，较早的 CQD 访问最新 CQD 中的数据。 较旧的 CQD 数据不再可用，并且您不能导出您的建筑物或报表数据。

在 "聚合" 或 "摘要" 级别上，您可能会看到您的旧的和较新的 CQD 报表之间有更多数据差异 如果比较粒度级别的数据，将获得 "横向到横向" 比较。 例如，如果你要查看单个建筑物的数据，则较旧的 CQD 报表的质量不佳的百分比应该是相同的。

- 选择具有紧密焦点的方案，如企业有线连接、Windows 桌面或单个区域或建筑物。
- 检查团队 MR、TR 或 MP IP 范围。 团队范围比 Skype for business Online 更新，这可能会导致与防火墙的连接问题。
- 不要比较汇总或顶级数字。 这些比较将使你能够将企业有线连接上的 Skype for business Online 通话的大型通话量与 LTE 或专用网络上的一小大量团队通话进行比较。
- 注意位置偏向和人口差异：有许多比较过于不同的比较非常有用：
  - NOAM： APAC
  - 纽约州： Goa
  - 有线 : wifi
  - 公司网络：家庭网络
  
### <a name="why-cant-i-see-euii-in-cqd"></a>为什么我在 CQD 中看不到 EUII？

这些管理员角色可以访问 CQD，但不能查看 EUII （最终用户身份信息）：
- Microsoft 365 报表读者
- 团队沟通支持专家

若要了解有关可访问 CQD 的角色的详细信息-包括 EUII-读取[分配角色以访问 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？

当仅在 CQD 报表（isTeams = 1）中筛选团队时，将筛选*第一个终结点*为团队的所有调用。 如果*第二个终结点*是 Skype for business，则该信息将显示在您的 CQD 报告中。

CQDv2 和 CQDv3 将始终具有不同的总数，因为 CQDv3 将具有 CQDv2 没有的新方案。 这就是比较 "摘要总数" 或 "不带筛选器的聚合的所有数字" 的原因将具有这些预期的差异。  

根据客户的情形，CQDv3 将包括 SFB 2019 本地呼叫（如果 SFB 2019 与数据连接器一起使用）、Skype 机器人呼叫（AA、CVI、VDI）、实时事件和 PSTN 呼叫。 适用于客户的方案/功能，但其数据不在 CQD V2 中。

例如，预计你的客户和你将看到200000音频流，并且 CQD V2 摘要报告中出现5000故障。300000音频流与5500故障的对比2019（来自 CQD V3 中的本地呼叫、CVI 呼叫、PSTN 呼叫等）。

为了确定是否存在任何意外的差异，您必须查看整个数据的各种细目。  与意向进行比较。  按用户代理类别对数据进行切片是我们建议的第一项。  *第一种产品*和*第二种产品*也是良好的切片器。  


## <a name="related-topics"></a>相关主题

[改善和监控团队的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)

[上载租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报告](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)