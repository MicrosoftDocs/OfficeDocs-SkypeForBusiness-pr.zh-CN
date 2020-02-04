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
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="ff6b7-102">Lync Server 2013 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="ff6b7-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff6b7-103">_**主题上次修改时间：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="ff6b7-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="ff6b7-104">IMReportSummaryTable 提供组织中的即时消息会话的整体报告。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="ff6b7-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff6b7-106">列</span><span class="sxs-lookup"><span data-stu-id="ff6b7-106">Column</span></span></th>
<th><span data-ttu-id="ff6b7-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff6b7-107">Data Type</span></span></th>
<th><span data-ttu-id="ff6b7-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="ff6b7-108">Key/Index</span></span></th>
<th><span data-ttu-id="ff6b7-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff6b7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff6b7-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff6b7-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6b7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ff6b7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ff6b7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-113">即时消息会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6b7-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="ff6b7-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6b7-115">char （1）</span><span class="sxs-lookup"><span data-stu-id="ff6b7-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ff6b7-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6b7-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="ff6b7-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6b7-118">nvarchar （257）</span><span class="sxs-lookup"><span data-stu-id="ff6b7-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-119">Primary</span><span class="sxs-lookup"><span data-stu-id="ff6b7-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-120">托管会话的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6b7-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="ff6b7-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6b7-122">int</span><span class="sxs-lookup"><span data-stu-id="ff6b7-122">int</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-123">Primary</span><span class="sxs-lookup"><span data-stu-id="ff6b7-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff6b7-124">通话的优先级（例如，紧急或非紧急）。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="ff6b7-125">优先级信息存储在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表中</a>。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6b7-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="ff6b7-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6b7-127">bigint</span><span class="sxs-lookup"><span data-stu-id="ff6b7-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6b7-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="ff6b7-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6b7-129">bigint</span><span class="sxs-lookup"><span data-stu-id="ff6b7-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff6b7-130">会话期间交换的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="ff6b7-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

