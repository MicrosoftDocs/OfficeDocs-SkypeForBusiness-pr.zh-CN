---
title: Lync Server 2013：估计语音使用和流量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06093893c5de9a08322e1577fbbbe6779d4209cc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="a6062-102">估计 Lync Server 2013 的语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="a6062-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6062-103">_**主题上次修改时间：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="a6062-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="a6062-104">Microsoft Lync Server 2013、计划工具使用以下指标估计每个站点上的用户流量以及支持该流量所需的端口数。</span><span class="sxs-lookup"><span data-stu-id="a6062-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="a6062-105">对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="a6062-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="a6062-106">对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="a6062-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="a6062-107">对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="a6062-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="a6062-108">端口数依次确定所需中介服务器和网关的数量。</span><span class="sxs-lookup"><span data-stu-id="a6062-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="a6062-109">大多数组织考虑将范围从2个端口部署到最多960端口的公共交换电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="a6062-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="a6062-110">（甚至更大的网关，但主要由电话服务提供商使用。）</span><span class="sxs-lookup"><span data-stu-id="a6062-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="a6062-p102">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="a6062-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

