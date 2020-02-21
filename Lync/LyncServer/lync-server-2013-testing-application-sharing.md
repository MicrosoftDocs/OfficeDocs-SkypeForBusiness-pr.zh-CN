---
title: Lync Server 2013：测试应用程序共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c82ecab8883a6ccb5e6573d1d164e41648f14bfe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="5f697-102">在 Lync Server 2013 中测试应用程序共享</span><span class="sxs-lookup"><span data-stu-id="5f697-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f697-103">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="5f697-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f697-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="5f697-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5f697-105">每天</span><span class="sxs-lookup"><span data-stu-id="5f697-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f697-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="5f697-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5f697-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f697-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f697-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="5f697-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5f697-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="5f697-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5f697-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsASConference cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="5f697-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="5f697-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5f697-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5f697-112">Description</span><span class="sxs-lookup"><span data-stu-id="5f697-112">Description</span></span>

<span data-ttu-id="5f697-113">**CsASConference** cmdlet 验证一对测试用户是否可以参与包含应用程序共享的联机会议。</span><span class="sxs-lookup"><span data-stu-id="5f697-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="5f697-114">为此，该 cmdlet 将为两个用户注册 Lync Server 2013，然后使用其中一个用户帐户来创建包括应用程序共享的新会议。</span><span class="sxs-lookup"><span data-stu-id="5f697-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="5f697-115">之后，cmdlet 会验证第二个用户是否能够加入该会议。</span><span class="sxs-lookup"><span data-stu-id="5f697-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5f697-116">运行测试</span><span class="sxs-lookup"><span data-stu-id="5f697-116">Running the test</span></span>

<span data-ttu-id="5f697-p103">示例 1 中显示的命令验证能否在池 atl-cs-001.litwareinc.com 中召开应用程序共享会议。此命令假定您已为指定的池配置了一对测试用户。如果不存在此类测试用户，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="5f697-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="5f697-p104">示例 2 测试 Join Launcher 服务能否参与池 atl-cs-001.litwareinc.com 中的应用程序共享会议。请注意，该命令仅测试服务本身；您无需任何移动设备便可运行该命令。</span><span class="sxs-lookup"><span data-stu-id="5f697-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="5f697-122">示例2中显示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登录 Lync Server 2013，然后执行应用程序共享会议。</span><span class="sxs-lookup"><span data-stu-id="5f697-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="5f697-123">为执行此操作，示例中的第一个命令使用 Get-Credential cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，其中包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="5f697-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="5f697-124">（因为登录名（litwareinc\\pilar）已作为参数包含，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，将生成的 credential 对象存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="5f697-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="5f697-125">第二个命令执行相同的操作，但这次返回的是 Ken Myer 帐户的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="5f697-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="5f697-126">使用 credential 对象时，第三个命令确定这两个用户是否可以登录 Lync Server 2013 并执行应用程序共享会议。</span><span class="sxs-lookup"><span data-stu-id="5f697-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="5f697-127">若要执行此任务，请调用**CsASConference** cmdlet 以及以下参数： TargetFqdn （注册器池的 FQDN）;SenderSipAddress （第一个测试用户的 SIP 地址）;SenderCredential （包含此同一用户的凭据的 Windows PowerShell 对象）;ReceiverSipAddress （其他测试用户的 SIP 地址）;和 ReceiverCredential （包含其他测试用户的凭据的 Windows PowerShell 对象）。</span><span class="sxs-lookup"><span data-stu-id="5f697-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5f697-128">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="5f697-128">Determining success or failure</span></span>

<span data-ttu-id="5f697-129">如果正确配置了应用程序共享，则会收到类似于以下内容的输出，并将 Result 属性标记为 "**成功"：**</span><span class="sxs-lookup"><span data-stu-id="5f697-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5f697-130">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f697-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f697-131">结果：成功</span><span class="sxs-lookup"><span data-stu-id="5f697-131">Result : Success</span></span>

<span data-ttu-id="5f697-132">延迟：00:00:01</span><span class="sxs-lookup"><span data-stu-id="5f697-132">Latency : 00:00:01</span></span>

<span data-ttu-id="5f697-133">错误消息：</span><span class="sxs-lookup"><span data-stu-id="5f697-133">Error Message :</span></span>

<span data-ttu-id="5f697-134">诊断</span><span class="sxs-lookup"><span data-stu-id="5f697-134">Diagnosis :</span></span>

<span data-ttu-id="5f697-135">如果指定用户不能共享应用程序，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="5f697-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5f697-136">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f697-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5f697-137">结果：失败</span><span class="sxs-lookup"><span data-stu-id="5f697-137">Result : Failure</span></span>

<span data-ttu-id="5f697-138">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="5f697-138">Latency : 00:00:00</span></span>

<span data-ttu-id="5f697-139">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="5f697-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5f697-140">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="5f697-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5f697-141">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="5f697-141">established connection failed because connected host has</span></span>

<span data-ttu-id="5f697-142">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="5f697-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5f697-143">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="5f697-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5f697-144">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="5f697-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5f697-145">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="5f697-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5f697-146">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="5f697-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5f697-147">诊断</span><span class="sxs-lookup"><span data-stu-id="5f697-147">Diagnosis :</span></span>

<span data-ttu-id="5f697-148">例如，以前的输出包括 "连接方未正确响应" 这一说明，这通常表示边缘服务器存在问题。</span><span class="sxs-lookup"><span data-stu-id="5f697-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5f697-149">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="5f697-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="5f697-150">以下是**测试 CsASConference**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="5f697-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="5f697-151">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="5f697-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5f697-152">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="5f697-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5f697-153">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="5f697-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5f697-154">如果为测试用户分配了阻止其使用应用程序共享的会议策略，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="5f697-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="5f697-155">如果边缘服务器配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="5f697-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f697-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f697-156">See Also</span></span>


[<span data-ttu-id="5f697-157">Set-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="5f697-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="5f697-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="5f697-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

