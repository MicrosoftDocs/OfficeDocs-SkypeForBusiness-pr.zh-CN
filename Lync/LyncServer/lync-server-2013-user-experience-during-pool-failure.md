---
title: 在池故障期间 Lync Server 2013 用户体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d33dad39527f64ba7b96ae6d75f8d6e11a2f04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="766d8-102">Lync Server 2013 中池发生故障期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="766d8-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="766d8-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="766d8-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="766d8-104">如果对池进行故障转移，则会强制受影响池的所有用户注销后登录备份池。</span><span class="sxs-lookup"><span data-stu-id="766d8-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="766d8-105">登录到备份池的用户在短时间内可能会处于恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="766d8-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="766d8-106">在恢复模式下，用户无法执行会导致 Lync Server 发生永久更改的任务，如添加联系人。</span><span class="sxs-lookup"><span data-stu-id="766d8-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="766d8-107">故障转移完成后，所有用户均可从备份池获得所有服务。</span><span class="sxs-lookup"><span data-stu-id="766d8-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="766d8-108">池失败时，将中断用户具有的任何会话，用户必须在故障转移后重新建立这些会话才能继续。</span><span class="sxs-lookup"><span data-stu-id="766d8-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="766d8-p102">故障转移或故障回复期间，不能重新连接用户。位于失败的池上的用户将由备份池临时提供服务。当主池还原后，管理员可以将这些用户恢复为由其原始主池提供服务。</span><span class="sxs-lookup"><span data-stu-id="766d8-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="766d8-112">注意在 Lync 2013 中，位置信息服务器数据库不会复制到备份池。</span><span class="sxs-lookup"><span data-stu-id="766d8-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="766d8-113">作为最佳做法，管理员应定期备份 LIS 数据库，并在故障转移后使用最新备份副本在备份池中还原 LIS 数据库。</span><span class="sxs-lookup"><span data-stu-id="766d8-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="766d8-114">故障转移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="766d8-114">User Experience During Failover</span></span>

<span data-ttu-id="766d8-p104">如果某用户所在的池失败，则该用户将被注销。该用户所参与的任何对等会话将被终止，该用户组织的会议也将被终止。在注册器恢复能力计时器过期或管理员启动故障转移过程之前（以先发生的为准），该用户将无法重新登录。当用户重新登录时，将会登录到备份池。如果他们在故障转移完成前登录，则在故障转移完成前，他们将一直处于恢复能力模式。只有在故障转移完成之后，用户才能建立新会话或重新建立之前的会话。</span><span class="sxs-lookup"><span data-stu-id="766d8-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="766d8-120">故障回复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="766d8-120">User Experience During Failback</span></span>

<span data-ttu-id="766d8-p105">当受影响的用户登录到备份池时，可能会发生池故障回复，用户在故障回复期间将保持登录并正常运行。请注意，故障回复过程需要几分钟的时间才能完成。作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="766d8-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="766d8-124">下表显示了有关在故障回复期间和之后如何影响 Lync 2013 客户端或 Microsoft Lync 2010 客户端的更多详细信息，以及其他池中的用户如何查看并与正在进行故障回复的池中的用户进行交互。</span><span class="sxs-lookup"><span data-stu-id="766d8-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="766d8-125">使用 Microsoft Office Communicator 2007 R2 客户端的用户在前端池完全故障恢复之前无法登录。</span><span class="sxs-lookup"><span data-stu-id="766d8-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="766d8-p107">术语*受影响用户* 指从主池进行故障转移并由备份池提供服务的用户。根据定义，原来位于备份池上的任何用户不是受影响用户。</span><span class="sxs-lookup"><span data-stu-id="766d8-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="766d8-128">受影响用户在故障回复池中的用户体验</span><span class="sxs-lookup"><span data-stu-id="766d8-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="766d8-129">用户状态或任务</span><span class="sxs-lookup"><span data-stu-id="766d8-129">User state or task</span></span></th>
<th><span data-ttu-id="766d8-130">故障回复期间</span><span class="sxs-lookup"><span data-stu-id="766d8-130">During failback</span></span></th>
<th><span data-ttu-id="766d8-131">故障回复完成后</span><span class="sxs-lookup"><span data-stu-id="766d8-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="766d8-132">已登录用户的用户状态</span><span class="sxs-lookup"><span data-stu-id="766d8-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="766d8-p108">用户仍登录并连接到备份池。有时，用户将注销，然后在恢复能力模式下登录回原始主池。</span><span class="sxs-lookup"><span data-stu-id="766d8-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="766d8-135">用户仍然保持登录并转到常规模式。</span><span class="sxs-lookup"><span data-stu-id="766d8-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766d8-136">用户新登录</span><span class="sxs-lookup"><span data-stu-id="766d8-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="766d8-137">用户可在恢复能力模式下登录主池。</span><span class="sxs-lookup"><span data-stu-id="766d8-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="766d8-138">用户可在常规模式下登录原始主池。</span><span class="sxs-lookup"><span data-stu-id="766d8-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="766d8-139">受影响用户组织的正在进行的会议</span><span class="sxs-lookup"><span data-stu-id="766d8-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="766d8-p109">将终止所有形式的会议。将显示“重新加入”按钮，但在受影响用户处于恢复能力模式时任何用户均无法重新加入。</span><span class="sxs-lookup"><span data-stu-id="766d8-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="766d8-p110">所有形式的会议现在可以正常进行。每个参与者需要单击才能重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="766d8-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766d8-144">不受影响用户组织的正在进行的会议</span><span class="sxs-lookup"><span data-stu-id="766d8-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="766d8-p111">会议将继续，受影响用户可留在会议中。受影响用户将被限制为仅可执行其在恢复能力模式下可执行的操作。</span><span class="sxs-lookup"><span data-stu-id="766d8-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="766d8-147">会议将继续，受影响用户可留在会议中，所有形式的会议可在用户退出恢复能力模式后正常进行。</span><span class="sxs-lookup"><span data-stu-id="766d8-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="766d8-148">安排或修改计划的会议，创建临时会议</span><span class="sxs-lookup"><span data-stu-id="766d8-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="766d8-149">当用户处于恢复能力模式时无法实现。</span><span class="sxs-lookup"><span data-stu-id="766d8-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="766d8-150">所有形式的会议均可实现。</span><span class="sxs-lookup"><span data-stu-id="766d8-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766d8-151">同一池中的其他用户可看见的状态</span><span class="sxs-lookup"><span data-stu-id="766d8-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="766d8-152">当用户在恢复能力模式期间登录备份池时状态未知。</span><span class="sxs-lookup"><span data-stu-id="766d8-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="766d8-153">显示用户设置的最后状态，并且现在将会反映状态更改。</span><span class="sxs-lookup"><span data-stu-id="766d8-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="766d8-154">联系人列表和通讯簿服务可用性</span><span class="sxs-lookup"><span data-stu-id="766d8-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="766d8-155">不可用</span><span class="sxs-lookup"><span data-stu-id="766d8-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="766d8-156">可用</span><span class="sxs-lookup"><span data-stu-id="766d8-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766d8-157">所有对等会话和形式</span><span class="sxs-lookup"><span data-stu-id="766d8-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="766d8-158">可用</span><span class="sxs-lookup"><span data-stu-id="766d8-158">Available</span></span></p></td>
<td><p><span data-ttu-id="766d8-159">可用</span><span class="sxs-lookup"><span data-stu-id="766d8-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="766d8-160">在其他池的故障回复期间位于不受影响池的用户的用户体验</span><span class="sxs-lookup"><span data-stu-id="766d8-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="766d8-161">用户任务</span><span class="sxs-lookup"><span data-stu-id="766d8-161">User task</span></span></th>
<th><span data-ttu-id="766d8-162">故障回复期间</span><span class="sxs-lookup"><span data-stu-id="766d8-162">During failback</span></span></th>
<th><span data-ttu-id="766d8-163">故障回复完成后</span><span class="sxs-lookup"><span data-stu-id="766d8-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="766d8-164">查看受影响用户的状态</span><span class="sxs-lookup"><span data-stu-id="766d8-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="766d8-165">显示受影响用户设置的最后状态。</span><span class="sxs-lookup"><span data-stu-id="766d8-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="766d8-p112">正常工作。不受影响的用户可看到受影响用户进行的更新。</span><span class="sxs-lookup"><span data-stu-id="766d8-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766d8-168">受影响用户组织的正在进行的会议</span><span class="sxs-lookup"><span data-stu-id="766d8-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="766d8-169">将终止所有形式的会议。</span><span class="sxs-lookup"><span data-stu-id="766d8-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="766d8-p113">所有形式的会议现在可以正常进行。每个参与者需要单击才能重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="766d8-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="766d8-172">不受影响用户组织的正在进行的会议</span><span class="sxs-lookup"><span data-stu-id="766d8-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="766d8-173">会议将继续，并且受影响用户可留在会议中，所有形式的会议都将正常进行。</span><span class="sxs-lookup"><span data-stu-id="766d8-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="766d8-174">会议将继续，并且受影响用户可留在会议中，所有形式的会议都将正常进行。</span><span class="sxs-lookup"><span data-stu-id="766d8-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766d8-175">所有对等会话和形式</span><span class="sxs-lookup"><span data-stu-id="766d8-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="766d8-176">可用</span><span class="sxs-lookup"><span data-stu-id="766d8-176">Available</span></span></p></td>
<td><p><span data-ttu-id="766d8-177">可用</span><span class="sxs-lookup"><span data-stu-id="766d8-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

