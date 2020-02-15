---
title: Lync Server 2013：测试位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a46eecb63ed35075cb44ff840e733f781357ea6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="3f308-102">在 Lync Server 2013 中测试位置策略</span><span class="sxs-lookup"><span data-stu-id="3f308-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f308-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3f308-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f308-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="3f308-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3f308-105">每天</span><span class="sxs-lookup"><span data-stu-id="3f308-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f308-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="3f308-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3f308-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f308-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f308-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="3f308-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3f308-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="3f308-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3f308-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 New-cslocationpolicy cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="3f308-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="3f308-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3f308-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3f308-112">说明</span><span class="sxs-lookup"><span data-stu-id="3f308-112">Description</span></span>

<span data-ttu-id="3f308-113">New-cslocationpolicy cmdlet 验证是否已将位置策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="3f308-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="3f308-114">可以使用位置策略来应用与 E9-1-1 功能和客户端位置相关的设置。</span><span class="sxs-lookup"><span data-stu-id="3f308-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="3f308-115">位置策略确定是否为用户启用 E9-1-1，如果答案是 "是"，则是紧急呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="3f308-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="3f308-116">例如，可以使用位置策略定义发生紧急呼叫的号码（美国的911）、企业安全是否应自动通知以及应如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="3f308-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="3f308-117">可以测试用户或网络子网的位置策略。</span><span class="sxs-lookup"><span data-stu-id="3f308-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="3f308-118">如果通过指定 Subnet 参数的值对子网运行测试，则 cmdlet 将尝试解析该子网的位置策略。</span><span class="sxs-lookup"><span data-stu-id="3f308-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="3f308-119">如果没有位置策略分配到子网，则将检索配置用户的位置策略。</span><span class="sxs-lookup"><span data-stu-id="3f308-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="3f308-120">如果成功检索子网策略，则输出将包含以子网-tagid 开头的 LocationPolicyTagID 值。</span><span class="sxs-lookup"><span data-stu-id="3f308-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="3f308-121">如果未找到子网的位置策略，则 LocationPolicyTagID 将以 user-tagid 开头。</span><span class="sxs-lookup"><span data-stu-id="3f308-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3f308-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="3f308-122">Running the test</span></span>

<span data-ttu-id="3f308-123">可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行 New-cslocationpolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3f308-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="3f308-124">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="3f308-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3f308-125">例如：</span><span class="sxs-lookup"><span data-stu-id="3f308-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3f308-126">若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="3f308-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="3f308-127">然后，您必须在调用 New-cslocationpolicy 时包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="3f308-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="3f308-128">有关详细信息，请参阅[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="3f308-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3f308-129">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="3f308-129">Determining success or failure</span></span>

<span data-ttu-id="3f308-130">如果指定用户具有有效的位置策略，则将接收与以下内容类似的输出，并将 Result 属性标记为 "**成功"：**</span><span class="sxs-lookup"><span data-stu-id="3f308-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3f308-131">EnhancedEmergencyServicesEnabled： true</span><span class="sxs-lookup"><span data-stu-id="3f308-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="3f308-132">LocationPolicyTagID：用户-tagid</span><span class="sxs-lookup"><span data-stu-id="3f308-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="3f308-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3f308-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3f308-134">结果：成功</span><span class="sxs-lookup"><span data-stu-id="3f308-134">Result : Success</span></span>

<span data-ttu-id="3f308-135">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="3f308-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="3f308-136">误差</span><span class="sxs-lookup"><span data-stu-id="3f308-136">Error :</span></span>

<span data-ttu-id="3f308-137">诊断</span><span class="sxs-lookup"><span data-stu-id="3f308-137">Diagnosis :</span></span>

<span data-ttu-id="3f308-138">如果找不到指定用户的有效位置策略，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="3f308-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3f308-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3f308-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3f308-140">结果：失败</span><span class="sxs-lookup"><span data-stu-id="3f308-140">Result : Failure</span></span>

<span data-ttu-id="3f308-141">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="3f308-141">Latency : 00:00:00</span></span>

<span data-ttu-id="3f308-142">错误：未找到404</span><span class="sxs-lookup"><span data-stu-id="3f308-142">Error : 404, Not Found</span></span>

<span data-ttu-id="3f308-143">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="3f308-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="3f308-144">原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="3f308-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="3f308-145">尚.</span><span class="sxs-lookup"><span data-stu-id="3f308-145">exist.</span></span>

<span data-ttu-id="3f308-146">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="3f308-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3f308-147">以前的输出表明由于指定用户无效而导致测试失败：该帐户不存在，或者尚未为 Lync Server 启用该用户。</span><span class="sxs-lookup"><span data-stu-id="3f308-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="3f308-148">您可以通过运行与以下类似的命令来验证帐户的有效性，并确定是否已为 nm-第 14-第14级启用该帐户：</span><span class="sxs-lookup"><span data-stu-id="3f308-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="3f308-149">如果 New-cslocationpolicy 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="3f308-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="3f308-150">包含 Verbose 参数时，New-cslocationpolicy 将返回它在验证位置策略时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="3f308-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="3f308-151">例如，此输出指示 Lync Server 无法登录测试用户，可能是因为提供了无效密码：</span><span class="sxs-lookup"><span data-stu-id="3f308-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="3f308-152">发送注册请求：</span><span class="sxs-lookup"><span data-stu-id="3f308-152">Sending Registration request :</span></span>

<span data-ttu-id="3f308-153">目标 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3f308-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="3f308-154">用户 Sip 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3f308-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="3f308-155">注册器端口 = 5061</span><span class="sxs-lookup"><span data-stu-id="3f308-155">Registrar Port = 5061</span></span>

<span data-ttu-id="3f308-156">已选择身份验证类型 "IWA"。</span><span class="sxs-lookup"><span data-stu-id="3f308-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="3f308-157">针对 sip/atl-001-litwareinc 的注册命中率</span><span class="sxs-lookup"><span data-stu-id="3f308-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3f308-158">"Register" 活动在 "0.0601795" 秒内完成。</span><span class="sxs-lookup"><span data-stu-id="3f308-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="3f308-159">"登录被拒绝" 异常。</span><span class="sxs-lookup"><span data-stu-id="3f308-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="3f308-160">检查是否正在使用正确的凭据，以及帐户是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3f308-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="3f308-161">在工作流过程中发生。</span><span class="sxs-lookup"><span data-stu-id="3f308-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3f308-162">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="3f308-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="3f308-163">以下是测试 New-cslocationpolicy 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="3f308-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="3f308-164">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="3f308-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="3f308-165">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="3f308-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3f308-166">用户帐户有效，但当前未对 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="3f308-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3f308-167">若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="3f308-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="3f308-168">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="3f308-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

