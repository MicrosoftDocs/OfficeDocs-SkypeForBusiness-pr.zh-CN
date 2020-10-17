---
title: Lync Server 2013：测试 Lync 客户端身份验证
description: Lync Server 2013：测试 Lync 客户端身份验证。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560578"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="7629e-103">在 Lync Server 2013 中测试 Lync 客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="7629e-103">Testing Lync Client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7629e-104">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7629e-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7629e-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="7629e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7629e-106">每天</span><span class="sxs-lookup"><span data-stu-id="7629e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7629e-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="7629e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7629e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7629e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7629e-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="7629e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7629e-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="7629e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7629e-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsClientAuth cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7629e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="7629e-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7629e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7629e-113">说明</span><span class="sxs-lookup"><span data-stu-id="7629e-113">Description</span></span>

<span data-ttu-id="7629e-114">Test-CsClientAuth cmdlet 使您能够确定用户是否可以使用客户端证书登录 Lync Server，可以运行 Test-CsClientAuth cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7629e-114">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="7629e-115">呼叫 Test-CsClientAuth 之后，cmdlet 将与证书提供服务联系，并下载一份指定用户的任意客户端证书。</span><span class="sxs-lookup"><span data-stu-id="7629e-115">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="7629e-116">如果可以找到并下载客户端证书，Test-CsClientAuth 将尝试使用该证书进行登录。</span><span class="sxs-lookup"><span data-stu-id="7629e-116">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="7629e-117">如果登录成功，则 Test-CsClientAuth 将注销并报告测试成功。</span><span class="sxs-lookup"><span data-stu-id="7629e-117">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="7629e-118">如果无法找到或下载证书，或者 cmdlet 无法使用该证书登录，则 Test-CsClientAuth 将报告测试失败。</span><span class="sxs-lookup"><span data-stu-id="7629e-118">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7629e-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="7629e-119">Running the test</span></span>

<span data-ttu-id="7629e-120">使用为 Lync Server 启用的任何用户的帐户运行 Test-CsClientAuth cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7629e-120">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="7629e-121">若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="7629e-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="7629e-122">然后，必须在系统调用 CsClientAuth 时包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="7629e-122">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="7629e-123">有关详细信息，请参阅 [CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="7629e-123">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7629e-124">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="7629e-124">Determining success or failure</span></span>

<span data-ttu-id="7629e-125">如果指定用户可以使用客户端证书登录到 Lync Server，则会收到类似于以下的输出，并将 Result 属性标记为 " **成功"：**</span><span class="sxs-lookup"><span data-stu-id="7629e-125">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7629e-126">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7629e-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7629e-127">结果：成功</span><span class="sxs-lookup"><span data-stu-id="7629e-127">Result : Success</span></span>

<span data-ttu-id="7629e-128">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="7629e-128">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="7629e-129">误差</span><span class="sxs-lookup"><span data-stu-id="7629e-129">Error :</span></span>

<span data-ttu-id="7629e-130">诊断</span><span class="sxs-lookup"><span data-stu-id="7629e-130">Diagnosis :</span></span>

<span data-ttu-id="7629e-131">如果指定的用户无法登录，则结果将显示为 "失败"，并将在 "错误和诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="7629e-131">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7629e-132">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7629e-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7629e-133">结果：失败</span><span class="sxs-lookup"><span data-stu-id="7629e-133">Result : Failure</span></span>

<span data-ttu-id="7629e-134">延迟：00：00：03.3645259</span><span class="sxs-lookup"><span data-stu-id="7629e-134">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="7629e-135">错误：无法为给定用户下载 CS 证书。</span><span class="sxs-lookup"><span data-stu-id="7629e-135">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="7629e-136">检查是否</span><span class="sxs-lookup"><span data-stu-id="7629e-136">Check if</span></span>

<span data-ttu-id="7629e-137">提供的 uri 和凭据是正确的。</span><span class="sxs-lookup"><span data-stu-id="7629e-137">provided uri and credentials are correct.</span></span>

<span data-ttu-id="7629e-138">诊断</span><span class="sxs-lookup"><span data-stu-id="7629e-138">Diagnosis :</span></span>

<span data-ttu-id="7629e-139">例如，由于无法为指定用户找到有效的客户端证书，因此以前的输出表明测试失败。</span><span class="sxs-lookup"><span data-stu-id="7629e-139">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="7629e-140">您可以通过运行命令来返回颁发给用户的客户端证书的列表，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7629e-140">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="7629e-141">如果 Test-CsClientAuth 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="7629e-141">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="7629e-142">包含 Verbose 参数时，Test-CsClientAuth 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="7629e-142">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="7629e-143">例如：</span><span class="sxs-lookup"><span data-stu-id="7629e-143">For example:</span></span>

<span data-ttu-id="7629e-144">尝试为用户下载 CS 证书： kenmyer@litwareinc.com 终结点： STEpid</span><span class="sxs-lookup"><span data-stu-id="7629e-144">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="7629e-145">Web 服务 url： https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="7629e-145">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="7629e-146">无法从 web 服务下载 CS 证书。</span><span class="sxs-lookup"><span data-stu-id="7629e-146">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="7629e-147">复选</span><span class="sxs-lookup"><span data-stu-id="7629e-147">CHECK:</span></span>

<span data-ttu-id="7629e-148">\- Web 服务 url 有效且 web 服务正常运行</span><span class="sxs-lookup"><span data-stu-id="7629e-148">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="7629e-149">\-如果使用 PhoneNo \\ \\ Pin 进行身份验证，请确保它们与用户 uri 匹配</span><span class="sxs-lookup"><span data-stu-id="7629e-149">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="7629e-150">\- 如果使用 NTLM \\ Kerberos 身份验证，请确保提供有效的凭据</span><span class="sxs-lookup"><span data-stu-id="7629e-150">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7629e-151">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="7629e-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="7629e-152">下面是 Test-CsClientAuth 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="7629e-152">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="7629e-153">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="7629e-153">You specified a user account that was not valid.</span></span> <span data-ttu-id="7629e-154">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="7629e-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="7629e-155">用户帐户有效，但当前未对 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="7629e-155">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="7629e-156">若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="7629e-156">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="7629e-157">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="7629e-157">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="7629e-158">测试用户可能没有有效的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="7629e-158">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="7629e-159">您可以使用类似如下的命令返回有关分配给用户的客户端证书的信息：</span><span class="sxs-lookup"><span data-stu-id="7629e-159">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

