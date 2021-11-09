---
title: 关于服务器中的中继间Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 了解如何Skype for Business Server 企业语音中继间路由。
ms.openlocfilehash: 16a67af73db89f884f797c24123b984d3eb87789
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855409"
---
# <a name="about-inter-trunk-routing-in-skype-for-business-server"></a>关于服务器中的中继间Skype for Business Server
 
了解如何Skype for Business Server 企业语音中继间路由。
  
Skype for Business Server通过支持内部路由提供基本会话管理。 这Skype for Business Server为下游电话系统提供呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样，Skype for Business Server可以相互连接两个或多个 IP-PBX 系统，以便可以在不同 IP-PBX 系统的 PBX 电话之间拨打和接听呼叫。 
  
下图说明了如何Skype for Business Server PSTN 网关和 IP-PBX 之间的互连性。
  
![Lync Server 连接 PSTN 网关/IP-PBX 图表。](../../media/inter_trunk01.jpg)
  
下图说明了如何Skype for Business Server两个 IP-PBX 系统。
  
![Lync Server 互连 IP-PAX 系统图。](../../media/inter_trunk02.jpg)
  

