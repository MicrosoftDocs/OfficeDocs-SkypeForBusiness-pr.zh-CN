---
title: 配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 摘要：为 Skype for Business Server 综合事务配置测试用户帐户和观察程序节点设置。
ms.openlocfilehash: 4069b1b51dc826beb631306e941eb40146188f42
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111598"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="d635e-103">配置观察程序节点测试用户和设置</span><span class="sxs-lookup"><span data-stu-id="d635e-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="d635e-104">**摘要：** 为 Skype for Business Server 综合事务配置测试用户帐户和观察程序节点设置。</span><span class="sxs-lookup"><span data-stu-id="d635e-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="d635e-105">在配置将充当观察程序节点的计算机之后，您必须：</span><span class="sxs-lookup"><span data-stu-id="d635e-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="d635e-106">[配置要由这些](test-users-and-settings.md#testuser) 观察程序节点使用的测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="d635e-107">如果您使用的是 Negotiate 身份验证方法，则必须同时使用 **Set-CsTestUserCredential** cmdlet 来启用这些测试帐户，以在观察程序节点上使用。</span><span class="sxs-lookup"><span data-stu-id="d635e-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="d635e-108">更新观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="d635e-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="d635e-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="d635e-109">Configure Test User Accounts</span></span>
<span data-ttu-id="d635e-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d635e-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="d635e-111">测试帐户不需要表示实际人员，但它们必须是有效的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="d635e-112">此外，必须为 Skype for Business Server 启用这些帐户，它们必须具有有效的 SIP 地址，并且应启用这些帐户企业语音 (以使用 Test-CsPstnPeerToPeerCall 综合事务) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="d635e-113">如果使用 TrustedServer 身份验证方法，只需确保这些帐户存在并按说明进行配置。</span><span class="sxs-lookup"><span data-stu-id="d635e-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="d635e-114">应为每个要测试的池分配至少两个测试用户。</span><span class="sxs-lookup"><span data-stu-id="d635e-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="d635e-115">如果使用 Negotiate 身份验证方法，还必须使用 Set-CsTestUserCredential cmdlet 和 Skype for Business Server 命令行管理程序使这些测试帐户能够处理综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="d635e-116">为此，运行与以下命令类似的命令 (这些命令假定已创建两个 Active Directory 用户帐户，并且这些帐户已启用 Skype for Business Server) ：</span><span class="sxs-lookup"><span data-stu-id="d635e-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="d635e-117">您不仅必须包括 SIP 地址，还必须包括用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="d635e-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="d635e-118">如果您不包括密码，则 Set-CsTestUserCredential cmdlet 将提示您输入该信息。</span><span class="sxs-lookup"><span data-stu-id="d635e-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="d635e-119">可以使用前面代码块中显示的域名\用户名格式来指定用户名。</span><span class="sxs-lookup"><span data-stu-id="d635e-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="d635e-120">若要验证是否创建了测试用户凭据，请从 Skype for Business Server 命令行管理程序 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="d635e-121">将为每个用户返回类似此信息：</span><span class="sxs-lookup"><span data-stu-id="d635e-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="d635e-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="d635e-122">**UserName**</span></span>|<span data-ttu-id="d635e-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="d635e-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d635e-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="d635e-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="d635e-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="d635e-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="d635e-126">使用默认综合事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d635e-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="d635e-127">创建测试用户后，可以使用类似以下的命令创建观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="d635e-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="d635e-128">此命令会创建一个新的观察程序节点，该节点使用默认设置并运行默认的综合事务集。</span><span class="sxs-lookup"><span data-stu-id="d635e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="d635e-129">新的观察程序节点还使用测试 watcher1@litwareinc.com，watcher2@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="d635e-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="d635e-130">如果观察程序节点使用 TrustedServer 身份验证，则两个测试帐户可以是为 Active Directory 和 Skype for Business Server 启用的任何有效用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="d635e-131">如果观察程序节点使用 Negotiate 身份验证方法，则还必须使用 Set-CsTestUserCredential cmdlet 为观察程序节点启用这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="d635e-132">若要验证是否正确配置了目标池的自动发现以登录，而不是直接将目标池作为目标，请改为使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d635e-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="d635e-133">配置扩展的测试</span><span class="sxs-lookup"><span data-stu-id="d635e-133">Configuring Extended Tests</span></span>

<span data-ttu-id="d635e-134">如果要启用 PSTN 测试（用于验证与公用电话交换网的连接），则需要在设置观察程序节点时执行一些额外的配置。</span><span class="sxs-lookup"><span data-stu-id="d635e-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="d635e-135">首先，必须通过从 Skype for Business Server 命令行管理程序运行类似于以下的命令，将测试用户与 PSTN 测试类型关联：</span><span class="sxs-lookup"><span data-stu-id="d635e-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="d635e-136">此命令的结果必须存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="d635e-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="d635e-137">本示例中，变量名为 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="d635e-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="d635e-138">接下来，可以使用 **New-CsWatcherNodeConfiguration** cmdlet 将变量 (中存储的测试类型 $pstnTest) 与 Skype for Business Server 池关联。</span><span class="sxs-lookup"><span data-stu-id="d635e-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="d635e-139">例如，以下命令为池池创建新的观察程序节点 atl-cs-001.litwareinc.com，添加之前创建的两个测试用户，并添加 PSTN 测试类型：</span><span class="sxs-lookup"><span data-stu-id="d635e-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="d635e-140">如果您尚未在观察程序节点计算机上安装 Skype for Business Server 核心文件和 RTCLocal 数据库，则上述命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d635e-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="d635e-141">若要测试多个语音策略，可以使用 **New-CsExtendedTest** cmdlet 为每个策略创建一个扩展测试。</span><span class="sxs-lookup"><span data-stu-id="d635e-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="d635e-142">所提供的用户应配置所需的语音策略。</span><span class="sxs-lookup"><span data-stu-id="d635e-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="d635e-143">扩展测试通过使用逗号分隔符传递到 **New-CsWatcherNodeConfiguration** cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="d635e-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="d635e-144">-ExtendedTests @{Add=$pstnTest 1，$pstnTest 2，$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="d635e-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="d635e-145">由于 **调用 New-CsWatcherNodeConfiguration** cmdlet 时没有使用 Tests 参数，因此只会为新的观察程序节点启用默认综合事务 (和指定的扩展综合事务) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="d635e-146">因此，观察程序节点将测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="d635e-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="d635e-147">注册</span><span class="sxs-lookup"><span data-stu-id="d635e-147">Registration</span></span>
    
- <span data-ttu-id="d635e-148">IM</span><span class="sxs-lookup"><span data-stu-id="d635e-148">IM</span></span>
    
- <span data-ttu-id="d635e-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="d635e-149">GroupIM</span></span>
    
- <span data-ttu-id="d635e-150">P2PAV（对等音频/视频会话）</span><span class="sxs-lookup"><span data-stu-id="d635e-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="d635e-151">AvConference（音频/会议）</span><span class="sxs-lookup"><span data-stu-id="d635e-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="d635e-152">状态</span><span class="sxs-lookup"><span data-stu-id="d635e-152">Presence</span></span>
    
- <span data-ttu-id="d635e-153">ABS（通讯簿服务）</span><span class="sxs-lookup"><span data-stu-id="d635e-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="d635e-154">ABWQ（通讯簿 Web 服务）</span><span class="sxs-lookup"><span data-stu-id="d635e-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="d635e-155">默认情况下，不会测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="d635e-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="d635e-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="d635e-156">ASConference</span></span>
    
- <span data-ttu-id="d635e-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="d635e-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="d635e-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="d635e-158">DataConference</span></span>
    
- <span data-ttu-id="d635e-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="d635e-159">DialinConferencing</span></span>
    
- <span data-ttu-id="d635e-160">ExumConnectivity（Exchange 统一消息）</span><span class="sxs-lookup"><span data-stu-id="d635e-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="d635e-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="d635e-161">JoinLauncher</span></span>
    
- <span data-ttu-id="d635e-162">MCXP2PIM (旧版移动设备即时消息) </span><span class="sxs-lookup"><span data-stu-id="d635e-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="d635e-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="d635e-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="d635e-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d635e-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="d635e-165">PSTN (PSTN 网关呼叫，指定为扩展测试) </span><span class="sxs-lookup"><span data-stu-id="d635e-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="d635e-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="d635e-166">UcwaConference</span></span>
    
- <span data-ttu-id="d635e-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="d635e-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="d635e-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="d635e-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="d635e-169">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="d635e-170">在配置观察程序节点之后，您可以使用 Set-CsWatcherNodeConfiguration cmdlet 添加或从节点中删除综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="d635e-171">例如，要将 PersistentChatMessage 测试添加到观察程序节点，请使用 Add 方法和与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="d635e-172">可以通过使用逗号分隔测试名称来添加多个测试。</span><span class="sxs-lookup"><span data-stu-id="d635e-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="d635e-173">例如：</span><span class="sxs-lookup"><span data-stu-id="d635e-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="d635e-174">如果其中一个或多个测试（例如，dataConference (已在观察程序节点上启用) ，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="d635e-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="d635e-175">在这种情况下，您将收到与以下类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="d635e-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="d635e-176">Set-CsWatcherNodeConfiguration："urn：schema：Microsoft.Rtc.Management.Settings.WatcherNode.2010：TestName"键或唯一标识约束存在重复键序列"DataConference"。</span><span class="sxs-lookup"><span data-stu-id="d635e-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="d635e-177">发生此错误时，不会应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="d635e-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="d635e-178">该命令应在删除重复测试后重新运行。</span><span class="sxs-lookup"><span data-stu-id="d635e-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="d635e-179">若要从观察程序节点中删除综合事务，请使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="d635e-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="d635e-180">例如，以下命令会从观察程序节点中删除 ABWQ 测试：</span><span class="sxs-lookup"><span data-stu-id="d635e-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="d635e-181">可以使用 Replace 方法将当前启用的所有测试替换为一个或多个新测试。</span><span class="sxs-lookup"><span data-stu-id="d635e-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="d635e-182">例如，如果希望观察程序节点仅运行 IM 测试，可以使用以下命令进行配置：</span><span class="sxs-lookup"><span data-stu-id="d635e-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="d635e-183">运行此命令时，将禁用指定观察程序节点上的所有综合事务（IM 除外）。</span><span class="sxs-lookup"><span data-stu-id="d635e-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="d635e-184">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="d635e-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="d635e-185">如果您想要查看已分配给观察程序节点的测试，请使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="d635e-186">此命令将返回类似此信息，具体取决于已分配给节点的综合事务：</span><span class="sxs-lookup"><span data-stu-id="d635e-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="d635e-187">注册 IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="d635e-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="d635e-188">要按字母顺序查看综合事务，请改为使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="d635e-189">若要验证是否创建了观察程序节点，请从 Skype for Business Server 命令行管理程序 键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="d635e-190">您将获得与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="d635e-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="d635e-191">标识 ：atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d635e-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="d635e-192">TestUsers ： {sip:watcher1@litwareinc.com， sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="d635e-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="d635e-193">ExtendedTests ： {TestUsers=IList<System.String>;Name=PSTN Test;Te...}</span><span class="sxs-lookup"><span data-stu-id="d635e-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="d635e-194">TargetFqdn ： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d635e-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="d635e-195">PortNumber ： 5061</span><span class="sxs-lookup"><span data-stu-id="d635e-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="d635e-196">若要验证观察程序节点是否正确配置，请从 Skype for Business Server 命令行管理程序 键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="d635e-197">此命令将测试部署中的每个观察程序节点并确认是否已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="d635e-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="d635e-198">已安装所需的注册器角色。</span><span class="sxs-lookup"><span data-stu-id="d635e-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="d635e-199">在运行 cmdlet cmdlet (时，将创建所需的Set-CsWatcherNodeConfiguration注册表) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="d635e-200">你的服务器运行的是正确版本的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="d635e-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="d635e-201">您的端口配置正确。</span><span class="sxs-lookup"><span data-stu-id="d635e-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="d635e-202">所分配的测试用户是否具有所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="d635e-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="d635e-203">管理观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d635e-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="d635e-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d635e-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="d635e-205">除了修改在观察程序节点上执行的综合事务之外，您还可以使用 **Set-CsWatcherNodeConfiguration** cmdlet 执行另外两项重要任务：启用和禁用观察程序节点，以及将观察程序节点配置为在运行其测试时使用内部 Web URL 或外部 Web URL。</span><span class="sxs-lookup"><span data-stu-id="d635e-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="d635e-206">默认情况下，观察程序节点旨在定期运行其所有启用的综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="d635e-207">但是，有时您可能需要暂停这些事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="d635e-208">例如，如果观察程序节点临时断开了网络连接，则没有必要运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="d635e-209">如果没有网络连接，这些事务将失败。</span><span class="sxs-lookup"><span data-stu-id="d635e-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="d635e-210">若要临时禁用观察程序节点，请从 Skype for Business Server 命令行管理程序 运行类似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="d635e-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="d635e-211">此命令将禁止在观察程序节点 atl 观察程序上执行综合 001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="d635e-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="d635e-212">若要恢复综合事务的执行，请将 Enabled 属性设置回 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="d635e-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="d635e-213">Enabled 属性可用于启用或禁用观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="d635e-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="d635e-214">如果要永久删除观察程序节点，请使用 **Remove-CsWatcherNodeConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d635e-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="d635e-215">该命令从指定计算机中删除所有观察程序节点配置设置，从而阻止该计算机自动运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="d635e-216">但是，该命令不会卸载 System Center 代理文件或 Skype for Business Server 系统文件。</span><span class="sxs-lookup"><span data-stu-id="d635e-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="d635e-217">默认情况下，观察程序节点在进行测试时使用组织的外部 Web URL。</span><span class="sxs-lookup"><span data-stu-id="d635e-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="d635e-218">但是，还可以将观察程序节点配置为使用组织的内部 Web URL。</span><span class="sxs-lookup"><span data-stu-id="d635e-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="d635e-219">这使管理员可验证位于外围网络内的用户的 URL 访问权限。</span><span class="sxs-lookup"><span data-stu-id="d635e-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="d635e-220">若要将观察程序节点配置为使用内部 URL 而不是外部 URL，可以将 UseInternalWebURls 属性设置为 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="d635e-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="d635e-221">将此属性重置为默认值 False ($False) 将导致观察程序再次使用外部 URL：</span><span class="sxs-lookup"><span data-stu-id="d635e-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="d635e-222">综合事务的特殊设置说明</span><span class="sxs-lookup"><span data-stu-id="d635e-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="d635e-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d635e-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d635e-224">大多数综合事务可以像现在一样在观察程序节点上运行。</span><span class="sxs-lookup"><span data-stu-id="d635e-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="d635e-225">在大多数情况下，一旦将综合事务添加到观察程序节点配置设置中，观察程序节点就可以在其测试通过期间开始使用该综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="d635e-226">但是，有些综合事务需要特殊的设置说明，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="d635e-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="d635e-227">数据会议综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="d635e-228">如果观察程序节点计算机位于外围网络外部，则可能无法运行数据会议综合事务，除非首先通过完成以下步骤禁用网络服务帐户的 Windows Internet Explorer® Internet 浏览器代理设置：</span><span class="sxs-lookup"><span data-stu-id="d635e-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="d635e-229">在观察程序节点计算机上，单击"开始"，单击"所有程序 **"，** 单击"附件"，右键单击"**命令提示符**"，然后单击"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="d635e-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="d635e-230">在控制台窗口中，键入以下命令，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d635e-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="d635e-231">将在命令窗口中看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="d635e-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="d635e-232">此消息指示你已禁用Internet Explorer服务帐户的代理设置。</span><span class="sxs-lookup"><span data-stu-id="d635e-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="d635e-233">Exchange 统一消息综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="d635e-234">统一消息 (UM) 事务验证测试用户能否连接到 Exchange 中存储的语音邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="d635e-235">测试用户将需要预配置语音邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="d635e-236">持久聊天综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="d635e-237">若要使用持久聊天综合事务，必须先创建一个通道，并授予测试用户使用该通道的权限。</span><span class="sxs-lookup"><span data-stu-id="d635e-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="d635e-238">您可以使用持久聊天综合事务配置此通道：</span><span class="sxs-lookup"><span data-stu-id="d635e-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="d635e-239">您必须从企业内部运行此安装任务：</span><span class="sxs-lookup"><span data-stu-id="d635e-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="d635e-240">如果从非服务器计算机运行，则执行 cmdlet 的用户必须是 Role-Based Access Control (RBAC) 的 CsPersistentChatAdministrators 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d635e-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="d635e-241">如果从服务器本身运行，则执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="d635e-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="d635e-242">PSTN 对等呼叫综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="d635e-243">该Test-CsPstnPeerToPeerCall事务验证能否通过公用电话交换网和 PSTN (接收) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="d635e-244">若要运行此综合事务，必须配置：</span><span class="sxs-lookup"><span data-stu-id="d635e-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="d635e-245">两个启用 UC 的测试 (呼叫方和一个接收器) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="d635e-246">为每个用户帐户配置外线直拨分机 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="d635e-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="d635e-247">允许呼叫接收者号码到达 PSTN 网关的 VoIP 策略和语音路由。</span><span class="sxs-lookup"><span data-stu-id="d635e-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="d635e-248">接受呼叫和媒体的 PSTN 网关，该网关将基于拨打的号码将呼叫路由回接收者主池。</span><span class="sxs-lookup"><span data-stu-id="d635e-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="d635e-249">统一联系人存储综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="d635e-250">统一联系人存储综合事务验证 Skype for Business Server 能否代表用户从 Exchange 检索联系人。</span><span class="sxs-lookup"><span data-stu-id="d635e-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="d635e-251">若要使用此综合事务，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="d635e-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="d635e-252">Lyss-Exchange配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="d635e-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="d635e-253">测试用户必须具有有效的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="d635e-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="d635e-254">满足这些条件后，可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange：</span><span class="sxs-lookup"><span data-stu-id="d635e-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="d635e-255">测试用户联系人列表迁移到 Exchange 可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="d635e-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="d635e-256">若要监视迁移进度，可以在没有 -Setup 标志的情况下运行相同的命令行：</span><span class="sxs-lookup"><span data-stu-id="d635e-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="d635e-257">迁移完成后，此命令行将成功。</span><span class="sxs-lookup"><span data-stu-id="d635e-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="d635e-258">XMPP 综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="d635e-259">XMPP (IM) 事务中的可扩展消息传递和状态协议要求使用一个或多个联盟域配置 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="d635e-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="d635e-260">若要启用 XMPP 综合事务，您必须提供 XmppTestReceiverMailAddress 参数以及可路由 XMPP 域中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d635e-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="d635e-261">例如：</span><span class="sxs-lookup"><span data-stu-id="d635e-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="d635e-262">本示例中，需要存在 Skype for Business Server 规则，将邮件路由 litwareinc.com XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="d635e-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="d635e-263">XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="d635e-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d635e-264">有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。</span><span class="sxs-lookup"><span data-stu-id="d635e-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="d635e-265">视频互操作服务器 (VIS) 综合事务</span><span class="sxs-lookup"><span data-stu-id="d635e-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="d635e-266">视频互操作服务器 (VIS) 综合事务需要您下载并安装 (VISSTSupportPackage.msi[) 。](https://www.microsoft.com/download/details.aspx?id=46921)</span><span class="sxs-lookup"><span data-stu-id="d635e-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="d635e-267">若要安装VISSTSupportPackage.msi请确保已安装 (msi 的系统) 要求"下的依赖项。</span><span class="sxs-lookup"><span data-stu-id="d635e-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="d635e-268">运行VISSTSupportPackage.msi以执行简单安装。</span><span class="sxs-lookup"><span data-stu-id="d635e-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="d635e-269">.msi 将安装以下路径中的所有文件："%ProgramFiles%\VIS 综合事务支持包"。</span><span class="sxs-lookup"><span data-stu-id="d635e-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="d635e-270">若要详细了解如何运行 VIS 综合事务，请参阅 [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="d635e-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="d635e-271">更改综合事务的运行频率</span><span class="sxs-lookup"><span data-stu-id="d635e-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="d635e-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d635e-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d635e-273">默认情况下，综合事务将每 15 分钟与配置的用户一起运行一次。</span><span class="sxs-lookup"><span data-stu-id="d635e-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="d635e-274">综合事务在一组用户内按顺序运行，以避免两个综合事务相互冲突。</span><span class="sxs-lookup"><span data-stu-id="d635e-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="d635e-275">需要较长的间隔才能完成所有综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="d635e-276">如果更频繁地运行综合事务是可取的，应减少与一组给定用户一起运行的综合事务数，以便测试可以在所需时间范围内完成，同时提供一些偶尔出现网络延迟的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d635e-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="d635e-277">如果需要运行更多的综合事务，请创建更多用户集以运行其他综合事务。</span><span class="sxs-lookup"><span data-stu-id="d635e-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="d635e-278">若要更改综合事务运行的频率，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d635e-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="d635e-279">打开 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="d635e-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="d635e-280">单击"创作"部分。</span><span class="sxs-lookup"><span data-stu-id="d635e-280">Click Authoring section.</span></span> <span data-ttu-id="d635e-281">单击"创作 (下的规则) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="d635e-282">在"规则"部分，查找名称为"主综合事务运行程序性能收集规则"的规则。</span><span class="sxs-lookup"><span data-stu-id="d635e-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="d635e-283">右键单击该规则，然后选择"覆盖"，选择"替代规则"，然后选择"对于类的所有对象：池观察程序"。</span><span class="sxs-lookup"><span data-stu-id="d635e-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="d635e-284">在"替代属性"窗口中，选择"参数名称""频率"，将"替代值"设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="d635e-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="d635e-285">在同一窗口中，选择需要应用此替代的管理包。</span><span class="sxs-lookup"><span data-stu-id="d635e-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="d635e-286">使用综合事务的富日志记录</span><span class="sxs-lookup"><span data-stu-id="d635e-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="d635e-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d635e-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d635e-288">综合事务证明在帮助识别系统问题方面极其有用。</span><span class="sxs-lookup"><span data-stu-id="d635e-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="d635e-289">例如，Test-CsRegistration cmdlet 可能会提醒管理员用户向 Skype for Business Server 注册时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="d635e-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="d635e-290">但是，可能需要其他详细信息来确定失败的实际原因。</span><span class="sxs-lookup"><span data-stu-id="d635e-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="d635e-291">因此，综合事务可提供丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="d635e-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="d635e-292">利用丰富的日志记录，对于综合事务执行的每个活动，将记录以下信息：</span><span class="sxs-lookup"><span data-stu-id="d635e-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="d635e-293">活动开始的时间。</span><span class="sxs-lookup"><span data-stu-id="d635e-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="d635e-294">活动完成的时间。</span><span class="sxs-lookup"><span data-stu-id="d635e-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="d635e-295">已执行的操作 (例如，创建、加入或离开会议;登录 Skype for Business Server;发送即时消息) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="d635e-296">活动运行时生成的信息性、详细、警告或错误消息。</span><span class="sxs-lookup"><span data-stu-id="d635e-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="d635e-297">SIP 注册消息。</span><span class="sxs-lookup"><span data-stu-id="d635e-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="d635e-298">活动运行时生成的异常记录或诊断代码。</span><span class="sxs-lookup"><span data-stu-id="d635e-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="d635e-299">运行活动最终结果。</span><span class="sxs-lookup"><span data-stu-id="d635e-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="d635e-300">每次运行综合事务时都会自动生成此信息，但不自动显示此信息或将此信息保存到日志文件。</span><span class="sxs-lookup"><span data-stu-id="d635e-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d635e-301">如果手动运行综合事务，可以使用 OutLoggerVariable 参数指定一个Windows PowerShell存储该信息的变量。</span><span class="sxs-lookup"><span data-stu-id="d635e-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d635e-302">从该日志，可以选择使用两种方法之一以 XML 或 HTML 格式在富日志中保存和/或查看错误消息。</span><span class="sxs-lookup"><span data-stu-id="d635e-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="d635e-303">若要检索疑难解答信息，请指定 OutLoggerVariable 参数，后跟您选择的变量名称：</span><span class="sxs-lookup"><span data-stu-id="d635e-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="d635e-304">变量名称不要以 $ 字符开头。</span><span class="sxs-lookup"><span data-stu-id="d635e-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="d635e-305">使用一个变量名称，如 RegistrationTest (，$RegistrationTest) 。</span><span class="sxs-lookup"><span data-stu-id="d635e-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="d635e-306">运行此命令时，将看到类似以下的输出：</span><span class="sxs-lookup"><span data-stu-id="d635e-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="d635e-307">目标 Fqdn ： atl-cs-001.litwareinc.com 结果 ： 失败延迟 ： 00：00：00 错误消息 ： 此计算机没有任何分配的证书。</span><span class="sxs-lookup"><span data-stu-id="d635e-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="d635e-308">诊断 ：你可以访问有关此失败的详细信息，而不只是此处显示的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d635e-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="d635e-309">若要以 HTML 格式访问此信息，请使用与此类似的命令将存储在变量 RegistrationTest 中的信息保存到 HTML 文件中：</span><span class="sxs-lookup"><span data-stu-id="d635e-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="d635e-310">您也可以使用 ToXML() 方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="d635e-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="d635e-311">可以使用 Windows 应用程序、Microsoft Internet Explorer或其他能够打开 HTML/XML 文件Visual Studio查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="d635e-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="d635e-312">从 System Center Operations Manager 内部运行的综合事务将针对故障自动生成这些日志文件。</span><span class="sxs-lookup"><span data-stu-id="d635e-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d635e-313">如果在 Skype for Business Server PowerShell 能够加载和运行综合事务之前执行失败，将不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="d635e-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d635e-314">默认情况下，Skype for Business Server 将日志文件保存到未共享的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d635e-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d635e-315">若要使这些日志易于访问，应共享此文件夹。</span><span class="sxs-lookup"><span data-stu-id="d635e-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="d635e-316">例如 \\ ：atl-watcher-001.litwareinc.com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="d635e-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>