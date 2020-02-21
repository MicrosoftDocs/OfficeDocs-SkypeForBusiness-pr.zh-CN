---
title: Lync Server 2013 支持的池配对选项和最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33bc5e9622728fb4ee9c2a6a566e6010466d577
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="77a39-102">Lync Server 2013 的受支持的池配对选项和最佳做法</span><span class="sxs-lookup"><span data-stu-id="77a39-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77a39-103">_**上次修改的主题：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="77a39-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="77a39-p101">要包括互相配对的前端池的两个数据中心之间没有距离限制。建议使用位于相同世界区域的两个数据中心，因为它们之间存在高速链接。最好两个数据中心之间拥有足够距离，以避免一个灾难同时袭击两个数据中心。</span><span class="sxs-lookup"><span data-stu-id="77a39-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="77a39-107">跨世界区域分布两个数据中心也是可行的，但可能会因为数据复制延迟而导致丢失较多数据。</span><span class="sxs-lookup"><span data-stu-id="77a39-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="77a39-108">在规划要配对的池时，必须记住仅支持以下配对：</span><span class="sxs-lookup"><span data-stu-id="77a39-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="77a39-p102">Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。</span><span class="sxs-lookup"><span data-stu-id="77a39-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="77a39-p103">物理池仅能与其他物理池配对。同样，虚拟池仅能与其他虚拟池配对。</span><span class="sxs-lookup"><span data-stu-id="77a39-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="77a39-113">配对在一起的池必须运行相同的操作系统。</span><span class="sxs-lookup"><span data-stu-id="77a39-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="77a39-114">拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。</span><span class="sxs-lookup"><span data-stu-id="77a39-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="77a39-115">例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。</span><span class="sxs-lookup"><span data-stu-id="77a39-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="77a39-116">但是，不支持这些类型的配对。</span><span class="sxs-lookup"><span data-stu-id="77a39-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="77a39-117">配对中的每个池应能够在发生灾难时为两个池中的所有用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="77a39-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="77a39-118">如果对 Enterprise Edition 进行配对，还可以在后端服务器上实现高可用性，但是对于 Standard Edition 池的配对，仅能采用灾难恢复措施。</span><span class="sxs-lookup"><span data-stu-id="77a39-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

