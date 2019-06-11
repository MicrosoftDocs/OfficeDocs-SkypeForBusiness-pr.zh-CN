---
title: 'Lync Server 2013: 测试会议中的共享'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="c9024-102">在 Lync Server 2013 中测试会议中的共享</span><span class="sxs-lookup"><span data-stu-id="c9024-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9024-103">_**主题上次修改时间:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c9024-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9024-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="c9024-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c9024-105">每天</span><span class="sxs-lookup"><span data-stu-id="c9024-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9024-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="c9024-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c9024-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9024-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9024-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="c9024-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c9024-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="c9024-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c9024-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行<strong>CsDataConference</strong> cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c9024-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="c9024-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="c9024-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c9024-112">说明</span><span class="sxs-lookup"><span data-stu-id="c9024-112">Description</span></span>

<span data-ttu-id="c9024-113">在 Lync Server 2013 中, 数据会议是指使用协作活动 (如 whiteboarding 或批注) 的任何会议。</span><span class="sxs-lookup"><span data-stu-id="c9024-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="c9024-114">**CsDataConference** cmdlet 使你能够验证一对用户是否能够参与数据会议。</span><span class="sxs-lookup"><span data-stu-id="c9024-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c9024-115">运行测试</span><span class="sxs-lookup"><span data-stu-id="c9024-115">Running the test</span></span>

<span data-ttu-id="c9024-116">示例1中所示的命令验证是否可以在 pool atl-cs-001.litwareinc.com 上进行数据会议。</span><span class="sxs-lookup"><span data-stu-id="c9024-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c9024-117">此命令假设你为指定的池配置了一对测试用户。</span><span class="sxs-lookup"><span data-stu-id="c9024-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="c9024-118">如果不存在这样的测试用户, 该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="c9024-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="c9024-119">示例2中所示的命令将测试一对用户 (litwareinc\\pilar 和 litwareinc\\kenmyer) 的功能以登录 Lync Server 2013, 然后进行数据会议。</span><span class="sxs-lookup"><span data-stu-id="c9024-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="c9024-120">为此, 示例中的第一个命令使用**Get 凭据**Cmdlet 创建 Windows PowerShell 命令行界面凭据对象, 该对象包含用户 Pilar Ackerman 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="c9024-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="c9024-121">(因为登录名 (litwareinc\\pilar) 已包含为参数, 所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。)然后, 所生成的凭据对象将存储在名为 $cred 1 的变量中。</span><span class="sxs-lookup"><span data-stu-id="c9024-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="c9024-122">第二个命令执行相同操作, 这一次返回 Ken Myer 帐户的凭据对象。</span><span class="sxs-lookup"><span data-stu-id="c9024-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="c9024-123">使用凭据对象, 第三个命令确定这两个用户是否可以登录 Lync Server 2013 并进行数据会议。</span><span class="sxs-lookup"><span data-stu-id="c9024-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="c9024-124">若要执行此任务, **CsDataConference** cmdlet 与以下参数一起调用: TargetFqdn (注册机构池的 FQDN);SenderSipAddress (第一测试用户的 SIP 地址);SenderCredential (包含此同一用户的凭据的 Windows PowerShell 对象);ReceiverSipAddress (其他测试用户的 SIP 地址);和 ReceiverCredential (包含其他测试用户的凭据的 Windows PowerShell 对象)。</span><span class="sxs-lookup"><span data-stu-id="c9024-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c9024-125">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="c9024-125">Determining success or failure</span></span>

<span data-ttu-id="c9024-126">如果正确配置了数据会议, 则会收到与此类似的输出, 结果属性标记为**成功:**</span><span class="sxs-lookup"><span data-stu-id="c9024-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c9024-127">目标 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c9024-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c9024-128">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="c9024-128">Result : Success</span></span>

<span data-ttu-id="c9024-129">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c9024-129">Latency : 00:00:00</span></span>

<span data-ttu-id="c9024-130">错误消息:</span><span class="sxs-lookup"><span data-stu-id="c9024-130">Error Message :</span></span>

<span data-ttu-id="c9024-131">自检</span><span class="sxs-lookup"><span data-stu-id="c9024-131">Diagnosis :</span></span>

<span data-ttu-id="c9024-132">如果指定用户无法使用数据共享, 则结果将显示为 "**失败**", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="c9024-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c9024-133">目标 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c9024-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c9024-134">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="c9024-134">Result : Failure</span></span>

<span data-ttu-id="c9024-135">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c9024-135">Latency : 00:00:00</span></span>

<span data-ttu-id="c9024-136">错误消息: 10060, 连接尝试失败, 因为已连接的参与方</span><span class="sxs-lookup"><span data-stu-id="c9024-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c9024-137">在一段时间后未正确响应, 或者</span><span class="sxs-lookup"><span data-stu-id="c9024-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c9024-138">已建立连接失败, 因为连接的主机已</span><span class="sxs-lookup"><span data-stu-id="c9024-138">established connection failed because connected host has</span></span>

<span data-ttu-id="c9024-139">无法响应\[2001: 4898: e8: f39e: 5c9a: ad83: 81b3: 9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="c9024-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="c9024-140">内部异常: 连接尝试失败, 因为</span><span class="sxs-lookup"><span data-stu-id="c9024-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c9024-141">已连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="c9024-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c9024-142">时间, 或已建立的连接失败, 因为已连接的主机</span><span class="sxs-lookup"><span data-stu-id="c9024-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c9024-143">无法响应</span><span class="sxs-lookup"><span data-stu-id="c9024-143">has failed to respond</span></span>

<span data-ttu-id="c9024-144">\[2001: 4898: e8: f39e: 5c9a: ad83: 81b3: 9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="c9024-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="c9024-145">自检</span><span class="sxs-lookup"><span data-stu-id="c9024-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c9024-146">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="c9024-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="c9024-147">下面是**测试 CsDataConference**可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="c9024-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="c9024-148">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="c9024-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c9024-149">如果使用, 则必须正确配置可选参数, 否则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="c9024-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c9024-150">重新运行不带可选参数的命令, 并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="c9024-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c9024-151">执行数据会议的能力取决于已分配给组织会议的用户的会议策略 (在**CsDataConference** cmdlet 的情况下为 "sender")。</span><span class="sxs-lookup"><span data-stu-id="c9024-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="c9024-152">如果不允许组织者在其会议中包含协作活动 (例如, 如果其会议策略将 EnableDataCollaboration 属性设置为 False), 则**CsDataConference** cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="c9024-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="c9024-153">如果边缘服务器配置错误或尚未部署, 此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="c9024-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

