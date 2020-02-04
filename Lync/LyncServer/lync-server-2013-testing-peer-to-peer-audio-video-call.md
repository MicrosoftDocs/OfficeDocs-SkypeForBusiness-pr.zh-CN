---
title: Lync Server 2013：测试对等音频/视频通话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="3ea59-102">在 Lync Server 2013 中测试对等音频/视频呼叫</span><span class="sxs-lookup"><span data-stu-id="3ea59-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea59-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3ea59-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ea59-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="3ea59-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3ea59-105">每天</span><span class="sxs-lookup"><span data-stu-id="3ea59-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea59-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="3ea59-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3ea59-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ea59-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea59-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="3ea59-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3ea59-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="3ea59-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3ea59-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsP2PAV cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="3ea59-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="3ea59-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3ea59-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3ea59-112">说明</span><span class="sxs-lookup"><span data-stu-id="3ea59-112">Description</span></span>

<span data-ttu-id="3ea59-113">Test-CsP2PAV 用于确定一对测试用户是否可以参与对等 A/V 对话。</span><span class="sxs-lookup"><span data-stu-id="3ea59-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="3ea59-114">若要测试此方案，cmdlet 将通过登录到 Lync Server 的两个用户开始。</span><span class="sxs-lookup"><span data-stu-id="3ea59-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="3ea59-115">假设两次登录成功，第一位用户邀请第二位用户加入 A/V 呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ea59-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="3ea59-116">第二个用户接受呼叫，将测试两个用户之间的连接，然后结束呼叫并从系统中注销测试用户。</span><span class="sxs-lookup"><span data-stu-id="3ea59-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="3ea59-117">测试 CsP2PAV 实际上不执行 A/V 调用。</span><span class="sxs-lookup"><span data-stu-id="3ea59-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="3ea59-118">不会在测试用户之间交换多媒体信息。</span><span class="sxs-lookup"><span data-stu-id="3ea59-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="3ea59-119">相反，cmdlet 仅验证是否可以建立合适的连接，以及两个用户是否可以进行此类呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ea59-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="3ea59-120">有关详细信息，请参阅[CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="3ea59-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3ea59-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="3ea59-121">Running the test</span></span>

<span data-ttu-id="3ea59-122">CsP2PAV cmdlet 可以使用一对预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何两个用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="3ea59-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="3ea59-123">若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3ea59-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3ea59-124">例如：</span><span class="sxs-lookup"><span data-stu-id="3ea59-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3ea59-125">若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Lync Server 凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="3ea59-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="3ea59-126">然后，当你调用 Test-CsP2PAV 时，你必须包含这些凭据对象和两个帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="3ea59-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3ea59-127">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="3ea59-127">Determining success or failure</span></span>

<span data-ttu-id="3ea59-128">如果两个测试用户可以完成对等 A/V 调用，则会收到与以下内容类似的输出：结果属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="3ea59-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3ea59-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ea59-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ea59-130">结果：成功</span><span class="sxs-lookup"><span data-stu-id="3ea59-130">Result : Success</span></span>

<span data-ttu-id="3ea59-131">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="3ea59-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="3ea59-132">时发生</span><span class="sxs-lookup"><span data-stu-id="3ea59-132">Error :</span></span>

<span data-ttu-id="3ea59-133">自检</span><span class="sxs-lookup"><span data-stu-id="3ea59-133">Diagnosis :</span></span>

<span data-ttu-id="3ea59-134">如果测试用户无法完成呼叫，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="3ea59-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3ea59-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ea59-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ea59-136">结果：失败</span><span class="sxs-lookup"><span data-stu-id="3ea59-136">Result : Failure</span></span>

<span data-ttu-id="3ea59-137">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="3ea59-137">Latency : 00:00:00</span></span>

<span data-ttu-id="3ea59-138">错误：480，暂时不可用</span><span class="sxs-lookup"><span data-stu-id="3ea59-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="3ea59-139">诊断： ErrorCode = 15030，Source = atl-litwareinc，Reason = Failed</span><span class="sxs-lookup"><span data-stu-id="3ea59-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="3ea59-140">路由到 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3ea59-140">to route to Exchange Server</span></span>

<span data-ttu-id="3ea59-141">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="3ea59-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3ea59-142">例如，以前的输出表明由于无法联系 Microsoft Exchange Server，测试失败。</span><span class="sxs-lookup"><span data-stu-id="3ea59-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="3ea59-143">此错误消息通常表示 Exchange 统一消息的配置出现问题。</span><span class="sxs-lookup"><span data-stu-id="3ea59-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="3ea59-144">如果测试 CsP2PAV 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="3ea59-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="3ea59-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="3ea59-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="3ea59-146">当包含 Verbose 参数时，CsP2PAV 将返回它尝试的每个操作的分步帐户，因为它检查指定用户登录到 Lync 服务器的能力。</span><span class="sxs-lookup"><span data-stu-id="3ea59-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="3ea59-147">例如，假设测试未通过以下诊断：</span><span class="sxs-lookup"><span data-stu-id="3ea59-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="3ea59-148">ErrorCode = 6003，Source = atl-ws-01-litwareinc，Reason = 不支持的对话框外请求</span><span class="sxs-lookup"><span data-stu-id="3ea59-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="3ea59-149">如果重新运行 Test CsP2PAV 并包含 Verbose 参数，将获得如下输出：</span><span class="sxs-lookup"><span data-stu-id="3ea59-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="3ea59-150">详细： "注册" 活动已开始。</span><span class="sxs-lookup"><span data-stu-id="3ea59-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="3ea59-151">正在发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="3ea59-151">Sending Registration request:</span></span>

<span data-ttu-id="3ea59-152">目标 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ea59-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="3ea59-153">用户 Sip 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ea59-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="3ea59-154">注册机构端口 = 5062。</span><span class="sxs-lookup"><span data-stu-id="3ea59-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="3ea59-155">已选择身份验证类型 "IWA"。</span><span class="sxs-lookup"><span data-stu-id="3ea59-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="3ea59-156">"终结点无法注册" 异常。</span><span class="sxs-lookup"><span data-stu-id="3ea59-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="3ea59-157">有关特定原因，请参阅错误代码。 '</span><span class="sxs-lookup"><span data-stu-id="3ea59-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="3ea59-158">在 STP2PAVWorkflow 执行工作流期间发生。</span><span class="sxs-lookup"><span data-stu-id="3ea59-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="3ea59-159">尽管这可能不会很明显，但如果你仔细检查输出，你将看到指定的注册器端口（端口5062）不正确。</span><span class="sxs-lookup"><span data-stu-id="3ea59-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="3ea59-160">进而导致测试失败。</span><span class="sxs-lookup"><span data-stu-id="3ea59-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3ea59-161">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="3ea59-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="3ea59-162">下面是测试 CsP2PAV 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="3ea59-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="3ea59-163">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="3ea59-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="3ea59-164">你可以通过运行类似如下所示的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="3ea59-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="3ea59-165">Move-csuser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="3ea59-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="3ea59-166">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="3ea59-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3ea59-167">若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="3ea59-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="3ea59-168">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="3ea59-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

