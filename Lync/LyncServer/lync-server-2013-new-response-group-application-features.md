---
title: Lync Server 2013：新的响应组应用程序功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37263eeb099ea468713526c20a2c6b14bed0694d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="aec2d-102">Lync Server 2013 中新的响应组应用程序功能</span><span class="sxs-lookup"><span data-stu-id="aec2d-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aec2d-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="aec2d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="aec2d-104">通过响应组应用程序，可以按特定用途将传入呼叫路由和排列到指定人员，例如客户服务、内部技术支持或部门的常规电话支持。</span><span class="sxs-lookup"><span data-stu-id="aec2d-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="aec2d-105">以下响应组应用程序功能是 Lync Server 2013 中的新增功能：</span><span class="sxs-lookup"><span data-stu-id="aec2d-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="aec2d-106">**Manager 角色**</span><span class="sxs-lookup"><span data-stu-id="aec2d-106">**Manager role**</span></span>
    
    <span data-ttu-id="aec2d-107">Lync Server 2013 引入了新的响应组管理器角色。</span><span class="sxs-lookup"><span data-stu-id="aec2d-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="aec2d-108">目前有两个响应组管理角色：响应组管理器和响应组管理员。</span><span class="sxs-lookup"><span data-stu-id="aec2d-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="aec2d-109">虽然响应组管理员仍可以为任何响应组配置任何元素，但管理者只能为其拥有的响应组配置特定元素。</span><span class="sxs-lookup"><span data-stu-id="aec2d-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="aec2d-110">针对管理模型的此改进可提高响应组的可伸缩性，尤其是在大型部署方案中。</span><span class="sxs-lookup"><span data-stu-id="aec2d-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="aec2d-111">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="aec2d-111">**High availability**</span></span>
    
    <span data-ttu-id="aec2d-112">以 SQL Server 镜像的形式，对响应组应用程序的高可用性支持作为对 Lync Server 2013 的高可用性的总体配置和部署的一部分进行启用。</span><span class="sxs-lookup"><span data-stu-id="aec2d-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="aec2d-113">如果您配置高可用性但丢失与主后端服务器的连接，则利用镜像后端服务器不会影响响应组功能。</span><span class="sxs-lookup"><span data-stu-id="aec2d-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="aec2d-114">对响应组应用程序的 SQL Server 镜像的支持无法在整个 Lync Server 2013 高可用性配置之外单独启用或配置。</span><span class="sxs-lookup"><span data-stu-id="aec2d-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="aec2d-115">**灾难恢复**</span><span class="sxs-lookup"><span data-stu-id="aec2d-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="aec2d-116">响应组应用程序的灾难恢复支持作为成对前端池的配置和部署的一部分启用，这是整个 Lync Server 2013 灾难恢复配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="aec2d-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="aec2d-117">此外，响应组导入和导出 cmdlet 支持故障转移到备份池的过程以及故障回复到主池或新池的过程。</span><span class="sxs-lookup"><span data-stu-id="aec2d-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="aec2d-118">如果主池中出现中断情况，可将响应组故障转移到备份池，然后在中断停止后将响应组故障回复到主池或新池。</span><span class="sxs-lookup"><span data-stu-id="aec2d-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aec2d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aec2d-119">See Also</span></span>


[<span data-ttu-id="aec2d-120">在 Lync Server 2013 中规划响应组</span><span class="sxs-lookup"><span data-stu-id="aec2d-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

