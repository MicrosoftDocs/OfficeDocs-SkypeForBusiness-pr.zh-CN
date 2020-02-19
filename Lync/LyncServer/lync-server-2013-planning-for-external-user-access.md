---
title: Lync Server 2013：规划外部用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15b4a64c729268efcbdf2bb572c47122d4b41510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ff84b-102">在 Lync Server 2013 中规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="ff84b-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff84b-103">_**上次修改的主题：** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="ff84b-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="ff84b-p101">大部分组织中的通信涉及内部网络外的服务和用户。这些服务和用户包括临时或永久位于组织外的员工、客户或伙伴组织的员工、使用公共即时消息 (IM) 服务的人员以及受邀参加会议和发布会的潜在客户、合作伙伴或匿名用户。在本文档中，这些人员统称为*外部用户*。</span><span class="sxs-lookup"><span data-stu-id="ff84b-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="ff84b-107">使用 Microsoft Lync Server 2013，组织中的用户可以使用 IM 和状态与外部用户进行通信，并且他们可以参与音频/视频（A/V）会议和与您的非现场员工和其他类型的外部用户的网络会议。</span><span class="sxs-lookup"><span data-stu-id="ff84b-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="ff84b-108">还可以支持从移动设备和通过企业语音进行外部访问。</span><span class="sxs-lookup"><span data-stu-id="ff84b-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="ff84b-109">不是组织成员的外部用户可以参与 Lync Server 2013 会议，从而允许匿名与会者。</span><span class="sxs-lookup"><span data-stu-id="ff84b-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="ff84b-110">若要支持整个组织的防火墙中的通信，请在外围网络（也称为 DMZ、隔离区域和屏蔽子网）中部署 Lync Server 2013 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="ff84b-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="ff84b-111">边缘服务器可控制防火墙外的用户如何连接到内部 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="ff84b-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="ff84b-112">还控制从防火墙内发出的与外部用户的通信。</span><span class="sxs-lookup"><span data-stu-id="ff84b-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="ff84b-113">根据您的要求，您可在一个或多个位置部署一台或多台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="ff84b-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="ff84b-114">本节介绍了 Lync Server 2013 中的外部用户访问方案，并说明了如何规划边缘和反向代理拓扑。</span><span class="sxs-lookup"><span data-stu-id="ff84b-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff84b-115">虽然您需要一台边缘服务器来支持企业语音和外部用户访问，但本节重点介绍了对 IM、状态、A/V 会议、联合、web 会议和 Lync Mobile 的支持。</span><span class="sxs-lookup"><span data-stu-id="ff84b-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="ff84b-116">有关企业语音支持的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 中规划企业语音</A>。</span><span class="sxs-lookup"><span data-stu-id="ff84b-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff84b-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ff84b-117">In This Section</span></span>

  - [<span data-ttu-id="ff84b-118">Lync Server 2013 中影响边缘服务器规划的更改</span><span class="sxs-lookup"><span data-stu-id="ff84b-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="ff84b-119">Lync Server 2013 的外部用户访问组件的系统要求</span><span class="sxs-lookup"><span data-stu-id="ff84b-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="ff84b-120">Lync Server 2013 中的外部用户访问概述</span><span class="sxs-lookup"><span data-stu-id="ff84b-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="ff84b-121">了解 Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="ff84b-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="ff84b-122">在 Lync Server 2013 中选择拓扑</span><span class="sxs-lookup"><span data-stu-id="ff84b-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="ff84b-123">Lync Server 2013 中的数据收集</span><span class="sxs-lookup"><span data-stu-id="ff84b-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="ff84b-124">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="ff84b-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="ff84b-125">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="ff84b-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="ff84b-126">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="ff84b-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="ff84b-127">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="ff84b-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

