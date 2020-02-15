---
title: Lync Server 2013： IMReportSummary 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 287fc0ceff26a5940d717b4efa1ef2c525acb0f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="2d739-102">Lync Server 2013 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="2d739-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d739-103">_**上次修改的主题：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="2d739-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="2d739-104">IMReportSummaryTable 提供有关组织中进行的即时消息会话的总体报告。</span><span class="sxs-lookup"><span data-stu-id="2d739-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="2d739-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2d739-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d739-106">列</span><span class="sxs-lookup"><span data-stu-id="2d739-106">Column</span></span></th>
<th><span data-ttu-id="2d739-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="2d739-107">Data Type</span></span></th>
<th><span data-ttu-id="2d739-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="2d739-108">Key/Index</span></span></th>
<th><span data-ttu-id="2d739-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d739-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d739-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="2d739-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2d739-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2d739-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2d739-112">主</span><span class="sxs-lookup"><span data-stu-id="2d739-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d739-113">即时消息会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2d739-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d739-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="2d739-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="2d739-115">char （1）</span><span class="sxs-lookup"><span data-stu-id="2d739-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="2d739-116">主</span><span class="sxs-lookup"><span data-stu-id="2d739-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d739-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="2d739-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="2d739-118">nvarchar （257）</span><span class="sxs-lookup"><span data-stu-id="2d739-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="2d739-119">主</span><span class="sxs-lookup"><span data-stu-id="2d739-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d739-120">承载会话的池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="2d739-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d739-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="2d739-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="2d739-122">int</span><span class="sxs-lookup"><span data-stu-id="2d739-122">int</span></span></p></td>
<td><p><span data-ttu-id="2d739-123">主</span><span class="sxs-lookup"><span data-stu-id="2d739-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d739-124">呼叫的优先级（例如，紧急或非紧急）。</span><span class="sxs-lookup"><span data-stu-id="2d739-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="2d739-125">优先级信息存储在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表中</a>。</span><span class="sxs-lookup"><span data-stu-id="2d739-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d739-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="2d739-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="2d739-127">bigint</span><span class="sxs-lookup"><span data-stu-id="2d739-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d739-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="2d739-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="2d739-129">bigint</span><span class="sxs-lookup"><span data-stu-id="2d739-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d739-130">会话期间交换的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="2d739-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

