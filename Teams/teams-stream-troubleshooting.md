---
title: Microsoft Teams 中的实时流式处理疑难解答
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
description: 本文将讨论 Microsoft Teams 流式处理事件的故障排除选项。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767932"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Microsoft Teams 中的实时事件疑难解答

> [!IMPORTANT]
> **中国**：位于中国的用户将无法设置或参加 Teams 或 Yammer 直播活动或观看点播视频，因为目前，这些应用所依赖的 Azure CDN 在中国可能无法访问。
>
> 作为管理员，你可能需要设置 VPN 来连接公司网络，以便这些应用无缝工作。 完成后，组织中的人员可以安排和参加实时事件。

## <a name="before-a-live-event"></a>直播活动前

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>确保所有事件都可以在网络中访问

#### <a name="general-teams-endpoints"></a>常规 Teams 终结点

Teams 需要连接到 Internet。 [Office 365 Teams 终结点](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)中列出的所有终结点都需要可供组织网络中的 Teams 用户访问。

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Teams 编码器实时事件 - RMTP 引入终结点

若要获取从编码器发送到 Teams 的 Teams 编码器实时事件的视频源，需要在网络的防火墙中打开域名和端口：

- 域：*.rtmpingest.mcr.teams.microsoft.com
- 端口：用于 RTMP/RTMPS) 的 1935/1936 (

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>确保有足够的上传带宽

通过 RTMP 生成或流式传输实时事件时，推送实时流的站点上的 Internet 上传带宽可能不够。 低上传带宽可能会导致帧丢失或实时视频本身出现问题，这可能会导致观看者出现播放问题。

确保推送实时流的计算机和网络的上传速度高于为实时流设置的比特率。 如果从编码器输出 5 Mbps 的流，但上传比特率接近或低于该流，则可能无法足够快地上传流，可能会遇到问题。

如果存在上传带宽问题，可以尝试以下几项操作：

1. 对从中推送流的任何计算机使用硬有线以太网连接，以避免 WiFi 中的任何中断。
1. 将实时源的编码比特率降低到远低于最大上传速度的值。

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>为多个并发查看者准备网络

在直播活动期间，许多人将加入观看直播活动。 这可能会给网络和 Internet 下载带宽带来压力。 需要评估当前的网络基础结构，并确保企业网络中的人员具有观看直播活动所需的带宽。 为了帮助减少直播活动所需的 Internet 流量，有两个选项：

1. 配置网络中的现有缓存代理，以缓存 Teams 中的视频。
1. 使用第三方 eCDN 视频传送解决方案来优化视频流量。

### <a name="i-cant-create-a-live-event"></a>我无法创建直播活动

Microsoft Teams 和 Yammer 中存在权限，用户需要能够创建实时事件，具体取决于你用于直播活动的服务。

1. 检查 Teams 管理员是否允许你创建实时事件。
1. 请向管理员确认你拥有允许创建实时事件的有效 Teams 许可证。

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>确保观看者有权观看活动

Microsoft Teams 实时事件在活动本身 (组织者、制作者、演示者、与会者) 具有一些不同的权限角色。

有关详细信息，请参阅 [Microsoft Teams 事件组角色](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) 。

## <a name="producing-a-live-event"></a>制作直播活动

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>我不知道如何设置编码器

最简单的入门方法是按照 [在 Microsoft Teams 中使用编码器进行实时流式处理](teams-encoder-setup.md) 一文中概述的说明进行操作。

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>我的编码器未连接到服务器引入 URL

- 检查 RTMP URL 是否正确输入为编码器的输出。
- 检查是否已正确输入 RTMP 密钥作为编码器的输出。
- 检查 Internet 连接的状态，确保编码器已正确连接并联机。
- 你可能具有可能阻止连接的输出的网络安全性或防火墙相关设置。
- Teams 可能不支持你的编码器。 在 [Microsoft Teams 中使用编码器进行实时流式传输](teams-encoder-setup.md)中查看经过测试的编码器列表。

### <a name="i-cant-get-rtmps-to-work"></a>我无法让 RTMP 正常工作

- 某些编码器可能支持 Teams 不支持的其他实现。 在 [Microsoft Teams 中使用编码器进行实时流式处理](teams-encoder-setup.md)中查看与 Teams 配合使用的经过测试的编码器列表。
- 并非所有编码器或版本都支持 RTMP。 请咨询制造商或软件创建者，了解他们支持的内容。

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>我尝试开始设置，这需要很长时间

通常，可能需要几分钟才能开始设置，然后才能开始推送编码器。 如果服务很忙，可能需要更长的时间才能开始，因此建议在安排的实时活动之前给自己足够的时间开始设置。

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>我尝试开始设置，但发生了太多事件

如果在启动已达到最大事件数的事件时收到消息，请联系 Teams 管理员，该管理员能够停止其他事件，为更高的优先级事件腾出空间。

### <a name="i-cant-see-producer-view"></a>我看不到制作者视图

1. 从编码器开始流式传输后，制作者预览可能需要几秒钟才能显示。
1. 确保编码器已连接到 Teams。
1. 有时，刷新 Teams 中的页面会有所帮助。 系统可能会询问你是否要离开页面;这不会影响直播活动。
1. 某些网络可能会阻止访问内容。 确保网络安全和防火墙设置允许 RTMP 协议，并且 [所需的域](/microsoft-365/enterprise/urls-and-ip-address-ranges) 在允许列表中。 它可以帮助尝试查看它是否适用于不同的网络环境，独立于公司网络、VPN 或锁定的网络。

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>我的饲料看起来不好，质量差，或有故障

1. 从推送实时流的计算机检查上传带宽。 低带宽可能会导致帧丢失、质量不佳或视频流出现故障。 需要高于流式传输的比特率的上传带宽。
1. 请确保使用 Teams 的建议编码器设置。 有关详细信息 [，请参阅在 Microsoft Teams 中手动配置实时事件流式处理编码器](teams-encoder-configuration.md) 。
1. 检查进入编码器的音频/视频是否没有任何问题。 路由到编码器的源音频或视频源本身可能有问题，这会导致向观众发送糟糕的体验。
1. 检查编码器上的 CPU 负载。 你可能使用源内容和/或尝试推送的比特率来最大化 CPU。 如果 CPU 负载过高，请尝试降低实时源覆盖/内容的复杂性，或降低你正在流式传输的比特率。
1. 确保编码器是最新的。 如果是硬件编码器，请确保具有最新的固件更新。 如果是软件编码器，请确保运行最新版本。
1. 尝试重置或重启编码器。 请注意，如果在实时流中执行此操作，观看者将在编码器重启时在播放时看到错误。 从编码器重启实时流式传输后，观看者必须重新加载页面才能再次获取实时流。

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>我从编码器结束了直播活动，但观看者看到错误

在断开编码器连接之前，选择“ **停止事件** ”。 如果已断开编码器连接，仍可以选择“ **停止事件**”，但观看者可能会看到错误。

### <a name="my-viewers-are-seeing-issues"></a>我的查看者看到了问题

- 如果单个查看者报告了问题，请确保查看者有足够的带宽，并且连接到良好的 Internet 来观看事件。
- 如果同一网络中有多个人员出现问题，则可能遇到与网络拥塞相关的问题。 查看 [将 eCDN 与 Microsoft Teams 配合使用来缩放视频交付并监视网络流量](teams-stream-ecdn.md) ，以查看是否可以确定问题的解决方案。
- 很多时候，当多个查看者看到问题时，它实际上与编码器源相关。
  - 检查编码器是否已正确设置为编码器设置中概述的规范，并正确配置。
  - 确保有足够的上传带宽进行流式传输。 可以尝试减少编码器输出的带宽。
  - 有时重置编码器会有所帮助，但请注意，重新连接时必须保持相同的设置。 受众成员可能会在直播活动中看到错误或故障。

### <a name="i-or-my-viewers-cant-hear-the-video"></a>我或我的观众听不到视频

1. 检查编码器是否正在发送音频。
1. 检查音频设备是否已接通电源。
1. 如果在 Windows 上，请确保选择并取消静音正确的音频设备。
1. 如果编码器中断，某些浏览器或设备可能无法正确恢复和播放音频。

> [!NOTE]
> 如果已将 Microsoft eCDN 部署为实时事件的视频分发提供商，请参阅 [排查 eCDN 性能问题](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) ，详细了解如何排查可能遇到的 eCDN 性能问题。
