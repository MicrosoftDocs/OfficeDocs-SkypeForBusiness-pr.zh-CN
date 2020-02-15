---
title: Lync Server 2013：设置用于存档的存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a3633ee21fc26fe21557731ece31cf5a0bbb171
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="998ce-102">在 Lync Server 2013 中设置存储以进行存档</span><span class="sxs-lookup"><span data-stu-id="998ce-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="998ce-103">_**上次修改的主题：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="998ce-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="998ce-104">Lync Server 2013 的存档存储包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="998ce-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="998ce-105">\*\*\*\*   存储 IM 内容需要数据存储数据存储。</span><span class="sxs-lookup"><span data-stu-id="998ce-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="998ce-106">\*\*\*\*   存储会议（会议）内容数据存储和文件存储需要文件存储文件存储。</span><span class="sxs-lookup"><span data-stu-id="998ce-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="998ce-107">设置数据存储</span><span class="sxs-lookup"><span data-stu-id="998ce-107">Setting Up Data Storage</span></span>

<span data-ttu-id="998ce-108">在 Lync Server 2013 中设置存档数据存储的要求取决于您希望存储存档数据的方式：</span><span class="sxs-lookup"><span data-stu-id="998ce-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="998ce-109">将 Lync Server 2013 存档与 Exchange 部署集成，以存储使用 Exchange 存储的存档数据。</span><span class="sxs-lookup"><span data-stu-id="998ce-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="998ce-110">设置单独的 SQL Server 数据库服务器以存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="998ce-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="998ce-111">为存档数据设置 Exchange 存储</span><span class="sxs-lookup"><span data-stu-id="998ce-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="998ce-112">若要设置 Exchange 以存储存档数据，则需要 Exchange 部署运行 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="998ce-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="998ce-113">此外，用户邮箱必须驻留在 Exchange 2013 服务器上，并且必须将其邮箱置于就地保留状态。</span><span class="sxs-lookup"><span data-stu-id="998ce-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="998ce-114">有关配置 Exchange 2013 的详细信息，请参阅 Exchange 产品文档。</span><span class="sxs-lookup"><span data-stu-id="998ce-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="998ce-115">为存档数据设置 SQL Server 数据库服务器存储</span><span class="sxs-lookup"><span data-stu-id="998ce-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="998ce-116">Lync Server 2013 中的存档需要 SQL Server 数据库软件来存储存档的数据，除非您将部署与 Exchange 集成。</span><span class="sxs-lookup"><span data-stu-id="998ce-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="998ce-117">对于 SQL Server 存档数据库，您必须在将承载存档数据库的计算机上安装 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="998ce-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="998ce-118">您可使用用于前端池的后端数据库的同一 SQL 实例。</span><span class="sxs-lookup"><span data-stu-id="998ce-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="998ce-119">为实现最佳性能，应当在独立于中央管理存储的计算机上部署存档数据库。</span><span class="sxs-lookup"><span data-stu-id="998ce-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="998ce-120">有关并置 Lync Server 2013 组件的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="998ce-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="998ce-121">每个数据库服务器都必须运行受支持的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="998ce-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="998ce-122">有关受支持的版本的详细信息，请参阅规划文档中的在[Lync Server 2013 中存档的技术要求](lync-server-2013-technical-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="998ce-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="998ce-123">在部署和启用存档之前，必须设置 SQL Server 平台。</span><span class="sxs-lookup"><span data-stu-id="998ce-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="998ce-124">如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。</span><span class="sxs-lookup"><span data-stu-id="998ce-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="998ce-125">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="998ce-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="998ce-126">有关 SQL Server 的详细信息，请参阅 SQL Server 技术[http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)中心。</span><span class="sxs-lookup"><span data-stu-id="998ce-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="998ce-127">确保 SQL Server 代理服务启动类型为 "自动"，并且 SQL Server 代理服务运行的是存放存档数据库的 SQL 实例，以便默认的存档 SQL Server 维护作业可以按其预定时间运行，具体对 SQL Server 代理服务的控制。</span><span class="sxs-lookup"><span data-stu-id="998ce-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="998ce-128">设置文件存储</span><span class="sxs-lookup"><span data-stu-id="998ce-128">Setting Up File Storage</span></span>

<span data-ttu-id="998ce-129">存档使用您在设置前端池或 Standard Edition Server 时指定的 Lync Server 2013 文件共享。</span><span class="sxs-lookup"><span data-stu-id="998ce-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="998ce-130">无法更改用于存档的文件共享。</span><span class="sxs-lookup"><span data-stu-id="998ce-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="998ce-131">有关受支持的文件存储系统的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="998ce-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

