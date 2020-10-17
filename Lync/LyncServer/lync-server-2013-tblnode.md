---
title: Lync Server 2013： tblNode
description: Lync Server 2013： tblNode。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547548"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="aa8d2-103">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="aa8d2-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa8d2-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="aa8d2-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="aa8d2-105">tblNode 包含 (类别或聊天室节点的对象树，) 在 Lync Server 2013 控制面板和管理 cmdlet 中进行管理。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="aa8d2-106">列数</span><span class="sxs-lookup"><span data-stu-id="aa8d2-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa8d2-107">列</span><span class="sxs-lookup"><span data-stu-id="aa8d2-107">Column</span></span></th>
<th><span data-ttu-id="aa8d2-108">类型</span><span class="sxs-lookup"><span data-stu-id="aa8d2-108">Type</span></span></th>
<th><span data-ttu-id="aa8d2-109">说明</span><span class="sxs-lookup"><span data-stu-id="aa8d2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-110">个</span><span class="sxs-lookup"><span data-stu-id="aa8d2-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-112">节点 ID（唯一编号）。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="aa8d2-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-114">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-115">节点 GUID。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-116">parentID</span><span class="sxs-lookup"><span data-stu-id="aa8d2-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-117">int</span><span class="sxs-lookup"><span data-stu-id="aa8d2-117">int</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-p101">父节点 ID。根节点（ID 为 1）将其自身用作父项。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="aa8d2-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-121">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-122">如果节点是类别，则为 True。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="aa8d2-123">如果节点是聊天室，则为 False。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="aa8d2-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-125">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-126">节点名称。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="aa8d2-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-128">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-129">节点描述。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-130">invite</span><span class="sxs-lookup"><span data-stu-id="aa8d2-130">invite</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-131">位</span><span class="sxs-lookup"><span data-stu-id="aa8d2-131">bit</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-132">针对类别：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-133">如果邀请打开，则为 True。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-134">如果邀请关闭，则为 False。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="aa8d2-135">针对聊天室：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-136">如果邀请关闭，则为 False（覆盖父类别）。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-137">如果邀请设置是继承自父类别，则为 Null。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-138">日志</span><span class="sxs-lookup"><span data-stu-id="aa8d2-138">logged</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-139">位</span><span class="sxs-lookup"><span data-stu-id="aa8d2-139">bit</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-140">针对类别：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-141">如果聊天历史记录打开，则为 True。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-142">如果聊天历史记录关闭，则为 False。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="aa8d2-143">针对聊天室：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-144">不适.</span><span class="sxs-lookup"><span data-stu-id="aa8d2-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-145">filePost</span><span class="sxs-lookup"><span data-stu-id="aa8d2-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-146">位</span><span class="sxs-lookup"><span data-stu-id="aa8d2-146">bit</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-147">针对类别：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-148">如果允许文件上载，则为 True。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-149">如果不允许文件上载，则为 False。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="aa8d2-150">针对聊天室：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-151">不适.</span><span class="sxs-lookup"><span data-stu-id="aa8d2-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-152">禁用</span><span class="sxs-lookup"><span data-stu-id="aa8d2-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-153">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-p102">如果聊天室已禁用，则为 True。仅适用于聊天室。（对于类别则为 False。）</span><span class="sxs-lookup"><span data-stu-id="aa8d2-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-157">性能</span><span class="sxs-lookup"><span data-stu-id="aa8d2-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-158">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-159">行为（在 EnumValue 表中查找）：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-160">4：普通（普通聊天室）。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-161">5：大会堂（大会堂聊天室，仅演示者可以参与）。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="aa8d2-162">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-163">visibility</span><span class="sxs-lookup"><span data-stu-id="aa8d2-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-164">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-165">可见性（在 EnumValue 表中查找）：</span><span class="sxs-lookup"><span data-stu-id="aa8d2-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="aa8d2-166">2：专用</span><span class="sxs-lookup"><span data-stu-id="aa8d2-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-167">3：范围</span><span class="sxs-lookup"><span data-stu-id="aa8d2-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="aa8d2-168">6：打开</span><span class="sxs-lookup"><span data-stu-id="aa8d2-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="aa8d2-169">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-170">siopID</span><span class="sxs-lookup"><span data-stu-id="aa8d2-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-171">GUID</span><span class="sxs-lookup"><span data-stu-id="aa8d2-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-p103">如果外接程序与此聊天室关联，则为外接程序 GUID。（类别没有外接程序。）</span><span class="sxs-lookup"><span data-stu-id="aa8d2-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="aa8d2-174">外接程序信息在 SiopWhiteList 表中进行查找。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="aa8d2-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-176">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-177">创建此节点的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="aa8d2-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-179">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-180">节点创建的时间戳。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="aa8d2-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-182">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-183">对此节点执行最新更新的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="aa8d2-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-185">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="aa8d2-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-186">此节点最新更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="aa8d2-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-188">datetime</span><span class="sxs-lookup"><span data-stu-id="aa8d2-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-p104">影响此节点的最近一次清除操作（从 tblScopedPrincipal 表中删除范围，从 tblPrincipalRole 表中删除角色）的时间。用于聊天服务的内部缓存更新机制。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="aa8d2-191">Keys</span><span class="sxs-lookup"><span data-stu-id="aa8d2-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa8d2-192">列</span><span class="sxs-lookup"><span data-stu-id="aa8d2-192">Column</span></span></th>
<th><span data-ttu-id="aa8d2-193">说明</span><span class="sxs-lookup"><span data-stu-id="aa8d2-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-194">个</span><span class="sxs-lookup"><span data-stu-id="aa8d2-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-195">主键。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-196">性能</span><span class="sxs-lookup"><span data-stu-id="aa8d2-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-197">在 tblEnumValue.valueID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-198">visibility</span><span class="sxs-lookup"><span data-stu-id="aa8d2-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-199">在 tblEnumValue.valueID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa8d2-200">parentID</span><span class="sxs-lookup"><span data-stu-id="aa8d2-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-201">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa8d2-202">siopID</span><span class="sxs-lookup"><span data-stu-id="aa8d2-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="aa8d2-203">在 tblSiopWhiteList.siopId 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aa8d2-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

