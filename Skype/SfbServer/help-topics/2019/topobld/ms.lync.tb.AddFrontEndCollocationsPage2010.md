---
title: 添加前端服务器并置 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 对于 Enterprise Edition 部署中，您可以将并置任一 A / V 会议服务、 中介服务器，或两者上的前端池，也可以部署其中各个作为独立服务器。 对于 Standard Edition 服务器部署，A / V 会议服务始终并置，如果启用会议。
ms.openlocfilehash: 495132c2dc290e175447e6a58eee04fcfab2892a
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964553"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="dccb1-104">添加前端服务器并置 2010</span><span class="sxs-lookup"><span data-stu-id="dccb1-104">Add Front End Server Collocations 2010</span></span>
 
<span data-ttu-id="dccb1-105">对于 Enterprise Edition 部署中，您可以将并置任一 A / V 会议服务、 中介服务器，或两者上的前端池，也可以部署其中各个作为独立服务器。</span><span class="sxs-lookup"><span data-stu-id="dccb1-105">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers.</span></span> <span data-ttu-id="dccb1-106">对于 Standard Edition 服务器部署，A / V 会议服务始终并置，如果启用会议。</span><span class="sxs-lookup"><span data-stu-id="dccb1-106">For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dccb1-107">A / V 会议服务是必需的如果在**选择功能**页上选择**会议**。</span><span class="sxs-lookup"><span data-stu-id="dccb1-107">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="dccb1-108">Enterprise Edition 前端池可以使用并置 A / V 会议服务或独立 A / V 会议池。</span><span class="sxs-lookup"><span data-stu-id="dccb1-108">An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool.</span></span> <span data-ttu-id="dccb1-109">如果会议未选中状态，置 A / V 会议服务将不可用。</span><span class="sxs-lookup"><span data-stu-id="dccb1-109">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>
  
<span data-ttu-id="dccb1-110">您可以并置在 Standard Edition 前端服务器或 Enterprise Edition 前端池上的中介服务器角色。</span><span class="sxs-lookup"><span data-stu-id="dccb1-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="dccb1-111">如果您部署直接 SIP 连接到限定的公用电话交换网 (pstn) 网关支持媒体绕过和域名系统 (DNS) 负载平衡，不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="dccb1-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="dccb1-112">由于合格网关支持的 DNS 负载平衡到中介服务器池，并且他们可以从池中的任何中介服务器接收通信，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="dccb1-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="dccb1-113">我们还建议并置中介服务器的前端池上部署 IP Pbx 或连接到 Internet 电话服务服务器提供商的会话边界控制器 (SBC) 时，只要满足以下条件的任何一个：</span><span class="sxs-lookup"><span data-stu-id="dccb1-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>
  
- <span data-ttu-id="dccb1-114">IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="dccb1-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
- <span data-ttu-id="dccb1-115">IP-PBX 或 SBC 已配置为接收来自池中任意中介服务器，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="dccb1-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
<span data-ttu-id="dccb1-116">规划工具可用于评估是否要将并置中介服务器的前端池可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="dccb1-116">You can use the Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="dccb1-117">如果您的环境无法满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="dccb1-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>
  
<span data-ttu-id="dccb1-118">在常规，并置的 A / V 会议服务器或中介服务器不建议如果您的组织具有高可用性和可伸缩性掌握有关详细信息并置在前端池中 Enterprise Edition 中的这些服务器角色部署，请参阅部署文档中的[Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="dccb1-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="dccb1-119">有关详细信息 A / V 会议功能和组件，请参阅[Planning for 会议](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)规划文档中。</span><span class="sxs-lookup"><span data-stu-id="dccb1-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="dccb1-120">有关企业语音功能和组件，包括中介服务器的详细信息请参阅规划文档中的[规划 Skype 业务服务器中的企业语音](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="dccb1-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>
  

