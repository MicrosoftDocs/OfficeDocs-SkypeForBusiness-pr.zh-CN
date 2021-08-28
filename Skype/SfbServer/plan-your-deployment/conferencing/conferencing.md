---
title: 规划会议Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 摘要：阅读本主题，了解会议功能Skype for Business Server。
ms.openlocfilehash: 90200648c8e370bd0e59f0b6759717cd706b683d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628584"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>规划会议Skype for Business Server
 
**摘要：** 阅读本主题，了解会议功能Skype for Business Server。
  
Skype for Business Server中的会议功能允许用户使用其 Skype for Business 客户端在线开会和召开会议，而不是让每个人都在同一房间开会。 会议参与者可以使用其 Skype for Business 客户端连接到会议，获得完整的音频和视频体验，或者使用电话拨入会议。 会议还支持即时消息、桌面和应用程序共享以及交互式白板。
  
本主题包括以下部分：
  
- 会议特性和功能
    
- 会议组件
    
- 会议策略
    
- 支持大型会议
    
- 确定组织需求
    
## <a name="conferencing-features-and-capabilities"></a>会议特性和功能

Skype for Business Server 中提供四种类型的会议：Web 会议、音频和视频 (A/V) 会议、电话拨入式会议和即时消息 (IM) 会议。 
  
可以选择启用所有会议类型，也可以选择仅使用一种类型，具体取决于你的需求。 例如，您可以启用所有类型的会议（包括电话拨入式会议）以允许无法通过 Skype for Business 客户端加入会议的用户通过电话拨入和参与会议音频。 在部署Skype for Business Server时，将自动部署 IM 会议功能;指定是否使用拓扑生成器部署 Web、A/V 和电话拨入式会议。 有关详细信息，请参阅在部署[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md) 
  
以下小节介绍每种会议类型的特性和功能。
  
### <a name="web-conferencing"></a>Web 会议

Web 会议允许与会者协作处理会议期间共享的文档，并允许会议演示者通过 Skype for Business 客户端共享应用程序。 Web 会议提供以下功能： 
  
- **白板和批注。** 白板是一个空白画布，可用于借助文本、墨迹、图形和图像进行协作。 所有与会者都可看到在白板上所做的注释。 白板功能使与会者能够交流想法、集体讨论、做笔记等，从而增进协作。
    
- **轮询。** 轮询功能使演示者能够快速确定参与者的偏好，从而增强协作。 在联机会议和对话过程中，演示者可以使用轮询从参与者收集匿名响应。 所有演示者都可以看到结果，并可以向所有与会者隐藏或显示结果。
    
- **应用程序共享和桌面共享。** 会议期间，会议演示者可以在多监视器环境中共享其整个桌面、单个应用程序或各个监视器。 除了查看内容外，会议的其他参与者还可以请求控制演示者的屏幕，并授予权限与内容交互 (包括滚动和编辑) 。 会议参与者还可以担任演示者，并开始在会议期间共享内容。
    
- **PowerPoint共享。** 允许用户通过 PowerPoint Web Apps 服务器在Office共享会议演示文稿，这允许：
    
  - 高分辨率显示并支持PowerPoint功能，如动画、幻灯片切换和嵌入式视频。
    
  - 移动设备可以访问这些演示文稿。
    
  - 具有适当权限的用户可以独立于演示文稿本身PowerPoint浏览整个演示文稿。 例如，当 Ken 演示自己的幻灯片放映时，Heidi 可以查看想要放映的任何幻灯片，而不会影响 Ken 的演示。
    
### <a name="audio-and-video-conferencing"></a>音频和视频会议

音频和视频会议允许在会议中播放音频和视频。 音频允许与会者相互交谈，就像他们在同一房间一样。 视频启用视频显示，Skype for Business视频的任何与会者或演示者通过支持视频的 Web 摄像头或会议设备加入会议。
  
 Skype for Business Server提供了一些用户可用于为用户配置音频会议体验的功能，其中包括：
  
- **受众静音。** 演示者可以使用此设置将会议的所有音频参与者设为静音，并且使会议置于非演示者无法自行取消静音的状态。
    
- **会议进入/退出通知。** 如果已启用电话拨入式会议，则演示者可以使用此设置打开或关闭进入和退出通知，以最大限度地减少会议进行中的干扰。
    
- **通过拨出添加用户。** 已授予权限的演示者和与会者可以将 PSTN 号码添加到会议，并且让会议拨出到这些号码。
    
  Skype for Business Server提供了多个用户可用于为用户配置视频会议体验的功能，其中包括：
  
- **库视图。** 在超过两人的视频会议中，用户会自动看到会议中的每个人。 如果会议参与者超过五名，则最活跃的参与者的视频显示在最上面一行，并且仅显示其他参与者的照片。 默认情况下，多方视频已打开。
    
- **全景视频。** 如果在会议室中安装了 RoundTable 视频会议设备，则此功能可提供会议室的 360 度完整视图。 全景视频带仅适用于 RoundTable 设备。
    
- **仅演示者视频模式。** 演示者可以配置会议，以便只显示演示者的视频。 当多个视频流可用并锁定到不同源时，这可以防止大型会议中出现干扰。 此模式还适用于由 RoundTable 设备捕获和提供的视频。
    
- **视频聚焦。** 演示者可以配置会议，以便会议的其他参与者只能看到来自视频源的选定参与者的视频。 此模式还适用于由 RoundTable 设备为全景视频捕获和提供的视频。
    
### <a name="dial-in-conferencing"></a>拨入式会议

电话拨入式会议允许与会者通过电话拨入会议来加入会议的音频部分。 电话拨入式会议是音频会议的一部分且需要其他配置。 有关电话拨入式会议详细信息，请参阅在[](dial-in-conferencing.md)Skype for Business Server 中规划电话拨入式会议和在 Skype for Business Server[中配置电话拨入式Skype for Business Server。](../../deploy/deploy-conferencing/dial-in-conferencing.md) 
  
### <a name="instant-messaging-conferencing"></a>即时消息会议

即时消息 (IM) 会议允许两方在单个 IM 会话中进行通信。 有关 IM 会议的详细信息，请参阅 Plan [for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
## <a name="conferencing-components"></a>会议组件

支持会议功能的组件包括：
  
- **应用程序服务。** 应用程序服务提供了一个平台，用于部署、承载和管理 UC (应用程序) 通信。 电话拨入式会议使用两个需要应用程序服务的 UC 应用程序：会议助理和 会议公告。 默认情况下，在前端池中的前端服务器上安装并激活应用程序服务。 它还安装在每个Standard Edition服务器上，以启用和配置电话拨入式会议。
    
- **会议助理应用程序。** 该会议助理应用程序是一个统一通信应用程序，它接受公用电话交换网 (PSTN) 呼叫、播放提示以及将呼叫加入 A/V 会议。 默认情况下会议助理应用程序电话拨入式会议时安装并激活电话拨入式会议。
    
- **会议公告应用程序。** 会议公告应用程序 是一个统一通信应用程序，可对某些操作（例如，当参与者加入或离开会议、参与者静音或取消静音、有人进入会议厅或锁定或解锁会议）播放提示音和提示。 会议公告应用程序还支持从电话键盘 (DTMF) 双音多频命令。 默认情况下会议公告应用程序电话拨入式会议时自动安装并激活会议。
    
- **电话拨入式会议设置页。** "电话拨入式会议 设置"页显示会议拨入号码及其可用语言、分配的会议信息 (即，对于不需要安排) 的会议和会议中的 DTMF 控件，并支持管理个人标识号 (PIN) 和分配的会议信息。 "电话拨入式会议设置页会自动作为 Web 服务的一部分进行安装。
    
- **中介服务器和 PSTN 网关。** 电话拨入式会议需要中介服务器在 Skype for Business Server 与 PSTN 网关之间的某些配置) 中转换信号 (和媒体，需要 PSTN 网关在中介服务器和 PSTN 网关之间转换信号和媒体。 对于电话拨入式会议，必须部署至少一台中介服务器和以下服务器之一：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
  > [!NOTE]
  > 如果还要部署 企业语音，则中介服务器和 PSTN 网关是部署企业语音的一部分。 如果不部署企业语音，则需要为电话拨入式会议部署至少一台中介服务器，以及至少一个 PSTN 网关、IP-PBX 或 SBC。 
  
- **文件存储。** 文件存储用于录制的名称音频文件。 文件存储是每个部署或部署Enterprise Edition Standard Edition组件。
    
- **用户存储。** 用户存储用于存储用户Skype for Business Server PIN。 PIN 是哈希值。 用户存储是每个部署或部署Enterprise Edition Standard Edition组件。
    
- **Office Web Apps 服务器。** 若要使用 Web 会议功能，管理员必须安装 Office Web Apps Server，并且必须将 Skype for Business Server 配置为与 Office Web Apps Server 通信。
    
## <a name="conferencing-policies"></a>会议策略

若要强制执行组织的策略和控制带宽使用量，您可以为用户可组织的会议类型设置策略。 您可以定义各种会议策略，并将其分配给各个用户和用户组。 还可以设置用于管理对等对话的策略。 有关设置会议策略的详细信息，[请参阅管理会议](../../manage/conferencing/conferencing-policies.md)Skype for Business Server。 有关带宽管理的详细信息，请参阅 Plan [for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
## <a name="support-for-large-meetings"></a>支持大型会议

会议可以支持Skype for Business Server取决于会议托管在共享池还是专用池中：
  
- 在共享池中，Skype for Business Server最多 250 个用户主持会议。 共享池是承载所有 Skype for Business Server 工作负荷的池，包括即时消息 (IM) 和状态、会议和企业语音。 
    
- 在专用池中，Skype for Business Server使用 Web 和音频/视频 (A/V) 会议（包括共享 PowerPoint 演示文稿）支持多达 1000 个参与者的会议。 若要实现此支持，需要配置一个专用池以支持大型会议，并且需要以某种方式管理该池以确保一次仅主持一个大型会议。 
    
有关管理大型会议的信息，请参阅在 Skype for Business Server[中规划大型Skype for Business Server。](large-meetings.md)
  
如果你的组织需要更大的会议功能，则应考虑实施利用 Skype 会议 广播的混合环境，这是一种属于 Microsoft 365 和 Office 365 的联机服务。 Skype 会议广播使用户能够主持会议，并广播给最多 10，000 名参与者的大型联机受众。 使用广播Skype 会议要求已在Skype for Business Server或生产组织混合Microsoft 365混合Office 365配置。 所有用户都必须建立联机租户作为先决条件。 如果你有兴趣部署可以利用广播的混合Skype 会议，请参阅为本地广播配置[Skype 会议部署](../../deploy/configure-skype-meeting-broadcast.md)。
  
## <a name="determine-your-organizations-needs"></a>确定组织需求

在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。 以下列表将指导您完成会议规划过程，以根据组织的要求确定应部署哪些会议功能。
  
> [!NOTE]
> 在部署时启用会议时，将自动启用 Web 和 A/V 会议。 但是，可以通过配置会议策略来禁用特定功能，如本主题前面所述。 
  
- **是否要启用包括文档协作和应用程序共享的 Web 会议？**
    
    如果是，则必须使用规划工具或拓扑生成器为前端池启用会议。 有关详细信息，请参阅在部署[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    与文档协作相比，应用程序共享要求使用更多的网络带宽。 Skype for Business Server提供了一种限制机制来控制每个应用程序共享会话。 默认情况下，每个会话设置为 1.5 KB/秒。 如果不希望启用应用程序共享，但希望进行文档协作，可以启用会议并使用会议策略禁用应用程序共享。 有关配置会议策略的详细信息，请参阅管理会议[Skype for Business Server。](../../manage/conferencing/conferencing-policies.md)
    
    若要使用户能够共享PowerPoint演示文稿，您需要配置 Office Web Apps Server。 有关配置 Web Apps Server Office的详细信息，请参阅 Configure [integration with Office Web Apps Server in Skype for Business Server。](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **是否要启用音频和视频会议？**
    
    如果是，则必须使用规划工具或拓扑生成器为前端池启用会议。 有关详细信息，请参阅在部署[Skype for Business Server。](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    音频和视频会议需要并使用比 Web 会议会议更多的网络带宽 (包括文档协作和应用程序共享) 。 如果不希望启用音频和视频会议，但希望启用 Web 会议，可以启用会议并使用会议策略禁用 A/V 会议。
    
    如果要启用音频会议但不启用视频会议，可以启用 A/V 会议并使用会议策略来阻止视频会议。 或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。 
    
    有关配置会议策略的信息，请参阅管理会议[Skype for Business Server。](../../manage/conferencing/conferencing-policies.md)
    
    > [!NOTE]
    > 企业语音 A/V 会议时无需安装会议。 如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。 
  
- **使用 PSTN 电话时，是否要允许用户加入会议的音频部分？**
    
    如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。
    
    电话拨入式会议是一项可选功能，可在部署电话拨入式会议Skype for Business Server配置。 尽管电话拨入式会议使用的一些组件与企业语音相同，但即使未部署电话拨入式企业语音。 电话拨入式会议支持企业用户和匿名用户。 有关为企业用户和匿名用户配置电话拨入式会议的信息，请参阅在[Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md)中部署会议和在 Skype for Business Server[中配置电话拨入式Skype for Business Server。](../../deploy/deploy-conferencing/dial-in-conferencing.md)
    
- **是否要允许具有外部客户端Skype for Business用户加入会议？**
    
    通过允许外部参加会议，可最大限度地提高对会议Skype for Business Server。 外部用户可能包括：
    
  - **远程用户。** 组织内部的用户在防火墙外工作，并且使用其便携式计算机或其他Skype for Business Server设备。
    
  - **联盟用户。** 来自合作公司的用户，这些用户也运行Skype for Business Server。 若要使用户轻松与这些用户联系，请与这些公司建立联盟关系。
    
  - **匿名用户。** 用户专门邀请加入特定会议的其他任何外部用户。 贵公司的会议组织者可以将会议的电子邮件邀请发送给外部用户。 该电子邮件包含一个链接，外部用户可以单击该链接以加入会议。
    
    如果要允许外部用户，则需要部署边缘服务器。 此外，通过部署边缘服务器，您可以与其他组织（如您的客户或供应商）建立联盟关系，来自这些组织的用户可以更轻松地与用户进行协作。
    
    有关部署边缘服务器的详细信息，请参阅规划边缘服务器和部署边缘服务器。 有关为 Office Web Apps Server 启用外部访问的详细信息，请参阅在 Skype for Business Server 中配置与[Office Web Apps Server 的Skype for Business Server。](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **是否要控制可以加入会议Skype for Business Server客户端？**
    
    如果是，则应配置与会页面，以便只有要支持的客户端选项可用。 用户每次单击链接以加入安排的会议时，Skype for Business Server检测计算机上是否已安装客户端。 然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。 与会页面始终包含使用会议Skype for Business Web应用。 除了此选项之外，还可以决定是否包含 Attendee 和早期版本的 Communicator。 
    

