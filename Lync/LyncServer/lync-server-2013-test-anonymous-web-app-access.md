---
title: 'Lync Server 2013: 测试匿名 Web 应用访问'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 701954a872645e80d6aac82cab1fbf5745ad6984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="f66ab-102">在 Lync Server 2013 中测试匿名 Web 应用访问</span><span class="sxs-lookup"><span data-stu-id="f66ab-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f66ab-103">_**主题上次修改时间:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="f66ab-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f66ab-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="f66ab-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f66ab-105">每月</span><span class="sxs-lookup"><span data-stu-id="f66ab-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f66ab-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="f66ab-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f66ab-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f66ab-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f66ab-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="f66ab-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f66ab-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="f66ab-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f66ab-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsWebAppAnonymous cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="f66ab-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="f66ab-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="f66ab-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f66ab-112">说明</span><span class="sxs-lookup"><span data-stu-id="f66ab-112">Description</span></span>

<span data-ttu-id="f66ab-113">CsWebAppAnonymous cmdlet 验证匿名用户是否可以使用 Lync Web App 加入 Lync Server 会议。</span><span class="sxs-lookup"><span data-stu-id="f66ab-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="f66ab-114">运行 cmdlet 时, CsWebAppAnonymous 会联系 Web 票证服务以获取匿名用户的 Web 票证。</span><span class="sxs-lookup"><span data-stu-id="f66ab-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="f66ab-115">如果 cmdlet 成功获取此票证, 则 CsWebAppAnonymous 将联系 Lync Server 并尝试建立单独的会议, 以便发送即时消息、应用程序共享和数据协作。</span><span class="sxs-lookup"><span data-stu-id="f66ab-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="f66ab-116">请注意, 测试 CsWebAppAnonymous 仅验证用于创建这些会议的 Api 和连接。</span><span class="sxs-lookup"><span data-stu-id="f66ab-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="f66ab-117">该 cmdlet 实际上不会创建和执行任何会议。</span><span class="sxs-lookup"><span data-stu-id="f66ab-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f66ab-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="f66ab-118">Running the test</span></span>

<span data-ttu-id="f66ab-119">CsWebAppAnonymous cmdlet 可以使用一对预配置的测试帐户或任何两个已启用 Lync Server 的用户的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="f66ab-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f66ab-120">若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="f66ab-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="f66ab-121">例如：</span><span class="sxs-lookup"><span data-stu-id="f66ab-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="f66ab-122">若要使用实际用户帐户运行此检查, 必须为每个帐户创建两个 Lync Server 管理外壳凭据对象 (包含帐户名和密码的对象)。</span><span class="sxs-lookup"><span data-stu-id="f66ab-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f66ab-123">然后, 当你调用 Test-CsWebAppAnonymous 时, 你必须包含这些凭据对象和两个帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="f66ab-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="f66ab-124">有关详细信息, 请参阅 CsWebAppAnonymous cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f66ab-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="f66ab-125">请注意, CsWebAppAnonymous 已弃用, 无法在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="f66ab-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f66ab-126">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="f66ab-126">Determining success or failure</span></span>

<span data-ttu-id="f66ab-127">如果 CsWebAppAnonymous 可以将匿名用户加入其会议, 则 cmdlet 将返回测试结果成功:</span><span class="sxs-lookup"><span data-stu-id="f66ab-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="f66ab-128">目标 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="f66ab-128">Target Fqdn :</span></span>

<span data-ttu-id="f66ab-129">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="f66ab-129">Result : Success</span></span>

<span data-ttu-id="f66ab-130">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f66ab-130">Latency : 00:00:00</span></span>

<span data-ttu-id="f66ab-131">错误消息:</span><span class="sxs-lookup"><span data-stu-id="f66ab-131">Error Message :</span></span>

<span data-ttu-id="f66ab-132">自检</span><span class="sxs-lookup"><span data-stu-id="f66ab-132">Diagnosis :</span></span>

<span data-ttu-id="f66ab-133">如果匿名用户无法加入必要的会议, 则测试结果将标记为 "失败"。</span><span class="sxs-lookup"><span data-stu-id="f66ab-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="f66ab-134">通常情况下, CsWebAppAnonymous 测试还将报告详细的错误消息和诊断:</span><span class="sxs-lookup"><span data-stu-id="f66ab-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="f66ab-135">目标 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f66ab-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f66ab-136">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="f66ab-136">Result : Failure</span></span>

<span data-ttu-id="f66ab-137">延迟:00:00: 05.9746266</span><span class="sxs-lookup"><span data-stu-id="f66ab-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="f66ab-138">错误消息: 未收到 Web 票证服务的响应</span><span class="sxs-lookup"><span data-stu-id="f66ab-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="f66ab-139">诊断: HTTP 请求未通过客户端授权</span><span class="sxs-lookup"><span data-stu-id="f66ab-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="f66ab-140">身份验证方案 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="f66ab-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="f66ab-141">的身份验证</span><span class="sxs-lookup"><span data-stu-id="f66ab-141">The authentication</span></span>

<span data-ttu-id="f66ab-142">从服务器收到的标头是 "协商, NTLM"。</span><span class="sxs-lookup"><span data-stu-id="f66ab-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f66ab-143">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="f66ab-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="f66ab-144">CsWebAppAnonymous 故障通常围绕用户身份验证错误进行旋转: 你必须使用有效的用户帐户运行测试, 即使 cmdlet 检查匿名用户连接到 Lync 服务器的能力。</span><span class="sxs-lookup"><span data-stu-id="f66ab-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="f66ab-145">如果 CsWebAppAnonymous 测试失败, 应验证指定用户是否具有有效的 Lync Server 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f66ab-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="f66ab-146">您可以使用类似下面的命令检索 Lync 服务器帐户信息:</span><span class="sxs-lookup"><span data-stu-id="f66ab-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="f66ab-147">如果 Enabled 属性不等于 True 或命令失败, 则意味着用户没有有效的 Lync 服务器帐户。</span><span class="sxs-lookup"><span data-stu-id="f66ab-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="f66ab-148">你还应验证运行 cmdlet 时提供的密码是否为有效密码。</span><span class="sxs-lookup"><span data-stu-id="f66ab-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="f66ab-149">Office Web Apps 服务器的配置问题也可能导致测试 CsWebAppAnonymous 失败。如果你收到以下诊断, 通常会出现这种情况:</span><span class="sxs-lookup"><span data-stu-id="f66ab-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="f66ab-150">通过客户端身份验证方案 "Ntlm" 对 HTTP 请求进行了未经授权。</span><span class="sxs-lookup"><span data-stu-id="f66ab-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="f66ab-151">从服务器收到的身份验证标头是 "协商, NTLM"。</span><span class="sxs-lookup"><span data-stu-id="f66ab-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="f66ab-152">有关诊断和解决 Office Web Apps 服务器问题的详细信息, 请参阅博客文章[Office Web Apps server 2013-计算机始终报告为 "不正常](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)"。</span><span class="sxs-lookup"><span data-stu-id="f66ab-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

