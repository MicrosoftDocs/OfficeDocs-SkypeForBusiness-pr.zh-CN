---
title: 规划远程呼叫控制Skype for Business
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
description: 远程呼叫控制是 Lync Server 早期版本中的一项功能，它使用户能够使用 Lync Server 控制其 PBX 电话。 在Skype for Business Server，此功能已替换为通过工位呼叫功能。 在 2015 Skype for Business Server的客户端版本中，远程呼叫控制不再可用于在客户端中配置，并且已删除供其使用。
ms.openlocfilehash: c7b4156c90810206824d922af17b83381a64afe17a3a927825eae91445245cfa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302366"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>规划远程呼叫控制Skype for Business
 
远程呼叫控制是 Lync Server 早期版本中的一项功能，它使用户能够使用 Lync Server 控制其 PBX 电话。 在Skype for Business Server，此功能已替换为通过工位呼叫功能。  *在 2015 Skype for Business Server的客户端版本中，远程呼叫控制不再可用于在客户端中配置，并且已删除供其使用。* 
  
 组织中位于运行 Lync Server 的前端服务器上远程呼叫控制用户可以继续使用远程呼叫控制，即使他们使用的是 Skype for Business 客户端。 但是，对于位于远程Skype for Business Server，不支持远程呼叫控制。 有关服务器/客户端组合及其是否可以支持远程呼叫控制或通过工位呼叫的信息，请参阅下表。
  
||**Skype for Business启用 Skype UI 的客户端**|**Skype for Business启用 Lync UI 的客户端**|**Skype for Business 2016 客户端**|**Lync 2013 客户端**|**Lync 2010 客户端**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |通过工作电话呼叫  <br/> |1 <br/> |通过工作电话呼叫  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |1 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
| Lync Server 2010 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |1 <br/> |远程呼叫控制  <br/> |远程呼叫控制  <br/> |
   
1. 这两种功能都不受支持。
  
有关详细信息，请参阅 Lync Server 2013 文档中的 Remote [Call Control。](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control)
  
## <a name="see-also"></a>另请参阅

[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[桌面客户端功能比较Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[拨打Skype for Business但将 PBX 桌面电话用于音频](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)