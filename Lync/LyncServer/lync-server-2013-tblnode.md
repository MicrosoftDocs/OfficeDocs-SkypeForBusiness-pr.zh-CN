---
title: Lync Server 2013： tblNode
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
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="987ef-102">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="987ef-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="987ef-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="987ef-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="987ef-104">tblNode 包含在 Lync Server 2013 控制面板和管理 cmdlet 中托管的对象树（包含类别或聊天室节点）。</span><span class="sxs-lookup"><span data-stu-id="987ef-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="987ef-105">Columns</span><span class="sxs-lookup"><span data-stu-id="987ef-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="987ef-106">列</span><span class="sxs-lookup"><span data-stu-id="987ef-106">Column</span></span></th>
<th><span data-ttu-id="987ef-107">类型</span><span class="sxs-lookup"><span data-stu-id="987ef-107">Type</span></span></th>
<th><span data-ttu-id="987ef-108">说明</span><span class="sxs-lookup"><span data-stu-id="987ef-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="987ef-109">个</span><span class="sxs-lookup"><span data-stu-id="987ef-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="987ef-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-111">节点 ID（唯一编号）。</span><span class="sxs-lookup"><span data-stu-id="987ef-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="987ef-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="987ef-113">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-114">节点 GUID。</span><span class="sxs-lookup"><span data-stu-id="987ef-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-115">parentID</span><span class="sxs-lookup"><span data-stu-id="987ef-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="987ef-116">int</span><span class="sxs-lookup"><span data-stu-id="987ef-116">int</span></span></p></td>
<td><p><span data-ttu-id="987ef-p101">父节点 ID。根节点（ID 为 1）将其自身用作父项。</span><span class="sxs-lookup"><span data-stu-id="987ef-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="987ef-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="987ef-120">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-121">如果节点是类别，则为 True。</span><span class="sxs-lookup"><span data-stu-id="987ef-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="987ef-122">如果节点是聊天室，则为 False。</span><span class="sxs-lookup"><span data-stu-id="987ef-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="987ef-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="987ef-124">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-125">节点名称。</span><span class="sxs-lookup"><span data-stu-id="987ef-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="987ef-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="987ef-127">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-128">节点描述。</span><span class="sxs-lookup"><span data-stu-id="987ef-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-129">invite</span><span class="sxs-lookup"><span data-stu-id="987ef-129">invite</span></span></p></td>
<td><p><span data-ttu-id="987ef-130">位</span><span class="sxs-lookup"><span data-stu-id="987ef-130">bit</span></span></p></td>
<td><p><span data-ttu-id="987ef-131">针对类别：</span><span class="sxs-lookup"><span data-stu-id="987ef-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-132">如果邀请打开，则为 True。</span><span class="sxs-lookup"><span data-stu-id="987ef-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="987ef-133">如果邀请关闭，则为 False。</span><span class="sxs-lookup"><span data-stu-id="987ef-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="987ef-134">针对聊天室：</span><span class="sxs-lookup"><span data-stu-id="987ef-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-135">如果邀请关闭，则为 False（覆盖父类别）。</span><span class="sxs-lookup"><span data-stu-id="987ef-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="987ef-136">如果邀请设置是继承自父类别，则为 Null。</span><span class="sxs-lookup"><span data-stu-id="987ef-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-137">日志</span><span class="sxs-lookup"><span data-stu-id="987ef-137">logged</span></span></p></td>
<td><p><span data-ttu-id="987ef-138">位</span><span class="sxs-lookup"><span data-stu-id="987ef-138">bit</span></span></p></td>
<td><p><span data-ttu-id="987ef-139">针对类别：</span><span class="sxs-lookup"><span data-stu-id="987ef-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-140">如果聊天历史记录打开，则为 True。</span><span class="sxs-lookup"><span data-stu-id="987ef-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="987ef-141">如果聊天历史记录关闭，则为 False。</span><span class="sxs-lookup"><span data-stu-id="987ef-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="987ef-142">针对聊天室：</span><span class="sxs-lookup"><span data-stu-id="987ef-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-143">不适.</span><span class="sxs-lookup"><span data-stu-id="987ef-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-144">filePost</span><span class="sxs-lookup"><span data-stu-id="987ef-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="987ef-145">位</span><span class="sxs-lookup"><span data-stu-id="987ef-145">bit</span></span></p></td>
<td><p><span data-ttu-id="987ef-146">针对类别：</span><span class="sxs-lookup"><span data-stu-id="987ef-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-147">如果允许文件上载，则为 True。</span><span class="sxs-lookup"><span data-stu-id="987ef-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="987ef-148">如果不允许文件上载，则为 False。</span><span class="sxs-lookup"><span data-stu-id="987ef-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="987ef-149">针对聊天室：</span><span class="sxs-lookup"><span data-stu-id="987ef-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-150">不适.</span><span class="sxs-lookup"><span data-stu-id="987ef-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-151">禁用</span><span class="sxs-lookup"><span data-stu-id="987ef-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="987ef-152">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-p102">如果聊天室已禁用，则为 True。仅适用于聊天室。（对于类别则为 False。）</span><span class="sxs-lookup"><span data-stu-id="987ef-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-156">性能</span><span class="sxs-lookup"><span data-stu-id="987ef-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="987ef-157">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-158">行为（在 EnumValue 表中查找）：</span><span class="sxs-lookup"><span data-stu-id="987ef-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-159">4：普通（普通聊天室）。</span><span class="sxs-lookup"><span data-stu-id="987ef-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="987ef-160">5：大会堂（大会堂聊天室，仅演示者可以参与）。</span><span class="sxs-lookup"><span data-stu-id="987ef-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="987ef-161">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="987ef-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-162">visibility</span><span class="sxs-lookup"><span data-stu-id="987ef-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="987ef-163">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-164">可见性（在 EnumValue 表中查找）：</span><span class="sxs-lookup"><span data-stu-id="987ef-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="987ef-165">2：专用</span><span class="sxs-lookup"><span data-stu-id="987ef-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="987ef-166">3：范围</span><span class="sxs-lookup"><span data-stu-id="987ef-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="987ef-167">6：打开</span><span class="sxs-lookup"><span data-stu-id="987ef-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="987ef-168">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="987ef-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-169">siopID</span><span class="sxs-lookup"><span data-stu-id="987ef-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="987ef-170">GUID</span><span class="sxs-lookup"><span data-stu-id="987ef-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="987ef-p103">如果外接程序与此聊天室关联，则为外接程序 GUID。（类别没有外接程序。）</span><span class="sxs-lookup"><span data-stu-id="987ef-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="987ef-173">外接程序信息在 SiopWhiteList 表中进行查找。</span><span class="sxs-lookup"><span data-stu-id="987ef-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="987ef-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="987ef-175">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-176">创建此节点的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="987ef-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="987ef-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="987ef-178">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-179">节点创建的时间戳。</span><span class="sxs-lookup"><span data-stu-id="987ef-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="987ef-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="987ef-181">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-182">对此节点执行最新更新的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="987ef-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="987ef-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="987ef-184">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="987ef-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="987ef-185">此节点最新更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="987ef-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="987ef-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="987ef-187">datetime</span><span class="sxs-lookup"><span data-stu-id="987ef-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="987ef-p104">影响此节点的最近一次清除操作（从 tblScopedPrincipal 表中删除范围，从 tblPrincipalRole 表中删除角色）的时间。用于聊天服务的内部缓存更新机制。</span><span class="sxs-lookup"><span data-stu-id="987ef-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="987ef-190">Keys</span><span class="sxs-lookup"><span data-stu-id="987ef-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="987ef-191">列</span><span class="sxs-lookup"><span data-stu-id="987ef-191">Column</span></span></th>
<th><span data-ttu-id="987ef-192">说明</span><span class="sxs-lookup"><span data-stu-id="987ef-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="987ef-193">个</span><span class="sxs-lookup"><span data-stu-id="987ef-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="987ef-194">主键。</span><span class="sxs-lookup"><span data-stu-id="987ef-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-195">性能</span><span class="sxs-lookup"><span data-stu-id="987ef-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="987ef-196">在 tblEnumValue.valueID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="987ef-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-197">visibility</span><span class="sxs-lookup"><span data-stu-id="987ef-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="987ef-198">在 tblEnumValue.valueID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="987ef-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="987ef-199">parentID</span><span class="sxs-lookup"><span data-stu-id="987ef-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="987ef-200">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="987ef-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="987ef-201">siopID</span><span class="sxs-lookup"><span data-stu-id="987ef-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="987ef-202">在 tblSiopWhiteList.siopId 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="987ef-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

