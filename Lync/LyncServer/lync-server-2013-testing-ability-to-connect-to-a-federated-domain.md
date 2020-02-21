---
title: Lync Server 2013：测试连接到联盟域的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ce7f6855e792b5edd339ee87f2955336a943615
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="b0bf2-102">从 Lync Server 2013 中连接到联盟域的测试能力</span><span class="sxs-lookup"><span data-stu-id="b0bf2-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0bf2-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b0bf2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0bf2-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="b0bf2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b0bf2-105">每天</span><span class="sxs-lookup"><span data-stu-id="b0bf2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0bf2-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="b0bf2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b0bf2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0bf2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0bf2-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="b0bf2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b0bf2-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b0bf2-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsFederatedPartner cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="b0bf2-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b0bf2-112">Description</span><span class="sxs-lookup"><span data-stu-id="b0bf2-112">Description</span></span>

<span data-ttu-id="b0bf2-113">Test-CsFederatedPartner 验证您能否连接到联盟伙伴的域。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="b0bf2-114">若要验证与某个域的连接，该域必须列在允许（联合）域的集合中。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="b0bf2-115">您可以使用以下命令检索 "允许的域" 列表中的域列表：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="b0bf2-116">有关详细信息，请参阅[CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b0bf2-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="b0bf2-117">Running the test</span></span>

<span data-ttu-id="b0bf2-118">FederatedPartner cmdlet 需要以下两条信息：边缘服务器的 FQDN 和联盟伙伴的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="b0bf2-119">例如，以下命令将测试连接到域 contoso.com 的能力：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="b0bf2-120">通过此命令，您可以测试与当前允许的域列表中的所有域的连接：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="b0bf2-121">有关详细信息，请参阅[CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b0bf2-122">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="b0bf2-122">Determining success or failure</span></span>

<span data-ttu-id="b0bf2-123">如果可以联系指定的域，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="b0bf2-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b0bf2-124">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b0bf2-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b0bf2-125">结果：成功</span><span class="sxs-lookup"><span data-stu-id="b0bf2-125">Result : Success</span></span>

<span data-ttu-id="b0bf2-126">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="b0bf2-126">Latency : 00:00:00</span></span>

<span data-ttu-id="b0bf2-127">误差</span><span class="sxs-lookup"><span data-stu-id="b0bf2-127">Error :</span></span>

<span data-ttu-id="b0bf2-128">诊断</span><span class="sxs-lookup"><span data-stu-id="b0bf2-128">Diagnosis :</span></span>

<span data-ttu-id="b0bf2-129">如果无法联系指定的域，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b0bf2-130">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b0bf2-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b0bf2-131">结果：失败</span><span class="sxs-lookup"><span data-stu-id="b0bf2-131">Result : Failure</span></span>

<span data-ttu-id="b0bf2-132">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="b0bf2-132">Latency : 00:00:00</span></span>

<span data-ttu-id="b0bf2-133">错误：504，服务器超时</span><span class="sxs-lookup"><span data-stu-id="b0bf2-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="b0bf2-134">诊断： ErrorCode = 2，Source = atl-cs-litwareinc，Reason = 参阅</span><span class="sxs-lookup"><span data-stu-id="b0bf2-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="b0bf2-135">响应代码和原因短语。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-135">response code and reason phrase.</span></span>

<span data-ttu-id="b0bf2-136">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="b0bf2-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="b0bf2-137">例如，以前的输出表明测试因服务器超时错误而失败。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="b0bf2-138">这通常指示网络连接问题或联系边缘服务器时出现问题。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="b0bf2-139">如果 CsFederatedPartner 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b0bf2-140">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="b0bf2-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="b0bf2-141">以下是测试 CsFederatedPartner 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="b0bf2-142">边缘服务器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-142">The Edge Server might not be available.</span></span> <span data-ttu-id="b0bf2-143">您可以使用以下命令来使用您的边缘服务器的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="b0bf2-144">然后，可以 ping 每台边缘服务器以验证是否可以通过网络访问它。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="b0bf2-145">例如：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="b0bf2-146">指定的域可能未列在允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="b0bf2-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="b0bf2-147">若要验证已添加到允许的域列表中的域，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="b0bf2-148">如果您想要查看阻止用户与之通信的域的列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="b0bf2-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

