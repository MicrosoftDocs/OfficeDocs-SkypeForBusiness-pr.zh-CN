---
title: 添加前端服务器并置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: 对于企业版部署，"A/V" 会议服务是 collocated 在前端池。 你还可以在前端池上 collocate 中介服务器，也可以将其作为独立服务器进行部署。 如果启用了会议，则 A/V 会议服务始终 collocated。
ms.openlocfilehash: 0f6b3307d73f87af10140ecf594f8e662cfdd369
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820824"
---
# <a name="add-front-end-server-collocations"></a>添加前端服务器并置

对于企业版部署，"A/V" 会议服务是 collocated 在前端池。 你还可以在前端池上 collocate 中介服务器，也可以将其作为独立服务器进行部署。 如果启用了会议，则 A/V 会议服务始终 collocated。

> [!NOTE]
> 如果在 "**选择功能**" 页面上选择了 "**会议**"，则需要 A/V 会议服务。 企业版前端池使用 collocated A/V 会议服务。 如果未选择会议，Collocate 的 A/V 会议服务将不可用。

你可以在标准版前端服务器或企业版前端池上 collocate 中介服务器角色。 如果你将直接 SIP 连接部署到支持媒体绕过和域名系统（DNS）负载平衡的合格的公共交换电话网络（PSTN）网关，则不需要独立的中介服务器池。 不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且它们可以接收来自池中的任何中介服务器的流量。 我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器（SBC）时，在前端池中 collocate 中介服务器，前提是满足以下任何条件：

- 将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量，并且可以将流量统一路由到池中的所有中介服务器。

- 将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量，并且可以将流量统一路由到池中的所有中介服务器。

你可以使用 Microsoft Lync Server 2013、计划工具评估你想要 collocate 中介服务器的前端池是否可以处理负载。 如果你的环境无法满足这些要求，则必须部署独立的中介服务器池。

通常，如果你的组织具有高可用性和可伸缩性要求，则不建议使用中介服务器 collocation。 有关在企业版部署中的前端池中 collocating 这些服务器角色的详细信息，请参阅在部署文档中[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。 有关 A/V 会议功能和组件的详细信息，请参阅规划文档中的 "[规划会议](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)"。 有关企业语音功能和组件（包括中介服务器）的详细信息，请参阅规划文档中的 Skype for business [Server 2015 中的 "规划企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)"。


