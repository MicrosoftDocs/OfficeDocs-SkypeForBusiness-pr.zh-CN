---
title: 在 Skype for Business 服务器中规划会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 摘要：阅读本主题，了解 Skype for Business 服务器中的会议功能和功能。
ms.openlocfilehash: f91c815cf0b5d0b69ad5815157cba7a56bb28307
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816000"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划会议
 
**摘要：** 阅读本主题，了解 Skype for Business 服务器中的会议功能和功能。
  
Skype for Business Server 中的会议允许用户使用 Skype for business 客户端在线开会和召开会议，而不是每个人都在同一个房间内协作。 会议参与者可以使用 Skype for Business 客户端连接到完整音频和视频体验的会议，或使用电话拨入会议。 会议还支持即时消息、桌面和应用程序共享，以及交互式白板。
  
本主题包括以下部分：
  
- 会议特性和功能
    
- 会议组件
    
- 会议策略
    
- 大型会议支持
    
- 确定组织的需求
    
## <a name="conferencing-features-and-capabilities"></a>会议特性和功能

Skype for Business 服务器中提供了四种类型的会议： web 会议、音频和视频（A/V）会议、电话拨入式会议和即时消息（IM）会议。 
  
根据你的需要，可选择启用所有会议类型，或者只使用一种类型。 例如，你可以启用所有类型（包括电话拨入式会议），以便允许无法使用 Skype for Business 客户端加入会议的用户通过电话拨入和参与会议音频。 部署 Skype for Business 服务器时，即时消息会议功能将自动部署;使用拓扑生成器指定是否部署 web、A/V 和电话拨入式会议。 有关详细信息，请参阅[在 Skype For Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。 
  
以下小节介绍每种会议类型的特性和功能。
  
### <a name="web-conferencing"></a>Web 会议

网络会议允许会议与会者协作处理会议期间共享的文档，并让会议演示者通过 Skype for Business 客户端共享应用程序。 Web 会议提供了以下特性： 
  
- **白板和批注。** 白板是一个空白画布，可用于借助文本、墨迹、图形和图像进行协作。所有与会者都可看到在白板上所做的注释。白板功能使与会者能够交流想法、集体讨论、做笔记等，从而增进协作。
    
- **投票。** 轮询功能使演示者能够快速确定参与者的首选项，从而增强协作。 在联机会议和对话过程中，演示者可以使用投票从参与者收集匿名响应。 所有演示者都可以看到结果，并可以向所有与会者隐藏或显示结果。
    
- **应用程序共享和桌面共享。** 在会议期间，会议演示者可以在多监视器环境中共享其整个桌面、单个应用程序或单个监视器。 除了查看内容之外，其他与会者可以请求控制演示者的屏幕，并在获得许可的情况下交互操作内容（包括滚动和编辑）。 与会者还可以在会议期间以演示者身份接管会议并开始共享内容。
    
- **PowerPoint 共享。** 允许用户在会议中通过 Office Web Apps Server 共享 PowerPoint 演示文稿，该功能实现了：
    
  - 高分辨率的显示，并支持动画、幻灯片转换和嵌入视频等 PowerPoint 功能。
    
  - 移动设备可以访问这些演示文稿。
    
  - 具有适当权限的用户能够独立于 PowerPoint 演示文稿本身来浏览文稿。例如，当 Ken 演示其幻灯片放映时，Heidi 可以查看自己所需的任何幻灯片，而不会影响 Ken 的演示。
    
### <a name="audio-and-video-conferencing"></a>音频和视频会议

音频和视频会议功能在会议中支持音频和视频。 音频功能可以让与会者像同处一室一样相互交谈。 视频可在使用支持视频的网络摄像头或会议设备上加入会议的任何与会者或演示者的 Skype for Business 客户端中启用视频显示。
  
 Skype for Business 服务器提供了多项功能，用户可使用这些功能为用户配置音频会议体验，包括以下内容：
  
- **观众静音。** 演示者可使用此设置将会议中的所有音频参与者静音，并使会议处于非演示者无法自行取消静音的状态。
    
- **会议进入/退出公告。** 如果已启用电话拨入式会议，演示者可使用此设置打开或关闭进入/退出通知以最大程度地减小会议进行中受到的干扰。
    
- **通过拨出来添加用户。** 已授予权限的演示者和与会者可以向会议添加 PSTN 号码，并让会议拨出到这些号码。
    
  Skype for Business 服务器提供了多项功能，用户可使用这些功能为用户配置视频会议体验，包括以下内容：
  
- **库视图。** 在超过两名与会者的视频会议中，用户会自动看到会议中的每一名与会者。 如果与会者超过五名，那么最活跃与会者的视频将显示在最上面一行，并仅对其他与会者显示照片。 默认情况下，已启用多方视频。
    
- **全景视频。** 如果在会议室中安装了 RoundTable 视频会议设备，则此功能可提供会议室的 360 度全景。 全景视频带只能用于 RoundTable 设备。
    
- **仅演示者视频模式。** 演示者可以对会议进行配置，以仅显示来自演示者的视频。 如果提供了多个视频流并锁定到不同的源，这可阻止大型会议受到干扰。 此模式还适用于由 RoundTable 设备捕获和提供的视频。
    
- **视频聚焦。** 演示者可以对会议进行配置，以使会议中的其他参与者仅看到由作为视频源的选定参与者提供的视频。 此模式还适用于由 RoundTable 设备针对全景视频捕获和提供的视频。
    
### <a name="dial-in-conferencing"></a>电话拨入式会议

电话拨入式会议允许会议与会者通过电话拨入会议，加入会议的音频部分。 电话拨入式会议是音频会议的子集，需要额外的配置。 有关电话拨入式会议的详细信息，请参阅[在 skype for Business 服务器中规划电话拨入式会议](dial-in-conferencing.md)和[在 Skype for Business 服务器中配置电话拨入式会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)。 
  
### <a name="instant-messaging-conferencing"></a>即时消息会议

即时消息 (IM) 会议允许两个以上的用户在单个 IM 会话中进行通信。 有关即时消息会议的详细信息，请参阅[Skype For Business 服务器中的计划即时消息和状态](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
## <a name="conferencing-components"></a>会议组件

支持会议功能的组件包括：
  
- **应用程序服务。** 应用程序服务为部署、承载和管理统一通信 (UC) 应用程序提供了一个平台。 电话拨入式会议使用两个需要应用程序服务的 UC 应用程序：会议助理和会议通知。 默认情况下，应用程序服务在前端池中的每台前端服务器上安装和激活。 该服务还安装在每个 Standard Edition 服务器上，以启用和配置电话拨入式会议。
    
- **会议助理应用程序。** 会议助理应用程序是接受公用电话交换网 (PSTN) 呼叫、播放提示音并将呼叫加入 A/V 会议的统一通信应用程序。默认情况下，在启用电话拨入式会议时，系统会安装并激活会议助理应用程序。
    
- **会议通知。** 会议通知应用程序是在执行特定操作时（例如，当参与者加入或离开会议时，将参与者静音或取消静音时，有人进入会议厅时，以及锁定或取消锁定会议时）向 PSTN 参与者播放提示音和提示的统一通信应用程序。会议通知还支持电话小键盘的双音多频 (DTMF) 命令。默认情况下，在启用电话拨入式会议时，系统会自动安装并激活会议通知应用程序。
    
- **“电话拨入式会议设置”页。**“电话拨入式会议设置”页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。“电话拨入式会议设置”页作为 Web 服务的一部分自动安装。
    
- **中介服务器和 PSTN 网关。** 电话拨入式会议需要中介服务器才能在 Skype for Business 服务器和 PSTN 网关之间转换信号（和媒体），以及用于在中介服务器和 PSTN 网关之间转换信号和媒体的 PSTN 网关. 对于电话拨入式会议，必须至少部署一个中介服务器和以下至少一个服务器：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
  > [!NOTE]
  > 如果您还在部署企业语音，则中介服务器和 PSTN 网关是企业语音部署的一部分。 如果不部署企业语音，则需要为电话拨入式会议至少部署一个中介服务器和至少一个 PSTN 网关、IP PBX 或 SBC。 
  
- **文件存储。** 文件存储用于录制的名称音频文件。文件存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。
    
- **用户存储。** 用户存储用于存储用户 Skype for business 服务器 Pin。 PIN 是哈希值。 用户存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。
    
- **Office Web Apps Server。** 为了使用 web 会议功能，管理员必须安装 Office Web Apps 服务器，并且他们必须配置 Skype for Business 服务器才能与 Office Web Apps 服务器通信。
    
## <a name="conferencing-policies"></a>会议策略

若要强制实施你的组织的策略和控制带宽使用，你可以为用户可组织的会议类型设置策略。 可以定义各种会议策略，并将其分配给各个用户和用户组。 还可以设置管理对等对话的策略。 有关设置会议策略的详细信息，请参阅[在 Skype For Business 服务器中管理会议策略](../../manage/conferencing/conferencing-policies.md)。 有关带宽管理的详细信息，请参阅[在 Skype For Business 服务器中计划呼叫许可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
## <a name="support-for-large-meetings"></a>大型会议支持

Skype for Business 服务器可以支持的会议大小取决于会议是在共享还是专门的池中托管：
  
- 在共享池上，Skype for Business 服务器可以托管最多250个用户的会议。 共享池是托管所有 Skype for Business 服务器工作负荷（包括即时消息（IM）和联机状态、会议和企业语音）的池。 
    
- 在专用的池中，Skype for Business 服务器可以支持最多1000个参与者使用 web 和音频/视频（A/V）会议的会议，包括共享 PowerPoint 演示文稿。 若要实现此支持，需要配置专用池来支持大型会议，并且需要以某种方式管理该池以确保一次仅主持一个大型会议。 
    
有关管理大型会议的详细信息，请参阅[在 Skype For Business 服务器中规划大型会议](large-meetings.md)。
  
如果您的组织需要更大的会议功能，您应该考虑实施一个混合环境，该环境利用 Skype 会议直播（属于 Office 365 的一项在线服务）。 Skype 会议直播使用户可以向多达10000个参与者的大型联机受众主持和广播会议。 使用 Skype 会议直播需要在具有生产 Office 365 租户的混合设置中配置 Skype for business 服务器。 所有用户都必须具有作为先决条件建立的联机租户。 如果你对部署可利用 Skype 会议直播的混合解决方案感兴趣，请参阅[为 Skype 会议直播配置内部部署部署](../../deploy/configure-skype-meeting-broadcast.md)。
  
## <a name="determine-your-organizations-needs"></a>确定组织需求

在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。 下表将指导你完成会议规划过程，以根据组织的要求确定应部署的会议功能。
  
> [!NOTE]
> 在部署中启用会议时，您将自动启用 Web 和 A/V 会议。 但是，您可以按本主题前面所述，通过配置会议策略来禁用特定功能。 
  
- **是否要启用包括文档协作和应用程序共享的 Web 会议？**
    
    如果是，就必须使用规划工具或拓扑生成器来为前端池启用会议。 有关详细信息，请参阅[在 Skype For Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
    
    与文档协作相比，应用程序共享要求使用更多的网络带宽。 Skype for business 服务器提供控制每个应用程序共享会话的节流机制。 默认情况下，每个会话设置为 1.5 KB/秒。 如果您不想启用应用程序共享，但需要文档协作，则可以启用会议并使用会议策略来禁用应用程序共享。 有关配置会议策略的详细信息，请参阅[在 Skype For Business 服务器中管理会议策略](../../manage/conferencing/conferencing-policies.md)。
    
    若要支持用户共享 PowerPoint 演示文稿，则需要配置 Office Web Apps Server。 有关配置 Office Web Apps 服务器的详细信息，请参阅[在 Skype For Business server 中配置与 Office Web apps 集成服务器的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。
    
- **是否要启用音频和视频会议？**
    
    如果是，就必须使用规划工具或拓扑生成器来为前端池启用会议。 有关详细信息，请参阅[在 Skype For Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
    
    与 Web 会议（包括文档协作和应用程序共享）相比，音频和视频会议需要并使用更多的网络带宽。 如果您不希望启用音频和视频会议，但希望启用 Web 会议，则可以启用会议并使用会议策略来禁用 A/V 会议。
    
    如果希望启用音频会议但不启用视频会议，则可以启用 A/V 会议并使用会议策略来阻止视频会议。或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。 
    
    有关配置会议策略的详细信息，请参阅[在 Skype For Business 服务器中管理会议策略](../../manage/conferencing/conferencing-policies.md)。
    
    > [!NOTE]
    > 企业语音对于 A/V 会议不是必需的。如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。 
  
- **您是否希望让用户在使用 PSTN 手机时加入会议的音频部分？**
    
    如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。
    
    电话拨入式会议是一项可选功能，您可以在部署 Skype for Business Server 会议时进行配置。 虽然电话拨入式会议使用的某些组件与企业语音使用的组件相同，但是即使未部署企业语音，也可以部署电话拨入式会议。 电话拨入式会议支持企业用户和匿名用户。 有关为企业和匿名用户配置电话拨入式会议的详细信息，请参阅在 skype for business[服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)和[在 Skype for Business 服务器中配置电话拨入式会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
    
- **是否要允许使用 Skype for Business 客户端的外部用户加入会议？**
    
    通过允许外部参与会议，您可以在 Skype for Business 服务器中实现最大投资。 外部用户可能包括：
    
  - **远程用户。** 您的组织自己的用户在您的防火墙外工作，并且正在使用其笔记本电脑或其他 Skype for business 服务器设备。
    
  - **联盟用户。** 与其他人同时运行 Skype for Business 服务器的公司用户。 要使用户轻松与这些用户联系，应与这些公司建立联盟关系。
    
  - **匿名用户。** 用户专门邀请其加入特定会议的任何其他外部用户。 公司的会议组织者可以向外部用户发送电子邮件以邀请他们参加会议。 该电子邮件包含一个链接，外部用户通过单击该链接即可加入会议。
    
    如果想要允许外部用户，你需要部署 Edge 服务器。 此外，在部署边缘服务器后，可以与其他组织（如您的客户或供应商）建立联盟关系，这样，来自这些组织的用户便可以更轻松地与您的用户协作。
    
    有关部署边缘服务器的详细信息，请参阅“规划边缘服务器”和“部署边缘服务器”。 有关启用 Office Web Apps 服务器的外部 access 的详细信息，请参阅[在 Skype For Business 服务器中配置与 Office Web apps 集成服务器的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。
    
- **您是否想要控制可以加入 Skype for Business 服务器会议的客户？**
    
    如果是，则应配置与会页面，以便只有要支持的客户端选项可用。 每当用户单击链接加入计划的会议时，Skype for Business 服务器检测是否已在计算机上安装了客户端。 然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。 会议加入页面始终包含使用 Skype for Business Web 应用的选项。 除了此选项之外，还可以决定是否包含 Attendee 和早期版本 Communicator 的链接。 
    

