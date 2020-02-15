---
title: 配置观察程序节点测试用户和配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5373984e3a4349d73974d9f3b6c243999fbb165
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="58d7e-102">在 Lync Server 2013 中配置观察程序节点测试用户和配置设置</span><span class="sxs-lookup"><span data-stu-id="58d7e-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58d7e-103">_**上次修改的主题：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="58d7e-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="58d7e-104">在配置将充当观察程序节点的计算机之后，您必须：</span><span class="sxs-lookup"><span data-stu-id="58d7e-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="58d7e-105">创建可供这些观察程序节点使用的测试帐户。</span><span class="sxs-lookup"><span data-stu-id="58d7e-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="58d7e-106">如果您使用的是 Negotiate 身份验证方法，则必须同时使用 [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet 来启用这些测试帐户，以在观察程序节点上使用。</span><span class="sxs-lookup"><span data-stu-id="58d7e-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="58d7e-107">更新观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="58d7e-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="58d7e-108">本节介绍：</span><span class="sxs-lookup"><span data-stu-id="58d7e-108">This section covers:</span></span>

  - <span data-ttu-id="58d7e-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="58d7e-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="58d7e-110">使用默认综合事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="58d7e-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="58d7e-111">配置扩展的测试</span><span class="sxs-lookup"><span data-stu-id="58d7e-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="58d7e-112">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="58d7e-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="58d7e-113">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="58d7e-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="58d7e-114">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="58d7e-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="58d7e-115">测试用户不需要表示实际人员，但必须是有效的 Active Directory 域服务帐户;此外，必须为 Lync Server 2013 启用这些帐户，它们必须具有有效的 SIP 地址，并且应为企业语音启用这些帐户（以使用 CsPstnPeerToPeerCall 综合事务）。</span><span class="sxs-lookup"><span data-stu-id="58d7e-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="58d7e-116">如果使用 TrustedServer 身份验证方法，则您所需要做的就是确保这些帐户存在并且已按此处所指定的那样进行配置。</span><span class="sxs-lookup"><span data-stu-id="58d7e-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="58d7e-117">您应为要测试的每个池至少分配三个测试用户。</span><span class="sxs-lookup"><span data-stu-id="58d7e-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="58d7e-118">如果使用的是协商身份验证方法，则还必须使用**CsTestUserCredential** Cmdlet 和 Lync Server 命令行管理程序，以使这些测试帐户能够处理综合事务。</span><span class="sxs-lookup"><span data-stu-id="58d7e-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="58d7e-119">您可以通过运行与以下类似的命令来执行此操作（这些命令假设已创建三个 nm-ad-2nd 用户帐户，并且已针对 nm-server-w15-long 启用这些帐户。</span><span class="sxs-lookup"><span data-stu-id="58d7e-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="58d7e-120">（这些命令假定已经创建了三个 Active Directory 用户帐户，并且已为这些帐户启用了 Lync Server 2013。）：</span><span class="sxs-lookup"><span data-stu-id="58d7e-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="58d7e-121">请注意，不仅必须包括 SIP 地址，而且还要包括用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="58d7e-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="58d7e-122">如果不包括密码，Set-CsTestUserCredential 将提示您输入该信息。</span><span class="sxs-lookup"><span data-stu-id="58d7e-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="58d7e-123">可以使用上面显示的域名\\用户名格式指定用户名，或使用格式用户 name@domain 名称指定名称。例如：</span><span class="sxs-lookup"><span data-stu-id="58d7e-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="58d7e-124">若要验证是否已创建测试用户凭据，请在 Lync Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="58d7e-125">应针对每个用户返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="58d7e-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="58d7e-126">使用默认综合事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="58d7e-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="58d7e-127">在创建测试用户之后，您可以使用与以下类似的命令创建观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="58d7e-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="58d7e-128">此命令会创建一个新的观察程序节点，该节点使用默认设置并运行默认的综合事务集。</span><span class="sxs-lookup"><span data-stu-id="58d7e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="58d7e-129">新的观察程序节点还使用测试用户 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="58d7e-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="58d7e-130">如果观察程序节点使用的是 TrustedServer 身份验证，则这三个测试帐户可以是为 Active Directory 和 Lync Server 启用的任何有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="58d7e-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="58d7e-131">如果观察程序节点使用的是 Negotiate 身份验证方法，您必须同时使用 **Set-CsTestUserCredential** cmdlet 为观察程序节点启用这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="58d7e-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="58d7e-132">配置扩展的测试</span><span class="sxs-lookup"><span data-stu-id="58d7e-132">Configuring Extended Tests</span></span>

<span data-ttu-id="58d7e-133">如果您想要启用公用电话交换网（PSTN 测试），以验证与公用电话交换网的连接，则需要在设置观察程序节点时执行一些额外的配置。</span><span class="sxs-lookup"><span data-stu-id="58d7e-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="58d7e-134">首先，您需要将测试用户与 PSTN 测试类型相关联。</span><span class="sxs-lookup"><span data-stu-id="58d7e-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="58d7e-135">若要执行此操作，请在 Lync Server 命令行管理程序中运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="58d7e-136">请注意，必须将此命令的结果存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="58d7e-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="58d7e-137">在此示例中，指的是名为 $pstnTest 的变量。</span><span class="sxs-lookup"><span data-stu-id="58d7e-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="58d7e-138">在这种情况下，您可以使用**new-cswatchernodeconfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）与 Lync Server 2013 池相关联。</span><span class="sxs-lookup"><span data-stu-id="58d7e-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="58d7e-139">例如，下列命令会为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置，从而添加先前已创建的三个测试用户，并同时添加 PSTN 测试类型：</span><span class="sxs-lookup"><span data-stu-id="58d7e-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="58d7e-140">请注意，如果尚未在观察程序节点计算机上安装 Lync Server core 文件和 RTCLocal 数据库，则上述命令将失败。</span><span class="sxs-lookup"><span data-stu-id="58d7e-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="58d7e-141">要测试多个语音策略，需要使用 **New-CsExtendedTest** cmdlet 为每个策略创建一个扩展测试。</span><span class="sxs-lookup"><span data-stu-id="58d7e-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="58d7e-142">应使用所需的语音策略对分配给此测试的用户进行配置。</span><span class="sxs-lookup"><span data-stu-id="58d7e-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="58d7e-143">然后，使用与以下类似的命令将扩展测试传递到 **New-CsWatcherNodeConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="58d7e-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="58d7e-p110">如果在未使用 Tests 参数的情况下呼叫 New-CsWatcherNodeConfiguration，则表示只会针对新的观察程序节点启用默认综合事务（以及指定的扩展综合事务）。这意味着该观察程序节点将测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="58d7e-p110">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="58d7e-146">注册</span><span class="sxs-lookup"><span data-stu-id="58d7e-146">Registration</span></span>

  - <span data-ttu-id="58d7e-147">IM</span><span class="sxs-lookup"><span data-stu-id="58d7e-147">IM</span></span>

  - <span data-ttu-id="58d7e-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="58d7e-148">GroupIM</span></span>

  - <span data-ttu-id="58d7e-149">P2PAV（对等音频/视频会话）</span><span class="sxs-lookup"><span data-stu-id="58d7e-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="58d7e-150">AvConference（音频/会议）</span><span class="sxs-lookup"><span data-stu-id="58d7e-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="58d7e-151">状态</span><span class="sxs-lookup"><span data-stu-id="58d7e-151">Presence</span></span>

  - <span data-ttu-id="58d7e-152">ABS（通讯簿服务）</span><span class="sxs-lookup"><span data-stu-id="58d7e-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="58d7e-153">ABWQ（通讯簿 Web 服务）</span><span class="sxs-lookup"><span data-stu-id="58d7e-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="58d7e-p111">PSTN（PSTN 网关呼叫，指定为扩展测试。默认情况下会禁用 PSTN。只是因为命令使用 ExtendedTests 参数启用了 PSTN，所以在这种情况下才会启用测试。）</span><span class="sxs-lookup"><span data-stu-id="58d7e-p111">PSTN (PSTN gateway calls, specified as an extended test. By default, PSTN is disabled. The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="58d7e-157">这还意味着在默认情况下不会测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="58d7e-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="58d7e-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="58d7e-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="58d7e-159">MCXP2PIM（移动设备即时消息）</span><span class="sxs-lookup"><span data-stu-id="58d7e-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="58d7e-160">ExumConnectivity（Exchange 统一消息）</span><span class="sxs-lookup"><span data-stu-id="58d7e-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="58d7e-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="58d7e-161">JoinLauncher</span></span>

  - <span data-ttu-id="58d7e-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="58d7e-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="58d7e-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="58d7e-163">DataConference</span></span>

  - <span data-ttu-id="58d7e-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="58d7e-164">XmppIM</span></span>

  - <span data-ttu-id="58d7e-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="58d7e-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="58d7e-166">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="58d7e-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="58d7e-167">在配置观察程序节点之后，您可以使用 **Set-CsWatcherNodeConfiguration** cmdlet 添加或从节点中删除综合事务。</span><span class="sxs-lookup"><span data-stu-id="58d7e-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="58d7e-168">例如，要将 PersistentChatMessage 测试添加到观察程序节点，请使用 Add 方法和与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="58d7e-p113">可以通过使用逗号分隔测试名称来添加多个测试。例如：</span><span class="sxs-lookup"><span data-stu-id="58d7e-p113">Multiple tests can be added by separating the test names by using commas. For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="58d7e-p114">请注意，如果已在观察程序节点上启用其中一个或多个测试（例如，DataConference），则将会发生错误。在这种情况下，您将收到与以下类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="58d7e-p114">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="58d7e-173">发生此错误时，不会应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="58d7e-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="58d7e-174">应通过删除的重复测试重新运行此命令。</span><span class="sxs-lookup"><span data-stu-id="58d7e-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="58d7e-p116">要从观察程序节点中删除综合事务，请使用 Remove 方法而不是 Add 方法。例如，以下命令会从观察程序节点中删除 ABWQ 测试：</span><span class="sxs-lookup"><span data-stu-id="58d7e-p116">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method. For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="58d7e-p117">您也可以使用 Replace 方法将所有目前启用的测试替换为一个或多个新测试。例如，如果您只是希望观察程序节点运行 IM 测试，则可以使用以下命令对此进行配置：</span><span class="sxs-lookup"><span data-stu-id="58d7e-p117">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="58d7e-179">在运行上述命令时，除了 IM 以外，将禁用指定观察程序节点上的所有综合事务。</span><span class="sxs-lookup"><span data-stu-id="58d7e-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="58d7e-180">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="58d7e-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="58d7e-181">如果您想要查看已分配给观察程序节点的测试，请使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="58d7e-182">根据已分配给节点的综合事务，上述命令将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="58d7e-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="58d7e-183">要按字母顺序查看综合事务，请改为使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="58d7e-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="58d7e-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="58d7e-185">若要验证是否已创建观察程序节点，请在 Lync Server 命令行管理程序中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="58d7e-186">您将收到与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="58d7e-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="58d7e-187">若要验证是否已正确配置观察程序节点，请在 Lync Server 命令行管理程序中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="58d7e-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="58d7e-188">上述命令将测试您的部署中的每个观察程序节点，并告诉您诸如以下方面的信息：</span><span class="sxs-lookup"><span data-stu-id="58d7e-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="58d7e-189">是否已安装所需的注册器角色。</span><span class="sxs-lookup"><span data-stu-id="58d7e-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="58d7e-190">是否在您运行 Set-CsWatcherNodeConfiguration 时为您创建了所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="58d7e-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="58d7e-191">您的服务器运行的是正确版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="58d7e-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="58d7e-192">是否已正确配置您的端口。</span><span class="sxs-lookup"><span data-stu-id="58d7e-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="58d7e-193">所分配的测试用户是否具有所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="58d7e-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

