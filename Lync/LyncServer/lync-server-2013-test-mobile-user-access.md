---
title: Lync Server 2013：测试移动用户访问
description: Lync Server 2013：测试移动用户访问。
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
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541868"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="c38c9-103">在 Lync Server 2013 中测试移动用户访问权限</span><span class="sxs-lookup"><span data-stu-id="c38c9-103">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c38c9-104">_**上次修改的主题：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="c38c9-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c38c9-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="c38c9-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c38c9-106">每月</span><span class="sxs-lookup"><span data-stu-id="c38c9-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c38c9-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="c38c9-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c38c9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c38c9-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c38c9-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="c38c9-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c38c9-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="c38c9-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c38c9-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsMcxConference cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c38c9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="c38c9-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c38c9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c38c9-113">说明</span><span class="sxs-lookup"><span data-stu-id="c38c9-113">Description</span></span>

<span data-ttu-id="c38c9-114">移动服务使移动设备用户可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c38c9-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="c38c9-115">Exchange 即时消息和状态信息。</span><span class="sxs-lookup"><span data-stu-id="c38c9-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="c38c9-116">在内部存储和检索语音邮件，而不是使用其无线提供商。</span><span class="sxs-lookup"><span data-stu-id="c38c9-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="c38c9-117">利用 Lync Server 功能，例如通过工作和拨出式会议进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="c38c9-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="c38c9-118">Test-CsMcxConference cmdlet 提供了一种快速而简单的方法来验证用户是否可以使用移动设备加入和参与 Lync Server 会议。</span><span class="sxs-lookup"><span data-stu-id="c38c9-118">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c38c9-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="c38c9-119">Running the test</span></span>

<span data-ttu-id="c38c9-120">若要运行此检查，必须为每个帐户 (包含帐户名称和密码) 的对象创建三个 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="c38c9-120">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="c38c9-121">接下来，您必须在调用 Test-CsMcxConference 时包含这些凭据对象和 SIP 地址，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c38c9-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="c38c9-122">有关详细信息，请参阅 [CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c38c9-122">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c38c9-123">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="c38c9-123">Determining success or failure</span></span>

<span data-ttu-id="c38c9-124">如果检查成功，Test-CsMcxConference 将报告成功的测试结果：</span><span class="sxs-lookup"><span data-stu-id="c38c9-124">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="c38c9-125">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c38c9-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c38c9-126">目标 Uri： http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="c38c9-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="c38c9-127">结果：成功</span><span class="sxs-lookup"><span data-stu-id="c38c9-127">Result : Success</span></span>

<span data-ttu-id="c38c9-128">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="c38c9-128">Latency : 00:00:00</span></span>

<span data-ttu-id="c38c9-129">错误消息：</span><span class="sxs-lookup"><span data-stu-id="c38c9-129">Error Message :</span></span>

<span data-ttu-id="c38c9-130">诊断</span><span class="sxs-lookup"><span data-stu-id="c38c9-130">Diagnosis :</span></span>

<span data-ttu-id="c38c9-131">如果检查不成功 Test-CsMcxConference 将报告失败的测试结果。</span><span class="sxs-lookup"><span data-stu-id="c38c9-131">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="c38c9-132">此测试结果通常附带详细的错误消息和诊断。</span><span class="sxs-lookup"><span data-stu-id="c38c9-132">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="c38c9-133">例如：</span><span class="sxs-lookup"><span data-stu-id="c38c9-133">For example:</span></span>

<span data-ttu-id="c38c9-134">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c38c9-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c38c9-135">目标 Uri： https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="c38c9-135">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="c38c9-136">结果：失败</span><span class="sxs-lookup"><span data-stu-id="c38c9-136">Result : Failure</span></span>

<span data-ttu-id="c38c9-137">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="c38c9-137">Latency : 00:00:00</span></span>

<span data-ttu-id="c38c9-138">错误消息：未收到 Web-Ticket 服务的响应。</span><span class="sxs-lookup"><span data-stu-id="c38c9-138">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="c38c9-139">内部异常： HHTP 请求未通过客户端授权</span><span class="sxs-lookup"><span data-stu-id="c38c9-139">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="c38c9-140">协商方案 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="c38c9-140">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="c38c9-141">收到的身份验证标头</span><span class="sxs-lookup"><span data-stu-id="c38c9-141">The authentication header received</span></span>

<span data-ttu-id="c38c9-142">来自服务器 "协商"。</span><span class="sxs-lookup"><span data-stu-id="c38c9-142">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="c38c9-143">内部异常：远程服务器返回错误： (401) </span><span class="sxs-lookup"><span data-stu-id="c38c9-143">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="c38c9-144">受到.</span><span class="sxs-lookup"><span data-stu-id="c38c9-144">Unauthorized.</span></span>

<span data-ttu-id="c38c9-145">诊断</span><span class="sxs-lookup"><span data-stu-id="c38c9-145">Diagnosis :</span></span>

<span data-ttu-id="c38c9-146">内部诊断： X-MS-服务器-Fqdb： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c38c9-146">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c38c9-147">Cache-Control： private</span><span class="sxs-lookup"><span data-stu-id="c38c9-147">Cache-Control : private</span></span>

<span data-ttu-id="c38c9-148">Content-Type： text/html;字符集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="c38c9-148">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="c38c9-149">服务器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="c38c9-149">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="c38c9-150">WWW-Authenticate： Negotiate、NTLM</span><span class="sxs-lookup"><span data-stu-id="c38c9-150">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="c38c9-151">X-电源： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c38c9-151">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="c38c9-152">X-内容类型-选项： nosniff</span><span class="sxs-lookup"><span data-stu-id="c38c9-152">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="c38c9-153">日期：周三，28年5月 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="c38c9-153">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="c38c9-154">Content-长度：6305</span><span class="sxs-lookup"><span data-stu-id="c38c9-154">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c38c9-155">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="c38c9-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="c38c9-156">如果 Test-CsMcxConference 失败，应首先验证移动服务是否正在运行且可以访问。</span><span class="sxs-lookup"><span data-stu-id="c38c9-156">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="c38c9-157">可通过使用 web 浏览器来验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c38c9-157">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="c38c9-158">例如，以下命令将验证池 atl-cs-001.litwareinc.com 的 URL：</span><span class="sxs-lookup"><span data-stu-id="c38c9-158">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="c38c9-159">如果可以访问移动服务，则应验证测试用户是否具有有效的 Lync Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="c38c9-159">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="c38c9-160">您可以使用与以下内容类似的命令检索帐户信息：</span><span class="sxs-lookup"><span data-stu-id="c38c9-160">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="c38c9-161">如果 Enabled 属性不等于 True，或者如果命令失败，则表示用户没有有效的 Lync Server 帐户。此外，还应验证每个用户帐户是否已启用移动性。</span><span class="sxs-lookup"><span data-stu-id="c38c9-161">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="c38c9-162">若要执行此操作，请首先确定分配给该帐户的移动策略：</span><span class="sxs-lookup"><span data-stu-id="c38c9-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="c38c9-163">了解策略名称后，请使用 Get-CsMobilityPolicy cmdlet 确认相关策略 (例如，RedmondMobilityPolicy) 的 EnableMobility 属性设置为 True：</span><span class="sxs-lookup"><span data-stu-id="c38c9-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="c38c9-164">如果您在运行 Test-CsMcxConference 通常意味着您未指定有效的用户帐户时收到 "身份验证标头" 错误消息，请验证用户名和密码，然后再次尝试测试。</span><span class="sxs-lookup"><span data-stu-id="c38c9-164">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="c38c9-165">如果确信用户帐户有效，则使用 Get-CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。</span><span class="sxs-lookup"><span data-stu-id="c38c9-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="c38c9-166">这将告诉你在组织中启用了哪些身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="c38c9-166">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="c38c9-167">有关如何对移动服务进行故障排除的更多提示，请参阅博客文章 [故障排除外部 Lync 移动连接问题](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)分步。</span><span class="sxs-lookup"><span data-stu-id="c38c9-167">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

