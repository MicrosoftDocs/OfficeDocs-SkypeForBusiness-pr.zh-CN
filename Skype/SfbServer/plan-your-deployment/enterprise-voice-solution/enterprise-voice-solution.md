---
title: 在 Skype for Business Server 企业语音解决方案
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
ms.assetid: f9c6fd1d-c379-47d1-8447-19274ace9951
description: 摘要：了解在 Skype for Business Server 中规划统一语音和通信解决方案的选项。
ms.openlocfilehash: 7f335fd3fe954e7a0e66381da9dad0748ee02905
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825722"
---
# <a name="plan-your-enterprise-voice-solution-in-skype-for-business-server"></a>在 Skype for Business Server 企业语音解决方案
 
**摘要：** 了解在 Skype for Business Server 中规划统一语音和通信解决方案的选项。
  
Skype for Business Server 提供了两种本地 企业语音 选项，即 企业语音 和单位电话呼叫，用于将组织的电话系统与 Skype for Business Server 部署集成，从而获得真正的统一通信解决方案。 这两个选项都允许用户使用其 Skype for Business 客户端与组织内外的其他用户发起语音呼叫。
  
还可以同时使用企业语音和通过工电话呼叫。
  
- 企业语音是最完整的语音服务。 它是一个支持软件的 IP 语音 (VoIP) 解决方案，提供非常丰富的功能集，包括与 Outlook 和 Exchange 的丰富集成，以及许多强大的功能，如响应组、呼叫停止、团队呼叫、组内呼叫应答和增强型紧急 E9-1-1 支持。 通过企业语音，用户可以使用音频设备（如带计算机的耳机）或支持 VoIP 的电话，而不是传统的 PSTN 或 PBX 电话。
    
- 通过工号呼叫提供了一种将 Skype for Business 解决方案与现有 PBX 电话系统集成的方法。 启用了通过工位呼叫的用户可以在 Skype for Business 中单击以呼叫部署中的其他用户或外部用户。 呼叫使用用户的 PBX 电话完成。 此外，这些用户可以在 Skype for Business 中单击以加入会议。
    
    对于仍拥有 PBX 电话但正在转换到 企业语音 的用户来说，部署通过工号呼叫也是一项好处，因为它使这些用户能够使用其 Skype for Business 客户端来控制其电话呼叫。
    
     通过工次电话呼叫提供比企业语音更为有限的一组语音功能。 例如，它不支持委派、团队呼叫、响应组或增强型 E9-1-1。
    
当然，您可以为一些用户启用企业语音而其他用户使用的是 PBX 电话。 此外，在转换到完整企业语音解决方案时，您可以启用仍具有 PBX 电话的用户企业语音。 这些用户可以在办公地点使用 PBX 电话，还可企业语音 VoIP 设备在其他位置使用 VoIP 设备拨打或接听电话。 如果这些用户启用了通过工号呼叫功能，则他们可以在办公期间使用 Skype for Business 客户端控制其 PBX 电话。
  
> [!NOTE]
> 远程呼叫控制是 Lync Server 早期版本中提供的一项功能，允许用户使用其 Skype for Business 客户端在 PBX 电话上拨打和接听电话。 远程呼叫控制不受 Skype for Business Server 服务器上用户的支持，但是仍位于运行 Lync Server 2013 的服务器上具有 Skype for Business 客户端的用户受支持。 
  
## <a name="see-also"></a>另请参阅


[规划企业语音 Skype for Business Server 中的服务](enterprise-voice.md)
  
[在 Skype for Business Server 中规划通过工位呼叫](call-via-work.md)
  
[在 Skype for Business 中规划远程呼叫控制](remote-call-control.md)

