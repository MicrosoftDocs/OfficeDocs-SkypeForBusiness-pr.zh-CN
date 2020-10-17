---
title: Lync Server 2013：规划监视
description: Lync Server 2013：规划监视。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for monitoring
ms:assetid: 26cead5a-183c-42f1-a4b0-0e8d61c6159d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204752(v=OCS.15)
ms:contentKeyID: 48183671
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ee78f06423bc167e26455d399ce2dd16f24262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549328"
---
# <a name="planning-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="0b8ba-103">在 Lync Server 2013 中规划监视</span><span class="sxs-lookup"><span data-stu-id="0b8ba-103">Planning for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b8ba-104">_**上次修改的主题：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="0b8ba-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="0b8ba-105">Microsoft Lync Server 2013 中的监控服务为管理员提供了一种方法，用于收集组织中发生的通信会话的使用率、趋势和服务质量数据。</span><span class="sxs-lookup"><span data-stu-id="0b8ba-105">The monitoring service in Microsoft Lync Server 2013 provides a way for administrators to collect usage, trend, and quality of service data for the communication sessions that take place in their organization.</span></span> <span data-ttu-id="0b8ba-106">Lync Server 2013 中的监控不再需要单独的服务器角色;相反，监视服务内置在每个前端服务器中。</span><span class="sxs-lookup"><span data-stu-id="0b8ba-106">Monitoring in Lync Server 2013 no longer requires a separate server role; instead, the monitoring service is built into each Front End server.</span></span> <span data-ttu-id="0b8ba-107">但是，默认情况下，在 Lync Server 2013 中不启用监控功能。</span><span class="sxs-lookup"><span data-stu-id="0b8ba-107">However, by default monitoring is not enabled in Lync Server 2013.</span></span> <span data-ttu-id="0b8ba-108">本文档将帮助您确定是否应在贵组织中启用该功能。</span><span class="sxs-lookup"><span data-stu-id="0b8ba-108">This document will help you determine whether or not monitoring should be enabled in your organization.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b8ba-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="0b8ba-109">In This Section</span></span>

  - [<span data-ttu-id="0b8ba-110">Lync Server 2013 中的监控概述</span><span class="sxs-lookup"><span data-stu-id="0b8ba-110">Overview of monitoring in Lync Server 2013</span></span>](lync-server-2013-overview-of-monitoring.md)

  - [<span data-ttu-id="0b8ba-111">定义在 Lync Server 2013 中进行监视的要求</span><span class="sxs-lookup"><span data-stu-id="0b8ba-111">Defining your requirements for monitoring in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-monitoring.md)

  - [<span data-ttu-id="0b8ba-112">在 Lync Server 2013 中启用监视</span><span class="sxs-lookup"><span data-stu-id="0b8ba-112">Enabling monitoring in Lync Server 2013</span></span>](lync-server-2013-enabling-monitoring.md)

  - [<span data-ttu-id="0b8ba-113">在 Lync Server 2013 中访问监视数据</span><span class="sxs-lookup"><span data-stu-id="0b8ba-113">Accessing monitoring data in Lync Server 2013</span></span>](lync-server-2013-accessing-monitoring-data.md)

  - [<span data-ttu-id="0b8ba-114">Lync Server 2013 中用于监控的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="0b8ba-114">Components and topologies for monitoring in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-monitoring.md)

  - [<span data-ttu-id="0b8ba-115">Lync Server 2013 中用于监视的部署清单</span><span class="sxs-lookup"><span data-stu-id="0b8ba-115">Deployment checklist for monitoring in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-monitoring.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

