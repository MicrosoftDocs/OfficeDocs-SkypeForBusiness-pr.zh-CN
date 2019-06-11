---
title: 'Lync Server 2013: 测试 Lync 客户端身份验证'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8ea26c39582a69062526c7b4ae00343bb19482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="2e197-102">在 Lync Server 2013 中测试 Lync 客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="2e197-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e197-103">_**主题上次修改时间:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2e197-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e197-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="2e197-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2e197-105">每天</span><span class="sxs-lookup"><span data-stu-id="2e197-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e197-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="2e197-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2e197-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e197-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e197-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="2e197-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2e197-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="2e197-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2e197-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsClientAuth cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="2e197-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="2e197-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="2e197-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2e197-112">说明</span><span class="sxs-lookup"><span data-stu-id="2e197-112">Description</span></span>

<span data-ttu-id="2e197-113">CsClientAuth cmdlet 使你能够确定用户是否可以使用客户端证书登录 Lync 服务器, 你可以运行 CsClientAuth cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2e197-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="2e197-114">在调用 CsClientAuth 后, cmdlet 将联系证书预配服务, 并为指定的用户下载任何客户端证书的副本。</span><span class="sxs-lookup"><span data-stu-id="2e197-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="2e197-115">如果可以找到并下载客户端证书, CsClientAuth 将尝试使用该证书登录。</span><span class="sxs-lookup"><span data-stu-id="2e197-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="2e197-116">如果登录成功, CsClientAuth 将注销并报告测试已成功。</span><span class="sxs-lookup"><span data-stu-id="2e197-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="2e197-117">如果无法找到或下载证书, 或者 cmdlet 无法使用该证书登录, 则测试 CsClientAuth 将报告测试失败。</span><span class="sxs-lookup"><span data-stu-id="2e197-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2e197-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="2e197-118">Running the test</span></span>

<span data-ttu-id="2e197-119">CsClientAuth cmdlet 是使用已启用 Lync Server 的任何用户的帐户运行的。</span><span class="sxs-lookup"><span data-stu-id="2e197-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="2e197-120">若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="2e197-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="2e197-121">然后, 在系统调用 Test-CsClientAuth 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="2e197-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="2e197-122">有关详细信息, 请参阅[CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="2e197-122">For more information, see the Help documentation for the [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2e197-123">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="2e197-123">Determining success or failure</span></span>

<span data-ttu-id="2e197-124">如果指定用户可以使用客户端证书登录到 Lync 服务器, 你将收到与此类似的输出, 结果属性标记为**成功:**</span><span class="sxs-lookup"><span data-stu-id="2e197-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2e197-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2e197-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2e197-126">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="2e197-126">Result : Success</span></span>

<span data-ttu-id="2e197-127">延迟:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="2e197-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="2e197-128">时发生</span><span class="sxs-lookup"><span data-stu-id="2e197-128">Error :</span></span>

<span data-ttu-id="2e197-129">自检</span><span class="sxs-lookup"><span data-stu-id="2e197-129">Diagnosis :</span></span>

<span data-ttu-id="2e197-130">如果指定的用户无法登录, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="2e197-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2e197-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2e197-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2e197-132">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="2e197-132">Result : Failure</span></span>

<span data-ttu-id="2e197-133">延迟:00:00: 03.3645259</span><span class="sxs-lookup"><span data-stu-id="2e197-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="2e197-134">错误: 无法下载给定用户的 CS 证书。</span><span class="sxs-lookup"><span data-stu-id="2e197-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="2e197-135">检查是否</span><span class="sxs-lookup"><span data-stu-id="2e197-135">Check if</span></span>

<span data-ttu-id="2e197-136">提供的 uri 和凭据是正确的。</span><span class="sxs-lookup"><span data-stu-id="2e197-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="2e197-137">自检</span><span class="sxs-lookup"><span data-stu-id="2e197-137">Diagnosis :</span></span>

<span data-ttu-id="2e197-138">例如, 以前的输出声明由于无法为指定用户找到有效的客户端证书而导致测试失败。</span><span class="sxs-lookup"><span data-stu-id="2e197-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="2e197-139">你可以通过运行命令来返回颁发给用户的客户端证书的列表, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2e197-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="2e197-140">如果 CsClientAuth 失败, 则可能需要重新运行测试, 这一次包括 Verbose 参数:</span><span class="sxs-lookup"><span data-stu-id="2e197-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="2e197-141">当包含 Verbose 参数时, CsClientAuth 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="2e197-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2e197-142">例如：</span><span class="sxs-lookup"><span data-stu-id="2e197-142">For example:</span></span>

<span data-ttu-id="2e197-143">尝试下载用户的 CS 证书: kenmyer@litwareinc.com 终结点: STEpid</span><span class="sxs-lookup"><span data-stu-id="2e197-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="2e197-144">Web 服务 url:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="2e197-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="2e197-145">无法从 web 服务下载 CS 证书。</span><span class="sxs-lookup"><span data-stu-id="2e197-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="2e197-146">选中</span><span class="sxs-lookup"><span data-stu-id="2e197-146">CHECK:</span></span>

<span data-ttu-id="2e197-147">\-Web 服务 url 有效且 web 服务正常运行</span><span class="sxs-lookup"><span data-stu-id="2e197-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="2e197-148">\-如果使用 PhoneNo\\\\Pin 进行身份验证, 请确保它们与用户 uri 匹配</span><span class="sxs-lookup"><span data-stu-id="2e197-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="2e197-149">\-如果使用 NTLM\\Kerberos 身份验证, 请确保提供有效的凭据</span><span class="sxs-lookup"><span data-stu-id="2e197-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2e197-150">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="2e197-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="2e197-151">下面是测试 CsClientAuth 可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="2e197-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="2e197-152">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="2e197-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="2e197-153">你可以通过运行类似如下所示的命令来验证用户帐户是否存在:</span><span class="sxs-lookup"><span data-stu-id="2e197-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2e197-154">用户帐户有效, 但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="2e197-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2e197-155">若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:</span><span class="sxs-lookup"><span data-stu-id="2e197-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2e197-156">如果 Enabled 属性设置为 False, 则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="2e197-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="2e197-157">测试用户可能没有有效的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="2e197-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="2e197-158">你可以使用类似下面的命令返回有关分配给用户的客户端证书的信息:</span><span class="sxs-lookup"><span data-stu-id="2e197-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

