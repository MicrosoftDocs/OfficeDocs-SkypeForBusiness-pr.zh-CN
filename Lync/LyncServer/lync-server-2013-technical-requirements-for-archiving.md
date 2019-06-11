---
title: 'Lync Server 2013: 存档的技术要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="fcef2-102">Lync Server 2013 中存档的技术要求</span><span class="sxs-lookup"><span data-stu-id="fcef2-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcef2-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="fcef2-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="fcef2-104">Lync Server 2013 技术要求包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="fcef2-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="fcef2-105">基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="fcef2-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="fcef2-106">必须为存档安装的必备软件。</span><span class="sxs-lookup"><span data-stu-id="fcef2-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="fcef2-107">存档的数据存储要求。</span><span class="sxs-lookup"><span data-stu-id="fcef2-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="fcef2-108">针对存档部署的扩展要求和注意事项。</span><span class="sxs-lookup"><span data-stu-id="fcef2-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="fcef2-109">存档数据库的性能要求和注意事项。</span><span class="sxs-lookup"><span data-stu-id="fcef2-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fcef2-110">缩放和性能信息在此 Lync Server 2013 版本中不可用。</span><span class="sxs-lookup"><span data-stu-id="fcef2-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="fcef2-111">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="fcef2-111">Infrastructure Requirements</span></span>

<span data-ttu-id="fcef2-112">Lync Server 2013 存档基础结构要求与 Lync Server 2013 的部署相同。</span><span class="sxs-lookup"><span data-stu-id="fcef2-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="fcef2-113">有关详细信息, 请参阅在规划文档中[确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcef2-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="fcef2-114">存档先决条件</span><span class="sxs-lookup"><span data-stu-id="fcef2-114">Archiving Prerequisites</span></span>

<span data-ttu-id="fcef2-115">Lync Server 2013 简化了存档的先决条件, 原因如下:</span><span class="sxs-lookup"><span data-stu-id="fcef2-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="fcef2-116">存档服务器不再是服务器角色。</span><span class="sxs-lookup"><span data-stu-id="fcef2-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="fcef2-117">统一的数据收集代理在池和标准版服务器中的前端服务器上运行, 用于捕获用于存档的数据, 因此不会为存档设置单独的系统平台。</span><span class="sxs-lookup"><span data-stu-id="fcef2-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="fcef2-118">存档使用 Lync Server 2013 文件存储来临时存储会议内容文件, 因此不会为存档设置单独的文件存储。</span><span class="sxs-lookup"><span data-stu-id="fcef2-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="fcef2-119">在 Lync Server 2013 中, 不需要消息队列。</span><span class="sxs-lookup"><span data-stu-id="fcef2-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="fcef2-120">存档的数据存储要求</span><span class="sxs-lookup"><span data-stu-id="fcef2-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="fcef2-121">此外, 你还需要设置用于存档存储的基础结构。</span><span class="sxs-lookup"><span data-stu-id="fcef2-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="fcef2-122">这包括以下一项或两项:</span><span class="sxs-lookup"><span data-stu-id="fcef2-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="fcef2-123">**Microsoft Exchange 存储**。</span><span class="sxs-lookup"><span data-stu-id="fcef2-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="fcef2-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span><span class="sxs-lookup"><span data-stu-id="fcef2-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="fcef2-125">如果要使用 Microsoft Exchange 集成, 以便 Lync 存档数据存储在 Exchange 合规性数据中, 则必须将 Exchange 2013 用于 Exchange 部署, 并确保最大存储空间支持存储会议内容文件。</span><span class="sxs-lookup"><span data-stu-id="fcef2-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="fcef2-126">如果你使用 Microsoft Exchange 集成选项部署存档, 则 Lync 存档数据仅存储 Exchange 2013 服务器上托管的用户的 Exchange 2013 合规性数据。</span><span class="sxs-lookup"><span data-stu-id="fcef2-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="fcef2-127">在使用 Microsoft Exchange 集成选项部署和启用存档之前, 必须部署 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="fcef2-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="fcef2-128">如果你选择使用 Exchange 2013 存储, 则无需为存档部署单独的 SQL Server 数据库, 除非你的 Exchange 2013 服务器上未托管 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="fcef2-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="fcef2-129">**用于存档的 SQL Server 数据库存储**。</span><span class="sxs-lookup"><span data-stu-id="fcef2-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="fcef2-130">若要支持未托管在 Exchange 2013 服务器上的用户, 或者不希望使用 Microsoft Exchange 集成选项, 则必须使用 SQL Server 数据库部署存档存储。</span><span class="sxs-lookup"><span data-stu-id="fcef2-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="fcef2-131">Lync Server 2013 支持以下64位版本的 SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fcef2-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="fcef2-132">Microsoft SQL Server 2008 R2 企业版</span><span class="sxs-lookup"><span data-stu-id="fcef2-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="fcef2-133">Microsoft SQL Server 2008 R2 标准版</span><span class="sxs-lookup"><span data-stu-id="fcef2-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="fcef2-134">Microsoft SQL Server 2012 企业版</span><span class="sxs-lookup"><span data-stu-id="fcef2-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="fcef2-135">Microsoft SQL Server 2012 标准版</span><span class="sxs-lookup"><span data-stu-id="fcef2-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcef2-136">Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支持存档。</span><span class="sxs-lookup"><span data-stu-id="fcef2-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="fcef2-137">不支持32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="fcef2-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="fcef2-138">有关其他 SQL Server 要求和限制, 请参阅在规划文档或支持文档中<A href="lync-server-2013-database-software-support.md">Lync Server 2013 中的数据库软件支持</A>。</span><span class="sxs-lookup"><span data-stu-id="fcef2-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="fcef2-139">在部署和启用存档之前, 必须设置 SQL Server 平台。</span><span class="sxs-lookup"><span data-stu-id="fcef2-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="fcef2-140">如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。</span><span class="sxs-lookup"><span data-stu-id="fcef2-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="fcef2-141">你还可以稍后创建数据库, 包括安装过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="fcef2-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="fcef2-142">有关 SQL Server 的详细信息, 请参阅 SQL Server 技术[http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)中心。</span><span class="sxs-lookup"><span data-stu-id="fcef2-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

