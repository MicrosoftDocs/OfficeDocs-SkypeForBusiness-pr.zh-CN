---
title: Lync Server 2013： tblComplianceParticipant
description: Lync Server 2013： tblComplianceParticipant。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569068"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="9ad16-103">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="9ad16-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ad16-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9ad16-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9ad16-105">tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="9ad16-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="9ad16-106">列数</span><span class="sxs-lookup"><span data-stu-id="9ad16-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ad16-107">列</span><span class="sxs-lookup"><span data-stu-id="9ad16-107">Column</span></span></th>
<th><span data-ttu-id="9ad16-108">类型</span><span class="sxs-lookup"><span data-stu-id="9ad16-108">Type</span></span></th>
<th><span data-ttu-id="9ad16-109">说明</span><span class="sxs-lookup"><span data-stu-id="9ad16-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ad16-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="9ad16-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="9ad16-111">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="9ad16-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="9ad16-112">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="9ad16-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ad16-113">userId</span><span class="sxs-lookup"><span data-stu-id="9ad16-113">userId</span></span></p></td>
<td><p><span data-ttu-id="9ad16-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="9ad16-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9ad16-115">参与者的主体 ID（与 tblPrincipal.prinID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="9ad16-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ad16-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="9ad16-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="9ad16-117">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="9ad16-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="9ad16-118">加入事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="9ad16-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ad16-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="9ad16-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="9ad16-120">bigint</span><span class="sxs-lookup"><span data-stu-id="9ad16-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="9ad16-p101">如果仍加入参与者，则为 null。如果不为 null，则为通道离开事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="9ad16-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="9ad16-123">当所有转换器处理该事件时，将最终删除这些项。</span><span class="sxs-lookup"><span data-stu-id="9ad16-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ad16-124">userUri</span><span class="sxs-lookup"><span data-stu-id="9ad16-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="9ad16-125">nvarchar(255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="9ad16-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="9ad16-126">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="9ad16-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ad16-127">serverID</span><span class="sxs-lookup"><span data-stu-id="9ad16-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="9ad16-128">int</span><span class="sxs-lookup"><span data-stu-id="9ad16-128">int</span></span></p></td>
<td><p><span data-ttu-id="9ad16-129">服务器标识（如 tblServerIdentity.serverID 表中所示）。</span><span class="sxs-lookup"><span data-stu-id="9ad16-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ad16-130">sessionId</span><span class="sxs-lookup"><span data-stu-id="9ad16-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="9ad16-131">bigint</span><span class="sxs-lookup"><span data-stu-id="9ad16-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="9ad16-p102">服务器会话。它是每次聊天服务启动时生成的随机数字。它用于区分会话以便标识孤立参与者。</span><span class="sxs-lookup"><span data-stu-id="9ad16-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="9ad16-135">键</span><span class="sxs-lookup"><span data-stu-id="9ad16-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ad16-136">列</span><span class="sxs-lookup"><span data-stu-id="9ad16-136">Column</span></span></th>
<th><span data-ttu-id="9ad16-137">说明</span><span class="sxs-lookup"><span data-stu-id="9ad16-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ad16-138">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="9ad16-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="9ad16-139">主键。</span><span class="sxs-lookup"><span data-stu-id="9ad16-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

