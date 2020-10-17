---
title: Lync Server 2013：定义和配置拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f98c5961385bd2f99c0698af1b5f422abe4c60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504539"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="d70a0-102">在 Lync Server 2013 中定义和配置拓扑</span><span class="sxs-lookup"><span data-stu-id="d70a0-102">Defining and configuring the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d70a0-103">_**上次修改的主题：** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="d70a0-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="d70a0-104">您可以使用拓扑生成器定义和配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="d70a0-105">拓扑生成器不要求您是本地 Administrators 组的成员，也不要求是权限域组的成员 (例如 Domain Admins) 。</span><span class="sxs-lookup"><span data-stu-id="d70a0-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="d70a0-106">您能够以标准用户身份定义拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="d70a0-107">因第一次使用而启动拓扑生成器并随后编辑会话时，系统会提示您要使拓扑生成器加载当前配置文档的位置。</span><span class="sxs-lookup"><span data-stu-id="d70a0-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="d70a0-108">选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="d70a0-108">The choices are the following:</span></span>

  - <span data-ttu-id="d70a0-109">从现有部署下载拓扑</span><span class="sxs-lookup"><span data-stu-id="d70a0-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="d70a0-110">从本地文件打开拓扑</span><span class="sxs-lookup"><span data-stu-id="d70a0-110">Open topology from a local file</span></span>

  - <span data-ttu-id="d70a0-111">新建拓扑</span><span class="sxs-lookup"><span data-stu-id="d70a0-111">New topology</span></span>

<span data-ttu-id="d70a0-112">如果已经定义了一个拓扑并已建立了中央管理存储，则应选择从现有部署下载拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="d70a0-113">拓扑生成器将读取数据库并检索当前的定义。</span><span class="sxs-lookup"><span data-stu-id="d70a0-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="d70a0-114">如果您有一个现有的中央管理存储，则应始终选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d70a0-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="d70a0-115">如果尚未建立中央管理存储，并且想要编辑以前保存的配置，则应选择从本地文件中打开拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="d70a0-116">将要打开的文件就是以前会话中保存的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d70a0-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="d70a0-117">可以使用此选项编辑以前保存的拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d70a0-p104">如果您已有发布的拓扑，则不应加载本地配置文件，而应选择从现有部署下载拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="d70a0-120">如果要创建新的拓扑生成器配置，请选择创建新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="d70a0-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="d70a0-121">以前保存的设计不会被覆盖，除非选择将其另存为以前设计会话中创建的同一文件。</span><span class="sxs-lookup"><span data-stu-id="d70a0-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="d70a0-122">在上述每个选项中，系统都会提示您提供存储拓扑生成器配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d70a0-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="d70a0-123">文件的位置可以是本地位置、已建立文件共享上的共享位置或可移动介质。</span><span class="sxs-lookup"><span data-stu-id="d70a0-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d70a0-124">本部分内容</span><span class="sxs-lookup"><span data-stu-id="d70a0-124">In This Section</span></span>

  - [<span data-ttu-id="d70a0-125">在 Lync Server 2013 拓扑生成器中定义和配置拓扑</span><span class="sxs-lookup"><span data-stu-id="d70a0-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="d70a0-126">在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="d70a0-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="d70a0-127">在 Lync Server 2013 中为灾难恢复部署配对的前端池</span><span class="sxs-lookup"><span data-stu-id="d70a0-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="d70a0-128">在 Lync Server 2013 中部署 SQL 镜像以实现后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="d70a0-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="d70a0-129">在 Lync Server 2013 中编辑或配置简单 Url</span><span class="sxs-lookup"><span data-stu-id="d70a0-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="d70a0-130">在 Lync Server 2013 中选择中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="d70a0-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

