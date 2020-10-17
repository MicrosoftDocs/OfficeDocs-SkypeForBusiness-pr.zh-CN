---
title: Lync Server 2013：了解 SQL Server 的防火墙要求
description: Lync Server 2013：了解 SQL Server 的防火墙要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434474b36ced0fe64b9398f7d0e6136ff523a93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542378"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="c20cf-103">了解使用 Lync Server 2013 的 SQL Server 的防火墙要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-103">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c20cf-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c20cf-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c20cf-105">对于标准版部署，会在安装 Lync Server 2013 期间自动创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="c20cf-105">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="c20cf-106">但是，对于企业版部署，必须在 SQL Server 后端服务器上手动配置防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="c20cf-106">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="c20cf-107">TCP/CP 协议只允许给定端口对给定 IP 地址使用一次。</span><span class="sxs-lookup"><span data-stu-id="c20cf-107">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="c20cf-108">这意味着，对于基于 SQL Server 的服务器，可以为默认数据库实例分配默认 TCP 端口 1433。</span><span class="sxs-lookup"><span data-stu-id="c20cf-108">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="c20cf-109">对于其他任何实例，将需要使用 SQL Server 配置管理器分配唯一并且未使用的端口。</span><span class="sxs-lookup"><span data-stu-id="c20cf-109">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="c20cf-110">本主题包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="c20cf-110">This topic covers:</span></span>

  - <span data-ttu-id="c20cf-111">使用默认实例时防火墙例外的要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-111">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="c20cf-112">SQL Server Browser 服务的防火墙例外要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-112">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="c20cf-113">使用命名实例时静态侦听端口的要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-113">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="c20cf-114">使用默认实例时防火墙例外的要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-114">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="c20cf-115">如果在部署 Lync Server 2013 时对任何数据库使用 SQL Server 默认实例，则使用以下防火墙规则要求来帮助确保从前端池到 SQL Server 默认实例的通信。</span><span class="sxs-lookup"><span data-stu-id="c20cf-115">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20cf-116">协议</span><span class="sxs-lookup"><span data-stu-id="c20cf-116">Protocol</span></span></th>
<th><span data-ttu-id="c20cf-117">端口</span><span class="sxs-lookup"><span data-stu-id="c20cf-117">Port</span></span></th>
<th><span data-ttu-id="c20cf-118">Direction</span><span class="sxs-lookup"><span data-stu-id="c20cf-118">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20cf-119">TCP</span><span class="sxs-lookup"><span data-stu-id="c20cf-119">TCP</span></span></p></td>
<td><p><span data-ttu-id="c20cf-120">1433</span><span class="sxs-lookup"><span data-stu-id="c20cf-120">1433</span></span></p></td>
<td><p><span data-ttu-id="c20cf-121">入站至 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c20cf-121">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="c20cf-122">SQL Server Browser 服务的防火墙例外要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-122">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="c20cf-123">SQL Server Browser 服务将查找数据库实例，并与配置为供该实例（命名实例或默认实例）使用的端口进行通信。</span><span class="sxs-lookup"><span data-stu-id="c20cf-123">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20cf-124">协议</span><span class="sxs-lookup"><span data-stu-id="c20cf-124">Protocol</span></span></th>
<th><span data-ttu-id="c20cf-125">端口</span><span class="sxs-lookup"><span data-stu-id="c20cf-125">Port</span></span></th>
<th><span data-ttu-id="c20cf-126">Direction</span><span class="sxs-lookup"><span data-stu-id="c20cf-126">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20cf-127">UDP</span><span class="sxs-lookup"><span data-stu-id="c20cf-127">UDP</span></span></p></td>
<td><p><span data-ttu-id="c20cf-128">1434</span><span class="sxs-lookup"><span data-stu-id="c20cf-128">1434</span></span></p></td>
<td><p><span data-ttu-id="c20cf-129">进货</span><span class="sxs-lookup"><span data-stu-id="c20cf-129">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="c20cf-130">使用命名实例时静态侦听端口的要求</span><span class="sxs-lookup"><span data-stu-id="c20cf-130">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="c20cf-131">在 SQL Server 配置中对支持 Lync Server 2013 的数据库使用命名实例时，可以使用 SQL Server 配置管理器配置静态端口。</span><span class="sxs-lookup"><span data-stu-id="c20cf-131">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="c20cf-132">将静态端口分配至每个命名实例后，在防火墙内为每个静态端口创建例外。</span><span class="sxs-lookup"><span data-stu-id="c20cf-132">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20cf-133">协议</span><span class="sxs-lookup"><span data-stu-id="c20cf-133">Protocol</span></span></th>
<th><span data-ttu-id="c20cf-134">端口</span><span class="sxs-lookup"><span data-stu-id="c20cf-134">Port</span></span></th>
<th><span data-ttu-id="c20cf-135">Direction</span><span class="sxs-lookup"><span data-stu-id="c20cf-135">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20cf-136">TCP</span><span class="sxs-lookup"><span data-stu-id="c20cf-136">TCP</span></span></p></td>
<td><p><span data-ttu-id="c20cf-137">静态定义</span><span class="sxs-lookup"><span data-stu-id="c20cf-137">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="c20cf-138">进货</span><span class="sxs-lookup"><span data-stu-id="c20cf-138">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="c20cf-139">SQL Server 文档</span><span class="sxs-lookup"><span data-stu-id="c20cf-139">SQL Server Documentation</span></span>

<span data-ttu-id="c20cf-140">Microsoft SQL Server 2012 文档提供了有关如何配置数据库的防火墙访问的详细指南。</span><span class="sxs-lookup"><span data-stu-id="c20cf-140">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="c20cf-141">有关 Microsoft SQL Server 2012 的详细信息，请参阅位于的 "配置 Windows 防火墙以允许 SQL Server 访问" [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) 。</span><span class="sxs-lookup"><span data-stu-id="c20cf-141">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

