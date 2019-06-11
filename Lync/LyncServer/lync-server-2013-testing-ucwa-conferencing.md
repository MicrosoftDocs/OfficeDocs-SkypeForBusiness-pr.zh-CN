---
title: 'Lync Server 2013: 测试 UCWA 会议'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="447f0-102">在 Lync Server 2013 中测试 UCWA 会议</span><span class="sxs-lookup"><span data-stu-id="447f0-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="447f0-103">_**主题上次修改时间:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="447f0-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="447f0-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="447f0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="447f0-105">每天</span><span class="sxs-lookup"><span data-stu-id="447f0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="447f0-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="447f0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="447f0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="447f0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="447f0-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="447f0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="447f0-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="447f0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="447f0-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行<strong>CsUcwaConference</strong> cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="447f0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="447f0-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="447f0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="447f0-112">说明</span><span class="sxs-lookup"><span data-stu-id="447f0-112">Description</span></span>

<span data-ttu-id="447f0-113">**CsUcwaConference** cmdlet 验证一对测试用户是否可以使用统一通信 Web API (UCWA) 安排、加入和召开联机会议。</span><span class="sxs-lookup"><span data-stu-id="447f0-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="447f0-114">为此, cmdlet 使用 Lync Server web ticket 服务对这两个测试用户进行身份验证, 并使用 Lync Server 注册它们。</span><span class="sxs-lookup"><span data-stu-id="447f0-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="447f0-115">然后, 该 cmdlet 使用组织者凭据启动会议, 并邀请参与者加入会议。</span><span class="sxs-lookup"><span data-stu-id="447f0-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="447f0-116">加入会议后, **CsUcwaConference** cmdlet 验证用户是否可以执行诸如 exchange 即时消息和执行池之类的操作, 然后断开会议并注销两个测试用户。</span><span class="sxs-lookup"><span data-stu-id="447f0-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="447f0-117">计划的会议在测试完成后也会被删除。</span><span class="sxs-lookup"><span data-stu-id="447f0-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="447f0-118">**CsUcwaConference** cmdlet 还可用于确定匿名用户是否可以加入联机会议。</span><span class="sxs-lookup"><span data-stu-id="447f0-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="447f0-119">请注意, 除非在该池中安装了 UCWA, 否则不应针对 Microsoft Lync Server 2010 池运行**CsUcwaConference** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="447f0-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="447f0-120">如果 UCWA 尚未安装, 则对**CsUcwaConference** cmdlet 的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="447f0-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="447f0-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="447f0-121">Running the test</span></span>

<span data-ttu-id="447f0-122">示例1中所示的命令验证一对测试用户是否可以参与 pool atl-cs-001.litwareinc.com 上的 UCWA 会议。</span><span class="sxs-lookup"><span data-stu-id="447f0-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="447f0-123">请注意, 如果尚未预定义一对 atl-cs-001.litwareinc.com 的运行状况监视配置测试用户, 此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="447f0-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="447f0-124">示例2中所示的命令测试一对用户 (litwareinc\\pilar 和 litwareinc\\kenmyer) 的功能以参与 UCWA 会议。</span><span class="sxs-lookup"><span data-stu-id="447f0-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="447f0-125">为此, 示例中的第一个命令使用 Get 凭据 cmdlet 创建 Windows PowerShell 命令行界面凭据对象, 该对象包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="447f0-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="447f0-126">(由于 "登录名"、\\"litwareinc pilar" 已作为参数包含, 因此 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。)然后, 所生成的凭据对象将存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="447f0-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="447f0-127">第二个命令执行相同操作, 这一次返回 Ken Myer 帐户的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="447f0-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="447f0-128">使用这两个凭据对象, 示例中的第三个命令确定两个用户是否可以参与 UCWA 会议。</span><span class="sxs-lookup"><span data-stu-id="447f0-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="447f0-129">若要运行此任务, **CsUcwaConference** cmdlet 与以下参数一起调用: TargetFqdn (注册机构池的 FQDN);OrganizerSipAddress (会议组织者的 SIP 地址);OrganizerCredential (包含此同一用户的凭据的 Windows PowerShell 对象);ParticipantSipAddress (其他测试用户的 SIP 地址);和 ParticipantCredential (包含其他用户的凭据的 Windows PowerShell 命令行界面对象)。</span><span class="sxs-lookup"><span data-stu-id="447f0-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="447f0-130">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="447f0-130">Determining success or failure</span></span>

<span data-ttu-id="447f0-131">如果会议配置正确, 你将收到类似于此的输出, 结果属性标记为 "**成功":**</span><span class="sxs-lookup"><span data-stu-id="447f0-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="447f0-132">目标 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="447f0-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="447f0-133">目标 Uri: https://LyncTest-LyncTest。</span><span class="sxs-lookup"><span data-stu-id="447f0-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="447f0-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="447f0-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="447f0-135">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="447f0-135">Result : Success</span></span>

<span data-ttu-id="447f0-136">延迟:00:00: 14.9862716</span><span class="sxs-lookup"><span data-stu-id="447f0-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="447f0-137">错误消息:</span><span class="sxs-lookup"><span data-stu-id="447f0-137">Error Message :</span></span>

<span data-ttu-id="447f0-138">自检</span><span class="sxs-lookup"><span data-stu-id="447f0-138">Diagnosis :</span></span>

<span data-ttu-id="447f0-139">如果指定用户无法使用会议, 则结果将显示为 "**失败**", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="447f0-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="447f0-140">警告: 无法读取给定的完全限定的注册机构端口号</span><span class="sxs-lookup"><span data-stu-id="447f0-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="447f0-141">域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="447f0-141">domain name (FQDN).</span></span> <span data-ttu-id="447f0-142">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="447f0-142">Using default Registrar port number.</span></span> <span data-ttu-id="447f0-143">除了</span><span class="sxs-lookup"><span data-stu-id="447f0-143">Exception:</span></span>

<span data-ttu-id="447f0-144">InvalidOperationException: 在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="447f0-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="447f0-145">看</span><span class="sxs-lookup"><span data-stu-id="447f0-145">at</span></span>

<span data-ttu-id="447f0-146">SipSyntheticTransaction. TryRetri 的 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="447f0-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="447f0-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="447f0-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="447f0-148">Test-CsUcwaConference: 没有分配测试用户</span><span class="sxs-lookup"><span data-stu-id="447f0-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="447f0-149">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="447f0-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="447f0-150">验证测试用户配置。</span><span class="sxs-lookup"><span data-stu-id="447f0-150">Verify test user configuration.</span></span>

<span data-ttu-id="447f0-151">在第1行: 1 个字符: 1</span><span class="sxs-lookup"><span data-stu-id="447f0-151">At line:1 char:1</span></span>

<span data-ttu-id="447f0-152">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="447f0-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="447f0-153">\+CategoryInfo: ResourceUnavailable: (:)\[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="447f0-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="447f0-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="447f0-154">, InvalidOperationException</span></span>

<span data-ttu-id="447f0-155">\+FullyQualifiedErrorId: NotFoundTestUsers、</span><span class="sxs-lookup"><span data-stu-id="447f0-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="447f0-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="447f0-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="447f0-157">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="447f0-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="447f0-158">下面是**测试 CsUcwaConference**可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="447f0-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="447f0-159">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="447f0-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="447f0-160">如果使用, 则必须正确配置可选参数, 否则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="447f0-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="447f0-161">重新运行不带可选参数的命令, 并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="447f0-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="447f0-162">执行会议的功能取决于已分配给组织会议的用户的会议策略 (在**CsUcwaConference** cmdlet 的情况下为 "sender")。</span><span class="sxs-lookup"><span data-stu-id="447f0-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="447f0-163">如果不允许组织者在其会议中包含协作活动 (例如, 如果其会议策略将 EnableDataCollaboration 属性设置为 False), 则**CsUcwaConference** cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="447f0-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="447f0-164">如果边缘服务器配置错误或尚未部署, 此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="447f0-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="447f0-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="447f0-165">See Also</span></span>


[<span data-ttu-id="447f0-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="447f0-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="447f0-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="447f0-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="447f0-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="447f0-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

