---
title: 添加前端服务器并置 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 对于 Enterprise Edition 部署，可以将 A/V 会议服务、中介服务器或这两者并置在前端池上，也可以将其分别部署为独立的服务器。对于 Standard Edition Server 部署，如果启用会议，则将始终并置 A/V 会议服务。
ms.openlocfilehash: c0efab1ee8b388a7d8dfa710c8937f314e83721e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626644"
---
# <a name="add-front-end-server-collocations-2010"></a>添加前端服务器并置 2010

对于 Enterprise Edition 部署，可以将 A/V 会议服务、中介服务器或这两者并置在前端池上，也可以将其分别部署为独立的服务器。对于 Standard Edition Server 部署，如果启用会议，则将始终并置 A/V 会议服务。

> [!NOTE]
> 如果在 **“选择功能”** 页上选择了 **“会议”**，则需要使用 A/V 会议服务。Enterprise Edition 前端池可能会使用并置的 A/V 会议服务或独立的 A/V 会议池。如果未选择“会议”，则“并置 A/V 会议”服务将不可用。

可以将中介服务器角色并Standard Edition前端服务器或Enterprise Edition前端池。 如果将直接 SIP 连接部署到支持媒体旁路和域名系统 (DNS) 负载平衡的合格公用电话交换网 (PSTN) 网关，则不需要独立的中介服务器池。 若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。 我们还建议您在部署 IP-PBXs 或连接到 Internet 电话服务提供商的会话边界控制器 (SBC) （只要满足以下任一条件）时，就将中介服务器并排在前端池上：

- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

可以使用 Microsoft Lync Server 2013 规划工具评估要并并中介服务器的前端池是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。

通常，如果组织具有高可用性和可伸缩性要求，则不建议并置 A/V 会议服务器或中介服务器。有关在 Enterprise Edition 部署中的前端池中并置这些服务器角色的详细信息，请参阅部署文档中的 Define and [Configure a Front End Pool。](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) 有关 A/V 会议功能和组件的详细信息，请参阅规划文档中的[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)。 有关中介企业语音组件的详细信息，请参阅规划文档中的 Plan [for 企业语音 in Skype for Business Server 2015。](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)