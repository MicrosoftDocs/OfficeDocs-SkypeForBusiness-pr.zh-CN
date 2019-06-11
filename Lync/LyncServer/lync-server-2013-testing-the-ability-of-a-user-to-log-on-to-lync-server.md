---
title: 'Lync Server 2013: 测试用户登录 Lync Server 的能力'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="409a3-102">测试用户登录 Lync Server 2013 的能力</span><span class="sxs-lookup"><span data-stu-id="409a3-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="409a3-103">_**主题上次修改时间:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="409a3-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="409a3-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="409a3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="409a3-105">每天</span><span class="sxs-lookup"><span data-stu-id="409a3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="409a3-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="409a3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="409a3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="409a3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="409a3-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="409a3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="409a3-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="409a3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="409a3-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsRegistration cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="409a3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="409a3-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="409a3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="409a3-112">说明</span><span class="sxs-lookup"><span data-stu-id="409a3-112">Description</span></span>

<span data-ttu-id="409a3-113">CsRegistration cmdlet 使你能够验证你的组织中的用户是否可以登录 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="409a3-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="409a3-114">运行 Test CsRegistration 时, cmdlet 会尝试登录到 Lync Server 的测试用户, 如果成功, 则将测试用户从系统断开连接。</span><span class="sxs-lookup"><span data-stu-id="409a3-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="409a3-115">所有这些操作在没有任何用户交互的情况下发生, 并且不会影响任何实际用户。</span><span class="sxs-lookup"><span data-stu-id="409a3-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="409a3-116">例如, 假设测试帐户 sip:kenmyer@litwareinc.com 对应于具有真实 Lync 服务器帐户的真实用户。</span><span class="sxs-lookup"><span data-stu-id="409a3-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="409a3-117">在这种情况下, 将在不中断真正的 Ken Myer 的情况下执行测试。</span><span class="sxs-lookup"><span data-stu-id="409a3-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="409a3-118">当 Ken Myer 测试帐户从系统注销时, 该用户将保持登录状态的 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="409a3-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="409a3-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="409a3-119">Running the test</span></span>

<span data-ttu-id="409a3-120">CsRegistration cmdlet 可以使用预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="409a3-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="409a3-121">若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 注册机构的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="409a3-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="409a3-122">例如：</span><span class="sxs-lookup"><span data-stu-id="409a3-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="409a3-123">若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="409a3-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="409a3-124">然后, 在调用 Test-CsRegistration 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="409a3-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="409a3-125">有关详细信息, 请参阅[CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="409a3-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="409a3-126">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="409a3-126">Determining success or failure</span></span>

<span data-ttu-id="409a3-127">如果指定用户可以登录到 (然后从 Lync Server 注销), 你将收到与以下内容类似的输出, 结果属性标记为**成功:**</span><span class="sxs-lookup"><span data-stu-id="409a3-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="409a3-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="409a3-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="409a3-129">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="409a3-129">Result : Success</span></span>

<span data-ttu-id="409a3-130">延迟:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="409a3-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="409a3-131">时发生</span><span class="sxs-lookup"><span data-stu-id="409a3-131">Error :</span></span>

<span data-ttu-id="409a3-132">自检</span><span class="sxs-lookup"><span data-stu-id="409a3-132">Diagnosis :</span></span>

<span data-ttu-id="409a3-133">如果指定的用户无法登录或注销, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="409a3-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="409a3-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="409a3-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="409a3-135">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="409a3-135">Result : Failure</span></span>

<span data-ttu-id="409a3-136">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="409a3-136">Latency : 00:00:00</span></span>

<span data-ttu-id="409a3-137">错误: 404, 未找到</span><span class="sxs-lookup"><span data-stu-id="409a3-137">Error : 404, Not Found</span></span>

<span data-ttu-id="409a3-138">诊断: ErrorCode = 1003, source = atl-litwareinc, Reason = User</span><span class="sxs-lookup"><span data-stu-id="409a3-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="409a3-139">不存在</span><span class="sxs-lookup"><span data-stu-id="409a3-139">not exist</span></span>

<span data-ttu-id="409a3-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="409a3-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="409a3-141">例如, 以前的输出表明由于找不到指定用户, 测试失败。</span><span class="sxs-lookup"><span data-stu-id="409a3-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="409a3-142">可通过运行以下命令确定 SIP 地址是否有效 (以及用户是否已为 Lync Server 启用了该 SIP 地址):</span><span class="sxs-lookup"><span data-stu-id="409a3-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="409a3-143">如果 CsRegistration 失败, 则可能需要重新运行测试, 这一次包括 Verbose 参数:</span><span class="sxs-lookup"><span data-stu-id="409a3-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="409a3-144">当包含 Verbose 参数时, CsRegistration 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="409a3-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="409a3-145">例如：</span><span class="sxs-lookup"><span data-stu-id="409a3-145">For example:</span></span>

<span data-ttu-id="409a3-146">详细: "注册" 活动已开始。</span><span class="sxs-lookup"><span data-stu-id="409a3-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="409a3-147">正在发送注册请求:</span><span class="sxs-lookup"><span data-stu-id="409a3-147">Sending Registration request:</span></span>

<span data-ttu-id="409a3-148">目标 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="409a3-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="409a3-149">用户 Sip 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="409a3-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="409a3-150">注册机构端口 = 5061。</span><span class="sxs-lookup"><span data-stu-id="409a3-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="409a3-151">已选中 "受信任" 身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="409a3-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="409a3-152">"终结点无法注册" 异常。</span><span class="sxs-lookup"><span data-stu-id="409a3-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="409a3-153">请参阅在执行工作流 STRegistrerWorkflow 时出现的特定原因的 ErrorCode。</span><span class="sxs-lookup"><span data-stu-id="409a3-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="409a3-154">异常调用堆栈: SipAsyncResult'1: ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="409a3-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="409a3-155">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="409a3-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="409a3-156">下面是测试 CsRegistration 可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="409a3-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="409a3-157">您指定了一个不正确的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="409a3-157">You specified an incorrect user account.</span></span> <span data-ttu-id="409a3-158">你可以通过运行类似如下所示的命令来验证用户帐户是否存在:</span><span class="sxs-lookup"><span data-stu-id="409a3-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="409a3-159">用户帐户有效, 但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="409a3-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="409a3-160">若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:</span><span class="sxs-lookup"><span data-stu-id="409a3-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="409a3-161">如果 Enabled 属性设置为 False, 则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="409a3-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="409a3-162">您指定了一个不正确的注册机构池。</span><span class="sxs-lookup"><span data-stu-id="409a3-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="409a3-163">你可以使用以下命令返回注册机构池的 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="409a3-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="409a3-164">注册机构池目前不可用。</span><span class="sxs-lookup"><span data-stu-id="409a3-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="409a3-165">尝试 ping 池以查看它是否响应:</span><span class="sxs-lookup"><span data-stu-id="409a3-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

