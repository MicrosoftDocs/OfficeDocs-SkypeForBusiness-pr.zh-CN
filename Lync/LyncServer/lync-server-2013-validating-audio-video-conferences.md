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
ms.openlocfilehash: 89bb8f38ea650bf64179b917b227d7ccaaf10791
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="1e742-102">在 Lync Server 2013 中验证音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="1e742-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e742-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1e742-103">_**Topic Last Modified:** 2014-06-05_</span></span>


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
<td><p><span data-ttu-id="1e742-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="1e742-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1e742-105">每天</span><span class="sxs-lookup"><span data-stu-id="1e742-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e742-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="1e742-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1e742-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e742-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e742-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="1e742-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1e742-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="1e742-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1e742-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsAVConference cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="1e742-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="1e742-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1e742-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1e742-112">说明</span><span class="sxs-lookup"><span data-stu-id="1e742-112">Description</span></span>

<span data-ttu-id="1e742-113">CsAVConference cmdlet 检查两个测试用户是否可以参与音频/视频（A/V）会议。</span><span class="sxs-lookup"><span data-stu-id="1e742-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="1e742-114">当 cmdlet 运行时，两个用户登录到系统。</span><span class="sxs-lookup"><span data-stu-id="1e742-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="1e742-115">成功登录后，第一个用户将创建一个/V 会议，然后等待第二位用户加入该会议。</span><span class="sxs-lookup"><span data-stu-id="1e742-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="1e742-116">在数据的简短交换后，会议将被删除，并且两个测试用户已注销。</span><span class="sxs-lookup"><span data-stu-id="1e742-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="1e742-117">请注意，CsAVConference 不会在两个测试用户之间进行实际的 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="1e742-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="1e742-118">相反，cmdlet 将验证两个用户是否可以建立执行此类会议所需的所有连接。</span><span class="sxs-lookup"><span data-stu-id="1e742-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="1e742-119">可在[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)中找到此命令的更多示例。</span><span class="sxs-lookup"><span data-stu-id="1e742-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1e742-120">运行测试</span><span class="sxs-lookup"><span data-stu-id="1e742-120">Running the test</span></span>

<span data-ttu-id="1e742-121">CsAVConference cmdlet 可以使用一对预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何两个用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="1e742-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="1e742-122">若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1e742-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="1e742-123">例如：</span><span class="sxs-lookup"><span data-stu-id="1e742-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="1e742-124">若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="1e742-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="1e742-125">然后，在调用 Test-CsAVConference 时，必须包含两个帐户的凭据对象和 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="1e742-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="1e742-126">有关详细信息，请参阅[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="1e742-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1e742-127">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="1e742-127">Determining Success or Failure</span></span>

<span data-ttu-id="1e742-128">如果指定用户可以成功完成 A/V 会议，你将收到类似于此的输出，结果属性标记为 "成功" **：**</span><span class="sxs-lookup"><span data-stu-id="1e742-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1e742-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e742-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1e742-130">结果：成功</span><span class="sxs-lookup"><span data-stu-id="1e742-130">Result : Success</span></span>

<span data-ttu-id="1e742-131">延迟：00：00：02.6841765</span><span class="sxs-lookup"><span data-stu-id="1e742-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="1e742-132">时发生</span><span class="sxs-lookup"><span data-stu-id="1e742-132">Error :</span></span>

<span data-ttu-id="1e742-133">自检</span><span class="sxs-lookup"><span data-stu-id="1e742-133">Diagnosis :</span></span>

<span data-ttu-id="1e742-134">如果用户无法完成会议，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="1e742-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1e742-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e742-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1e742-136">结果：失败</span><span class="sxs-lookup"><span data-stu-id="1e742-136">Result : Failure</span></span>

<span data-ttu-id="1e742-137">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="1e742-137">Latency : 00:00:00</span></span>

<span data-ttu-id="1e742-138">错误：404，未找到</span><span class="sxs-lookup"><span data-stu-id="1e742-138">Error : 404, Not Found</span></span>

<span data-ttu-id="1e742-139">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="1e742-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="1e742-140">原因 = 没有为 SIP 启用目标 URI，或者没有为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="1e742-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="1e742-141">并存.</span><span class="sxs-lookup"><span data-stu-id="1e742-141">exist.</span></span>

<span data-ttu-id="1e742-142">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="1e742-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="1e742-143">例如，以前的输出表明由于帐户不存在或者帐户尚未为 Lync Server 启用，导致测试失败的原因是两个用户帐户中的至少一个帐户无效。</span><span class="sxs-lookup"><span data-stu-id="1e742-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="1e742-144">你可以通过运行类似如下所示的命令来验证两个测试帐户是否存在，以及是否为 Lync Server 启用了这些帐户：</span><span class="sxs-lookup"><span data-stu-id="1e742-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="1e742-145">如果 CsAVConference 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="1e742-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="1e742-146">当包含 Verbose 参数时，CsAVConference 将返回在检查指定用户是否参与 AV 会议的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="1e742-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="1e742-147">例如，假设测试失败并收到以下诊断：</span><span class="sxs-lookup"><span data-stu-id="1e742-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="1e742-148">ErrorCode = 1008，Source = accessproxy，Reason = 无法解析 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="1e742-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="1e742-149">如果使用 Verbose 参数重新运行测试，返回的分步信息将包含类似以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="1e742-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="1e742-150">详细： "注册" 活动已开始。</span><span class="sxs-lookup"><span data-stu-id="1e742-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="1e742-151">正在发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="1e742-151">Sending Registration request:</span></span>

<span data-ttu-id="1e742-152">目标 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e742-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1e742-153">用户 Sip 地址 = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e742-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="1e742-154">注册机构端口 = 5061。</span><span class="sxs-lookup"><span data-stu-id="1e742-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="1e742-155">已选中 "受信任" 身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1e742-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="1e742-156">"注册" 活动已开始。</span><span class="sxs-lookup"><span data-stu-id="1e742-156">'Register' activity started.</span></span>

<span data-ttu-id="1e742-157">正在发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="1e742-157">Sending Registration request:</span></span>

<span data-ttu-id="1e742-158">目标 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e742-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1e742-159">用户 Sip 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1e742-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="1e742-160">注册机构端口 = 5061。</span><span class="sxs-lookup"><span data-stu-id="1e742-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="1e742-161">已选中 "受信任" 身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1e742-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="1e742-162">"终结点无法注册" 异常。</span><span class="sxs-lookup"><span data-stu-id="1e742-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="1e742-163">有关特定原因，请参阅错误代码。 '</span><span class="sxs-lookup"><span data-stu-id="1e742-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="1e742-164">工作流期间发生</span><span class="sxs-lookup"><span data-stu-id="1e742-164">occurred during Workflow</span></span>

<span data-ttu-id="1e742-165">该输出中的最后一行指示用户 sip:kenmyer@litwareinc.com 无法注册 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1e742-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="1e742-166">这意味着你应该验证 SIP 地址 sip:kenmyer@litwareinc.com 是否有效，以及是否为 Lync Server 启用关联的用户。</span><span class="sxs-lookup"><span data-stu-id="1e742-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1e742-167">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="1e742-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="1e742-168">下面是测试 CsAVConference 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="1e742-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="1e742-169">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="1e742-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="1e742-170">你可以通过运行类似如下所示的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="1e742-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1e742-171">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="1e742-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="1e742-172">若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="1e742-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="1e742-173">如果 Enabled 属性设置为 False，表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="1e742-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

