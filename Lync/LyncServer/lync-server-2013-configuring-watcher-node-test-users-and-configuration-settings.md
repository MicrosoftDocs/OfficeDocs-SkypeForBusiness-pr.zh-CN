---
title: 配置观察程序节点测试用户和配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d446934e8d84a12a6eecd84fbc94a956d8ae95e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d9f23-102">在 Lync Server 2013 中配置观察程序节点测试用户和配置设置</span><span class="sxs-lookup"><span data-stu-id="d9f23-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9f23-103">_**主题上次修改时间:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="d9f23-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="d9f23-104">在配置将用作观察者节点的计算机后, 必须:</span><span class="sxs-lookup"><span data-stu-id="d9f23-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="d9f23-105">创建要由这些观察程序节点使用的测试帐户。</span><span class="sxs-lookup"><span data-stu-id="d9f23-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="d9f23-106">如果你使用协商身份验证方法, 你还必须使用[CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet 来启用这些测试帐户, 以便在 "观察程序" 节点上使用。</span><span class="sxs-lookup"><span data-stu-id="d9f23-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="d9f23-107">更新观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="d9f23-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="d9f23-108">本部分包括:</span><span class="sxs-lookup"><span data-stu-id="d9f23-108">This section covers:</span></span>

  - <span data-ttu-id="d9f23-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="d9f23-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="d9f23-110">使用默认合成事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d9f23-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="d9f23-111">配置扩展测试</span><span class="sxs-lookup"><span data-stu-id="d9f23-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="d9f23-112">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="d9f23-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="d9f23-113">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="d9f23-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="d9f23-114">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="d9f23-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="d9f23-115">测试用户不需要表示实际人员, 但它们必须是有效的 Active Directory 域服务帐户;此外, 必须为 Lync Server 2013 启用这些帐户, 它们必须具有有效的 SIP 地址, 并且应该为企业语音启用 (以使用 CsPstnPeerToPeerCall 合成事务)。</span><span class="sxs-lookup"><span data-stu-id="d9f23-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="d9f23-116">如果你使用 TrustedServer 身份验证方法, 则你需要做的就是确保这些帐户存在并且已按照此处的指定进行配置。</span><span class="sxs-lookup"><span data-stu-id="d9f23-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="d9f23-117">你应该为要测试的每个池至少分配三个测试用户。</span><span class="sxs-lookup"><span data-stu-id="d9f23-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="d9f23-118">如果你使用协商身份验证方法, 你还必须使用**CsTestUserCredential** Cmdlet 和 Lync Server Management Shell 来使这些测试帐户能够处理合成事务。</span><span class="sxs-lookup"><span data-stu-id="d9f23-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="d9f23-119">你可以通过运行如下所示的命令来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d9f23-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="d9f23-120">(这些命令假设已经创建了三个 Active Directory 用户帐户, 并且已为 Lync Server 2013 启用了这些帐户。):</span><span class="sxs-lookup"><span data-stu-id="d9f23-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="d9f23-121">请注意, 不仅必须包括 SIP 地址, 还必须包括用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="d9f23-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="d9f23-122">如果不包含密码集, CsTestUserCredential 将提示您输入该信息。</span><span class="sxs-lookup"><span data-stu-id="d9f23-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="d9f23-123">用户名可以使用上面显示的域名\\用户名格式指定, 或使用用户名 @ 域名设置格式。例如:</span><span class="sxs-lookup"><span data-stu-id="d9f23-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="d9f23-124">若要验证是否已创建测试用户凭据, 请从 Lync Server 命令行管理程序中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="d9f23-125">应为每个用户返回类似于以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="d9f23-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="d9f23-126">使用默认合成事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d9f23-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="d9f23-127">在创建测试用户之后, 你可以使用类似下面的命令创建观察程序节点:</span><span class="sxs-lookup"><span data-stu-id="d9f23-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="d9f23-128">此命令将创建一个新的监视程序节点, 该节点使用默认设置并运行一组默认的合成事务。</span><span class="sxs-lookup"><span data-stu-id="d9f23-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="d9f23-129">新的观察程序节点还使用 test 用户 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="d9f23-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="d9f23-130">如果观察程序节点使用 TrustedServer 身份验证, 则三个测试帐户可以是为 Active Directory 和 Lync Server 启用的任何有效用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d9f23-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="d9f23-131">如果观察程序节点使用协商身份验证方法, 则还必须通过使用**CsTestUserCredential** cmdlet 为观察程序节点启用这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d9f23-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="d9f23-132">配置扩展测试</span><span class="sxs-lookup"><span data-stu-id="d9f23-132">Configuring Extended Tests</span></span>

<span data-ttu-id="d9f23-133">如果想要启用公共交换电话网络 (PSTN 测试), 它将验证与公共交换电话网络的连接性, 则需要在设置观察程序节点时执行其他一些配置。</span><span class="sxs-lookup"><span data-stu-id="d9f23-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="d9f23-134">首先, 你需要将测试用户与 PSTN 测试类型相关联。</span><span class="sxs-lookup"><span data-stu-id="d9f23-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="d9f23-135">若要执行此操作, 请在 Lync Server 命令行管理程序中运行类似下面的命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="d9f23-136">请注意, 此命令的结果必须存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="d9f23-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="d9f23-137">在此示例中, 这是一个名为 $pstnTest 的变量。</span><span class="sxs-lookup"><span data-stu-id="d9f23-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="d9f23-138">此时, 你可以使用**CsWatcherNodeConfiguration** cmdlet 将测试类型 (存储在变量 $pstnTest 中) 与 Lync Server 2013 池相关联。</span><span class="sxs-lookup"><span data-stu-id="d9f23-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="d9f23-139">例如, 以下命令为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置, 添加以前创建的三个测试用户以及添加 PSTN 测试类型:</span><span class="sxs-lookup"><span data-stu-id="d9f23-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="d9f23-140">请注意, 如果尚未在观察程序节点计算机上安装 Lync Server core 文件和 RTCLocal 数据库, 上述命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d9f23-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="d9f23-141">若要测试多个语音策略, 你需要使用**CsExtendedTest** cmdlet 为每个策略创建扩展测试。</span><span class="sxs-lookup"><span data-stu-id="d9f23-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="d9f23-142">分配到此测试的用户应配置所需的语音策略。</span><span class="sxs-lookup"><span data-stu-id="d9f23-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="d9f23-143">然后, 通过使用如下所示的命令将扩展测试传递到**CsWatcherNodeConfiguration** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9f23-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="d9f23-144">如果在未使用 "测试" 参数的情况下调用 New CsWatcherNodeConfiguration, 则表示新的观察程序节点仅启用默认合成事务 (和指定的扩展合成事务)。</span><span class="sxs-lookup"><span data-stu-id="d9f23-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="d9f23-145">这意味着观察程序节点将测试以下组件:</span><span class="sxs-lookup"><span data-stu-id="d9f23-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="d9f23-146">注册</span><span class="sxs-lookup"><span data-stu-id="d9f23-146">Registration</span></span>

  - <span data-ttu-id="d9f23-147">即时消息</span><span class="sxs-lookup"><span data-stu-id="d9f23-147">IM</span></span>

  - <span data-ttu-id="d9f23-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="d9f23-148">GroupIM</span></span>

  - <span data-ttu-id="d9f23-149">P2PAV (对等音频/视频会话)</span><span class="sxs-lookup"><span data-stu-id="d9f23-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="d9f23-150">AvConference (音频/会议)</span><span class="sxs-lookup"><span data-stu-id="d9f23-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="d9f23-151">状态</span><span class="sxs-lookup"><span data-stu-id="d9f23-151">Presence</span></span>

  - <span data-ttu-id="d9f23-152">ABS (通讯簿服务)</span><span class="sxs-lookup"><span data-stu-id="d9f23-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="d9f23-153">ABWQ (通讯簿 web 服务)</span><span class="sxs-lookup"><span data-stu-id="d9f23-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="d9f23-154">PSTN (PSTN 网关呼叫, 指定为扩展测试。</span><span class="sxs-lookup"><span data-stu-id="d9f23-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="d9f23-155">默认情况下, PSTN 处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d9f23-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="d9f23-156">此测试仅在此情况下启用, 因为命令通过使用 ExtendedTests 参数启用了 PSTN。)</span><span class="sxs-lookup"><span data-stu-id="d9f23-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="d9f23-157">这还意味着默认情况下不会测试以下组件:</span><span class="sxs-lookup"><span data-stu-id="d9f23-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="d9f23-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="d9f23-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="d9f23-159">MCXP2PIM (移动设备即时消息)</span><span class="sxs-lookup"><span data-stu-id="d9f23-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="d9f23-160">ExumConnectivity (Exchange 统一消息)</span><span class="sxs-lookup"><span data-stu-id="d9f23-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="d9f23-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="d9f23-161">JoinLauncher</span></span>

  - <span data-ttu-id="d9f23-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d9f23-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="d9f23-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="d9f23-163">DataConference</span></span>

  - <span data-ttu-id="d9f23-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="d9f23-164">XmppIM</span></span>

  - <span data-ttu-id="d9f23-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="d9f23-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="d9f23-166">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="d9f23-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="d9f23-167">配置了观察程序节点后, 你可以使用**CsWatcherNodeConfiguration** cmdlet 在节点中添加或删除合成事务。</span><span class="sxs-lookup"><span data-stu-id="d9f23-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="d9f23-168">例如, 若要向观察程序节点添加 PersistentChatMessage 测试, 请使用 Add 方法和类似如下的命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="d9f23-169">可通过使用逗号分隔测试名称来添加多个测试。</span><span class="sxs-lookup"><span data-stu-id="d9f23-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="d9f23-170">例如：</span><span class="sxs-lookup"><span data-stu-id="d9f23-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="d9f23-171">请注意, 如果在观察程序节点上已启用一个或多个这些测试 (例如 DataConference), 将出现错误。</span><span class="sxs-lookup"><span data-stu-id="d9f23-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="d9f23-172">在这种情况下, 你将收到类似于以下内容的错误消息:</span><span class="sxs-lookup"><span data-stu-id="d9f23-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="d9f23-173">发生此错误时, 将不会应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="d9f23-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="d9f23-174">应重新运行该命令, 并删除重复的测试。</span><span class="sxs-lookup"><span data-stu-id="d9f23-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="d9f23-175">若要从观察程序节点中删除合成事务, 请使用 Remove 方法, 而不是 Add 方法。</span><span class="sxs-lookup"><span data-stu-id="d9f23-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="d9f23-176">例如, 此命令将从观察程序节点中删除 ABWQ 测试:</span><span class="sxs-lookup"><span data-stu-id="d9f23-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="d9f23-177">你还可以使用 Replace 方法将当前启用的所有测试替换为一个或多个新测试。</span><span class="sxs-lookup"><span data-stu-id="d9f23-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="d9f23-178">例如, 如果你只希望观察程序节点运行 IM 测试, 则可以通过使用以下命令来配置它:</span><span class="sxs-lookup"><span data-stu-id="d9f23-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="d9f23-179">运行上述命令时, 将禁用指定的观察程序节点上的所有合成事务, IM 除外。</span><span class="sxs-lookup"><span data-stu-id="d9f23-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="d9f23-180">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="d9f23-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="d9f23-181">如果要查看已分配给观察程序节点的测试, 请使用类似下面的命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="d9f23-182">上述命令将根据分配给节点的合成事务返回类似于此的信息:</span><span class="sxs-lookup"><span data-stu-id="d9f23-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="d9f23-183">若要按字母顺序查看合成事务, 请改用以下命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="d9f23-184">CsWatcherNodeConfiguration-Identity "atl-cs-001.litwareinc.com" |Select-对象-ExpandProperty 测试 |排序-对象</span><span class="sxs-lookup"><span data-stu-id="d9f23-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="d9f23-185">若要验证是否已创建观察程序节点, 请在 Lync Server 命令行管理程序中键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="d9f23-186">您将收到类似以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="d9f23-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="d9f23-187">若要验证是否正确配置了观察程序节点, 请在 Lync Server 命令行管理程序中键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="d9f23-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="d9f23-188">前面的命令将在你的部署中测试每个观察程序节点并告诉你信息, 例如:</span><span class="sxs-lookup"><span data-stu-id="d9f23-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="d9f23-189">已安装所需的注册机构角色。</span><span class="sxs-lookup"><span data-stu-id="d9f23-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="d9f23-190">当你运行 CsWatcherNodeConfiguration 时, 将为你创建所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d9f23-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="d9f23-191">您的服务器运行的是正确版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="d9f23-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="d9f23-192">您的端口配置正确。</span><span class="sxs-lookup"><span data-stu-id="d9f23-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="d9f23-193">您分配的测试用户具有所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="d9f23-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

