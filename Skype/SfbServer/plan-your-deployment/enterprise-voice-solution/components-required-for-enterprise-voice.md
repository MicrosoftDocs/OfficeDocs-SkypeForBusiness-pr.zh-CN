---
title: Skype for business Server 中的企业语音所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype for Business 服务器中的企业语音组件摘要。
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277004"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Skype for business Server 中的企业语音所需的组件
 
Skype for Business 服务器中的企业语音组件摘要。
  
若要部署企业语音, 拓扑中需要以下组件。 
  
- 一个或多个中介服务器, 用于转换信号和在某些配置中, 在内部 Skype for business 服务器之间、企业语音基础结构和公共交换电话网络 (PSTN) 网关或会话初始协议之间的媒体(SIP) 主干。 中介服务器是企业语音部署中最重要的组件。 有关详细信息, 请参阅[Skype For Business 服务器中的中介服务器组件](mediation-server.md)。
    
    中介服务器可以与前端服务器 collocated, 也可以作为独立服务器安装。
    
- PSTN 连接组件，可能包括 SIP 中继或 PSTN 网关。 有关详细信息, 请参阅[Skype For Business 服务器中的 PSTN 连接组件](pstn-connectivity.md)。
    
- 边缘服务器, 允许用户在组织的防火墙之外使用企业语音功能。 
    
    Access Edge 服务提供 SIP 信号, 用于从组织防火墙之外的 Skype for Business 用户进行呼叫。 A/V 边缘服务使媒体可以遍历 NAT 和防火墙。 从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。
    
    A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。
    
- 此外, 某些企业语音组件在前端服务器上运行。 有关这些组件的详细信息, 请参阅[Skype for Business 服务器的前端服务器 VoIP 组件](front-end-server-voip.md)
    

