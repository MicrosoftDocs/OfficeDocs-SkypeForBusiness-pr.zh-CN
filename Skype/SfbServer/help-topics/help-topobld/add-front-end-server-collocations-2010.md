---
title: 添加前端服务器搭配 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 企业版部署中，可以布置是 A / V 会议服务、 中介服务器，或同时在前端池，或者您可以部署每个作为独立服务器。 标准版服务器部署中，A / V 会议服务始终搭配如果启用会议了。
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="4fcc7-104">添加前端服务器搭配 2010</span><span class="sxs-lookup"><span data-stu-id="4fcc7-104">Add Front End Server Collocations 2010</span></span>
 
<span data-ttu-id="4fcc7-105">企业版部署中，可以布置是 A / V 会议服务、 中介服务器，或同时在前端池，或者您可以部署每个作为独立服务器。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-105">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers.</span></span> <span data-ttu-id="4fcc7-106">标准版服务器部署中，A / V 会议服务始终搭配如果启用会议了。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-106">For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4fcc7-107">A / V 会议服务是必需的如果在**选择功能**页上选择了**会议**。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-107">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="4fcc7-108">企业版前端池可能使用并入 A / V 会议服务或独立的 A / V 会议池。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-108">An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool.</span></span> <span data-ttu-id="4fcc7-109">如果会议没有选择，Collocate A / V 会议服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-109">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>
  
<span data-ttu-id="4fcc7-110">您可以配置标准版前端服务器或前端企业版池中的中介服务器角色。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="4fcc7-111">如果将直接 SIP 连接部署到支持媒体回避和域名系统 (DNS) 负载平衡的限定公共交换的电话网络 (PSTN) 网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="4fcc7-112">由于限定的网关的 DNS 负载平衡到池的中介服务器的能力并且能够从池中任何中介服务器接收通信，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="4fcc7-113">我们还建议，您布置中介服务器前端池上时您已部署 IP Pbx 或连接到互联网电话服务服务器提供程序的会话边框控制器 (SBC)，只要满足以下条件的任何操作：</span><span class="sxs-lookup"><span data-stu-id="4fcc7-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>
  
- <span data-ttu-id="4fcc7-114">IP PBX 或 SBC 被配置为从池中任何中介服务器接收通信，可以将路由通信统一到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
- <span data-ttu-id="4fcc7-115">IP PBX 或 SBC 被配置为从池中任何中介服务器接收通信，可以将路由通信统一到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
<span data-ttu-id="4fcc7-116">您可以使用 Microsoft Lync Server 2013，规划工具来评估是否想要布置中介服务器的前端池可以处理的负载。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="4fcc7-117">如果您的环境不能满足这些要求，您必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>
  
<span data-ttu-id="4fcc7-118">中的一个常规，配置 / V 会议服务器或中介服务器不建议如果您的组织具有高可用性和可伸缩性要求适用于有关的详细信息配置在企业版池中前端服务器角色部署，请参阅部署文档中[定义和配置前结束池](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="4fcc7-119">有关 A / V 会议功能和组件，请参阅[规划会议](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)的规划文档中。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="4fcc7-120">企业语音的功能和组件，包括中介服务器的详细信息请参阅规划文档中的[企业语音在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="4fcc7-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>
  

