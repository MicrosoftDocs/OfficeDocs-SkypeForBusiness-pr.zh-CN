---
title: 在企业语音中规划Skype for Business Server
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
description: 摘要：了解在 Skype for Business Server 中规划统一语音和通信解决方案Skype for Business Server。
ms.openlocfilehash: 3ac268b69cc125ee6327244c8b7b9777b9886a16763f9831a2582a935f931432
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286691"
---
# <a name="plan-your-enterprise-voice-solution-in-skype-for-business-server"></a>在企业语音中规划Skype for Business Server
 
**摘要：** 了解在 Skype for Business Server 中规划统一语音和通信解决方案Skype for Business Server。
  
Skype for Business Server提供了两个本地 企业语音 选项（企业语音 和单位电话呼叫）用于将组织的电话系统与 Skype for Business Server 部署集成，从而提供真正的统一通信解决方案。 这两个选项都允许用户使用 Skype for Business 客户端发起与组织内外的其他用户的语音呼叫。
  
还可以同时使用 企业语音 和通过工电话呼叫。
  
- 企业语音是最完整的语音产品/服务。 它是一种由软件提供支持的 IP 语音 (VoIP) 解决方案，提供一个非常丰富的功能集，包括与 Outlook 和 Exchange 的丰富集成，以及许多强大的功能，如响应组、呼叫停止、团队呼叫、组内呼叫应答和增强型紧急 E9-1-1 支持。 通过企业语音，用户可以将音频设备（如耳机）与计算机或支持 VoIP 的电话（而不是传统的 PSTN 或 PBX 电话）一同使用。
    
- 通过工号呼叫提供了一种将 Skype for Business 解决方案与现有 PBX 电话系统集成的方法。 启用了通过工位呼叫的用户可以通过单击Skype for Business呼叫其他用户，无论是部署内部用户还是外部用户。 使用用户的 PBX 电话完成呼叫。 此外，这些用户可以单击Skype for Business加入会议。
    
    部署通过工号呼叫对仍拥有 PBX 电话但正在转换到 企业语音 的用户也是一项好处，因为它使这些用户能够使用 Skype for Business 客户端控制其电话呼叫。
    
     通过工位呼叫提供一组比企业语音更加有限的语音功能。 例如，它不支持委派、团队呼叫、响应组或增强型 E9-1-1。
    
当然，您可以为一些用户启用 企业语音而其他用户使用的是 PBX 电话。 此外，在转换到完整企业语音解决方案时，您可以为仍具有 PBX 电话的用户启用企业语音。 这些用户可以在办公地点使用 PBX 电话，也可以企业语音设备在其他位置使用 VoIP 设备拨打或接听呼叫。 如果为这些用户启用了"通过工号呼叫"功能，他们可以使用其 Skype for Business 客户端在办公室控制其 PBX 电话。
  
> [!NOTE]
> 远程呼叫控制是 Lync Server 早期版本中提供的一项功能，允许用户使用其 Skype for Business 客户端在 PBX 电话上拨打和接听电话呼叫。 远程呼叫控制不受 Skype for Business Server 服务器上用户的支持，但具有 Skype for Business 客户端的用户仍位于运行 Lync Server 2013 的服务器上。 
  
## <a name="see-also"></a>另请参阅


[规划企业语音Skype for Business Server](enterprise-voice.md)
  
[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[规划远程呼叫控制Skype for Business](remote-call-control.md)

