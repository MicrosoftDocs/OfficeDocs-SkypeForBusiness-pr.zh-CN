---
title: Lync Server 2013：存档的技术要求
description: Lync Server 2013：存档的技术要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6100753ad2c62424eb68c8c258094ba51848170e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577168"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="39f0d-103">Lync Server 2013 中存档的技术要求</span><span class="sxs-lookup"><span data-stu-id="39f0d-103">Technical requirements for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f0d-104">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="39f0d-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="39f0d-105">Lync Server 2013 技术要求包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="39f0d-105">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="39f0d-106">基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="39f0d-106">Infrastructure requirements.</span></span>

  - <span data-ttu-id="39f0d-107">存档所必须安装的必备软件。</span><span class="sxs-lookup"><span data-stu-id="39f0d-107">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="39f0d-108">存档的数据存储要求。</span><span class="sxs-lookup"><span data-stu-id="39f0d-108">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="39f0d-109">存档部署的缩放要求和注意事项。</span><span class="sxs-lookup"><span data-stu-id="39f0d-109">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="39f0d-110">存档数据库的性能要求和注意事项。</span><span class="sxs-lookup"><span data-stu-id="39f0d-110">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39f0d-111">此 Lync Server 2013 版本中不提供缩放和性能信息。</span><span class="sxs-lookup"><span data-stu-id="39f0d-111">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="39f0d-112">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="39f0d-112">Infrastructure Requirements</span></span>

<span data-ttu-id="39f0d-113">Lync Server 2013 存档基础结构要求与部署 Lync Server 2013 的要求相同。</span><span class="sxs-lookup"><span data-stu-id="39f0d-113">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="39f0d-114">有关详细信息，请参阅规划文档中的 [确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="39f0d-114">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="39f0d-115">存档必备组件</span><span class="sxs-lookup"><span data-stu-id="39f0d-115">Archiving Prerequisites</span></span>

<span data-ttu-id="39f0d-116">Lync Server 2013 出于以下原因，简化了存档的先决条件：</span><span class="sxs-lookup"><span data-stu-id="39f0d-116">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="39f0d-p102">存档服务器不再是服务器角色。相反，统一数据收集代理在池中的前端服务器和 Standard Edition 服务器上运行以捕获存档数据，因此您无需针对存档设置单独的系统平台。</span><span class="sxs-lookup"><span data-stu-id="39f0d-p102">Archiving Server is no longer a server role. Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="39f0d-119">存档将 Lync Server 2013 文件存储用于会议内容文件的临时存储，因此您不需要为存档设置单独的文件存储。</span><span class="sxs-lookup"><span data-stu-id="39f0d-119">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="39f0d-120">在 Lync Server 2013 中，不需要消息队列。</span><span class="sxs-lookup"><span data-stu-id="39f0d-120">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="39f0d-121">存档的数据存储要求</span><span class="sxs-lookup"><span data-stu-id="39f0d-121">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="39f0d-p103">此外，您需要为存档存储设置基础结构。这包括以下一个或两个存储：</span><span class="sxs-lookup"><span data-stu-id="39f0d-p103">Additionally, you need to set up the infrastructure for Archiving storage. This includes one or both of the following:</span></span>

  - <span data-ttu-id="39f0d-124">**Microsoft Exchange 存储**。</span><span class="sxs-lookup"><span data-stu-id="39f0d-124">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="39f0d-125">会议内容文件（如 PowerPoint 演示文稿）将作为附件存档。</span><span class="sxs-lookup"><span data-stu-id="39f0d-125">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="39f0d-126">如果要使用 Microsoft Exchange 集成，以便将 Lync 存档数据与 Exchange 合规性数据存储在一起，则必须将 Exchange 2013 用于 Exchange 部署，并确保最大存储大小支持存储会议内容文件。</span><span class="sxs-lookup"><span data-stu-id="39f0d-126">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="39f0d-127">如果使用 Microsoft Exchange 集成选项部署存档，Lync 存档数据将仅存储在 Exchange 2013 服务器上的用户的 Exchange 2013 合规性数据中。</span><span class="sxs-lookup"><span data-stu-id="39f0d-127">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="39f0d-128">在使用 Microsoft Exchange 集成选项部署和启用存档之前，必须部署 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="39f0d-128">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="39f0d-129">如果选择使用 Exchange 2013 存储，则无需为存档部署单独的 SQL Server 数据库，除非您的 Lync 用户没有驻留在 Exchange 2013 服务器上。</span><span class="sxs-lookup"><span data-stu-id="39f0d-129">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="39f0d-130">**用于存档的 SQL Server 数据库存储**。</span><span class="sxs-lookup"><span data-stu-id="39f0d-130">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="39f0d-131">若要支持不驻留在 Exchange 2013 服务器上的用户，或者不希望使用 Microsoft Exchange 集成选项，则必须使用 SQL Server 数据库部署存档存储。</span><span class="sxs-lookup"><span data-stu-id="39f0d-131">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="39f0d-132">Lync Server 2013 支持以下64位版本的 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="39f0d-132">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="39f0d-133">Microsoft SQL Server 2008 R2 企业版</span><span class="sxs-lookup"><span data-stu-id="39f0d-133">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="39f0d-134">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="39f0d-134">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="39f0d-135">Microsoft SQL Server 2012 企业版</span><span class="sxs-lookup"><span data-stu-id="39f0d-135">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="39f0d-136">Microsoft SQL Server 2012 标准版</span><span class="sxs-lookup"><span data-stu-id="39f0d-136">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39f0d-137">Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支持存档。</span><span class="sxs-lookup"><span data-stu-id="39f0d-137">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="39f0d-138">32位版本的 SQL Server 不受支持。</span><span class="sxs-lookup"><span data-stu-id="39f0d-138">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="39f0d-139">有关其他 SQL Server 要求和限制，请参阅规划文档中或可支持性文档中的 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 中的数据库软件支持</A> 。</span><span class="sxs-lookup"><span data-stu-id="39f0d-139">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="39f0d-140">在部署和启用存档之前，必须设置 SQL Server 平台。</span><span class="sxs-lookup"><span data-stu-id="39f0d-140">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="39f0d-141">如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。</span><span class="sxs-lookup"><span data-stu-id="39f0d-141">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="39f0d-142">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="39f0d-142">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="39f0d-143">有关 SQL Server 的详细信息，请参阅 SQL Server 技术中心 [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。</span><span class="sxs-lookup"><span data-stu-id="39f0d-143">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

