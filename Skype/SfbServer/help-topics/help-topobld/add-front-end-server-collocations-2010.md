---
title: 添加前端服务器搭配 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 企业版部署中，可以布置是 A / V 会议服务、 中介服务器，或同时在前端池，或者您可以部署每个作为独立服务器。 标准版服务器部署中，A / V 会议服务始终搭配如果启用会议了。
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations-2010"></a>添加前端服务器搭配 2010
 
企业版部署中，可以布置是 A / V 会议服务、 中介服务器，或同时在前端池，或者您可以部署每个作为独立服务器。 标准版服务器部署中，A / V 会议服务始终搭配如果启用会议了。
  
> [!NOTE]
> A / V 会议服务是必需的如果在**选择功能**页上选择了**会议**。 企业版前端池可能使用并入 A / V 会议服务或独立的 A / V 会议池。 如果会议没有选择，Collocate A / V 会议服务将不可用。
  
您可以配置标准版前端服务器或前端企业版池中的中介服务器角色。 如果将直接 SIP 连接部署到支持媒体回避和域名系统 (DNS) 负载平衡的限定公共交换的电话网络 (PSTN) 网关，则不需要独立的中介服务器池。 由于限定的网关的 DNS 负载平衡到池的中介服务器的能力并且能够从池中任何中介服务器接收通信，则不需要独立的中介服务器池。 我们还建议，您布置中介服务器前端池上时您已部署 IP Pbx 或连接到互联网电话服务服务器提供程序的会话边框控制器 (SBC)，只要满足以下条件的任何操作：
  
- IP PBX 或 SBC 被配置为从池中任何中介服务器接收通信，可以将路由通信统一到池中的所有中介服务器。
    
- IP PBX 或 SBC 被配置为从池中任何中介服务器接收通信，可以将路由通信统一到池中的所有中介服务器。
    
您可以使用 Microsoft Lync Server 2013，规划工具来评估是否想要布置中介服务器的前端池可以处理的负载。 如果您的环境不能满足这些要求，您必须部署独立的中介服务器池。
  
中的一个常规，配置 / V 会议服务器或中介服务器不建议如果您的组织具有高可用性和可伸缩性要求适用于有关的详细信息配置在企业版池中前端服务器角色部署，请参阅部署文档中[定义和配置前结束池](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。 有关 A / V 会议功能和组件，请参阅[规划会议](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)的规划文档中。 企业语音的功能和组件，包括中介服务器的详细信息请参阅规划文档中的[企业语音在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。
  

