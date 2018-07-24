---
title: 添加前端服务器并置 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 对于 Enterprise Edition 部署中，您可以将并置任一 A / V 会议服务、 中介服务器，或两者上的前端池，也可以部署其中各个作为独立服务器。 对于 Standard Edition 服务器部署，A / V 会议服务始终并置，如果启用会议。
ms.openlocfilehash: f13511877d7c6ba951f524455e215fb1e426eeea
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20994677"
---
# <a name="add-front-end-server-collocations-2010"></a>添加前端服务器并置 2010
 
对于 Enterprise Edition 部署中，您可以将并置任一 A / V 会议服务、 中介服务器，或两者上的前端池，也可以部署其中各个作为独立服务器。 对于 Standard Edition 服务器部署，A / V 会议服务始终并置，如果启用会议。
  
> [!NOTE]
> A / V 会议服务是必需的如果在**选择功能**页上选择**会议**。 Enterprise Edition 前端池可以使用并置 A / V 会议服务或独立 A / V 会议池。 如果会议未选中状态，置 A / V 会议服务将不可用。
  
您可以并置在 Standard Edition 前端服务器或 Enterprise Edition 前端池上的中介服务器角色。 如果您部署直接 SIP 连接到限定的公用电话交换网 (pstn) 网关支持媒体绕过和域名系统 (DNS) 负载平衡，不需要独立的中介服务器池。 由于合格网关支持的 DNS 负载平衡到中介服务器池，并且他们可以从池中的任何中介服务器接收通信，则不需要独立的中介服务器池。 我们还建议并置中介服务器的前端池上部署 IP Pbx 或连接到 Internet 电话服务服务器提供商的会话边界控制器 (SBC) 时，只要满足以下条件的任何一个：
  
- IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。
    
- IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。
    
您可以使用 Microsoft Lync Server 2013 规划工具以评估是否要将并置中介服务器的前端池可以处理负载。 如果您的环境无法满足这些要求，则必须部署独立的中介服务器池。
  
在常规，并置的 A / V 会议服务器或中介服务器不建议如果您的组织具有高可用性和可伸缩性掌握有关详细信息并置在前端池中 Enterprise Edition 中的这些服务器角色部署，请参阅部署文档中的[Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。 有关详细信息 A / V 会议功能和组件，请参阅[Planning for 会议](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)规划文档中。 有关企业语音功能和组件，包括中介服务器的详细信息请参阅规划文档中的[规划中的业务服务器 2015 Skype 的企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。
  

