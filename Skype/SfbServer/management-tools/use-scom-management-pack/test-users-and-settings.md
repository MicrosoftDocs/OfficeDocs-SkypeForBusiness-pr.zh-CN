---
title: 配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 摘要： 配置测试用户帐户和业务服务器综合事务的 Skype 的观察程序节点设置。
ms.openlocfilehash: f1f80632c20212a1aa9a78bc272a8bc6340c9366
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904165"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="36ba2-103">配置观察程序节点测试用户和设置</span><span class="sxs-lookup"><span data-stu-id="36ba2-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="36ba2-104">**摘要：** 配置测试用户帐户和业务服务器综合事务的 Skype 的观察程序节点设置。</span><span class="sxs-lookup"><span data-stu-id="36ba2-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="36ba2-105">配置将充当观察程序节点计算机之后，您必须：</span><span class="sxs-lookup"><span data-stu-id="36ba2-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="36ba2-106">[配置测试用户帐户](test-users-and-settings.md#testuser)，使用这些观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="36ba2-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="36ba2-107">如果您使用的协商身份验证方法，您还必须使用**Set-cstestusercredential** cmdlet 来启用这些测试观察程序节点上使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="36ba2-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="36ba2-108">更新观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="36ba2-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="36ba2-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="36ba2-109">Configure Test User Accounts</span></span>
<span data-ttu-id="36ba2-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="36ba2-110"></span></span>

<span data-ttu-id="36ba2-111">测试帐户不需要表示实际的人员，但他们必须是有效的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="36ba2-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="36ba2-112">此外，这些帐户必须为 Business Server 启用的 Skype、 它们必须具有有效的 SIP 地址和它们应启用企业语音 （以便使用 Test-cspstnpeertopeercall 综合事务）。</span><span class="sxs-lookup"><span data-stu-id="36ba2-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="36ba2-113">如果您使用的 TrustedServer 身份验证方法，您需要执行所有是确保这些帐户存在，并将其如前所述配置。</span><span class="sxs-lookup"><span data-stu-id="36ba2-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="36ba2-114">为每个要测试的池的至少两个测试用户，您应将其分配。</span><span class="sxs-lookup"><span data-stu-id="36ba2-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="36ba2-115">如果您使用的协商身份验证方法，您还必须使用 Set-cstestusercredential cmdlet 和业务 Server 命令行管理程序启用这些 Skype 测试帐户的综合事务处理。</span><span class="sxs-lookup"><span data-stu-id="36ba2-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="36ba2-116">执行此操作通过运行类似以下 （这些命令假定已创建了两个 Active Directory 用户帐户并为业务服务器的 Skype 启用这些帐户） 的命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="36ba2-117">您必须包括不仅的 SIP 地址，但还用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="36ba2-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="36ba2-118">如果不包括密码，Set-cstestusercredential cmdlet 将提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="36ba2-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="36ba2-119">可以通过使用前面的代码块中所示的域 name\user 名称格式指定的用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="36ba2-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="36ba2-120">若要验证已创建的测试用户凭据，请从 Skype 的业务 Server 命令行管理程序运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="36ba2-121">为每个用户，将返回类似于以下的信息：</span><span class="sxs-lookup"><span data-stu-id="36ba2-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="36ba2-122">**用户名**</span><span class="sxs-lookup"><span data-stu-id="36ba2-122">**UserName**</span></span>|<span data-ttu-id="36ba2-123">**密码**</span><span class="sxs-lookup"><span data-stu-id="36ba2-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36ba2-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="36ba2-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="36ba2-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="36ba2-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="36ba2-126">使用默认综合事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="36ba2-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="36ba2-127">创建测试用户之后，您可以使用类似如下的命令创建观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="36ba2-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="36ba2-128">此命令创建一个新的观察程序节点的使用默认设置并在运行综合事务的默认设置。</span><span class="sxs-lookup"><span data-stu-id="36ba2-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="36ba2-129">新的观察程序节点还使用的测试用户 watcher1@litwareinc.com 和 watcher2@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="36ba2-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="36ba2-130">如果观察程序节点使用 TrustedServer 身份验证，两个测试帐户可以是任何有效的用户帐户启用 Active Directory 和 Skype 业务 Server。</span><span class="sxs-lookup"><span data-stu-id="36ba2-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="36ba2-131">如果观察程序节点使用的协商身份验证方法，这些用户帐户必须也启用观察程序节点使用 Set-cstestusercredential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="36ba2-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="36ba2-132">若要验证目标的自动发现登录的池已正确配置，而不是直接目标池改为使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="36ba2-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="36ba2-133">配置扩展的测试</span><span class="sxs-lookup"><span data-stu-id="36ba2-133">Configuring Extended Tests</span></span>

<span data-ttu-id="36ba2-134">如果您想要启用 PSTN 测试，验证与公用电话交换网的连接，您需要执行其他一些配置设置的观察程序节点时。</span><span class="sxs-lookup"><span data-stu-id="36ba2-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="36ba2-135">首先，必须通过运行 Business Server 命令行管理程序从 Skype 类似于以下命令将测试用户与 PSTN 测试类型关联：</span><span class="sxs-lookup"><span data-stu-id="36ba2-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="36ba2-136">此命令的结果必须存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="36ba2-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="36ba2-137">本示例中，该变量名为 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="36ba2-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="36ba2-138">接下来，您可以使用**New-cswatchernodeconfiguration** cmdlet 将业务服务器池 Skype 的测试类型 （存储在变量 $pstnTest） 相关联。</span><span class="sxs-lookup"><span data-stu-id="36ba2-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="36ba2-139">例如，以下命令创建新观察程序节点配置的池 atl-cs-001.litwareinc.com，添加两个测试用户之前，创建和添加 PSTN 测试类型：</span><span class="sxs-lookup"><span data-stu-id="36ba2-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="36ba2-140">如果您尚未安装 Skype 业务 Server 核心文件和 RTCLocal 数据库在观察程序节点计算机上，上述命令将失败。</span><span class="sxs-lookup"><span data-stu-id="36ba2-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="36ba2-141">若要测试多个语音策略，可以使用**New-csextendedtest** cmdlet 创建每个策略扩展的的测试。</span><span class="sxs-lookup"><span data-stu-id="36ba2-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="36ba2-142">应与所需的语音策略配置提供的用户。</span><span class="sxs-lookup"><span data-stu-id="36ba2-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="36ba2-143">扩展的测试传递到**New-cswatchernodeconfiguration** cmdlet 通过使用逗号分隔的分隔符，如：</span><span class="sxs-lookup"><span data-stu-id="36ba2-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="36ba2-144">-ExtendedTests @{添加 = $pstnTest1$ pstnTest2、 $pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="36ba2-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="36ba2-145">由于无需使用 Tests 参数调用**New-cswatchernodeconfiguration** cmdlet，将为新观察程序节点启用仅默认综合事务 （和指定的扩展综合事务）。</span><span class="sxs-lookup"><span data-stu-id="36ba2-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="36ba2-146">因此，观察程序节点将测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="36ba2-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="36ba2-147">注册</span><span class="sxs-lookup"><span data-stu-id="36ba2-147">Registration</span></span>
    
- <span data-ttu-id="36ba2-148">即时消息</span><span class="sxs-lookup"><span data-stu-id="36ba2-148">IM</span></span>
    
- <span data-ttu-id="36ba2-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="36ba2-149">GroupIM</span></span>
    
- <span data-ttu-id="36ba2-150">P2PAV （对等音频/视频会话）</span><span class="sxs-lookup"><span data-stu-id="36ba2-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="36ba2-151">AvConference （音频/会议）</span><span class="sxs-lookup"><span data-stu-id="36ba2-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="36ba2-152">状态</span><span class="sxs-lookup"><span data-stu-id="36ba2-152">Presence</span></span>
    
- <span data-ttu-id="36ba2-153">ABS （通讯簿服务）</span><span class="sxs-lookup"><span data-stu-id="36ba2-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="36ba2-154">ABWQ （通讯簿 web 服务）</span><span class="sxs-lookup"><span data-stu-id="36ba2-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="36ba2-155">默认情况下不会测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="36ba2-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="36ba2-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="36ba2-156">ASConference</span></span>
    
- <span data-ttu-id="36ba2-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="36ba2-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="36ba2-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="36ba2-158">DataConference</span></span>
    
- <span data-ttu-id="36ba2-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="36ba2-159">DialinConferencing</span></span>
    
- <span data-ttu-id="36ba2-160">ExumConnectivity （Exchange 统一消息）</span><span class="sxs-lookup"><span data-stu-id="36ba2-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="36ba2-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="36ba2-161">JoinLauncher</span></span>
    
- <span data-ttu-id="36ba2-162">MCXP2PIM （旧的移动设备即时消息）</span><span class="sxs-lookup"><span data-stu-id="36ba2-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="36ba2-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="36ba2-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="36ba2-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="36ba2-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="36ba2-165">PSTN （PSTN 网关呼叫，作为扩展测试指定）</span><span class="sxs-lookup"><span data-stu-id="36ba2-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="36ba2-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="36ba2-166">UcwaConference</span></span>
    
- <span data-ttu-id="36ba2-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="36ba2-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="36ba2-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="36ba2-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="36ba2-169">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="36ba2-170">在配置观察程序节点之后，您可以使用 Set-cswatchernodeconfiguration cmdlet 添加或删除节点的综合事务。</span><span class="sxs-lookup"><span data-stu-id="36ba2-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="36ba2-171">例如，若要添加到观察程序节点 PersistentChatMessage 测试，使用 Add 方法和类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="36ba2-172">通过使用逗号分隔的测试名称可以添加多个测试。</span><span class="sxs-lookup"><span data-stu-id="36ba2-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="36ba2-173">例如：</span><span class="sxs-lookup"><span data-stu-id="36ba2-173">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="36ba2-174">如果一个或多个这些测试 (例如，DataConference) 已启用观察程序节点上，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="36ba2-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="36ba2-175">在这种情况下，您会收到类似于以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="36ba2-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="36ba2-176">Set-cswatchernodeconfiguration： 没有重复的键序列 DataConference' 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName 键或唯一标识约束。</span><span class="sxs-lookup"><span data-stu-id="36ba2-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="36ba2-177">发生此错误时，将不应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="36ba2-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="36ba2-178">应与重复测试删除重新运行该命令。</span><span class="sxs-lookup"><span data-stu-id="36ba2-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="36ba2-179">若要从观察程序节点删除综合事务，请使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="36ba2-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="36ba2-180">例如，此命令会删除 ABWQ 测试从观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="36ba2-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="36ba2-181">您可以使用 Replace 方法替换所有当前已启用的测试与一个或更多新测试。</span><span class="sxs-lookup"><span data-stu-id="36ba2-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="36ba2-182">例如，如果您希望仅来运行该 IM 测试观察程序节点，您可以配置的使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="36ba2-183">运行此命令时，除了 IM 以外，将禁用指定观察程序节点上的所有综合事务。</span><span class="sxs-lookup"><span data-stu-id="36ba2-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="36ba2-184">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="36ba2-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="36ba2-185">如果您想要查看已分配给观察程序节点测试，使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="36ba2-186">此命令将返回信息类似于以下，具体取决于已分配给节点的综合事务：</span><span class="sxs-lookup"><span data-stu-id="36ba2-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="36ba2-187">注册 IM GroupIM P2PAV AvConference 状态 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="36ba2-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="36ba2-188">若要按字母顺序查看综合事务，请改为使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="36ba2-189">若要验证已创建观察程序节点，键入业务 Server 命令行管理程序从 Skype 以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="36ba2-190">您将获得信息类似如下：</span><span class="sxs-lookup"><span data-stu-id="36ba2-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="36ba2-191">标识： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36ba2-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="36ba2-192">TestUsers: {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="36ba2-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="36ba2-193">ExtendedTests: {TestUsers=IList<System.String>;名称 = PSTN 测试;Te...}</span><span class="sxs-lookup"><span data-stu-id="36ba2-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="36ba2-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="36ba2-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="36ba2-195">端口号： 5061</span><span class="sxs-lookup"><span data-stu-id="36ba2-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="36ba2-196">若要验证已正确配置观察程序节点，键入业务 Server 命令行管理程序从 Skype 以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="36ba2-197">此命令将测试您的部署中的每个观察程序节点，并确认是否已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="36ba2-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="36ba2-198">安装所需的注册器角色。</span><span class="sxs-lookup"><span data-stu-id="36ba2-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="36ba2-199">创建必需的注册表项 （完成您运行 Set-cswatchernodeconfiguration cmdlet 时）。</span><span class="sxs-lookup"><span data-stu-id="36ba2-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="36ba2-200">您的服务器的企业服务器运行 Skype 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="36ba2-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="36ba2-201">您的端口配置正确。</span><span class="sxs-lookup"><span data-stu-id="36ba2-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="36ba2-202">您已分配的测试用户具有所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="36ba2-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="36ba2-203">管理观察程序节点</span><span class="sxs-lookup"><span data-stu-id="36ba2-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="36ba2-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="36ba2-204"></span></span>

<span data-ttu-id="36ba2-205">除了修改执行观察程序节点的综合事务，您可以使用**Set-cswatchernodeconfiguration** cmdlet 执行两个其他重要任务： 启用和禁用观察程序节点，以及配置运行测试时，使用内部 Web Url 或外部 Web Url 的观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="36ba2-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="36ba2-206">默认情况下，旨在定期运行其所有已启用的综合事务观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="36ba2-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="36ba2-207">有时，但是，您可能想要暂停这些事务。</span><span class="sxs-lookup"><span data-stu-id="36ba2-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="36ba2-208">例如，如果从网络上暂时断开观察程序节点，则没有理由运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="36ba2-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="36ba2-209">没有网络连接，这些事务将失败。</span><span class="sxs-lookup"><span data-stu-id="36ba2-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="36ba2-210">要暂时禁用观察程序节点，请对业务 Server 命令行管理程序运行从 Skype 类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="36ba2-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="36ba2-211">此命令将禁用综合事务观察程序节点 atl 观察程序 001.litwareinc.com 上的执行。</span><span class="sxs-lookup"><span data-stu-id="36ba2-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="36ba2-212">若要继续执行的综合事务，设置 Enabled 属性返回为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="36ba2-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="36ba2-213">Enabled 属性可用于打开或关闭观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="36ba2-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="36ba2-214">如果您想要永久删除观察程序节点，使用**Remove-cswatchernodeconfiguration** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="36ba2-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="36ba2-215">该命令删除指定的计算机，这样可以防止在该计算机自动运行综合事务的所有观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="36ba2-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="36ba2-216">但是，该命令不会卸载 System Center 代理文件或业务 Server 系统文件 Skype。</span><span class="sxs-lookup"><span data-stu-id="36ba2-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="36ba2-217">默认情况下，观察程序节点使用组织的外部 Web Url 时进行测试。</span><span class="sxs-lookup"><span data-stu-id="36ba2-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="36ba2-218">但是，观察程序节点，还可以配置为使用组织的内部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="36ba2-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="36ba2-219">这使管理员可以确认 for 位于外围网络的用户的 URL 访问。</span><span class="sxs-lookup"><span data-stu-id="36ba2-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="36ba2-220">若要配置观察程序节点以使用内部 Url，而不是外部 Url，请将 UseInternalWebURls 属性设置为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="36ba2-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="36ba2-221">重置为默认值为 false，表示 ($False) 的此属性将导致观察程序再次使用的外部 Url:</span><span class="sxs-lookup"><span data-stu-id="36ba2-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="36ba2-222">综合事务的特殊设置说明</span><span class="sxs-lookup"><span data-stu-id="36ba2-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="36ba2-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="36ba2-223"></span></span>

<span data-ttu-id="36ba2-224">大多数综合事务可以作为观察程序节点上运行的是。</span><span class="sxs-lookup"><span data-stu-id="36ba2-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="36ba2-225">在大多数情况下，只要综合事务将添加到观察程序节点配置设置，观察程序节点可以开始的使用其测试期间的综合事务将传递。</span><span class="sxs-lookup"><span data-stu-id="36ba2-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="36ba2-226">但是，有一些综合事务需要特殊设置说明的以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="36ba2-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="36ba2-227">数据会议综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-228">如果您观察程序节点计算机位于外围网络外，您将可能无法运行数据会议综合事务，除非您先禁用网络的 Windows Internet Explorer® Internet 浏览器代理设置通过完成以下步骤的服务帐户：</span><span class="sxs-lookup"><span data-stu-id="36ba2-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="36ba2-229">在观察程序节点计算机上，表中，单击**开始**、 单击**所有程序**，都单击**附件**数据，右键都单击**命令提示符处**，，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="36ba2-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="36ba2-230">在控制台窗口中，键入以下命令，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="36ba2-230">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="36ba2-231">您将看到命令窗口中显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="36ba2-231">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="36ba2-232">BITSAdmin 已弃用，不保证在将来版本的 Windows 中不可用。</span><span class="sxs-lookup"><span data-stu-id="36ba2-232">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="36ba2-233">现在由位 PowerShell cmdlet 提供 BITS 服务管理工具。</span><span class="sxs-lookup"><span data-stu-id="36ba2-233">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="36ba2-234">Internet NetworkService 帐户的代理设置设置为 NO_PROXY。</span><span class="sxs-lookup"><span data-stu-id="36ba2-234">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="36ba2-235">(连接 = 默认值)</span><span class="sxs-lookup"><span data-stu-id="36ba2-235">(connection = default)</span></span>
  
<span data-ttu-id="36ba2-236">此消息表明您已禁用网络服务帐户的 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="36ba2-236">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="36ba2-237">Exchange 统一消息综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-237">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-238">Exchange 统一消息 (UM) 综合事务验证测试用户可以连接到帐户驻留在 Exchange 中的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="36ba2-238">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="36ba2-239">测试用户将需要预配置了语音邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="36ba2-239">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="36ba2-240">持久聊天综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-240">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-241">若要使用持久聊天的综合事务，必须首先创建通道，并授予用户权限以使用它的测试。</span><span class="sxs-lookup"><span data-stu-id="36ba2-241">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="36ba2-242">您可以使用持久聊天的综合事务配置此通道：</span><span class="sxs-lookup"><span data-stu-id="36ba2-242">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="36ba2-243">您必须运行此安装程序必须从企业内部运行任务：</span><span class="sxs-lookup"><span data-stu-id="36ba2-243">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="36ba2-244">如果从非服务器计算机运行，执行 cmdlet 的用户必须是基于角色的访问控制 (RBAC) 的 CsPersistentChatAdministrators 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="36ba2-244">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="36ba2-245">如果从服务器本身运行，执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="36ba2-245">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="36ba2-246">PSTN 对等呼叫综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-246">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-247">Test-cspstnpeertopeercall 综合事务验证发起和接收通过公用电话交换网 (PSTN) 呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="36ba2-247">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="36ba2-248">若要运行此综合事务，您必须配置：</span><span class="sxs-lookup"><span data-stu-id="36ba2-248">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="36ba2-249">两个启用 UC 的测试用户 （呼叫者和接收者）。</span><span class="sxs-lookup"><span data-stu-id="36ba2-249">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="36ba2-250">每个用户帐户的外线直拨分机 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="36ba2-250">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="36ba2-251">允许对接收者的号码的呼叫到达 PSTN 网关的 VoIP 策略和语音路由。</span><span class="sxs-lookup"><span data-stu-id="36ba2-251">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="36ba2-252">拨打接受呼叫并将路由回接收者主池，基于该号码的呼叫的媒体的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="36ba2-252">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="36ba2-253">统一的联系人存储库综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-253">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-254">统一联系人存储库综合事务验证业务服务器从 Exchange 中检索代表用户的联系人的 Skype 的能力。</span><span class="sxs-lookup"><span data-stu-id="36ba2-254">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="36ba2-255">若要使用此综合事务，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="36ba2-255">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="36ba2-256">必须配置 Lyss Exchange 服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="36ba2-256">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="36ba2-257">测试用户必须具有有效的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="36ba2-257">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="36ba2-258">满足这些条件后，您可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange:</span><span class="sxs-lookup"><span data-stu-id="36ba2-258">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="36ba2-259">可能需要一些时间，测试将迁移到 Exchange 的用户联系人列表。</span><span class="sxs-lookup"><span data-stu-id="36ba2-259">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="36ba2-260">若要监视迁移进度，相同的命令行可以运行-安装标记的情况下：</span><span class="sxs-lookup"><span data-stu-id="36ba2-260">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="36ba2-261">迁移完成后，将会成功此命令行。</span><span class="sxs-lookup"><span data-stu-id="36ba2-261">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="36ba2-262">XMPP 综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-262">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-263">可扩展消息传递和状态协议 (XMPP) IM 综合事务需要与一个或多个联盟域配置 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="36ba2-263">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="36ba2-264">若要启用 XMPP 综合事务，必须使用可路由的 XMPP 域的用户帐户提供 XmppTestReceiverMailAddress 参数。</span><span class="sxs-lookup"><span data-stu-id="36ba2-264">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="36ba2-265">例如：</span><span class="sxs-lookup"><span data-stu-id="36ba2-265">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="36ba2-266">本示例中，业务服务器规则 Skype 需要路由到 XMPP 网关的 litwareinc.com 的消息已存在。</span><span class="sxs-lookup"><span data-stu-id="36ba2-266">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="36ba2-267">XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="36ba2-267">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="36ba2-268">有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="36ba2-268">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="36ba2-269">视频互操作性服务器 (VIS) 综合事务</span><span class="sxs-lookup"><span data-stu-id="36ba2-269">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="36ba2-270">视频互操作服务器 (VIS) 综合事务需要您下载并安装综合事务支持文件 ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921))。</span><span class="sxs-lookup"><span data-stu-id="36ba2-270">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="36ba2-271">若要安装 VISSTSupportPackage.msi 确保的 msi 已安装了 （下系统要求） 的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="36ba2-271">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="36ba2-272">运行 VISSTSupportPackage.msi 进行简单的安装。</span><span class="sxs-lookup"><span data-stu-id="36ba2-272">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="36ba2-273">.Msi 安装在以下路径中的所有文件:"%ProgramFiles%\VIS 综合事务支持包"。</span><span class="sxs-lookup"><span data-stu-id="36ba2-273">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="36ba2-274">有关如何运行 VIS 综合事务的详细信息，请参阅[测试 CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="36ba2-274">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="36ba2-275">综合事务的更改的运行的频率</span><span class="sxs-lookup"><span data-stu-id="36ba2-275">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="36ba2-276"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="36ba2-276"></span></span>

<span data-ttu-id="36ba2-277">默认情况下综合事务将与配置用户每 15 分钟运行。</span><span class="sxs-lookup"><span data-stu-id="36ba2-277">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="36ba2-278">综合事务的用户，以避免相互冲突的两个综合事务一组按顺序运行。</span><span class="sxs-lookup"><span data-stu-id="36ba2-278">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="36ba2-279">较长的间隔需要提供所有综合事务，若要完成的时间。</span><span class="sxs-lookup"><span data-stu-id="36ba2-279">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="36ba2-280">它是否需要更频繁地运行综合事务，以便与偶尔网络延迟一些缓冲区所需的时间范围内完成测试应减少与给定的用户设置运行综合事务数。</span><span class="sxs-lookup"><span data-stu-id="36ba2-280">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="36ba2-281">如果运行的更多的综合事务，需要创建多个用户设置运行其他综合事务。</span><span class="sxs-lookup"><span data-stu-id="36ba2-281">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="36ba2-282">若要更改频率运行综合事务的频率，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="36ba2-282">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="36ba2-283">打开 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="36ba2-283">Open System Center Operations Manager.</span></span> <span data-ttu-id="36ba2-284">单击创作节。</span><span class="sxs-lookup"><span data-stu-id="36ba2-284">Click Authoring section.</span></span> <span data-ttu-id="36ba2-285">单击 （在创作） 下的规则部分。</span><span class="sxs-lookup"><span data-stu-id="36ba2-285">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="36ba2-286">在规则部分中，找到名为"Main 综合事务运行程序性能集合规则"规则。</span><span class="sxs-lookup"><span data-stu-id="36ba2-286">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="36ba2-287">右键单击该规则，并选中覆盖，选择该规则，重写方法，然后选择"类别的所有对象： 池观察程序"。</span><span class="sxs-lookup"><span data-stu-id="36ba2-287">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="36ba2-288">覆盖属性窗口中选择参数名称"频率"，并将覆盖值设置为所需的一个。</span><span class="sxs-lookup"><span data-stu-id="36ba2-288">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="36ba2-289">在同一窗口中，选择此重写需要应用的管理包。</span><span class="sxs-lookup"><span data-stu-id="36ba2-289">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="36ba2-290">使用综合事务的富日志记录</span><span class="sxs-lookup"><span data-stu-id="36ba2-290">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="36ba2-291"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="36ba2-291"></span></span>

<span data-ttu-id="36ba2-292">综合事务证明中帮助确定系统与问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="36ba2-292">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="36ba2-293">例如，Test-csregistration cmdlet 无法通知用户已有难度业务服务器注册 Skype 事实的管理员。</span><span class="sxs-lookup"><span data-stu-id="36ba2-293">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="36ba2-294">但是，可能需要其他详细信息，以确定实际失败的原因。</span><span class="sxs-lookup"><span data-stu-id="36ba2-294">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="36ba2-295">因此，对于综合事务提供丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="36ba2-295">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="36ba2-296">使用富日志记录，每个活动的综合事务不承担，记录以下信息：</span><span class="sxs-lookup"><span data-stu-id="36ba2-296">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="36ba2-297">活动的开始时间。</span><span class="sxs-lookup"><span data-stu-id="36ba2-297">The time that the activity started.</span></span>
    
- <span data-ttu-id="36ba2-298">活动的完成时间。</span><span class="sxs-lookup"><span data-stu-id="36ba2-298">The time that the activity finished.</span></span>
    
- <span data-ttu-id="36ba2-299">已执行的操作 (例如，创建、 加入或离开会议; 登录到 Skype 并 Business Server; 发送即时消息)。</span><span class="sxs-lookup"><span data-stu-id="36ba2-299">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="36ba2-300">信息性、 verbose 和警告或在活动运行时生成的错误消息。</span><span class="sxs-lookup"><span data-stu-id="36ba2-300">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="36ba2-301">SIP 注册消息。</span><span class="sxs-lookup"><span data-stu-id="36ba2-301">SIP registration messages.</span></span>
    
- <span data-ttu-id="36ba2-302">异常记录或诊断代码生成在活动运行时。</span><span class="sxs-lookup"><span data-stu-id="36ba2-302">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="36ba2-303">运行活动的最终结果。</span><span class="sxs-lookup"><span data-stu-id="36ba2-303">The net result of running the activity.</span></span>
    
<span data-ttu-id="36ba2-304">此信息将自动生成每次运行时综合事务，但不是会自动显示或保存到日志文件。</span><span class="sxs-lookup"><span data-stu-id="36ba2-304">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="36ba2-305">如果手动运行综合事务，您可以使用 OutLoggerVariable 参数指定的信息将存储在其中的 Windows PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="36ba2-305">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="36ba2-306">从此处，您可以使用两种方法之一将保存的选择和/或视图中丰富的错误消息日志以 XML 或 HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="36ba2-306">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="36ba2-307">若要检索的疑难解答信息，请指定 OutLoggerVariable 参数，后, 跟您选择的变量名：</span><span class="sxs-lookup"><span data-stu-id="36ba2-307">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="36ba2-308">不以 $ 字符在变量名。</span><span class="sxs-lookup"><span data-stu-id="36ba2-308">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="36ba2-309">使用一个变量的名称，例如 RegistrationTest (而不是 $RegistrationTest)。</span><span class="sxs-lookup"><span data-stu-id="36ba2-309">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="36ba2-310">运行此命令时，您将看到类似如下的输出：</span><span class="sxs-lookup"><span data-stu-id="36ba2-310">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="36ba2-311">目标 Fqdn: atl-cs-001.litwareinc.com 结果： 故障延迟： 00:00:00 错误消息： 此计算机不具有任何已分配的证书。</span><span class="sxs-lookup"><span data-stu-id="36ba2-311">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="36ba2-312">诊断： 您可以访问此故障比刚刚此处显示的错误消息的更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="36ba2-312">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="36ba2-313">若要访问此信息以 HTML 格式，使用与此类似的命令以保存到 HTML 文件的 RegistrationTest 变量中存储的信息：</span><span class="sxs-lookup"><span data-stu-id="36ba2-313">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="36ba2-314">此外，您可以使用 ToXML() 方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="36ba2-314">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="36ba2-315">您可以通过使用 Windows Internet Explorer、 Microsoft Visual Studio 或任何其他应用程序能够打开 HTML/XML 文件中查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="36ba2-315">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="36ba2-316">在 System Center Operations Manager 从运行综合事务将自动生成这些日志文件的故障。</span><span class="sxs-lookup"><span data-stu-id="36ba2-316">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="36ba2-317">如果在执行失败，无法加载并运行综合事务的业务 Server PowerShell Skype 之前，将不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="36ba2-317">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="36ba2-318">默认情况下，业务服务器 Skype 将日志文件存储不共享的文件夹。</span><span class="sxs-lookup"><span data-stu-id="36ba2-318">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="36ba2-319">若要使无法访问这些日志，您应共享该文件夹。</span><span class="sxs-lookup"><span data-stu-id="36ba2-319">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="36ba2-320">例如： \\atl-watcher-001.litwareinc.com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="36ba2-320">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
