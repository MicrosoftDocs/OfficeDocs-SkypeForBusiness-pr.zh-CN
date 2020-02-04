---
title: Lync Server 2013：用于监控的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="431fa-102">Lync Server 2013 中用于监控的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="431fa-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="431fa-103">_**主题上次修改时间：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="431fa-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="431fa-104">由于统一数据收集代理会在每个前端服务器上自动安装和激活，因此无需将服务器配置为监视服务器;每个前端服务器都已充当监视服务器。</span><span class="sxs-lookup"><span data-stu-id="431fa-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="431fa-105">但是，你将需要安装和配置数据库以用作你的监视数据的后端数据存储。</span><span class="sxs-lookup"><span data-stu-id="431fa-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="431fa-106">Microsoft Lync Server 2013 可以将以下任意数据库用作监视的后端存储：</span><span class="sxs-lookup"><span data-stu-id="431fa-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="431fa-107">Microsoft SQL Server 2008 R2 企业版</span><span class="sxs-lookup"><span data-stu-id="431fa-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="431fa-108">Microsoft SQL Server 2008 R2 标准版</span><span class="sxs-lookup"><span data-stu-id="431fa-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="431fa-109">Microsoft SQL Server 2012 企业版</span><span class="sxs-lookup"><span data-stu-id="431fa-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="431fa-110">Microsoft SQL Server 2012 标准版</span><span class="sxs-lookup"><span data-stu-id="431fa-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="431fa-111">请注意，您必须使用这些数据库的64位版本;32位版本的 SQL Server 无法用作监视的后端存储。</span><span class="sxs-lookup"><span data-stu-id="431fa-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="431fa-112">同样，Lync Server 2013 不支持 SQL Server 2008 或 SQL Server 2012 的速成版。</span><span class="sxs-lookup"><span data-stu-id="431fa-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="431fa-113">有关 Lync Server 2013 的数据库要求的详细信息，请参阅 Lync server 2013 支持指南中的 " [Lync server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)" 主题。</span><span class="sxs-lookup"><span data-stu-id="431fa-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="431fa-114">请记住，必须先安装并配置 SQL Server，然后再部署和配置监控。</span><span class="sxs-lookup"><span data-stu-id="431fa-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="431fa-115">但是，你只需部署 SQL Server 本身;您无需提前设置监视数据库。</span><span class="sxs-lookup"><span data-stu-id="431fa-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="431fa-116">因此，当你发布 Lync Server 拓扑时，将自动为你创建这些数据库。</span><span class="sxs-lookup"><span data-stu-id="431fa-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="431fa-p104">监控数据可以与其他类型的数据共享 SQL Server 实例。通常，呼叫详细信息记录数据库 (LcsCdr) 和体验质量数据库 (QoEMetrics) 共享相同的 SQL 实例；这两个监控数据库与存档数据库 (LcsLog) 位于相同的 SQL 实例中也是很常见的。对 SQL Server 实例的唯一真正要求是，SQL Server 的任何一个实例仅限于以下各项：</span><span class="sxs-lookup"><span data-stu-id="431fa-p104">Monitoring data can share a SQL Server instance with other types of data. Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog). About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="431fa-120">Lync Server 2013 后端数据库的一个实例。</span><span class="sxs-lookup"><span data-stu-id="431fa-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="431fa-121">（作为一般规则，建议不要将监视数据库 collocated 在同一 SQL 实例中，甚至可以在同一台计算机上，而不是后端数据库。</span><span class="sxs-lookup"><span data-stu-id="431fa-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="431fa-122">尽管技术上可以使用后端数据库所需的磁盘空间来运行监视数据库的风险。）</span><span class="sxs-lookup"><span data-stu-id="431fa-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="431fa-123">呼叫详细信息记录数据库的一个实例。</span><span class="sxs-lookup"><span data-stu-id="431fa-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="431fa-124">体验质量数据库的一个实例。</span><span class="sxs-lookup"><span data-stu-id="431fa-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="431fa-125">存档数据库的一个实例。</span><span class="sxs-lookup"><span data-stu-id="431fa-125">One instance of the archiving database.</span></span>

<span data-ttu-id="431fa-126">换句话说，在 SQL Server 的同一实例中，不能有两个 LcsCdr 数据库实例。</span><span class="sxs-lookup"><span data-stu-id="431fa-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="431fa-127">如果需要 LcsCdr 数据库的多个实例，则需要配置多个 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="431fa-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="431fa-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="431fa-128">See Also</span></span>


[<span data-ttu-id="431fa-129">在 Lync Server 2013 中部署监视</span><span class="sxs-lookup"><span data-stu-id="431fa-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

