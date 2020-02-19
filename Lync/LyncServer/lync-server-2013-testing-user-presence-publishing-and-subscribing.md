---
title: Lync Server 2013：测试用户状态发布和订阅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="325c7-102">在 Lync Server 2013 中测试用户状态发布和订阅</span><span class="sxs-lookup"><span data-stu-id="325c7-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="325c7-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="325c7-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="325c7-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="325c7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="325c7-105">每天</span><span class="sxs-lookup"><span data-stu-id="325c7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="325c7-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="325c7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="325c7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="325c7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="325c7-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="325c7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="325c7-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="325c7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="325c7-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsPresence cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="325c7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="325c7-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="325c7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="325c7-112">说明</span><span class="sxs-lookup"><span data-stu-id="325c7-112">Description</span></span>

<span data-ttu-id="325c7-113">CsPresence 用于确定一对测试用户是否可以登录 Lync Server，然后交换状态信息。</span><span class="sxs-lookup"><span data-stu-id="325c7-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="325c7-114">为此，此 cmdlet 首先使这两个用户登录系统。</span><span class="sxs-lookup"><span data-stu-id="325c7-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="325c7-115">如果登录成功，第一个测试用户随后将要求从第二个用户接收状态信息。</span><span class="sxs-lookup"><span data-stu-id="325c7-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="325c7-116">第二个用户发布此信息，然后 Test-CsPresence 验证是否信息是否已成功传输到第一个用户。</span><span class="sxs-lookup"><span data-stu-id="325c7-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="325c7-117">在交换状态信息后，这两个测试用户就会从 Lync Server 注销。</span><span class="sxs-lookup"><span data-stu-id="325c7-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="325c7-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="325c7-118">Running the test</span></span>

<span data-ttu-id="325c7-119">CsPresence cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="325c7-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="325c7-120">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="325c7-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="325c7-121">例如：</span><span class="sxs-lookup"><span data-stu-id="325c7-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="325c7-122">若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="325c7-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="325c7-123">在调用 CsPresence 时，必须包括这些凭据对象和两个帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="325c7-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="325c7-124">有关详细信息，请参阅[CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="325c7-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="325c7-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="325c7-125">Determining success or failure</span></span>

<span data-ttu-id="325c7-126">如果指定用户可以交换状态信息，则会收到类似于以下内容的输出，并将 Result 属性标记为 "**成功"：**</span><span class="sxs-lookup"><span data-stu-id="325c7-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="325c7-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="325c7-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="325c7-128">结果：成功</span><span class="sxs-lookup"><span data-stu-id="325c7-128">Result : Success</span></span>

<span data-ttu-id="325c7-129">延迟：00：00：06.3280315</span><span class="sxs-lookup"><span data-stu-id="325c7-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="325c7-130">误差</span><span class="sxs-lookup"><span data-stu-id="325c7-130">Error :</span></span>

<span data-ttu-id="325c7-131">诊断</span><span class="sxs-lookup"><span data-stu-id="325c7-131">Diagnosis :</span></span>

<span data-ttu-id="325c7-132">如果两个用户不能交换状态信息，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="325c7-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="325c7-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="325c7-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="325c7-134">结果：失败</span><span class="sxs-lookup"><span data-stu-id="325c7-134">Result : Failure</span></span>

<span data-ttu-id="325c7-135">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="325c7-135">Latency : 00:00:00</span></span>

<span data-ttu-id="325c7-136">错误：未找到404</span><span class="sxs-lookup"><span data-stu-id="325c7-136">Error : 404, Not Found</span></span>

<span data-ttu-id="325c7-137">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="325c7-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="325c7-138">原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="325c7-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="325c7-139">尚.</span><span class="sxs-lookup"><span data-stu-id="325c7-139">exist.</span></span>

<span data-ttu-id="325c7-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="325c7-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="325c7-141">例如，由于至少有两个用户帐户中的一个无效，因此以前的输出表明测试失败：该帐户不存在，或者尚未为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="325c7-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="325c7-142">您可以通过运行与以下内容类似的命令来验证帐户是否存在，并确定是否为 Lync Server 启用了这些帐户：</span><span class="sxs-lookup"><span data-stu-id="325c7-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="325c7-143">如果 CsPresence 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="325c7-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="325c7-144">包含 Verbose 参数时，CsPresence 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="325c7-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="325c7-145">例如：</span><span class="sxs-lookup"><span data-stu-id="325c7-145">For example:</span></span>

<span data-ttu-id="325c7-146">注册请求命中未知</span><span class="sxs-lookup"><span data-stu-id="325c7-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="325c7-147">"Register" 活动在 "0.0345791" 秒内完成。</span><span class="sxs-lookup"><span data-stu-id="325c7-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="325c7-148">"SelfSubscribeActivity" 活动已启动。</span><span class="sxs-lookup"><span data-stu-id="325c7-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="325c7-149">"SelfSubscribeActivity" 活动在 "0.0041174" 秒内完成。</span><span class="sxs-lookup"><span data-stu-id="325c7-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="325c7-150">"SubscribePresence" 活动已启动。</span><span class="sxs-lookup"><span data-stu-id="325c7-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="325c7-151">"SubscribePresence" 活动在 "0.0038764" 秒内完成。</span><span class="sxs-lookup"><span data-stu-id="325c7-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="325c7-152">"PublishPresence" 活动已启动。</span><span class="sxs-lookup"><span data-stu-id="325c7-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="325c7-153">在25秒内未收到异常 "状态通知"。</span><span class="sxs-lookup"><span data-stu-id="325c7-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="325c7-154">ruing 工作流 STPresenceWorkflow 执行发生。</span><span class="sxs-lookup"><span data-stu-id="325c7-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="325c7-155">在25秒内未收到状态通知这一事实可能表示网络问题阻止交换信息。</span><span class="sxs-lookup"><span data-stu-id="325c7-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="325c7-156">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="325c7-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="325c7-157">以下是测试 CsPresence 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="325c7-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="325c7-158">您指定了不正确的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="325c7-158">You specified an incorrect user account.</span></span> <span data-ttu-id="325c7-159">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="325c7-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="325c7-160">用户帐户有效，但当前未对 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="325c7-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="325c7-161">若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="325c7-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="325c7-162">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="325c7-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

