---
title: 所需的 Skype 中的企业语音的企业服务器组件
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 企业语音组件中的业务服务器 Skype 摘要。
ms.openlocfilehash: 800a12b2d83703f188fff04452cf865757d5cad9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970477"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>所需的 Skype 中的企业语音的企业服务器组件
 
企业语音组件中的业务服务器 Skype 摘要。
  
若要部署企业语音，需要以下组件在拓扑中。 
  
- 一个或多个中介服务器，翻译信号的以及在某些配置中，对于业务 Server，企业语音基础结构和公用电话交换网 (pstn) 网关或会话初始协议您内部 Skype 之间的媒体(SIP) 中继。 中介服务器是企业语音部署中最重要的组件。 有关详细信息，请参阅[Skype 业务服务器中的中介服务器组件](mediation-server.md)。
    
    可以与前端服务器并置或独立服务器安装中介服务器。
    
- PSTN 连接组件，可能包括 SIP 中继或 PSTN 网关。 有关详细信息，请参阅[Skype 业务服务器中的 PSTN 连接组件](pstn-connectivity.md)。
    
- 边缘服务器，贵组织的防火墙之外时允许的用户的企业语音功能使用。 
    
    访问边缘服务提供的 Skype 从组织防火墙之外的业务用户的呼叫的 SIP 信号。 A/V 边缘服务使媒体可以遍历 NAT 和防火墙。 从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。
    
    A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。
    
- 此外，在前端服务器上运行某些企业语音组件。 有关这些组件的详细信息，请参阅[Skype 业务服务器的前端服务器 VoIP 组件](front-end-server-voip.md)
    

