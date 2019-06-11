---
title: 'Lync Server 2013: IMReportSummary 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="85ef9-102">Lync Server 2013 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="85ef9-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ef9-103">_**主题上次修改时间:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="85ef9-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="85ef9-104">IMReportSummaryTable 提供组织中的即时消息会话的整体报告。</span><span class="sxs-lookup"><span data-stu-id="85ef9-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="85ef9-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="85ef9-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85ef9-106">列</span><span class="sxs-lookup"><span data-stu-id="85ef9-106">Column</span></span></th>
<th><span data-ttu-id="85ef9-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="85ef9-107">Data Type</span></span></th>
<th><span data-ttu-id="85ef9-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="85ef9-108">Key/Index</span></span></th>
<th><span data-ttu-id="85ef9-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="85ef9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85ef9-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="85ef9-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85ef9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="85ef9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="85ef9-112">Primary</span><span class="sxs-lookup"><span data-stu-id="85ef9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="85ef9-113">即时消息会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="85ef9-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ef9-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="85ef9-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="85ef9-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="85ef9-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="85ef9-116">Primary</span><span class="sxs-lookup"><span data-stu-id="85ef9-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ef9-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="85ef9-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="85ef9-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="85ef9-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="85ef9-119">Primary</span><span class="sxs-lookup"><span data-stu-id="85ef9-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="85ef9-120">托管会话的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="85ef9-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ef9-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="85ef9-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="85ef9-122">int</span><span class="sxs-lookup"><span data-stu-id="85ef9-122">int</span></span></p></td>
<td><p><span data-ttu-id="85ef9-123">Primary</span><span class="sxs-lookup"><span data-stu-id="85ef9-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="85ef9-124">通话的优先级 (例如, 紧急或非紧急)。</span><span class="sxs-lookup"><span data-stu-id="85ef9-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="85ef9-125">优先级信息存储在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表中</a>。</span><span class="sxs-lookup"><span data-stu-id="85ef9-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ef9-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="85ef9-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="85ef9-127">bigint</span><span class="sxs-lookup"><span data-stu-id="85ef9-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ef9-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="85ef9-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="85ef9-129">bigint</span><span class="sxs-lookup"><span data-stu-id="85ef9-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85ef9-130">会话期间交换的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="85ef9-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

