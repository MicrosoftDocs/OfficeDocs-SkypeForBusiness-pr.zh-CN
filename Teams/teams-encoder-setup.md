---
title: Microsoft Teams 中用于流式传输的编码器设置
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
description: 本文将讨论 Microsoft Teams 流式处理事件的基于编码器的 RTMP 设置。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767928"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>在 Microsoft Teams 中使用编码器进行实时流式处理

Teams 编码器允许用户使用 Microsoft Teams 直接从外部硬件或基于软件的编码器生成实时事件。

## <a name="overview"></a>概述

编码器从实时事件中使用的各种源（如相机、麦克风、桌面屏幕捕获等）获取音频和视频内容。 它将媒体压缩并转换为合适的数字格式，然后将其发送到 Teams，以便向受众实时传送视频流。 请参阅 [我们的自定义生产 playbook](https://aka.ms/CustomProductionVEP) ，详细了解如何将 Teams 生产技术 (（例如 NDI) ）与外部编码器配合使用。

## <a name="production-workflow-when-using-an-encoder"></a>使用编码器时的生产工作流

生成 Teams 实时事件的工作流如下所示：

在 Teams 或 Yammer 中安排直播活动，并且已选择 **Teams 编码器** 选项。 这会预配 RTMP 终结点，该终结点随 RTMP (S) URL 和相应的密钥一起提供。 编码器使用 URL 和密钥连接到计划的实时事件的 RTMP 终结点。

### <a name="common-encoders-user-with-live-events"></a>具有实时事件的常见编码器用户

Microsoft 测试了以下两个列表中的编码器，以便使用 Teams 进行实时流式处理。 第一个列表是这些编码器的子集，这些编码器已经过产品测试，以便于使用和快速设置。

#### <a name="stream-ready-encoders"></a>流就绪编码器

|编码                                |网站  |详细信息  |
|---------------------------------------|---------|---------|
|Haivision                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |使用 Haivision Hub 提供高质量的高清视频，这是 RTMP 的强大替代方案。 |
|Haivision                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |H.264 和 HEV 视频编码器提供高达 4K 分辨率的高质量 ABR 视频级联。 |
|打开广播公司软件 (OBS Studio)  |[Open Broadcaster Software](https://obsproject.com/) |高性能实时视频/音频捕获和混合 - 支持所有流式处理平台等。 |
|vMix                                   |[vMix](https://www.vmix.com/) |控制相机、视频、音频等的录制、混合和实时流式传输的软件视觉混音器。 |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |涵盖所有基础知识和多相机制作的网络广播软件。 |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |将多台 Apple 设备与一台或多台相机同步，以便实时捕获和编辑视频。 |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |实时视频和音频录制，用于实时流式传输到连接 Internet 的设备 |
|XSplit Broadcaster                     |[XSplit Broadcaster](https://www.xsplit.com/) |生成、混合和提供丰富的视频内容，包括实时流式传输的游戏玩法。 |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |用于处理视频、音频和其他多媒体文件和实时流的开源软件套件。 |
|生产卡车          |[生产卡车](https://www.blueframetech.com/productiontruck) |从移动面包车或卡车拍摄和流式传输现场事件。 |
|Live Arena AI 制作者                 |AI 生成者 |作为会议应用集成到 Microsoft Teams 中的生产工作室。|
|StreamYard                             |StreamYard |浏览器中的实时流式处理工作室。|
|Socialive                              |Socialive |云视频制作平台，提供一体式体验，用于制作和分发工作室质量的视频内容。|
|Brandlive                              |BrandLive |基于云的生产平台。|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Haivision Makito X Encoder 和 Makito KB Encoder

如果你有现有的 Haivision X 或 Makito KB 编码器，则可以从下拉列表中选择适当的选项，并按照说明列表进行操作。

1. 选择“ **开始设置** ”以创建用于实时传送视频流的频道。 等待设置完成。 屏幕上会显示“ **已准备好连接** ”消息。
1. 完成后，下载包含所有编码参数（包括引入 URL 和事件名称）的预设。 将预设导入编码器并启动编码器。
1. 返回 Teams。 在能够从编码器查看预览后，选择“ **启动事件** ”以上线，以便观众可以看到实时事件。

> [!NOTE]
> 尚未测试对 RTMPS 的 Haivision KB 编码器支持。 Haivision Makito X Encoder 不支持 RTMPS。 这两个编码器的下载预设包含 RTMP 引入 URL。

### <a name="switcher-studio"></a>Switcher Studio

可以使用 Switcher Studio 通过 iPhone 或 iPad 开始流式传输到 Teams。

1. 选择“ **开始设置** ”以创建用于实时传送视频流的频道。 等待设置完成。 屏幕上会显示“ **已准备好连接** ”消息。
2. Switcher Studio 将打开 Switcher Studio 仪表板，将实时事件添加到你的帐户。

> [!NOTE]
> 如果还没有 Switcher Studio 帐户，则需要创建一个) 。

3. 完成此操作后，可以转到 iPhone 或 iPad 上的 Switcher Studio 应用，在“输出”选项卡中选择“Teams”，并开始流式传输到 Teams。
4. 返回 Teams。 在能够从编码器查看预览后，选择“ **开始活动** ”以上线，以便观众可以看到直播活动。

> [!NOTE]
> Switcher Studio 使用 RTMP 引入 URL。

### <a name="wirecast"></a>Wirecast

如果你是 Wirecast 的现有用户，可以从下拉列表中选择此选项，将实时流发送到 Teams。 请注意，你将需要 Wirecast 版本 10 或更高版本。

1. 选择“ **开始设置** ”以创建用于实时传送视频流的频道。 等待设置完成。 屏幕上会显示“ **已准备好连接** ”消息。
1. 编码器将在预配置的计算机上启动 Wirecast 应用，并使用正确的编码参数和为该实时事件引入 URL。 准备就绪后，单击 Wirecast 应用中的 Teams 图标，开始流式传输到 Teams。
1. 返回 Teams。 在能够从编码器查看预览后，选择“ **开始活动** ”以上线，以便观众可以看到直播活动。

> [!NOTE]
> 在预配置 RTMPS 引入 URL 的情况下启动 Wirecast 应用。
