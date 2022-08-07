---
title: 使用 Power BI 分析 Microsoft Teams 的 CQD 数据
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: 使用 Power BI 分析 Microsoft Teams 的 CQD 数据。
ms.openlocfilehash: 45dca06abc3ee2a8980c3b963e22fbc8646e15a4
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270697"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>使用 Power BI 分析 Microsoft Teams 的 CQD 数据

2022 年 7 月新增功能：新的体验质量 (QER) 模板已添加到 [用于 CQD 下载的 Power BI 查询模板](https://www.microsoft.com/download/details.aspx?id=102291)中。 QER 是一个强大的报告模板，可取代 2020 年发布的原始 CQD Power BI 查询模板。 虽然原始模板仍可用于演示目的，但不再支持它们，我们建议客户切换到将继续接收更新的 QER 模板。 请注意，这不适用于 CQD Teams 自动助理&呼叫队列历史报告。

对于调用质量仪表板 (Teams 中的 CQD) 报表，如果希望使用 Power BI 查询和报告数据，请下载 CQD Power BI 模板。 在 Power BI 中打开模板时，系统会提示你使用 CQD 管理员凭据登录。 可以自定义这些查询模板，并将其分发给组织中拥有 Power BI 许可证和 CQD 管理员权限的任何人。

在使用这些 PBIT 文件之前，需要使用 [下载](https://www.microsoft.com/download/details.aspx?id=102291)中包含的 *MicrosoftCallQuality.pqx* 文件 [安装适用于 Microsoft CQD 的 Power BI 连接器](CQD-Power-BI-connector.md)。 

确保具有正确的 [CQD 访问角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 来访问 Power BI 报表。 

|Pbit |说明 |
|:----------|:---------|
|<strong> (New！) </strong> QER.pbit     |  体验质量报告 (QER) 模板使客户能够在升级之前主动识别影响 Teams 会议和通话体验的问题。 还提供了报告，使管理员能够快速响应不断升级的问题，并帮助回答问题：“会议期间发生了什么？  此模板提供以下报告：</p><li>搜索 - 支持按会议 URL、会议 ID、子网或 UPN 进行搜索。</li><li>会议运行状况详细信息 – 单个会议的详细指标。</li><li>用户运行状况详细信息 - 单个用户的详细指标。</li><li>媒体运行状况 – 有关整个租户会议和通话运行状况的关键运行状况指标 (KHI) 的高级概述。</li><li>媒体设置 - 分析媒体设置失败。</li><li>媒体可靠性 – 分析媒体可靠性问题。</li><li>音频/视频/共享运行状况 - 查看音频、视频或共享运行状况的中级 KHI。</li><li>音频/视频/共享运行状况详细信息 - 查看有关音频、视频或共享运行状况的详细指标。</li><li>VPN - 查看 VPN 对会议运行状况的影响。  (估计或映射 VPN) </li><li>前 10 个报表 - 标识租户中的问题区域。</li><li>日报 - 查看 KHI 的每日报告。</li><li>使用情况 – 常规会议和通话使用情况。</li><li>用户反馈 - 查看用户调查反馈，也称为“速率我的呼叫”。</li><li>传输 - 标识阻止 UDP 的网络。</li><li>设备 - 查看设备的影响。</li><li>客户端 - 查看以客户端为中心的指标。</li><li>生成数据 - 查看 CQD 中的生成数据文件。</li><li>PSTN 运行状况和用户详细信息 - 两个报告，提供基于 PSTN 的调用的高级摘要以及单个用户运行状况。</li><li>网络指标 - 两个显示原始网络指标详细信息的报表，用于抖动、数据包丢失和延迟。</li> <br/> 此模板取代已弃用的模板，如下所示。|
|CQD Teams 自动助理&调用队列历史报表.pbit     |  此模板提供以下三个报表：</p><li>自动助理 - 显示针对进入自动助理的呼叫的分析。</li><li>呼叫队列 - 显示对进入呼叫队列的呼叫的分析。</li><li>代理时间线 - 显示代理在呼叫队列调用中处于活动状态的时间线视图。</li><br>若要了解详细信息，请阅读 [自动助理&呼叫队列历史报告](aa-cq-cqd-historical-reports.md)。 |
|CQD Teams 利用率报告.pbit     | 显示组织中的用户如何使用 Teams 以及使用多少。 请确保上传生成数据以最大化报告体验。 若要了解详细信息，请阅读 [使用 CQD Power BI 报表查看 Microsoft Teams 利用率](CQD-teams-utilization-report.md)。 |
|CQD PSTN 直接路由报表.pbit <br/> *(已弃用)*    | 提供特定于通过直接路由的 PSTN 调用的见解的示例模板。 若要了解详细信息，请阅读 [使用 CQD PSTN 直接路由报告](CQD-PSTN-report.md)。 |
|CQD Helpdesk Report.pbit <br/> *(已弃用)*     |此模板集成了生成和 EUII 数据，演示了如何生成报表，以便从单个用户中钻取，以查找该用户调用质量不佳的上游根本原因 (例如，用户位于) 遇到网络问题的建筑物中。 |
|CQD 位置增强型 Report.pbit <br/> *(已弃用)*     | 此示例模板重新想象 CQD SPD 位置报告。 包括 9 个报表，提供呼叫质量、生成 WiFi、可靠性和“我的呼叫速率” (RMC) 信息，以及通过生成或按用户进行的其他钻取。 请确保上传生成数据以最大化报告体验。 |
|CQD 移动设备报表.pbit <br/> *(已弃用)*     | 此示例模板提供专门针对移动设备用户优化的见解，包括通话质量、可靠性和“我的通话速率”。 查看 Android、iOS)  (移动网络、WiFi 网络和移动操作系统报表。 |
|CQD 摘要报表.pbit <br/> *(已弃用)*    | 演示 CQD 与 Power BI 如何提供更好的可视化效果、改进的演示文稿、增加的信息密度和滚动日期。 通过这些报表可以更轻松地标识离群值。 使用易于使用的交互式映射按位置钻取调用质量。 九个新报表：</p>- 整体质量<br>- 整体可靠性<br>- RMC (对我的呼叫进行总体) 评分<br>- 会议质量<br>- P2P 质量<br>- 会议可靠性<br>- P2P 可靠性<br>- 会议 RMC<br>- P2P RMC         |
|CQD 用户反馈 (将我的呼叫) Report.pbit 评分 <br/> *(已弃用)*    | 使用“速率我的呼叫”数据演示 Power BI 报表，你可以轻松地使用它来帮助支持对组织的呼叫。 使用逐字交叉引用以识别最终用户教育机会。 |

> [!TIP]
> 为 CQD 数据设置 Power BI 报表后，将其作为选项卡添加到通道。 在频道中选择 **+** 后，选择 **Power BI** ，然后找到报表。 若要了解详细信息，请使用 [适用于 Teams 的 Power BI 选项卡读取嵌入报表](/power-bi/service-embed-report-microsoft-teams)。 请记住，只有具有 Power BI 许可证和 CQD 管理员凭据的人员才能访问这些报表。

## <a name="related-topics"></a>相关主题

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](./monitor-call-quality-qos.md)
