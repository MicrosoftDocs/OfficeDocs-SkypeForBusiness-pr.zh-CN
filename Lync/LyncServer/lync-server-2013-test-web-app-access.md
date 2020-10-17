---
title: Lync Server 2013：测试 Web 应用程序访问
description: Lync Server 2013：测试 Web 应用访问。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3bbc8008df4fe47fc5a39571356383fe5a6035
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560828"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="0618f-103">在 Lync Server 2013 中测试 Web 应用程序访问</span><span class="sxs-lookup"><span data-stu-id="0618f-103">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0618f-104">_**上次修改的主题：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="0618f-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0618f-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="0618f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0618f-106">每月</span><span class="sxs-lookup"><span data-stu-id="0618f-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0618f-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="0618f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0618f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0618f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0618f-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="0618f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0618f-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="0618f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0618f-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsWebApp cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="0618f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="0618f-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0618f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0618f-113">说明</span><span class="sxs-lookup"><span data-stu-id="0618f-113">Description</span></span>

<span data-ttu-id="0618f-114">Test-CsWebApp cmdlet 验证已通过身份验证的用户是否可以使用 Lync Web App 加入 Lync Server 会议。</span><span class="sxs-lookup"><span data-stu-id="0618f-114">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="0618f-115">运行 cmdlet 时，Test-CsWebApp 与 Web 票证服务联系，以获取指定用户的 Web 入场券。</span><span class="sxs-lookup"><span data-stu-id="0618f-115">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="0618f-116">这些票证可有效地充当 Lync Server 会议的 "许可票证"。</span><span class="sxs-lookup"><span data-stu-id="0618f-116">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="0618f-117">如果可以检索票证，并且可以对用户进行身份验证，则 Test-CsWebApp 将与 Lync Server 联系，并尝试为即时消息、应用程序共享和数据协作建立单独的会议。</span><span class="sxs-lookup"><span data-stu-id="0618f-117">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="0618f-118">请注意，Test-CsWebApp 只验证用于创建这些会议的 Api 和连接。</span><span class="sxs-lookup"><span data-stu-id="0618f-118">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="0618f-119">此 cmdlet 旨在验证 Lync Web App 是否可用于创建和加入会议。</span><span class="sxs-lookup"><span data-stu-id="0618f-119">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="0618f-120">但是，它实际上并不创建和开展会议。</span><span class="sxs-lookup"><span data-stu-id="0618f-120">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0618f-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="0618f-121">Running the test</span></span>

<span data-ttu-id="0618f-122">可以使用一对预配置的测试帐户或任何两个已启用 Lync Server 的用户的帐户运行 Test-CsWebApp cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0618f-122">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="0618f-123">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的完全限定的域名即可。</span><span class="sxs-lookup"><span data-stu-id="0618f-123">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="0618f-124">例如：</span><span class="sxs-lookup"><span data-stu-id="0618f-124">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="0618f-125">若要使用实际用户帐户运行此检查，必须为每个帐户 (包含帐户名称和密码) 的对象创建两个 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="0618f-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="0618f-126">在调用 CsWebApp 时，必须包括这些凭据对象和两个帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="0618f-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="0618f-127">有关详细信息，请参阅 [CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0618f-127">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="0618f-128">请注意，Test-CsWebApp 已弃用，无法在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="0618f-128">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0618f-129">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="0618f-129">Determining success or failure</span></span>

<span data-ttu-id="0618f-130">如果 Test-CsWebApp 可以将用户加入其会议，则 cmdlet 将返回测试结果 "成功"：</span><span class="sxs-lookup"><span data-stu-id="0618f-130">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="0618f-131">目标 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="0618f-131">Target Fqdn :</span></span>

<span data-ttu-id="0618f-132">结果：成功</span><span class="sxs-lookup"><span data-stu-id="0618f-132">Result : Success</span></span>

<span data-ttu-id="0618f-133">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="0618f-133">Latency : 00:00:00</span></span>

<span data-ttu-id="0618f-134">错误消息：</span><span class="sxs-lookup"><span data-stu-id="0618f-134">Error Message :</span></span>

<span data-ttu-id="0618f-135">诊断</span><span class="sxs-lookup"><span data-stu-id="0618f-135">Diagnosis :</span></span>

<span data-ttu-id="0618f-136">如果用户无法加入必需的会议，则测试结果将被标记为 "失败"。</span><span class="sxs-lookup"><span data-stu-id="0618f-136">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="0618f-137">通常 Test-CsWebApp 还将报告回详细的错误消息和诊断：</span><span class="sxs-lookup"><span data-stu-id="0618f-137">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="0618f-138">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0618f-138">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0618f-139">结果：失败</span><span class="sxs-lookup"><span data-stu-id="0618f-139">Result : Failure</span></span>

<span data-ttu-id="0618f-140">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="0618f-140">Latency : 00:00:00</span></span>

<span data-ttu-id="0618f-141">错误消息：未收到 Web-Ticket 服务的响应</span><span class="sxs-lookup"><span data-stu-id="0618f-141">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="0618f-142">诊断： HTTP 请求未通过客户端授权</span><span class="sxs-lookup"><span data-stu-id="0618f-142">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="0618f-143">身份验证方案 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="0618f-143">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="0618f-144">的身份验证</span><span class="sxs-lookup"><span data-stu-id="0618f-144">The authentication</span></span>

<span data-ttu-id="0618f-145">从服务器接收到的标头是 "协商，NTLM"。</span><span class="sxs-lookup"><span data-stu-id="0618f-145">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0618f-146">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="0618f-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="0618f-147">Test-CsWebApp 故障通常涉及到用户身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="0618f-147">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="0618f-148">如果 Test-CsWebApp 失败，应首先验证指定的用户是否具有有效的用户帐户，并且是否为 Lync Server 启用了。</span><span class="sxs-lookup"><span data-stu-id="0618f-148">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="0618f-149">您可以使用与以下内容类似的命令检索帐户信息：</span><span class="sxs-lookup"><span data-stu-id="0618f-149">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="0618f-150">如果 Enabled 属性不等于 True，或者如果命令失败，则表示用户没有有效的 Lync Server 帐户。此外，还应验证提供给 cmdlet 的密码是否有效。</span><span class="sxs-lookup"><span data-stu-id="0618f-150">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

