---
title: 安装和配置观察程序节点
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 摘要： 安装和配置观察程序节点的 Skype Business Server 综合事务。
ms.openlocfilehash: 6719826515954290f30eac272f638b846f45142a
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "25375984"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="26e5a-103">安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="26e5a-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="26e5a-104">**摘要：** 安装和配置观察程序节点的 Skype Business Server 综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="26e5a-105">观察程序节点是定期运行的业务服务器综合事务的 Skype 的计算机。</span><span class="sxs-lookup"><span data-stu-id="26e5a-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="26e5a-106">综合事务是验证关键用户方案（如能否登录或交换即时消息）是否正常起作用的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26e5a-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="26e5a-107">对于业务服务器 2015年的 Skype，System Center Operations Manager 可以运行下表中，其中包括三种综合事务类型中所示的综合事务：</span><span class="sxs-lookup"><span data-stu-id="26e5a-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="26e5a-108">**默认值**默认情况下运行观察程序节点的综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="26e5a-109">创建新的观察程序节点时，可以指定该节点将运行哪些综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="26e5a-110">（这是通过 New-cswatchernodeconfiguration cmdlet 使用的测试参数的用途）。如果您不使用 Tests 参数创建观察程序节点时，它将自动运行所有默认综合事务，并将不会都运行任何非默认综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="26e5a-111">这意味着，例如，观察程序节点将配置为运行 Test-CsAddressBookService 测试，但不会配置为运行 Test-CsExumConnectivity 测试。</span><span class="sxs-lookup"><span data-stu-id="26e5a-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="26e5a-112">**非默认**默认情况下不运行观察程序节点的测试。</span><span class="sxs-lookup"><span data-stu-id="26e5a-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="26e5a-113">（有关详细信息，请参阅默认类型的说明）。但是，可以启用观察程序节点要运行任何非默认综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="26e5a-114">当您创建观察程序节点 （通过使用 New-cswatchernodeconfiguration cmdlet），或已创建观察程序节点后的随时时，您可以这样做。</span><span class="sxs-lookup"><span data-stu-id="26e5a-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="26e5a-115">请注意，多个非默认综合事务需要额外的安装步骤。</span><span class="sxs-lookup"><span data-stu-id="26e5a-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="26e5a-116">有关这些步骤的详细信息，请参阅综合事务的特殊设置说明。</span><span class="sxs-lookup"><span data-stu-id="26e5a-116">For details about these steps, see Special Setup Instructions for Synthetic Transactions.</span></span> <span data-ttu-id="26e5a-117">有关这些步骤的详细信息，请参阅[综合事务的特殊设置说明](test-users-and-settings.md#special_synthetictrans)。</span><span class="sxs-lookup"><span data-stu-id="26e5a-117">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions ](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="26e5a-118">**扩展**一种非默认综合事务的特殊类型。</span><span class="sxs-lookup"><span data-stu-id="26e5a-118">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="26e5a-119">与其他综合事务，不同扩展测试可多次运行在每个过程。</span><span class="sxs-lookup"><span data-stu-id="26e5a-119">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="26e5a-120">验证行为，例如，池中的多个公用电话交换网 (pstn) 语音路由时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="26e5a-120">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="26e5a-121">您可以配置此只需通过观察程序节点到添加的扩展测试的多个实例。</span><span class="sxs-lookup"><span data-stu-id="26e5a-121">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="26e5a-122">有关向观察程序节点添加其他综合事务的过程的详细信息，请参阅[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)。</span><span class="sxs-lookup"><span data-stu-id="26e5a-122">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="26e5a-123">您可以使用 Skype 的业务 Server 命令行管理程序以删除观察程序节点的综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-123">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="26e5a-124">可用于观察程序节点的综合事务包括：</span><span class="sxs-lookup"><span data-stu-id="26e5a-124">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="26e5a-125">**Cmdlet 名称（测试名称）**</span><span class="sxs-lookup"><span data-stu-id="26e5a-125">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="26e5a-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="26e5a-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26e5a-127">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="26e5a-127">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="26e5a-128">确保用户能够查找不在其联系人列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="26e5a-128">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="26e5a-129">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="26e5a-129">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="26e5a-130">确保用户能够查找不在其联系人列表中通过 HTTP 的用户。</span><span class="sxs-lookup"><span data-stu-id="26e5a-130">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="26e5a-131">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="26e5a-131">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="26e5a-132">确认用户能够创建和参与音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="26e5a-132">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="26e5a-133">Test-CsGroupIM (IM Conferencing)</span><span class="sxs-lookup"><span data-stu-id="26e5a-133">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="26e5a-134">确认用户能够在会议中发送即时消息并且可参与三个或三个以上的人员组成的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="26e5a-134">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="26e5a-135">Test-CsIM (P2P IM)</span><span class="sxs-lookup"><span data-stu-id="26e5a-135">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="26e5a-136">确认用户能够发送对等即时消息。</span><span class="sxs-lookup"><span data-stu-id="26e5a-136">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="26e5a-137">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="26e5a-137">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="26e5a-138">确认用户能够发出对等音频呼叫（仅信号）。</span><span class="sxs-lookup"><span data-stu-id="26e5a-138">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="26e5a-139">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="26e5a-139">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="26e5a-140">确保用户能够查看其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="26e5a-140">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="26e5a-141">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="26e5a-141">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="26e5a-142">确保用户能够登录到 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-142">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="26e5a-143">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="26e5a-143">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="26e5a-144">确认用户能够向企业外部人员发出呼叫以及接收其发出的呼叫（PSTN 号码）。</span><span class="sxs-lookup"><span data-stu-id="26e5a-144">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="26e5a-145">Test-CsASConference (ASConference)</span><span class="sxs-lookup"><span data-stu-id="26e5a-145">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="26e5a-146">确认用户能够创建和参与应用程序共享会议。</span><span class="sxs-lookup"><span data-stu-id="26e5a-146">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="26e5a-147">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="26e5a-147">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="26e5a-148">确认音频视频边缘服务器能够接受对等呼叫和会议呼叫的连接。</span><span class="sxs-lookup"><span data-stu-id="26e5a-148">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="26e5a-149">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="26e5a-149">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="26e5a-150">确认用户可参与数据协作会议（包含白板和投票等活动的联机会议）。</span><span class="sxs-lookup"><span data-stu-id="26e5a-150">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="26e5a-151">Test-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="26e5a-151">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="26e5a-152">确认用户能够拨打电话号码加入会议。</span><span class="sxs-lookup"><span data-stu-id="26e5a-152">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="26e5a-153">Test-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="26e5a-153">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="26e5a-154">确认用户能够拨打电话号码加入会议。</span><span class="sxs-lookup"><span data-stu-id="26e5a-154">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="26e5a-155">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="26e5a-155">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="26e5a-156">确认用户可以连接到 Exchange 统一消息 (UM)。</span><span class="sxs-lookup"><span data-stu-id="26e5a-156">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="26e5a-157">Test-csgroupim TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="26e5a-157">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="26e5a-158">确认用户能够创建并加入计划的会议（通过 Web 地址链接）。</span><span class="sxs-lookup"><span data-stu-id="26e5a-158">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="26e5a-159">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="26e5a-159">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="26e5a-160">确认移动设备用户能够注册和发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="26e5a-160">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="26e5a-161">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="26e5a-161">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="26e5a-162">确认视频互操作服务器已启动，可以通过视频的 SIP 中继处理传入连接。</span><span class="sxs-lookup"><span data-stu-id="26e5a-162">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="26e5a-163">**注意：** MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="26e5a-163">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="26e5a-164">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="26e5a-164">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="26e5a-165">确认用户可使用持久聊天服务交换消息。</span><span class="sxs-lookup"><span data-stu-id="26e5a-165">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="26e5a-166">Test-CsUcwaConference (UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="26e5a-166">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="26e5a-167">确认用户可通过 Web 加入会议。</span><span class="sxs-lookup"><span data-stu-id="26e5a-167">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="26e5a-168">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="26e5a-168">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="26e5a-169">确认可通过统一的联系人存储库访问用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="26e5a-169">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="26e5a-170">统一联系人存储库提供了一种方法来维护一组可访问的业务服务器 2015年、 Outlook 消息和协作客户端和/或 Outlook Web Access 使用 Skype 联系人的用户。</span><span class="sxs-lookup"><span data-stu-id="26e5a-170">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="26e5a-171">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="26e5a-171">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="26e5a-172">确认可通过可扩展消息传递和状态协议 (XMPP) 网关发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="26e5a-172">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="26e5a-173">XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-173">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="26e5a-174">不需要安装观察程序节点以使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="26e5a-174">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="26e5a-175">如果未安装这些节点，您仍可以获取实时通知从 Skype 业务服务器 2015年组件时出现问题。</span><span class="sxs-lookup"><span data-stu-id="26e5a-175">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="26e5a-176">（的组件和用户管理包不使用观察程序节点。）但是，观察程序节点是必需的如果您想要使用的主动监控管理包监视的端到端方案。</span><span class="sxs-lookup"><span data-stu-id="26e5a-176">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26e5a-177">管理员还可手动运行综合事务，而无需使用或安装 Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="26e5a-177">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="26e5a-178">根据您 Skype Business Server 部署的大小，综合事务可以使用大量的计算机内存和处理器时间。</span><span class="sxs-lookup"><span data-stu-id="26e5a-178">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="26e5a-179">因此，建议您使用专用计算机作为观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="26e5a-179">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="26e5a-180">例如，不应该配置 Business Server 前端服务器充当观察程序节点的 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-180">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="26e5a-181">观察程序节点应满足基本硬件要求与任何其他计算机中的企业服务器拓扑您 Skype 相同。</span><span class="sxs-lookup"><span data-stu-id="26e5a-181">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="26e5a-182">因为不能在同一台计算机上安装 Lync Server 2013 和业务服务器 2015年的 Skype 的核心系统文件，旧的 Lync Server 2013 观察程序节点不能并置为 Skype 业务服务器 2015年观察程序节点的相同计算机上。</span><span class="sxs-lookup"><span data-stu-id="26e5a-182">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="26e5a-183">但是，业务服务器 2015年观察程序节点的 Skype 可以同时监视 Skype 业务服务器 2015年和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="26e5a-183">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="26e5a-184">默认综合事务同时支持两种产品版本。</span><span class="sxs-lookup"><span data-stu-id="26e5a-184">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="26e5a-185">内部或外部企业以帮助验证，则可能部署 Lync Server 2013 观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="26e5a-185">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="26e5a-186">至企业内部用户的池的连接。</span><span class="sxs-lookup"><span data-stu-id="26e5a-186">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="26e5a-187">通过在企业外部工作的远程用户的外围网络的连接。</span><span class="sxs-lookup"><span data-stu-id="26e5a-187">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="26e5a-188">至分支机构装置的连接。</span><span class="sxs-lookup"><span data-stu-id="26e5a-188">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="26e5a-189">连接到 Lync Server 2013 企业内部和通过外围网络。</span><span class="sxs-lookup"><span data-stu-id="26e5a-189">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="26e5a-p110">为了帮助简化管理，企业内部和外部有不同的身份验证选项。有关详细信息，请参阅[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p110">To help simplify administration, different authentication options are available for inside and outside of the enterprise. For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="26e5a-192">为了将计算机配置为观察程序节点，必须先完成以下前提任务：</span><span class="sxs-lookup"><span data-stu-id="26e5a-192">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="26e5a-193">安装 System Center Operations Manager 和导入业务服务器 2015年管理包的 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-193">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="26e5a-194">您必须还首先验证观察程序节点计算机满足所有先决条件安装业务服务器 2015 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-194">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="26e5a-195">在观察程序节点上安装以下项目：</span><span class="sxs-lookup"><span data-stu-id="26e5a-195">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="26e5a-196">完整版的.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="26e5a-196">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="26e5a-197">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="26e5a-197">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="26e5a-198">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="26e5a-198">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="26e5a-199">在满足先决条件后，可按下面的步骤配置观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="26e5a-199">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="26e5a-200">安装观察程序节点计算机上的业务服务器 2015年核心文件 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-200">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="26e5a-201">在观察程序节点计算机上安装 System Center Operations Manager 代理。</span><span class="sxs-lookup"><span data-stu-id="26e5a-201">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="26e5a-202">运行 Watchernode.msi 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="26e5a-202">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="26e5a-203">使用 **New-CsWatcherNodeConfiguration** cmdlet 配置观察程序节点要采用的测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26e5a-203">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="26e5a-204">安装 Skype for Business Server 2015 核心文件和 RTCLocal 数据库</span><span class="sxs-lookup"><span data-stu-id="26e5a-204">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="26e5a-205">若要安装的计算机上的业务服务器 2015年核心文件 Skype，完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="26e5a-205">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="26e5a-206">当您安装的核心文件时，将自动安装 RTCLocal 数据库。</span><span class="sxs-lookup"><span data-stu-id="26e5a-206">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="26e5a-207">请注意，您不需要观察程序节点上安装 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="26e5a-207">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="26e5a-208">SQL Server Express 将会自动安装。</span><span class="sxs-lookup"><span data-stu-id="26e5a-208">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="26e5a-209">安装 Business Server 2015 核心文件和 RTCLocal 数据库 Skype:</span><span class="sxs-lookup"><span data-stu-id="26e5a-209">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="26e5a-210">在观察程序节点计算机上，依次单击“开始”、“所有程序”和“附件”，再右键单击“命令提示符”，然后单击“以管理员身份运行”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-210">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="26e5a-211">在控制台窗口中，键入以下命令，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="26e5a-211">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="26e5a-212">确保输入您 Skype Business Server 安装程序文件的相应路径： D:\Setup.exe /BootstrapLocalMgmtTo 验证是否成功安装核心 Skype 业务服务器组件，单击**开始**，单击**所有程序**单击**业务服务器 2015年的 Skype**，，然后单击**业务 Server Management Shell 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="26e5a-212">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="26e5a-213">中的业务 Server 命令行管理程序 Skype，键入以下 Windows PowerShell 命令并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="26e5a-213">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="26e5a-214">首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="26e5a-214">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="26e5a-215">如果不返回出错的情况下运行该命令，可以假定 Skype 业务服务器安装已成功完成。</span><span class="sxs-lookup"><span data-stu-id="26e5a-215">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="26e5a-216">如果您的观察程序节点计算机位于您的外围网络内部，则可以运行以下命令来验证 Skype for Business Server 2015 的安装：</span><span class="sxs-lookup"><span data-stu-id="26e5a-216">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="26e5a-217">Get CsPinPolicyYou 会收到类似于以下，具体取决于数配置为在组织中使用的 PIN 策略的信息：</span><span class="sxs-lookup"><span data-stu-id="26e5a-217">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="26e5a-218">标识： 全局</span><span class="sxs-lookup"><span data-stu-id="26e5a-218">Identity : Global</span></span>
  
<span data-ttu-id="26e5a-219">说明：</span><span class="sxs-lookup"><span data-stu-id="26e5a-219">Description :</span></span>
  
<span data-ttu-id="26e5a-220">MinPasswordLength: 5</span><span class="sxs-lookup"><span data-stu-id="26e5a-220">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="26e5a-221">PINHistoryCount: 0</span><span class="sxs-lookup"><span data-stu-id="26e5a-221">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="26e5a-222">AllowCommonPatterns: False</span><span class="sxs-lookup"><span data-stu-id="26e5a-222">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="26e5a-223">PINLifetime: 0</span><span class="sxs-lookup"><span data-stu-id="26e5a-223">PINLifetime : 0</span></span>
  
<span data-ttu-id="26e5a-224">MaximumLogonAttempts :</span><span class="sxs-lookup"><span data-stu-id="26e5a-224">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="26e5a-225">如果看到有关 PIN 策略的信息，表明核心组件已安装成功。</span><span class="sxs-lookup"><span data-stu-id="26e5a-225">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="26e5a-226">在观察程序节点上安装 Operation Manager 代理文件</span><span class="sxs-lookup"><span data-stu-id="26e5a-226">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="26e5a-227">类似于业务服务器安装程序报告组件通知 Skype，业务服务器 2015年观察程序节点的 Skype 需要安装 System Center Operations Manager 代理文件。</span><span class="sxs-lookup"><span data-stu-id="26e5a-227">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="26e5a-228">这样的综合事务，要运行和通知要报告给 System Center Operations Manager 根管理服务器。</span><span class="sxs-lookup"><span data-stu-id="26e5a-228">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="26e5a-229">若要安装代理文件，请按照[配置将受监控的企业服务器计算机的 Skype](configure-computers-to-monitor.md)中列出的过程。</span><span class="sxs-lookup"><span data-stu-id="26e5a-229">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="26e5a-230">将观察程序节点配置为运行综合事务</span><span class="sxs-lookup"><span data-stu-id="26e5a-230">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="26e5a-231"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="26e5a-231"></span></span>

<span data-ttu-id="26e5a-232">安装了 System Center Operations Manager 代理文件后，您必须配置观察程序节点本身。</span><span class="sxs-lookup"><span data-stu-id="26e5a-232">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="26e5a-233">配置步骤将因观察程序节点计算机位于外围网络内部还是外部而有所不同。</span><span class="sxs-lookup"><span data-stu-id="26e5a-233">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="26e5a-234">配置观察程序节点时，还必须选择该节点要采用的身份验证方法类型。</span><span class="sxs-lookup"><span data-stu-id="26e5a-234">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="26e5a-235">Skype 的业务服务器 2015年让您能够选择两种身份验证方法之一： 受信任的服务器或凭据身份验证。</span><span class="sxs-lookup"><span data-stu-id="26e5a-235">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="26e5a-236">下表显示了这两种方法间的差异：</span><span class="sxs-lookup"><span data-stu-id="26e5a-236">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="26e5a-237">**说明**</span><span class="sxs-lookup"><span data-stu-id="26e5a-237">**Description**</span></span>|<span data-ttu-id="26e5a-238">**支持的位置**</span><span class="sxs-lookup"><span data-stu-id="26e5a-238">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26e5a-239">TrustedServer</span><span class="sxs-lookup"><span data-stu-id="26e5a-239">TrustedServer</span></span>  <br/> |<span data-ttu-id="26e5a-240">使用证书可模拟内部服务器并绕过身份验证质询。</span><span class="sxs-lookup"><span data-stu-id="26e5a-240">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="26e5a-241">这对于喜欢在每个观察程序节点管理单个证书而不是多个用户密码的管理员来说很有用。</span><span class="sxs-lookup"><span data-stu-id="26e5a-241">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="26e5a-242">企业内部。</span><span class="sxs-lookup"><span data-stu-id="26e5a-242">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="26e5a-243">采用这种方法时，观察程序节点必须与要监控的池位于同一个域中。</span><span class="sxs-lookup"><span data-stu-id="26e5a-243">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="26e5a-244">如果观察程序节点与池在不同的域中，请改用凭据身份验证。</span><span class="sxs-lookup"><span data-stu-id="26e5a-244">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="26e5a-245">Negotiate</span><span class="sxs-lookup"><span data-stu-id="26e5a-245">Negotiate</span></span>  <br/> |<span data-ttu-id="26e5a-246">将用户名和密码安全地存储在每个观察程序节点的 Windows 凭据管理器中。</span><span class="sxs-lookup"><span data-stu-id="26e5a-246">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="26e5a-247">此模式需要更多密码管理，但它是企业外部的观察程序节点的唯一选择。</span><span class="sxs-lookup"><span data-stu-id="26e5a-247">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="26e5a-248">不能将这些观察程序节点视为经过身份验证的受信任终结点。</span><span class="sxs-lookup"><span data-stu-id="26e5a-248">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="26e5a-249">企业外部。</span><span class="sxs-lookup"><span data-stu-id="26e5a-249">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="26e5a-250">企业内部。</span><span class="sxs-lookup"><span data-stu-id="26e5a-250">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="26e5a-251">配置观察程序节点以使用受信任的服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="26e5a-251">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="26e5a-252"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="26e5a-252"></span></span>

<span data-ttu-id="26e5a-253">如果观察程序节点计算机位于外围网络中，则使用受信任服务器身份验证可大大减少管理任务，只需维护单个证书即可，而无需使用大量用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="26e5a-253">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="26e5a-254">若要配置受信任服务器身份验证，必须先创建受信任应用程序池来承载观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="26e5a-254">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="26e5a-255">您已创建的受信任应用程序池后，然后必须在受信任应用程序以运行该观察程序节点配置综合事务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-255">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26e5a-256">受信任的应用程序是授予受信任的状态运行业务服务器 2015 Skype 的一部分，但不是内置一部分的产品的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26e5a-256">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="26e5a-257">受信任状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="26e5a-257">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="26e5a-258">若要创建受信任应用程序池，打开 Skype 业务 Server 命令行管理程序，并运行类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="26e5a-258">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="26e5a-259">有关上述命令中参数的详细信息，键入从业务 Server 命令行管理程序提示符 Skype 以下内容：</span><span class="sxs-lookup"><span data-stu-id="26e5a-259">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="26e5a-260">在创建受信任的应用程序池之后，就可使用 **New-CsTrustedApplication** cmdlet 和类似下面的命令，将观察程序节点计算机配置为，将综合事务作为受信任的应用程序来运行。</span><span class="sxs-lookup"><span data-stu-id="26e5a-260">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="26e5a-261">在完成上述命令并创建受信任的应用程序之后，请运行 **Enable-CsTopology** cmdlet，以确保更改生效：</span><span class="sxs-lookup"><span data-stu-id="26e5a-261">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```
Enable-CsTopology
```

<span data-ttu-id="26e5a-262">运行 Enable-CsTopology 后，重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="26e5a-262">After running Enable-CsTopology, restart the computer.</span></span>
  
<span data-ttu-id="26e5a-263">若要验证已创建新的受信任应用程序，在 Skype 的业务 Server 命令行管理程序提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="26e5a-263">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="26e5a-264">在观察程序节点上配置默认证书</span><span class="sxs-lookup"><span data-stu-id="26e5a-264">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="26e5a-265"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="26e5a-265"></span></span>

<span data-ttu-id="26e5a-266">使用 TrustedServer 身份验证每个观察程序节点必须使用适用于业务 Server 部署向导 Skype 分配一个默认证书。</span><span class="sxs-lookup"><span data-stu-id="26e5a-266">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="26e5a-267">若要分配默认证书：</span><span class="sxs-lookup"><span data-stu-id="26e5a-267">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="26e5a-268">单击开始、 单击所有程序、 都单击业务服务器 2015 Skype，然后都单击 Skype 业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="26e5a-268">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="26e5a-269">在业务 Server 部署向导的 Skype，单击安装或更新 Skype 业务 Server 系统，然后单击运行范畴请求、 安装或分配证书。</span><span class="sxs-lookup"><span data-stu-id="26e5a-269">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="26e5a-270">如果禁用“运行”按钮，则您可能需要先单击“安装本地配置存储”下方的“运行”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-270">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="26e5a-271">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="26e5a-271">Do one of the following:</span></span>
  
- <span data-ttu-id="26e5a-p122">如果您已有一个可用作默认证书的证书，请单击证书向导中的“默认”，然后单击“分配”。按照证书分配向导中的步骤分配此证书。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p122">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="26e5a-p123">如果您需要请求用作默认证书的证书，请单击“请求”，然后按照证书请求向导中的步骤进行操作以请求该证书。如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p123">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="26e5a-276">安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="26e5a-276">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="26e5a-277"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="26e5a-277"></span></span>

<span data-ttu-id="26e5a-278">您已重新启动观察程序节点计算机并配置证书之后，您必须运行 Watchernode.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="26e5a-278">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="26e5a-279">（必须运行 Watchernode.msi 的任何计算机上安装 Operations Manager 代理文件和业务服务器 2015年核心组件的 Skype。）</span><span class="sxs-lookup"><span data-stu-id="26e5a-279">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="26e5a-280">若要安装和配置观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="26e5a-280">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="26e5a-281">通过单击开始，单击所有程序、 Skype 的业务服务器 2015年，然后都单击的业务 Server Management Shell Skype 业务 Server 命令行管理程序打开 Skype。</span><span class="sxs-lookup"><span data-stu-id="26e5a-281">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="26e5a-282">在命令行管理程序中，键入以下命令，然后按 Enter（确保指定 Watchernode.msi 副本的实际路径）：</span><span class="sxs-lookup"><span data-stu-id="26e5a-282">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="26e5a-p125">您还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。打开命令窗口后，键入与上面的步骤 2 所示的相同命令。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p125">You can also run Watchernode.msi n from a command window. To open a command window, click Start, right-click Command Prompt, and then click Run as administrator. When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="26e5a-p126">在前面的命令中，名称/值对 Authentication=TrustedServer 区分大小写。必须完全按所示输入。例如，由于没有正确使用字母大小写，下面的命令将失败：</span><span class="sxs-lookup"><span data-stu-id="26e5a-p126">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive. It must be typed exactly as shown. For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="26e5a-p127">TrustedServer 模式只能对位于外围网络内部的计算机使用。当观察程序节点以 TrustedServer 模式运行时，管理员无需在计算机上保留测试用户密码。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p127">TrustedServer mode can be used only with computers that lie inside the perimeter network. When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="26e5a-291">配置观察程序节点以使用协商</span><span class="sxs-lookup"><span data-stu-id="26e5a-291">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="26e5a-292"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="26e5a-292"></span></span>

<span data-ttu-id="26e5a-p128">如果观察程序节点计算机位于外围网络之外，则必须遵循一个略有不同的过程来配置该观察程序节点运行综合事务：具体而言，不应创建受信任的应用程序池或受信任的应用程序。这意味着，您需要完成接下来的两个任务。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p128">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application. That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="26e5a-295">更新 RTC Local Read-Only Administrators 组中的成员身份</span><span class="sxs-lookup"><span data-stu-id="26e5a-295">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="26e5a-296">如果观察程序节点位于外围网络之外，则必须在观察程序节点上完成以下过程，将 Network Service 帐户添加到观察程序节点计算机上的 RTC Local Read-only Administrators 组：</span><span class="sxs-lookup"><span data-stu-id="26e5a-296">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="26e5a-297">单击“开始”，右键单击“计算机”，然后单击“管理”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-297">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="26e5a-298">在“服务器管理器”中，展开“配置”，展开“本地用户和组”，然后单击“组”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-298">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="26e5a-299">在“组”窗格中，双击“RTC Local Read-only Administrators”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-299">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="26e5a-300">在“RTC Local Read-only Administrators 属性”对话框中，单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-300">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="26e5a-301">在“选择用户、计算机、服务帐户或组”对话框中，单击“位置”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-301">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="26e5a-302">在“位置”对话框中，选择观察程序节点计算机的名称，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-302">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="26e5a-303">在“输入要选择的对象名称”框中，键入“Network Service”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-303">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="26e5a-304">在“RTC Local Read-only Administrators 属性”对话框中，单击“确定”，然后关闭“服务器管理器”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-304">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="26e5a-305">重新启动观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="26e5a-305">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="26e5a-306">安装观察程序节点配置文件</span><span class="sxs-lookup"><span data-stu-id="26e5a-306">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="26e5a-307">下一步是运行文件 Watchernode.msi：</span><span class="sxs-lookup"><span data-stu-id="26e5a-307">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="26e5a-p129">打开 Microsoft Skype for Business Server 2015 命令行管理程序。依次单击“开始”、“所有程序”和“Microsoft Skype for Business Server 2015”，然后单击“Skype for Business Server 命令行管理程序”。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p129">Open the Microsoft Skype for Business Server 2015 Management Shell. Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="26e5a-310">在 Skype for Business Server 命令行管理程序中，键入以下命令，然后按 Enter（确保指定 Watchernode.msi 副本的实际路径）：</span><span class="sxs-lookup"><span data-stu-id="26e5a-310">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="26e5a-p130">如前所述，还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。命令窗口打开后，键入上面的步骤 2 所示的相同命令。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p130">As mentioned previously, Watchernode.msi can also be run from a command window. To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**. When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="26e5a-p131">任何时候如果无法将观察程序节点设置为一个受信任应用程序池，都将使用协商模式。在此模式中，管理员需要管理观察程序节点上的测试用户密码。</span><span class="sxs-lookup"><span data-stu-id="26e5a-p131">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

