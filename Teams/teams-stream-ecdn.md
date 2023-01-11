---
title: 在 Microsoft Teams 中缩放视频交付
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文将讨论规模视频交付和企业内容分发网络 (eCDN) Microsoft Teams 流式处理事件。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767917"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>将 eCDN 与 Microsoft Teams 配合使用，缩放视频交付并监视网络流量

播放来自 Microsoft Teams 的视频和“外部应用或设备”实时事件 (以前称为“外部编码器”制作) 使用自适应比特率流式处理 (ABR) 作为单播流传送。 这意味着每个观看者都从 Internet 获取自己的视频流。 对于发送到组织大部分部分的实时事件或视频，观看者可能会消耗大量的网络和 Internet 带宽。

组织可能希望了解并减少实时活动和热门视频的这种网络流量。 如果是这样，则可以使 Teams 与受信任的 Microsoft 合作伙伴集成，这些合作伙伴提供企业内容分发网络 (eCDN) 解决方案，其中包括自我管理交付技术、实时监视和深入网络分析。 这些 eCDN 平台使组织可以监视、缩放和优化 (视频流的分发，有时还会在整个企业网络中) 其他内容类型。

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>在 Teams 外部获取和设置 eCDN 解决方案

通过与受信任的 Microsoft eCDN 合作伙伴合作，获取有关监视和缩放视频交付的专家帮助。

在启用用于 Teams 的 eCDN 解决方案之前，必须在外部购买并设置该 eCDN 解决方案，并且独立于 Teams。 为确保解决方案满足你的需求，一些合作伙伴提供其内容交付和网络分析技术的免费试用版。

多个 eCDN 解决方案已预先集成，可以启用与 Teams 一起使用。 请参阅以下提供商提供的信息。

### <a name="hive-streaming"></a>Hive 流式处理

**Hive 流式处理视频体验平台** 包括三个核心产品：

- **Hive 视频优化** 基于仅获得专利的软件零配置算法。 优化可自动最大限度地提高整个组织的实时视频和点播视频 (VOD) 的质量和覆盖。
- **Hive 视频分析** 可帮助客户了解实时事件和点播视频性能的趋势，从而随着时间的推移提高观众参与度。 随着参与度提高，整个公司的视频采用率也随着提高。
- **Hive 视频操作** 提供强大的功能，旨在在直播视频活动之前和期间主动确保流式处理视频的成功。 操作工具使视频流式处理和 UC 团队能够在问题发生之前查找和更正问题。

所有这些都致力于创建从规划到执行和分析的全方位视频体验。 最大化流式传输视频通信的体验对于员工参与和实现公司使命的一致性至关重要。 若要了解详细信息，请查看 [此链接](https://www.hivestreaming.com/partners/microsoft)。

### <a name="kollective"></a>Kollective

**Kollective Technology** 是一个基于云的内容分发平台，它利用智能对等互连来传送实时和点播企业视频，在仅 1% 的带宽内提供 100% 的视频质量和 100% 的参与度。 Kollective 与 Teams Live Events 的集成使全球分散的员工能够轻松使用视频、改善员工沟通、提高整体参与度以及增加培训和留任机会。

**Kollective IQ** 是一个复杂、用户友好的分析平台，适用于Microsoft Stream。 借助可自定义的报告、可视化效果和仪表板，可以轻松地量化和消化复杂的全球企业网络的用户体验和参与度。 通信管理员和网络管理员可以监视实时事件和网络活动，以便快速解决瓶颈，确保网络性能达到峰值。

若要了解有关这些选项的详细信息，请查看 [此链接](https://kollective.com/microsoft-live-events/)。

### <a name="microsoft-ecdn"></a>Microsoft eCDN

**Microsoft eCDN** 解决了在大型企业虚拟活动（如全手会议）期间发生的网络拥塞问题。 Microsoft eCDN 通过 LAN 形成网状网络，将负载减少 95%，并消除网络问题。 Microsoft eCDN 是第一个使用 WebRTC 作为基础的 eCDN，这意味着无需安装软件或硬件。 财富 500 强客户可缓解网络问题，并信任 Peer5 举办其最大的公司活动。

- Microsoft eCDN 的零设置网络配置可确保远程工作者和/或大量视频流量不会使网络紧张，也不会迫使你投资昂贵的基础结构。 它包括自动站点检测、自动 VPN 检测和自动 NAT/防火墙遍历。 [有关详细信息，请参阅此链接](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant)。
- 使用 Microsoft eCDN 的静默测试允许 IT 管理员在其公司网络上模拟大型实时事件，从而允许在发生真实事件之前进行彻底且无中断的测试以及故障排除。 [有关详细信息，请参阅此链接](/ecdn/how-to/perform-silent-test)。
- Microsoft eCDN 的行业领先分析提供精细分析，使管理员能够快速找到任何流式处理问题的根本原因。 你的工具包包括交付和 UX 指标、高级向下钻取、每用户分析和后端 API。 [有关详细信息，请参阅此链接](/ecdn/technical-documentation/analytics)。

### <a name="ramp"></a>Ramp

当流式传输实时事件和点播视频时，**渐变 eCDN** 将网络带宽消耗减少 90% 或更多， (VOD) 。 使用 Ramp 混合和匹配 eCDN 技术的任意组合-多播、缓存和对等网络。 借助集中式管理、监视和见解分析，你可以获得对网络性能的可见性和控制，以创建最高质量的查看器体验。

- **渐变多播+** 是流式传输实时视频的最有效方式。 使用多播协议时，无论有 100、10，000 还是 10，000 个观看者，你只使用一个查看器所需的带宽。 [有关详细信息，请参阅此链接](https://www.rampecdn.com/altitudecdn/multicast/)。
- **Ramp OmniCache™** 是特定于视频的缓存软件，它使用本地缓存向附近的受众提供实时视频和 VOD 视频，大大减少了通过 Internet 连接和 WAN 链接传输的视频流的数量。 [有关详细信息，请参阅此链接](https://www.rampecdn.com/altitudecdn/video-cache/)。
- **使用渐变对等 (P2P)** ，即使在基础结构有限的位置，也可以优化带宽。 P2P 生成观看相同内容的客户端设备的对等网络，以将视频流从一个观看设备重新分发到另一个观看设备。 [有关详细信息，请参阅此链接](https://www.rampecdn.com/altitudecdn/p2p/)。

### <a name="riverbed"></a>Riverbed

**Riverbed** 是网络优化方面的行业标准，它已将其加速解决方案扩展到 Teams。 Microsoft 365 客户可以放心地加速 Microsoft 365 流量（包括 Teams），以及大量其他领先的企业 SaaS 服务，从任何地方提高员工工作效率。 可以通过轻松的设置启用 Teams 加速，该设置附带对 Riverbed 的世界级支持和持续投资的所有保证。 [有关详细信息，请参阅此链接](https://www.riverbed.com/office365)。

> [!NOTE]
> 所选的 eCDN 解决方案受所选合作伙伴 eCDN 提供商的服务条款和隐私策略的约束，后者将控制你对 eCDN 提供商解决方案的使用。 你使用 eCDN 提供商的解决方案不受 Microsoft 批量许可条款或在线服务条款的约束。 如果你不同意第三方提供商的条款，请不要在 Microsoft Teams 中启用 eCDN 解决方案。

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>为 eCDN 解决方案配置流编码器类型事件

购买并设置 eCDN 解决方案后，可以启用它以用于Microsoft Stream，包括通过 Microsoft Teams 或 Yammer 创建的流编码器实时事件。

1. 以 Microsoft 365 全局管理员或 Teams 管理员身份打开 Teams 管理中心，并导航到 [实时事件设置](https://admin.teams.microsoft.com/broadcasts/settings) 页。
1. 将 **视频分发提供程序** 切换为 **“打开**”。
1. 从 **视频分发** 提供程序下拉列表中选择 **eCDN/SDN** 提供程序。
1. 按照解决方案提供商的指示填写其他字段 (并非所有字段都由) 的所有解决方案提供商使用。
1. 选择“**保存**”。
1. 若要检查设置是否正确，请选择“ **验证设置**”。
    - 搜索组织中要验证的任何视频。
    - 如果 eCDN 提供程序设置正确，则会在验证设置工具上看到 **“成功”** 消息。
    - 如果未正确设置，将看到 **“失败”** 消息。 复制事件消息以与提供商共享，以便进行故障排除。

为 eCDN 解决方案配置 Teams 后，Teams 中播放的任何视频或实时事件都会自动利用该解决方案。

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>通过 Teams 和 Yammer 为 eCDN 解决方案配置 Teams 生产类型事件

如果计划通过 Teams 或 Yammer 创建 Teams 实时事件，则需要 [将 eCDN 提供程序配置为与 Microsoft Teams 集成](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) 。

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>获取 eCDN 解决方案的视频分析报告

如上所述，某些 eCDN 解决方案还提供分析报告，提供有关播放会话、查看器和服务质量的更深入信息。 如果你的提供商在 Teams 管理中心设置提供程序时提供了要配置的分析报告 URL 模板，则视频或事件的所有者可以轻松访问特定视频或事件的分析报告。

视频的所有者将直接在视频下看到“分析”选项卡。 在此选项卡上，将有一个链接供所有者访问 eCDN 提供程序系统中此特定视频的分析报告。

如果你是 Teams 管理员，也可以提升访问权限以查看“分析”选项卡并访问 eCDN 分析报告链接，即使你不是直播活动或视频的所有者也是如此。

1. 作为 Teams 管理员，请转到视频播放器页面。
1. 选择“**设置**”。
1. 选择“ **在管理模式下查看**”。
1. 选择“ **分析** ”选项卡。

## <a name="troubleshooting-issues"></a>排查问题

请确保在网络中正确设置了 eCDN 解决方案，并且已根据说明和特定配置字符串正确配置 Teams 以启用提供程序。 如果仍然遇到问题，下面的一些信息可能会有所帮助。

### <a name="verify-setup-tool"></a>验证设置工具

如果 eCDN 解决方案出现问题，可以随时返回并运行 **验证安装** 工具。 为测试视频显示的 eCDN 提供程序事件消息可以为你和 eCDN 提供程序提供有关哪些操作不起作用的详细信息。

- 转到 **设置** > **管理员设置** > **eCDN 提供程序** > **验证设置**

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>通过 URL 查询字符串为特定会话禁用 eCDN

若要确定你看到的问题是 eCDN 解决方案还是 Teams，可以通过查询字符串轻松禁用特定播放会话的 eCDN 解决方案。

- 如果播放 URL 中已有问号 **？**，则添加 **&disableSDN=true**。
- 如果播放 URL 没有问号 **，请在** 其中添加 **？disableSDN=true**。

### <a name="view-ecdn-info-in-browser-console"></a>在浏览器控制台中查看 eCDN 信息

如果 eCDN 解决方案提供商支持它，则他们可以通过其解决方案在播放初始化期间打印调试信息。 此额外信息可能有助于确定出了什么问题。 可以通过查询字符串启用额外的控制台调试消息。

- 如果播放 URL 中已有问号 **？**，则添加 **&isSDNDebug=true**。
- 如果播放 URL 没有问号 **，请在** 其中添加 **？isSDNDebug=true**。

当浏览器处于活动状态时，在键盘上选择 **F12** ，并切换到“ **控制台** ”选项卡，查看加载页面期间打印的所有信息，并在播放 URL 上设置了 isSDNDebug=true 查询字符串。
