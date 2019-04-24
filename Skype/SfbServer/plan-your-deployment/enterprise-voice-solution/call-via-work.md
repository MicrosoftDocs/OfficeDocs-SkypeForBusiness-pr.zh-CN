---
title: 规划用单位电话的 Skype 业务服务器的呼叫
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 用于呼叫通过 Skype 中规划 Business Server，这样可使 for Business 的 Skype 和 PBX 电话系统，之间的集成，以便用户可以使用 for Business 的 Skype 控制其 PBX 电话。
ms.openlocfilehash: 3a2452f732d55f305d91cee9cd2b940f7bb3c88e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207242"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>规划用单位电话的 Skype 业务服务器的呼叫
 
用于呼叫通过 Skype 中规划 Business Server，这样可使 for Business 的 Skype 和 PBX 电话系统，之间的集成，以便用户可以使用 for Business 的 Skype 控制其 PBX 电话。
  
 **通过单位电话呼叫**中的业务服务器，它可以与您现有的 PBX 电话系统集成业务解决方案您 Skype Skype 的新功能。 启用呼叫通过单位电话的用户可以单击 for Business 呼叫另一个用户，可以在部署或外部用户的 Skype 中。 将使用用户的 PBX 电话完成呼叫。 这样 PBX 电话与用户在其丰富 Skype 业务对话中包括音频。 在早期版本的 Lync Server 远程呼叫控制是一种功能，允许用户控制其 PBX 电话与 Lync Server。 在业务服务器 Skype，此功能已取代与通过单位电话呼叫。
  
通过单位电话呼叫启用 PBX 电话用户的以下
  
- 单击呼叫，通过 PBX 电话提供音频。
    
- 状态、 用户搜索和 IM 集成-例如，在 IM 会话中的两个呼叫通过单位电话用户可以添加音频到他们的会话，与 PBX 电话通过提供音频。
    
- 向呼叫通过单位电话呼叫添加即时消息、 应用程序共享和文件传输功能。
    
- 一键式会议加入功能
    
## <a name="how-it-works"></a>运作方式

通过单位电话呼叫使用统一通信 Web API (UCWA) 作为背对背用户代理 (B2BUA) PBX 系统之间您 Skype 业务服务器部署中，以便连接所需的任何计算机支持的电信应用 (CSTA) 网关为业务 Server 与 PBX 系统的 Skype。 UCWA 是在早期版本的 Lync Server 启用 mobile 连接和 web 客户端中, 引入的一个服务，并且每个前端服务器上自动安装。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>调用通过单位电话呼叫的呼叫工作流

以下说明了如何启用呼叫通过单位电话的用户可以使用业务服务器 Skype 发起呼叫：
  
![显示单位电话呼叫通话期间的步骤；首先，呼叫者在 Skype for Business 客户端中单击呼叫某人；随后 UCMA 使呼叫者的电话响铃。在呼叫者拿起电话时，呼叫接收人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. 用户在其 Skype 业务客户端中选择用户，然后单击电话图标来呼叫该联系人。 或者，在 IM 对话期间，用户通过单击呼叫正在与其进行会话的用户。
    
2. 发出呼叫的用户的 PBX 电话开始振铃。 此电话的呼叫者 ID 显示您已设置为显示中的所有用户发起通过单位电话呼叫的呼叫的呼叫者 ID 全局电话号码。 此全局电话号码不是对应于任何人电话实际电话号码。 相反，它是一个可视信号，以使用户可以知道这是他们自己的传出呼叫，并不传入呼叫同时发生。 在部署通过单位电话呼叫时，您应告知有关此全局电话号码和含义的那些用户。
    
3. 拨打呼叫的用户拿起他们的 PBX 电话。 Skype for Business 然后发起语音呼叫到被叫方。 
    
4. 被叫方应答时，将开始语音呼叫。 如果两个用户已经有转 IM 会话，它可以继续。
    
### <a name="joining-a-conference-with-call-via-work"></a>加入使用单位电话呼叫会议

调用通过单位电话用户可以通过单击会议 URL 加入预定的会议。 Skype for Business 之前的会议服务拨打该用户的 PBX 电话，然后显示**拨出**的邮件。 调用通过单位电话用户然后拿起 PBX 电话和加入会议。
  
呼叫通过单位电话用户可以还使用**立即开会**选项中的业务的 Skype 创建立即开会会议。 然后，用户看到的**拨出**消息和 PBX 电话振铃。
  
呼叫通过单位电话用户可以还拨入会议通过调用 for Business 内 Skype 中的会议桥号。 如果需要会议 PIN，用户必须使用其 PBX 电话输入 PIN。
  
### <a name="incoming-calls"></a>传入呼叫

时启用的用户呼叫通过单位电话的所有拨打同时 （如果用户已设置同时响铃） 的业务客户端接收业务呼叫、 在 PBX 电话与用户的 Skype 的 Skype。 用户可以接受通过拿起 PBX 电话，或单击上的业务通知 Skype**接受**呼叫。 如果用户接受 for Business 使用 Skype 调用，用于呼叫的业务窗口 Skype 保持打开状态。 但是，如果用户接受拿起 PBX 电话的呼叫，然后关闭业务通知窗口 Skype 和业务会话，只能通过 PBX 电话的语音呼叫没有任何 Skype。
  
当启用呼叫通过单位电话的用户收到 PBX 的呼叫，仅 PBX 电话响铃。
  
## <a name="limitations-of-call-via-work"></a>用单位电话呼叫的限制

通过单位电话呼叫是语音解决方案的要求很少硬件设置，但具有完整的企业语音还是远程呼叫控制中可用的功能与相比的限制。 通过单位电话呼叫具有以下限制：
  
- 如果某人尝试邀请此用户加入会议的用户的电话号码的呼叫通过单位电话用户已设置为通过单位电话呼叫回拨号码的呼叫转接，邀请将不会到达用户。 您应告知用户通过单击该名称，而非电话号码邀请参与者加入会议。 
    
- 增强型 911 的功能和恶意呼叫跟踪呼叫通过单位电话呼叫过程中不可用。
    
- 启用呼叫通过单位电话的用户无法使用委派、 团队呼叫或响应组功能。
    
- 呼叫通过单位电话的用户无法使用 for Business 的 Skype 录制会议，设置为静音或取消静音呼叫、 保留或转接呼叫，或使用呼叫寄存。
    
- 用户不能使用呼叫通过单位电话访问其 PBX 的语音邮件。
    
- 呼叫通过单位电话的用户无法升级到协作会议包含视频，Powerpoint 白板，如 communications 或一个注释语音呼叫作为启动会话。
    
- 呼叫通过单位电话的用户不能向 2 人呼叫中添加更多的用户。
    
- 不是支持桌面电话配对或 VDI 插件配对。
    
- 如果用户使或应答呼叫使用 PBX 电话 （和不使用 Skype 业务窗口），将呼叫无日志。
    
- 如果 PBX 系统不支持**与替换的引用**，将发生以下行为。 在呼叫通过单位电话呼叫中，如果用户从 PBX 电话转移正在进行的呼叫，呼叫窗口将不会消失从其 Skype 业务窗口。 如果用户然后关闭呼叫窗口，将结束传输目标与接受方之间的呼叫。 
    
## <a name="prerequisites-for-call-via-work"></a>用单位电话呼叫的先决条件

若要启用呼叫通过单位电话的任何用户，您必须就地一些必备组件。 有关这些先决条件，以及如何为用户启用呼叫通过单位电话的步骤，请参阅[部署呼叫通过单位电话的业务服务器 2015 Skype 中](../../deploy/deploy-call-via-work.md)。 
  
## <a name="see-also"></a>另请参阅

[Plan for Business 的 Skype 中的远程呼叫控制](remote-call-control.md)
  
[在 Skype for Business Server 2015 中部署单位电话呼叫](../../deploy/deploy-call-via-work.md)

