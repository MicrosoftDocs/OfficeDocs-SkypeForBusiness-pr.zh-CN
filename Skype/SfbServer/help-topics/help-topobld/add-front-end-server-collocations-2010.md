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
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 对于 Enterprise Edition 部署，可以将 A/V 会议服务、中介服务器或这两者并置在前端池上，也可以将其分别部署为独立的服务器。对于 Standard Edition Server 部署，如果启用会议，则将始终并置 A/V 会议服务。
ms.openlocfilehash: 1cd253c9415027eb36affe11dcd58832d6c07e8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824102"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="46ee8-104">添加前端服务器并置 2010</span><span class="sxs-lookup"><span data-stu-id="46ee8-104">Add Front End Server Collocations 2010</span></span>

<span data-ttu-id="46ee8-p102">对于 Enterprise Edition 部署，可以将 A/V 会议服务、中介服务器或这两者并置在前端池上，也可以将其分别部署为独立的服务器。对于 Standard Edition Server 部署，如果启用会议，则将始终并置 A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="46ee8-p102">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers. For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="46ee8-p103">如果在 **“选择功能”** 页上选择了 **“会议”**，则需要使用 A/V 会议服务。Enterprise Edition 前端池可能会使用并置的 A/V 会议服务或独立的 A/V 会议池。如果未选择“会议”，则“并置 A/V 会议”服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="46ee8-p103">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page. An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool. If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="46ee8-110">可以将中介服务器角色并排在 Standard Edition 前端服务器或 Enterprise Edition 前端池上。</span><span class="sxs-lookup"><span data-stu-id="46ee8-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="46ee8-111">如果将直接 SIP 连接部署到支持媒体旁路和域名系统 (DNS) 负载平衡的限定公用电话交换网 (PSTN) 网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="46ee8-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="46ee8-112">若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。</span><span class="sxs-lookup"><span data-stu-id="46ee8-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="46ee8-113">我们还建议您在部署 IP-PBXs 或连接到 Internet 电话服务提供商的会话边界控制器 (SBC) （只要满足以下任一条件）时，将中介服务器并排在前端池上：</span><span class="sxs-lookup"><span data-stu-id="46ee8-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="46ee8-114">IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="46ee8-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="46ee8-115">IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="46ee8-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="46ee8-116">可以使用 Microsoft Lync Server 2013 规划工具评估要并集中介服务器的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="46ee8-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="46ee8-117">如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="46ee8-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="46ee8-118">通常，如果组织具有高可用性和可伸缩性要求，则不建议并置 A/V 会议服务器或中介服务器。有关在 Enterprise Edition 部署中的前端池中并置这些服务器角色的详细信息，请参阅部署文档中的"[](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)定义和配置前端池"。</span><span class="sxs-lookup"><span data-stu-id="46ee8-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="46ee8-119">有关 A/V 会议功能和组件的详细信息，请参阅规划文档中的[Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)。</span><span class="sxs-lookup"><span data-stu-id="46ee8-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="46ee8-120">有关中介企业语音组件的详细信息，请参阅规划文档中的企业语音 Skype for [Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 中的规划。</span><span class="sxs-lookup"><span data-stu-id="46ee8-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


