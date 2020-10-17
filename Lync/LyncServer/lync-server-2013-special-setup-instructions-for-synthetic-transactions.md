---
title: Lync Server 2013：综合事务的特殊设置说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3841cb8a582e44e14b9ae7c73f3b3aed6b6ded33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519569"
---
# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="a1a68-102">Lync Server 2013 中的综合事务的特殊设置说明</span><span class="sxs-lookup"><span data-stu-id="a1a68-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1a68-103">_**上次修改的主题：** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="a1a68-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="a1a68-p101">大多数综合事务可按原样在观察程序节点上运行；也就是说，一旦将综合事务添加到观察程序节点配置设置，观察程序节点就可在其测试通过期间开始使用综合事务。但此情况并不适用于所有综合事务。以下几节讨论了这些例外（需要特定安装说明的综合事务）。</span><span class="sxs-lookup"><span data-stu-id="a1a68-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="a1a68-107">处理服务器超时错误</span><span class="sxs-lookup"><span data-stu-id="a1a68-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="a1a68-108">在某些情况下，您可能会发现您的综合事务失败，并出现服务器超时错误 (错误代码 504) 。</span><span class="sxs-lookup"><span data-stu-id="a1a68-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="a1a68-109">这些错误通常是由防火墙问题引起的。</span><span class="sxs-lookup"><span data-stu-id="a1a68-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="a1a68-110">执行综合事务时，该事务在 MonitoringHost.exe 进程下运行;反过来，MonitoringHost.exe 启动 PowerShell.exe 进程的一个实例。</span><span class="sxs-lookup"><span data-stu-id="a1a68-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="a1a68-111">如果防火墙阻止 MonitoringHost.exe 或 PowerShell.exe，则综合事务将失败，并将生成504错误。</span><span class="sxs-lookup"><span data-stu-id="a1a68-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="a1a68-112">若要解决此问题，您应手动为本地计算机上的 MonitoringHost.exe 和 PowerShell.exe 创建入站防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="a1a68-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="a1a68-113">可以通过 Windows 防火墙或第三方本地防火墙软件执行此操作，具体取决于您的服务器的预先存在的配置。</span><span class="sxs-lookup"><span data-stu-id="a1a68-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="a1a68-114">如果要在综合事务主机和要监视的 Lync 服务器之间使用网络防火墙设备，则应将主机视为客户端计算机，并 [在 Lync Server 2013 中观察内部服务器的端口和协议中的](lync-server-2013-ports-and-protocols-for-internal-servers.md)所有防火墙端口要求。</span><span class="sxs-lookup"><span data-stu-id="a1a68-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="a1a68-115">数据会议综合事务</span><span class="sxs-lookup"><span data-stu-id="a1a68-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="a1a68-116">如果您的观察程序节点计算机位于您的外围网络之外，则您可能无法运行数据会议综合事务，除非您首先禁用网络服务帐户的 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="a1a68-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="a1a68-117">若要为此服务禁用代理设置，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="a1a68-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="a1a68-118">在观察程序节点计算机上，依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“附件”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1a68-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="a1a68-119">在控制台窗口中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a1a68-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="a1a68-120">命令窗口中将显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="a1a68-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="a1a68-121">此邮件表示您已禁用网络服务帐户的 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="a1a68-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="a1a68-122">Exchange 统一消息综合事务</span><span class="sxs-lookup"><span data-stu-id="a1a68-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="a1a68-123">Exchange 统一消息 (UM) 综合事务验证测试用户是否可以连接到位于 Exchange 中的语音邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="a1a68-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="a1a68-124">需要先为这些测试用户预配置语音邮件帐户，然后他们才能使用 Exchange UM 测试。</span><span class="sxs-lookup"><span data-stu-id="a1a68-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="a1a68-125">持久聊天综合事务</span><span class="sxs-lookup"><span data-stu-id="a1a68-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="a1a68-126">若要使用持久聊天综合事务，管理员必须首先创建一个通道，并向测试用户授予使用该功能的权限。</span><span class="sxs-lookup"><span data-stu-id="a1a68-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="a1a68-127">[CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet 可用于正确配置这些测试用户：</span><span class="sxs-lookup"><span data-stu-id="a1a68-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="a1a68-128">必须从企业内部运行此设置任务：</span><span class="sxs-lookup"><span data-stu-id="a1a68-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="a1a68-129">如果从非服务器计算机运行，则运行此 cmdlet 的用户必须是基于角色的访问控制 (RBAC) 的 PersistentChatAdministrators 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="a1a68-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="a1a68-130">如果从服务器本身运行，则运行此 cmdlet 的用户应是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="a1a68-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a1a68-131">在上面的命令中，已包含 Setup 参数并设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="a1a68-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="a1a68-132">如果包含 Setup 参数，Test-CsPersistentChatMessage 将创建一个特殊的持久聊天室，并向测试用户填充该聊天室。</span><span class="sxs-lookup"><span data-stu-id="a1a68-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="a1a68-133">这有助于确保实际存在一个可用于测试目的的聊天室。</span><span class="sxs-lookup"><span data-stu-id="a1a68-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="a1a68-134">请注意，安装程序参数应仅在前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="a1a68-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="a1a68-135">仅管理员能够删除由 Test-CsPersistentChatMessage 创建的聊天室。</span><span class="sxs-lookup"><span data-stu-id="a1a68-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="a1a68-136">PSTN 对等呼叫综合事务</span><span class="sxs-lookup"><span data-stu-id="a1a68-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="a1a68-137">[CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)综合事务通过公开交换电话网络 (PSTN) 验证是否可以拨打和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1a68-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="a1a68-138">若要运行此综合事务，管理员必须：</span><span class="sxs-lookup"><span data-stu-id="a1a68-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="a1a68-139"> (呼叫者和接收方) 启用企业语音的两个测试用户。</span><span class="sxs-lookup"><span data-stu-id="a1a68-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="a1a68-140">为每个用户帐户配置外线直拨分机 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="a1a68-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="a1a68-141">配置允许对接收者的号码的呼叫到达 PSTN 网关的语音策略和语音路由。</span><span class="sxs-lookup"><span data-stu-id="a1a68-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="a1a68-142">配置接受呼叫的 PSTN 网关和基于拨打的号码将呼叫路由回接收者主池的媒体。</span><span class="sxs-lookup"><span data-stu-id="a1a68-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="a1a68-143">统一的联系人存储库综合事务</span><span class="sxs-lookup"><span data-stu-id="a1a68-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="a1a68-144">统一联系人存储综合事务验证 Lync Server 2013 是否可以代表用户从 Microsoft Exchange Server 2013 检索联系人。</span><span class="sxs-lookup"><span data-stu-id="a1a68-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="a1a68-145">若要使用此综合事务，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="a1a68-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="a1a68-146">必须在 Lync Server 2013 和 Exchange 2013 之间配置[ (OAuth) 和在 Lync server 2013 中的合作伙伴应用程序管理服务器到服务器的身份验证](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a68-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="a1a68-147">测试用户必须具有有效的 Exchange 2013 邮箱。</span><span class="sxs-lookup"><span data-stu-id="a1a68-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="a1a68-148">在满足这些条件后，管理员可以运行以下命令来验证 SIP 地址为 kenmyer@litwareinc.com 的用户是否能从统一的联系人存储库中检索其联系人：</span><span class="sxs-lookup"><span data-stu-id="a1a68-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="a1a68-149">请注意上面的命令中使用的 Setup 参数的用法。</span><span class="sxs-lookup"><span data-stu-id="a1a68-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="a1a68-150">如果运行 Test-CsUnifiedContactStore 时包含 Setup 参数，则指定用户的联系人（在此示例中，为 sip:kenmyer@litwareinc.com）将被移至统一的联系人存储库中。</span><span class="sxs-lookup"><span data-stu-id="a1a68-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="a1a68-151"> (当然，如果用户的联系人已在统一联系人存储中，则无需移动它们。 ) 安装程序参数通常仅在第 Test-CsUnifiedContactStore 一次执行) 时 (使用一次，且只应与测试用户一起使用;即，用户帐户永远不会实际登录到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="a1a68-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="a1a68-152">在将测试用户迁移到统一的联系人存储库后，可通过调用 Test-CsUnifiedContactStore（不带 Setup 参数）来验证是否能检索用户的联系人：</span><span class="sxs-lookup"><span data-stu-id="a1a68-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="a1a68-153">XMPP 综合事务</span><span class="sxs-lookup"><span data-stu-id="a1a68-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="a1a68-154">XMPP（可扩展消息传递和状态协议）IM 综合事务要求为一个或多个联盟域配置 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="a1a68-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="a1a68-155">若要启用 XMPP 综合事务，则必须将 XmppTestReceiverMailAddress 参数与可路由的 XMPP 域中的用户帐户一起提供。</span><span class="sxs-lookup"><span data-stu-id="a1a68-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="a1a68-156">例如：</span><span class="sxs-lookup"><span data-stu-id="a1a68-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="a1a68-157">在此示例中，必须存在 Lync Server 2013 规则，才能将 litwareinc.com 的邮件路由到 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="a1a68-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

