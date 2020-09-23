---
title: 添加前端服务器并置 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 对于 Enterprise Edition 部署，可以将 A/V 会议服务、中介服务器或这两者并置在前端池上，也可以将其分别部署为独立的服务器。对于 Standard Edition Server 部署，如果启用会议，则将始终并置 A/V 会议服务。
ms.openlocfilehash: 86bef8bdcbdd36033e64912bdce2d9ea3469e45c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216513"
---
# <a name="add-front-end-server-collocations-2010"></a>添加前端服务器并置 2010

对于 Enterprise Edition 部署，可以将 A/V 会议服务、中介服务器或这两者并置在前端池上，也可以将其分别部署为独立的服务器。对于 Standard Edition Server 部署，如果启用会议，则将始终并置 A/V 会议服务。

> [!NOTE]
> 如果在 **“选择功能”** 页上选择了 **“会议”**，则需要使用 A/V 会议服务。Enterprise Edition 前端池可能会使用并置的 A/V 会议服务或独立的 A/V 会议池。如果未选择“会议”，则“并置 A/V 会议”服务将不可用。

您可以在 Standard Edition 前端服务器或 Enterprise Edition 前端池上并置中介服务器角色。 如果将直接 SIP 连接部署到合格的公开交换电话网络 (PSTN) 网关支持媒体旁路和域名系统 (DNS) 负载平衡，则无需使用独立中介服务器池。 若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。 我们还建议您在部署并置时，在前端池上中介服务器，或连接到 Internet 电话服务器提供程序的会话边界控制器 (SBC) ，前提是满足以下任一条件：

- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

您可以使用 Microsoft Lync Server 2013、规划工具来评估您要并置中介服务器的前端池是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。

通常情况下，如果您的组织具有高可用性和可伸缩性 requirementsFor 有关在企业版部署的前端池中并置这些服务器角色的详细信息，则不建议使用并置的会议服务器或中介服务器。请参阅部署文档中的 [定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。 有关 A/V 会议功能和组件的详细信息，请参阅规划文档中的[Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)。 有关企业语音功能和组件（包括中介服务器）的详细信息，请参阅规划文档中的在 [Skype For Business Server 2015 中规划企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 。


