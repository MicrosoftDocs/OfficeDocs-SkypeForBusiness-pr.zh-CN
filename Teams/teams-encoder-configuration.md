---
title: Microsoft Teams 中流式传输的编码器配置
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
description: 本文将讨论 Microsoft Teams 流式处理事件的基于编码器的 RTMP 配置。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767927"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>在 Microsoft Teams 中为实时事件流式传输配置编码器

Teams 接受来自输出 RTMP 或 RTMPS 的各种不同编码器的实时源。 每个编码器都不同，因此在发送到 Teams 时，请务必遵循编码器配置的准则。

若要了解如何在 Teams 中设置实时事件，请阅读创建实时事件。 如果已使用与 Teams 集成的编码器，请阅读 [为实时流式传输配置编码器](teams-encoder-setup.md)。

## <a name="configuration-steps"></a>配置步骤

使用 Teams 或 Yammer 安排直播活动，并选择 **“Teams 编码器** ”选项后，你将能够从会议邀请中检索 RTMP URL 和密钥，并使用它们将源发送到 Teams 制作者 UI。

### <a name="gather-the-rtmp-information"></a>收集 RTMP 信息

#### <a name="scheduled-in-teams"></a>在 Teams 中计划

1. 打开 Teams 客户端并导航到 **“日历**”。
1. 选择计划的直播活动，然后选择双箭头按钮以查看邀请详细信息。
1. 转到 **“RTMP 详细信息** ”部分。
1. 选择“ **获取 RTMP”** 链接，将 RTMP 引入 URL 复制到剪贴板。
1. 选择“ **获取 RTMP 密钥** ”，将 RTMP 密钥复制到剪贴板。

#### <a name="scheduled-in-yammer"></a>在 Yammer 中计划

1. 导航到已安排活动的 Yammer 社区。
1. 选择“ **事件** ”选项卡以查看即将发生的计划事件。
1. 选择所需的事件以显示详细信息页。
1. 在右侧的 **“生成**”下，选择 **RTMP 信息** 链接以公开 RTMP URL 和密钥。

## <a name="encoder-setup"></a>编码器设置

1. 收集 RTMP 信息后，请确保根据以下建议的编码器设置配置了正确的编码器设置。
1. 在编码器的流式处理设置中输入 RTMP URL 和密钥 (有关具体) 的详细信息，请参阅制造商的文档。
1. 使用所需的音频和视频源配置编码器。
1. 打开 Teams 客户端，以生成者身份加入实时通风口。
1. 开始从编码器流式传输到 Teams RTMP 引入 URL。
1. 在 Teams 生成者窗口中，几秒钟后，编码器的 RTMP 源将显示在演示者区域中。
1. 单击演示者区域中的 RTMP 源，将其放入左侧的队列中。
1. 对源感到满意后，选择“ **实时发送** ”，该源随后也会显示在“生成者”窗口的右侧。
1. 选择“ **开始** ”以开始流。

## <a name="recommended-encoder-settings"></a>建议的编码器设置

### <a name="ingest-protocols"></a>引入协议

- 单比特率 RTMPS 或 RTMP

### <a name="video-format"></a>视频格式

- 编解码器：H.264
- 配置文件：高 (级别 4.0) 
- 比特率：高达 5 Mbps (5000 kbps) 
- 严格常量比特率 (CBR) 
- 关键帧/GOP：2 秒
  - 每个 GOP 的开头必须有一个 IDR 帧
  - 帧速率：29.97 fps 或 30 fps
  - 分辨率：1280 x 720 (720P) 
  - 交错模式：渐进式

### <a name="audio-format"></a>音频格式

- 编解码器：AAC (LC) 
- 比特率：192 kbps
- 采样率：48 kHz 或 44.1 kHz (推荐 48 kHz) 

### <a name="playback-requirements"></a>播放要求

- 必须同时存在音频和视频流才能在 Teams 中播放内容。

### <a name="configuration-tips"></a>配置提示

- 请尽可能使用硬连线 Internet 连接。
- 确定带宽要求时，将流式处理比特率加倍。 虽然这不是强制性要求，但它将有助于缓解网络拥塞的影响。
- 使用基于软件的编码器时，请关闭任何不必要的程序。
- 开始推送编码器配置后，请勿更改编码器配置。 它对事件有负面影响，并可能导致事件不稳定。 如果要在事件开始之前执行此操作，则必须使用 Teams 中的生成者控件断开连接，然后重新开始设置。
- 如果在实时事件期间编码器断开连接，请重新连接编码器，使其保持与继续进程相同的时间戳。 任何不连续都可能导致某些浏览器和设备上的音频或视频问题。
- 给自己充足的时间来设置活动。 对于大规模事件，建议在活动前一小时开始设置。
