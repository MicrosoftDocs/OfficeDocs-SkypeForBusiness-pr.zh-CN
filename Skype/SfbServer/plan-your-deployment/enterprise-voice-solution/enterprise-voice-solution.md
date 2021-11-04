---
title: 在企业语音中规划Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f9c6fd1d-c379-47d1-8447-19274ace9951
description: 摘要：了解在 Skype for Business Server 中规划统一语音和通信解决方案Skype for Business Server。
ms.openlocfilehash: 2cd47f1b3655166ced3bec5591a7b8197639544a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749951"
---
# <a name="plan-your-enterprise-voice-solution-in-skype-for-business-server"></a>在企业语音中规划Skype for Business Server
 
**摘要：** 了解在 Skype for Business Server 中规划统一语音和通信解决方案Skype for Business Server。
  
Skype for Business Server 提供了两个本地 企业语音 选项（企业语音 和单位电话呼叫）用于将组织的电话系统与 Skype for Business Server 部署集成，从而提供真正的统一通信解决方案。 这两个选项都允许用户使用 Skype for Business 客户端与组织内外的其他用户发起语音呼叫。
  
还可以同时使用 企业语音 和通过工电话呼叫。
  
- 企业语音是最完整的语音服务。 它是一种由软件提供支持的 IP 语音 (VoIP) 解决方案，提供一个非常丰富的功能集，包括与 Outlook 和 Exchange 的丰富集成，以及许多强大的功能，如响应组、呼叫停止、团队呼叫、组内呼叫应答和增强型紧急 E9-1-1 支持。 通过企业语音，用户可以使用音频设备（如耳机）和计算机或支持 VoIP 的电话，而不是传统的 PSTN 或 PBX 电话。
    
- 通过工号呼叫提供了一种将 Skype for Business 解决方案与现有 PBX 电话系统集成的方法。 启用了通过工位呼叫的用户可以通过单击Skype for Business呼叫其他用户，无论是部署内部用户还是外部用户。 使用用户的 PBX 电话完成呼叫。 此外，这些用户可以单击Skype for Business加入会议。
    
    对于仍拥有 PBX 电话但正在转换到 企业语音 的用户，部署通过工号呼叫也是一项好处，因为它使这些用户能够使用 Skype for Business 客户端控制其电话呼叫。
    
     通过工位呼叫提供一组比企业语音更加有限的语音功能。 例如，它不支持委派、团队呼叫、响应组或增强型 E9-1-1。
    
当然，您可以为一些用户启用 企业语音而其他用户使用的是 PBX 电话。 此外，在转换到完整企业语音解决方案时，您可以为仍具有 PBX 电话的用户启用企业语音。 这些用户可以在办公地点使用 PBX 电话，还可在企业语音使用 VoIP 设备拨打或接听呼叫。 如果为这些用户启用了"通过工号呼叫"功能，他们可以使用其 Skype for Business 客户端在办公室控制其 PBX 电话。
  
> [!NOTE]
> 远程呼叫控制是 Lync Server 早期版本中提供的一项功能，允许用户使用 Skype for Business 客户端在 PBX 电话上拨打和接听电话呼叫。 远程呼叫控制不受 Skype for Business Server 服务器上用户的支持，但具有 Skype for Business 客户端的用户仍位于运行 Lync Server 2013 的服务器上。 
  
## <a name="see-also"></a>另请参阅


[规划企业语音Skype for Business Server](enterprise-voice.md)
  
[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[规划远程呼叫控制Skype for Business](remote-call-control.md)

