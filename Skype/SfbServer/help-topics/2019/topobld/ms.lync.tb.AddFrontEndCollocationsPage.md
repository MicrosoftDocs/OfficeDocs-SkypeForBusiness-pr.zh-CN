---
title: 添加前端服务器并置
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: 对于 Enterprise Edition 部署，A / V 会议服务并置在前端池上。 您还可以并置中介服务器上的前端池，或您可以将其部署为独立服务器。 A / V 会议服务始终并置，如果启用会议。
ms.openlocfilehash: 58f06cda9927c7596844fd3cda884bdfe48e32a7
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974976"
---
# <a name="add-front-end-server-collocations"></a>添加前端服务器并置
 
对于 Enterprise Edition 部署，A / V 会议服务并置在前端池上。 您还可以并置中介服务器上的前端池，或您可以将其部署为独立服务器。 A / V 会议服务始终并置，如果启用会议。
  
> [!NOTE]
> A / V 会议服务是必需的如果在**选择功能**页上选择**会议**。 Enterprise Edition 前端池使用并置 A / V 会议服务。 如果会议未选中状态，置 A / V 会议服务将不可用。
  
您可以并置在 Standard Edition 前端服务器或 Enterprise Edition 前端池上的中介服务器角色。 如果您部署直接 SIP 连接到限定的公用电话交换网 (pstn) 网关支持媒体绕过和域名系统 (DNS) 负载平衡，不需要独立的中介服务器池。 由于合格网关支持的 DNS 负载平衡到中介服务器池，并且他们可以从池中的任何中介服务器接收通信，则不需要独立的中介服务器池。 我们还建议并置中介服务器的前端池上部署 IP Pbx 或连接到 Internet 电话服务服务器提供商的会话边界控制器 (SBC) 时，只要满足以下条件的任何一个：
  
- IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。
    
- IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。
    
规划工具可用于评估是否要将并置中介服务器的前端池可以处理负载。 如果您的环境无法满足这些要求，则必须部署独立的中介服务器池。
  
一般来说，如果您的组织具有高可用性和可伸缩性要求不建议并置的中介服务器。 有关详细信息并置在前端池中 Enterprise Edition 部署中的这些服务器角色，请参阅部署文档中的[Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。 有关详细信息 A / V 会议功能和组件，请参阅[Planning for 会议](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)规划文档中。 有关企业语音功能和组件，包括中介服务器的详细信息请参阅规划文档中的[规划 Skype 业务服务器中的企业语音](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。
  

