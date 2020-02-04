---
title: Lync Server 2013：测试移动用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 628fd3aae4f66316627176c3af025eb63202bafb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="21741-102">在 Lync Server 2013 中测试移动用户访问权限</span><span class="sxs-lookup"><span data-stu-id="21741-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21741-103">_**主题上次修改时间：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="21741-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21741-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="21741-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="21741-105">每月</span><span class="sxs-lookup"><span data-stu-id="21741-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21741-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="21741-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="21741-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21741-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21741-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="21741-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="21741-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="21741-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="21741-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsMcxConference cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="21741-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="21741-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="21741-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="21741-112">说明</span><span class="sxs-lookup"><span data-stu-id="21741-112">Description</span></span>

<span data-ttu-id="21741-113">移动服务使移动设备用户可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="21741-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="21741-114">Exchange 即时消息和状态信息。</span><span class="sxs-lookup"><span data-stu-id="21741-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="21741-115">在内部存储和检索语音邮件，而不是无线提供商。</span><span class="sxs-lookup"><span data-stu-id="21741-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="21741-116">利用 Lync 服务器功能，例如通过工作电话和拨出式会议进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="21741-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="21741-117">CsMcxConference cmdlet 提供一种快速简便的方式来验证用户是否可以使用移动设备加入和参与 Lync Server 会议。</span><span class="sxs-lookup"><span data-stu-id="21741-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="21741-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="21741-118">Running the test</span></span>

<span data-ttu-id="21741-119">若要运行此检查，必须为每个帐户创建三个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="21741-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="21741-120">然后，当你调用 Test CsMcxConference 时，你必须包含这些凭据对象和两个帐户的 SIP 地址，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="21741-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="21741-121">有关详细信息，请参阅[CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="21741-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="21741-122">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="21741-122">Determining success or failure</span></span>

<span data-ttu-id="21741-123">如果检查成功，则测试 CsMcxConference 将报告成功的测试结果：</span><span class="sxs-lookup"><span data-stu-id="21741-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="21741-124">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="21741-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="21741-125">目标 Uri：http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="21741-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="21741-126">结果：成功</span><span class="sxs-lookup"><span data-stu-id="21741-126">Result : Success</span></span>

<span data-ttu-id="21741-127">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="21741-127">Latency : 00:00:00</span></span>

<span data-ttu-id="21741-128">错误消息：</span><span class="sxs-lookup"><span data-stu-id="21741-128">Error Message :</span></span>

<span data-ttu-id="21741-129">自检</span><span class="sxs-lookup"><span data-stu-id="21741-129">Diagnosis :</span></span>

<span data-ttu-id="21741-130">如果支票未成功测试，CsMcxConference 将报告失败的测试结果。</span><span class="sxs-lookup"><span data-stu-id="21741-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="21741-131">此测试结果通常附带详细的错误消息和诊断。</span><span class="sxs-lookup"><span data-stu-id="21741-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="21741-132">例如：</span><span class="sxs-lookup"><span data-stu-id="21741-132">For example:</span></span>

<span data-ttu-id="21741-133">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="21741-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="21741-134">目标 Uri：https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="21741-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="21741-135">结果：失败</span><span class="sxs-lookup"><span data-stu-id="21741-135">Result : Failure</span></span>

<span data-ttu-id="21741-136">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="21741-136">Latency : 00:00:00</span></span>

<span data-ttu-id="21741-137">错误消息：未收到 Web 票证服务的任何响应。</span><span class="sxs-lookup"><span data-stu-id="21741-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="21741-138">内部异常： HHTP 请求未通过客户端授权</span><span class="sxs-lookup"><span data-stu-id="21741-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="21741-139">协商方案 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="21741-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="21741-140">收到的身份验证标头</span><span class="sxs-lookup"><span data-stu-id="21741-140">The authentication header received</span></span>

<span data-ttu-id="21741-141">来自服务器的 "协商"。</span><span class="sxs-lookup"><span data-stu-id="21741-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="21741-142">内部异常：远程服务器返回错误：（401）</span><span class="sxs-lookup"><span data-stu-id="21741-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="21741-143">便.</span><span class="sxs-lookup"><span data-stu-id="21741-143">Unauthorized.</span></span>

<span data-ttu-id="21741-144">自检</span><span class="sxs-lookup"><span data-stu-id="21741-144">Diagnosis :</span></span>

<span data-ttu-id="21741-145">内部诊断： X 毫秒-服务器-Fqdb： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="21741-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="21741-146">缓存控制： private</span><span class="sxs-lookup"><span data-stu-id="21741-146">Cache-Control : private</span></span>

<span data-ttu-id="21741-147">内容类型：文本/html;字符集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="21741-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="21741-148">服务器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="21741-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="21741-149">WWW-身份验证：协商，NTLM</span><span class="sxs-lookup"><span data-stu-id="21741-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="21741-150">X-通过： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="21741-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="21741-151">X-内容类型-选项： nosniff</span><span class="sxs-lookup"><span data-stu-id="21741-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="21741-152">日期：星期三，28五月 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="21741-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="21741-153">内容长度：6305</span><span class="sxs-lookup"><span data-stu-id="21741-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="21741-154">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="21741-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="21741-155">如果测试 CsMcxConference 失败，应首先验证移动服务是否正在运行且可访问。</span><span class="sxs-lookup"><span data-stu-id="21741-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="21741-156">可通过使用 web 浏览器验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="21741-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="21741-157">例如，此命令将验证 pool atl-cs-001.litwareinc.com 的 URL：</span><span class="sxs-lookup"><span data-stu-id="21741-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="21741-158">如果可以访问移动服务，则应验证测试用户是否具有有效的 Lync 服务器帐户。</span><span class="sxs-lookup"><span data-stu-id="21741-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="21741-159">你可以使用类似下面的命令检索帐户信息：</span><span class="sxs-lookup"><span data-stu-id="21741-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="21741-160">如果 Enabled 属性不等于 True 或命令失败，则意味着用户没有有效的 Lync 服务器帐户。你还应验证每个用户帐户是否已启用移动。</span><span class="sxs-lookup"><span data-stu-id="21741-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="21741-161">若要执行此操作，请首先确定分配给该帐户的移动策略：</span><span class="sxs-lookup"><span data-stu-id="21741-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="21741-162">知道策略名称后，请使用 CsMobilityPolicy cmdlet 验证有问题的策略（例如，RedmondMobilityPolicy）是否将 EnableMobility 属性设置为 True：</span><span class="sxs-lookup"><span data-stu-id="21741-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="21741-163">如果你在运行测试 CsMcxConference 时收到 "身份验证头" 错误消息，这通常意味着你未指定有效的用户帐户，请验证用户名和密码，然后再次尝试测试。</span><span class="sxs-lookup"><span data-stu-id="21741-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="21741-164">如果您确信用户帐户有效，请使用 CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。</span><span class="sxs-lookup"><span data-stu-id="21741-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="21741-165">这将告诉你在你的组织中启用了哪些身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="21741-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="21741-166">有关如何解决移动服务问题的更多提示，请参阅分步[解决外部 Lync 移动性连接问题](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)的博客文章。</span><span class="sxs-lookup"><span data-stu-id="21741-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

