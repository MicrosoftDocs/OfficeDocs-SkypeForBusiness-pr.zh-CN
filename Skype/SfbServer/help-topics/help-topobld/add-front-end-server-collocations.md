---
title: 添加前端服务器并置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: 对于 Enterprise Edition 部署，A / V 会议服务并置在前端池上。 您还可以并置中介服务器上的前端池，或您可以将其部署为独立服务器。 A / V 会议服务始终并置，如果启用会议。
ms.openlocfilehash: 98e42a36bd57d256b66e08b6a44cca1d8b492155
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884355"
---
# <a name="add-front-end-server-collocations"></a><span data-ttu-id="5b307-105">添加前端服务器并置</span><span class="sxs-lookup"><span data-stu-id="5b307-105">Add Front End Server Collocations</span></span>

<span data-ttu-id="5b307-106">对于 Enterprise Edition 部署，A / V 会议服务并置在前端池上。</span><span class="sxs-lookup"><span data-stu-id="5b307-106">For an Enterprise Edition deployment, the A/V Conferencing service is collocated on the Front End pool.</span></span> <span data-ttu-id="5b307-107">您还可以并置中介服务器上的前端池，或您可以将其部署为独立服务器。</span><span class="sxs-lookup"><span data-stu-id="5b307-107">You can also collocate the Mediation Server on the Front End pool, or you can deploy it as a stand-alone server.</span></span> <span data-ttu-id="5b307-108">A / V 会议服务始终并置，如果启用会议。</span><span class="sxs-lookup"><span data-stu-id="5b307-108">The A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="5b307-109">A / V 会议服务是必需的如果在**选择功能**页上选择**会议**。</span><span class="sxs-lookup"><span data-stu-id="5b307-109">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="5b307-110">Enterprise Edition 前端池使用并置 A / V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="5b307-110">An Enterprise Edition Front End pool uses a collocated A/V Conferencing service.</span></span> <span data-ttu-id="5b307-111">如果会议未选中状态，置 A / V 会议服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="5b307-111">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="5b307-112">您可以并置在 Standard Edition 前端服务器或 Enterprise Edition 前端池上的中介服务器角色。</span><span class="sxs-lookup"><span data-stu-id="5b307-112">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="5b307-113">如果您部署直接 SIP 连接到限定的公用电话交换网 (pstn) 网关支持媒体绕过和域名系统 (DNS) 负载平衡，不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="5b307-113">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="5b307-114">由于合格网关支持的 DNS 负载平衡到中介服务器池，并且他们可以从池中的任何中介服务器接收通信，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="5b307-114">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="5b307-115">我们还建议并置中介服务器的前端池上部署 IP Pbx 或连接到 Internet 电话服务服务器提供商的会话边界控制器 (SBC) 时，只要满足以下条件的任何一个：</span><span class="sxs-lookup"><span data-stu-id="5b307-115">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="5b307-116">IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="5b307-116">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="5b307-117">IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="5b307-117">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="5b307-118">您可以使用 Microsoft Lync Server 2013 规划工具以评估是否要将并置中介服务器的前端池可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="5b307-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="5b307-119">如果您的环境无法满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="5b307-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="5b307-120">一般来说，如果您的组织具有高可用性和可伸缩性要求不建议并置的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="5b307-120">In general, collocation of Mediation Server is not recommended if your organization has high availability and scalability requirements.</span></span> <span data-ttu-id="5b307-121">有关详细信息并置在前端池中 Enterprise Edition 部署中的这些服务器角色，请参阅部署文档中的[Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="5b307-121">For details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="5b307-122">有关详细信息 A / V 会议功能和组件，请参阅[Planning for 会议](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)规划文档中。</span><span class="sxs-lookup"><span data-stu-id="5b307-122">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5b307-123">有关企业语音功能和组件，包括中介服务器的详细信息请参阅规划文档中的[规划中的业务服务器 2015 Skype 的企业语音](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="5b307-123">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


