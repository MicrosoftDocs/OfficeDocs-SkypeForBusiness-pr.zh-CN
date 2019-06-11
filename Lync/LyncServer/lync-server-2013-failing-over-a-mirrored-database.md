---
title: Lync Server 2013：对镜像数据库进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a943705f13cff4f015285b1ef74feb11dc540091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="02d14-102">在 Lync Server 2013 中对镜像数据库进行故障转移</span><span class="sxs-lookup"><span data-stu-id="02d14-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02d14-103">_**主题上次修改时间:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="02d14-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="02d14-104">如果你已将后端数据库配置为使用与见证的同步镜像, 则自动故障转移。</span><span class="sxs-lookup"><span data-stu-id="02d14-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="02d14-105">如果您已配置了没有见证的同步镜像, 则可以使用以下过程来故障转移和恢复您的数据库。</span><span class="sxs-lookup"><span data-stu-id="02d14-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="02d14-106">你还可以使用这些过程手动故障转移和回切, 即使你已配置见证。</span><span class="sxs-lookup"><span data-stu-id="02d14-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="02d14-107">故障转移后端数据库</span><span class="sxs-lookup"><span data-stu-id="02d14-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="02d14-108">在故障转移之前, 通过键入以下 cmdlet 确定哪些后端数据库是主体, 哪个是镜像:</span><span class="sxs-lookup"><span data-stu-id="02d14-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="02d14-109">如果中央管理存储托管在此池中, 请键入以下 cmdlet 以确定哪个是主体, 后者是中央管理存储的镜像:</span><span class="sxs-lookup"><span data-stu-id="02d14-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="02d14-110">执行用户数据库的故障转移:</span><span class="sxs-lookup"><span data-stu-id="02d14-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="02d14-111">如果主映像出现故障, 并且您已故障转移到镜像, 请键入:</span><span class="sxs-lookup"><span data-stu-id="02d14-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="02d14-112">如果镜像失败, 并且您将故障转移到主映像, 请键入:</span><span class="sxs-lookup"><span data-stu-id="02d14-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="02d14-113">如果该池托管中央管理服务器, 请执行中央管理存储的故障转移。</span><span class="sxs-lookup"><span data-stu-id="02d14-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="02d14-114">如果主映像出现故障, 并且您已故障转移到镜像, 请键入:</span><span class="sxs-lookup"><span data-stu-id="02d14-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="02d14-115">如果镜像失败, 并且您将故障转移到主映像, 请键入:</span><span class="sxs-lookup"><span data-stu-id="02d14-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

