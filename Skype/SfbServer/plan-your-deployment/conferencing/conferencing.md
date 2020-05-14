---
title: 在 Skype for Business Server 中规划会议
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
description: 摘要：阅读本主题，了解 Skype for Business Server 中的会议特性和功能。
ms.openlocfilehash: 1c67eecda6c7691dfbb042f4743733b73864a426
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221162"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中规划会议
 
**摘要：** 阅读本主题，了解 Skype for Business Server 中的会议特性和功能。
  
Skype for Business Server 中的会议允许用户使用其 Skype for business 客户端在线开会和召开会议，而不是每个人都在同一个聊天室中进行协作。 会议参与者可以通过其 Skype for Business 客户端连接到会议以获取完整的音频和视频体验，也可以使用电话拨入会议。 会议还支持即时消息、桌面和应用程序共享以及交互式白板。
  
本主题包括以下部分：
  
- 会议特性和功能
    
- 会议组件
    
- 会议策略
    
- 对大型会议的支持
    
- 确定组织的需求
    
## <a name="conferencing-features-and-capabilities"></a>会议特性和功能

Skype for Business Server 中提供了四种类型的会议： web 会议、音频和视频（A/V）会议、电话拨入式会议和即时消息（IM）会议。 
  
您可以选择启用所有会议类型，或仅使用一种类型，具体取决于您的需要。 例如，您可以启用所有类型（包括电话拨入式会议），以允许无法加入具有 Skype for Business 客户端的会议的用户呼叫并参与电话中的会议音频。 部署 Skype for Business Server 时，会自动部署 IM 会议功能;您可以使用拓扑生成器来指定是否部署 web、A/V 和电话拨入式会议。 有关详细信息，请参阅[在 Skype For Business Server 中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。 
  
以下各小节介绍了每种会议类型的特性和功能。
  
### <a name="web-conferencing"></a>Web 会议

通过 Web 会议，会议与会者可以在会议期间共享的文档进行协作，并且会议演示者可以通过 Skype for Business 客户端共享应用程序。 Web 会议提供以下功能： 
  
- **白板和批注。** 白板是一个空白画布，可用于借助文本、墨迹、图形和图像进行协作。 所有与会者都可看到在白板上所做的注释。 白板功能使与会者能够交流想法、集体讨论、做笔记等，从而增进协作。
    
- **投票.** 轮询功能使演示者能够快速确定参与者的首选项，从而增强协作功能。 在联机会议和对话过程中，演示者可以使用轮询从参与者收集匿名响应。 所有演示者都可以看到结果，并可以向所有与会者隐藏或显示结果。
    
- **应用程序共享和桌面共享。** 在会议期间，会议演示者可以在多监视器环境中共享其整个桌面、单个应用程序或单个监视器。 除了仅查看内容之外，会议中的其他参与者还可以请求对演示者屏幕的控制，并通过权限与内容进行交互（包括滚动和编辑）。 会议参与者还可以作为演示者接管，并在会议期间开始共享内容。
    
- **PowerPoint 共享。** 允许用户通过 Office Web Apps server 在会议中共享 PowerPoint 演示文稿，这允许：
    
  - 高分辨率显示和支持 PowerPoint 功能，例如动画、幻灯片切换和嵌入的视频。
    
  - 移动设备可以访问这些演示文稿。
    
  - 具有适当权限的用户可以独立于演示文稿本身在 PowerPoint 演示文稿中滚动。 例如，当 Ken 演示幻灯片放映时，Heidi 可以查看她想要的任何幻灯片，而不会影响 Ken 的演示文稿。
    
### <a name="audio-and-video-conferencing"></a>音频和视频会议

音频和视频会议允许在会议中进行音频和视频。 通过音频，与会者可以相互对话，就好像它们位于同一聊天室中一样。 视频在 Skype for Business 客户端中为加入会议的任何与会者或演示者（可支持视频的网络摄像机或会议设备）启用视频显示。
  
 Skype for Business Server 提供了多项功能，用户可以使用这些功能为用户配置音频会议体验，其中包括以下内容：
  
- **访问群体静音。** 演示者可以使用此设置将会议中的所有音频参与者设为静音，并将会议置于非演示者无法自行取消静音的状态中。
    
- **会议进入/退出通知。** 如果已启用电话拨入式会议，演示者可以使用此设置打开或关闭 "进入和退出通知" 以最大限度地减少打扰，同时进行会议。
    
- **通过拨出来添加用户。** 向其授予权限的演示者和与会者可以向会议中添加 PSTN 号码，并让会议拨出到这些号码。
    
  Skype for Business Server 提供了多项功能，用户可以使用这些功能为用户配置视频会议体验，其中包括以下内容：
  
- **库视图。** 在包含两人以上的视频会议中，用户可自动查看会议中的所有人。 如果会议具有五个以上的参与者，则最活跃的参与者的视频显示在顶部行中，并且只有照片显示给其他参与者。 默认情况下，多方视频处于打开状态。
    
- **全景视频。** 如果在会议室中安装了圆桌会议视频会议设备，此功能将提供会议室的完整360度视图。 全景视频条仅适用于圆桌会议设备。
    
- **仅演示者视频模式。** 演示者可以对会议进行配置，以便仅显示来自演示者的视频。 当多个视频流可用且锁定到不同的源时，这将阻止大型会议中的打扰。 此模式还适用于由圆桌会议设备捕获和提供的视频。
    
- **视频聚焦。** 演示者可以对会议进行配置，以便会议中的其他参与者只能看到来自所选参与者的视频源中的视频。 此模式还适用于由圆桌会议设备为全景视频捕获和提供的视频。
    
### <a name="dial-in-conferencing"></a>电话拨入式会议

通过电话拨入会议，电话拨入式会议允许与会者加入会议的音频部分。 电话拨入式会议是音频会议的一部分且需要其他配置。 有关电话拨入式会议的详细信息，请参阅在 skype for [Business server 中规划电话拨入式会议](dial-in-conferencing.md)和[在 Skype for Business server 中配置电话拨入式会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)。 
  
### <a name="instant-messaging-conferencing"></a>即时消息会议

即时消息（IM）会议允许两个以上的参与方在单个 IM 会话中进行通信。 有关 IM 会议的详细信息，请参阅[Plan for 即时消息和状态在 Skype For Business Server 中](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
## <a name="conferencing-components"></a>会议组件

支持会议功能的组件包括以下各项：
  
- **应用程序服务。** 应用程序服务提供了用于部署、托管和管理统一通信（UC）应用程序的平台。 电话拨入式会议使用两个需要应用程序服务的 UC 应用程序：会议助理和会议通知。 默认情况下，在前端池中的每台前端服务器上安装和激活应用程序服务。 它还安装在每个 Standard Edition 服务器上，以启用和配置电话拨入式会议。
    
- **会议助理应用程序。** 会议助理应用程序是一个统一通信应用程序，它接受公共交换电话网络（PSTN）呼叫、播放提示，并将呼叫加入 A/V 会议。 在启用电话拨入式会议时，默认情况下会安装和激活会议助理应用程序。
    
- **会议通知应用程序。** 会议通知应用程序是一个统一通信应用程序，它在特定操作上对 PSTN 参与者播放声音和提示，例如当参与者加入会议或离开会议时，参与者的状态为静音或 unmuted，某人进入了会议会议厅，或者会议已锁定或解除锁定。 会议通知应用程序还支持电话键盘中的双音多频（DTMF）命令。 启用电话拨入式会议时，默认情况下会自动安装并激活会议通知应用程序。
    
- **"电话拨入式会议设置" 页。** "电话拨入式会议设置" 页显示会议拨入号码及其可用语言、分配的会议信息（即，对于不需要安排的会议）以及会议 DTMF 控制，并支持对个人标识号（PIN）和分配的会议信息的管理。 "电话拨入式会议设置" 页将作为 Web 服务的一部分自动安装。
    
- **中介服务器和 PSTN 网关。** 电话拨入式会议要求中介服务器转换 Skype for Business Server 和 PSTN 网关之间的信号（和某些配置中的媒体），以及在中介服务器和 PSTN 网关之间转换信号和媒体的 PSTN 网关。 对于电话拨入式会议，必须至少部署一个中介服务器和以下至少一个：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
  > [!NOTE]
  > 如果还部署企业语音，中介服务器和 PSTN 网关是企业语音部署的一部分。 如果不部署企业语音，则需要为电话拨入式会议部署至少一台中介服务器，以及至少一个 PSTN 网关、IP-PBX 或 SBC。 
  
- **文件存储。** 文件存储用于记录的名称音频文件。 文件存储是每个 Enterprise Edition 或 Standard Edition 部署中的一个标准组件。
    
- **用户存储。** 用户存储用于存储用户的 Skype for Business 服务器 Pin。 对 Pin 进行哈希处理。 用户存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。
    
- **Office Web Apps 服务器。** 为了使用 web 会议功能，管理员必须安装 Office Web Apps Server，并且必须将 Skype for Business Server 配置为与 Office Web Apps Server 进行通信。
    
## <a name="conferencing-policies"></a>会议策略

若要强制实施组织的策略并控制带宽使用情况，可以为用户可组织的会议类型设置策略。 您可以定义各种各样的会议策略，并将它们分配给各个用户和用户组。 还可以设置用于管理对等对话的策略。 有关设置会议策略的详细信息，请参阅[在 Skype For Business Server 中管理会议策略](../../manage/conferencing/conferencing-policies.md)。 有关带宽管理的详细信息，请参阅[在 Skype For Business Server 中规划呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
## <a name="support-for-large-meetings"></a>对大型会议的支持

Skype for Business Server 可以支持的会议大小取决于会议是否托管在共享或专用池上：
  
- 在共享池上，Skype for Business Server 可以托管最高为250个用户的会议。 共享池是承载所有 Skype for Business Server 工作负荷（包括即时消息（IM）和状态、会议和企业语音）的池。 
    
- 在专用池上，Skype for Business Server 可以通过 web 和音频/视频（A/V）会议（包括共享 PowerPoint 演示文稿）支持最高为1000个参与者的会议。 若要实现此支持，需要配置一个专用池以支持大型会议，并且需要以某种方式管理该池以确保一次仅主持一个大型会议。 
    
有关管理大型会议的详细信息，请参阅[在 Skype For Business Server 中规划大型会议](large-meetings.md)。
  
如果您的组织需要更大的会议功能，应考虑实施一个使用 Skype 会议直播的混合环境，该环境是 Microsoft 365 和 Office 365 中的一种联机服务。 通过 Skype 会议直播，用户可以将会议托管和广播到最多为10000个参与者的大型 online 访问群体。 使用 Skype 会议广播要求已在混合设置中使用生产 Microsoft 365 或 Office 365 组织配置 Skype for Business Server。 所有用户必须具有作为先决条件建立的联机租户。 如果您希望部署可利用 Skype 会议直播的混合解决方案，请参阅[为 Skype 会议直播配置本地部署](../../deploy/configure-skype-meeting-broadcast.md)。
  
## <a name="determine-your-organizations-needs"></a>确定您的组织需要

在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。 下面的列表引导您完成会议规划过程，以根据您的组织的要求确定应部署的会议功能。
  
> [!NOTE]
> 在部署时启用会议时，将自动启用 web 和 A/V 会议。 但是，您可以按照本主题前面所述，通过配置会议策略来禁用特定功能。 
  
- **是否要启用包括文档协作和应用程序共享的 Web 会议？**
    
    如果是这样，则必须通过使用规划工具或使用拓扑生成器为前端池启用会议。 有关详细信息，请参阅[在 Skype For Business Server 中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
    
    与文档协作相比，应用程序共享要求使用更多的网络带宽。 Skype for Business Server 提供控制每个应用程序共享会话的限制机制。 默认情况下，每个会话设置为 1.5 KB/秒。 如果您不想启用应用程序共享，但需要文档协作，则可以启用会议并使用会议策略来禁用应用程序共享。 有关配置会议策略的详细信息，请参阅[在 Skype For Business Server 中管理会议策略](../../manage/conferencing/conferencing-policies.md)。
    
    若要使用户能够共享 PowerPoint 演示文稿，您需要配置 Office Web Apps Server。 有关配置 Office Web Apps Server 的详细信息，请参阅[Configure integration With Office Web Apps server In Skype For Business server](../../deploy/deploy-conferencing/office-web-app-server.md)。
    
- **是否要启用音频和视频会议？**
    
    如果是这样，则必须通过使用规划工具或使用拓扑生成器为前端池启用会议。 有关详细信息，请参阅[在 Skype For Business Server 中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。
    
    音频和视频会议要求和使用比 web 会议更多的网络带宽（包括文档协作和应用程序共享）。 如果您不想启用音频和视频会议，但希望启用 web 会议，则可以启用会议并使用会议策略来禁用 A/V 会议。
    
    如果想要启用音频会议，而不是视频会议，则可以启用 A/V 会议并使用会议策略来阻止视频会议。 或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。 
    
    有关配置会议策略的详细信息，请参阅[在 Skype For Business Server 中管理会议策略](../../manage/conferencing/conferencing-policies.md)。
    
    > [!NOTE]
    > 您无需使用企业语音即可使用 A/V 会议。 如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。 
  
- **使用 PSTN 电话时，是否要允许用户加入会议的音频部分？**
    
    如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。
    
    电话拨入式会议是一项可选功能，可在部署 Skype for Business Server 会议时进行配置。 虽然电话拨入式会议使用企业语音使用的某些组件，但即使不部署企业语音，也可以部署电话拨入式会议。 电话拨入式会议支持企业用户和匿名用户。 有关为企业和匿名用户配置电话拨入式会议的详细信息，请参阅在 skype for [Business server 中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)和[在 Skype for Business server 中配置电话拨入式会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
    
- **是否要让具有 Skype for Business 客户端的外部用户加入会议？**
    
    通过允许外部参与会议，可以最大限度地提高 Skype for business Server 的投资。 外部用户可能包括：
    
  - **远程用户。** 您的组织自己的用户，在防火墙外工作并使用其便携式计算机或其他 Skype for Business Server 设备时。
    
  - **联合用户。** 公司的用户也可以与其他人一起运行 Skype for Business Server。 若要使您的用户能够轻松地与这些用户联系，您可以创建与这些公司的联盟关系。
    
  - **匿名用户。** 您的用户专门邀请其加入特定会议的任何其他外部用户。 公司中的会议组织者可以向外部用户发送会议的电子邮件邀请。 该电子邮件包含外部用户可单击以加入会议的链接。
    
    如果要允许外部用户，则需要部署边缘服务器。 此外，在部署了边缘服务器的情况下，你可以与其他组织（例如客户或供应商）创建联合关系，并且这些组织中的用户可以更轻松地与你的用户进行协作。
    
    有关部署边缘服务器的详细信息，请参阅 Plan for Edge Servers and Deploy Edge Servers。 有关启用 Office Web Apps Server 外部访问的详细信息，请参阅[Configure integration With Office Web Apps server In Skype For Business server](../../deploy/deploy-conferencing/office-web-app-server.md)。
    
- **是否要控制可加入 Skype for Business Server 会议的客户端？**
    
    如果是，则应配置与会页面，以便只有要支持的客户端选项可用。 用户每次单击链接加入计划的会议时，Skype for Business Server 都会检测是否已在计算机上安装了客户端。 然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。 会议加入页面始终包含使用 Skype for Business Web 应用的选项。 除了此选项之外，您还可以决定是否包括与会者的链接和以前版本的 Communicator。 
    

