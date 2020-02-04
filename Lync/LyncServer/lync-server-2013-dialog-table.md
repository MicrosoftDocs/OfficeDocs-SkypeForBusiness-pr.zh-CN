---
title: Lync Server 2013：Dialog 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="1dce1-102">Lync Server 2013 中的 Dialog 表</span><span class="sxs-lookup"><span data-stu-id="1dce1-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dce1-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1dce1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1dce1-104">对话框表是支持表;每条记录表示一个会话初始协议（SIP）对话框。</span><span class="sxs-lookup"><span data-stu-id="1dce1-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dce1-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1dce1-106"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1dce1-107"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1dce1-108"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dce1-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dce1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1dce1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dce1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1dce1-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1dce1-112">优质（QoE） agent 接收来自呼叫方或被叫方的第一个报告的时间。</span><span class="sxs-lookup"><span data-stu-id="1dce1-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="1dce1-113">与 SessionSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="1dce1-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dce1-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1dce1-115">int</span><span class="sxs-lookup"><span data-stu-id="1dce1-115">int</span></span></p></td>
<td><p><span data-ttu-id="1dce1-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1dce1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1dce1-117">序列号，以便在具有相同的 ConferenceDateTime 时区分会话。</span><span class="sxs-lookup"><span data-stu-id="1dce1-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dce1-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="1dce1-119">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="1dce1-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dce1-120">全局唯一的对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="1dce1-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dce1-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="1dce1-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="1dce1-122">int</span><span class="sxs-lookup"><span data-stu-id="1dce1-122">int</span></span></p></td>
<td><p><span data-ttu-id="1dce1-123">食指</span><span class="sxs-lookup"><span data-stu-id="1dce1-123">index</span></span></p></td>
<td><p><span data-ttu-id="1dce1-124">对话框 ID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="1dce1-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

