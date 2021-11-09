---
title: 添加前端服务器并置
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: 对于 Enterprise Edition 部署，A/V 会议服务并置在前端池上。还可以在前端池上并置中介服务器，或者可以将其部署为独立服务器。如果启用了会议，则始终并置 A/V 会议服务。
ms.openlocfilehash: e8f3a5ac2e5b6cca244d4a396bf69f554ad4ff77
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832636"
---
# <a name="add-front-end-server-collocations"></a>添加前端服务器并置

对于 Enterprise Edition 部署，A/V 会议服务并置在前端池上。还可以在前端池上并置中介服务器，或者可以将其部署为独立服务器。如果启用了会议，则始终并置 A/V 会议服务。

> [!NOTE]
> 如果在“选择功能”页上选择了“会议”，则需要使用 A/V 会议服务。Enterprise Edition 前端池使用并置的 A/V 会议服务。如果未选择“会议”，则“并置 A/V 会议”服务将不可用。

可以将中介服务器角色并Standard Edition前端服务器或Enterprise Edition前端池。 如果将直接 SIP 连接部署到支持媒体旁路和域名系统 (DNS) 负载平衡的合格公用电话交换网 (PSTN) 网关，则不需要独立的中介服务器池。 若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。 我们还建议您在部署 IP-PBXs 或连接到 Internet 电话服务提供商的会话边界控制器 (SBC) （只要满足以下任一条件）时，就将中介服务器并排在前端池上：

- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

可以使用规划工具评估要并并中介服务器的前端池是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。

总而言之，如果组织具有高可用性和可伸缩性要求，则不建议并置中介服务器。 有关在 Enterprise Edition 部署的前端池中并置这些服务器角色的详细信息，请参阅部署文档中的[Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)。 有关 A/V 会议功能和组件的详细信息，请参阅规划文档中的[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)。 有关中介企业语音组件（包括中介服务器）的详细信息，请参阅规划文档中企业语音规划[Skype for Business Server中的规划](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。