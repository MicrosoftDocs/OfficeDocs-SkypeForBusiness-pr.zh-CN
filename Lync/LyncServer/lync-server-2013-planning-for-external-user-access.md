---
title: Lync Server 2013：规划外部用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="7ecb3-102">在 Lync Server 2013 中规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="7ecb3-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ecb3-103">_**主题上次修改时间:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="7ecb3-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="7ecb3-104">大多数组织中的通信涉及不在内部网络内部的服务和用户。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="7ecb3-105">这些服务和用户包括临时或永久离开的员工、客户或合作伙伴组织的员工、使用公共即时消息 (IM) 服务的用户、你邀请的客户、合作伙伴和匿名用户会议和演示文稿。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="7ecb3-106">在本文档中, 这些人统称为*外部用户*。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="7ecb3-107">使用 Microsoft Lync Server 2013, 组织中的用户可以使用 IM 和状态与外部用户进行通信, 并且他们可以使用您的非现场员工和其他类型的外部用户参与音频/视频 (A/V) 会议和 web 会议。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="7ecb3-108">您还可以通过移动设备和企业语音支持外部访问。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="7ecb3-109">不是组织成员的外部用户可以参与 Lync Server 2013 会议, 从而允许匿名与会者参与。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="7ecb3-110">若要支持整个组织的防火墙中的通信, 请在外围网络 (也称为 DMZ、隔离区和屏蔽子网) 中部署 Lync Server 2013 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="7ecb3-111">边缘服务器控制防火墙外的用户可以如何连接到内部 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="7ecb3-112">它还控制与来源于防火墙的外部用户的通信。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="7ecb3-113">可以在一个或多个位置部署一个或多个边缘服务器, 具体取决于你的要求。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="7ecb3-114">本部分介绍 Lync Server 2013 中的外部用户访问方案, 并介绍如何规划边缘和反向代理拓扑。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ecb3-115">虽然您需要一个 Edge 服务器来支持企业语音和外部用户访问, 但本部分重点介绍 IM、状态、A/V 会议、联盟、web 会议和 Lync Mobile 的支持。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="7ecb3-116">有关企业语音支持的详细信息, 请参阅规划文档中的<A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 中的 "规划企业语音</A>"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ecb3-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="7ecb3-117">In This Section</span></span>

  - [<span data-ttu-id="7ecb3-118">Lync Server 2013 中影响边缘服务器规划的更改</span><span class="sxs-lookup"><span data-stu-id="7ecb3-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="7ecb3-119">Lync Server 2013 的外部用户访问组件的系统要求</span><span class="sxs-lookup"><span data-stu-id="7ecb3-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="7ecb3-120">Lync Server 2013 中的外部用户访问概述</span><span class="sxs-lookup"><span data-stu-id="7ecb3-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="7ecb3-121">了解 Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="7ecb3-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="7ecb3-122">在 Lync Server 2013 中选择拓扑</span><span class="sxs-lookup"><span data-stu-id="7ecb3-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="7ecb3-123">Lync Server 2013 中的数据收集</span><span class="sxs-lookup"><span data-stu-id="7ecb3-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="7ecb3-124">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="7ecb3-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="7ecb3-125">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="7ecb3-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="7ecb3-126">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="7ecb3-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="7ecb3-127">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="7ecb3-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

