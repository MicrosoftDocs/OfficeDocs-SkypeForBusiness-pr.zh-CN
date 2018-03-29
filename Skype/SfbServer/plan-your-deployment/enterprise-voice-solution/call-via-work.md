---
title: 在 Skype for Business Server 2015 中规划单位电话呼叫
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 用于调用通过 Skype 在规划业务服务器，以便用户可以使用 Skype 业务来控制其 PBX 电话使业务的 Skype 和 PBX 电话系统之间的集成。
ms.openlocfilehash: d70ffb7cd46f5d2ffd7efe4db860f3a84ca34ef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-via-work-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划单位电话呼叫
 
用于调用通过 Skype 在规划业务服务器，以便用户可以使用 Skype 业务来控制其 PBX 电话使业务的 Skype 和 PBX 电话系统之间的集成。
  
 **调用通过工作**是 Skype，这使您可以与您现有的 PBX 电话系统集成业务解决方案您 Skype 业务服务器中的新功能。 启用呼叫通过工作的用户可以单击中业务调用另一个用户，或者在您的部署或外部用户的 Skype。 呼叫使用用户的 PBX 电话完成。 这使得具有 PBX 电话的用户在其丰富的业务对话 Skype 包含音频。 在以前版本的 Lync 服务器远程调用控制是一种功能，使用户能够控制手机 PBX Lync Server。 在 Skype 业务服务器，此功能已被调用通过工作。
  
调用通过工作使下面的 PBX 电话用户
  
- 单击呼叫，通过 PBX 电话提供音频。
    
- 状态、 用户搜索和 IM 集成--例如，两个调用通过工作用户 IM 会话中的可以添加音频到他们的会话，通过 PBX 电话提供音频。
    
- 通过工作调用调用添加即时消息、 应用程序共享和文件传输的能力。
    
- 一键式会议加入功能
    
## <a name="how-it-works"></a>运作方式

调用通过工作使用统一通信 Web API (UCWA) 作为 PBX 系统和您 Skype 之间的背对背的用户代理 (B2BUA) 业务服务器部署中，因此连接所需的任何计算机支持的电信应用程序 (CSTA) 网关PBX 系统具有的业务服务器的 Skype。 UCWA 是 Lync 服务器以启用移动与连接性和 web 客户端的前一版本中引入的服务，将自动安装在每个前端服务器上。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>通过工作中调用调用工作流

以下说明了启用调用通过工作的用户如何使用 Skype 业务服务器进行调用：
  
![显示单位电话呼叫通话期间的步骤；首先，呼叫者在 Skype for Business 客户端中单击呼叫某人；随后 UCMA 使呼叫者的电话响铃。在呼叫者拿起电话时，呼叫接收人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. 用户在其 Skype 业务客户端，选择用户并单击电话图标，可以给他们打电话。 或者，在 IM 对话期间，用户通过单击呼叫正在与其进行会话的用户。
    
2. 用户发出调用的 PBX 电话开始响。 此电话的来电显示您已设置在呼叫调用通过工作的所有用户的来电显示全局的电话号码。 此全局电话号码不是一个实际的电话号码对应于任何一个人的电话。 相反，它是视觉信号，让用户知道这是他们自己传出的呼叫，并不在同一时间发生的传入呼叫。 调用通过工作部署时，应提醒这些用户了解此全局电话号码以及它意味着什么。
    
3. 拨打呼叫的用户拿起他们的 PBX 电话。 接着，Skype 业务启动语音呼叫到被调用方。 
    
4. 被叫方接听时，将开始语音呼叫。如果两位用户已经在进行 IM 会话，则会话将继续。
    
### <a name="joining-a-conference-with-call-via-work"></a>使用通过工号拨号加入会议

通过工作中调用用户可以通过单击会议 URL 加入计划的会议。 Skype 业务直到会议服务拨打用户的 PBX 电话然后将显示**为拨出**的消息。 通过工作中调用用户然后选取 PBX 电话并加入会议。
  
通过工作中调用用户可以使用**立即开会**选项在 Skype 业务创建立即开会的会议 然后用户会看到“**正在外拨**”消息，PBX 电话开始响铃。
  
通过工作中调用用户可以还拨入会议通过调用业务会议桥接器号码 Skype。 如果需要会议 PIN，用户必须使用他们的 PBX 电话输入 PIN。
  
### <a name="incoming-calls"></a>传入呼叫

当启用用户调用通过工作将接收所有环同时 （如果用户设置同时振铃） 的业务客户端业务呼叫、 PBX 电话和 Skype 用户的 Skype。 用户可以接受通过拨打电话 PBX 或单击**接受**业务通知 Skype 上的调用。 如果用户接受的业务使用 Skype 呼叫，Skype 呼叫业务窗口保持打开状态。 但如果用户接受的拿起 PBX 电话呼叫，Skype 业务通知窗口将关闭，并没有任何 Skype 业务会话，只通过 PBX 电话语音呼叫。
  
当用户调用通过工作为启用接收 PBX 电话，PBX 电话响铃。
  
## <a name="limitations-of-call-via-work"></a>工作通过呼叫限制

调用通过工作是一种语音解决方案，需要进行很少的硬件设置，但是有比较完整的企业语音或远程呼叫控制中可用的功能的限制。 调用通过工作有以下限制：
  
- 如果调用通过工作用户设置呼叫转移到调用通过工作回拨号码，并且有人试图邀请此用户访问该用户的电话号码通过会议，邀请将不会到达用户。 你应指导你的用户通过单击姓名（而非电话号码）邀请参与者加入会议。 
    
- 911 的增强的能力和恶意调用跟踪的工作通过调用调用期间不可用。
    
- 启用的工作通过调用用户不能使用委派、 团队调用或响应功能进行分组。
    
- 调用通过工作的用户无法使用 Skype 业务要录制会议，静音或取消静音通话、 存放或转接呼叫，或者使用调用公园。
    
- 用户不能使用调用通过工作来访问他们 PBX 的语音邮件消息。
    
- 用户调用通过工作的不能升级作为协作会议，其中包括通信，如视频，Powerpoint，白板或一个注意语音呼叫启动一个会话。
    
- 调用通过工作的用户不能添加更多用户，对 2 人联络。
    
- 不支持桌面电话配对或 VDI 插件配对。
    
- 如果用户使或应答呼叫使用 PBX 电话 （而非使用 Skype 业务窗口） 时，将调用的任何日志。
    
- 如果你的 PBX 系统不支持 **REFER with Replaces**，将发生以下行为。 在调用通过工作调用中，如果用户从 PBX 电话转移正在进行呼叫，呼叫窗口将不会消失从其 Skype 业务窗口。 如果用户随后关闭呼叫窗口，转接目标和受让方之间的呼叫将终结。 
    
## <a name="prerequisites-for-call-via-work"></a>通过工作的呼叫的先决条件

要启用所有用户的调用通过工作，必须在地方一些必备。 了解更多有关这些系统必备组件，以及如何启用用户调用通过工作的步骤，请参阅[部署调用通过工作中的业务服务器 2015 Skype](../../deploy/deploy-call-via-work.md)。 
  
## <a name="see-also"></a>另请参阅

#### 

[远程呼叫控制下的企业 2015年的 Skype 的计划](remote-call-control.md)
  
[部署工作在 Skype 业务服务器 2015年通过调用](../../deploy/deploy-call-via-work.md)

