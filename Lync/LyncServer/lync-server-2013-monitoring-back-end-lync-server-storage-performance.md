---
title: Lync Server 2013：监视后端 Lync Server 存储性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531949"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="0a25a-102">监视后端 Lync Server 2013 存储性能</span><span class="sxs-lookup"><span data-stu-id="0a25a-102">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a25a-103">_**上次修改的主题：** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="0a25a-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="0a25a-104">Lync Server 2013 后端数据库是 Lync Server 2013 部署的一个非常重要的部分。</span><span class="sxs-lookup"><span data-stu-id="0a25a-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="0a25a-105">我们建议持续监视数据库和相应的事务日志，以帮助确保 Lync Server 2013 后端能够以最佳方式执行。</span><span class="sxs-lookup"><span data-stu-id="0a25a-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="0a25a-106">下表列出了应监视的性能计数器，以了解有关存储性能的信息。</span><span class="sxs-lookup"><span data-stu-id="0a25a-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="0a25a-107">当系统处于其正常) 负载时，必须首先确定这些计数器的比较基准值 (，以了解系统压力时的性能变化。</span><span class="sxs-lookup"><span data-stu-id="0a25a-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="0a25a-108">要监视的性能计数器</span><span class="sxs-lookup"><span data-stu-id="0a25a-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a25a-109">性能计数器</span><span class="sxs-lookup"><span data-stu-id="0a25a-109">Performance Counter</span></span></th>
<th><span data-ttu-id="0a25a-110">基准阈值</span><span class="sxs-lookup"><span data-stu-id="0a25a-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a25a-111">每秒事务数 (RTC) </span><span class="sxs-lookup"><span data-stu-id="0a25a-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a25a-112">每秒事务数 (rtcdyn) </span><span class="sxs-lookup"><span data-stu-id="0a25a-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a25a-113">每秒事务数 (tempdb) </span><span class="sxs-lookup"><span data-stu-id="0a25a-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a25a-114"> (RTC) 的日志刷新数/秒</span><span class="sxs-lookup"><span data-stu-id="0a25a-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a25a-115">日志刷新次数/秒 (rtcdyn) </span><span class="sxs-lookup"><span data-stu-id="0a25a-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a25a-116">日志刷新次数/秒 (tempdb) </span><span class="sxs-lookup"><span data-stu-id="0a25a-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a25a-117">磁盘传输/秒 (读写) RTC db</span><span class="sxs-lookup"><span data-stu-id="0a25a-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a25a-118">磁盘传输/秒-RTC 日志</span><span class="sxs-lookup"><span data-stu-id="0a25a-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a25a-119">磁盘传输数/秒-rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="0a25a-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a25a-120">磁盘传输数/秒-rtcdyn 日志</span><span class="sxs-lookup"><span data-stu-id="0a25a-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

