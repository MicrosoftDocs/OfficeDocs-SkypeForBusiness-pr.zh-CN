---
title: Lync Server 2013：测试 PSTN 对等呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="b368f-102">在 Lync Server 2013 中测试 PSTN 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="b368f-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b368f-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b368f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b368f-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="b368f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b368f-105">每天</span><span class="sxs-lookup"><span data-stu-id="b368f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b368f-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="b368f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b368f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b368f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b368f-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="b368f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b368f-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="b368f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b368f-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsPstnPeerToPeerCall cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b368f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="b368f-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b368f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b368f-112">说明</span><span class="sxs-lookup"><span data-stu-id="b368f-112">Description</span></span>

<span data-ttu-id="b368f-113">CsPstnPeerToPeerCall cmdlet 验证一对用户必须通过公共交换电话网络（PSTN）网关进行对等呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="b368f-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="b368f-114">当你调用 CsPstnPeerToPeerCall 时，cmdlet 将首先尝试登录到 Lync Server 的两个测试用户。</span><span class="sxs-lookup"><span data-stu-id="b368f-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="b368f-115">如果登录成功，此 cmdlet 将使用户1尝试通过 PSTN 网关调用用户2。</span><span class="sxs-lookup"><span data-stu-id="b368f-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="b368f-116">CsPstnPeerToPeerCall 将使用分配给测试用户的拨号计划、语音策略和其他策略和配置设置进行此呼叫。</span><span class="sxs-lookup"><span data-stu-id="b368f-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="b368f-117">如果测试按计划进行，cmdlet 将验证用户2是否能够接听呼叫，然后从系统中注销两个测试帐户。</span><span class="sxs-lookup"><span data-stu-id="b368f-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="b368f-118">Test-CsPstnPeerToPeerCall 进行实际的电话通话，一个验证是否可以建立连接，并且还通过网络传输 DTMF 代码以确定是否可以通过连接发送媒体。</span><span class="sxs-lookup"><span data-stu-id="b368f-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="b368f-119">呼叫由 cmdlet 本身应答，并且不需要手动终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="b368f-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="b368f-120">（也就是说，没有人必须回答，然后挂断呼叫的电话。）</span><span class="sxs-lookup"><span data-stu-id="b368f-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b368f-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="b368f-121">Running the test</span></span>

<span data-ttu-id="b368f-122">CsPstnPeerToPeerCall cmdlet 可以使用一对预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何两个用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="b368f-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="b368f-123">若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b368f-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="b368f-124">例如：</span><span class="sxs-lookup"><span data-stu-id="b368f-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="b368f-125">若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。</span><span class="sxs-lookup"><span data-stu-id="b368f-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="b368f-126">然后，当你调用 Test-CsPstnPeerToPeerCall 时，你必须包含这些凭据对象和两个帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="b368f-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="b368f-127">有关详细信息，请参阅[CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="b368f-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b368f-128">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="b368f-128">Determining success or failure</span></span>

<span data-ttu-id="b368f-129">如果指定的用户可以完成对等呼叫，你将收到与此类似的输出，结果属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="b368f-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b368f-130">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b368f-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b368f-131">结果：成功</span><span class="sxs-lookup"><span data-stu-id="b368f-131">Result : Success</span></span>

<span data-ttu-id="b368f-132">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="b368f-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="b368f-133">时发生</span><span class="sxs-lookup"><span data-stu-id="b368f-133">Error :</span></span>

<span data-ttu-id="b368f-134">自检</span><span class="sxs-lookup"><span data-stu-id="b368f-134">Diagnosis :</span></span>

<span data-ttu-id="b368f-135">如果指定用户无法完成对等呼叫，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="b368f-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b368f-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b368f-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b368f-137">结果：失败</span><span class="sxs-lookup"><span data-stu-id="b368f-137">Result : Failure</span></span>

<span data-ttu-id="b368f-138">延迟：00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="b368f-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="b368f-139">错误：403，"已禁止"</span><span class="sxs-lookup"><span data-stu-id="b368f-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="b368f-140">诊断： ErrorCode = 12001，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="b368f-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="b368f-141">原因 = 用户策略不包含手机路线使用情况</span><span class="sxs-lookup"><span data-stu-id="b368f-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="b368f-142">以前的输出表明测试未成功，因为分配给至少一个指定用户的语音策略不包含电话用途。</span><span class="sxs-lookup"><span data-stu-id="b368f-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="b368f-143">（电话使用将语音策略与语音路线关联。</span><span class="sxs-lookup"><span data-stu-id="b368f-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="b368f-144">如果没有语音策略和相应的语音路由，则不能通过 PSTN 进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="b368f-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="b368f-145">如果 CsPstnPeerToPeerCall 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="b368f-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="b368f-146">当包含 Verbose 参数时，CsPstnPeerToPeerCall 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="b368f-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="b368f-147">例如，此输出表明网络问题阻止与 PSTN 的连接：</span><span class="sxs-lookup"><span data-stu-id="b368f-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="b368f-148">建立对 "sip： + 12065551219@litwareinc .com" 的音频视频通话; 用户 = phone "。</span><span class="sxs-lookup"><span data-stu-id="b368f-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="b368f-149">从网络收到了异常 ' A 404 （未找到）响应，操作失败。</span><span class="sxs-lookup"><span data-stu-id="b368f-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b368f-150">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="b368f-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="b368f-151">下面是测试 CsPstnPeerToPeerCall 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="b368f-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="b368f-152">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="b368f-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="b368f-153">你可以通过运行类似如下所示的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="b368f-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b368f-154">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="b368f-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b368f-155">若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="b368f-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b368f-156">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="b368f-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="b368f-157">分配给指定用户的语音策略没有有效的 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="b368f-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="b368f-158">你可以使用类似下面的命令确定分配给用户的语音策略：</span><span class="sxs-lookup"><span data-stu-id="b368f-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="b368f-159">然后，你可以使用如下所示的命令确定分配给该策略的 PSTN 用途（如果有），该命令将检索有关每用户语音策略 RedmondVoicePolicy 的信息：</span><span class="sxs-lookup"><span data-stu-id="b368f-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

