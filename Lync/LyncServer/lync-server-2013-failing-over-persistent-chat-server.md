---
title: Lync Server 2013：对持久聊天服务器进行故障转移
description: Lync Server 2013：对持久聊天服务器进行故障转移。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a3a8f5df203cc23be39a4a691ad713330eab59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554958"
---
# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ef5cc-103">在 Lync Server 2013 中对持久聊天服务器进行故障转移</span><span class="sxs-lookup"><span data-stu-id="ef5cc-103">Failing over Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef5cc-104">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ef5cc-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ef5cc-105">持久聊天服务器的故障转移主要是一个手动过程。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-105">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="ef5cc-106">故障转移过程基于以下假设：辅助数据中心已启动并在运行，但主持久聊天数据库所在的持久聊天服务器服务完全不可用，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="ef5cc-106">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="ef5cc-107">持久聊天服务器主数据库和持久聊天服务器镜像数据库已关闭。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-107">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="ef5cc-108">Lync Server 前端服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-108">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="ef5cc-109">该过程主要包含两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="ef5cc-109">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="ef5cc-110">恢复主持久聊天数据库 (mgc) 。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-110">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="ef5cc-111">建立新的主数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-111">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="ef5cc-112">持久聊天合规性数据库 (mgccomp) 未进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-112">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="ef5cc-113">此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-113">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="ef5cc-114">作为持久聊天管理员，你的责任是正确管理适配器输出以避免数据丢失。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-114">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="ef5cc-115">对持久聊天服务器进行故障转移</span><span class="sxs-lookup"><span data-stu-id="ef5cc-115">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="ef5cc-116">从持久聊天服务器备份日志传送数据库中删除日志传送。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-116">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="ef5cc-117">使用 SQL Server Management Studio 连接到持久聊天服务器备份 mgc 数据库所在的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-117">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="ef5cc-118">打开主数据库的查询窗口。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-118">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="ef5cc-119">使用以下命令取消日志传送：</span><span class="sxs-lookup"><span data-stu-id="ef5cc-119">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="ef5cc-120">从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-120">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="ef5cc-121">按顺序将任何未应用的事务日志备份应用到辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-121">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="ef5cc-122">有关详细信息，请参阅中的 "how to： Apply a Transaction Log Backup (Transact-sql) " https://go.microsoft.com/fwlink/p/?linkid=247428 。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-122">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="ef5cc-p103">使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ef5cc-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="ef5cc-125">如果包含以下项，将断开与 mgc 数据库的所有连接：</span><span class="sxs-lookup"><span data-stu-id="ef5cc-125">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="ef5cc-126">**exec sp \_ who2** ，用于识别与 mgc 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-126">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="ef5cc-127">\*\*kill \<spid\> \*\*以结束这些连接。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-127">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="ef5cc-128">使数据库联机：</span><span class="sxs-lookup"><span data-stu-id="ef5cc-128">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="ef5cc-129">**使用恢复还原数据库 mgc**。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-129">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="ef5cc-130">在 Lync Server 命令行管理程序中，使用命令 **集 CsPersistentChatState-Identity "service： atl-cs-001.litwareinc.com" – PoolState FailedOver** 故障转移到 mgc 备份数据库。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-130">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="ef5cc-131">请务必将持久聊天池的完全限定域名替换为 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-131">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="ef5cc-132">mgc 备份数据库现在充当主数据库。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-132">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="ef5cc-133">在 Lync Server 命令行管理程序中，使用 **CsMirrorDatabase** cmdlet 为现在用作主数据库的备份数据库建立高可用性镜像。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-133">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="ef5cc-134">使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-134">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="ef5cc-135">此镜像与最初在安装期间为主数据库配置的镜像不同。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-135">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="ef5cc-136">有关详细信息，请参阅在 [Lync server 2013 中部署 SQL 镜像以实现后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)一节中的 "使用 Lync Server 命令行管理程序 cmdlet" 一节。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-136">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="ef5cc-137">设置持久聊天服务器活动服务器。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-137">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="ef5cc-138">在 Lync Server 命令行管理程序中，使用 **set-cspersistentchatactiveserver** cmdlet 设置活动服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-138">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ef5cc-139">所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-139">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="ef5cc-140">在这种情况下，从持久聊天服务器主数据库到持久聊天服务器备份数据库的故障转移已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-140">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

