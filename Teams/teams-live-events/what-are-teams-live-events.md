---
title: Microsoft Teams 实时事件是什么？
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: 了解实时事件如何使用户能够将视频和内容广播到 Microsoft 团队、Yammer 和 Microsoft Stream 中的大型在线受众。
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29537a43fecd2da927497743bc5b488510fbabf7
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548929"
---
# <a name="what-are-microsoft-teams-live-events"></a>Microsoft Teams 实时事件是什么？

## <a name="overview"></a>概述

通过 Microsoft 团队实时活动, 你组织中的用户可以将视频和会议内容广播到大型在线受众。 

Microsoft 365 实时事件将实时视频流转到新的级别, 在整个服务生命周期中与与会者在实时事件之前、期间和之后鼓励其连接。 你可以使用 Microsoft Stream、Microsoft 团队或 Yammer 在你的受众、团队或社区所驻留的任何位置创建实时事件。  

团队提供基于聊天的协作、通话、会议和活动事件, 因此您可以展开您的会议的受众。 团队活动事件是团队会议的扩展, 使用户能够将视频和会议内容广播给较大的联机受众。 这些内容适用于一对多通信, 其中事件的主机在移动时主要是查看由主机共享的内容。 与会者可以在 Yammer、团队和/或 Microsoft Stream 中观看实时或录制的事件, 并可使用 "&" 或 "Yammer 对话" 与演示者进行交互。 

团队活动事件被视为下一版本的 Skype 会议直播, 最终将替换 Skype 会议直播中提供的功能。 在此情况下, Microsoft 将继续为在其组织中使用 Skype for Business 的用户继续支持 Skype 会议直播, 而不会中断新事件或将来事件的服务。 但是, 我们鼓励你尝试使用团队实时事件来利用所有全新的激动人心的功能, 包括屏幕共享和对外部硬件/软件编码器的支持。 

因此, 让我们开始吧。 首先, 看看下图显示了 Microsoft 365 实时事件中涉及的高级组件以及它们的连接方式。 

![显示实时事件的关键组件的图表](../media/teams-live-events.png  "图表显示实时事件、计划、生产、Microsoft Stream 平台、经过认证的第三方 eCDN 提供商的关键组件")

### <a name="event-group-roles"></a>事件组角色
团队中的实时事件使多个角色 (组织者、制造者、演示者和与会者) 能够成功广播和参与事件。 若要了解详细信息, 请参阅[事件组角色](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)。

## <a name="key-components"></a>关键组件
因此, 您可以从上面的图片看到, 团队中的实时事件使用了四个关键组件。

### <a name="scheduling"></a>级
团队使组织者能够使用相应的与会者权限创建事件, 指定事件团队成员, 选择 "生产方法", 然后邀请与会者。 如果实时事件是从 Yammer 组内创建的, 则实时事件参与者将能够使用 Yammer 对话与事件中的人员交互。 

![显示 "新的实时事件" 屏幕的屏幕截图](../media/teams-live-events-schedule.png "显示 \"新建实时事件\" 屏幕以创建和安排新实时事件的屏幕截图")

### <a name="production"></a>生成
视频输入是实时事件的基础, 它可能会因单个网络摄像头而异。 Microsoft 365 中的实时事件支持各种生产方案, 包括使用 web 摄像头的快速入门事件或外部设备或应用程序中生成的事件。 您可以根据其项目要求和预算选择这些选项。 可通过两种方式生成事件:

- **Microsoft 团队**: 此生产方法允许用户使用其网络摄像头在 Microsoft 团队中生成活动事件, 或使用来自团队室系统的/V 输入。 如果你希望使用连接到电脑的音频和视频设备或邀请远程演示者参与事件, 此选项是最佳和最快捷的选择。 此选项允许用户轻松地使用其 web 摄像头, 并将其屏幕作为输入到事件中进行共享。 

    ![显示使用 "快速入门" 方法生成的实时事件的屏幕截图](../media/teams-live-events-quick-start.png "屏幕截图显示使用快速入门生产方法生成的实时事件")

- **外部应用程序或设备**: 外部编码器允许用户直接从外部硬件或基于软件的编码器 (使用[Microsoft Stream](https://stream.microsoft.com)) 生成实时事件。 如果你已经有了 studio 质量的设备 (例如 media mixers), 并且支持实时消息传递协议 (RTMP) 服务流, 则此选项最适用。 这种类型的生产通常在大规模事件中使用, 如 executive 城镇 halls-将媒体混合器中的单个流广播给观众。 

    ![显示使用外部编码器生成的实时事件的屏幕截图](../media/teams-live-events-external-encoder.png "显示使用外部编码器生产方法生成的实时事件的屏幕截图")

### <a name="streaming-platform"></a>流式处理平台
实时事件流平台由以下部分组成:

- **Azure 媒体服务**: [azure 媒体服务](https://docs.microsoft.com/azure/media-services/previous/)为你提供了一种广播质量的视频流服务, 可在当今最常用的移动设备上与更大的受众联系。 媒体服务增强了辅助功能、分发和可伸缩性, 并让您能够轻松、经济高效地将内容流式传输给您的本地或全球受众, 同时保护内容。
- **Azure 内容交付网络 (CDN)**: 一旦你的流投入使用, 它将通过[Azure 内容交付网络 (cdn)](https://docs.microsoft.com/azure/cdn/)进行传递。 Azure 媒体服务为流式处理终结点提供集成的 CDN。 这允许在全球查看流, 无缓冲。

### <a name="enterprise-content-delivery-network-ecdn"></a>企业内容交付网络 (eCDN)
ECDN 的目标是从 internet 获取视频内容, 并将内容分散到整个企业中, 而不会影响网络性能。 您可以使用以下认证的 eCDN 合作伙伴之一来优化您的网络, 以便在您的组织内保持实时事件:
- [配置单元](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [渐变](http://www.ramp.com)

### <a name="attendee-experience"></a>与会者体验 
与会者体验是实时事件的最重要的方面, 并且很重要的是与会者无需任何问题即可参与实时事件。 与会者体验使用 Azure Media Player (适用于 Microsoft 团队中生成的事件) 和流播放器 (对于在外部 enccoder 中生成的事件) 在桌面、浏览器和移动 (iOS、Android) 中工作。 Office 365 提供 Yammer 和团队, 因为这两个协作中心和实时与会者体验集成到了这些协作工具中。 

![显示实时事件与会者体验的屏幕截图](../media/teams-live-events-attendee.png "显示实时事件与会者体验的屏幕截图")

## <a name="next-steps"></a>后续步骤
转到 "[规划团队实时事件](plan-for-teams-live-events.md)"。

### <a name="related-topics"></a>相关主题
- [Yammer、Microsoft 团队和 Microsoft Stream 中跨 Microsoft 365 的实时事件](https://docs.microsoft.com/stream/live-event-m365)
- [Microsoft 团队中的实时事件](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer 中的实时事件](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft Stream 中的实时事件](https://docs.microsoft.com/stream/live-event-overview)

 
