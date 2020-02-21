---
title: Lync Server 2013：测试会议中的共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b46fba4c9426a76bfb7c8ca9f15e7cba4950e8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="cd45d-102">在 Lync Server 2013 中测试会议中的共享</span><span class="sxs-lookup"><span data-stu-id="cd45d-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd45d-103">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="cd45d-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd45d-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="cd45d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cd45d-105">每天</span><span class="sxs-lookup"><span data-stu-id="cd45d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd45d-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="cd45d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cd45d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd45d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd45d-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="cd45d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cd45d-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="cd45d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cd45d-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsDataConference</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="cd45d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="cd45d-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cd45d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cd45d-112">说明</span><span class="sxs-lookup"><span data-stu-id="cd45d-112">Description</span></span>

<span data-ttu-id="cd45d-113">在 Lync Server 2013 中，数据会议是指使用协作活动（如白板或批注）的任何会议。</span><span class="sxs-lookup"><span data-stu-id="cd45d-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="cd45d-114">**CsDataConference** cmdlet 使您能够验证一对用户是否能够参与数据会议。</span><span class="sxs-lookup"><span data-stu-id="cd45d-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cd45d-115">运行测试</span><span class="sxs-lookup"><span data-stu-id="cd45d-115">Running the test</span></span>

<span data-ttu-id="cd45d-p103">示例 1 中显示的命令验证是否可以在池 atl-cs-001.litwareinc.com 上召开数据会议。此命令假定您已为指定的池配置了一对测试用户。如果不存在此类测试用户，此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="cd45d-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="cd45d-119">示例2中显示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登录 Lync Server 2013，然后进行数据会议。</span><span class="sxs-lookup"><span data-stu-id="cd45d-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="cd45d-120">为执行此操作，示例中的第一个命令使用**Get-Credential** Cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，其中包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="cd45d-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="cd45d-121">（因为登录名（litwareinc\\pilar）已作为参数包含，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，将生成的 credential 对象存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="cd45d-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="cd45d-122">第二个命令执行相同的操作，但这次返回的是 Ken Myer 帐户的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="cd45d-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="cd45d-123">使用 credential 对象时，第三个命令确定这两个用户是否可以登录 Lync Server 2013 并进行数据会议。</span><span class="sxs-lookup"><span data-stu-id="cd45d-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="cd45d-124">若要执行此任务，请调用**CsDataConference** cmdlet 以及以下参数： TargetFqdn （注册器池的 FQDN）;SenderSipAddress （第一个测试用户的 SIP 地址）;SenderCredential （包含此同一用户的凭据的 Windows PowerShell 对象）;ReceiverSipAddress （其他测试用户的 SIP 地址）;和 ReceiverCredential （包含其他测试用户的凭据的 Windows PowerShell 对象）。</span><span class="sxs-lookup"><span data-stu-id="cd45d-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cd45d-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="cd45d-125">Determining success or failure</span></span>

<span data-ttu-id="cd45d-126">如果正确配置了数据会议，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="cd45d-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="cd45d-127">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cd45d-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cd45d-128">结果：成功</span><span class="sxs-lookup"><span data-stu-id="cd45d-128">Result : Success</span></span>

<span data-ttu-id="cd45d-129">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="cd45d-129">Latency : 00:00:00</span></span>

<span data-ttu-id="cd45d-130">错误消息：</span><span class="sxs-lookup"><span data-stu-id="cd45d-130">Error Message :</span></span>

<span data-ttu-id="cd45d-131">诊断</span><span class="sxs-lookup"><span data-stu-id="cd45d-131">Diagnosis :</span></span>

<span data-ttu-id="cd45d-132">如果指定用户不能使用数据共享，则结果将显示为 "**失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="cd45d-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="cd45d-133">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="cd45d-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="cd45d-134">结果：失败</span><span class="sxs-lookup"><span data-stu-id="cd45d-134">Result : Failure</span></span>

<span data-ttu-id="cd45d-135">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="cd45d-135">Latency : 00:00:00</span></span>

<span data-ttu-id="cd45d-136">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="cd45d-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="cd45d-137">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="cd45d-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="cd45d-138">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="cd45d-138">established connection failed because connected host has</span></span>

<span data-ttu-id="cd45d-139">无法响应\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="cd45d-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="cd45d-140">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="cd45d-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="cd45d-141">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="cd45d-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="cd45d-142">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="cd45d-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="cd45d-143">未能响应</span><span class="sxs-lookup"><span data-stu-id="cd45d-143">has failed to respond</span></span>

<span data-ttu-id="cd45d-144">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="cd45d-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="cd45d-145">诊断</span><span class="sxs-lookup"><span data-stu-id="cd45d-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cd45d-146">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="cd45d-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="cd45d-147">以下是**测试 CsDataConference**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="cd45d-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="cd45d-148">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="cd45d-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="cd45d-149">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="cd45d-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="cd45d-150">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="cd45d-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="cd45d-151">执行数据会议的能力取决于已分配给组织会议的用户的会议策略（如果是**CsDataConference** cmdlet，则为 "sender"）。</span><span class="sxs-lookup"><span data-stu-id="cd45d-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="cd45d-152">如果不允许组织者在他或她的会议中包含协作活动（例如，如果其会议策略将 EnableDataCollaboration 属性设置为 False），则**CsDataConference** cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="cd45d-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="cd45d-153">如果边缘服务器配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="cd45d-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

