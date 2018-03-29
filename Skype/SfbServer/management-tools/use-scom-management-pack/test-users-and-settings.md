---
title: 配置观察程序节点测试用户和设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 摘要： 配置测试用户帐户和服务器业务综合事务 Skype 的观察程序节点设置。
ms.openlocfilehash: 55172fb152b3b02e87e8d46048c820c2c1b2dd04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="d883e-103">配置观察程序节点测试用户和设置</span><span class="sxs-lookup"><span data-stu-id="d883e-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="d883e-104">**摘要：**配置测试用户帐户和服务器业务综合事务 Skype 的观察程序节点设置。</span><span class="sxs-lookup"><span data-stu-id="d883e-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="d883e-105">在配置后将充当观察者节点的计算机，您必须：</span><span class="sxs-lookup"><span data-stu-id="d883e-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="d883e-106">[配置测试用户帐户](test-users-and-settings.md#testuser)，将由这些观察者节点。</span><span class="sxs-lookup"><span data-stu-id="d883e-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="d883e-107">如果您使用协商身份验证方法，您还必须使用**集 CsTestUserCredential** cmdlet 以启用这些测试用于观察程序节点上的帐户。</span><span class="sxs-lookup"><span data-stu-id="d883e-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="d883e-108">更新的观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="d883e-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="d883e-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="d883e-109">Configure Test User Accounts</span></span>
<span data-ttu-id="d883e-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d883e-110"></span></span>

<span data-ttu-id="d883e-111">测试帐户不需要代表实际的人，但它们必须是有效的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="d883e-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="d883e-112">此外，这些帐户必须启用为 Skype 业务服务器 2015年，它们必须具有有效的 SIP 地址，并应为企业语音 （用于测试 CsPstnPeerToPeerCall 综合事务） 启用它们。</span><span class="sxs-lookup"><span data-stu-id="d883e-112">In addition, these accounts must be enabled for Skype for Business Server 2015, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="d883e-113">如果您使用的 TrustedServer 身份验证方法，您需要做是确保这些帐户存在，并对其所述配置。</span><span class="sxs-lookup"><span data-stu-id="d883e-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="d883e-114">您应该指定您想要测试每个池的至少三个测试用户。</span><span class="sxs-lookup"><span data-stu-id="d883e-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="d883e-115">如果您使用协商身份验证方法，则还必须使用一组 CsTestUserCredential cmdlet 和 Skype 的业务服务器命令行管理程序来启用这些测试帐户要使用综合事务。</span><span class="sxs-lookup"><span data-stu-id="d883e-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="d883e-116">通过运行命令类似于以下 （这些命令假定已创建了三个活动目录用户帐户，这些帐户启用的 Skype 的业务服务器 2015年） 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="d883e-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server 2015):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="d883e-117">您必须包括不仅 SIP 地址，但同时用户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="d883e-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="d883e-118">如果不包括密码，集 CsTestUserCredential cmdlet 将提示您输入该信息。</span><span class="sxs-lookup"><span data-stu-id="d883e-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="d883e-119">可以通过使用前面的代码块中所示的域 name\user 名称格式指定的用户名。</span><span class="sxs-lookup"><span data-stu-id="d883e-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="d883e-120">要验证已创建的测试用户凭据，请从 Skype 的业务服务器管理外壳程序运行这些命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="d883e-121">将为每个用户返回类似以下的信息：</span><span class="sxs-lookup"><span data-stu-id="d883e-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="d883e-122">**用户名**</span><span class="sxs-lookup"><span data-stu-id="d883e-122">**UserName**</span></span>|<span data-ttu-id="d883e-123">**密码**</span><span class="sxs-lookup"><span data-stu-id="d883e-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d883e-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="d883e-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="d883e-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="d883e-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="d883e-126">使用默认综合事务配置基本的观察者节点</span><span class="sxs-lookup"><span data-stu-id="d883e-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="d883e-127">在创建测试用户之后，可以使用类似以下的命令来创建观察者节点：</span><span class="sxs-lookup"><span data-stu-id="d883e-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="d883e-128">此命令创建一个新的观察程序节点，将使用默认设置运行综合事务的默认设置。</span><span class="sxs-lookup"><span data-stu-id="d883e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="d883e-129">新观察程序节点还使用测试用户 watcher1@litwareinc.com、 watcher2@litwareinc.com 和 watcher3@litwareinc.com。如果观察者节点使用 TrustedServer 身份验证，三种测试帐户可以是启用 Active Directory 和 Skype 业务服务器的任何有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d883e-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com. If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="d883e-130">如果观察者节点使用协商身份验证方法，这些用户帐户还必须被启用观察程序节点通过设置 CsTestUserCredential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d883e-130">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="d883e-131">验证目标的自动发现池来登录配置正确，而不是直接面向池改为使用下列步骤：</span><span class="sxs-lookup"><span data-stu-id="d883e-131">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="d883e-132">配置扩展的测试</span><span class="sxs-lookup"><span data-stu-id="d883e-132">Configuring Extended Tests</span></span>

<span data-ttu-id="d883e-133">如果您想要启用 PSTN 测试，验证与公共交换的电话网络的连接，您需要执行一些额外的配置设置的观察程序节点时。</span><span class="sxs-lookup"><span data-stu-id="d883e-133">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="d883e-134">首先，您必须将测试用户与 PSTN 测试类型关联由业务服务器管理外壳程序运行从 Skype 与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-134">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="d883e-135">此命令的结果必须存储在一个变量中。</span><span class="sxs-lookup"><span data-stu-id="d883e-135">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="d883e-136">在此示例中，变量被命名为 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="d883e-136">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="d883e-137">接下来，可以使用**新建 CsWatcherNodeConfiguration** cmdlet 将 Skype 业务服务器 2015年池的测试类型 （存储在变量 $pstnTest 中） 相关联。</span><span class="sxs-lookup"><span data-stu-id="d883e-137">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server 2015 pool.</span></span> <span data-ttu-id="d883e-138">例如，以下命令将创建池 atl-cs-001.litwareinc.com，添加以前创建的三个测试用户的新观察程序节点配置和添加 PSTN 测试类型：</span><span class="sxs-lookup"><span data-stu-id="d883e-138">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="d883e-139">如果您尚未安装 Skype 业务服务器核心文件和 RTCLocal 数据库的观察程序节点计算机上，上面的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d883e-139">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="d883e-140">若要测试多个语音策略，可以通过使用**New CsExtendedTest** cmdlet 创建为每个策略扩展的测试。</span><span class="sxs-lookup"><span data-stu-id="d883e-140">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="d883e-141">提供的用户应与所需的语音策略配置。</span><span class="sxs-lookup"><span data-stu-id="d883e-141">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="d883e-142">通过使用逗号分隔符，如到**新建 CsWatcherNodeConfiguration** cmdlet 传递扩展的测试：</span><span class="sxs-lookup"><span data-stu-id="d883e-142">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="d883e-143">-ExtendedTests @ {0} 添加 = $pstnTest1，pstnTest2 美元，美元 pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="d883e-143">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="d883e-144">由于**新建 CsWatcherNodeConfiguration** cmdlet 曾不使用测试参数的情况下，只有默认综合事务 （和指定的扩展综合事务） 将启用新观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="d883e-144">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="d883e-145">因此，观察者节点将测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="d883e-145">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="d883e-146">注册</span><span class="sxs-lookup"><span data-stu-id="d883e-146">Registration</span></span>
    
- <span data-ttu-id="d883e-147">IM</span><span class="sxs-lookup"><span data-stu-id="d883e-147">IM</span></span>
    
- <span data-ttu-id="d883e-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="d883e-148">GroupIM</span></span>
    
- <span data-ttu-id="d883e-149">P2PAV （对等音频/视频会话）</span><span class="sxs-lookup"><span data-stu-id="d883e-149">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="d883e-150">AvConference （音频/会议）</span><span class="sxs-lookup"><span data-stu-id="d883e-150">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="d883e-151">状态</span><span class="sxs-lookup"><span data-stu-id="d883e-151">Presence</span></span>
    
- <span data-ttu-id="d883e-152">ABS （通讯簿服务）</span><span class="sxs-lookup"><span data-stu-id="d883e-152">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="d883e-153">ABWQ （地址簿 web 服务）</span><span class="sxs-lookup"><span data-stu-id="d883e-153">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="d883e-154">默认情况下，下列组件也不会测试：</span><span class="sxs-lookup"><span data-stu-id="d883e-154">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="d883e-155">ASConference</span><span class="sxs-lookup"><span data-stu-id="d883e-155">ASConference</span></span>
    
- <span data-ttu-id="d883e-156">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="d883e-156">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="d883e-157">DataConference</span><span class="sxs-lookup"><span data-stu-id="d883e-157">DataConference</span></span>
    
- <span data-ttu-id="d883e-158">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="d883e-158">DialinConferencing</span></span>
    
- <span data-ttu-id="d883e-159">ExumConnectivity （Exchange 统一消息）</span><span class="sxs-lookup"><span data-stu-id="d883e-159">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="d883e-160">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="d883e-160">JoinLauncher</span></span>
    
- <span data-ttu-id="d883e-161">MCXP2PIM （移动设备即时消息）</span><span class="sxs-lookup"><span data-stu-id="d883e-161">MCXP2PIM (mobile device instant messaging)</span></span>
    
- <span data-ttu-id="d883e-162">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="d883e-162">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="d883e-163">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d883e-163">PersistentChatMessage</span></span>
    
- <span data-ttu-id="d883e-164">PSTN （PSTN 网关呼叫，指定为扩展测试）</span><span class="sxs-lookup"><span data-stu-id="d883e-164">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="d883e-165">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="d883e-165">UcwaConference</span></span>
    
- <span data-ttu-id="d883e-166">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="d883e-166">UnifiedContactStore</span></span>
    
- <span data-ttu-id="d883e-167">XmppIM</span><span class="sxs-lookup"><span data-stu-id="d883e-167">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="d883e-168">添加和移除综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-168">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="d883e-169">观察者节点配置后，可以使用一组 CsWatcherNodeConfiguration cmdlet 以添加或删除节点的综合事务。</span><span class="sxs-lookup"><span data-stu-id="d883e-169">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="d883e-170">例如，若要向观察者节点的 PersistentChatMessage 测试，使用 Add 方法并与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-170">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="d883e-171">可以通过用逗号隔开的测试名称添加多个测试。</span><span class="sxs-lookup"><span data-stu-id="d883e-171">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="d883e-172">例如：</span><span class="sxs-lookup"><span data-stu-id="d883e-172">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="d883e-173">如果一个或多个这些测试 (例如，DataConference) 已经在观察程序节点上已启用，则将发生错误。</span><span class="sxs-lookup"><span data-stu-id="d883e-173">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="d883e-174">在这种情况下，您将收到类似于以下的错误信息：</span><span class="sxs-lookup"><span data-stu-id="d883e-174">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="d883e-175">组-CsWatcherNodeConfiguration： 没有重复的键序列 DataConference urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName 键或唯一标识约束。</span><span class="sxs-lookup"><span data-stu-id="d883e-175">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="d883e-176">发生此错误时，会不应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="d883e-176">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="d883e-177">应与删除重复测试重新运行该命令。</span><span class="sxs-lookup"><span data-stu-id="d883e-177">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="d883e-178">要从观察者节点删除综合事务处理，请使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="d883e-178">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="d883e-179">例如，此命令将从观察者节点删除 ABWQ 测试：</span><span class="sxs-lookup"><span data-stu-id="d883e-179">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="d883e-180">Replace 方法可用于替换所有当前已启用的测试与一个或更多新的测试。</span><span class="sxs-lookup"><span data-stu-id="d883e-180">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="d883e-181">例如，如果您希望只是为了运行 IM 测试观察程序节点，您可以配置，使用此命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-181">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="d883e-182">当您运行此命令时，指定观察程序节点上的所有综合事务将被禁用，除了 IM。</span><span class="sxs-lookup"><span data-stu-id="d883e-182">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="d883e-183">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="d883e-183">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="d883e-184">如果您想要查看已分配给观察者节点测试，使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-184">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="d883e-185">此命令将返回的信息类似，具体取决于已分配给节点的综合交易记录：</span><span class="sxs-lookup"><span data-stu-id="d883e-185">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="d883e-186">注册 IM GroupIM P2PAV AvConference 出席 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="d883e-186">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="d883e-187">若要按字母顺序查看综合事务，而是使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-187">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="d883e-188">来验证已创建了一个观察程序节点，请键入下面的命令从 Skype 业务服务器管理外壳程序：</span><span class="sxs-lookup"><span data-stu-id="d883e-188">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="d883e-189">您将得到的信息与以下类似：</span><span class="sxs-lookup"><span data-stu-id="d883e-189">You will get back information similar to this:</span></span>
  
<span data-ttu-id="d883e-190">身份： atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com、 sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="d883e-190">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="d883e-191">ExtendedTests: {TestUsers = IList < System.String >;名称 = PSTN 测试;Te...}</span><span class="sxs-lookup"><span data-stu-id="d883e-191">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="d883e-192">TargetFqdn: atl-cs-001.litwareinc.com 端口号： 5061To 验证观察程序节点是否已配置正确，键入下面的命令从 Skype 业务服务器管理外壳程序：</span><span class="sxs-lookup"><span data-stu-id="d883e-192">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="d883e-193">此命令将在您的部署中测试每个观察者节点并确认是否已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="d883e-193">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="d883e-194">安装所需的注册器角色</span><span class="sxs-lookup"><span data-stu-id="d883e-194">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="d883e-195">创建必需的注册表项 （完成时运行一组 CsWatcherNodeConfiguration cmdlet）</span><span class="sxs-lookup"><span data-stu-id="d883e-195">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="d883e-196">您的服务器业务服务器运行 Skype 的正确版本</span><span class="sxs-lookup"><span data-stu-id="d883e-196">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="d883e-197">您的端口已正确配置</span><span class="sxs-lookup"><span data-stu-id="d883e-197">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="d883e-198">分配的测试用户具有所需的凭据</span><span class="sxs-lookup"><span data-stu-id="d883e-198">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="d883e-199">管理观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d883e-199">Managing Watcher Nodes</span></span>
<span data-ttu-id="d883e-200"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d883e-200"></span></span>

<span data-ttu-id="d883e-201">除了修改综合观察程序节点执行的事务，还可以使用**一组 CsWatcherNodeConfiguration** cmdlet 执行两项重要任务： 启用和禁用的观察程序节点，以及配置要在运行测试时使用内部 Web Url 或外部的 Web Url 的观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="d883e-201">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="d883e-202">默认情况下，旨在定期运行其所有已启用的综合事务观察者节点。</span><span class="sxs-lookup"><span data-stu-id="d883e-202">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="d883e-203">有时，但是，您可能需要挂起这些交易记录。</span><span class="sxs-lookup"><span data-stu-id="d883e-203">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="d883e-204">例如，如果观察者节点暂时从网络上断开，则没有必要运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="d883e-204">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="d883e-205">没有网络连接，这些事务将失败。</span><span class="sxs-lookup"><span data-stu-id="d883e-205">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="d883e-206">若要暂时禁用观察程序节点，请运行业务服务器管理外壳从 Skype 与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d883e-206">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="d883e-207">此命令将禁用上观察程序节点 atl 观察程序 001.litwareinc.com 的综合事务的执行。若要继续执行综合事务，可用属性重新设置为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="d883e-207">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="d883e-208">可用属性可用于打开或关闭的观察者节点。</span><span class="sxs-lookup"><span data-stu-id="d883e-208">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="d883e-209">如果您想要永久删除观察者节点，使用**删除 CsWatcherNodeConfiguration** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d883e-209">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="d883e-210">该命令从指定的计算机，这样可以防止该计算机自动运行综合事务中删除所有的观察者节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="d883e-210">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="d883e-211">但是，该命令不会卸载系统中心代理文件或 Skype 业务服务器 2015年系统文件。</span><span class="sxs-lookup"><span data-stu-id="d883e-211">However, the command does not uninstall the System Center agent files or the Skype for Business Server 2015 system files.</span></span>
  
<span data-ttu-id="d883e-212">默认情况下，观察者节点进行测试时使用组织的外部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="d883e-212">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="d883e-213">但是，观察者节点，也可以配置为使用组织的内部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="d883e-213">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="d883e-214">这使管理员可以验证 URL 位于周边网络内的用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d883e-214">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="d883e-215">配置要使用内部 Url 而不是外部 Url，请将 UseInternalWebURls 属性设置为 True ($True) 的观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="d883e-215">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="d883e-216">正在此属性重置为 False ($False) 的默认值将导致观察程序再次使用外部 Url:</span><span class="sxs-lookup"><span data-stu-id="d883e-216">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="d883e-217">综合事务的特殊安装说明</span><span class="sxs-lookup"><span data-stu-id="d883e-217">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="d883e-218"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d883e-218"></span></span>

<span data-ttu-id="d883e-219">大多数的综合事务可以作为观察者节点上运行的是。</span><span class="sxs-lookup"><span data-stu-id="d883e-219">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="d883e-220">在大多数情况下，只要综合事务添加到观察程序节点配置设置，观察程序节点可以使用综合事务在其测试期间传递。</span><span class="sxs-lookup"><span data-stu-id="d883e-220">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="d883e-221">但是，有一些综合事务需要特殊的安装说明进行操作，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="d883e-221">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="d883e-222">数据会议综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-222">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="d883e-223">如果您观察程序节点计算机位于外围网络以外，您将可能不能运行数据会议综合事务，除非您先禁用网络的 Windows Internet Explorer® Internet 浏览器代理服务器设置服务帐户通过完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d883e-223">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="d883e-224">在观察程序节点计算机上，单击**开始**，单击**所有程序**，都单击**附件**、 右键都单击**命令提示符**下，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="d883e-224">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="d883e-225">在控制台窗口中，键入以下命令，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="d883e-225">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="d883e-226">您将看到在命令窗口中显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="d883e-226">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="d883e-227">BITSAdmin 已被否决，并不能保证在未来版本的 Windows 中不可用。</span><span class="sxs-lookup"><span data-stu-id="d883e-227">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="d883e-228">现在由位 PowerShell cmdlet 提供用于 BITS 服务管理工具。</span><span class="sxs-lookup"><span data-stu-id="d883e-228">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="d883e-229">因特网代理设置为网络服务帐户设置为 NO_PROXY。</span><span class="sxs-lookup"><span data-stu-id="d883e-229">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="d883e-230">(连接 = 默认值)</span><span class="sxs-lookup"><span data-stu-id="d883e-230">(connection = default)</span></span>
  
<span data-ttu-id="d883e-231">此消息表明您已禁用 Internet Explorer 代理设置为网络服务帐户。</span><span class="sxs-lookup"><span data-stu-id="d883e-231">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="d883e-232">Exchange 统一消息综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-232">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="d883e-233">Exchange 统一消息 (UM) 综合事务验证测试用户可以连接到语音邮件帐户驻留在 Exchange。</span><span class="sxs-lookup"><span data-stu-id="d883e-233">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="d883e-234">测试用户将需要进行预配置语音邮件帐户了。</span><span class="sxs-lookup"><span data-stu-id="d883e-234">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="d883e-235">持续聊天综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-235">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="d883e-236">若要使用持久聊天综合事务，首先要创建一个通道，并授予用户权限以使用它的测试。</span><span class="sxs-lookup"><span data-stu-id="d883e-236">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="d883e-237">您可以使用持久聊天综合事务配置此通道：</span><span class="sxs-lookup"><span data-stu-id="d883e-237">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true

```

<span data-ttu-id="d883e-238">您必须运行此安装程序必须从企业内部运行任务：</span><span class="sxs-lookup"><span data-stu-id="d883e-238">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="d883e-239">如果从非服务器计算机上运行，执行该 cmdlet 的用户必须是基于角色的访问控制 (RBAC) CsPersistentChatAdministrators 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d883e-239">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="d883e-240">如果从该服务器本身运行，执行该 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="d883e-240">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="d883e-241">PSTN 呼叫对等综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-241">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="d883e-242">测试 CsPstnPeerToPeerCall 综合事务验证发出和接收呼叫通过公用交换的电话网 (PSTN) 的能力。</span><span class="sxs-lookup"><span data-stu-id="d883e-242">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="d883e-243">若要运行此综合交易记录，您必须配置：</span><span class="sxs-lookup"><span data-stu-id="d883e-243">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="d883e-244">两个统一通信启用测试用户 （调用方和接收方）。</span><span class="sxs-lookup"><span data-stu-id="d883e-244">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="d883e-245">直接向内拨号 (DID) 编号，为每个用户帐户的。</span><span class="sxs-lookup"><span data-stu-id="d883e-245">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="d883e-246">允许接收方的号码呼叫到达 PSTN 网关的 VoIP 策略和语音路由。</span><span class="sxs-lookup"><span data-stu-id="d883e-246">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="d883e-247">拨打 PSTN 网关，接受呼叫，并将路由调用返回到接收方的主池，根据数量的媒体。</span><span class="sxs-lookup"><span data-stu-id="d883e-247">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="d883e-248">统一联系人存储库综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-248">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="d883e-249">综合统一联系人存储交易记录验证业务服务器 2015 从 Exchange 中检索联系人代表用户的 Skype 的能力。</span><span class="sxs-lookup"><span data-stu-id="d883e-249">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server 2015 to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="d883e-250">若要使用此综合交易记录，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="d883e-250">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="d883e-251">必须配置 Lyss Exchange 服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="d883e-251">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="d883e-252">测试的用户必须具有有效的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="d883e-252">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="d883e-253">满足这些条件后，您可以运行下面的 Windows PowerShell cmdlet，要迁移到 Exchange 的测试用户的联系人列表：</span><span class="sxs-lookup"><span data-stu-id="d883e-253">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="d883e-254">它需要一些时间测试的用户迁移到 Exchange 的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="d883e-254">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="d883e-255">若要监视的迁移进度，相同的命令行可以运行没有-设置标记：</span><span class="sxs-lookup"><span data-stu-id="d883e-255">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="d883e-256">迁移完成后，此命令行中将会成功。</span><span class="sxs-lookup"><span data-stu-id="d883e-256">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="d883e-257">XMPP 综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-257">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="d883e-258">可扩展的消息传递和在线协议 (XMPP) IM 综合事务需要与一个或多个联盟域配置 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="d883e-258">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="d883e-259">要启用 XMPP 综合事务，必须提供一个 XmppTestReceiverMailAddress 参数可穿绕的 XMPP 域的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d883e-259">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="d883e-260">例如：</span><span class="sxs-lookup"><span data-stu-id="d883e-260">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="d883e-261">在此示例中，Skype 业务服务器 2015年规则将需要将消息路由到 XMPP 网关 litwareinc.com 的存在</span><span class="sxs-lookup"><span data-stu-id="d883e-261">In this example, a Skype for Business Server 2015 rule will need to exist to route messages for litwareinc.com to an XMPP gateway</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="d883e-262">互操作的视频服务器 (VIS) 综合事务</span><span class="sxs-lookup"><span data-stu-id="d883e-262">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="d883e-263">视频服务器互操作 (VIS) 综合事务都要求您下载并安装综合事务的支持文件 ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921))。</span><span class="sxs-lookup"><span data-stu-id="d883e-263">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="d883e-264">要安装 VISSTSupportPackage.msi 确保为已安装 msi 的依赖项 （在系统要求）。</span><span class="sxs-lookup"><span data-stu-id="d883e-264">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="d883e-265">运行 VISSTSupportPackage.msi 进行简单的安装。</span><span class="sxs-lookup"><span data-stu-id="d883e-265">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="d883e-266">.Msi 文件安装在以下路径中的所有文件:"%ProgramFiles%\VIS 综合事务支持包"。</span><span class="sxs-lookup"><span data-stu-id="d883e-266">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="d883e-267">有关如何运行 VIS 综合事务的更多详细信息请参阅[测试 CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="d883e-267">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="d883e-268">综合事务更改运行的频率</span><span class="sxs-lookup"><span data-stu-id="d883e-268">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="d883e-269"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d883e-269"></span></span>

<span data-ttu-id="d883e-270">默认情况下，综合事务将运行与已配置用户每隔 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="d883e-270">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="d883e-271">综合事务是一组用户，以避免彼此发生冲突的两个综合事务中按顺序运行。</span><span class="sxs-lookup"><span data-stu-id="d883e-271">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="d883e-272">较长的间隔需要提供所有的综合事务完成的时间。</span><span class="sxs-lookup"><span data-stu-id="d883e-272">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="d883e-273">如果需要更频繁地运行综合事务，以便一些偶尔的网络延迟的缓冲区所需的时间范围内完成测试应减少综合使用一组给定的用户运行的事务数。</span><span class="sxs-lookup"><span data-stu-id="d883e-273">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="d883e-274">如果运行多个综合事务是理想，创建更多的用户集来运行其他综合事务。</span><span class="sxs-lookup"><span data-stu-id="d883e-274">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="d883e-275">若要更改的综合事务运行的频率，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d883e-275">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="d883e-276">开放式系统中心操作管理器。</span><span class="sxs-lookup"><span data-stu-id="d883e-276">Open System Center Operations Manager.</span></span> <span data-ttu-id="d883e-277">单击创作节。</span><span class="sxs-lookup"><span data-stu-id="d883e-277">Click Authoring section.</span></span> <span data-ttu-id="d883e-278">单击规则部分 （下创作）</span><span class="sxs-lookup"><span data-stu-id="d883e-278">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="d883e-279">在规则部分中，查找名为"Main 综合事务流道性能收集规则"规则</span><span class="sxs-lookup"><span data-stu-id="d883e-279">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="d883e-280">鼠标右键单击该规则，并选择重写，重写规则，选择，然后选择"类的所有对象： 池观察程序"</span><span class="sxs-lookup"><span data-stu-id="d883e-280">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="d883e-281">重写属性窗口中选择参数名称"频率"，并设置到所需的替代值。</span><span class="sxs-lookup"><span data-stu-id="d883e-281">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="d883e-282">在同一个窗口中，选择此重写需要应用的管理包</span><span class="sxs-lookup"><span data-stu-id="d883e-282">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="d883e-283">使用综合事务日志记录格式</span><span class="sxs-lookup"><span data-stu-id="d883e-283">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="d883e-284"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d883e-284"></span></span>

<span data-ttu-id="d883e-285">综合事务证明有助于确定与系统问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="d883e-285">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="d883e-286">例如，测试 CsRegistration cmdlet 可能警告管理员用户都遇到了困难与 Skype 业务服务器注册的事实。</span><span class="sxs-lookup"><span data-stu-id="d883e-286">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="d883e-287">但是，可能需要更多详细信息以确定故障的真实原因。</span><span class="sxs-lookup"><span data-stu-id="d883e-287">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="d883e-288">由于这个原因，综合事务提供丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="d883e-288">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="d883e-289">丰富的记录，为综合事务承担，每个活动记录以下信息：</span><span class="sxs-lookup"><span data-stu-id="d883e-289">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="d883e-290">活动开始的时间。</span><span class="sxs-lookup"><span data-stu-id="d883e-290">The time that the activity started.</span></span>
    
- <span data-ttu-id="d883e-291">活动结束的时间。</span><span class="sxs-lookup"><span data-stu-id="d883e-291">The time that the activity finished.</span></span>
    
- <span data-ttu-id="d883e-292">已执行的操作 (例如，创建、 加入，或离开会议; 到 Skype 业务服务器签名; 发送即时消息)。</span><span class="sxs-lookup"><span data-stu-id="d883e-292">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="d883e-293">信息性、 详细信息; 警告或活动运行时生成的错误消息</span><span class="sxs-lookup"><span data-stu-id="d883e-293">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="d883e-294">SIP 注册消息。</span><span class="sxs-lookup"><span data-stu-id="d883e-294">SIP registration messages.</span></span>
    
- <span data-ttu-id="d883e-295">异常错误记录或活动运行时生成的诊断代码。</span><span class="sxs-lookup"><span data-stu-id="d883e-295">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="d883e-296">正在运行活动的最终结果。</span><span class="sxs-lookup"><span data-stu-id="d883e-296">The net result of running the activity.</span></span>
    
<span data-ttu-id="d883e-297">此信息自动生成的每次运行时的综合事务，但不是会自动显示或保存到日志文件。</span><span class="sxs-lookup"><span data-stu-id="d883e-297">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d883e-298">如果您手动运行综合事务，您可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="d883e-298">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d883e-299">从那里，您可以选择使用两种方法之一保存和/或富中的查看错误消息日志以 XML 或 HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="d883e-299">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="d883e-300">若要检索的疑难解答信息，请指定 OutLoggerVariable 参数，跟您选择的变量名：</span><span class="sxs-lookup"><span data-stu-id="d883e-300">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="d883e-301">： 前面使用 $ 字符的变量名。</span><span class="sxs-lookup"><span data-stu-id="d883e-301">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="d883e-302">使用的变量名称，如 RegistrationTest (而不是 $RegistrationTest)。</span><span class="sxs-lookup"><span data-stu-id="d883e-302">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="d883e-303">当您运行此命令时，您会看到类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d883e-303">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="d883e-304">目标 Fqdn: atl-cs-001.litwareinc.com 结果： 故障延迟时间： 00:00:00 的错误消息： 此计算机不具有任何已分配的证书。</span><span class="sxs-lookup"><span data-stu-id="d883e-304">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="d883e-305">诊断： 可以访问此故障比只是此处所示的错误消息的更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="d883e-305">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="d883e-306">若要访问此信息在 HTML 格式，使用类似于此的命令保存到 HTML 文件的 RegistrationTest 变量中存储的信息：</span><span class="sxs-lookup"><span data-stu-id="d883e-306">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="d883e-307">或者，您可以使用 ToXML() 方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="d883e-307">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="d883e-308">您可以通过使用 Windows Internet Explorer、 Microsoft Visual Studio 或任何其他应用程序能够打开 HTML/XML 文件来查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="d883e-308">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="d883e-309">综合事务从运行在系统中心操作管理器将自动生成这些日志文件失败。</span><span class="sxs-lookup"><span data-stu-id="d883e-309">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d883e-310">如果前业务服务器 PowerShell 的 Skype 是能够加载并运行综合事务执行失败，将不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="d883e-310">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d883e-311">默认情况下，业务服务器 2015年的 Skype 将日志文件保存到未共享的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d883e-311">By default, Skype for Business Server 2015 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d883e-312">若要使这些日志可随时访问，应共享此文件夹。</span><span class="sxs-lookup"><span data-stu-id="d883e-312">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="d883e-313">例如： \\atl-watcher-001.litwareinc.com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="d883e-313">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
  

