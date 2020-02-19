---
title: Lync Server 2013：测试到 Lync 通知的 Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f192d71bbe36bd4e417c06e93152858ac761ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="ec247-102">在 Lync Server 2013 中测试 Exchange to Lync 通知</span><span class="sxs-lookup"><span data-stu-id="ec247-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec247-103">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ec247-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec247-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="ec247-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ec247-105">每天</span><span class="sxs-lookup"><span data-stu-id="ec247-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec247-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="ec247-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ec247-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec247-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec247-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="ec247-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ec247-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="ec247-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ec247-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsExStorageNotification</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ec247-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="ec247-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ec247-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ec247-112">说明</span><span class="sxs-lookup"><span data-stu-id="ec247-112">Description</span></span>

<span data-ttu-id="ec247-113">**CsExStorageNotification** cmdlet 用于验证 Microsoft Exchange Server 2013 通知服务是否可以在任何时候对用户的联系人列表进行更新时通知 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ec247-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="ec247-114">此 cmdlet 仅在使用统一联系人存储库时才有效。</span><span class="sxs-lookup"><span data-stu-id="ec247-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ec247-115">运行测试</span><span class="sxs-lookup"><span data-stu-id="ec247-115">Running the test</span></span>

<span data-ttu-id="ec247-116">示例1测试中显示的命令，用于查看 Lync Server Storage Service 是否可以连接到 Microsoft Exchange Server 邮箱通知服务，以供用户 sip:kenmyer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ec247-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="ec247-117">在此示例中，将 NetNamedPipe 用作 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="ec247-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ec247-118">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="ec247-118">Determining success or failure</span></span>

<span data-ttu-id="ec247-119">如果已正确配置 Exchange 集成，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功**：</span><span class="sxs-lookup"><span data-stu-id="ec247-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="ec247-120">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec247-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec247-121">结果：成功</span><span class="sxs-lookup"><span data-stu-id="ec247-121">Result : Success</span></span>

<span data-ttu-id="ec247-122">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec247-122">Latency : 00:00:00</span></span>

<span data-ttu-id="ec247-123">错误消息：</span><span class="sxs-lookup"><span data-stu-id="ec247-123">Error Message :</span></span>

<span data-ttu-id="ec247-124">诊断</span><span class="sxs-lookup"><span data-stu-id="ec247-124">Diagnosis :</span></span>

<span data-ttu-id="ec247-125">如果指定的用户无法接收通知，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="ec247-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ec247-126">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec247-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec247-127">结果：失败</span><span class="sxs-lookup"><span data-stu-id="ec247-127">Result : Failure</span></span>

<span data-ttu-id="ec247-128">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec247-128">Latency : 00:00:00</span></span>

<span data-ttu-id="ec247-129">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="ec247-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ec247-130">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="ec247-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ec247-131">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="ec247-131">established connection failed because connected host has</span></span>

<span data-ttu-id="ec247-132">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="ec247-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ec247-133">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="ec247-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ec247-134">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="ec247-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ec247-135">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="ec247-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ec247-136">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="ec247-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ec247-137">诊断</span><span class="sxs-lookup"><span data-stu-id="ec247-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ec247-138">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="ec247-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="ec247-139">以下是**测试 CsExStorageNotification**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="ec247-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="ec247-140">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="ec247-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ec247-141">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="ec247-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ec247-142">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="ec247-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ec247-143">如果 Microsoft Exchange Server 配置不正确或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ec247-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec247-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec247-144">See Also</span></span>


[<span data-ttu-id="ec247-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="ec247-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

