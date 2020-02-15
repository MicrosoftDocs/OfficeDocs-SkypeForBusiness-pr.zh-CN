---
title: Lync Server 2013：了解 SQL Server 的防火墙要求
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
ms.openlocfilehash: ba04284106bcd1b0cbf17d214d8ad0b1a1ff9024
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="5658a-102">了解使用 Lync Server 2013 的 SQL Server 的防火墙要求</span><span class="sxs-lookup"><span data-stu-id="5658a-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5658a-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5658a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5658a-104">对于标准版部署，会在安装 Lync Server 2013 期间自动创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="5658a-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="5658a-105">但是，对于企业版部署，必须在 SQL Server 后端服务器上手动配置防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="5658a-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="5658a-106">TCP/CP 协议只允许给定端口对给定 IP 地址使用一次。</span><span class="sxs-lookup"><span data-stu-id="5658a-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="5658a-107">这意味着，对于基于 SQL Server 的服务器，可以为默认数据库实例分配默认 TCP 端口 1433。</span><span class="sxs-lookup"><span data-stu-id="5658a-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="5658a-108">对于其他任何实例，将需要使用 SQL Server 配置管理器分配唯一并且未使用的端口。</span><span class="sxs-lookup"><span data-stu-id="5658a-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="5658a-109">本主题包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="5658a-109">This topic covers:</span></span>

  - <span data-ttu-id="5658a-110">使用默认实例时防火墙例外的要求</span><span class="sxs-lookup"><span data-stu-id="5658a-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="5658a-111">SQL Server Browser 服务的防火墙例外要求</span><span class="sxs-lookup"><span data-stu-id="5658a-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="5658a-112">使用命名实例时静态侦听端口的要求</span><span class="sxs-lookup"><span data-stu-id="5658a-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="5658a-113">使用默认实例时防火墙例外的要求</span><span class="sxs-lookup"><span data-stu-id="5658a-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="5658a-114">如果在部署 Lync Server 2013 时对任何数据库使用 SQL Server 默认实例，则使用以下防火墙规则要求来帮助确保从前端池到 SQL Server 默认实例的通信。</span><span class="sxs-lookup"><span data-stu-id="5658a-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5658a-115">协议</span><span class="sxs-lookup"><span data-stu-id="5658a-115">Protocol</span></span></th>
<th><span data-ttu-id="5658a-116">端口</span><span class="sxs-lookup"><span data-stu-id="5658a-116">Port</span></span></th>
<th><span data-ttu-id="5658a-117">Direction</span><span class="sxs-lookup"><span data-stu-id="5658a-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5658a-118">TCP</span><span class="sxs-lookup"><span data-stu-id="5658a-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="5658a-119">1433</span><span class="sxs-lookup"><span data-stu-id="5658a-119">1433</span></span></p></td>
<td><p><span data-ttu-id="5658a-120">入站至 SQL Server</span><span class="sxs-lookup"><span data-stu-id="5658a-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="5658a-121">SQL Server Browser 服务的防火墙例外要求</span><span class="sxs-lookup"><span data-stu-id="5658a-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="5658a-122">SQL Server Browser 服务将查找数据库实例，并与配置为供该实例（命名实例或默认实例）使用的端口进行通信。</span><span class="sxs-lookup"><span data-stu-id="5658a-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5658a-123">协议</span><span class="sxs-lookup"><span data-stu-id="5658a-123">Protocol</span></span></th>
<th><span data-ttu-id="5658a-124">端口</span><span class="sxs-lookup"><span data-stu-id="5658a-124">Port</span></span></th>
<th><span data-ttu-id="5658a-125">Direction</span><span class="sxs-lookup"><span data-stu-id="5658a-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5658a-126">UDP</span><span class="sxs-lookup"><span data-stu-id="5658a-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="5658a-127">1434</span><span class="sxs-lookup"><span data-stu-id="5658a-127">1434</span></span></p></td>
<td><p><span data-ttu-id="5658a-128">进货</span><span class="sxs-lookup"><span data-stu-id="5658a-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="5658a-129">使用命名实例时静态侦听端口的要求</span><span class="sxs-lookup"><span data-stu-id="5658a-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="5658a-130">在 SQL Server 配置中对支持 Lync Server 2013 的数据库使用命名实例时，可以使用 SQL Server 配置管理器配置静态端口。</span><span class="sxs-lookup"><span data-stu-id="5658a-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="5658a-131">将静态端口分配至每个命名实例后，在防火墙内为每个静态端口创建例外。</span><span class="sxs-lookup"><span data-stu-id="5658a-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5658a-132">协议</span><span class="sxs-lookup"><span data-stu-id="5658a-132">Protocol</span></span></th>
<th><span data-ttu-id="5658a-133">端口</span><span class="sxs-lookup"><span data-stu-id="5658a-133">Port</span></span></th>
<th><span data-ttu-id="5658a-134">Direction</span><span class="sxs-lookup"><span data-stu-id="5658a-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5658a-135">TCP</span><span class="sxs-lookup"><span data-stu-id="5658a-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="5658a-136">静态定义</span><span class="sxs-lookup"><span data-stu-id="5658a-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="5658a-137">进货</span><span class="sxs-lookup"><span data-stu-id="5658a-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="5658a-138">SQL Server 文档</span><span class="sxs-lookup"><span data-stu-id="5658a-138">SQL Server Documentation</span></span>

<span data-ttu-id="5658a-139">Microsoft SQL Server 2012 文档提供了有关如何配置数据库的防火墙访问的详细指南。</span><span class="sxs-lookup"><span data-stu-id="5658a-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="5658a-140">有关 Microsoft SQL Server 2012 的详细信息，请参阅位于[http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)的 "配置 Windows 防火墙以允许 SQL Server 访问"。</span><span class="sxs-lookup"><span data-stu-id="5658a-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

