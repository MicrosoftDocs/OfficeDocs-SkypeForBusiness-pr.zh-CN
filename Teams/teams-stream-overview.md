---
title: Microsoft Teams 中用于流式传输的编码器概述
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
description: 本文概述了 Microsoft Teams 流式处理事件的基于编码器的 RTMP 配置。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d7ea21edb6677397785367cecd3daaf9bbe513f3
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767916"
---
# <a name="live-streaming-events-in-microsoft-teams"></a>Microsoft Teams 中的实时流式处理事件

可以在组织中使用 Microsoft Teams 创建实时事件。 你可以为各种方案（例如公司范围的事件、领导更新等）安排、制作和交付实时事件。 实时流式处理事件使制作人能够策划和控制向受众广播的内容。

可以从编码器使用单比特率 RTMP 或 RTMPS 流创建、计划和运行实时事件 - 我们将负责所有转码，以便向查看者提供自适应比特率。

与 Teams 中的其他任何视频一样，你可以让直播活动向整个公司开放，或限制对特定组的访问权限。 这提供了 Teams 内部的端到端创建和查看体验。

活动结束后，视频将按需提供，具有智能功能，包括：

- 语音转文本和隐藏式字幕。
- 使用脚本搜索和时间码可以快速查找视频中重要的时刻。

## <a name="live-events-in-microsoft-365"></a>Microsoft 365 中的实时事件

无论受众、团队或社区位于何处，都可以在 Teams 或 Yammer 中创建直播活动。 与会者可以通过高清 (高清) 视频观看活动，并通过审查的 Q&A 体验提交问题。 跨 Microsoft 365 的无缝集成意味着你可以使用 Teams 交付高度生成的工作室质量事件。

## <a name="get-started"></a>开始使用

确保希望能够创建实时事件的用户具有创建实时事件所需的授予权限。 默认情况下，组织中的每个人都可以创建实时事件，但 Teams 管理员可以限制访问权限。 详细了解实时事件管理。

1. 在 Teams 管理中心的左侧导航栏中，转到 **“会议** > **实时事件策略** ”> **“管理策略** ”选项卡。
1. 如果想要：
    1. 编辑现有默认策略，选择 **“全局 (组织范围的默认)**。
    1. 创建新的自定义策略，选择“ **+添加**”。
    1. 编辑自定义策略，选择该策略，然后选择 **“编辑**”。

## <a name="monitor-your-event"></a>监视事件

作为制作者，你可以使用 Teams 客户端查看) 右侧可见的受众源 (以及当前观看活动的与会者人数。

## <a name="capabilities"></a>功能

以下是实时流式处理事件的功能：

|操作                                            |限制                                                               |
|-----------------------------------------------------|---------------------------------------------------------------------|
|使用外部编码器) 在 Teams (中创建实时事件  |企业 (E1、E3、E5) 、教育 (A3、A5)                           |
|观看直播活动                                     |具有查看事件权限的查看者以及有效的 Teams 许可证 (除非事件是公开的，则不需要查看许可证)  |
|最大分辨率                                   |720p                                                                 |
|直播前或直播) 中的最大并发实时事件 (数 |15                                                                   |
|活动并发查看器                            |10000                                                                |
|直播活动的最大长度                         |4 小时                                                              |
|合作伙伴网络缓存支持                      |Hive、Kollective、Riverbed、Ramp、Microsoft                          |
|其他网络缓存支持                        |可以工作，但不受支持                                        |
|与会者 DVR 控件                                |暂停， 播放速度 (2x 追赶， 1x 在直播) ， 查找                |
|实时字幕                                   |从编码器传递 708 字幕                                |
|自动语音转文本和字幕                |事件后处理                                            |
|交互式讨论                              |从 Yammer 创建事件时，通过 Yammer 受支持           |
|Teams 注释                                       |在事件结束后可用                                       |
|在事件) 后，在实时事件 (按需观看        |实时自动转换为按需，以便在 Teams 中即时查看和编制索引 |
|可下载录制                               |所有者在直播活动后已处理并可用               |

Teams 中的实时事件是一项高度可用的服务，你可以期待大规模的良好性能。 在导致需要故障转移的不太可能的情况下，使用外部编码的实时事件将不具有冗余，并且无法恢复。
