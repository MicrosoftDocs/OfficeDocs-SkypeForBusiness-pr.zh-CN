---
title: 添加前端服务器搭配
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: 企业版部署中，A / V 会议服务在前端池上搭配。 也可以布置在前端池中，中介服务器，或您可以将其部署为独立服务器。 A / V 会议服务始终搭配如果启用会议了。
ms.openlocfilehash: c68ed9e05252d72739f2912f109951d0be723699
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations"></a><span data-ttu-id="ab968-105">添加前端服务器搭配</span><span class="sxs-lookup"><span data-stu-id="ab968-105">Add Front End Server Collocations</span></span>
 
<span data-ttu-id="ab968-106">企业版部署中，A / V 会议服务在前端池上搭配。</span><span class="sxs-lookup"><span data-stu-id="ab968-106">For an Enterprise Edition deployment, the A/V Conferencing service is collocated on the Front End pool.</span></span> <span data-ttu-id="ab968-107">也可以布置在前端池中，中介服务器，或您可以将其部署为独立服务器。</span><span class="sxs-lookup"><span data-stu-id="ab968-107">You can also collocate the Mediation Server on the Front End pool, or you can deploy it as a stand-alone server.</span></span> <span data-ttu-id="ab968-108">A / V 会议服务始终搭配如果启用会议了。</span><span class="sxs-lookup"><span data-stu-id="ab968-108">The A/V Conferencing service is always collocated if conferencing is enabled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab968-109">A / V 会议服务是必需的如果在**选择功能**页上选择了**会议**。</span><span class="sxs-lookup"><span data-stu-id="ab968-109">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="ab968-110">企业版前端池使用并入 A / V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="ab968-110">An Enterprise Edition Front End pool uses a collocated A/V Conferencing service.</span></span> <span data-ttu-id="ab968-111">如果会议没有选择，Collocate A / V 会议服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="ab968-111">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>
  
<span data-ttu-id="ab968-112">您可以配置标准版前端服务器或前端企业版池中的中介服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ab968-112">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="ab968-113">如果将直接 SIP 连接部署到支持媒体回避和域名系统 (DNS) 负载平衡的限定公共交换的电话网络 (PSTN) 网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="ab968-113">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="ab968-114">由于限定的网关的 DNS 负载平衡到池的中介服务器的能力并且能够从池中任何中介服务器接收通信，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="ab968-114">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="ab968-115">我们还建议，您布置中介服务器前端池上时您已部署 IP Pbx 或连接到互联网电话服务服务器提供程序的会话边框控制器 (SBC)，只要满足以下条件的任何操作：</span><span class="sxs-lookup"><span data-stu-id="ab968-115">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>
  
- <span data-ttu-id="ab968-116">IP PBX 或 SBC 被配置为从池中任何中介服务器接收通信，可以将路由通信统一到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ab968-116">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
- <span data-ttu-id="ab968-117">IP PBX 或 SBC 被配置为从池中任何中介服务器接收通信，可以将路由通信统一到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ab968-117">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
<span data-ttu-id="ab968-118">您可以使用 Microsoft Lync Server 2013，规划工具来评估是否想要布置中介服务器的前端池可以处理的负载。</span><span class="sxs-lookup"><span data-stu-id="ab968-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="ab968-119">如果您的环境不能满足这些要求，您必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="ab968-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>
  
<span data-ttu-id="ab968-120">一般情况下，建议不要中介服务器的配置，如果您的组织具有高可用性和可扩展性要求。</span><span class="sxs-lookup"><span data-stu-id="ab968-120">In general, collocation of Mediation Server is not recommended if your organization has high availability and scalability requirements.</span></span> <span data-ttu-id="ab968-121">有关配置这些前端池中企业版部署中的服务器角色的详细信息，请参阅部署文档中的[定义和配置前结束池](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ab968-121">For details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="ab968-122">有关 A / V 会议功能和组件，请参阅[规划会议](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)的规划文档中。</span><span class="sxs-lookup"><span data-stu-id="ab968-122">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ab968-123">企业语音的功能和组件，包括中介服务器的详细信息请参阅规划文档中的[企业语音在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="ab968-123">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>
  

