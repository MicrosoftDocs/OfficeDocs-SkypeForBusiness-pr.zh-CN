---
title: Lync Server 2013 支持的池配对选项和最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="792bf-102">支持 Lync Server 2013 的池配对选项和最佳做法</span><span class="sxs-lookup"><span data-stu-id="792bf-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="792bf-103">_**主题上次修改时间:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="792bf-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="792bf-104">对两个数据中心之间的距离没有限制, 包括彼此配对的前端池。</span><span class="sxs-lookup"><span data-stu-id="792bf-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="792bf-105">我们建议你在同一世界地区使用两个数据中心, 并在它们之间使用高速链接。</span><span class="sxs-lookup"><span data-stu-id="792bf-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="792bf-106">最好将两个数据中心分开, 以避免一次灾难碰到这两个数据中心。</span><span class="sxs-lookup"><span data-stu-id="792bf-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="792bf-107">可以在世界各地有两个数据中心, 但由于数据复制中的延迟, 可能会导致更高的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="792bf-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="792bf-108">当您计划对池进行配对时，必须谨记仅支持以下配对法：</span><span class="sxs-lookup"><span data-stu-id="792bf-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="792bf-109">Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。</span><span class="sxs-lookup"><span data-stu-id="792bf-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="792bf-110">同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。</span><span class="sxs-lookup"><span data-stu-id="792bf-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="792bf-111">物理池仅能与其他物理池配对。</span><span class="sxs-lookup"><span data-stu-id="792bf-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="792bf-112">同样，虚拟池仅能与其他虚拟池配对。</span><span class="sxs-lookup"><span data-stu-id="792bf-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="792bf-113">配对的池必须运行相同的操作系统。</span><span class="sxs-lookup"><span data-stu-id="792bf-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="792bf-p104">拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。但是，不支持进行这些类型的配对。</span><span class="sxs-lookup"><span data-stu-id="792bf-p104">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations. For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool. However, these types of pairings are not supported.</span></span>

<span data-ttu-id="792bf-117">每个池中的每个池都应具有在发生灾难时为来自两个池的所有用户提供服务的容量。</span><span class="sxs-lookup"><span data-stu-id="792bf-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="792bf-118">如果你对企业版池进行了配对, 你也可以在后端服务器上实现高可用性, 但对于标准版池, 只有灾难恢复措施可用。</span><span class="sxs-lookup"><span data-stu-id="792bf-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

