---
title: 第 8 阶段：停用旧池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df23d085a63cf67736b038b120fc294aa376f962
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="74295-102">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="74295-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74295-103">_**主题上次修改时间:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="74295-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="74295-104">以下主题提供了更新 DNS 条目、移动内容管理服务器、取消池以及从 Lync Server 2010 的旧式部署中停用和删除服务器和池的指南。</span><span class="sxs-lookup"><span data-stu-id="74295-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="74295-105">不需要本部分中列出的所有过程。</span><span class="sxs-lookup"><span data-stu-id="74295-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="74295-106">阅读文档并确定要使用的解除授权过程。</span><span class="sxs-lookup"><span data-stu-id="74295-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="74295-107">有关删除 Lync Server 2010 服务器和服务器角色以及解除 Lync Server 2010 部署的分步指南, 请参阅 "卸载 Microsoft Lync Server 2010 和删除服务器角色", 可在[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)此处下载.</span><span class="sxs-lookup"><span data-stu-id="74295-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74295-108">有关迁移和升级 Microsoft 统一通信托管 API (UCMA) 应用程序的信息, 在取消旧环境之前, 请参阅<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="74295-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74295-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="74295-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="74295-110">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="74295-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="74295-111">将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74295-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="74295-112">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="74295-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="74295-113">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="74295-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="74295-114">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="74295-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="74295-115">删除企业版前端服务器或标准版前端服务器</span><span class="sxs-lookup"><span data-stu-id="74295-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="74295-116">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="74295-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

