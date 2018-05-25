---
title: 在 Skype for Business 2015 中规划远程呼叫控制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制时在早期版本的 Lync Server 启用用户控制其 PBX 电话与 Lync Server 的功能。 在业务服务器 Skype，此功能已取代与通过单位电话呼叫。 中的客户端版本的 Skype 业务服务器 2015年和转转接、 远程呼叫控件不再是可用于配置在客户端，并使用已删除。
ms.openlocfilehash: e3a8031a79d547a279b377a45e1e8461cd47a2e7
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a>在 Skype for Business 2015 中规划远程呼叫控制
 
远程呼叫控制时在早期版本的 Lync Server 启用用户控制其 PBX 电话与 Lync Server 的功能。 在业务服务器 Skype，此功能已取代与通过单位电话呼叫。  *中的客户端版本的 Skype 业务服务器 2015年和转转接、 远程呼叫控件不再是可用于配置在客户端，并使用已删除。* 
  
 远程呼叫控制组织中的用户驻留在前端服务器运行 Lync Server 上可以继续使用远程呼叫控制，即使它们使用 Skype for Business 客户端。 但是，业务服务器位于 Skype 上的任何用户，不支持远程呼叫控制。 有关服务器/客户端组合以及它们是否可以支持远程呼叫控制或通过工号拨号，请参阅下表。
  
||**启用业务 2015年客户端 With Skype UI 的 Skype**|**启用业务 2015年客户端 With Lync UI 的 Skype**|**Skype 业务 2016年客户端**|**Lync 2013 客户端**|**Lync 2010 客户端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server 2015 <br/> |通过工号拨号  <br/> |1 <br/> |通过工号拨号  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |1 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
| Lync Server 2010 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |1 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
   
1. 支持既功能。
  
有关详细信息，请参阅 Lync Server 2013 文档中的[远程呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。
  
## <a name="see-also"></a>另请参阅

#### 

[规划用单位电话的 Skype 业务服务器 2015年呼叫](call-via-work.md)
  
[Skype for Business 的桌面客户端功能比较](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[使业务呼叫 Skype，但使用 PBX 桌面电话音频](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

