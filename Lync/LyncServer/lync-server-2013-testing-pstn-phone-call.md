---
title: 'Lync Server 2013: 测试 PSTN 电话呼叫'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="4d92a-102">在 Lync Server 2013 中测试 PSTN 电话呼叫</span><span class="sxs-lookup"><span data-stu-id="4d92a-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d92a-103">_**主题上次修改时间:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4d92a-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d92a-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="4d92a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4d92a-105">每天</span><span class="sxs-lookup"><span data-stu-id="4d92a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d92a-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="4d92a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4d92a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d92a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d92a-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="4d92a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4d92a-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="4d92a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4d92a-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsRegistration cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="4d92a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="4d92a-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="4d92a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4d92a-112">说明</span><span class="sxs-lookup"><span data-stu-id="4d92a-112">Description</span></span>

<span data-ttu-id="4d92a-113">CsPstnOutboundCall cmdlet 可测试用户拨打 PSTN 上的电话号码的功能的能力。</span><span class="sxs-lookup"><span data-stu-id="4d92a-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="4d92a-114">运行 Test CsPstnOutboundCall 时, cmdlet 首先尝试将测试用户登录到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="4d92a-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="4d92a-115">如果登录成功, 则 cmdlet 将尝试通过 PSTN 网关进行电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="4d92a-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="4d92a-116">此电话将使用拨号计划、语音策略以及分配给测试帐户的其他策略和设置进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="4d92a-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="4d92a-117">接听呼叫时, cmdlet 通过网络发送双音调多频率 (DTMF) 代码以验证媒体连接。</span><span class="sxs-lookup"><span data-stu-id="4d92a-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="4d92a-118">进行测试时, CsPstnOutboundCall 将进行实际的电话呼叫: 目标电话将响铃, 并且必须回答该测试才能成功。</span><span class="sxs-lookup"><span data-stu-id="4d92a-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="4d92a-119">此通话也必须由管理员手动结束。</span><span class="sxs-lookup"><span data-stu-id="4d92a-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4d92a-120">运行测试</span><span class="sxs-lookup"><span data-stu-id="4d92a-120">Running the test</span></span>

<span data-ttu-id="4d92a-121">CsPstnOutboundCall cmdlet 可以使用预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="4d92a-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="4d92a-122">若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的 FQDN 以及正在调用的 PSTN 电话号码。</span><span class="sxs-lookup"><span data-stu-id="4d92a-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="4d92a-123">例如：</span><span class="sxs-lookup"><span data-stu-id="4d92a-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="4d92a-124">若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="4d92a-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="4d92a-125">然后, 在调用 Test-CsPstnOutboundCall 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="4d92a-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="4d92a-126">有关详细信息, 请参阅[CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="4d92a-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4d92a-127">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="4d92a-127">Determining success or failure</span></span>

<span data-ttu-id="4d92a-128">如果指定的用户可以进行呼叫, 并且接听呼叫, 则会收到与此类似的输出, 结果属性标记为**成功:**</span><span class="sxs-lookup"><span data-stu-id="4d92a-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="4d92a-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d92a-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4d92a-130">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="4d92a-130">Result : Success</span></span>

<span data-ttu-id="4d92a-131">延迟:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="4d92a-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="4d92a-132">时发生</span><span class="sxs-lookup"><span data-stu-id="4d92a-132">Error :</span></span>

<span data-ttu-id="4d92a-133">自检</span><span class="sxs-lookup"><span data-stu-id="4d92a-133">Diagnosis :</span></span>

<span data-ttu-id="4d92a-134">如果指定的用户不能进行呼叫或不接听呼叫, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="4d92a-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4d92a-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d92a-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4d92a-136">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="4d92a-136">Result : Failure</span></span>

<span data-ttu-id="4d92a-137">延迟: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="4d92a-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="4d92a-138">错误: 403, "已禁止"</span><span class="sxs-lookup"><span data-stu-id="4d92a-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="4d92a-139">诊断: ErrorCode = 12001, Source = atl-litwareinc, Reason = User</span><span class="sxs-lookup"><span data-stu-id="4d92a-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="4d92a-140">策略不包含手机路线使用情况</span><span class="sxs-lookup"><span data-stu-id="4d92a-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="4d92a-141">以前的输出表明测试失败的原因是分配给指定用户的语音策略不包含电话使用。</span><span class="sxs-lookup"><span data-stu-id="4d92a-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="4d92a-142">(电话使用将语音策略与语音路线关联。</span><span class="sxs-lookup"><span data-stu-id="4d92a-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="4d92a-143">如果没有语音政策和相应的语音路线, 则不能通过 PSTN 进行呼叫。)</span><span class="sxs-lookup"><span data-stu-id="4d92a-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="4d92a-144">如果测试 CsPstnOutboundCall 失败, 您可能需要重新运行测试, 这一次包括 Verbose 参数:</span><span class="sxs-lookup"><span data-stu-id="4d92a-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="4d92a-145">当包含 Verbose 参数时, CsPstnOutboundCall 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="4d92a-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="4d92a-146">例如, 此输出表明网络问题阻止与 PSTN 的连接:</span><span class="sxs-lookup"><span data-stu-id="4d92a-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="4d92a-147">正在与 "sip: +12065551219@litwareinc.com; user = phone" 建立音频视频通话。</span><span class="sxs-lookup"><span data-stu-id="4d92a-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="4d92a-148">从网络收到了异常 ' A 404 (未找到) 响应, 操作失败。</span><span class="sxs-lookup"><span data-stu-id="4d92a-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4d92a-149">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="4d92a-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="4d92a-150">下面是测试 CsPstnOutboundCall 可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="4d92a-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="4d92a-151">您指定了无效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4d92a-151">You specified an invalid user account.</span></span> <span data-ttu-id="4d92a-152">你可以通过运行类似如下所示的命令来验证用户帐户是否存在:</span><span class="sxs-lookup"><span data-stu-id="4d92a-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="4d92a-153">用户帐户有效, 但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="4d92a-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="4d92a-154">若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:</span><span class="sxs-lookup"><span data-stu-id="4d92a-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="4d92a-155">如果 Enabled 属性设置为 False, 表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="4d92a-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="4d92a-156">分配给指定用户的语音策略没有有效的 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="4d92a-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="4d92a-157">你可以使用类似下面的命令确定分配给用户的语音策略:</span><span class="sxs-lookup"><span data-stu-id="4d92a-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="4d92a-158">然后, 你可以使用如下所示的命令确定分配给该策略的 PSTN 用途 (如果有), 该命令将检索有关每用户语音策略 RedmondVoicePolicy 的信息:</span><span class="sxs-lookup"><span data-stu-id="4d92a-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

