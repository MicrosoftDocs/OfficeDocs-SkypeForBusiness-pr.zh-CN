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
ms.reviewer: tonysmit
search.appverid: MET150
description: 了解如何 live 事件使用户能够广播视频和 Microsoft 团队、 Yammer 和 Microsoft 流中的大型联机访问群体的内容。
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02db69572fa13e5c02717e7d8d192ca1b61cff8e
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542892"
---
# <a name="what-are-microsoft-teams-live-events"></a>Microsoft Teams 实时事件是什么？
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>概述

与 Microsoft 团队 live 事件，您的组织中的用户可以广播到大型联机访问群体的视频和会议内容。 

Microsoft 365 live 事件使 live 视频流到新的级别，鼓励连接在整个项目生命周期与与会者之前、 升级期间和之后 live 事件。 您可以创建 live 事件，只要在访问群体、 团队或社区驻留，使用 Microsoft 流，Microsoft 团队或 Yammer。  

团队提供基于聊天的协作、 呼叫、 会议和 live 事件，因此您可以展开您的会议的访问群体。 团队 live 事件是一种扩展的团队会议，使用户能够为大型联机访问群体广播视频和会议内容。 通过这些方法，其中的事件宿主前导之间的交互和访问群体参与主要是为了查看共享的主机的内容-一对多通信。 与会者可以观看 Yammer、 团队和/或 Microsoft 流的活动或录制事件，并可与使用仲裁的 Q & A 或 Yammer 对话的演示者进行交互。 

团队 live 事件视为 Skype 会议广播的下一个版本和最终将替换 Skype 会议广播中提供的功能。 期间团队 live 事件的公共预览发布，我们将继续支持服务的新的或将来事件不会中断的 Skype 会议广播。 但是，我们建议您 live 事件可以利用所有新功能和令人兴奋功能包括屏幕共享、 试用团队 attendee 计数和外部的硬件软件编码器的支持。 

因此，就可以开始。 首先，看看演示高级别的组件在 Microsoft 365 live 事件和连接方式所涉及的以下图表。 

![图表显示的实时事件的关键组件安排，生产，Microsoft 流平台，认证第三方 eCDN 提供程序](../media/teams-live-events.png  "图表显示的实时事件的关键组件安排，生产，Microsoft 流平台，认证第三方 eCDN 提供程序")

## <a name="key-components"></a>主要组件
因此，您可以看到上面图片中有四个主要组件，与团队中的实时事件一起使用。

### <a name="scheduling"></a>日程安排
团队提供的组织者与相应的与会者权限创建事件、 指定事件的工作组成员、 选择生产方法，并邀请与会者的功能。 如果从 Yammer 组内创建的实时事件，live 事件与会者都将能够使用 Yammer 对话与事件中的人员进行交互。 

![屏幕截图显示新建 live 事件的屏幕，确定创建和安排的新的实时事件](../media/teams-live-events-schedule.png "屏幕截图显示新建 live 事件的屏幕，确定创建和安排的新的实时事件")

### <a name="production"></a>生产
Microsoft 365 中的实时事件支持生产方案提供了一系列，包括使用和网络摄像机快速入门事件或使用 studio 质量设备外部编码器事件。 视频是 Live 事件的基础，这可以因而异单个网络摄像机到多照相机专业人员视频生产环境。 您可以选择以下选项，具体取决于其项目要求和预算。 有两种方法将生成事件：

- **快速入门生产**： 快速入门生产方法允许用户生成使用团队会议其 live 事件。 此选项是最佳，如果您想要使用的音频和视频设备的最快选项连接到 PC，或参与事件邀请远程演示者。 此选项允许用户能够轻松地使用其和网络摄像机和共享其屏幕作为输入到的事件。 

    ![显示使用快速生成的实时事件的屏幕截图启动生产方法](../media/teams-live-events-quick-start.png "屏幕截图显示的由使用快速的实时事件启动生产方法")

- **外部编码器生产**： 外部编码器允许用户产生直接从外部硬件或与[Microsoft 流](https://stream.microsoft.com)基于软件的编码器其 live 事件。 此选项将是最佳如果您已有 studio 质量设备 （例如，媒体混音器） 到实时消息协议 (RTMP) 服务的支持流式处理。 如 executive 城镇大厅 – 从媒体混音器为单个流将广播到该访问群体其中的大型事件通常用于生产此类型。 

    ![显示使用外部编码器生产方法生成的实时事件的屏幕截图](../media/teams-live-events-external-encoder.png "屏幕截图显示的使用外部编码器生产方法生成的实时事件")

### <a name="streaming-platform"></a>流式平台
Live 的事件流平台的以下部分组成：

- **Azure 媒体服务**： [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/)为您提供了广播质量视频流的服务访问今天的最常用的移动设备上的较大访问群体。 Media Services 增强辅助功能、 分发和可伸缩性，并使其简单且经济高效流内容到您的本地或全球访问群体 — 同时保护您的内容。
- **Azure 内容交付网络 (CDN)**: 一旦您流投入，它通过[Azure 内容交付网络 (CDN)](https://docs.microsoft.com/azure/cdn/)。 Azure Media Services 提供集成的 CDN 流终结点。 这样世界各地查看与无缓冲的流。

### <a name="enterprise-content-delivery-network-ecdn"></a>企业内容交付网络 (eCDN)
ECDN 的目标是从 internet 视频内容并不会影响网络性能分布在整个企业的内容。 您可以使用下列选项之一认证 eCDN 合作伙伴优化您的网络保留组织内的实时事件：
- [配置单元](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [提升](http://www.ramp.com)

### <a name="attendee-experience"></a>参与者的体验 
参与者的体验是 live 事件的最重要方面和很重要，与会者可以参加的实时事件无任何问题。 参与者的体验使用 Azure 媒体播放器并跨桌面、 浏览器中，和 mobile (iOS，Android) 的工作方式。 Office 365 提供 Yammer 和团队为两个协作集线器和 live attendee 体验集成到这些协作工具。 

![屏幕截图显示 live 事件 attendee 体验](../media/teams-live-events-attendee.png "屏幕截图显示 live 事件 attendee 体验")

## <a name="next-steps"></a>后续步骤
转到[规划团队 live 事件](plan-for-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [跨 Yammer、 Microsoft 团队和 Microsoft 流中的 Microsoft 365 live 事件](https://docs.microsoft.com/stream/live-event-m365)
- [中的 Microsoft 团队的实时事件](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer 中的实时事件](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft 流中的实时事件](https://docs.microsoft.com/stream/live-event-overview)

 
