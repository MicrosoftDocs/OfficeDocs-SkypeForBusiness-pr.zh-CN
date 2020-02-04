---
title: Lync Server 2013：tblNode
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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="08f96-102">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="08f96-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f96-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="08f96-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="08f96-104">tblNode 包含在 Lync Server 2013 控制面板和管理 cmdlet 中托管的对象树（包括类别或聊天室节点）。</span><span class="sxs-lookup"><span data-stu-id="08f96-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="08f96-105">多</span><span class="sxs-lookup"><span data-stu-id="08f96-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08f96-106">列</span><span class="sxs-lookup"><span data-stu-id="08f96-106">Column</span></span></th>
<th><span data-ttu-id="08f96-107">类型</span><span class="sxs-lookup"><span data-stu-id="08f96-107">Type</span></span></th>
<th><span data-ttu-id="08f96-108">说明</span><span class="sxs-lookup"><span data-stu-id="08f96-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08f96-109">a</span><span class="sxs-lookup"><span data-stu-id="08f96-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="08f96-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-111">节点 ID （唯一编号）。</span><span class="sxs-lookup"><span data-stu-id="08f96-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="08f96-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="08f96-113">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-114">节点 GUID。</span><span class="sxs-lookup"><span data-stu-id="08f96-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-115">parentID</span><span class="sxs-lookup"><span data-stu-id="08f96-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="08f96-116">int</span><span class="sxs-lookup"><span data-stu-id="08f96-116">int</span></span></p></td>
<td><p><span data-ttu-id="08f96-117">父项的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="08f96-117">Node ID of parent.</span></span> <span data-ttu-id="08f96-118">根节点（ID 为1）也将其本身包括到父节点。</span><span class="sxs-lookup"><span data-stu-id="08f96-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="08f96-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="08f96-120">位，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-121">如果节点是类别，则为 True。</span><span class="sxs-lookup"><span data-stu-id="08f96-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="08f96-122">如果节点是聊天室，则为 False。</span><span class="sxs-lookup"><span data-stu-id="08f96-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="08f96-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="08f96-124">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="08f96-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-125">节点名称。</span><span class="sxs-lookup"><span data-stu-id="08f96-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="08f96-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="08f96-127">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="08f96-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-128">节点说明。</span><span class="sxs-lookup"><span data-stu-id="08f96-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-129">邀请</span><span class="sxs-lookup"><span data-stu-id="08f96-129">invite</span></span></p></td>
<td><p><span data-ttu-id="08f96-130">bit</span><span class="sxs-lookup"><span data-stu-id="08f96-130">bit</span></span></p></td>
<td><p><span data-ttu-id="08f96-131">对于类别：</span><span class="sxs-lookup"><span data-stu-id="08f96-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-132">如果邀请已打开，则为 True。</span><span class="sxs-lookup"><span data-stu-id="08f96-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="08f96-133">如果邀请已关闭，则为 False。</span><span class="sxs-lookup"><span data-stu-id="08f96-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="08f96-134">对于会议室：</span><span class="sxs-lookup"><span data-stu-id="08f96-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-135">如果邀请已关闭，则为 False （覆盖父类别）。</span><span class="sxs-lookup"><span data-stu-id="08f96-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="08f96-136">如果 "邀请" 设置继承自父类别，则为 Null。</span><span class="sxs-lookup"><span data-stu-id="08f96-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-137">身份</span><span class="sxs-lookup"><span data-stu-id="08f96-137">logged</span></span></p></td>
<td><p><span data-ttu-id="08f96-138">bit</span><span class="sxs-lookup"><span data-stu-id="08f96-138">bit</span></span></p></td>
<td><p><span data-ttu-id="08f96-139">对于类别：</span><span class="sxs-lookup"><span data-stu-id="08f96-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-140">如果打开聊天记录，则为 True。</span><span class="sxs-lookup"><span data-stu-id="08f96-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="08f96-141">如果聊天历史记录处于关闭状态，则为 False。</span><span class="sxs-lookup"><span data-stu-id="08f96-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="08f96-142">对于会议室：</span><span class="sxs-lookup"><span data-stu-id="08f96-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-143">Null.</span><span class="sxs-lookup"><span data-stu-id="08f96-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-144">filePost</span><span class="sxs-lookup"><span data-stu-id="08f96-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="08f96-145">bit</span><span class="sxs-lookup"><span data-stu-id="08f96-145">bit</span></span></p></td>
<td><p><span data-ttu-id="08f96-146">对于类别：</span><span class="sxs-lookup"><span data-stu-id="08f96-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-147">如果允许文件上载，则为 True。</span><span class="sxs-lookup"><span data-stu-id="08f96-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="08f96-148">如果不允许文件上载，则为 False。</span><span class="sxs-lookup"><span data-stu-id="08f96-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="08f96-149">对于会议室：</span><span class="sxs-lookup"><span data-stu-id="08f96-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-150">Null.</span><span class="sxs-lookup"><span data-stu-id="08f96-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-151">禁用</span><span class="sxs-lookup"><span data-stu-id="08f96-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="08f96-152">位，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-153">如果禁用聊天室，则为 True。</span><span class="sxs-lookup"><span data-stu-id="08f96-153">True if the chat room is disabled.</span></span> <span data-ttu-id="08f96-154">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="08f96-154">Applies only to chat rooms.</span></span> <span data-ttu-id="08f96-155">（False 表示类别。）</span><span class="sxs-lookup"><span data-stu-id="08f96-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-156">现象</span><span class="sxs-lookup"><span data-stu-id="08f96-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="08f96-157">smallint，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-158">行为（在 EnumValue 表中查看）：</span><span class="sxs-lookup"><span data-stu-id="08f96-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-159">4：普通（正常聊天室）。</span><span class="sxs-lookup"><span data-stu-id="08f96-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="08f96-160">5： Auditorium （Auditorium 聊天室，只有演示者可以参与）。</span><span class="sxs-lookup"><span data-stu-id="08f96-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="08f96-161">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="08f96-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-162">了解</span><span class="sxs-lookup"><span data-stu-id="08f96-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="08f96-163">smallint，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-164">可见性（在 EnumValue 表上查看）：</span><span class="sxs-lookup"><span data-stu-id="08f96-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="08f96-165">2：私密</span><span class="sxs-lookup"><span data-stu-id="08f96-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="08f96-166">3：范围</span><span class="sxs-lookup"><span data-stu-id="08f96-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="08f96-167">6：打开</span><span class="sxs-lookup"><span data-stu-id="08f96-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="08f96-168">仅适用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="08f96-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-169">siopID</span><span class="sxs-lookup"><span data-stu-id="08f96-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="08f96-170">GUID</span><span class="sxs-lookup"><span data-stu-id="08f96-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="08f96-171">加载项 GUID （如果外接程序与此聊天室相关联）。</span><span class="sxs-lookup"><span data-stu-id="08f96-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="08f96-172">（类别没有外接程序。）</span><span class="sxs-lookup"><span data-stu-id="08f96-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="08f96-173">外接程序信息在 SiopWhiteList 表中查找。</span><span class="sxs-lookup"><span data-stu-id="08f96-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="08f96-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="08f96-175">int，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-176">创建此节点的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="08f96-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="08f96-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="08f96-178">bigint，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-179">节点创建的时间戳。</span><span class="sxs-lookup"><span data-stu-id="08f96-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="08f96-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="08f96-181">int，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-182">执行此节点的最新更新的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="08f96-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="08f96-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="08f96-184">bigint，not null</span><span class="sxs-lookup"><span data-stu-id="08f96-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="08f96-185">此节点的最新更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="08f96-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="08f96-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="08f96-187">datetime</span><span class="sxs-lookup"><span data-stu-id="08f96-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="08f96-188">最新的清除操作（从 tblScopedPrincipal 表的作用域和 tblPrincipalRole 表中的角色删除）影响此节点的时间。</span><span class="sxs-lookup"><span data-stu-id="08f96-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="08f96-189">此功能由聊天服务的内部缓存更新机制使用。</span><span class="sxs-lookup"><span data-stu-id="08f96-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="08f96-190">标示</span><span class="sxs-lookup"><span data-stu-id="08f96-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08f96-191">列</span><span class="sxs-lookup"><span data-stu-id="08f96-191">Column</span></span></th>
<th><span data-ttu-id="08f96-192">说明</span><span class="sxs-lookup"><span data-stu-id="08f96-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08f96-193">a</span><span class="sxs-lookup"><span data-stu-id="08f96-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="08f96-194">主键。</span><span class="sxs-lookup"><span data-stu-id="08f96-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-195">现象</span><span class="sxs-lookup"><span data-stu-id="08f96-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="08f96-196">TblEnumValue 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="08f96-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-197">了解</span><span class="sxs-lookup"><span data-stu-id="08f96-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="08f96-198">TblEnumValue 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="08f96-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08f96-199">parentID</span><span class="sxs-lookup"><span data-stu-id="08f96-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="08f96-200">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="08f96-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08f96-201">siopID</span><span class="sxs-lookup"><span data-stu-id="08f96-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="08f96-202">TblSiopWhiteList 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="08f96-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

