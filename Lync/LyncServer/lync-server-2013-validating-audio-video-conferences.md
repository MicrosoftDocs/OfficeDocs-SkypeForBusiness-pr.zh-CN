---
title: Lync Server 2013：验证音频/视频会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82abbf918f4b375c10fdf201591e099f5cd4262e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="2adcc-102">在 Lync Server 2013 中验证音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="2adcc-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2adcc-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2adcc-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2adcc-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="2adcc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2adcc-105">每天</span><span class="sxs-lookup"><span data-stu-id="2adcc-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2adcc-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="2adcc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2adcc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2adcc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2adcc-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="2adcc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2adcc-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="2adcc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2adcc-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsAVConference cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="2adcc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="2adcc-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2adcc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2adcc-112">说明</span><span class="sxs-lookup"><span data-stu-id="2adcc-112">Description</span></span>

<span data-ttu-id="2adcc-113">CsAVConference cmdlet 检查两个测试用户是否可以参与音频/视频（A/V）会议。</span><span class="sxs-lookup"><span data-stu-id="2adcc-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="2adcc-114">运行此 cmdlet 时，这两个用户将登录系统。</span><span class="sxs-lookup"><span data-stu-id="2adcc-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="2adcc-115">成功登录后，第一个用户会创建 A/V 会议，然后等待第二个用户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="2adcc-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="2adcc-116">简单交换数据之后，删除此会议并注销这两个测试用户。</span><span class="sxs-lookup"><span data-stu-id="2adcc-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="2adcc-117">请注意，CsAVConference 不会在两个测试用户之间进行实际的 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="2adcc-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="2adcc-118">相反，cmdlet 会验证两个用户是否可以建立执行此类会议所需的所有连接。</span><span class="sxs-lookup"><span data-stu-id="2adcc-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="2adcc-119">在[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)中，可以找到此命令的更多示例。</span><span class="sxs-lookup"><span data-stu-id="2adcc-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2adcc-120">运行测试</span><span class="sxs-lookup"><span data-stu-id="2adcc-120">Running the test</span></span>

<span data-ttu-id="2adcc-121">CsAVConference cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="2adcc-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="2adcc-122">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="2adcc-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="2adcc-123">例如：</span><span class="sxs-lookup"><span data-stu-id="2adcc-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="2adcc-124">若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="2adcc-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="2adcc-125">然后，在调用 CsAVConference 时，必须包含两个帐户的凭据对象和 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="2adcc-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="2adcc-126">有关详细信息，请参阅[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="2adcc-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2adcc-127">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="2adcc-127">Determining Success or Failure</span></span>

<span data-ttu-id="2adcc-128">如果指定用户可以成功完成 A/V 会议，则会收到与以下内容类似的输出，并将 Result 属性标记为 "**成功"：**</span><span class="sxs-lookup"><span data-stu-id="2adcc-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2adcc-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2adcc-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2adcc-130">结果：成功</span><span class="sxs-lookup"><span data-stu-id="2adcc-130">Result : Success</span></span>

<span data-ttu-id="2adcc-131">延迟：00：00：02.6841765</span><span class="sxs-lookup"><span data-stu-id="2adcc-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="2adcc-132">误差</span><span class="sxs-lookup"><span data-stu-id="2adcc-132">Error :</span></span>

<span data-ttu-id="2adcc-133">诊断</span><span class="sxs-lookup"><span data-stu-id="2adcc-133">Diagnosis :</span></span>

<span data-ttu-id="2adcc-134">如果用户无法完成会议，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="2adcc-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2adcc-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2adcc-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2adcc-136">结果：失败</span><span class="sxs-lookup"><span data-stu-id="2adcc-136">Result : Failure</span></span>

<span data-ttu-id="2adcc-137">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="2adcc-137">Latency : 00:00:00</span></span>

<span data-ttu-id="2adcc-138">错误：未找到404</span><span class="sxs-lookup"><span data-stu-id="2adcc-138">Error : 404, Not Found</span></span>

<span data-ttu-id="2adcc-139">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="2adcc-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="2adcc-140">原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="2adcc-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="2adcc-141">尚.</span><span class="sxs-lookup"><span data-stu-id="2adcc-141">exist.</span></span>

<span data-ttu-id="2adcc-142">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="2adcc-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="2adcc-143">例如，由于帐户不存在或尚未为 Lync Server 启用帐户，因此以前的输出显示测试失败，因为这两个用户帐户中至少有一个帐户无效。</span><span class="sxs-lookup"><span data-stu-id="2adcc-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="2adcc-144">您可以通过运行与以下内容类似的命令来验证这两个测试帐户是否存在，以及是否为 Lync Server 启用了这些帐户：</span><span class="sxs-lookup"><span data-stu-id="2adcc-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="2adcc-145">如果 CsAVConference 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="2adcc-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="2adcc-146">当包含 Verbose 参数时，CsAVConference 将返回其在检查指定用户是否参与 AV 会议的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="2adcc-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="2adcc-147">例如，假设您的测试失败，并且您收到以下诊断：</span><span class="sxs-lookup"><span data-stu-id="2adcc-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="2adcc-148">ErrorCode = 1008，Source = accessproxy，Reason = 无法解析 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2adcc-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="2adcc-149">如果使用 Verbose 参数重新运行测试，则返回的分步信息将包含类似如下的输出：</span><span class="sxs-lookup"><span data-stu-id="2adcc-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="2adcc-150">详细： "注册" 活动已启动。</span><span class="sxs-lookup"><span data-stu-id="2adcc-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="2adcc-151">发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="2adcc-151">Sending Registration request:</span></span>

<span data-ttu-id="2adcc-152">目标 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2adcc-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2adcc-153">用户 Sip 地址 = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2adcc-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="2adcc-154">注册器端口 = 5061。</span><span class="sxs-lookup"><span data-stu-id="2adcc-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="2adcc-155">选择 "受信任" 的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="2adcc-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="2adcc-156">"注册" 活动已开始。</span><span class="sxs-lookup"><span data-stu-id="2adcc-156">'Register' activity started.</span></span>

<span data-ttu-id="2adcc-157">发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="2adcc-157">Sending Registration request:</span></span>

<span data-ttu-id="2adcc-158">目标 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2adcc-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2adcc-159">用户 Sip 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2adcc-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="2adcc-160">注册器端口 = 5061。</span><span class="sxs-lookup"><span data-stu-id="2adcc-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="2adcc-161">选择 "受信任" 的身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="2adcc-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="2adcc-162">"终结点无法注册" 异常。</span><span class="sxs-lookup"><span data-stu-id="2adcc-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="2adcc-163">有关具体原因，请参阅错误代码。</span><span class="sxs-lookup"><span data-stu-id="2adcc-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="2adcc-164">在工作流过程中发生</span><span class="sxs-lookup"><span data-stu-id="2adcc-164">occurred during Workflow</span></span>

<span data-ttu-id="2adcc-165">该输出中的最后一行指示用户 sip:kenmyer@litwareinc.com 无法注册 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="2adcc-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="2adcc-166">这意味着，您应验证 SIP 地址 sip:kenmyer@litwareinc.com 是否有效，以及是否为 Lync Server 启用了关联的用户。</span><span class="sxs-lookup"><span data-stu-id="2adcc-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2adcc-167">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="2adcc-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="2adcc-168">以下是测试 CsAVConference 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="2adcc-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="2adcc-169">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="2adcc-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="2adcc-170">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="2adcc-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2adcc-171">用户帐户有效，但当前未对 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="2adcc-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2adcc-172">若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="2adcc-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2adcc-173">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="2adcc-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

