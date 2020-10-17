---
title: Lync Server 2013：呼叫寄存的容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 079d1517afa72eeff607920d86b093ac01d673de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512829"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="3b94c-102">Lync Server 2013 中呼叫寄存的容量规划</span><span class="sxs-lookup"><span data-stu-id="3b94c-102">Capacity planning for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b94c-103">_**上次修改的主题：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="3b94c-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="3b94c-104">下表介绍了可以用作容量规划要求基础的呼叫寄存用户模型。</span><span class="sxs-lookup"><span data-stu-id="3b94c-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3b94c-105">请记住，对于灾难恢复容量规划，配对池的每个池都应该能够处理两个池中的呼叫寄存服务的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="3b94c-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="3b94c-106">呼叫寄存用户模型</span><span class="sxs-lookup"><span data-stu-id="3b94c-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b94c-107">跃点数</span><span class="sxs-lookup"><span data-stu-id="3b94c-107">Metric</span></span></th>
<th><span data-ttu-id="3b94c-108">每个前端池 (8 台前端服务器) </span><span class="sxs-lookup"><span data-stu-id="3b94c-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="3b94c-109">每台 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="3b94c-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b94c-110">寄存速率</span><span class="sxs-lookup"><span data-stu-id="3b94c-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="3b94c-111">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="3b94c-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="3b94c-112">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="3b94c-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b94c-113">取回寄存呼叫的速率</span><span class="sxs-lookup"><span data-stu-id="3b94c-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="3b94c-114">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="3b94c-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="3b94c-115">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="3b94c-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b94c-116">平均寄存持续时间</span><span class="sxs-lookup"><span data-stu-id="3b94c-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="3b94c-117">60 秒</span><span class="sxs-lookup"><span data-stu-id="3b94c-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="3b94c-118">60 秒</span><span class="sxs-lookup"><span data-stu-id="3b94c-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

