---
title: 'Lync Server 2013: 测试移动用户交换即时消息的能力'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="1468e-102">测试移动用户在 Lync Server 2013 中交换即时消息的能力</span><span class="sxs-lookup"><span data-stu-id="1468e-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1468e-103">_**主题上次修改时间:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="1468e-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1468e-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="1468e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1468e-105">每月</span><span class="sxs-lookup"><span data-stu-id="1468e-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1468e-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="1468e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1468e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1468e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1468e-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="1468e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1468e-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="1468e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1468e-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsMcxP2PIM cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="1468e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="1468e-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="1468e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1468e-112">说明</span><span class="sxs-lookup"><span data-stu-id="1468e-112">Description</span></span>

<span data-ttu-id="1468e-113">移动服务使移动设备用户可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1468e-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="1468e-114">Exchange 即时消息和状态信息。</span><span class="sxs-lookup"><span data-stu-id="1468e-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="1468e-115">在内部存储和检索语音邮件, 而不是无线提供商。</span><span class="sxs-lookup"><span data-stu-id="1468e-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="1468e-116">利用 Lync 服务器功能, 例如通过工作电话和拨出式会议进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="1468e-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="1468e-117">CsMxcP2PIM cmdlet 提供一种快速简便的方法来验证用户是否可以使用移动服务来交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="1468e-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1468e-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="1468e-118">Running the test</span></span>

<span data-ttu-id="1468e-119">若要运行此测试, 必须为每个帐户创建两个 Windows PowerShell 凭据对象 (包含帐户名和密码的对象)。</span><span class="sxs-lookup"><span data-stu-id="1468e-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="1468e-120">然后, 当你调用 Test-CsMcxP2PIM 时, 你必须包含这些凭据对象和两个帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="1468e-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="1468e-121">有关详细信息, 请参阅[CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1468e-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1468e-122">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="1468e-122">Determining success or failure</span></span>

<span data-ttu-id="1468e-123">如果两个测试用户可以使用移动服务来交换即时消息, 则 CsMcxP2PIM 将返回测试结果成功:</span><span class="sxs-lookup"><span data-stu-id="1468e-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="1468e-124">目标 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1468e-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1468e-125">目标 Uri:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="1468e-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="1468e-126">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="1468e-126">Result : Success</span></span>

<span data-ttu-id="1468e-127">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1468e-127">Latency : 00:00:00</span></span>

<span data-ttu-id="1468e-128">错误消息:</span><span class="sxs-lookup"><span data-stu-id="1468e-128">Error Message :</span></span>

<span data-ttu-id="1468e-129">自检</span><span class="sxs-lookup"><span data-stu-id="1468e-129">Diagnosis :</span></span>

<span data-ttu-id="1468e-130">如果测试失败, 则结果将设置为 "失败", 并且将显示详细的错误消息和诊断:</span><span class="sxs-lookup"><span data-stu-id="1468e-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="1468e-131">目标 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1468e-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1468e-132">目标 Uri:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="1468e-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="1468e-133">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="1468e-133">Result : Failure</span></span>

<span data-ttu-id="1468e-134">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="1468e-134">Latency : 00:00:00</span></span>

<span data-ttu-id="1468e-135">错误消息: 未收到 Web 票证服务的任何响应。</span><span class="sxs-lookup"><span data-stu-id="1468e-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="1468e-136">内部异常: HHTP 请求未经授权</span><span class="sxs-lookup"><span data-stu-id="1468e-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="1468e-137">客户端协商方案 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="1468e-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="1468e-138">的身份验证</span><span class="sxs-lookup"><span data-stu-id="1468e-138">The authentication</span></span>

<span data-ttu-id="1468e-139">从服务器收到的标头是 "协商, NTLM"。</span><span class="sxs-lookup"><span data-stu-id="1468e-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="1468e-140">内部异常: 远程服务器返回错误:</span><span class="sxs-lookup"><span data-stu-id="1468e-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="1468e-141">(401) 未经授权。</span><span class="sxs-lookup"><span data-stu-id="1468e-141">(401) Unauthorized.</span></span>

<span data-ttu-id="1468e-142">自检</span><span class="sxs-lookup"><span data-stu-id="1468e-142">Diagnosis :</span></span>

<span data-ttu-id="1468e-143">内部诊断: X-MS-服务器 Fqdb: atl-cs-</span><span class="sxs-lookup"><span data-stu-id="1468e-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="1468e-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1468e-144">001.litwareinc.com</span></span>

<span data-ttu-id="1468e-145">缓存控制: private</span><span class="sxs-lookup"><span data-stu-id="1468e-145">Cache-Control : private</span></span>

<span data-ttu-id="1468e-146">内容类型: 文本/html;字符集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="1468e-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="1468e-147">服务器: Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="1468e-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="1468e-148">WWW-身份验证: 协商, NTLM</span><span class="sxs-lookup"><span data-stu-id="1468e-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="1468e-149">X-通过: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1468e-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="1468e-150">X-内容类型-选项: nosniff</span><span class="sxs-lookup"><span data-stu-id="1468e-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="1468e-151">日期: 星期三, 28 五月 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="1468e-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="1468e-152">内容长度: 6305</span><span class="sxs-lookup"><span data-stu-id="1468e-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1468e-153">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="1468e-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="1468e-154">如果测试 CsMcxP2PIM 失败第一步应验证移动服务是否已启动并正在运行。</span><span class="sxs-lookup"><span data-stu-id="1468e-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="1468e-155">可通过使用 web 浏览器验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1468e-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="1468e-156">例如, 此命令将验证 pool atl-cs-001.litwareinc.com 的 URL:</span><span class="sxs-lookup"><span data-stu-id="1468e-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="1468e-157">如果移动服务似乎正在运行, 请验证你的两个测试用户是否具有有效的 Lync 服务器帐户。</span><span class="sxs-lookup"><span data-stu-id="1468e-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="1468e-158">你可以使用类似下面的命令检索帐户信息:</span><span class="sxs-lookup"><span data-stu-id="1468e-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="1468e-159">如果 Enabled 属性不等于 True 或命令失败, 则意味着用户没有有效的 Lync 服务器帐户。</span><span class="sxs-lookup"><span data-stu-id="1468e-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="1468e-160">你还应验证用户是否已启用移动。</span><span class="sxs-lookup"><span data-stu-id="1468e-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="1468e-161">若要执行此操作, 请首先确定分配给该帐户的移动策略:</span><span class="sxs-lookup"><span data-stu-id="1468e-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="1468e-162">知道策略名称后, 请使用 CsMobilityPolicy cmdlet 验证有问题的策略 (例如, RedmondMobilityPolicy) 是否将 EnableMobility 属性设置为 True:</span><span class="sxs-lookup"><span data-stu-id="1468e-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="1468e-163">如果收到一条带有身份验证头的错误消息, 这通常意味着你没有指定有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1468e-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="1468e-164">验证用户名和密码, 然后再次尝试测试。</span><span class="sxs-lookup"><span data-stu-id="1468e-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="1468e-165">如果您确信用户帐户有效, 请使用 CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1468e-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="1468e-166">这将告诉你在你的组织中启用了哪些身份验证方法。有关如何解决移动服务问题的更多提示, 请参阅分步[解决外部 Lync 移动性连接问题](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)的博客文章。</span><span class="sxs-lookup"><span data-stu-id="1468e-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

