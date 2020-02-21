---
title: Lync Server 2013： Dialog 表
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
ms.openlocfilehash: 18646cb43bc957ebee7da0a313e840cc18f3ed54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="349a4-102">Lync Server 2013 中的对话框表</span><span class="sxs-lookup"><span data-stu-id="349a4-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="349a4-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="349a4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="349a4-104">Dialog 表是一个支持表；每条记录代表一个会话初始协议 (SIP) 对话。</span><span class="sxs-lookup"><span data-stu-id="349a4-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="349a4-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="349a4-106"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="349a4-107"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="349a4-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="349a4-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="349a4-110">datetime</span><span class="sxs-lookup"><span data-stu-id="349a4-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="349a4-111">主</span><span class="sxs-lookup"><span data-stu-id="349a4-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="349a4-p101">用户体验质量 (QoE) 代理从呼叫者或被叫方接收第一个报告的时间。与 SessionSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="349a4-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="349a4-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="349a4-115">int</span><span class="sxs-lookup"><span data-stu-id="349a4-115">int</span></span></p></td>
<td><p><span data-ttu-id="349a4-116">主</span><span class="sxs-lookup"><span data-stu-id="349a4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="349a4-117">当会话具有相同的 ConferenceDateTime 时区分会话的序号。</span><span class="sxs-lookup"><span data-stu-id="349a4-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="349a4-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="349a4-119">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="349a4-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="349a4-120">全局唯一的对话 ID。</span><span class="sxs-lookup"><span data-stu-id="349a4-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="349a4-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="349a4-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="349a4-122">int</span><span class="sxs-lookup"><span data-stu-id="349a4-122">int</span></span></p></td>
<td><p><span data-ttu-id="349a4-123">index</span><span class="sxs-lookup"><span data-stu-id="349a4-123">index</span></span></p></td>
<td><p><span data-ttu-id="349a4-124">对话 ID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="349a4-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

