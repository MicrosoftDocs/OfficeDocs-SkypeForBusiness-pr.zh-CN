---
title: Lync Server 2013：安装和配置观察程序节点
description: Lync Server 2013：安装和配置观察程序节点。
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
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573998"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="c6cc1-103">在 Lync Server 2013 中安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="c6cc1-103">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6cc1-104">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="c6cc1-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="c6cc1-105">*观察程序节点* 是定期运行 Lync Server 合成事务的计算机。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-105">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="c6cc1-106">*综合事务* 是一种 Windows PowerShell cmdlet，用于验证关键最终用户方案（如登录系统的能力或 exchange 即时消息的功能）是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-106">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="c6cc1-107">对于 Lync Server 2013，System Center Operations Manager 可以运行下表中所示的综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-107">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="c6cc1-108">下表中显示了三种不同的综合事务类型：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-108">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="c6cc1-109">**默认值**。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-109">**Default**.</span></span> <span data-ttu-id="c6cc1-110">这些是默认情况下观察程序节点将运行的综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-110">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="c6cc1-111">创建新的观察程序节点时，您将具有指定此节点将运行的综合事务的选项。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-111">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="c6cc1-112"> (**new-cswatchernodeconfiguration** cmdlet 使用的测试参数的用途。 ) 如果在创建观察程序节点时不使用测试参数，它将自动运行所有默认的综合事务，并且不会运行任何非默认的综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-112">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="c6cc1-113">这意味着，例如，观察程序节点将配置为运行 Test-CsAddressBookService 测试，但不会配置为运行 Test-CsExumConnectivity 测试。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-113">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="c6cc1-114">**非默认值**。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-114">**Non-default**.</span></span> <span data-ttu-id="c6cc1-115">顾名思义，非默认综合事务是默认情况下观察程序节点不会运行的测试。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-115">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="c6cc1-116">但是，可启用观察程序节点运行任何非默认综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-116">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="c6cc1-117">您可在创建观察程序节点时或在创建后的任何时间执行此操作（使用 **New-CsWatcherNodeConfiguration** cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-117">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="c6cc1-118">许多非默认综合事务需要额外的设置步骤。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-118">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="c6cc1-119">有关详细信息，请参阅 [Lync Server 2013 中的综合事务的特殊设置说明](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-119">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="c6cc1-120">**扩展**。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-120">**Extended**.</span></span> <span data-ttu-id="c6cc1-121">扩展测试是特殊类型的非默认综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-121">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="c6cc1-122">与其他综合事务不同，扩展测试可在每次通过的情况下运行多次。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-122">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="c6cc1-123">这在验证一个池的多个公用电话交换网 (PSTN) 语音路由等行为时十分有用。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-123">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="c6cc1-124">此类测试可通过向观察程序节点添加多个扩展测试的实例来配置。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-124">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="c6cc1-125">有关将其他综合事务添加到观察程序节点的过程的详细信息，请参阅 [在 Lync Server 2013 中管理观察程序节点](lync-server-2013-managing-watcher-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-125">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="c6cc1-126">您可以使用 Lync Server 命令行管理程序从观察程序节点中删除综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-126">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="c6cc1-127">可用于观察程序节点的综合事务包括：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-127">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6cc1-128">Cmdlet 名称（测试名称）</span><span class="sxs-lookup"><span data-stu-id="c6cc1-128">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="c6cc1-129">说明</span><span class="sxs-lookup"><span data-stu-id="c6cc1-129">Description</span></span></th>
<th><span data-ttu-id="c6cc1-130">综合事务类型</span><span class="sxs-lookup"><span data-stu-id="c6cc1-130">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-131">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-131">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-132">确保用户能够查找不在其联系人列表内的用户。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-132">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-133">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-133">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-134">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-134">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-135">确保用户能够通过 HTTP 查找不在其联系人列表内的用户。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-135">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-136">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-136">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-137">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-137">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-138">确保用户能够发送对等即时消息。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-138">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-139">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-139">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-140">Test-CsP2PAV (P2PAV) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-140">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-141">确保用户能够发出对等音频呼叫（仅信号）。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-141">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-142">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-142">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-143">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-143">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-144">确保用户能够查看其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-144">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-145">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-145">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-146">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-146">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-147">确保用户能够登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-147">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-148">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-148">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-149">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-149">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-150">不与 Lync Server 2013 的本地版本一起使用</span><span class="sxs-lookup"><span data-stu-id="c6cc1-150">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-151">扩展</span><span class="sxs-lookup"><span data-stu-id="c6cc1-151">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-152">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="c6cc1-152">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-153">确保用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-153">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-154">Non-default，Extended</span><span class="sxs-lookup"><span data-stu-id="c6cc1-154">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-155">Test-CsAVConference (AvConference) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-155">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-156">确保用户能够创建和参与音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-156">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-157">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-157">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-159">确保 A/V 边缘服务器能够接受对等呼叫和会议呼叫的连接。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-159">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-160">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-160">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-161">Test-CsDataConference (DataConference) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-161">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-162">确保用户可参与数据协作会议（包含白板和投票等活动的联机会议）。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-162">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-163">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-163">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-164">Test-CsExumConnectivity (ExumConnectivity) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-164">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-165">确认用户可以连接到 Exchange 统一消息 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-165">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-166">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-166">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-167">Test-CsGroupIM (GroupIM) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-167">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-168">确保用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-168">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-169">默认值</span><span class="sxs-lookup"><span data-stu-id="c6cc1-169">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-170">Test-CsGroupIM – TestJoinLauncher (JoinLauncher) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-170">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-171">确保用户能够创建会议并能通过 Web 地址链接加入计划的会议。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-171">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-172">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-172">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-173">Test-CsMCXP2PIM (MCXP2PIM) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-173">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-174">确保移动设备用户能够注册和发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-174">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-175">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-175">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-176">Test-CsPersistentChatMessage (PersistentChatMessage) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-177">确认用户可以使用持久聊天服务交换邮件。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-177">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-178">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-178">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-179">Test-CsUnifiedContactStore (UnifiedContactStore) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-180">确保可通过统一的联系人存储库访问用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-180">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="c6cc1-181">统一联系人存储为用户提供了一种方法来维护一组可通过 Lync 2013、Outlook 和/或 Outlook Web Access 访问的联系人。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-181">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-182">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-182">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-183">Test-CsXmppIM (XmppIM) </span><span class="sxs-lookup"><span data-stu-id="c6cc1-183">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-184">确保可通过 XMPP（可扩展消息传递和状态协议）网关发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-184">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-185">非默认</span><span class="sxs-lookup"><span data-stu-id="c6cc1-185">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6cc1-186">您无需安装观察程序节点即可使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-186">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="c6cc1-187">如果不安装这些节点，您仍可以在出现问题时从 Lync Server 2013 组件获取实时警报。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-187">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="c6cc1-188"> (组件和用户管理包不使用观察程序节点。 ) 但是，如果要使用活动监视管理包监视端到端方案，则需要观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-188">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6cc1-189">管理员还可手动运行综合事务，无需使用或安装 Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-189">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="c6cc1-190">有关各种 Test-Cs cmdlet 的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlet 索引</A>。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-190">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="c6cc1-191">综合事务可能使用大量计算机内存和处理器时间，具体取决于您的部署规模。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-191">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="c6cc1-192">为此，建议您使用专用计算机作为观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-192">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="c6cc1-193">例如，不应将前端服务器配置为充当观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-193">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="c6cc1-194">观察程序节点应满足以下硬件规范：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-194">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6cc1-195">旧版 Microsoft Lync Server 2010 观察程序节点不能与 Lync Server 2013 观察程序节点在同一台计算机上并置。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-195">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="c6cc1-196">这是因为 Lync Server 2010 和 Lync Server 2013 的核心系统文件不能安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-196">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="c6cc1-197">但是，Lync Server 2013 观察程序节点可以同时监视 Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-197">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="c6cc1-198">这两个产品版本上均支持默认的综合事务。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-198">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="c6cc1-199">Lync Server 2013 观察程序节点可以部署在企业内部或外部，以帮助验证：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-199">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="c6cc1-200">至企业内部用户的池的连接。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-200">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="c6cc1-201">通过在企业外部工作的远程用户的外围网络的连接。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-201">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="c6cc1-202">至分支机构装置的连接。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-202">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="c6cc1-203">在企业内部和通过外围网络连接到 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-203">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="c6cc1-204">企业内部和企业外部有不同的身份验证选项可用以帮助管理。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-204">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="c6cc1-205">有关详细信息，请参阅 [将观察程序节点配置为在 Lync Server 2013 中运行综合事务](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-205">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="c6cc1-206">若要将计算机配置为充当观察程序节点，必须在安装 System Center Operations Manager 并导入 Lync Server 2013 管理包后完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-206">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="c6cc1-207">在安装 Lync Server 2013 core 文件和 System Center agent 文件之前，还应确保观察程序节点计算机满足安装 Lync Server 2013 的所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-207">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="c6cc1-208">此外，观察程序节点计算机还应安装下列项：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-208">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6cc1-209">硬件组件</span><span class="sxs-lookup"><span data-stu-id="c6cc1-209">Hardware component</span></span></th>
<th><span data-ttu-id="c6cc1-210">最低要求</span><span class="sxs-lookup"><span data-stu-id="c6cc1-210">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-211">CPU</span><span class="sxs-lookup"><span data-stu-id="c6cc1-211">CPU</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-212">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-212">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6cc1-213">64位处理器、四核、2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="c6cc1-213">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="c6cc1-214">64位双处理器、双核、2.33 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="c6cc1-214">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6cc1-215">内存</span><span class="sxs-lookup"><span data-stu-id="c6cc1-215">Memory</span></span></p></td>
<td><p><span data-ttu-id="c6cc1-216">8 GB</span><span class="sxs-lookup"><span data-stu-id="c6cc1-216">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6cc1-217">网络操作系统</span><span class="sxs-lookup"><span data-stu-id="c6cc1-217">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c6cc1-218">1个网络适配器 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="c6cc1-218">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="c6cc1-219">Windows Server 2008 R2、Windows Server 2012 或</span><span class="sxs-lookup"><span data-stu-id="c6cc1-219">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="c6cc1-220">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c6cc1-220">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="c6cc1-221">完整版的 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-221">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="c6cc1-222">Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-222">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="c6cc1-223">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-223">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="c6cc1-224">只要满足所有这些先决条件，就能通过下列方式配置观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="c6cc1-224">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="c6cc1-225">在观察程序节点计算机上安装 Lync Server 2013 core 文件。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-225">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="c6cc1-226">在观察程序节点计算机上安装 System Center Operations Manager 代理。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-226">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="c6cc1-227">运行 Watchernode.msi 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-227">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="c6cc1-228">使用 **CsWatcherNodeConfiguration** cmdlet 配置观察程序节点要使用的测试用户。</span><span class="sxs-lookup"><span data-stu-id="c6cc1-228">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

