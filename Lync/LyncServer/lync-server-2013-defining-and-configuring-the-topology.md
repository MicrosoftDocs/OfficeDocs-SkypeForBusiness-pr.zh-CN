---
title: Lync Server 2013：定义和配置拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="af5c7-102">在 Lync Server 2013 中定义和配置拓扑</span><span class="sxs-lookup"><span data-stu-id="af5c7-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af5c7-103">_**主题上次修改时间:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="af5c7-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="af5c7-104">使用拓扑生成器定义和配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="af5c7-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="af5c7-105">拓扑生成器不要求你是本地管理员组或权限域组 (如域管理员) 的成员。</span><span class="sxs-lookup"><span data-stu-id="af5c7-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="af5c7-106">你可以将拓扑定义为标准用户。</span><span class="sxs-lookup"><span data-stu-id="af5c7-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="af5c7-107">在首次使用时启动拓扑生成器和后续编辑会话时, 系统会提示你输入希望拓扑生成器加载当前配置文档的位置。</span><span class="sxs-lookup"><span data-stu-id="af5c7-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="af5c7-108">选项如下所示:</span><span class="sxs-lookup"><span data-stu-id="af5c7-108">The choices are the following:</span></span>

  - <span data-ttu-id="af5c7-109">从现有部署下载拓扑</span><span class="sxs-lookup"><span data-stu-id="af5c7-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="af5c7-110">打开本地文件中的拓扑</span><span class="sxs-lookup"><span data-stu-id="af5c7-110">Open topology from a local file</span></span>

  - <span data-ttu-id="af5c7-111">新拓扑</span><span class="sxs-lookup"><span data-stu-id="af5c7-111">New topology</span></span>

<span data-ttu-id="af5c7-112">如果已定义拓扑, 并且已建立中央管理存储, 则应选择从现有部署下载拓扑。</span><span class="sxs-lookup"><span data-stu-id="af5c7-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="af5c7-113">拓扑生成器将读取数据库并检索当前定义。</span><span class="sxs-lookup"><span data-stu-id="af5c7-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="af5c7-114">如果您有一个现有的中央管理存储, 则应始终选择此选项。</span><span class="sxs-lookup"><span data-stu-id="af5c7-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="af5c7-115">如果尚未建立中央管理存储, 并且想要编辑以前保存的配置, 则应选择从本地文件打开拓扑。</span><span class="sxs-lookup"><span data-stu-id="af5c7-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="af5c7-116">将打开的文件将是以前会话中保存的配置文件。</span><span class="sxs-lookup"><span data-stu-id="af5c7-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="af5c7-117">可以使用此选项编辑以前保存的拓扑。</span><span class="sxs-lookup"><span data-stu-id="af5c7-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="af5c7-118">如果已有已发布的拓扑, 则不应加载本地配置文件。</span><span class="sxs-lookup"><span data-stu-id="af5c7-118">If you already have a published topology, you should not load a local configuration file.</span></span> <span data-ttu-id="af5c7-119">你应该选择从现有部署下载拓扑。</span><span class="sxs-lookup"><span data-stu-id="af5c7-119">You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="af5c7-120">如果要创建新的拓扑生成器配置, 请选择 "创建新拓扑"。</span><span class="sxs-lookup"><span data-stu-id="af5c7-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="af5c7-121">除非选择将以前保存的设计保存为在早期的设计会话中创建的同一文件, 否则不会覆盖以前保存的设计。</span><span class="sxs-lookup"><span data-stu-id="af5c7-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="af5c7-122">在每个选项中, 系统将提示你提供存储拓扑生成器配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="af5c7-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="af5c7-123">文件的位置可以是本地位置、已建立的文件共享上的共享位置或可移动媒体。</span><span class="sxs-lookup"><span data-stu-id="af5c7-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="af5c7-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="af5c7-124">In This Section</span></span>

  - [<span data-ttu-id="af5c7-125">在 Lync Server 2013 拓扑生成器中定义和配置拓扑</span><span class="sxs-lookup"><span data-stu-id="af5c7-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="af5c7-126">在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="af5c7-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="af5c7-127">在 Lync Server 2013 中针对灾难恢复部署配对的前端池</span><span class="sxs-lookup"><span data-stu-id="af5c7-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="af5c7-128">在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="af5c7-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="af5c7-129">在 Lync Server 2013 中编辑或配置简单 URL</span><span class="sxs-lookup"><span data-stu-id="af5c7-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="af5c7-130">在 Lync Server 2013 中选择中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="af5c7-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

