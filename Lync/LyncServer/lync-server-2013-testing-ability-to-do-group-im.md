---
title: Lync Server 2013：测试执行组 IM 的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecb197f7ce8acbd4639be9ee20b93e6008922f3c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="96969-102">在 Lync Server 2013 中测试组 IM 的能力</span><span class="sxs-lookup"><span data-stu-id="96969-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96969-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="96969-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96969-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="96969-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="96969-105">每天</span><span class="sxs-lookup"><span data-stu-id="96969-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96969-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="96969-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="96969-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96969-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96969-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="96969-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="96969-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="96969-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="96969-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsGroupIM cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="96969-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="96969-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="96969-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="96969-112">说明</span><span class="sxs-lookup"><span data-stu-id="96969-112">Description</span></span>

<span data-ttu-id="96969-113">CsGroupIM cmdlet 验证组织中的用户是否可以执行组即时消息会话。</span><span class="sxs-lookup"><span data-stu-id="96969-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="96969-114">运行 CsGroupIM 时，cmdlet 会尝试将一对测试用户登录到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="96969-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="96969-115">如果登录成功，Test-CsGroupIM 将使用第一个测试用户创建新会议，然后邀请第二个用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="96969-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="96969-116">交换消息之后，这两个用户断开与系统的连接。</span><span class="sxs-lookup"><span data-stu-id="96969-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="96969-117">请注意，这一切在没有任何用户交互的情况下发生，而不会影响任何实际用户。</span><span class="sxs-lookup"><span data-stu-id="96969-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="96969-118">例如，假设测试帐户 sip:kenmyer@litwareinc.com 与具有实际 Lync Server 帐户的真实用户相对应。</span><span class="sxs-lookup"><span data-stu-id="96969-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="96969-119">在这种情况下，执行测试的过程中不会对真实的 Ken Myer 造成任何中断。</span><span class="sxs-lookup"><span data-stu-id="96969-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="96969-120">例如，即使从系统注销 Ken Myer 的测试帐户，Ken Myer 本人仍将保持已登录状态。</span><span class="sxs-lookup"><span data-stu-id="96969-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="96969-121">同样，实际 Ken Myer 不会收到加入会议的邀请。</span><span class="sxs-lookup"><span data-stu-id="96969-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="96969-122">该邀请将发送到测试帐户并由其接受。</span><span class="sxs-lookup"><span data-stu-id="96969-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="96969-123">有关详细信息，请参阅[CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="96969-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="96969-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="96969-124">Running the test</span></span>

<span data-ttu-id="96969-125">CsGroupIM cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="96969-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="96969-126">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="96969-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="96969-127">例如：</span><span class="sxs-lookup"><span data-stu-id="96969-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="96969-128">若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Lync Server 命令行管理程序凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="96969-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="96969-129">在调用 CsGroupIM 时，必须包括这些凭据对象和两个帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="96969-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="96969-130">有关详细信息，请参阅[CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="96969-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="96969-131">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="96969-131">Determining Success or Failure</span></span>

<span data-ttu-id="96969-132">如果两个用户可以完成组即时消息会话，您将收到与以下内容类似的输出，其中结果属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="96969-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="96969-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96969-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96969-134">结果：成功</span><span class="sxs-lookup"><span data-stu-id="96969-134">Result : Success</span></span>

<span data-ttu-id="96969-135">延迟：00：00：06.3812203</span><span class="sxs-lookup"><span data-stu-id="96969-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="96969-136">误差</span><span class="sxs-lookup"><span data-stu-id="96969-136">Error :</span></span>

<span data-ttu-id="96969-137">诊断</span><span class="sxs-lookup"><span data-stu-id="96969-137">Diagnosis :</span></span>

<span data-ttu-id="96969-138">如果两个用户无法完成即时消息会话，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="96969-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="96969-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96969-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96969-140">结果：失败</span><span class="sxs-lookup"><span data-stu-id="96969-140">Result : Failure</span></span>

<span data-ttu-id="96969-141">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="96969-141">Latency : 00:00:00</span></span>

<span data-ttu-id="96969-142">错误：未找到404</span><span class="sxs-lookup"><span data-stu-id="96969-142">Error : 404, Not Found</span></span>

<span data-ttu-id="96969-143">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="96969-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="96969-144">原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="96969-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="96969-145">尚.</span><span class="sxs-lookup"><span data-stu-id="96969-145">exist.</span></span>

<span data-ttu-id="96969-146">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="96969-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="96969-147">由于帐户不存在或尚未为 Lync Server 启用用户，因此以前的输出表明测试失败，因为其中至少有一个测试帐户无效。</span><span class="sxs-lookup"><span data-stu-id="96969-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="96969-148">您可以通过运行与以下内容类似的命令来验证帐户是否存在，以及帐户是否已启用 nm-第 14-第3级：</span><span class="sxs-lookup"><span data-stu-id="96969-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="96969-149">如果 CsGroupIM 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="96969-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="96969-150">包含 Verbose 参数时，CsGroupIM 将返回其在检查指定用户是否参与组即时消息会话的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="96969-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="96969-151">例如，如果您的测试失败，并且您被告知一个或多个用户帐户无效，则可以使用 Verbose 参数重新运行测试并确定哪个用户帐户无效：</span><span class="sxs-lookup"><span data-stu-id="96969-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="96969-152">发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="96969-152">Sending Registration request:</span></span>

 <span data-ttu-id="96969-153">目标 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96969-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="96969-154">用户 SIP 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96969-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="96969-155">寄存器端口 = 5061</span><span class="sxs-lookup"><span data-stu-id="96969-155">Register Port    = 5061</span></span>

<span data-ttu-id="96969-156">已选择身份验证类型 "IWA"。</span><span class="sxs-lookup"><span data-stu-id="96969-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="96969-157">"登录被拒绝" 异常。</span><span class="sxs-lookup"><span data-stu-id="96969-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="96969-158">检查是否正在使用正确的凭据，以及帐户是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="96969-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="96969-159">您可以看到，在此示例中，拥有 SIP 地址 sip:kenmyer@litwareinc.com 的用户无法登录。</span><span class="sxs-lookup"><span data-stu-id="96969-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="96969-160">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="96969-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="96969-161">以下是测试 CsGroupIM 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="96969-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="96969-162">您指定了不正确的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="96969-162">You specified an incorrect user account.</span></span> <span data-ttu-id="96969-163">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="96969-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="96969-164">用户帐户有效，但当前未对 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="96969-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="96969-165">若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="96969-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="96969-166">Get-csuser "sip:kenmyer@litwareinc.com" |选择-对象已启用</span><span class="sxs-lookup"><span data-stu-id="96969-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="96969-167">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="96969-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="96969-168">即时消息服务可能不可用。</span><span class="sxs-lookup"><span data-stu-id="96969-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="96969-169">使用 Lync Server，可以配置系统，以便在无法访问存档数据库时，即时消息不可用。</span><span class="sxs-lookup"><span data-stu-id="96969-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="96969-170">您可以通过运行与以下内容类似的命令来验证这一点：</span><span class="sxs-lookup"><span data-stu-id="96969-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="96969-171">如果将 BlockOnArchiveFailure 设置为 True，则应确定存档数据库是否可用。</span><span class="sxs-lookup"><span data-stu-id="96969-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="96969-172">您可以使用以下命令返回存档数据库的位置：</span><span class="sxs-lookup"><span data-stu-id="96969-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="96969-173">存档服务器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="96969-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="96969-174">您可以使用以下命令检索存档服务器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="96969-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="96969-175">然后，可以 ping 相应的服务器以验证其是否可用。</span><span class="sxs-lookup"><span data-stu-id="96969-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="96969-176">例如：</span><span class="sxs-lookup"><span data-stu-id="96969-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

