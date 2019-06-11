---
title: 'Lync Server 2013: 持久聊天服务器的技术要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="2be9d-102">Lync Server 2013 中持久聊天服务器的技术要求</span><span class="sxs-lookup"><span data-stu-id="2be9d-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2be9d-103">_**主题上次修改时间:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="2be9d-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="2be9d-104">托管持久聊天服务器的每台计算机都必须具有以下组件的现有 Lync Server 2013 拓扑的访问权限:</span><span class="sxs-lookup"><span data-stu-id="2be9d-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="2be9d-105">**Lync Server 2013、前端服务器。** 前端服务器是会话初始协议 (SIP) 路由的基础, 用于在运行持久聊天服务器的计算机与可能的持久聊天功能之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="2be9d-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="2be9d-106">开始部署持久聊天服务器之前, 请根据您的组织的需要, 验证 Lync Server 2013、标准版或 Lync 服务器前端池和任何其他运行 Lync Server 的内部计算机的部署。</span><span class="sxs-lookup"><span data-stu-id="2be9d-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="2be9d-107">以下部分介绍持久聊天服务器和存储持久聊天数据的数据库的特定要求。</span><span class="sxs-lookup"><span data-stu-id="2be9d-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="2be9d-108">持久聊天服务器要求</span><span class="sxs-lookup"><span data-stu-id="2be9d-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="2be9d-109">有关部署 Lync Server 和最新版本持久聊天服务器的推荐硬件的详细信息, 请参阅支持文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="2be9d-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2be9d-110">有关适用于 Lync Server 和持久聊天服务器的服务器和工具操作系统支持的详细信息, 请参阅支持文档中[Lync server 2013 中的 "服务器和工具" 操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="2be9d-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2be9d-111">有关部署持久聊天服务器所需的其他软件的详细信息, 请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2be9d-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="2be9d-112">持久聊天服务器软件先决条件</span><span class="sxs-lookup"><span data-stu-id="2be9d-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2be9d-113">软件</span><span class="sxs-lookup"><span data-stu-id="2be9d-113">Software</span></span></th>
<th><span data-ttu-id="2be9d-114">说明</span><span class="sxs-lookup"><span data-stu-id="2be9d-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2be9d-115">消息队列</span><span class="sxs-lookup"><span data-stu-id="2be9d-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="2be9d-116">如果已部署, 则为持久聊天服务器和持久聊天合规性服务使用。</span><span class="sxs-lookup"><span data-stu-id="2be9d-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="2be9d-117">持久聊天服务器数据库要求</span><span class="sxs-lookup"><span data-stu-id="2be9d-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="2be9d-118">持久聊天服务器使用持久聊天数据库来存储聊天历史记录、配置和用户预配数据。</span><span class="sxs-lookup"><span data-stu-id="2be9d-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="2be9d-119">或者, 它使用持久聊天合规数据库来存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="2be9d-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2be9d-120">持久聊天数据库 (mgc) 和合规性数据库 (mgccomp) 可以位于 SQL Server 的同一实例中, 也可以位于不同的 SQL Server 上。</span><span class="sxs-lookup"><span data-stu-id="2be9d-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="2be9d-121">为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。</span><span class="sxs-lookup"><span data-stu-id="2be9d-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="2be9d-122">持久聊天数据库服务器的服务器平台需要与 Lync Server 后端数据库服务器相同的硬件。</span><span class="sxs-lookup"><span data-stu-id="2be9d-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="2be9d-123">有关详细信息, 请参阅支持文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="2be9d-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2be9d-124">在数据库服务器上，确保安装了以下软件应用程序之一：</span><span class="sxs-lookup"><span data-stu-id="2be9d-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="2be9d-125">Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="2be9d-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="2be9d-126">有关如何安装 Microsoft SQL Server 2012 的详细信息, 请参阅 "安装 SQL Server 2012" [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)。</span><span class="sxs-lookup"><span data-stu-id="2be9d-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="2be9d-127">Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="2be9d-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="2be9d-128">有关如何安装 Microsoft SQL Server 2008 R2 的详细信息, 请参阅的[http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)"SQL server 安装 (sql Server 2008 R2)"。</span><span class="sxs-lookup"><span data-stu-id="2be9d-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="2be9d-129">持久聊天服务器证书要求</span><span class="sxs-lookup"><span data-stu-id="2be9d-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="2be9d-130">有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息, 请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。</span><span class="sxs-lookup"><span data-stu-id="2be9d-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

