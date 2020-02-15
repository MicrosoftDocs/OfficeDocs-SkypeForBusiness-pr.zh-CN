---
title: Lync Server 2013：设置用于存档的系统平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e1a8aea999fdf134b0152a9d37b2d36fc81ee8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="8d9bf-102">在 Lync Server 2013 中设置用于存档的系统平台</span><span class="sxs-lookup"><span data-stu-id="8d9bf-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d9bf-103">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8d9bf-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8d9bf-104">在开始部署存档之前，您必须在满足系统要求的硬件上安装必要的操作系统以及任何其他必备软件：</span><span class="sxs-lookup"><span data-stu-id="8d9bf-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="8d9bf-105">**Lync server 2013 platform**   Lync Server 2013 部署没有存档服务器。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="8d9bf-106">但是，统一数据收集代理会在前端服务器和 Standard Edition 服务器上运行以捕获要存档的数据，所以不需要单独的系统平台来承载存档功能。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="8d9bf-107">**数据存储平台**   在 Lync Server 2013 中，可以使用以下两种方法之一存储数据：</span><span class="sxs-lookup"><span data-stu-id="8d9bf-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="8d9bf-108">**Microsoft Exchange 集成**   如果要使用 Exchange 2013 部署来存储 Lync Server 2013 存档数据，而不是或除了设置单独的数据库以存储存档数据，则 exchange 部署必须运行 exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="8d9bf-109">有关为 Exchange 2013 设置系统平台的详细信息，请参阅 Exchange 产品文档。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="8d9bf-110">**SQL server**   如果要将单独的 SQL server 数据库用于存储存档数据（而不是使用 Microsoft Exchange 集成），则必须在部署存档之前为数据库设置系统平台。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="8d9bf-111">特定的系统平台要求取决于是否对存档数据库使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="8d9bf-112">有关为这些数据库设置系统平台的详细信息，请参阅 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 产品文档。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="8d9bf-113">**文件服务器平台**   Lync server 2013 将 lync server 存档文件存储在您在设置前端服务器或 Standard Edition 服务器时为文件存储指定的同一位置。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="8d9bf-114">您无法为存档文件存储指定其他位置，所以不需要单独的系统平台存档文件存储。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="8d9bf-115">如果使用 Microsoft Exchange 集成，则 Exchange 2013 文件的存档 Lync 通信将存储在 Exchange 2013 服务器上，以供驻留在这些 Exchange 服务器上的用户使用。</span><span class="sxs-lookup"><span data-stu-id="8d9bf-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

