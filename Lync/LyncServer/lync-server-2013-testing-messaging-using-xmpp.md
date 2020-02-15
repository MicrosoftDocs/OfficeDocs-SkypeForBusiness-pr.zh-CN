---
title: Lync Server 2013：使用 XMPP 测试邮件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94841a3ec17878258b26fd945aa60123ac76a9c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="92d15-102">在 Lync Server 2013 中使用 XMPP 测试邮件</span><span class="sxs-lookup"><span data-stu-id="92d15-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92d15-103">_**上次修改的主题：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="92d15-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d15-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="92d15-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="92d15-105">每天</span><span class="sxs-lookup"><span data-stu-id="92d15-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92d15-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="92d15-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="92d15-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92d15-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92d15-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="92d15-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="92d15-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="92d15-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="92d15-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsXmppIM</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="92d15-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="92d15-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="92d15-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="92d15-112">说明</span><span class="sxs-lookup"><span data-stu-id="92d15-112">Description</span></span>

<span data-ttu-id="92d15-113">可扩展消息传递和状态协议 (XMPP) 是用于在 Internet 中发送消息的标准通信协议（基于 XML）。</span><span class="sxs-lookup"><span data-stu-id="92d15-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="92d15-114">XMPP 最初被命名为 Jabber，并受几个 Internet 邮件和通信应用程序（如 Google 谈话和 Facebook 聊天）的支持。</span><span class="sxs-lookup"><span data-stu-id="92d15-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="92d15-115">**CsXmppIM** cmdlet 验证用户是否可以与 XMPP 网络上的用户交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="92d15-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="92d15-116">请注意，为使此测试成功，必须为 XMPP 用户提供有效的 SIP 地址，并且该 SIP 地址必须位于配置为允许的 XMPP 合作伙伴的网络中。</span><span class="sxs-lookup"><span data-stu-id="92d15-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="92d15-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="92d15-117">Running the test</span></span>

<span data-ttu-id="92d15-118">下面的示例验证 pool atl-cs-001.litwareinc.com 的 XMPP 即时消息功能。</span><span class="sxs-lookup"><span data-stu-id="92d15-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="92d15-119">仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，才会运行此命令。</span><span class="sxs-lookup"><span data-stu-id="92d15-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="92d15-120">如果有，则该命令将确定第一个测试用户是否可以向具有 SIP 地址 adelaney@contoso.com 的用户发送 XMPP 即时消息。</span><span class="sxs-lookup"><span data-stu-id="92d15-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="92d15-121">如果未定义测试用户，则命令将失败，因为它不会知道哪个用户登录。</span><span class="sxs-lookup"><span data-stu-id="92d15-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="92d15-122">如果尚未为池定义测试用户，则必须包括 UserSipAddress 参数以及在尝试登录时该命令应使用的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="92d15-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="92d15-123">下一个示例中所示的命令测试特定用户（litwareinc\\pilar）登录以将 XMPP 即时消息发送到用户 adelaney@contoso.com 的功能。</span><span class="sxs-lookup"><span data-stu-id="92d15-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="92d15-124">为执行此操作，示例中的第一个命令使用 Get-Credential cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，该对象包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="92d15-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="92d15-125">（因为登录名 litwareinc\\pilar 作为参数包括在内，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，将生成的 credential 对象存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="92d15-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="92d15-126">然后，第二个命令将检查此用户是否可以登录到池 atl-cs-001.litwareinc.com 并发送 XMPP 即时消息。</span><span class="sxs-lookup"><span data-stu-id="92d15-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="92d15-127">若要运行此任务，请调用**CsXmppIm** cmdlet 以及四个参数： TargetFqdn （注册器池的 FQDN）;接收器（要向其发送邮件的用户的 SIP 地址）;UserCredential （包含 Pilar Ackerman 的用户凭据的 Windows PowerShell 对象）;和 UserSipAddress （与提供的用户凭据对应的 SIP 地址）。</span><span class="sxs-lookup"><span data-stu-id="92d15-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="92d15-128">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="92d15-128">Determining success or failure</span></span>

<span data-ttu-id="92d15-129">如果正确配置 XMPP 即时消息，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="92d15-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="92d15-130">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="92d15-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="92d15-131">结果：成功</span><span class="sxs-lookup"><span data-stu-id="92d15-131">Result : Success</span></span>

<span data-ttu-id="92d15-132">延迟：00：00：02.5361946</span><span class="sxs-lookup"><span data-stu-id="92d15-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="92d15-133">错误消息：</span><span class="sxs-lookup"><span data-stu-id="92d15-133">Error Message :</span></span>

<span data-ttu-id="92d15-134">诊断</span><span class="sxs-lookup"><span data-stu-id="92d15-134">Diagnosis :</span></span>

<span data-ttu-id="92d15-135">如果指定用户无法使用 XMPP 即时消息，则结果将显示为 "**失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="92d15-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="92d15-136">警告：无法读取给定的完全限定的注册器端口号</span><span class="sxs-lookup"><span data-stu-id="92d15-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="92d15-137">域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="92d15-137">domain name (FQDN).</span></span> <span data-ttu-id="92d15-138">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="92d15-138">Using default Registrar port number.</span></span> <span data-ttu-id="92d15-139">异常</span><span class="sxs-lookup"><span data-stu-id="92d15-139">Exception:</span></span>

<span data-ttu-id="92d15-140">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="92d15-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="92d15-141">个</span><span class="sxs-lookup"><span data-stu-id="92d15-141">at</span></span>

<span data-ttu-id="92d15-142">TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="92d15-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="92d15-143">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="92d15-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="92d15-144">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="92d15-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="92d15-145">结果：失败</span><span class="sxs-lookup"><span data-stu-id="92d15-145">Result : Failure</span></span>

<span data-ttu-id="92d15-146">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="92d15-146">Latency : 00:00:00</span></span>

<span data-ttu-id="92d15-147">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="92d15-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="92d15-148">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="92d15-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="92d15-149">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="92d15-149">established connection failed because connected host has</span></span>

<span data-ttu-id="92d15-150">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="92d15-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="92d15-151">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="92d15-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="92d15-152">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="92d15-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="92d15-153">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="92d15-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="92d15-154">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="92d15-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="92d15-155">诊断</span><span class="sxs-lookup"><span data-stu-id="92d15-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="92d15-156">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="92d15-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="92d15-157">以下是**测试 CsXmppIM**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="92d15-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="92d15-158">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="92d15-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="92d15-159">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="92d15-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="92d15-160">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="92d15-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="92d15-161">如果 XMPP 网关配置配置不正确或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="92d15-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92d15-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92d15-162">See Also</span></span>


[<span data-ttu-id="92d15-163">CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="92d15-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

