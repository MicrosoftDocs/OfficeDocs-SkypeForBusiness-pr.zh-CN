---
title: 配置观察程序节点测试用户和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。
ms.openlocfilehash: ce0c82f6f850c7a2b632c828f938979747d99e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816111"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="ad9a3-103">配置观察程序节点测试用户和设置</span><span class="sxs-lookup"><span data-stu-id="ad9a3-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="ad9a3-104">**摘要：** 为 Skype for business Server 合成事务配置测试用户帐户和观察程序节点设置。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="ad9a3-105">在配置将用作观察者节点的计算机后，必须：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="ad9a3-106">配置要由这些观察程序节点使用的[测试用户帐户](test-users-and-settings.md#testuser)。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="ad9a3-107">如果你使用协商身份验证方法，你还必须使用**CsTestUserCredential** cmdlet 来启用这些测试帐户，以便在 "观察程序" 节点上使用。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="ad9a3-108">更新观察程序节点配置设置。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="ad9a3-109">配置测试用户帐户</span><span class="sxs-lookup"><span data-stu-id="ad9a3-109">Configure Test User Accounts</span></span>
<span data-ttu-id="ad9a3-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9a3-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="ad9a3-111">测试帐户不需要表示实际人员，但它们必须是有效的 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="ad9a3-112">此外，必须为 Skype for Business Server 启用这些帐户，它们必须具有有效的 SIP 地址，并且应该为企业语音启用（以使用 CsPstnPeerToPeerCall 合成事务）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="ad9a3-113">如果你使用的是 TrustedServer 身份验证方法，你需要做的就是确保这些帐户存在并按说明进行配置。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="ad9a3-114">你应该为要测试的每个池至少分配两个测试用户。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="ad9a3-115">如果你使用的是协商身份验证方法，你还必须使用 CsTestUserCredential cmdlet 和 Skype for Business Server Management Shell 来启用这些测试帐户以处理合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="ad9a3-116">通过运行类似于以下内容的命令来执行此操作（这些命令假设已创建两个 Active Directory 用户帐户，并且为 Skype for Business Server 启用了这些帐户）：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="ad9a3-117">你不仅必须包括 SIP 地址，还必须包括用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="ad9a3-118">如果不包含密码，CsTestUserCredential cmdlet 将提示你输入该信息。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="ad9a3-119">可以使用上述代码块中所示的域名 \ 用户名格式指定用户名。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="ad9a3-120">若要验证是否已创建测试用户凭据，请从 Skype for Business Server 命令行管理程序运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="ad9a3-121">将为每个用户返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="ad9a3-122">**用户名**</span><span class="sxs-lookup"><span data-stu-id="ad9a3-122">**UserName**</span></span>|<span data-ttu-id="ad9a3-123">**口令**</span><span class="sxs-lookup"><span data-stu-id="ad9a3-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad9a3-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="ad9a3-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="ad9a3-125">SecureString</span><span class="sxs-lookup"><span data-stu-id="ad9a3-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="ad9a3-126">使用默认合成事务配置基本观察程序节点</span><span class="sxs-lookup"><span data-stu-id="ad9a3-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="ad9a3-127">创建测试用户后，您可以使用类似下面的命令创建观察程序节点：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="ad9a3-128">此命令将创建一个新的监视程序节点，该节点使用默认设置并运行一组默认的合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="ad9a3-129">新的观察程序节点还使用 test users watcher1@litwareinc.com 和 watcher2@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="ad9a3-130">如果观察程序节点使用 TrustedServer 身份验证，则两个测试帐户可以是为 Active Directory 和 Skype for business 服务器启用的任何有效用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="ad9a3-131">如果观察程序节点使用协商身份验证方法，则还必须通过使用 CsTestUserCredential cmdlet 为观察程序节点启用这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="ad9a3-132">若要验证是否正确配置了目标池的自动发现，而不是定向到池，请改用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="ad9a3-133">配置扩展测试</span><span class="sxs-lookup"><span data-stu-id="ad9a3-133">Configuring Extended Tests</span></span>

<span data-ttu-id="ad9a3-134">如果你想要启用 PSTN 测试，从而验证与公共交换电话网络的连接，你需要在设置观察程序节点时执行其他一些配置。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="ad9a3-135">首先，您必须将测试用户与 PSTN 测试类型关联，方法是从 Skype for Business Server 命令行管理程序中运行如下命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="ad9a3-136">此命令的结果必须存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="ad9a3-137">在此示例中，变量被命名为 "$pstnTest"。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="ad9a3-138">接下来，你可以使用**CsWatcherNodeConfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）关联到 Skype For business 服务器池。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="ad9a3-139">例如，以下命令为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置、添加之前创建的两个测试用户以及添加 PSTN 测试类型：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="ad9a3-140">如果尚未在观察程序节点计算机上安装 Skype for business Server core 文件和 RTCLocal 数据库，上述命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="ad9a3-141">若要测试多个语音策略，可以使用**CsExtendedTest** cmdlet 为每个策略创建扩展测试。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="ad9a3-142">所提供的用户应配置所需的语音策略。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="ad9a3-143">扩展测试通过使用逗号分隔符传递到**CsWatcherNodeConfiguration** cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="ad9a3-144">-ExtendedTests @ {Add = $pstnTest 1，$pstnTest 2，$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="ad9a3-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="ad9a3-145">由于在未使用 "测试" 参数的情况下调用了**CsWatcherNodeConfiguration** cmdlet，因此将仅为新的观察程序节点启用默认合成事务（和指定的扩展合成事务）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="ad9a3-146">因此，观察程序节点将测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="ad9a3-147">注册</span><span class="sxs-lookup"><span data-stu-id="ad9a3-147">Registration</span></span>
    
- <span data-ttu-id="ad9a3-148">即时消息</span><span class="sxs-lookup"><span data-stu-id="ad9a3-148">IM</span></span>
    
- <span data-ttu-id="ad9a3-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="ad9a3-149">GroupIM</span></span>
    
- <span data-ttu-id="ad9a3-150">P2PAV （对等音频/视频会话）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="ad9a3-151">AvConference （音频/会议）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="ad9a3-152">状态</span><span class="sxs-lookup"><span data-stu-id="ad9a3-152">Presence</span></span>
    
- <span data-ttu-id="ad9a3-153">ABS （通讯簿服务）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="ad9a3-154">ABWQ （通讯簿 web 服务）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="ad9a3-155">默认情况下，不会测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="ad9a3-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="ad9a3-156">ASConference</span></span>
    
- <span data-ttu-id="ad9a3-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="ad9a3-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="ad9a3-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="ad9a3-158">DataConference</span></span>
    
- <span data-ttu-id="ad9a3-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="ad9a3-159">DialinConferencing</span></span>
    
- <span data-ttu-id="ad9a3-160">ExumConnectivity （Exchange 统一消息）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="ad9a3-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="ad9a3-161">JoinLauncher</span></span>
    
- <span data-ttu-id="ad9a3-162">MCXP2PIM （旧版移动设备即时消息）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="ad9a3-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="ad9a3-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="ad9a3-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="ad9a3-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="ad9a3-165">PSTN （PSTN 网关呼叫，指定为扩展测试）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="ad9a3-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="ad9a3-166">UcwaConference</span></span>
    
- <span data-ttu-id="ad9a3-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="ad9a3-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="ad9a3-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="ad9a3-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="ad9a3-169">添加和删除综合事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="ad9a3-170">配置了观察程序节点后，你可以使用 CsWatcherNodeConfiguration cmdlet 在节点中添加或删除合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="ad9a3-171">例如，若要向观察程序节点添加 PersistentChatMessage 测试，请使用 Add 方法和类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="ad9a3-172">可通过使用逗号分隔测试名称来添加多个测试。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="ad9a3-173">例如：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="ad9a3-174">如果这些测试中的一个或多个（例如，DataConference）已在观察程序节点上启用，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="ad9a3-175">在这种情况下，你将收到类似于以下内容的错误消息：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="ad9a3-176">Set-CsWatcherNodeConfiguration： "urn： schema： WatcherNode： TestName ' key 或 unique identity 约束有一个重复的键序列" DataConference "。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="ad9a3-177">发生此错误时，将不会应用任何更改。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="ad9a3-178">应在删除重复的测试后重新运行该命令。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="ad9a3-179">若要从观察程序节点中删除合成事务，请使用 Remove 方法。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="ad9a3-180">例如，此命令将从观察程序节点中删除 ABWQ 测试：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="ad9a3-181">可以使用 Replace 方法将当前启用的所有测试替换为一个或多个新测试。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="ad9a3-182">例如，如果你希望观察程序节点仅运行 IM 测试，则可以通过使用以下命令来配置它：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="ad9a3-183">运行此命令时，除 IM 外，指定的观察程序节点上的所有合成事务都将被禁用。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="ad9a3-184">查看和测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="ad9a3-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="ad9a3-185">如果要查看已分配给观察程序节点的测试，请使用类似下面的命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="ad9a3-186">此命令将根据分配给节点的合成事务返回类似于此的信息：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="ad9a3-187">注册 IM GroupIM P2PAV AvConference 状态 PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="ad9a3-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="ad9a3-188">若要按字母顺序查看合成事务，请改用以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="ad9a3-189">若要验证是否已创建观察程序节点，请在 Skype for Business Server Management Shell 中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="ad9a3-190">您将获得类似以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="ad9a3-191">标识： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ad9a3-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="ad9a3-192">TestUsers： {sip:watcher1@litwareinc.com，sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="ad9a3-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="ad9a3-193">ExtendedTests： {TestUsers = IList<String>;Name = PSTN 测试;Te ...}</span><span class="sxs-lookup"><span data-stu-id="ad9a3-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="ad9a3-194">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ad9a3-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="ad9a3-195">PortNumber：5061</span><span class="sxs-lookup"><span data-stu-id="ad9a3-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="ad9a3-196">若要验证是否正确配置了观察程序节点，请在 Skype for Business Server Management Shell 中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="ad9a3-197">此命令将在你的部署中测试每个观察程序节点并确认是否已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="ad9a3-198">已安装所需的注册机构角色。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="ad9a3-199">将创建所需的注册表项（在运行 CsWatcherNodeConfiguration cmdlet 时已完成）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="ad9a3-200">您的服务器运行的是正确版本的 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="ad9a3-201">您的端口配置正确。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="ad9a3-202">您分配的测试用户具有所需的凭据。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="ad9a3-203">管理观察程序节点</span><span class="sxs-lookup"><span data-stu-id="ad9a3-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="ad9a3-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9a3-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="ad9a3-205">除了修改在观察程序节点上执行的合成事务，还可以使用**CsWatcherNodeConfiguration** cmdlet 执行两个其他重要任务：启用和禁用 "观察程序" 节点，以及将观察程序节点配置为在运行其测试时使用内部 web url 或外部 web url。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="ad9a3-206">默认情况下，观察程序节点设计为定期运行其所有启用的合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="ad9a3-207">但是，有时您可能希望暂停这些交易。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="ad9a3-208">例如，如果观察程序节点暂时与网络断开连接，则没有理由运行合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="ad9a3-209">如果没有网络连接，这些事务将失败。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="ad9a3-210">若要暂时禁用观察程序节点，请从 Skype for Business 服务器管理外壳程序运行类似下面的命令：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="ad9a3-211">此命令将禁用观察程序节点 atl 观察程序001.litwareinc.com 上的合成事务的执行。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="ad9a3-212">若要恢复合成事务的执行，请将 Enabled 属性设置回 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="ad9a3-213">Enabled 属性可用于打开或关闭观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="ad9a3-214">如果要永久删除观察程序节点，请使用**CsWatcherNodeConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="ad9a3-215">该命令将从指定的计算机中删除所有观察程序节点配置设置，这将阻止计算机自动运行合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="ad9a3-216">但是，该命令不会卸载 System Center agent 文件或 Skype for business Server 系统文件。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="ad9a3-217">默认情况下，在执行测试时，观察程序节点使用组织的外部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="ad9a3-218">但是，观察程序节点也可以配置为使用组织的内部 Web Url。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="ad9a3-219">这使管理员能够验证位于外围网络内的用户的 URL 访问。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="ad9a3-220">若要将观察程序节点配置为使用内部 Url 而不是外部 Url，请将 UseInternalWebURls 属性设置为 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="ad9a3-221">将此属性重置为默认值 False （$False）将导致观察程序再次使用外部 Url：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="ad9a3-222">综合交易的特殊设置说明</span><span class="sxs-lookup"><span data-stu-id="ad9a3-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="ad9a3-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9a3-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="ad9a3-224">大多数合成事务可以按原样在观察程序节点上运行。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="ad9a3-225">在大多数情况下，一旦将合成事务添加到观察程序节点配置设置，观察程序节点就可以在其测试传递期间开始使用该合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="ad9a3-226">但是，存在一些需要特殊设置说明的合成事务，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="ad9a3-227">数据会议综合事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-228">如果你的观察程序节点计算机位于你的外围网络之外，则你可能无法运行数据会议合成事务，除非你首先禁用 Windows Internet Explorer®网络的 Internet 浏览器代理设置服务帐户，方法是完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="ad9a3-229">在观察程序节点计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="ad9a3-230">在控制台窗口中，键入以下命令，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-230">In the console window, type the following command and then press ENTER.</span></span> 
    
```console
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="ad9a3-231">您将在 "命令" 窗口中看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-231">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="ad9a3-232">BITSAdmin 已弃用，并且不保证在未来版本的 Windows 中可用。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-232">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="ad9a3-233">BITS 服务的管理工具现在由 BITS PowerShell cmdlet 提供。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-233">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="ad9a3-234">帐户网络版的 Internet 代理设置设置为 "NO_PROXY"。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-234">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="ad9a3-235">（连接 = 默认）</span><span class="sxs-lookup"><span data-stu-id="ad9a3-235">(connection = default)</span></span>
  
<span data-ttu-id="ad9a3-236">此消息表示你已禁用网络服务帐户的 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-236">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="ad9a3-237">Exchange 统一消息综合事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-237">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-238">Exchange 统一消息（UM）合成事务验证测试用户是否可以连接到位于 Exchange 中的语音邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-238">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="ad9a3-239">测试用户将需要通过语音邮件帐户进行预配置。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-239">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="ad9a3-240">持久聊天合成事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-240">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-241">若要使用持久聊天合成事务，必须首先创建一个通道，并向测试用户提供使用它的权限。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-241">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="ad9a3-242">你可以使用持久聊天合成事务来配置此通道：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-242">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="ad9a3-243">必须运行此设置任务才能从企业内部运行：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-243">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="ad9a3-244">如果从非服务器计算机运行，则执行 cmdlet 的用户必须是基于角色的访问控制（RBAC）的 CsPersistentChatAdministrators 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-244">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="ad9a3-245">如果从服务器本身运行，则执行 cmdlet 的用户必须是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-245">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="ad9a3-246">PSTN 对等呼叫综合事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-246">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-247">CsPstnPeerToPeerCall 合成事务可验证通过公共交换电话网络（PSTN）拨打和接听呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-247">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="ad9a3-248">若要运行此合成事务，必须配置：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-248">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="ad9a3-249">两个启用 UC 的测试用户（呼叫方和接收方）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-249">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="ad9a3-250">为每个用户帐户直接拨入（已有）号码。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-250">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="ad9a3-251">允许呼叫接收器网关的 VoIP 策略和语音路由。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-251">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="ad9a3-252">可接受呼叫和媒体的 PSTN 网关，它根据所拨打的号码将呼叫路由回接收器的主池。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-252">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="ad9a3-253">统一联系人存储综合事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-253">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-254">"统一联系人存储" 综合事务可验证 Skype for Business 服务器从 Exchange 代表用户检索联系人的能力。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-254">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="ad9a3-255">若要使用此合成事务，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-255">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="ad9a3-256">Lyss-必须配置 Exchange server 到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-256">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="ad9a3-257">测试用户必须具有有效的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-257">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="ad9a3-258">满足这些条件后，你可以运行以下 Windows PowerShell cmdlet 将测试用户的联系人列表迁移到 Exchange：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-258">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="ad9a3-259">将测试用户联系人列表迁移到 Exchange 可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-259">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="ad9a3-260">若要监视迁移进度，可以在没有-Setup 标志的情况下运行相同的命令行：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-260">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="ad9a3-261">完成迁移后，此命令行将成功。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-261">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="ad9a3-262">XMPP 合成事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-262">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-263">可扩展消息和状态协议（XMPP） IM 合成事务要求你将 XMPP 功能配置为一个或多个联合域。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-263">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="ad9a3-264">若要启用 XMPP 合成事务，必须在可路由的 XMPP 域中提供具有用户帐户的 XmppTestReceiverMailAddress 参数。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-264">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="ad9a3-265">例如：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-265">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="ad9a3-266">在此示例中，需要有 Skype for Business 服务器规则才能将 litwareinc.com 的邮件路由到 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-266">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="ad9a3-267">XMPP 网关和代理在 Skype for business Server 2015 中可用，但 Skype for business Server 2019 不再支持。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-267">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ad9a3-268">有关详细信息，请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-268">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="ad9a3-269">视频互操作服务器（VIS）合成事务</span><span class="sxs-lookup"><span data-stu-id="ad9a3-269">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="ad9a3-270">视频互操作服务器（VIS）合成事务需要你下载并安装合成事务支持文件（[VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921)）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-270">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="ad9a3-271">若要安装 VISSTSupportPackage，请确保已安装 msi 的依赖关系（在 "系统要求" 下）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-271">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="ad9a3-272">运行 VISSTSupportPackage 以执行简单安装。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-272">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="ad9a3-273">.Msi 将在以下路径中安装所有文件： "%ProgramFiles%\VIS 合成事务支持程序包"。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-273">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="ad9a3-274">有关如何运行 VIS 合成事务的更多详细信息，请参阅[CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-274">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="ad9a3-275">更改综合事务的运行频率</span><span class="sxs-lookup"><span data-stu-id="ad9a3-275">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="ad9a3-276"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9a3-276"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="ad9a3-277">默认情况下，综合事务将每15分钟与配置的用户一起运行。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-277">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="ad9a3-278">在一组用户中按顺序运行合成事务，以避免两个合成事务相互冲突。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-278">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="ad9a3-279">需要较长的时间间隔才能完成所有合成事务的完成。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-279">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="ad9a3-280">如果需要更频繁地运行合成事务，则应减少使用一组给定用户运行的合成事务的数量，以便可以在所需的时间范围内完成测试，以便在偶尔的网络延迟中使用某些缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-280">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="ad9a3-281">如果需要运行更多合成事务，请创建更多用户集以运行其他合成事务。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-281">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="ad9a3-282">若要更改运行合成事务的频率，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-282">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="ad9a3-283">打开 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-283">Open System Center Operations Manager.</span></span> <span data-ttu-id="ad9a3-284">单击 "创作分区"。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-284">Click Authoring section.</span></span> <span data-ttu-id="ad9a3-285">单击 "规则" 部分（在 "创作" 下）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-285">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="ad9a3-286">在 "规则" 部分中，找到名称为 "主合成事务运行程序性能收集规则" 的规则。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-286">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="ad9a3-287">右键单击该规则，然后选择 "替代"，选择 "替代规则"，然后选择 "对于类：池监视程序的所有对象"。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-287">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="ad9a3-288">在 "替代属性" 窗口中，选择 "参数名称" "Frequency"，然后将替代值设置为所需值。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-288">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="ad9a3-289">在同一窗口中，选择需要应用此覆盖的管理包。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-289">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="ad9a3-290">对综合事务使用丰富日志记录</span><span class="sxs-lookup"><span data-stu-id="ad9a3-290">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="ad9a3-291"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9a3-291"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="ad9a3-292">综合事务证明在帮助识别系统问题方面极其有用。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-292">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="ad9a3-293">例如，CsRegistration cmdlet 可以向管理员发出警告，指出用户在向 Skype for Business 服务器注册时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-293">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="ad9a3-294">但是，可能需要其他详细信息来确定失败的实际原因。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-294">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="ad9a3-295">出于此原因，综合事务提供了丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-295">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="ad9a3-296">对于综合事务仅负责的每个活动，有丰富的日志记录，记录以下信息：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-296">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="ad9a3-297">活动开始的时间。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-297">The time that the activity started.</span></span>
    
- <span data-ttu-id="ad9a3-298">活动完成的时间。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-298">The time that the activity finished.</span></span>
    
- <span data-ttu-id="ad9a3-299">执行的操作（例如，创建、加入或离开会议; 登录到 Skype for Business 服务器; 发送即时消息）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-299">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="ad9a3-300">在活动运行时生成的信息、详细、警告或错误消息。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-300">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="ad9a3-301">SIP 注册消息。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-301">SIP registration messages.</span></span>
    
- <span data-ttu-id="ad9a3-302">在活动运行时生成的异常记录或诊断代码。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-302">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="ad9a3-303">运行活动的最终结果。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-303">The net result of running the activity.</span></span>
    
<span data-ttu-id="ad9a3-304">此信息会在每次运行合成事务时自动生成，但不会自动显示或保存到日志文件。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-304">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="ad9a3-305">如果你手动运行合成事务，则可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-305">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="ad9a3-306">从这里，你可以选择使用两种方法之一以 XML 或 HTML 格式在富短日志中保存和/或查看错误消息。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-306">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="ad9a3-307">若要检索疑难解答信息，请指定 OutLoggerVariable 参数，后跟你选择的变量名称：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-307">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="ad9a3-308">不要在变量名前面加 $ 字符。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-308">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="ad9a3-309">使用变量名称，例如 RegistrationTest （not $RegistrationTest）。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-309">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="ad9a3-310">运行此命令时，将看到类似以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-310">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="ad9a3-311">目标 Fqdn： atl-cs-001.litwareinc.com 结果：故障延迟：00:00:00 错误消息：此计算机没有任何已分配的证书。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-311">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="ad9a3-312">诊断：你可以访问与此处所示错误消息更详细的此失败信息。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-312">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="ad9a3-313">若要以 HTML 格式访问此信息，请使用与此类似的命令将变量 RegistrationTest 中存储的信息保存到 HTML 文件中：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-313">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="ad9a3-314">或者，你可以使用 ToXML （）方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="ad9a3-314">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="ad9a3-315">你可以使用 Windows Internet Explorer、Microsoft Visual Studio 或任何能够打开 HTML/XML 文件的其他应用程序查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-315">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="ad9a3-316">从 System Center Operations Manager 内部运行的合成事务将自动为故障生成这些日志文件。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-316">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="ad9a3-317">如果在 Skype for business Server PowerShell 能够加载和运行合成事务之前执行失败，则不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-317">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ad9a3-318">默认情况下，Skype for business 服务器将日志文件保存到未共享的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-318">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="ad9a3-319">为使这些日志易于访问，您应该共享此文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-319">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="ad9a3-320">例如： \\atl-观察程序-001. litwareinc com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="ad9a3-320">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
