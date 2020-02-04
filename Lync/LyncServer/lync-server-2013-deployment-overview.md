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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="429ab-102">Lync Server 2013 部署概述</span><span class="sxs-lookup"><span data-stu-id="429ab-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="429ab-103">_**主题上次修改时间：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="429ab-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="429ab-104">Lync Server 2013 企业版和 Lync Server 2013 标准版之间的主要区别是标准版不支持企业版中包含的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="429ab-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="429ab-105">为了获得高可用性，你需要将多个前端服务器部署到一个池，然后你可以镜像运行 SQL Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="429ab-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="429ab-106">使用企业版，您可以选择 collocate 或定义独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="429ab-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="429ab-107">监视服务器和存档服务器可以使用运行 SQL Server 的独立服务器。</span><span class="sxs-lookup"><span data-stu-id="429ab-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="429ab-108">或者，他们可以在数据库服务器上为前端服务器和池运行 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="429ab-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="429ab-109">运行 Lync Server 2013 标准版的服务器适用于从组织的主部署中删除的较小组织和远程位置。</span><span class="sxs-lookup"><span data-stu-id="429ab-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="429ab-110">在灾难情况下，将两个标准版服务器服务器结合在一起以进行故障转移，从而支持最多5000用户。</span><span class="sxs-lookup"><span data-stu-id="429ab-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="429ab-111">不能像企业版中的前端服务器那样对标准版服务器进行池化。</span><span class="sxs-lookup"><span data-stu-id="429ab-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="429ab-112">此外，标准版使用的 SQL Server 数据库是运行 SQL Server Express 的 collocated 服务器，设计用于处理标准版服务器工作负荷。</span><span class="sxs-lookup"><span data-stu-id="429ab-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="429ab-113">这并不是说所有角色必须驻留在标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="429ab-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="429ab-114">你可以有独立的中介服务器和边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="429ab-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="429ab-115">用于中央管理存储的 SQL Server 数据库和适用于 Lync Server 2013 的用途必须驻留在标准版服务器 collocated 上，并与运行 SQL Server 的服务器配合。</span><span class="sxs-lookup"><span data-stu-id="429ab-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="429ab-116">监视服务器和存档服务器将独立服务器与 SQL Server 数据库结合使用。</span><span class="sxs-lookup"><span data-stu-id="429ab-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

