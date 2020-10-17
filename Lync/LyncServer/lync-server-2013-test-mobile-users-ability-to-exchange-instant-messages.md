---
title: Lync Server 2013：测试移动用户对 exchange 即时消息的能力
description: Lync Server 2013：测试移动用户对 exchange 即时消息的功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558288"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="05c65-103">测试移动用户在 Lync Server 2013 中 exchange 即时消息的功能</span><span class="sxs-lookup"><span data-stu-id="05c65-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05c65-104">_**上次修改的主题：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="05c65-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05c65-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="05c65-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="05c65-106">每月</span><span class="sxs-lookup"><span data-stu-id="05c65-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05c65-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="05c65-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="05c65-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05c65-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05c65-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="05c65-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="05c65-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="05c65-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="05c65-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsMcxP2PIM cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="05c65-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="05c65-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="05c65-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="05c65-113">说明</span><span class="sxs-lookup"><span data-stu-id="05c65-113">Description</span></span>

<span data-ttu-id="05c65-114">移动服务使移动设备用户可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05c65-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="05c65-115">Exchange 即时消息和状态信息。</span><span class="sxs-lookup"><span data-stu-id="05c65-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="05c65-116">在内部存储和检索语音邮件，而不是使用其无线提供商。</span><span class="sxs-lookup"><span data-stu-id="05c65-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="05c65-117">利用 Lync Server 功能，例如通过工作和拨出式会议进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="05c65-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="05c65-118">Test-CsMxcP2PIM cmdlet 提供了一种快速而简单的方法来验证用户是否可以使用移动服务来交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="05c65-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="05c65-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="05c65-119">Running the test</span></span>

<span data-ttu-id="05c65-120">若要运行此测试，必须为每个帐户 (包含帐户名称和密码) 的对象创建两个 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="05c65-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="05c65-121">在调用 Test-csmcxp2pim 时，必须包括这些凭据对象和两个帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="05c65-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="05c65-122">有关详细信息，请参阅 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="05c65-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="05c65-123">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="05c65-123">Determining success or failure</span></span>

<span data-ttu-id="05c65-124">如果两个测试用户可以通过使用移动服务来交换即时消息，Test-CsMcxP2PIM 将返回测试结果是否成功：</span><span class="sxs-lookup"><span data-stu-id="05c65-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="05c65-125">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="05c65-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="05c65-126">目标 Uri： http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="05c65-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="05c65-127">结果：成功</span><span class="sxs-lookup"><span data-stu-id="05c65-127">Result : Success</span></span>

<span data-ttu-id="05c65-128">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="05c65-128">Latency : 00:00:00</span></span>

<span data-ttu-id="05c65-129">错误消息：</span><span class="sxs-lookup"><span data-stu-id="05c65-129">Error Message :</span></span>

<span data-ttu-id="05c65-130">诊断</span><span class="sxs-lookup"><span data-stu-id="05c65-130">Diagnosis :</span></span>

<span data-ttu-id="05c65-131">如果测试失败，则结果将设置为 "失败"，并将显示详细的错误消息和诊断：</span><span class="sxs-lookup"><span data-stu-id="05c65-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="05c65-132">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="05c65-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="05c65-133">目标 Uri： https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="05c65-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="05c65-134">结果：失败</span><span class="sxs-lookup"><span data-stu-id="05c65-134">Result : Failure</span></span>

<span data-ttu-id="05c65-135">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="05c65-135">Latency : 00:00:00</span></span>

<span data-ttu-id="05c65-136">错误消息：未收到 Web-Ticket 服务的响应。</span><span class="sxs-lookup"><span data-stu-id="05c65-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="05c65-137">内部异常：未授权的 HHTP 请求</span><span class="sxs-lookup"><span data-stu-id="05c65-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="05c65-138">客户端协商方案 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="05c65-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="05c65-139">的身份验证</span><span class="sxs-lookup"><span data-stu-id="05c65-139">The authentication</span></span>

<span data-ttu-id="05c65-140">从服务器接收到的标头是 "协商，NTLM"。</span><span class="sxs-lookup"><span data-stu-id="05c65-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="05c65-141">内部异常：远程服务器返回错误：</span><span class="sxs-lookup"><span data-stu-id="05c65-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="05c65-142"> (401) 未经授权。</span><span class="sxs-lookup"><span data-stu-id="05c65-142">(401) Unauthorized.</span></span>

<span data-ttu-id="05c65-143">诊断</span><span class="sxs-lookup"><span data-stu-id="05c65-143">Diagnosis :</span></span>

<span data-ttu-id="05c65-144">内部诊断： X-MS-Fqdb： atl-cs-</span><span class="sxs-lookup"><span data-stu-id="05c65-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="05c65-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="05c65-145">001.litwareinc.com</span></span>

<span data-ttu-id="05c65-146">Cache-Control： private</span><span class="sxs-lookup"><span data-stu-id="05c65-146">Cache-Control : private</span></span>

<span data-ttu-id="05c65-147">Content-Type： text/html;字符集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="05c65-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="05c65-148">服务器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="05c65-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="05c65-149">WWW-Authenticate： Negotiate、NTLM</span><span class="sxs-lookup"><span data-stu-id="05c65-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="05c65-150">X-电源： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="05c65-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="05c65-151">X-内容类型-选项： nosniff</span><span class="sxs-lookup"><span data-stu-id="05c65-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="05c65-152">日期：周三，28年5月 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="05c65-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="05c65-153">Content-长度：6305</span><span class="sxs-lookup"><span data-stu-id="05c65-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="05c65-154">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="05c65-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="05c65-155">如果 Test-CsMcxP2PIM 失败第一步应是验证移动服务是否已启动并在运行。</span><span class="sxs-lookup"><span data-stu-id="05c65-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="05c65-156">可通过使用 web 浏览器来验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="05c65-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="05c65-157">例如，以下命令将验证池 atl-cs-001.litwareinc.com 的 URL：</span><span class="sxs-lookup"><span data-stu-id="05c65-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="05c65-158">如果移动服务似乎正在运行，请验证您的两个测试用户是否具有有效的 Lync Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="05c65-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="05c65-159">您可以使用与以下内容类似的命令检索帐户信息：</span><span class="sxs-lookup"><span data-stu-id="05c65-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="05c65-160">如果 Enabled 属性不等于 True，或者如果命令失败，则表示用户没有有效的 Lync Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="05c65-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="05c65-161">此外，还应验证用户是否已启用移动功能。</span><span class="sxs-lookup"><span data-stu-id="05c65-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="05c65-162">若要执行此操作，请首先确定分配给该帐户的移动策略：</span><span class="sxs-lookup"><span data-stu-id="05c65-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="05c65-163">了解策略名称后，请使用 Get-CsMobilityPolicy cmdlet 确认相关策略 (例如，RedmondMobilityPolicy) 的 EnableMobility 属性设置为 True：</span><span class="sxs-lookup"><span data-stu-id="05c65-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="05c65-164">如果收到包含身份验证标头的错误消息，则通常意味着您未指定有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="05c65-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="05c65-165">请验证用户名和密码，然后再次尝试测试。</span><span class="sxs-lookup"><span data-stu-id="05c65-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="05c65-166">如果确信用户帐户有效，则使用 Get-CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。</span><span class="sxs-lookup"><span data-stu-id="05c65-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="05c65-167">这将告诉你在组织中启用了哪些身份验证方法。有关如何对移动服务进行故障排除的更多提示，请参阅博客文章 [故障排除外部 Lync 移动连接问题](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)分步。</span><span class="sxs-lookup"><span data-stu-id="05c65-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

