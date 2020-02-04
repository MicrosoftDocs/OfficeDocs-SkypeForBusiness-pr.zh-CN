---
title: Lync Server 2013：测试持久聊天
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
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="ad000-102">在 Lync Server 2013 中测试持久聊天</span><span class="sxs-lookup"><span data-stu-id="ad000-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad000-103">_**主题上次修改时间：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="ad000-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad000-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="ad000-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ad000-105">每天</span><span class="sxs-lookup"><span data-stu-id="ad000-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad000-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="ad000-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ad000-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad000-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad000-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="ad000-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ad000-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="ad000-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ad000-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行<strong>CsPersistentChatMessage</strong> cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ad000-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="ad000-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ad000-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ad000-112">说明</span><span class="sxs-lookup"><span data-stu-id="ad000-112">Description</span></span>

<span data-ttu-id="ad000-113">**CsPersistentChatMessage** cmdlet 验证一对测试用户是否可以使用持久聊天服务交换消息。</span><span class="sxs-lookup"><span data-stu-id="ad000-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="ad000-114">为此，该 cmdlet 将两个用户记录到 Lync Server 2013，将用户连接到持久聊天室，交换一对消息，然后退出聊天室并注销两个用户。</span><span class="sxs-lookup"><span data-stu-id="ad000-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="ad000-115">请注意，如果你没有创建任何聊天室，或者没有为两个测试用户帐户分配可访问永久聊天服务的持久聊天策略，则对此 cmdlet 的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="ad000-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ad000-116">运行测试</span><span class="sxs-lookup"><span data-stu-id="ad000-116">Running the test</span></span>

<span data-ttu-id="ad000-117">以下示例中所示的命令将测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能以登录 Lync Server 2013，然后使用持久聊天服务交换邮件。</span><span class="sxs-lookup"><span data-stu-id="ad000-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="ad000-118">为此，示例中的第一个命令使用**Get 凭据**Cmdlet 创建 Windows PowerShell 命令行界面凭据对象，该对象包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="ad000-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="ad000-119">（由于 "登录名"、\\"litwareinc pilar" 已作为参数包含，因此 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，所生成的凭据对象将存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="ad000-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="ad000-120">第二个命令执行相同操作，这一次返回 Ken Myer 帐户的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="ad000-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="ad000-121">使用凭据对象，第三个命令确定这两个用户是否可以使用持久聊天来登录 Lync Server 2013 和 exchange 邮件。</span><span class="sxs-lookup"><span data-stu-id="ad000-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="ad000-122">若要执行此任务，请使用以下参数调用**CsPersistentChatMessage** Cmdlet： TargetFqdn （注册机构池的 FQDN）;SenderSipAddress （第一测试用户的 SIP 地址）;SenderCredential （包含此同一用户的凭据的 Windows PowerShell 对象）;ReceiverSipAddress （其他测试用户的 SIP 地址）;和 ReceiverCredential （包含其他测试用户的凭据的 Windows PowerShell 对象）。</span><span class="sxs-lookup"><span data-stu-id="ad000-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ad000-123">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="ad000-123">Determining success or failure</span></span>

<span data-ttu-id="ad000-124">如果指定用户具有有效的位置策略，则会收到与此类似的输出，结果属性标记为**成功**：</span><span class="sxs-lookup"><span data-stu-id="ad000-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="ad000-125">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ad000-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ad000-126">结果：成功</span><span class="sxs-lookup"><span data-stu-id="ad000-126">Result : Success</span></span>

<span data-ttu-id="ad000-127">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ad000-127">Latency : 00:00:00</span></span>

<span data-ttu-id="ad000-128">错误消息：</span><span class="sxs-lookup"><span data-stu-id="ad000-128">Error Message :</span></span>

<span data-ttu-id="ad000-129">自检</span><span class="sxs-lookup"><span data-stu-id="ad000-129">Diagnosis :</span></span>

<span data-ttu-id="ad000-130">如果指定用户无法使用持久聊天服务交换邮件，则结果将显示为 "**失败**"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="ad000-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ad000-131">警告：无法读取给定的完全限定的注册机构端口号</span><span class="sxs-lookup"><span data-stu-id="ad000-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="ad000-132">域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="ad000-132">domain name (FQDN).</span></span> <span data-ttu-id="ad000-133">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="ad000-133">Using default Registrar port number.</span></span> <span data-ttu-id="ad000-134">除了</span><span class="sxs-lookup"><span data-stu-id="ad000-134">Exception:</span></span>

<span data-ttu-id="ad000-135">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="ad000-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="ad000-136">看</span><span class="sxs-lookup"><span data-stu-id="ad000-136">at</span></span>

<span data-ttu-id="ad000-137">SipSyntheticTransaction. TryRetri 的 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="ad000-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="ad000-138">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="ad000-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="ad000-139">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ad000-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ad000-140">结果：失败</span><span class="sxs-lookup"><span data-stu-id="ad000-140">Result : Failure</span></span>

<span data-ttu-id="ad000-141">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ad000-141">Latency : 00:00:00</span></span>

<span data-ttu-id="ad000-142">错误消息：10060，连接尝试失败，因为已连接的参与方</span><span class="sxs-lookup"><span data-stu-id="ad000-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ad000-143">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="ad000-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ad000-144">已建立连接失败，因为连接的主机已</span><span class="sxs-lookup"><span data-stu-id="ad000-144">established connection failed because connected host has</span></span>

<span data-ttu-id="ad000-145">无法响应\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="ad000-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="ad000-146">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="ad000-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ad000-147">已连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="ad000-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ad000-148">时间，或已建立的连接失败，因为已连接的主机</span><span class="sxs-lookup"><span data-stu-id="ad000-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ad000-149">无法响应</span><span class="sxs-lookup"><span data-stu-id="ad000-149">has failed to respond</span></span>

<span data-ttu-id="ad000-150">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="ad000-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="ad000-151">自检</span><span class="sxs-lookup"><span data-stu-id="ad000-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ad000-152">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="ad000-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="ad000-153">下面是**测试 CsPersistentChatMessage**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="ad000-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="ad000-154">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="ad000-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ad000-155">所需的测试帐户可能不存在或已正确创建。</span><span class="sxs-lookup"><span data-stu-id="ad000-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="ad000-156">可能存在导致测试超时的意外延迟的网络问题。</span><span class="sxs-lookup"><span data-stu-id="ad000-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad000-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad000-157">See Also</span></span>


[<span data-ttu-id="ad000-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="ad000-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="ad000-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="ad000-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="ad000-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="ad000-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

