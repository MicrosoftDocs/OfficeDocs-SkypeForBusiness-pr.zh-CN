---
title: Skype for Business Server 企业语音所需的组件
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype for Business Server 企业语音组件摘要。
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825822"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server 企业语音所需的组件
 
Skype for Business Server 企业语音组件摘要。
  
若要企业语音，拓扑中需要以下组件。 
  
- 一个或多个中介服务器，用于转换内部 Skype for Business Server、企业语音 基础结构和公用电话交换网 (PSTN) 网关或会话初始协议 (SIP) 中继之间的信号和（在某些配置中）媒体。 中介服务器是部署部署中企业语音组件。 有关详细信息，请参阅 [Skype for Business Server 中的中介服务器组件](mediation-server.md)。
    
    中介服务器可以与前端服务器并排，也可以作为独立服务器安装。
    
- PSTN 连接组件，可包括 SIP 中继或 PSTN 网关。 有关详细信息，请参阅 Skype for Business Server 中的 [PSTN 连接组件](pstn-connectivity.md)。
    
- 边缘服务器，在用户位于企业语音外部时，可以使用这些功能。 
    
    访问边缘服务为来自组织防火墙之外的 Skype for Business 用户的呼叫提供 SIP 信号。 A/V 边缘服务使媒体可以遍历 NAT 和防火墙。 从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。
    
    A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。
    
- 此外，企业语音组件在前端服务器上运行。 有关这些组件的详细信息，请参阅 Skype for Business Server 的前端 [服务器 VoIP 组件](front-end-server-voip.md)
    

