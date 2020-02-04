---
title: Lync Server 2013：为 Lync Server 配置 SQL Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="f5a28-102">为 Lync Server 2013 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5a28-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5a28-103">_**主题上次修改时间：** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="f5a28-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="f5a28-104">本部分中的主题讨论如何部署和配置 SQL Server 以在 Lync Server 的企业部署中使用。</span><span class="sxs-lookup"><span data-stu-id="f5a28-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="f5a28-105">标准版服务器使用 collocated SQL server Express 版本的 SQL Server Express 版本，该版本适合于标准版服务器的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="f5a28-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="f5a28-106">Lync Server 2013 中央管理存储为池中的所有企业版服务器保留用户数据，并且设计为位于基于 SQL Server 的后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="f5a28-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="f5a28-107">作为集中的存储库，中央管理存储无法与任何其他 Lync Server 2013 角色安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="f5a28-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="f5a28-108">中央管理存储不能驻留在池中的企业版服务器上。</span><span class="sxs-lookup"><span data-stu-id="f5a28-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="f5a28-109">第一次发布拓扑并选择创建数据库时，将自动创建中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="f5a28-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="f5a28-110">指定为后端服务器的计算机必须已运行 SQL Server 数据库软件，才能成功安装。</span><span class="sxs-lookup"><span data-stu-id="f5a28-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5a28-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="f5a28-111">In This Section</span></span>

  - [<span data-ttu-id="f5a28-112">Lync Server 2013 的 SQL Server 数据和日志文件放置</span><span class="sxs-lookup"><span data-stu-id="f5a28-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="f5a28-113">在 Lync Server 2013 中配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5a28-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="f5a28-114">Lync Server 2013 中 SQL Server 的部署权限</span><span class="sxs-lookup"><span data-stu-id="f5a28-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="f5a28-115">在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库</span><span class="sxs-lookup"><span data-stu-id="f5a28-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="f5a28-116">了解 SQL Server 与 Lync Server 2013 一起使用时的防火墙要求</span><span class="sxs-lookup"><span data-stu-id="f5a28-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="f5a28-117">配置 Lync Server 2013 的 SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="f5a28-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

