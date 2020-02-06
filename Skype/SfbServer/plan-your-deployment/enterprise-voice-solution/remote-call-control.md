---
title: 在 Skype for Business 中规划远程呼叫控制
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: "\"远程呼叫控制\" 是以前版本的 Lync Server 中的一项功能，允许用户使用 Lync 服务器控制其 PBX 电话。 在 Skype for Business 服务器中，此功能已替换为 \"通过工作通话\"。 在 Skype for business Server 2015 的客户端版本和未来版本中，客户端中的远程呼叫控制不再可用，已被删除以供使用。"
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802502"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>在 Skype for Business 中规划远程呼叫控制
 
"远程呼叫控制" 是以前版本的 Lync Server 中的一项功能，允许用户使用 Lync 服务器控制其 PBX 电话。 在 Skype for Business 服务器中，此功能已替换为 "通过工作通话"。  *在 Skype for business Server 2015 的客户端版本和未来版本中，客户端中的远程呼叫控制不再可用，已被删除以供使用。* 
  
 远程呼叫控制组织中托管的前端服务器上托管的用户可以继续使用远程呼叫控制，即使他们使用的是 Skype for Business 客户端也是如此。 但是，对于驻留在 Skype for business 服务器上的任何用户，不支持远程呼叫控制。 有关服务器/客户端组合以及它们是否可以支持远程呼叫控制或通过工号拨号，请参阅下表。
  
||**启用 Skype UI 的 skype for Business 客户端**|**启用了 Lync UI 的 Skype for Business 客户端**|**Skype for Business 2016 客户端**|**Lync 2013 客户端**|**Lync 2010 客户端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |通过工号拨号  <br/> |1 <br/> |通过工号拨号  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |raid-1 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
| Lync Server 2010 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |raid-1 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
   
1. 这两个功能都不受支持。
  
有关详细信息，请参阅 Lync Server 2013 文档中的 "[远程呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)"。
  
## <a name="see-also"></a>另请参阅

[通过 Skype for Business Server 中的工作计划呼叫计划](call-via-work.md)
  
[Skype for business 的桌面客户端功能比较](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[进行 Skype for Business 呼叫，但使用 PBX 桌面电话进行音频](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

