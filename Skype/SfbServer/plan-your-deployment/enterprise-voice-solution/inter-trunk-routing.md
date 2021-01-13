---
title: Skype for Business Server 中的中继间路由
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 了解 Skype for Business Server 企业语音支持中继间路由。
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825592"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Skype for Business Server 中的中继间路由
 
了解 Skype for Business Server 企业语音支持中继间路由。
  
Skype for Business Server 通过支持跨平台路由提供基本的会话管理。 这使 Skype for Business Server 能够向下游电话系统提供呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样，Skype for Business Server 可以将两个或多个 IP-PBX 系统相互连接，以便可以在不同 IP-PBX 系统的 PBX 电话之间拨打和接收呼叫。 
  
下图说明了在 PSTN 网关和 IP-PBX 之间提供互连性的 Skype for Business Server。
  
![Lync Server 连接 PSTN 网关/IP-PBX 图](../../media/inter_trunk01.jpg)
  
下图说明了连接两个 IP-PBX 系统的 Skype for Business Server。
  
![Lync Server 互连 IP-PAX 系统图](../../media/inter_trunk02.jpg)
  

