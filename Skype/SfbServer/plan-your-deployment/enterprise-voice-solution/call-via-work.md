---
title: 在 Skype for Business Server 中规划通过工位呼叫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 在 Skype for Business Server 中规划通过工号呼叫，这将支持 Skype for Business 与 PBX 电话系统集成，以便用户可以使用 Skype for Business 控制其 PBX 电话。
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825872"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>在 Skype for Business Server 中规划通过工位呼叫
 
在 Skype for Business Server 中规划通过工号呼叫，这将支持 Skype for Business 与 PBX 电话系统集成，以便用户可以使用 Skype for Business 控制其 PBX 电话。
  
 **通过工号** 呼叫是 Skype for Business Server 中的一项新功能，使你能够将 Skype for Business 解决方案与现有 PBX 电话系统集成。 启用了通过工位呼叫的用户可以在 Skype for Business 中单击以呼叫部署中的其他用户或外部用户。 呼叫使用用户的 PBX 电话完成。 这使具有 PBX 电话的用户能够将音频包括在丰富的 Skype for Business 对话中。 在早期版本的 Lync Server 远程呼叫控制中，该功能使用户能够使用 Lync Server 控制 PBX 电话。 在 Skype for Business Server 中，此功能已替换为通过工位电话呼叫功能。
  
通过工号呼叫为 PBX 电话用户启用以下功能
  
- 即点即用体验，通过 PBX 电话提供的音频。
    
- 状态、用户搜索和 IM 集成-例如，IM 会话中的两个通过工位呼叫的用户可以通过 PBX 电话提供的音频将音频添加到其会话。
    
- 能够将 IM、应用程序共享和文件传输添加到通过工位电话呼叫。
    
- 一键式会议加入功能
    
## <a name="how-it-works"></a>运作方式

通过工号呼叫使用统一通信 Web API (UCWA) 作为 PBX 系统和 Skype for Business Server 部署之间的后端用户代理 (B2BUA) ，因此无需计算机支持的电信应用程序 (CSTA) 网关将 Skype for Business Server 与 PBX 系统连接。 UCWA 是 Lync Server 早期版本中引入的一项服务，用于启用与移动和 Web 客户端的连接，并且会自动安装在每个前端服务器上。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>通过工位呼叫的呼叫工作流

下面说明了启用通过工位电话呼叫的用户如何使用 Skype for Business Server 进行呼叫：
  
![显示通过工位电话呼叫期间的步骤;首先，呼叫者单击呼叫 Skype for Business 客户端中的某人;然后 UCWA 将呼叫者的电话响铃。 呼叫者接听电话时，将呼叫收件人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. 用户在 Skype for Business 客户端中选择一个用户，然后单击电话图标以呼叫他们。 或者，在 IM 对话期间，用户单击以呼叫正在与用户进行会话的用户。
    
2. 拨打呼叫的用户的 PBX 电话开始响铃。 此电话的呼叫者 ID 显示已设置为显示在发出通过工号呼叫的所有用户的呼叫者 ID 中的全局电话号码。 此全局电话号码不是对应于任何一个人电话的实际电话号码。 相反，它是一个可视信号，用于让用户知道这是他们自己的传出呼叫，而不是同时发生的传入呼叫。 部署通过工号呼叫时，应该向这些用户说明此全局电话号码及其的含义。
    
3. 拨打呼叫的用户将接听其 PBX 电话。 Skype for Business 然后向被叫方发起语音呼叫。 
    
4. 当被叫方应答时，语音呼叫将开始。 如果两个用户已经在进行 IM 会话，它可以继续。
    
### <a name="joining-a-conference-with-call-via-work"></a>通过电话呼叫加入会议

通过工位电话呼叫用户可以通过单击会议 URL 加入安排的会议。 Skype for Business 随后将显示" **拨出** "消息，直到会议服务拨打用户的 PBX 电话。 然后，通过工号呼叫用户接听 PBX 电话并加入会议。
  
通过工位电话呼叫用户还可使用Skype for Business 中的"立即开会"选项创建"立即开会"会议。 然后，用户会看到 **"拨出"** 消息，并且 PBX 电话响铃。
  
通过工号拨号用户还可通过从 Skype for Business 内呼叫会议网桥号码来拨入会议。 如果需要会议 PIN，用户必须使用其 PBX 电话输入 PIN。
  
### <a name="incoming-calls"></a>传入呼叫

当启用了通过工号呼叫的用户收到 Skype for Business 呼叫时，如果用户设置了同时响铃 (则 PBX 电话和用户的 Skype for Business 客户端将同时) 。 用户可以通过接听 PBX 电话或单击 Skype for Business通知上的"接受"来接受呼叫。 如果用户使用 Skype for Business 接受呼叫，则呼叫的 Skype for Business 窗口保持打开状态。 但是，如果用户通过接听 PBX 电话接受呼叫，则 Skype for Business 通知窗口关闭，并且没有 Skype for Business 会话，仅通过 PBX 电话进行语音呼叫。
  
启用通过工号呼叫的用户收到 PBX 呼叫时，仅 PBX 电话响铃。
  
## <a name="limitations-of-call-via-work"></a>通过工次电话呼叫的限制

通过工位呼叫是一种语音解决方案，几乎不需要硬件设置，但与完整呼叫或远程呼叫控制企业语音功能相比，存在一些限制。 通过工次电话呼叫具有以下限制：
  
- 如果通过工号呼叫的用户设置了呼叫转发到"通过工号呼叫"回拨号码，并且有人尝试按用户的电话号码邀请该用户参加会议，则邀请将不会到达该用户。 应指导用户通过单击姓名而不是电话号码来邀请参与者参加会议。 
    
- 增强型 911 功能以及恶意呼叫跟踪在通过工号呼叫期间不可用。
    
- 启用了通过工位呼叫的用户无法使用委派、团队呼叫或响应组功能。
    
- 通过工位呼叫的用户无法使用 Skype for Business 录制会议、将呼叫静音或取消静音、保留或转接呼叫或使用呼叫等待。
    
- 用户无法使用通过工位电话访问其 PBX 语音邮件。
    
- 通过工号呼叫的用户无法将作为语音呼叫启动的会话升级至包含视频、Powerpoint、白板或 One Note 等通信的协作会议。
    
- 通过工号呼叫的用户无法向 2 人呼叫添加更多用户。
    
- 不支持桌面电话配对或 VDI 插件配对。
    
- 如果用户使用 PBX 电话应答或 (而未使用 Skype for Business) ，则没有呼叫日志。
    
- 如果您的 PBX 系统不支持 **REFER with Replaces，** 则会发生以下行为。 在通过工号呼叫时，如果用户从 PBX 电话转移正在进行的呼叫，则呼叫窗口不会从 Skype for Business 窗口消失。 如果用户随后关闭呼叫窗口，则转接目标与被转接人之间的呼叫将结束。 
    
## <a name="prerequisites-for-call-via-work"></a>通过工次电话呼叫的先决条件

若要为任何用户启用通过工位电话呼叫，必须具备一些先决条件。 有关这些先决条件以及如何为用户启用通过工号呼叫的步骤，请参阅[Deploy Call Via Work in Skype for Business Server 2015。](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 中规划远程呼叫控制](remote-call-control.md)
  
[在 Skype for Business Server 2015 中部署通过工号呼叫](../../deploy/deploy-call-via-work.md)

