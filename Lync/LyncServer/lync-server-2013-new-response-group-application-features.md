---
title: Lync Server 2013：新的响应组应用程序功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="f605d-102">Lync Server 2013 中新的响应组应用程序功能</span><span class="sxs-lookup"><span data-stu-id="f605d-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f605d-103">_**主题上次修改时间:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f605d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="f605d-104">使用 "响应组" 应用程序, 您可以将传入呼叫路由和排队给指定人员进行特殊用途, 例如客户服务、内部技术支持或部门的常规电话支持。</span><span class="sxs-lookup"><span data-stu-id="f605d-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="f605d-105">以下响应组应用程序功能是 Lync Server 2013 中的新增功能:</span><span class="sxs-lookup"><span data-stu-id="f605d-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="f605d-106">**经理角色**</span><span class="sxs-lookup"><span data-stu-id="f605d-106">**Manager role**</span></span>
    
    <span data-ttu-id="f605d-107">Lync Server 2013 引入了新的 "响应组管理器" 角色。</span><span class="sxs-lookup"><span data-stu-id="f605d-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="f605d-108">现在, 响应组有两个管理角色: "响应组管理器" 和 "响应组管理员"。</span><span class="sxs-lookup"><span data-stu-id="f605d-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="f605d-109">虽然响应组管理员仍然可以为任何响应组配置任何元素, 但管理器只能配置特定元素, 而不是其拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="f605d-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="f605d-110">管理模型的这种改进提高了响应组的可伸缩性, 尤其是对于大型部署方案。</span><span class="sxs-lookup"><span data-stu-id="f605d-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="f605d-111">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="f605d-111">**High availability**</span></span>
    
    <span data-ttu-id="f605d-112">在 Lync Server 2013 的高可用性的整体配置和部署中, 对响应组应用程序的高可用性支持 (以 SQL Server 镜像的形式) 被启用。</span><span class="sxs-lookup"><span data-stu-id="f605d-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="f605d-113">如果为高可用性进行配置, 并且失去了与主后端服务器的连接, 则使用镜像后端服务器不会影响响应组功能。</span><span class="sxs-lookup"><span data-stu-id="f605d-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="f605d-114">无法在整个 Lync Server 2013 高可用性配置之外单独启用或配置对响应组应用程序的 SQL Server 镜像的支持。</span><span class="sxs-lookup"><span data-stu-id="f605d-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="f605d-115">**灾难恢复**</span><span class="sxs-lookup"><span data-stu-id="f605d-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="f605d-116">对响应组应用程序的灾难恢复支持启用为已配对的前端池的配置和部署的一部分, 这是整个 Lync Server 2013 灾难恢复配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="f605d-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="f605d-117">此外, "响应组导入" 和 "导出" cmdlet 支持将备份池和故障回复进程的故障转移过程转移到主池或新池。</span><span class="sxs-lookup"><span data-stu-id="f605d-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="f605d-118">如果主池中出现中断, 则响应组可以故障转移到备份池, 然后在中断结束时返回到主池或新池。</span><span class="sxs-lookup"><span data-stu-id="f605d-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f605d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f605d-119">See Also</span></span>


[<span data-ttu-id="f605d-120">在 Lync Server 2013 中规划响应组</span><span class="sxs-lookup"><span data-stu-id="f605d-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

