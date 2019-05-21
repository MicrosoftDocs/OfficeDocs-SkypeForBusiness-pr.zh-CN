---
title: 添加前端服务器并置 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 对于企业版部署, 你可以在前端池上 collocate "A/V" 会议服务、中介服务器或同时使用这两者, 也可以将它们作为独立服务器进行部署。 对于标准版服务器部署, 如果已启用会议, 则始终 collocated A/V 会议服务。
ms.openlocfilehash: 8a8191f29a30052fec837ee9136203eb5db1ee0d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275351"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="72ed8-104">添加前端服务器并置 2010</span><span class="sxs-lookup"><span data-stu-id="72ed8-104">Add Front End Server Collocations 2010</span></span>

<span data-ttu-id="72ed8-105">对于企业版部署, 你可以在前端池上 collocate "A/V" 会议服务、中介服务器或同时使用这两者, 也可以将它们作为独立服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="72ed8-105">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers.</span></span> <span data-ttu-id="72ed8-106">对于标准版服务器部署, 如果已启用会议, 则始终 collocated A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="72ed8-106">For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="72ed8-107">如果在 "**选择功能**" 页面上选择了 "**会议**", 则需要 A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="72ed8-107">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="72ed8-108">企业版前端池可以使用 collocated A/V 会议服务或独立的 A/V 会议池。</span><span class="sxs-lookup"><span data-stu-id="72ed8-108">An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool.</span></span> <span data-ttu-id="72ed8-109">如果未选择会议, Collocate 的 A/V 会议服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="72ed8-109">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="72ed8-110">你可以在标准版前端服务器或企业版前端池上 collocate 中介服务器角色。</span><span class="sxs-lookup"><span data-stu-id="72ed8-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="72ed8-111">如果你将直接 SIP 连接部署到支持媒体绕过和域名系统 (DNS) 负载平衡的合格的公共交换电话网络 (PSTN) 网关, 则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="72ed8-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="72ed8-112">不需要独立的中介服务器池, 因为合格的网关能够将 DNS 负载平衡到中介服务器池, 并且它们可以接收来自池中的任何中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="72ed8-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="72ed8-113">我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器 (SBC) 时, 在前端池中 collocate 中介服务器, 前提是满足以下任何条件:</span><span class="sxs-lookup"><span data-stu-id="72ed8-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="72ed8-114">将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量, 并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="72ed8-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="72ed8-115">将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量, 并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="72ed8-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="72ed8-116">你可以使用 Microsoft Lync Server 2013、计划工具评估你想要 collocate 中介服务器的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="72ed8-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="72ed8-117">如果你的环境无法满足这些要求, 则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="72ed8-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="72ed8-118">通常情况下, 如果你的组织具有高可用性和可伸缩性, 则不建议使用 collocation/V 会议服务器或中介服务器 requirementsFor 有关在企业版的前端池中 collocating 这些服务器角色的详细信息部署, 请参阅在部署文档中[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="72ed8-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="72ed8-119">有关 A/V 会议功能和组件的详细信息, 请参阅规划文档中的 "[规划会议](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)"。</span><span class="sxs-lookup"><span data-stu-id="72ed8-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="72ed8-120">有关企业语音功能和组件 (包括中介服务器) 的详细信息, 请参阅规划文档中的 Skype for business [Server 2015 中的 "规划企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)"。</span><span class="sxs-lookup"><span data-stu-id="72ed8-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


