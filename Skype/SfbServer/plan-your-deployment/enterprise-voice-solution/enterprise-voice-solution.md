---
title: 在 Skype for Business Server 中规划企业语音解决方案
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
ms.assetid: f9c6fd1d-c379-47d1-8447-19274ace9951
description: 摘要：了解在 Skype for business Server 中规划统一语音和通信解决方案的选项。
ms.openlocfilehash: 2f3b66815a5d49fcd770f85b7641d0a6c4dff7d8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359118"
---
# <a name="plan-your-enterprise-voice-solution-in-skype-for-business-server"></a>在 Skype for Business Server 中规划企业语音解决方案
 
**摘要：** 了解在 Skype for business Server 中规划统一语音和通信解决方案的选项。
  
Skype for Business Server 提供了两个本地企业语音选项（企业语音和呼叫通过工作），以便您可以将组织的电话系统与 Skype for Business Server 部署集成在一起，从而实现真正的统一通信解决方案。 这两个选项都允许用户使用其 Skype for Business 客户端启动语音呼叫，以与组织内部和外部的其他用户进行语音呼叫。
  
您还可以通过协同工作同时使用企业语音和呼叫。
  
- 企业语音是最完整的语音服务。 它是软件支持的语音 (VoIP) 解决方案，提供一组非常丰富的功能集，包括与 Outlook 和 Exchange 的丰富集成，以及许多功能强大的功能（如响应组、呼叫寄存、团队呼叫、组呼叫应答和增强的紧急 E9-1-1 支持）。 使用企业语音，用户可将耳机与计算机或启用 VoIP 的手机（而不是传统 PSTN 或 PBX 电话）一起使用。
    
- 通过工作进行的呼叫提供了一种将 Skype for Business 解决方案与现有 PBX 电话系统集成的方法。 为通过工作进行呼叫而启用的用户可以在 Skype for Business 中单击，以在部署中或外部用户调用其他用户。 使用用户的 PBX 电话完成呼叫。 此外，这些用户可以在 Skype for Business 中单击以加入会议。
    
    通过工作来部署呼叫也是对仍有 PBX 电话但要转换为企业语音的用户有用的，因为它允许这些用户使用其 Skype for Business 客户端来控制其电话呼叫。
    
     通过工作进行的呼叫提供了一组更有限的语音功能 thanEnterprise 语音。 例如，它不支持委派、团队呼叫、响应组或增强的 E9-1-1。
    
当然，您可以让一些用户在其他用户使用 PBX 电话的情况下启用企业语音。 此外，当您转换为完整的企业语音解决方案时，您可以允许仍有适用于企业语音的 PBX 电话的用户。 这些用户可以在其桌面使用其 PBX 电话，还可以使用企业语音在其他位置使用 VoIP 设备发出或接收呼叫。 如果已通过工作启用这些用户的呼叫，他们可以使用其 Skype for Business 客户端在其桌面控制其 PBX 电话。
  
> [!NOTE]
> 远程呼叫控制是在以前版本的 Lync Server 中提供的一项功能，使用户可以使用其 Skype for Business 客户端在其 PBX 电话上拨打和接听电话呼叫。 驻留在 Skype for business Server 服务器上的用户不支持远程呼叫控制，但对于在运行 Lync Server 2013 的服务器上仍驻留的 Skype for Business 客户端，用户支持远程呼叫控制。 
  
## <a name="see-also"></a>另请参阅


[在 Skype for Business Server 中规划企业语音](enterprise-voice.md)
  
[通过 Skype for Business Server 中的工作规划呼叫计划](call-via-work.md)
  
[在 Skype for Business 中规划远程呼叫控制](remote-call-control.md)

