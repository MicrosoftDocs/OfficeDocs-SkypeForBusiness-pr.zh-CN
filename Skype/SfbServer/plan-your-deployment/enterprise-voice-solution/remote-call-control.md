---
title: 在 Skype for Business 中规划远程呼叫控制
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制是 Lync Server 早期版本中的一项功能，它使用户能够使用 Lync Server 控制 PBX 电话。 在 Skype for Business Server 中，此功能已替换为通过工位电话呼叫功能。 在 Skype for Business Server 2015 的客户端版本中和今后，远程呼叫控制不再可用于在客户端中配置，并且已删除供使用。
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813512"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>在 Skype for Business 中规划远程呼叫控制
 
远程呼叫控制是 Lync Server 早期版本中的一项功能，它使用户能够使用 Lync Server 控制 PBX 电话。 在 Skype for Business Server 中，此功能已替换为通过工位电话呼叫功能。  *在 Skype for Business Server 2015 的客户端版本中和今后，远程呼叫控制不再可用于在客户端中配置，并且已删除供使用。* 
  
 组织中位于运行 Lync Server 的前端服务器中的远程呼叫控制用户可以继续使用远程呼叫控制，即使他们使用的是 Skype for Business 客户端。 但是，对于位于 Skype for Business Server 上的任何用户，不支持远程呼叫控制。 有关服务器/客户端组合及其是否可以支持远程呼叫控制或通过工位呼叫，请参阅下表。
  
||**启用了 Skype UI 的 Skype for Business 客户端**|**启用 Lync UI 的 Skype for Business 客户端**|**Skype for Business 2016 客户端**|**Lync 2013 客户端**|**Lync 2010 客户端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |通过工名呼叫  <br/> |1  <br/> |通过工名呼叫  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |1  <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
| Lync Server 2010 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |1  <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
   
1. 这两种功能都不受支持。
  
有关详细信息，请参阅 Lync [](https://go.microsoft.com/fwlink/p/?LinkId=530208) Server 2013 文档中的"远程呼叫控制"。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中规划通过工位呼叫](call-via-work.md)
  
[Skype for Business 的桌面客户端功能比较](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[拨打 Skype for Business 电话，但将 PBX 桌面电话用于音频](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

