---
title: Lync Server 2013：部署概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33328e124a1b444b4639b85bc6c1941c55f5ed1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="fdbf1-102">Lync Server 2013 部署概述</span><span class="sxs-lookup"><span data-stu-id="fdbf1-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdbf1-103">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="fdbf1-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="fdbf1-104">Lync Server 2013 Enterprise Edition 和 Lync Server 2013 Standard Edition 的主要区别在于，Standard Edition 不支持企业版中包含的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="fdbf1-105">为实现高可用性，您需要将多个前端服务器部署到一个池，然后可以镜像运行 SQL Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="fdbf1-106">使用 Enterprise Edition，可以选择并置或定义独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="fdbf1-107">监视服务器和存档服务器可以使用运行 SQL Server 的独立服务器。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="fdbf1-108">或者，它们可以在数据库服务器上为前端服务器和池运行 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="fdbf1-109">运行 Lync Server 2013 Standard Edition 的服务器适用于从组织的主部署中删除的地理位置较小的组织和远程位置。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="fdbf1-110">在灾难发生时，将两个标准版服务器服务器结合在一起进行故障转移，以支持最高为5000个用户。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="fdbf1-111">您无法像企业版中的前端服务器那样池标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="fdbf1-112">此外，Standard Edition 使用的 SQL Server 数据库是运行 SQL Server Express 的并置服务器，旨在处理 Standard Edition Server 工作负载。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="fdbf1-113">这并不是说所有角色都必须驻留在 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="fdbf1-114">您可以有独立的中介服务器和边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="fdbf1-115">中央管理存储的 SQL Server 数据库和用于 Lync Server 2013 的目的必须驻留在 Standard Edition server 并置和运行 SQL Server 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="fdbf1-116">监视服务器和存档服务器将独立服务器与 SQL Server 数据库一起使用。</span><span class="sxs-lookup"><span data-stu-id="fdbf1-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

