---
title: Lync Server 2013：安装和配置观察程序节点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89465227e351da3c69116201efe5ee4eab89eca4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="98c19-102">在 Lync Server 2013 中安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="98c19-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c19-103">_**主题上次修改时间：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="98c19-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="98c19-104">*观察程序节点*是定期运行 Lync Server 合成事务的计算机。</span><span class="sxs-lookup"><span data-stu-id="98c19-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="98c19-105">*合成事务*是验证关键最终用户方案（如登录系统或交换即时消息的功能）的 Windows PowerShell cmdlet 是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="98c19-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="98c19-106">对于 Lync Server 2013，System Center Operations Manager 可以运行下表中所示的合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="98c19-107">表中显示三种不同的合成事务类型：</span><span class="sxs-lookup"><span data-stu-id="98c19-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="98c19-108">**默认值**。</span><span class="sxs-lookup"><span data-stu-id="98c19-108">**Default**.</span></span> <span data-ttu-id="98c19-109">这些是观察程序节点默认将运行的合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="98c19-110">当创建新的观察程序节点时，可以选择指定节点将运行的合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="98c19-111">（这是**CsWatcherNodeConfiguration** cmdlet 使用的测试参数的用途。）如果在创建观察程序节点时未使用 "测试" 参数，则它将自动运行所有默认的合成事务，并且不会运行任何非默认的合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="98c19-112">例如，这意味着观察程序节点将配置为运行 CsAddressBookService 测试，但不会配置为运行测试 CsExumConnectivity 测试。</span><span class="sxs-lookup"><span data-stu-id="98c19-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="98c19-113">**非默认值**。</span><span class="sxs-lookup"><span data-stu-id="98c19-113">**Non-default**.</span></span> <span data-ttu-id="98c19-114">顾名思义，非默认合成事务是测试观察程序节点是否默认不运行。</span><span class="sxs-lookup"><span data-stu-id="98c19-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="98c19-115">但是，可以启用观察程序节点来运行任何非默认的合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="98c19-116">你可以在创建观察程序节点时执行此操作（使用**CsWatcherNodeConfiguration** cmdlet），或者在此后的任何时间执行此操作。</span><span class="sxs-lookup"><span data-stu-id="98c19-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="98c19-117">许多非默认的合成事务都需要额外的设置步骤。</span><span class="sxs-lookup"><span data-stu-id="98c19-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="98c19-118">有关详细信息，请参阅[Lync Server 2013 中的综合事务的特殊设置说明](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="98c19-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="98c19-119">**扩展**。</span><span class="sxs-lookup"><span data-stu-id="98c19-119">**Extended**.</span></span> <span data-ttu-id="98c19-120">扩展测试是一种特殊类型的非默认综合事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="98c19-121">与其他合成事务不同，扩展测试可以在每次传递期间运行多次。</span><span class="sxs-lookup"><span data-stu-id="98c19-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="98c19-122">这在验证一个池的多个公共交换电话网络（PSTN）语音路由等行为时非常有用。</span><span class="sxs-lookup"><span data-stu-id="98c19-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="98c19-123">只需将一个扩展测试的多个实例添加到观察程序节点即可配置此操作。</span><span class="sxs-lookup"><span data-stu-id="98c19-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="98c19-124">有关将其他合成事务添加到观察程序节点的过程的详细信息，请参阅[在 Lync Server 2013 中管理观察程序节点](lync-server-2013-managing-watcher-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="98c19-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="98c19-125">你可以使用 Lync Server Management Shell 从观察程序节点中删除合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="98c19-126">可用于观察程序节点的综合事务包括：</span><span class="sxs-lookup"><span data-stu-id="98c19-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98c19-127">Cmdlet 名称（测试名称）</span><span class="sxs-lookup"><span data-stu-id="98c19-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="98c19-128">描述</span><span class="sxs-lookup"><span data-stu-id="98c19-128">Description</span></span></th>
<th><span data-ttu-id="98c19-129">综合交易记录类型</span><span class="sxs-lookup"><span data-stu-id="98c19-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98c19-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="98c19-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="98c19-131">确认用户能够查找不在其联系人列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="98c19-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="98c19-132">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="98c19-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="98c19-134">确认用户能够通过 HTTP 查找不在联系人列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="98c19-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="98c19-135">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-136">Test-CsIM （IM）</span><span class="sxs-lookup"><span data-stu-id="98c19-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="98c19-137">确认用户能够发送对等即时消息。</span><span class="sxs-lookup"><span data-stu-id="98c19-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="98c19-138">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="98c19-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="98c19-140">确认用户能够发出对等音频呼叫（仅信号）。</span><span class="sxs-lookup"><span data-stu-id="98c19-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="98c19-141">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="98c19-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="98c19-143">确认用户能够查看其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="98c19-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="98c19-144">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="98c19-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="98c19-146">确认用户可以登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="98c19-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="98c19-147">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-148">Test-CsAudioConferencingProvider （ACP）</span><span class="sxs-lookup"><span data-stu-id="98c19-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="98c19-149">不与 Lync Server 2013 的本地版本一起使用</span><span class="sxs-lookup"><span data-stu-id="98c19-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="98c19-150">可扩展</span><span class="sxs-lookup"><span data-stu-id="98c19-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-151">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="98c19-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="98c19-152">确认用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。</span><span class="sxs-lookup"><span data-stu-id="98c19-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="98c19-153">非默认，扩展</span><span class="sxs-lookup"><span data-stu-id="98c19-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="98c19-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="98c19-155">确认用户能够创建和参与音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="98c19-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="98c19-156">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="98c19-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="98c19-158">确认 A/V 边缘服务器能够接受对等呼叫和电话会议的连接。</span><span class="sxs-lookup"><span data-stu-id="98c19-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="98c19-159">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-160">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="98c19-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="98c19-161">确认用户可以参与数据协作会议（包括活动（如白板和投票）的联机会议。</span><span class="sxs-lookup"><span data-stu-id="98c19-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="98c19-162">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="98c19-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="98c19-164">确认用户可以连接到 Exchange 统一消息（UM）。</span><span class="sxs-lookup"><span data-stu-id="98c19-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="98c19-165">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-166">Test-CsGroupIM （GroupIM）</span><span class="sxs-lookup"><span data-stu-id="98c19-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="98c19-167">确认用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="98c19-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="98c19-168">默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="98c19-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="98c19-170">确认用户能够通过 web 地址链接创建和加入计划会议。</span><span class="sxs-lookup"><span data-stu-id="98c19-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="98c19-171">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="98c19-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="98c19-173">确认移动设备用户能够注册和发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="98c19-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="98c19-174">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="98c19-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="98c19-176">确认用户可使用持久聊天服务交换消息。</span><span class="sxs-lookup"><span data-stu-id="98c19-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="98c19-177">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="98c19-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="98c19-179">确认可通过统一的联系人存储库访问用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="98c19-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="98c19-180">"统一联系人存储" 为用户提供了一种维护单个联系人集的方式，可使用 Lync 2013、Outlook 和/或 Outlook Web Access 进行访问。</span><span class="sxs-lookup"><span data-stu-id="98c19-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="98c19-181">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="98c19-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="98c19-183">确认即时消息可以通过 XMPP （可扩展消息和状态协议）网关发送。</span><span class="sxs-lookup"><span data-stu-id="98c19-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="98c19-184">非默认值</span><span class="sxs-lookup"><span data-stu-id="98c19-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="98c19-185">无需安装观察程序节点即可使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="98c19-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="98c19-186">如果不安装这些节点，则仍可在出现问题时从 Lync Server 2013 组件获取实时警报。</span><span class="sxs-lookup"><span data-stu-id="98c19-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="98c19-187">（组件和用户管理包不使用观察程序节点。）但是，如果你希望通过使用活动的监视管理包监视端到端方案，则需要观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="98c19-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98c19-188">管理员还可以手动运行综合事务，而无需使用或安装 Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="98c19-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="98c19-189">有关各种 Test-Cs cmdlet 的详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlet 索引</A>。</span><span class="sxs-lookup"><span data-stu-id="98c19-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="98c19-190">综合事务可能会占用大量计算机内存和处理器时间，具体取决于你的部署的大小。</span><span class="sxs-lookup"><span data-stu-id="98c19-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="98c19-191">因此，我们建议你将专用计算机用作观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="98c19-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="98c19-192">例如，不应将前端服务器配置为充当观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="98c19-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="98c19-193">观察程序节点应满足下列硬件规范：</span><span class="sxs-lookup"><span data-stu-id="98c19-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98c19-194">旧版 Microsoft Lync Server 2010 观察程序节点不能与 Lync Server 2013 观察程序节点在同一台计算机上 collocated。</span><span class="sxs-lookup"><span data-stu-id="98c19-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="98c19-195">这是因为 Lync Server 2010 和 Lync Server 2013 的核心系统文件不能安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="98c19-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="98c19-196">但是，Lync Server 2013 观察程序节点可以同时监视 Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="98c19-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="98c19-197">这两个产品版本均支持默认的合成事务。</span><span class="sxs-lookup"><span data-stu-id="98c19-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="98c19-198">Lync Server 2013 观察程序节点可以部署在企业内部或外部，以帮助验证：</span><span class="sxs-lookup"><span data-stu-id="98c19-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="98c19-199">至企业内部用户的池的连接。</span><span class="sxs-lookup"><span data-stu-id="98c19-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="98c19-200">通过外围网络连接到在企业外部工作的远程用户的连接。</span><span class="sxs-lookup"><span data-stu-id="98c19-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="98c19-201">至分支机构装置的连接。</span><span class="sxs-lookup"><span data-stu-id="98c19-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="98c19-202">在企业内和通过外围网络连接到 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="98c19-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="98c19-203">在企业内部和外部提供不同的身份验证选项，可帮助简化管理。</span><span class="sxs-lookup"><span data-stu-id="98c19-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="98c19-204">有关详细信息，请参阅[在 Lync Server 2013 中配置观察程序节点以运行合成事务](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="98c19-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="98c19-205">若要将计算机配置为充当观察程序节点，必须在安装 System Center Operations Manager 并导入 Lync Server 2013 管理包之后完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="98c19-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="98c19-206">在安装 Lync Server 2013 core 文件和 System Center agent 文件之前，还应确保观察程序节点计算机满足安装 Lync Server 2013 的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="98c19-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="98c19-207">此外，观察程序节点计算机还应安装下列项目：</span><span class="sxs-lookup"><span data-stu-id="98c19-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98c19-208">硬件组件</span><span class="sxs-lookup"><span data-stu-id="98c19-208">Hardware component</span></span></th>
<th><span data-ttu-id="98c19-209">最低要求</span><span class="sxs-lookup"><span data-stu-id="98c19-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98c19-210">CPU</span><span class="sxs-lookup"><span data-stu-id="98c19-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="98c19-211">以下两种之一：</span><span class="sxs-lookup"><span data-stu-id="98c19-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="98c19-212">64 位处理器、四核、2.33 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="98c19-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="98c19-213">64 位 2 路处理器、双核、2.33 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="98c19-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c19-214">内存</span><span class="sxs-lookup"><span data-stu-id="98c19-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="98c19-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="98c19-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c19-216">网络操作系统</span><span class="sxs-lookup"><span data-stu-id="98c19-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="98c19-217">1个网络适配器 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="98c19-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="98c19-218">Windows Server 2008 R2、Windows Server 2012 或</span><span class="sxs-lookup"><span data-stu-id="98c19-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="98c19-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="98c19-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="98c19-220">.NET Framework 4.5 的完整版本。</span><span class="sxs-lookup"><span data-stu-id="98c19-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="98c19-221">Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="98c19-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="98c19-222">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="98c19-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="98c19-223">一旦满足所有这些先决条件，您就可以通过以下方式配置观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="98c19-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="98c19-224">在观察程序节点计算机上安装 Lync Server 2013 core 文件。</span><span class="sxs-lookup"><span data-stu-id="98c19-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="98c19-225">在观察程序节点计算机上安装 System Center Operations Manager 代理。</span><span class="sxs-lookup"><span data-stu-id="98c19-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="98c19-226">运行 Watchernode 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="98c19-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="98c19-227">使用**CsWatcherNodeConfiguration** cmdlet 配置要由观察程序节点使用的测试用户。</span><span class="sxs-lookup"><span data-stu-id="98c19-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

