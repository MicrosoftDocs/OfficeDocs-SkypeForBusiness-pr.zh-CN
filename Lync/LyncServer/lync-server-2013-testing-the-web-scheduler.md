---
title: Lync Server 2013：测试 Web 计划程序
description: Lync Server 2013：测试 Web 计划程序。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556148"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="cbcdb-103">在 Lync Server 2013 中测试 Web 计划程序</span><span class="sxs-lookup"><span data-stu-id="cbcdb-103">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbcdb-104">_**上次修改的主题：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="cbcdb-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbcdb-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="cbcdb-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cbcdb-106">每天</span><span class="sxs-lookup"><span data-stu-id="cbcdb-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbcdb-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="cbcdb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cbcdb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbcdb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbcdb-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="cbcdb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cbcdb-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cbcdb-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>CsWebScheduler</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="cbcdb-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cbcdb-113">说明</span><span class="sxs-lookup"><span data-stu-id="cbcdb-113">Description</span></span>

<span data-ttu-id="cbcdb-114">**CsWebScheduler** cmdlet 使您能够确定特定用户是否可以使用 Web 计划程序安排会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-114">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="cbcdb-115">Web 计划程序使未运行 Outlook 的用户可以安排联机会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-115">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="cbcdb-116">此外，此新功能 (，它包含在 Microsoft Lync Server 2010 资源工具包中随附的 Web 计划程序工具中的功能，) 使用户能够：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-116">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="cbcdb-117">安排新的联机会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-117">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="cbcdb-118">列出该用户已安排的所有会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-118">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="cbcdb-119">查看/修改现有会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-119">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="cbcdb-120">删除现有会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-120">Delete an existing meeting.</span></span>

  - <span data-ttu-id="cbcdb-121">使用预先配置的 SMTP 邮件服务器向会议参与者发送电子邮件邀请。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-121">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="cbcdb-122">加入现有会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-122">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cbcdb-123">运行测试</span><span class="sxs-lookup"><span data-stu-id="cbcdb-123">Running the test</span></span>

<span data-ttu-id="cbcdb-124">下面的示例验证了池 atl-cs-001.litwareinc.com 的 Web 计划程序。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-124">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="cbcdb-125">仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，才会运行此命令。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-125">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="cbcdb-126">如果有，则该命令将确定第一个测试用户是否可以使用 Web 计划程序安排联机会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-126">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="cbcdb-127">如果未定义测试用户，则命令将失败，因为它不会知道哪个用户登录。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-127">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="cbcdb-128">如果尚未为池定义测试用户，则必须包括 UserSipAddress 参数以及该命令在尝试登录时应使用的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="cbcdb-129">下一个示例中所示的命令测试特定用户 (litwareinc \\ kenmeyer) 的功能，以使用 Web 计划程序安排联机会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-129">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="cbcdb-130">为执行此操作，示例中的第一个命令使用 **Get-Credential** Cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，该对象包含用户 Ken Meyer 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-130">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="cbcdb-131"> (因为登录名 litwareinc \\ kenmeyer 作为参数包括在内，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Ken Meyer 帐户的密码。 ) 生成的 Credential 对象将存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-131">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="cbcdb-132">然后，第二个命令将检查此用户是否可以登录到池 atl-cs-001.litwareinc.com 并安排联机会议。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-132">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="cbcdb-133">若要运行此任务，请调用 **CsWebScheduler** cmdlet 以及三个参数： TargetFqdn (注册器池的 FQDN) ;UserCredential (包含 Pilar Ackerman 的用户凭据的 Windows PowerShell 对象) ;和 UserSipAddress (与提供的用户凭据) 相对应的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-133">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cbcdb-134">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="cbcdb-134">Determining success or failure</span></span>

<span data-ttu-id="cbcdb-135">如果正确配置了 web 计划程序，则会收到与以下内容类似的输出，并将 Result 属性标记为 **成功**：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-135">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="cbcdb-136">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cbcdb-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cbcdb-137">目标 Uri： https://atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-137">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="cbcdb-138">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="cbcdb-138">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="cbcdb-139">结果：成功</span><span class="sxs-lookup"><span data-stu-id="cbcdb-139">Result : Success</span></span>

<span data-ttu-id="cbcdb-140">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="cbcdb-140">Latency : 00:00:00</span></span>

<span data-ttu-id="cbcdb-141">错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-141">Error Message :</span></span>

<span data-ttu-id="cbcdb-142">诊断</span><span class="sxs-lookup"><span data-stu-id="cbcdb-142">Diagnosis :</span></span>

<span data-ttu-id="cbcdb-143">如果未正确配置 web 计划程序，则结果将显示为 " **失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-143">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cbcdb-144">警告：无法读取给定的完全限定的注册器端口号</span><span class="sxs-lookup"><span data-stu-id="cbcdb-144">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="cbcdb-145"> (FQDN) 的域名称。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-145">domain name (FQDN).</span></span> <span data-ttu-id="cbcdb-146">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-146">Using default Registrar port number.</span></span> <span data-ttu-id="cbcdb-147">异常</span><span class="sxs-lookup"><span data-stu-id="cbcdb-147">Exception:</span></span>

<span data-ttu-id="cbcdb-148">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-148">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="cbcdb-149">个</span><span class="sxs-lookup"><span data-stu-id="cbcdb-149">at</span></span>

<span data-ttu-id="cbcdb-150">TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="cbcdb-150">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="cbcdb-151">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="cbcdb-151">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="cbcdb-152">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cbcdb-152">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cbcdb-153">目标 Uri：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-153">Target Uri :</span></span>

<span data-ttu-id="cbcdb-154">结果：失败</span><span class="sxs-lookup"><span data-stu-id="cbcdb-154">Result : Failure</span></span>

<span data-ttu-id="cbcdb-155">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="cbcdb-155">Latency : 00:00:00</span></span>

<span data-ttu-id="cbcdb-156">错误消息：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-156">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="cbcdb-157">诊断</span><span class="sxs-lookup"><span data-stu-id="cbcdb-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cbcdb-158">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="cbcdb-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="cbcdb-159">以下是 **测试 CsWebScheduler** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="cbcdb-159">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="cbcdb-160">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="cbcdb-161">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="cbcdb-162">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="cbcdb-163">如果 Web 计划程序配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="cbcdb-163">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cbcdb-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbcdb-164">See Also</span></span>


[<span data-ttu-id="cbcdb-165">CsWebServer</span><span class="sxs-lookup"><span data-stu-id="cbcdb-165">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

