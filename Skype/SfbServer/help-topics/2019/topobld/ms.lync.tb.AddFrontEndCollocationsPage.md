---
title: 添加前端服务器并置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: 对于企业版部署，"A/V" 会议服务是 collocated 在前端池。 你还可以在前端池上 collocate 中介服务器，也可以将其作为独立服务器进行部署。 如果启用了会议，则 A/V 会议服务始终 collocated。
ms.openlocfilehash: fe9eccaa7a59963b202009eba68aa0fdb9f1a15d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702917"
---
# <a name="add-front-end-server-collocations"></a><span data-ttu-id="398cf-105">添加前端服务器并置</span><span class="sxs-lookup"><span data-stu-id="398cf-105">Add Front End Server Collocations</span></span>

<span data-ttu-id="398cf-106">对于企业版部署，"A/V" 会议服务是 collocated 在前端池。</span><span class="sxs-lookup"><span data-stu-id="398cf-106">For an Enterprise Edition deployment, the A/V Conferencing service is collocated on the Front End pool.</span></span> <span data-ttu-id="398cf-107">你还可以在前端池上 collocate 中介服务器，也可以将其作为独立服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="398cf-107">You can also collocate the Mediation Server on the Front End pool, or you can deploy it as a stand-alone server.</span></span> <span data-ttu-id="398cf-108">如果启用了会议，则 A/V 会议服务始终 collocated。</span><span class="sxs-lookup"><span data-stu-id="398cf-108">The A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="398cf-109">如果在 "**选择功能**" 页面上选择了 "**会议**"，则需要 A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="398cf-109">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="398cf-110">企业版前端池使用 collocated A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="398cf-110">An Enterprise Edition Front End pool uses a collocated A/V Conferencing service.</span></span> <span data-ttu-id="398cf-111">如果未选择会议，Collocate 的 A/V 会议服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="398cf-111">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="398cf-112">你可以在标准版前端服务器或企业版前端池上 collocate 中介服务器角色。</span><span class="sxs-lookup"><span data-stu-id="398cf-112">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="398cf-113">如果你将直接 SIP 连接部署到支持媒体绕过和域名系统（DNS）负载平衡的合格的公共交换电话网络（PSTN）网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="398cf-113">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="398cf-114">不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且它们可以接收来自池中的任何中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="398cf-114">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="398cf-115">我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器（SBC）时，在前端池中 collocate 中介服务器，前提是满足以下任何条件：</span><span class="sxs-lookup"><span data-stu-id="398cf-115">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="398cf-116">将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="398cf-116">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="398cf-117">将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="398cf-117">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="398cf-118">你可以使用计划工具评估要在中介服务器 collocate 的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="398cf-118">You can use the Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="398cf-119">如果你的环境无法满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="398cf-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="398cf-120">通常，如果你的组织具有高可用性和可伸缩性要求，则不建议使用中介服务器 collocation。</span><span class="sxs-lookup"><span data-stu-id="398cf-120">In general, collocation of Mediation Server is not recommended if your organization has high availability and scalability requirements.</span></span> <span data-ttu-id="398cf-121">有关在企业版部署中的前端池中 collocating 这些服务器角色的详细信息，请参阅在部署文档中[定义和配置前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="398cf-121">For details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="398cf-122">有关 A/V 会议功能和组件的详细信息，请参阅规划文档中的 "[规划会议](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)"。</span><span class="sxs-lookup"><span data-stu-id="398cf-122">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="398cf-123">有关企业语音功能和组件（包括中介服务器）的详细信息，请参阅规划文档中的 Skype for business[服务器中的 "规划企业语音](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)"。</span><span class="sxs-lookup"><span data-stu-id="398cf-123">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


