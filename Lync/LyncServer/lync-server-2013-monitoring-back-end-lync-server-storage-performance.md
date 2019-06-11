---
title: 'Lync Server 2013: 监视后端 Lync 服务器存储性能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="43ae5-102">监视后端 Lync 服务器2013存储性能</span><span class="sxs-lookup"><span data-stu-id="43ae5-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43ae5-103">_**主题上次修改时间:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="43ae5-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="43ae5-104">Lync Server 2013 后端数据库是 Lync Server 2013 部署的非常重要的部分。</span><span class="sxs-lookup"><span data-stu-id="43ae5-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="43ae5-105">我们建议持续监视数据库和相应的事务日志, 以帮助确保 Lync Server 2013 后端的性能最优化。</span><span class="sxs-lookup"><span data-stu-id="43ae5-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="43ae5-106">下表标识应监视的性能计数器, 以了解有关存储性能的信息。</span><span class="sxs-lookup"><span data-stu-id="43ae5-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="43ae5-107">必须首先确定这些计数器的基线值 (当系统处于其正常、预期负载时), 以了解系统负载时的性能变化。</span><span class="sxs-lookup"><span data-stu-id="43ae5-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="43ae5-108">要监视的性能计数器</span><span class="sxs-lookup"><span data-stu-id="43ae5-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43ae5-109">性能计数器</span><span class="sxs-lookup"><span data-stu-id="43ae5-109">Performance Counter</span></span></th>
<th><span data-ttu-id="43ae5-110">基准阈值</span><span class="sxs-lookup"><span data-stu-id="43ae5-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43ae5-111">事务/秒 (RTC)</span><span class="sxs-lookup"><span data-stu-id="43ae5-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43ae5-112">事务/秒 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="43ae5-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43ae5-113">事务/秒 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="43ae5-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43ae5-114">日志刷新/秒 (RTC)</span><span class="sxs-lookup"><span data-stu-id="43ae5-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43ae5-115">日志刷新/秒 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="43ae5-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43ae5-116">日志刷新/秒 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="43ae5-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43ae5-117">每秒磁盘传输 (读 + 写)-RTC 数据库</span><span class="sxs-lookup"><span data-stu-id="43ae5-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43ae5-118">磁盘传输/秒-RTC 日志</span><span class="sxs-lookup"><span data-stu-id="43ae5-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43ae5-119">磁盘传输/秒-rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="43ae5-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43ae5-120">磁盘传输/秒-rtcdyn 日志</span><span class="sxs-lookup"><span data-stu-id="43ae5-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

