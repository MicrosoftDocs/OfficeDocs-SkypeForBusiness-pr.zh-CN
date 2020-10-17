---
title: Lync Server 2013：测试持久聊天
description: Lync Server 2013：测试持久聊天。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8b1dc4eef1870f1287dacdc1852ab1e24edd169
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556278"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="12821-103">在 Lync Server 2013 中测试持久聊天</span><span class="sxs-lookup"><span data-stu-id="12821-103">Testing persistent chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12821-104">_**上次修改的主题：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="12821-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12821-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="12821-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="12821-106">每天</span><span class="sxs-lookup"><span data-stu-id="12821-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12821-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="12821-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="12821-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12821-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12821-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="12821-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="12821-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="12821-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="12821-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>CsPersistentChatMessage</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="12821-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="12821-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="12821-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="12821-113">说明</span><span class="sxs-lookup"><span data-stu-id="12821-113">Description</span></span>

<span data-ttu-id="12821-114">**CsPersistentChatMessage** cmdlet 验证一对测试用户是否可以使用持久聊天服务交换邮件。</span><span class="sxs-lookup"><span data-stu-id="12821-114">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="12821-115">为执行此操作，cmdlet 会将两个用户记录到 Lync Server 2013，将用户连接到持久聊天室，交换一对消息，然后退出聊天室并注销两个用户。</span><span class="sxs-lookup"><span data-stu-id="12821-115">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="12821-116">请注意，如果您没有创建任何聊天室，或者没有为两个测试用户帐户分配可访问持久聊天服务的持久聊天策略，则调用此 cmdlet 将会失败。</span><span class="sxs-lookup"><span data-stu-id="12821-116">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="12821-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="12821-117">Running the test</span></span>

<span data-ttu-id="12821-118">下面的示例中所示的命令测试一对用户 (litwareinc \\ pilar and litwareinc \\ kenmyer) 登录到 Lync Server 2013，然后使用持久聊天服务交换邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="12821-118">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="12821-119">为执行此操作，示例中的第一个命令使用 **Get-Credential** Cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，该对象包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="12821-119">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="12821-120"> (因为登录名 litwareinc \\ pilar 包含为参数，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Pilar Ackerman 帐户的密码。 ) 生成的凭据对象将存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="12821-120">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="12821-121">第二个命令执行相同的操作，但这次返回的是 Ken Myer 帐户的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="12821-121">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="12821-122">使用 credential 对象时，第三个命令将确定这两个用户是否可以使用持久聊天登录 Lync Server 2013 和 exchange 邮件。</span><span class="sxs-lookup"><span data-stu-id="12821-122">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="12821-123">若要执行此任务，请使用以下参数调用 **CsPersistentChatMessage** Cmdlet： TargetFqdn (注册器池的 FQDN) ;SenderSipAddress (第一个测试用户) 的 SIP 地址;SenderCredential (包含此同一用户的凭据的 Windows PowerShell 对象) ;ReceiverSipAddress (其他测试用户) 的 SIP 地址;和 ReceiverCredential (Windows PowerShell 对象，其中包含其他测试用户) 的凭据。</span><span class="sxs-lookup"><span data-stu-id="12821-123">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="12821-124">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="12821-124">Determining success or failure</span></span>

<span data-ttu-id="12821-125">如果指定用户具有有效的位置策略，则将接收与以下内容类似的输出，并将 Result 属性标记为 " **成功**"：</span><span class="sxs-lookup"><span data-stu-id="12821-125">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="12821-126">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12821-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="12821-127">结果：成功</span><span class="sxs-lookup"><span data-stu-id="12821-127">Result : Success</span></span>

<span data-ttu-id="12821-128">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="12821-128">Latency : 00:00:00</span></span>

<span data-ttu-id="12821-129">错误消息：</span><span class="sxs-lookup"><span data-stu-id="12821-129">Error Message :</span></span>

<span data-ttu-id="12821-130">诊断</span><span class="sxs-lookup"><span data-stu-id="12821-130">Diagnosis :</span></span>

<span data-ttu-id="12821-131">如果指定用户无法使用持久聊天服务交换邮件，则结果将显示为 " **失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="12821-131">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="12821-132">警告：无法读取给定的完全限定的注册器端口号</span><span class="sxs-lookup"><span data-stu-id="12821-132">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="12821-133"> (FQDN) 的域名称。</span><span class="sxs-lookup"><span data-stu-id="12821-133">domain name (FQDN).</span></span> <span data-ttu-id="12821-134">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="12821-134">Using default Registrar port number.</span></span> <span data-ttu-id="12821-135">异常</span><span class="sxs-lookup"><span data-stu-id="12821-135">Exception:</span></span>

<span data-ttu-id="12821-136">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="12821-136">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="12821-137">个</span><span class="sxs-lookup"><span data-stu-id="12821-137">at</span></span>

<span data-ttu-id="12821-138">TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="12821-138">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="12821-139">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="12821-139">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="12821-140">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12821-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="12821-141">结果：失败</span><span class="sxs-lookup"><span data-stu-id="12821-141">Result : Failure</span></span>

<span data-ttu-id="12821-142">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="12821-142">Latency : 00:00:00</span></span>

<span data-ttu-id="12821-143">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="12821-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="12821-144">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="12821-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="12821-145">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="12821-145">established connection failed because connected host has</span></span>

<span data-ttu-id="12821-146">无法响应 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="12821-146">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="12821-147">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="12821-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="12821-148">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="12821-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="12821-149">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="12821-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="12821-150">未能响应</span><span class="sxs-lookup"><span data-stu-id="12821-150">has failed to respond</span></span>

<span data-ttu-id="12821-151">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="12821-151">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="12821-152">诊断</span><span class="sxs-lookup"><span data-stu-id="12821-152">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="12821-153">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="12821-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="12821-154">以下是 **测试 CsPersistentChatMessage** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="12821-154">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="12821-155">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="12821-155">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="12821-156">所需的测试帐户可能不存在或已正确创建。</span><span class="sxs-lookup"><span data-stu-id="12821-156">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="12821-157">可能存在导致测试超时的意外延迟的网络问题。</span><span class="sxs-lookup"><span data-stu-id="12821-157">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12821-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12821-158">See Also</span></span>


[<span data-ttu-id="12821-159">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="12821-159">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="12821-160">新 CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="12821-160">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="12821-161">CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="12821-161">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

