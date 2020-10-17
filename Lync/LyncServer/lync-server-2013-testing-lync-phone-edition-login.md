---
title: Lync Server 2013：测试 Lync Phone Edition 登录名
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b55ef9024caedaecb27bba3e01eb2bde5181fca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519019"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="fa3f4-102">在 Lync Server 2013 中测试 Lync Phone Edition 登录名</span><span class="sxs-lookup"><span data-stu-id="fa3f4-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa3f4-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fa3f4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa3f4-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="fa3f4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fa3f4-105">每天</span><span class="sxs-lookup"><span data-stu-id="fa3f4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa3f4-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="fa3f4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fa3f4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa3f4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa3f4-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="fa3f4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fa3f4-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fa3f4-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsPhoneBootstrap cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="fa3f4-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fa3f4-112">说明</span><span class="sxs-lookup"><span data-stu-id="fa3f4-112">Description</span></span>

<span data-ttu-id="fa3f4-113">使用 Test-CsPhoneBootstrap cmdlet，管理员可以通过 Lync 2013 Phone Edition 兼容的设备，验证给定用户（使用分配给他/她的电话号码和 PIN）是否可以登录到系统。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="fa3f4-114"> (实际不需要设备来运行测试。 ) </span><span class="sxs-lookup"><span data-stu-id="fa3f4-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="fa3f4-115">为了使 Test-CsPhoneBootstrap 进行检查，必须可以使用 DHCP 发现托管被测试用户帐户的注册器池。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="fa3f4-116">若要确定是否以这种方式发现注册器，请使用 cmdlet Get-CsRegistrarConfiguration 并检查 EnableDHCPServer 属性的值。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="fa3f4-117">如果此属性设置为 False，则必须使用 Set-CsRegistrarConfiguration 将属性值设置为 True，并使用 DHCP 使注册器可检测到。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="fa3f4-118">这也可以通过使用企业 DHCP 服务器并配置 Lync Server 特定的选项来实现。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fa3f4-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="fa3f4-119">Running the test</span></span>

<span data-ttu-id="fa3f4-120">若要运行 Test-CsPhoneBootstrap cmdlet，必须至少为有效的 Lync Server 用户提供 (PIN) 的电话号码和客户端个人标识号。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="fa3f4-121">例如，以下命令将测试电话号码为12065551219和 PIN 为0712的用户的登录能力：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="fa3f4-122">若要进行更全面的检查，您还可以包括用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="fa3f4-123">在这种情况下，电话号码、客户端 PIN 和 SIP 地址都必须有效，才能成功测试：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="fa3f4-124">有关详细信息，请参阅 [CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fa3f4-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="fa3f4-125">Determining success or failure</span></span>

<span data-ttu-id="fa3f4-126">如果指定的用户能够连接到 Lync Server，则会收到类似于以下内容的输出，并将 Result 属性标记为 **成功：**</span><span class="sxs-lookup"><span data-stu-id="fa3f4-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fa3f4-127">TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="fa3f4-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="fa3f4-128">CertProvisioningService</span><span class="sxs-lookup"><span data-stu-id="fa3f4-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="fa3f4-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fa3f4-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fa3f4-130">结果：成功</span><span class="sxs-lookup"><span data-stu-id="fa3f4-130">Result : Success</span></span>

<span data-ttu-id="fa3f4-131">延迟：00：00：06.3981276</span><span class="sxs-lookup"><span data-stu-id="fa3f4-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="fa3f4-132">误差</span><span class="sxs-lookup"><span data-stu-id="fa3f4-132">Error :</span></span>

<span data-ttu-id="fa3f4-133">诊断</span><span class="sxs-lookup"><span data-stu-id="fa3f4-133">Diagnosis :</span></span>

<span data-ttu-id="fa3f4-134">如果指定用户无法建立连接，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fa3f4-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fa3f4-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fa3f4-136">结果：失败</span><span class="sxs-lookup"><span data-stu-id="fa3f4-136">Result : Failure</span></span>

<span data-ttu-id="fa3f4-137">延迟：00：00：04.1993845</span><span class="sxs-lookup"><span data-stu-id="fa3f4-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="fa3f4-138">错误：错误-Web-Ticket 服务没有收到响应。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="fa3f4-139">诊断</span><span class="sxs-lookup"><span data-stu-id="fa3f4-139">Diagnosis :</span></span>

<span data-ttu-id="fa3f4-140">以前的输出表明测试失败，因为 Web 票证服务没有响应。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="fa3f4-141">这可能是因为服务本身存在问题，也可能是因为 SIP 地址、电话号码或客户端 PIN 传递到 CsPhoneBootstrap。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="fa3f4-142">您可以通过使用与以下命令类似的命令来验证用户的 SIP 地址和电话号码：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="fa3f4-143">您可以通过使用以下命令来验证用户是否具有有效的 PIN：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="fa3f4-144">如果 Test-CsPhoneBootstrap 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="fa3f4-145">包含 Verbose 参数时，Test-CsPhoneBootstrap 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="fa3f4-146">例如，以下是失败登录的部分输出，其中包含不正确的 PIN 的会话：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="fa3f4-147">将 PIN 验证与电话 \\ 分机： 12065551219 pin 结合使用：0712</span><span class="sxs-lookup"><span data-stu-id="fa3f4-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="fa3f4-148">无法获取 web 票证</span><span class="sxs-lookup"><span data-stu-id="fa3f4-148">Could not get web ticket</span></span>

<span data-ttu-id="fa3f4-149">复选</span><span class="sxs-lookup"><span data-stu-id="fa3f4-149">CHECK :</span></span>

<span data-ttu-id="fa3f4-150">\- Web 服务 url 有效且 web 服务正常运行</span><span class="sxs-lookup"><span data-stu-id="fa3f4-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="fa3f4-151">\- 如果使用 PhoneNo \\ PIN 进行身份验证，请确保它们与用户 uri 匹配</span><span class="sxs-lookup"><span data-stu-id="fa3f4-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="fa3f4-152">\- 如果使用 NTLM \\ Kerberos 身份验证，请确保提供有效的凭据</span><span class="sxs-lookup"><span data-stu-id="fa3f4-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fa3f4-153">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="fa3f4-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="fa3f4-154">下面是 Test-CsPhoneBootstrap 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="fa3f4-155">您可能指定了无效的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="fa3f4-156">您可以通过使用类似如下的命令来验证 SIP 地址是否正确：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fa3f4-157">您可能指定了无效的 PIN。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="fa3f4-158">虽然无法检索用户的 PIN 号码，但可以使用类似如下的命令验证用户是否至少具有 PIN 号：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fa3f4-159">您可能指定了无效的电话号码。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="fa3f4-160">您可以使用类似于以下的命令来验证用户的电话：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="fa3f4-161">注册器池未启用 DHCP。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="fa3f4-162">若要确定是否为 DHCP 启用了注册器池，请运行 Get-CsRegistrarConfiguration cmdlet，并检查 EnableDHCPServer 属性的值。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="fa3f4-163">例如：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

