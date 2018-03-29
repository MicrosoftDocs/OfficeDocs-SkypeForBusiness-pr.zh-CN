---
title: Skype for Business Server 2015 中的企业语音所需组件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 在 Skype 业务服务器的企业语音组件的摘要。
ms.openlocfilehash: 2c5df4c0d580d767693717cf48585ceb0d4c7365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的企业语音所需组件
 
在 Skype 业务服务器的企业语音组件的摘要。
  
若要部署企业语音，以下组件需要在您的拓扑结构。 
  
- 一个或多个中介服务器，转换信号传输和，在某些配置中，您的企业服务器，企业语音基础结构和公用交换的电话网络 (PSTN) 网关或会话初始化协议的内部 Skype 之间的介质(SIP) 干线。 中介服务器是企业语音部署中最关键的组件。 有关详细信息，请参阅[中业务服务器 2015年的 Skype 的中介服务器组件](mediation-server.md)。
    
    可以搭配使用前端服务器或独立服务器作为安装中介服务器。
    
- PSTN 连接组件，可能包括 SIP 中继或 PSTN 网关。 有关详细信息，请参阅[中的业务服务器 2015 Skype 的 PSTN 连接组件](pstn-connectivity.md)。
    
- 边缘服务器，可以使用企业语音功能由您的用户在组织的防火墙之外时。 
    
    访问边缘服务提供 SIP 信号从 Skype 电话的业务用户位于组织的防火墙之外。 A/V 边缘服务使媒体可以遍历 NAT 和防火墙。 从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。
    
    A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。
    
- 此外，某些企业语音组件在前端服务器上运行。 有关这些组件的详细信息，请参阅[前结束服务器 VoIP 业务服务器 2015年的 Skype 的组件](front-end-server-voip.md)
    

