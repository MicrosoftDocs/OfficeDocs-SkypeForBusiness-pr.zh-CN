---
title: 内部中继路由中 Skype 业务服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 了解如何为业务 Server 企业语音的 Skype 支持内部中继路由。
ms.openlocfilehash: a019e0340d9077874b35af0a116731f0ede97d67
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965399"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>内部中继路由中 Skype 业务服务器
 
了解如何为业务 Server 企业语音的 Skype 支持内部中继路由。
  
Skype 业务服务器提供通过支持的中继间路由的基本会话管理。 这样 Skype 业务服务器提供与下游电话系统的呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样，Skype 业务服务器可以互连两个或多个 IP-PBX 系统，以便可以发出呼叫，并将其从不同的 IP PBX 系统的 PBX 电话之间收到。 
  
下图展示了业务服务器提供 PSTN 网关和 IP-PBX 之间的互连性的 Skype。
  
![Lync Server - 连接 PSTN 网关/IP-PBX 图示](../../media/inter_trunk01.jpg)
  
下图显示连接两个 IP-PBX 系统的业务服务器 Skype。
  
![Lync Server - 将 IP-PAX 系统相互连接的图示](../../media/inter_trunk02.jpg)
  

