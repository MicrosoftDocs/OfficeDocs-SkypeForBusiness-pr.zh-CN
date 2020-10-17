---
title: Lync Server 2013：测试向智能手机发出的推送通知
description: Lync Server 2013：测试向智能手机发出的推送通知。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b92ef444a5331c9a673fd2db506631554e96eea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550838"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="46e5d-103">在 Lync Server 2013 中测试到智能手机的推送通知</span><span class="sxs-lookup"><span data-stu-id="46e5d-103">Test push notifications to smart phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e5d-104">_**上次修改的主题：** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="46e5d-104">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46e5d-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="46e5d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="46e5d-106">每月</span><span class="sxs-lookup"><span data-stu-id="46e5d-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e5d-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="46e5d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="46e5d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46e5d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e5d-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="46e5d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="46e5d-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="46e5d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="46e5d-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsMcxPushNotification cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="46e5d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="46e5d-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="46e5d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="46e5d-113">说明</span><span class="sxs-lookup"><span data-stu-id="46e5d-113">Description</span></span>

<span data-ttu-id="46e5d-114">推送通知服务 (Apple 推送通知服务和 Microsoft 推送通知服务) 可以向移动设备（如 Iphone 和 Windows phone）发送有关事件（如新即时消息或新语音邮件）的通知，即使这些设备上的 Lync 客户端当前已挂起或在后台运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="46e5d-114">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="46e5d-115">推送通知服务是在 Microsoft 服务器上运行的基于云的服务。</span><span class="sxs-lookup"><span data-stu-id="46e5d-115">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="46e5d-116">若要利用推送通知，必须能够连接到推送通知交换所，并对其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="46e5d-116">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="46e5d-117">通过 Test-CsMcxPushNotification cmdlet，管理员可以验证是否可以通过边缘服务器将推送通知请求路由到推送通知交换所。</span><span class="sxs-lookup"><span data-stu-id="46e5d-117">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="46e5d-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="46e5d-118">Running the test</span></span>

<span data-ttu-id="46e5d-119">若要测试推送通知服务，请调用 Test-CsMcxPushNotification cmdlet。</span><span class="sxs-lookup"><span data-stu-id="46e5d-119">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="46e5d-120">请确保指定边缘服务器的完全限定域名：</span><span class="sxs-lookup"><span data-stu-id="46e5d-120">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="46e5d-121">有关详细信息，请参阅 [CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="46e5d-121">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="46e5d-122">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="46e5d-122">Determining success or failure</span></span>

<span data-ttu-id="46e5d-123">如果 Test-CsMcxPushNotification 成功，cmdlet 将返回测试结果成功：</span><span class="sxs-lookup"><span data-stu-id="46e5d-123">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="46e5d-124">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="46e5d-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="46e5d-125">结果：成功</span><span class="sxs-lookup"><span data-stu-id="46e5d-125">Result : Success</span></span>

<span data-ttu-id="46e5d-126">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="46e5d-126">Latency : 00:00:00</span></span>

<span data-ttu-id="46e5d-127">误差</span><span class="sxs-lookup"><span data-stu-id="46e5d-127">Error :</span></span>

<span data-ttu-id="46e5d-128">诊断</span><span class="sxs-lookup"><span data-stu-id="46e5d-128">Diagnosis :</span></span>

<span data-ttu-id="46e5d-129">如果 Test-CsMcxPushNotification 无法连接到推送通知交换所，则 cmdlet 通常不会返回失败的测试结果。</span><span class="sxs-lookup"><span data-stu-id="46e5d-129">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="46e5d-130">相反，命令通常会完全失败。</span><span class="sxs-lookup"><span data-stu-id="46e5d-130">Instead the command will usually fail completely.</span></span> <span data-ttu-id="46e5d-131">例如：</span><span class="sxs-lookup"><span data-stu-id="46e5d-131">For example:</span></span>

<span data-ttu-id="46e5d-132">Test-CsMcxPushNotification：从网络收到 504 (服务器超时) 响应，操作失败。</span><span class="sxs-lookup"><span data-stu-id="46e5d-132">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="46e5d-133">有关详细信息，请参阅异常详细信息。</span><span class="sxs-lookup"><span data-stu-id="46e5d-133">See the exception details for more information.</span></span>

<span data-ttu-id="46e5d-134">位于行：1个字符：27</span><span class="sxs-lookup"><span data-stu-id="46e5d-134">At line:1 char:27</span></span>

<span data-ttu-id="46e5d-135">\+Test-CsMcxPushNotification \< \< \< \< AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="46e5d-135">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="46e5d-136">\+ CategoryInfo： OperationStopped： (： ) \[ Test-CsMcxPushNotification \] 、FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="46e5d-136">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="46e5d-137">\+ FullyQualifiedErrorId： WorkflowNotCompleted，SyntheticTransactions。 TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="46e5d-137">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="46e5d-138">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="46e5d-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="46e5d-139">如果推送通知服务失败，通常表明与边缘服务器通信时出现问题，或者与推送通知交换所进行通信时出现问题。</span><span class="sxs-lookup"><span data-stu-id="46e5d-139">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="46e5d-140">如果您在运行 CsMcxPushNotification 时遇到问题，您应执行的第一件事是验证您的边缘服务器是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="46e5d-140">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="46e5d-141">执行此操作的一种方法是使用 Test-CsAVEdgeConnectivity cmdlet：</span><span class="sxs-lookup"><span data-stu-id="46e5d-141">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="46e5d-142">此检查将验证指定的用户是否可以连接到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="46e5d-142">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="46e5d-143">如果边缘服务器看起来正常运行，这通常意味着您无法连接到推送通知 clearinghouse。</span><span class="sxs-lookup"><span data-stu-id="46e5d-143">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="46e5d-144">反过来，这通常意味着您尚未正确配置 clearinghouse URI，或者您没有指向此 URL 的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="46e5d-144">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="46e5d-145">您可以通过运行以下命令来验证 URI 是否已设置为正确的值 (sip:push@push.lync.com) ：</span><span class="sxs-lookup"><span data-stu-id="46e5d-145">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="46e5d-146">如果将 PushNotificationProxyUri 属性设置为 sip:push@push.lync.com 以外的任何其他属性，则可以使用 Set-McxConfiguration cmdlet 纠正该问题。</span><span class="sxs-lookup"><span data-stu-id="46e5d-146">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="46e5d-147">例如，以下命令将在整个组织中正确设置 URI：</span><span class="sxs-lookup"><span data-stu-id="46e5d-147">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="46e5d-148">有关详细信息，请参阅 [CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="46e5d-148">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="46e5d-149">如果 URI 配置正确，下一步应验证您是否具有解析为您的 SIP 域和边缘服务器的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="46e5d-149">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="46e5d-150">有关如何配置这些记录的详细信息，请参阅移动性的帮助主题 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="46e5d-150">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="46e5d-151">请注意，以下错误消息通常表明 DNS 记录存在问题：</span><span class="sxs-lookup"><span data-stu-id="46e5d-151">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="46e5d-152">从网络收到 504 (服务器超时) 响应，操作失败。</span><span class="sxs-lookup"><span data-stu-id="46e5d-152">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="46e5d-153">有关详细信息，请参阅异常详细信息。</span><span class="sxs-lookup"><span data-stu-id="46e5d-153">See the exception details for more information.</span></span>

<span data-ttu-id="46e5d-154">此外，Test-CsMcxConfiguration 也可能会失败，并出现以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="46e5d-154">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="46e5d-155">Test-CsMcxPushNotification：推送通知请求被拒绝。</span><span class="sxs-lookup"><span data-stu-id="46e5d-155">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="46e5d-156">位于行：1个字符：27</span><span class="sxs-lookup"><span data-stu-id="46e5d-156">At line:1 char:27</span></span>

<span data-ttu-id="46e5d-157">\+ Test-CsMcxPushNotification \<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="46e5d-157">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="46e5d-158">\+ CategoryInfo： OperationStopped： (： ) \[ Test-CsMcxPushNotification \] 、SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="46e5d-158">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="46e5d-159">\+ FullyQualifiedErrorId： WorkflowNotCompleted，SyntheticTransactions。 TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="46e5d-159">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="46e5d-160">如果启用了 URL 筛选并阻止了 http：和 https：前缀，则通常会出现 "推送通知请求被拒绝" 消息。</span><span class="sxs-lookup"><span data-stu-id="46e5d-160">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="46e5d-161">您可以使用类似如下的命令来确定要阻止的前缀：</span><span class="sxs-lookup"><span data-stu-id="46e5d-161">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="46e5d-162">如果结果中出现 "http：" 或 "https："，则必须将其从 "阻止的前缀" 列表中删除，才能使用推送通知。</span><span class="sxs-lookup"><span data-stu-id="46e5d-162">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="46e5d-163">可以通过使用与以下命令类似的命令来实现：</span><span class="sxs-lookup"><span data-stu-id="46e5d-163">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="46e5d-164">有关详细信息，请参阅 [CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="46e5d-164">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

