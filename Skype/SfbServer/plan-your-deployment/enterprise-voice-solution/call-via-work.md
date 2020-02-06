---
title: 通过 Skype for Business Server 中的工作计划呼叫计划
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 通过 Skype for business Server 中的工作计划进行呼叫计划，从而支持 Skype for Business 和 PBX 电话系统之间的集成，以便用户可以使用 Skype for business 控制其 PBX 电话。
ms.openlocfilehash: 38c61145dcad609c75e7b2e3433efee307f8dc28
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803152"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>通过 Skype for Business Server 中的工作计划呼叫计划
 
通过 Skype for business Server 中的工作计划进行呼叫计划，从而支持 Skype for Business 和 PBX 电话系统之间的集成，以便用户可以使用 Skype for business 控制其 PBX 电话。
  
 **通过工作进行呼叫**是 Skype For business 服务器中的一项新功能，使你能够将 Skype for business 解决方案与现有的 PBX 电话系统集成。 通过工作启用呼叫的用户可以在 Skype for Business 中单击，以在部署或外部用户中调用其他用户。 将使用用户的 PBX 电话完成呼叫。 这使使用 PBX 手机的用户可以在其丰富的 Skype for business 对话中包含音频。 在早期版本的 Lync Server 远程呼叫控制中，支持用户使用 Lync Server 控制其 PBX 手机的功能。 在 Skype for Business 服务器中，此功能已替换为 "通过工作通话"。
  
通过工作进行呼叫为 PBX 电话用户启用以下功能
  
- 单击呼叫，通过 PBX 电话提供音频。
    
- 状态、用户搜索和 IM 集成-例如，通过 IM 会话中的工作用户进行两次通话可将音频添加到其会话中，使用 PBX 手机提供的音频。
    
- 通过工作呼叫向呼叫添加即时消息、应用程序共享和文件传输的功能。
    
- 一键式会议加入功能
    
## <a name="how-it-works"></a>运作方式

通过工作进行呼叫使用统一通信 Web API （UCWA）作为 PBX 系统和 Skype for Business Server 部署之间的后端到后用户代理（B2BUA），以便无需使用计算机支持的电信应用程序（CSTA）网关连接带有 PBX 系统的 Skype for business 服务器。 UCWA 是以前版本的 Lync Server 中引入的一种服务，可与移动设备和 web 客户端建立连接，并且会在每台前端服务器上自动安装。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>通过工作呼叫进行呼叫的通话工作流

以下示例说明了通过工作启用呼叫呼叫的用户可以使用 Skype for Business 服务器进行呼叫：
  
![显示单位电话呼叫通话期间的步骤；首先，呼叫者在 Skype for Business 客户端中单击呼叫某人；随后 UCMA 使呼叫者的电话响铃。在呼叫者拿起电话时，呼叫接收人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. 用户在其 Skype for Business 客户端中选择用户，然后单击 "电话" 图标以呼叫它们。 或者，在 IM 对话期间，用户通过单击呼叫正在与其进行会话的用户。
    
2. 发出呼叫的用户的 PBX 电话开始响铃。 此电话的来电显示方式显示您已设置为在通过工作电话拨打电话的所有用户的来电显示中显示的全球电话号码。 此全球电话号码不是与任何一人的电话相对应的实际电话号码。 相反，它是一个视觉信号，让用户知道这是其自己的传出呼叫，而不是同时发生的传入呼叫。 当您通过工作部署呼叫时，您应该向这些用户讲解此全球电话号码及其含义。
    
3. 拨打呼叫的用户拿起他们的 PBX 电话。 然后，Skype for Business 将开始对被呼叫方的语音呼叫。 
    
4. 当被呼叫方接听时，语音通话开始。 如果两个用户已有即时消息会话，则可以继续。
    
### <a name="joining-a-conference-with-call-via-work"></a>通过工作通过通话加入会议

通过单击会议 URL，通过工作用户的呼叫可加入计划会议。 然后，Skype for Business 将显示 "**拨出**" 消息，直到会议服务拨打用户的 PBX 电话。 通过工作用户进行呼叫，然后领取 PBX 电话并加入会议。
  
通过工作用户进行的通话还可以使用 Skype for Business 中的 "**立即开会**" 选项创建 "立即开会" 会议。 然后，用户看到 "**拨出到**" 消息和 PBX 电话响铃。
  
通过工作用户拨打的电话还可以通过从 Skype for Business 呼叫会议桥号码拨入会议。 如果需要会议 PIN，用户必须使用 PBX 电话输入 PIN 码。
  
### <a name="incoming-calls"></a>传入呼叫

通过工作启用呼叫呼叫的用户收到 Skype for Business 呼叫时，PBX 电话和用户的 Skype for Business 客户端同时拨打所有电话（如果用户已设置同时拨打）。 用户可以通过使用 PBX 手机或单击 Skype for Business 通知上的 "**接受**" 来接受呼叫。 如果用户使用 Skype for Business 接受呼叫，则通话的 Skype for business 窗口保持打开状态。 但是，如果用户通过 PBX 手机接受呼叫，则 Skype for business 通知窗口将关闭，并且没有 Skype for business 会话，只能通过 PBX 电话进行语音通话。
  
当启用通过工作呼叫呼叫的用户收到 PBX 呼叫时，仅使用 PBX 电话响铃。
  
## <a name="limitations-of-call-via-work"></a>通过工作的通话限制

通过工作进行呼叫是一种需要很少硬件设置的语音解决方案，但与完全企业语音或远程通话控制中提供的功能有一定限制。 通过工作拨打的电话有以下限制：
  
- 如果通过工作用户拨打电话时，通过工作回呼号码设置呼叫转移到呼叫，而有人试图邀请用户的电话号码邀请此用户加入会议，邀请将不会到达用户。 你应通过单击名称而不是电话号码，向用户提供邀请参与者加入会议的操作。 
    
- 通过工作电话进行呼叫时，增强的911功能和恶意呼叫跟踪不可用。
    
- 通过工作启用呼叫的用户不能使用委派、团队呼叫或响应组功能。
    
- 通过工作进行呼叫的用户无法使用 Skype for Business 录制会议、将呼叫设为静音或取消静音、保留或转接呼叫，或使用呼叫寄存。
    
- 用户无法使用呼叫通过工作来访问其 PBX 语音邮件消息。
    
- 通过工作进行呼叫的用户无法将作为语音呼叫启动的会话提升为包括视频、Powerpoint、白板或一个笔记等通信的协作会议。
    
- 通过工作呼叫的用户不能将更多用户添加到两人通话。
    
- 不支持 deskphone 配对或 VDI 插件配对。
    
- 如果用户使用 PBX 电话（而不是使用 Skype for Business 窗口）发出或应答呼叫，则不会有通话记录。
    
- 如果你的 PBX 系统不支持 "**替换**"，将发生以下行为。 通过工作呼叫进行呼叫时，如果用户通过 PBX 手机传送正在进行的呼叫，则呼叫窗口不会从其 Skype for Business 窗口中消失。 如果用户关闭呼叫窗口，则传送目标与 transferee 之间的通话将结束。 
    
## <a name="prerequisites-for-call-via-work"></a>通过工作进行通话的先决条件

若要允许任何用户通过工作进行呼叫，您必须准备好一些先决条件。 有关这些先决条件的详细信息，以及如何通过工作启用用户呼叫的步骤，请参阅[通过 Skype For Business Server 2015 部署呼叫](../../deploy/deploy-call-via-work.md)。 
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 中规划远程呼叫控制](remote-call-control.md)
  
[在 Skype for Business Server 2015 中部署单位电话呼叫](../../deploy/deploy-call-via-work.md)

