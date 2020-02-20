---
title: 配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。
ms.openlocfilehash: bfbad6fbeb68100adaaee781c135531d226f43bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150493"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="d65e4-103">配置观察程序节点测试用户和设置</span><span class="sxs-lookup"><span data-stu-id="d65e4-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="d65e4-104">**摘要：** 为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。</span><span class="sxs-lookup"><span data-stu-id="d65e4-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="d65e4-105">在配置将充当观察程序节点的计算机之后，您必须：</span><span class="sxs-lookup"><span data-stu-id="d65e4-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="d65e4-106">配置这些观察程序节点要使用的[测试用户帐户](test-users-and-settings-2019.md#testuser)。</span><span class="sxs-lookup"><span data-stu-id="d65e4-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="d65e4-107">如果您使用的是 Negotiate 身份验证方法，则必须同时使用 **Set-CsTestUserCredential** cmdlet 来启用这些测试帐户，以在观察程序节点上使用。</span><span class="sxs-lookup"><span data-stu-id="d65e4-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="d65e4-108">更新观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="d65e4-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="d65e4-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="d65e4-109">Configure Test User Accounts</span></span>
<span data-ttu-id="d65e4-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d65e4-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="d65e4-111">测试帐户不需要表示实际人员，但它们必须是有效的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="d65e4-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="d65e4-112">此外，必须为 Skype for business Server 启用这些帐户，它们必须具有有效的 SIP 地址，并且应为企业语音启用这些帐户（以使用 CsPstnPeerToPeerCall 综合事务）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="d65e4-113">如果使用的是 TrustedServer 身份验证方法，您只需确保这些帐户存在并按说明进行配置即可。</span><span class="sxs-lookup"><span data-stu-id="d65e4-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="d65e4-114">您应为要测试的每个池至少分配三个测试用户。</span><span class="sxs-lookup"><span data-stu-id="d65e4-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="d65e4-115">如果使用的是协商身份验证方法，则还必须使用 CsTestUserCredential cmdlet 和 Skype for Business Server 命令行管理程序，以使这些测试帐户能够使用综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="d65e4-116">若要执行此操作，请运行与以下内容类似的命令（这些命令假定已创建三个 Active Directory 用户帐户，并且为 Skype for business Server 启用了这些帐户）：</span><span class="sxs-lookup"><span data-stu-id="d65e4-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="d65e4-117">除 SIP 地址之外，还必须包括用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="d65e4-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="d65e4-118">如果不包含密码，CsTestUserCredential cmdlet 将提示您输入该信息。</span><span class="sxs-lookup"><span data-stu-id="d65e4-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="d65e4-119">可以使用前面代码块中所示的域名 \ 用户名格式来指定用户名称。</span><span class="sxs-lookup"><span data-stu-id="d65e4-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="d65e4-120">若要验证是否已创建测试用户凭据，请从 Skype for Business Server 命令行管理程序运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="d65e4-121">将为每个用户返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="d65e4-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="d65e4-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="d65e4-122">**UserName**</span></span>|<span data-ttu-id="d65e4-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="d65e4-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d65e4-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="d65e4-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="d65e4-125">SecureString</span><span class="sxs-lookup"><span data-stu-id="d65e4-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="d65e4-126">使用默认综合事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d65e4-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="d65e4-127">在创建测试用户之后，可以使用类似如下的命令创建观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="d65e4-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="d65e4-128">此命令会创建一个新的观察程序节点，该节点使用默认设置并运行默认的综合事务集。</span><span class="sxs-lookup"><span data-stu-id="d65e4-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="d65e4-129">新的观察程序节点还使用测试用户 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="d65e4-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="d65e4-130">如果观察程序节点使用 TrustedServer 身份验证，则这三个测试帐户可以是为 Active Directory 和 Skype for business Server 启用的任何有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d65e4-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="d65e4-131">如果观察程序节点使用协商身份验证方法，则还必须使用 CsTestUserCredential cmdlet 为观察程序节点启用这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d65e4-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="d65e4-132">若要验证是否已正确配置目标池的自动发现，而不是以某个池为目标，请改为直接使用这些步骤：</span><span class="sxs-lookup"><span data-stu-id="d65e4-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="d65e4-133">配置扩展的测试</span><span class="sxs-lookup"><span data-stu-id="d65e4-133">Configuring Extended Tests</span></span>

<span data-ttu-id="d65e4-134">如果要启用 PSTN 测试（它会验证与公用电话交换网的连接），则需要在设置观察程序节点时执行一些额外的配置。</span><span class="sxs-lookup"><span data-stu-id="d65e4-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="d65e4-135">首先，您必须通过在 Skype for Business Server 命令行管理程序中运行与以下内容类似的命令，将测试用户与 PSTN 测试类型关联起来：</span><span class="sxs-lookup"><span data-stu-id="d65e4-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="d65e4-136">此命令的结果必须存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="d65e4-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="d65e4-137">在此示例中，变量被命名为 $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="d65e4-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="d65e4-138">接下来，可以使用**new-cswatchernodeconfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）与 Skype For business Server 池相关联。</span><span class="sxs-lookup"><span data-stu-id="d65e4-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="d65e4-139">例如，以下命令为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置，添加之前创建的三个测试用户，并添加 PSTN 测试类型：</span><span class="sxs-lookup"><span data-stu-id="d65e4-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="d65e4-140">如果尚未在观察程序节点计算机上安装 Skype for Business Server core 文件和 RTCLocal 数据库，上述命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d65e4-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="d65e4-141">若要测试多个语音策略，您可以使用**CsExtendedTest** cmdlet 为每个策略创建扩展测试。</span><span class="sxs-lookup"><span data-stu-id="d65e4-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="d65e4-142">提供的用户应使用所需的语音策略进行配置。</span><span class="sxs-lookup"><span data-stu-id="d65e4-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="d65e4-143">扩展测试通过使用逗号分隔符传递给**new-cswatchernodeconfiguration** cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="d65e4-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="d65e4-144">-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="d65e4-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="d65e4-145">由于在未使用测试参数的情况下调用**new-cswatchernodeconfiguration** cmdlet，因此将仅为新的观察程序节点启用默认的合成事务（和指定的扩展的合成事务）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="d65e4-146">因此，观察程序节点将测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="d65e4-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="d65e4-147">注册</span><span class="sxs-lookup"><span data-stu-id="d65e4-147">Registration</span></span>
    
- <span data-ttu-id="d65e4-148">IM</span><span class="sxs-lookup"><span data-stu-id="d65e4-148">IM</span></span>
    
- <span data-ttu-id="d65e4-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="d65e4-149">GroupIM</span></span>
    
- <span data-ttu-id="d65e4-150">P2PAV（对等音频/视频会话）</span><span class="sxs-lookup"><span data-stu-id="d65e4-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="d65e4-151">AvConference（音频/会议）</span><span class="sxs-lookup"><span data-stu-id="d65e4-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="d65e4-152">状态</span><span class="sxs-lookup"><span data-stu-id="d65e4-152">Presence</span></span>
    
- <span data-ttu-id="d65e4-153">ABS（通讯簿服务）</span><span class="sxs-lookup"><span data-stu-id="d65e4-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="d65e4-154">ABWQ（通讯簿 Web 服务）</span><span class="sxs-lookup"><span data-stu-id="d65e4-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="d65e4-155">默认情况下，不会测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="d65e4-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="d65e4-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="d65e4-156">ASConference</span></span>
    
- <span data-ttu-id="d65e4-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="d65e4-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="d65e4-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="d65e4-158">DataConference</span></span>
    
- <span data-ttu-id="d65e4-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="d65e4-159">DialinConferencing</span></span>
    
- <span data-ttu-id="d65e4-160">ExumConnectivity（Exchange 统一消息）</span><span class="sxs-lookup"><span data-stu-id="d65e4-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="d65e4-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="d65e4-161">JoinLauncher</span></span>
    
- <span data-ttu-id="d65e4-162">MCXP2PIM （旧版移动设备即时消息）</span><span class="sxs-lookup"><span data-stu-id="d65e4-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="d65e4-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="d65e4-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="d65e4-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d65e4-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="d65e4-165">PSTN （PSTN 网关呼叫，指定为扩展测试）</span><span class="sxs-lookup"><span data-stu-id="d65e4-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="d65e4-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="d65e4-166">UcwaConference</span></span>
    
- <span data-ttu-id="d65e4-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="d65e4-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="d65e4-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="d65e4-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="d65e4-169">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="d65e4-170">在配置观察程序节点之后，您可以使用 Set-CsWatcherNodeConfiguration cmdlet 添加或从节点中删除综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="d65e4-171">例如，要将 PersistentChatMessage 测试添加到观察程序节点，请使用 Add 方法和与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="d65e4-172">可以通过使用逗号分隔测试名称来添加多个测试。</span><span class="sxs-lookup"><span data-stu-id="d65e4-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="d65e4-173">例如：</span><span class="sxs-lookup"><span data-stu-id="d65e4-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="d65e4-174">如果已在观察程序节点上启用了一个或多个这些测试（例如，DataConference），则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="d65e4-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="d65e4-175">在这种情况下，您将收到与以下类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="d65e4-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="d65e4-176">New-cswatchernodeconfiguration： "urn： schema： TestName" 键或唯一标识约束中存在重复的键序列 "DataConference" （"urn： Watchernode.msi："）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="d65e4-177">发生此错误时，不会应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="d65e4-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="d65e4-178">应重新运行该命令，并删除重复的测试。</span><span class="sxs-lookup"><span data-stu-id="d65e4-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="d65e4-179">若要从观察程序节点中删除综合事务，请使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="d65e4-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="d65e4-180">例如，以下命令会从观察程序节点中删除 ABWQ 测试：</span><span class="sxs-lookup"><span data-stu-id="d65e4-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="d65e4-181">可以使用 Replace 方法将所有当前启用的测试替换为一个或多个新的测试。</span><span class="sxs-lookup"><span data-stu-id="d65e4-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="d65e4-182">例如，如果您希望观察程序节点仅运行 IM 测试，则可以使用以下命令对其进行配置：</span><span class="sxs-lookup"><span data-stu-id="d65e4-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="d65e4-183">运行此命令时，除 IM 外，指定的观察程序节点上的所有综合事务都将被禁用。</span><span class="sxs-lookup"><span data-stu-id="d65e4-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="d65e4-184">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="d65e4-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="d65e4-185">如果您想要查看已分配给观察程序节点的测试，请使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="d65e4-186">此命令将返回与此类似的信息，具体取决于已分配给该节点的综合事务：</span><span class="sxs-lookup"><span data-stu-id="d65e4-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="d65e4-187">注册 IM GroupIM P2PAV AvConference 状态 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="d65e4-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="d65e4-188">要按字母顺序查看综合事务，请改为使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="d65e4-189">若要验证是否已创建观察程序节点，请在 Skype for Business Server 命令行管理程序中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="d65e4-190">将返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="d65e4-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="d65e4-191">Identity： atl-cs-001.litwareinc.com TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="d65e4-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="d65e4-192">ExtendedTests： {TestUsers = IList<System.string>;Name = PSTN 测试;Te ...}</span><span class="sxs-lookup"><span data-stu-id="d65e4-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="d65e4-193">TargetFqdn： atl-cs-001.litwareinc.com PortNumber：5061To 验证是否已正确配置观察程序节点，请在 Skype for Business Server Management Shell 中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="d65e4-194">此命令将测试部署中的每个观察程序节点，并确认是否已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="d65e4-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="d65e4-195">安装了所需的注册者角色</span><span class="sxs-lookup"><span data-stu-id="d65e4-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="d65e4-196">将创建所需的注册表项（在运行 New-cswatchernodeconfiguration cmdlet 时完成）</span><span class="sxs-lookup"><span data-stu-id="d65e4-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="d65e4-197">你的服务器运行的是 Skype for Business Server 的正确版本</span><span class="sxs-lookup"><span data-stu-id="d65e4-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="d65e4-198">端口配置正确</span><span class="sxs-lookup"><span data-stu-id="d65e4-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="d65e4-199">您分配的测试用户具有所需的凭据</span><span class="sxs-lookup"><span data-stu-id="d65e4-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="d65e4-200">管理观察程序节点</span><span class="sxs-lookup"><span data-stu-id="d65e4-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="d65e4-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d65e4-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="d65e4-202">除了修改在观察程序节点上执行的合成事务之外，您还可以使用**new-cswatchernodeconfiguration** cmdlet 执行两个其他重要任务：启用和禁用观察程序节点，以及将观察程序节点配置为在运行其测试时使用内部 web url 或外部 web url。</span><span class="sxs-lookup"><span data-stu-id="d65e4-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="d65e4-203">默认情况下，观察程序节点旨在定期运行其所有启用的综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="d65e4-204">但是，有时您可能希望挂起这些事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="d65e4-205">例如，如果观察程序节点临时断开了网络连接，则没有必要运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="d65e4-206">如果没有网络连接，这些事务将会失败。</span><span class="sxs-lookup"><span data-stu-id="d65e4-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="d65e4-207">若要暂时禁用观察程序节点，请从 Skype for Business Server 命令行管理程序运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="d65e4-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="d65e4-208">此命令将禁用在观察程序节点 atl 观察程序001.litwareinc.com 上执行综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="d65e4-209">若要恢复综合事务的执行，请将 Enabled 属性设置回 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="d65e4-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="d65e4-210">Enabled 属性可用于启用或禁用观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="d65e4-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="d65e4-211">如果要永久删除观察程序节点，请使用 **Remove-CsWatcherNodeConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d65e4-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="d65e4-212">该命令将从指定的计算机中删除所有观察程序节点配置设置，这将阻止计算机自动运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="d65e4-213">但是，该命令不会卸载 System Center agent 文件或 Skype for Business Server 系统文件。</span><span class="sxs-lookup"><span data-stu-id="d65e4-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="d65e4-214">默认情况下，观察程序节点在实施测试时使用组织的外部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="d65e4-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="d65e4-215">但是，观察程序节点也可以配置为使用组织的内部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="d65e4-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="d65e4-216">这使管理员可验证位于外围网络内的用户的 URL 访问权限。</span><span class="sxs-lookup"><span data-stu-id="d65e4-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="d65e4-217">若要将观察程序节点配置为使用内部 Url 而不是外部 Url，请将 UseInternalWebURls 属性设置为 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="d65e4-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="d65e4-218">将此属性重置为默认值 False （$False）将导致观察程序再次使用外部 Url：</span><span class="sxs-lookup"><span data-stu-id="d65e4-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="d65e4-219">综合事务的特殊设置说明</span><span class="sxs-lookup"><span data-stu-id="d65e4-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="d65e4-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d65e4-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d65e4-221">大多数综合事务可以按方式在观察程序节点上运行。</span><span class="sxs-lookup"><span data-stu-id="d65e4-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="d65e4-222">在大多数情况下，一旦将综合事务添加到观察程序节点配置设置，观察程序节点就可以开始在其测试传递过程中使用该合成事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="d65e4-223">但是，有些合成事务需要特殊的安装说明，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="d65e4-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="d65e4-224">数据会议综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-225">如果您的观察程序节点计算机位于您的外围网络之外，则您可能无法运行数据会议综合事务，除非您先禁用 Windows Internet Explorer®网络的 Internet 浏览器代理设置服务帐户，方法是完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d65e4-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="d65e4-226">在观察程序节点计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="d65e4-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="d65e4-227">在控制台窗口中，键入以下命令，然后按 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="d65e4-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="d65e4-228">您将在命令窗口中看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="d65e4-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="d65e4-229">BITSAdmin 已弃用，并不保证在将来的 Windows 版本中可用。</span><span class="sxs-lookup"><span data-stu-id="d65e4-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="d65e4-230">BITS 服务的管理工具现在由 BITS PowerShell cmdlet 提供。</span><span class="sxs-lookup"><span data-stu-id="d65e4-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="d65e4-231">帐户 NetworkService 的 Internet 代理设置设置为 NO_PROXY。</span><span class="sxs-lookup"><span data-stu-id="d65e4-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="d65e4-232">（connection = default）</span><span class="sxs-lookup"><span data-stu-id="d65e4-232">(connection = default)</span></span>
  
<span data-ttu-id="d65e4-233">此消息表明您已禁用网络服务帐户的 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="d65e4-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="d65e4-234">Exchange 统一消息综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-235">Exchange 统一消息（UM）综合事务验证测试用户是否可以连接到 Exchange 中托管的语音邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="d65e4-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="d65e4-236">将需要使用语音邮件帐户对测试用户进行预配置。</span><span class="sxs-lookup"><span data-stu-id="d65e4-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="d65e4-237">持久聊天综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-238">若要使用持久聊天综合事务，必须先创建一个通道，并向测试用户授予使用该功能的权限。</span><span class="sxs-lookup"><span data-stu-id="d65e4-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="d65e4-239">您可以使用持久聊天综合事务来配置此通道：</span><span class="sxs-lookup"><span data-stu-id="d65e4-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="d65e4-240">必须运行此安装任务，才能从企业内部运行：</span><span class="sxs-lookup"><span data-stu-id="d65e4-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="d65e4-241">如果从非服务器计算机运行，则执行 cmdlet 的用户必须是基于角色的访问控制（RBAC）的 CsPersistentChatAdministrators 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d65e4-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="d65e4-242">如果从服务器本身运行，则执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="d65e4-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="d65e4-243">PSTN 对等呼叫综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-244">CsPstnPeerToPeerCall 综合事务验证通过公用电话交换网（PSTN）拨打和接听呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="d65e4-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="d65e4-245">若要运行此综合事务，您必须进行以下配置：</span><span class="sxs-lookup"><span data-stu-id="d65e4-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="d65e4-246">启用了 UC 的两个测试用户（一个呼叫者和一个接收器）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="d65e4-247">为每个用户帐户配置外线直拨分机 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="d65e4-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="d65e4-248">允许呼叫接收器的号码以到达 PSTN 网关的 VoIP 策略和语音路由。</span><span class="sxs-lookup"><span data-stu-id="d65e4-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="d65e4-249">一种 PSTN 网关，该网关接受根据拨打的号码将呼叫路由回接收器主池的呼叫和媒体。</span><span class="sxs-lookup"><span data-stu-id="d65e4-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="d65e4-250">统一联系人存储综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-251">统一联系人存储综合事务可验证 Skype for Business Server 代表用户从 Exchange 检索联系人的能力。</span><span class="sxs-lookup"><span data-stu-id="d65e4-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="d65e4-252">若要使用此综合事务，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="d65e4-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="d65e4-253">Lyss-必须配置 Exchange server 到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="d65e4-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="d65e4-254">测试用户必须具有有效的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="d65e4-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="d65e4-255">满足这些条件后，可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange：</span><span class="sxs-lookup"><span data-stu-id="d65e4-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="d65e4-256">测试用户联系人列表可能需要一段时间才能迁移到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="d65e4-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="d65e4-257">若要监视迁移进度，可以在没有-Setup 标志的情况下运行相同的命令行：</span><span class="sxs-lookup"><span data-stu-id="d65e4-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="d65e4-258">迁移完成后，此命令行将会成功。</span><span class="sxs-lookup"><span data-stu-id="d65e4-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="d65e4-259">XMPP 综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-260">可扩展消息传递和状态协议（XMPP） IM 合成事务要求您为 XMPP 功能配置一个或多个联盟域。</span><span class="sxs-lookup"><span data-stu-id="d65e4-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="d65e4-261">若要启用 XMPP 综合事务，必须在可路由的 XMPP 域中提供具有用户帐户的 XmppTestReceiverMailAddress 参数。</span><span class="sxs-lookup"><span data-stu-id="d65e4-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="d65e4-262">例如：</span><span class="sxs-lookup"><span data-stu-id="d65e4-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="d65e4-263">在此示例中，需要有一个 Skype for Business 服务器规则，以将 litwareinc.com 的邮件路由到 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="d65e4-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="d65e4-264">XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="d65e4-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d65e4-265">有关详细信息，请参阅[迁移 XMPP 联合](../migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="d65e4-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="d65e4-266">视频互操作服务器（VIS）综合事务</span><span class="sxs-lookup"><span data-stu-id="d65e4-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="d65e4-267">视频互操作服务器（VIS）综合事务要求您下载并安装综合事务支持文件（[VISSTSupportPackage](https://www.microsoft.com/download/details.aspx?id=46921)）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="d65e4-268">若要安装 VISSTSupportPackage，请确保已安装 msi 的依赖项（在 "系统要求" 下）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="d65e4-269">运行 VISSTSupportPackage 以执行简单安装。</span><span class="sxs-lookup"><span data-stu-id="d65e4-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="d65e4-270">.Msi 安装以下路径中的所有文件： "%ProgramFiles%\VIS 综合事务支持包"。</span><span class="sxs-lookup"><span data-stu-id="d65e4-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="d65e4-271">有关如何运行 VIS 综合事务的更多详细信息，请参阅[CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="d65e4-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="d65e4-272">更改综合事务的运行频率</span><span class="sxs-lookup"><span data-stu-id="d65e4-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="d65e4-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d65e4-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d65e4-274">默认情况下，综合事务将每15分钟运行一次配置的用户。</span><span class="sxs-lookup"><span data-stu-id="d65e4-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="d65e4-275">综合事务在一组用户中按顺序运行，以避免两个合成事务相互冲突。</span><span class="sxs-lookup"><span data-stu-id="d65e4-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="d65e4-276">需要更长的时间间隔，以提供所有综合事务的完成时间。</span><span class="sxs-lookup"><span data-stu-id="d65e4-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="d65e4-277">如果需要更频繁地运行综合事务，应减少使用一组给定用户运行的合成事务的数量，以便可以在所需的时间范围内完成这些测试，以避免偶尔出现的网络延迟。</span><span class="sxs-lookup"><span data-stu-id="d65e4-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="d65e4-278">如果需要运行更多的合成事务，请创建更多的用户集来运行其他综合事务。</span><span class="sxs-lookup"><span data-stu-id="d65e4-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="d65e4-279">若要更改运行综合事务的频率，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d65e4-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="d65e4-280">打开 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="d65e4-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="d65e4-281">单击 "创作部分"。</span><span class="sxs-lookup"><span data-stu-id="d65e4-281">Click Authoring section.</span></span> <span data-ttu-id="d65e4-282">单击 "规则" 部分（在 "创作" 下）</span><span class="sxs-lookup"><span data-stu-id="d65e4-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="d65e4-283">在 "规则" 部分中，查找名称为 "主合成事务运行程序性能收集规则" 的规则</span><span class="sxs-lookup"><span data-stu-id="d65e4-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="d65e4-284">右键单击该规则，然后选择 "覆盖"，选择 "覆盖规则"，然后选择 "对类的所有对象：池监视程序"</span><span class="sxs-lookup"><span data-stu-id="d65e4-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="d65e4-285">在 "替代属性" 窗口中，选择 "参数名称" "Frequency"，并将替代值设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="d65e4-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="d65e4-286">在同一窗口中，选择需要应用此替代的管理包</span><span class="sxs-lookup"><span data-stu-id="d65e4-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="d65e4-287">使用综合事务的富日志记录</span><span class="sxs-lookup"><span data-stu-id="d65e4-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="d65e4-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d65e4-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d65e4-289">综合事务证明在帮助确定系统问题方面极其有用。</span><span class="sxs-lookup"><span data-stu-id="d65e4-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="d65e4-290">例如，CsRegistration cmdlet 可能会提醒管理员，这实际上是用户在使用 Skype for business 服务器注册时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="d65e4-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="d65e4-291">但是，可能需要更多详细信息来确定失败的实际原因。</span><span class="sxs-lookup"><span data-stu-id="d65e4-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="d65e4-292">因此，综合事务提供了丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="d65e4-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="d65e4-293">对于综合事务 undertakes 的每个活动，使用丰富的日志记录，记录以下信息：</span><span class="sxs-lookup"><span data-stu-id="d65e4-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="d65e4-294">活动启动的时间。</span><span class="sxs-lookup"><span data-stu-id="d65e4-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="d65e4-295">活动完成的时间。</span><span class="sxs-lookup"><span data-stu-id="d65e4-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="d65e4-296">执行的操作（例如，创建、加入或离开会议; 登录到 Skype for business 服务器; 发送即时消息）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="d65e4-297">在活动运行时生成的参考消息、详细消息、警告消息或错误消息</span><span class="sxs-lookup"><span data-stu-id="d65e4-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="d65e4-298">SIP 注册邮件。</span><span class="sxs-lookup"><span data-stu-id="d65e4-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="d65e4-299">在活动运行时生成的异常记录或诊断代码。</span><span class="sxs-lookup"><span data-stu-id="d65e4-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="d65e4-300">运行活动的最终结果。</span><span class="sxs-lookup"><span data-stu-id="d65e4-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="d65e4-301">每次运行一个综合事务时，都会自动生成此信息，但不会自动将其显示或保存到日志文件中。</span><span class="sxs-lookup"><span data-stu-id="d65e4-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d65e4-302">如果手动运行的是综合事务，则可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="d65e4-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d65e4-303">在这里，可以选择使用两种方法之一以 XML 或 HTML 格式在富日志中保存和/或查看错误消息。</span><span class="sxs-lookup"><span data-stu-id="d65e4-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="d65e4-304">若要检索故障排除信息，请指定 OutLoggerVariable 参数，后跟您选择的变量名称：</span><span class="sxs-lookup"><span data-stu-id="d65e4-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="d65e4-305">：请勿在变量名称前面加上 $ 字符。</span><span class="sxs-lookup"><span data-stu-id="d65e4-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="d65e4-306">使用变量名，如 RegistrationTest （不 $RegistrationTest）。</span><span class="sxs-lookup"><span data-stu-id="d65e4-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="d65e4-307">运行此命令时，将看到类似如下的输出：</span><span class="sxs-lookup"><span data-stu-id="d65e4-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="d65e4-308">目标 Fqdn： atl-cs-001.litwareinc.com 结果：故障延迟：00:00:00 错误消息：此计算机没有任何已分配的证书。</span><span class="sxs-lookup"><span data-stu-id="d65e4-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="d65e4-309">诊断：您可以访问有关此故障的更多详细信息，而不只是此处显示的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d65e4-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="d65e4-310">若要以 HTML 格式访问此信息，请使用与此类似的命令将变量 RegistrationTest 中存储的信息保存到 HTML 文件中：</span><span class="sxs-lookup"><span data-stu-id="d65e4-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="d65e4-311">您也可以使用 ToXML() 方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="d65e4-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="d65e4-312">您可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序来查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="d65e4-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="d65e4-313">从 System Center Operations Manager 内部运行的综合事务将自动为故障生成这些日志文件。</span><span class="sxs-lookup"><span data-stu-id="d65e4-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d65e4-314">如果在 Skype for business Server PowerShell 能够加载和运行综合事务之前执行失败，则不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="d65e4-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d65e4-315">默认情况下，Skype for Business Server 将日志文件保存到未共享的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d65e4-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d65e4-316">若要方便地访问这些日志，应共享此文件夹。</span><span class="sxs-lookup"><span data-stu-id="d65e4-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="d65e4-317">例如： \\atl-观察程序-litwareinc. com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="d65e4-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
