---
title: Lync Server 2013：测试服务激活和组权限
description: Lync Server 2013：测试服务激活和组权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116cf939f3110616ce395eb14c7945890bdb89b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556258"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="48c1f-103">在 Lync Server 2013 中测试服务激活和组权限</span><span class="sxs-lookup"><span data-stu-id="48c1f-103">Testing service activation and group permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c1f-104">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="48c1f-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48c1f-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="48c1f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="48c1f-106">每天</span><span class="sxs-lookup"><span data-stu-id="48c1f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48c1f-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="48c1f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="48c1f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48c1f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48c1f-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="48c1f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="48c1f-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="48c1f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="48c1f-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsTopology cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="48c1f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="48c1f-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="48c1f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="48c1f-113">说明</span><span class="sxs-lookup"><span data-stu-id="48c1f-113">Description</span></span>

<span data-ttu-id="48c1f-114">通过 Test-CsTopology cmdlet，您可以验证 Lync Server 2013 在全局范围内是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="48c1f-114">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="48c1f-115">默认情况下，此 cmdlet 会检查整个 Lync Server 基础结构，验证所需的服务是否正在运行，以及是否为这些服务以及在安装 Lync Server 时创建的通用安全组设置了适当的权限。</span><span class="sxs-lookup"><span data-stu-id="48c1f-115">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="48c1f-116">除了验证 Lync Server 安装的有效性，Test-CsTopology 还允许您检查特定服务的有效性。</span><span class="sxs-lookup"><span data-stu-id="48c1f-116">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="48c1f-117">例如，以下命令将检查池 atl-cs-001.litwareinc.com 上的 A/V 会议服务器的状态：</span><span class="sxs-lookup"><span data-stu-id="48c1f-117">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="48c1f-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="48c1f-118">Running the test</span></span>

<span data-ttu-id="48c1f-119">默认情况下，Test-CsTopology 在屏幕上显示很小的输出。</span><span class="sxs-lookup"><span data-stu-id="48c1f-119">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="48c1f-120">相反，cmdlet 返回的信息将写入到 HTML 文件中。</span><span class="sxs-lookup"><span data-stu-id="48c1f-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="48c1f-121">Report 参数允许您为由 Enable-cstopology 生成的 HTML 文件指定文件路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="48c1f-121">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="48c1f-122">如果不包含 Report 参数，则 HTML 文件将自动保存到用户文件夹中，并将其命名为如下所示的名称： ce84964a-c4da-4622-ad34-c54ff3ed361f.html。</span><span class="sxs-lookup"><span data-stu-id="48c1f-122">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="48c1f-123">下面的示例命令将运行 Test-CsTopology，并将输出保存到名为 C： \\ LogsComputerTest.html 的文件中 \\ ：</span><span class="sxs-lookup"><span data-stu-id="48c1f-123">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="48c1f-124">有关详细信息，请参阅 [enable-cstopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="48c1f-124">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="48c1f-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="48c1f-125">Determining success or failure</span></span>

<span data-ttu-id="48c1f-126">与大多数测试 cmdlet 不同的是，Test-CsTopology 会报告回退成功或失败。</span><span class="sxs-lookup"><span data-stu-id="48c1f-126">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="48c1f-127">部分，这是因为每次运行 cmdlet 时都必须执行大量的验证检查。</span><span class="sxs-lookup"><span data-stu-id="48c1f-127">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="48c1f-128">而是将数据保存到 HTML 报告，然后可以使用 Internet Explorer 进行查看。</span><span class="sxs-lookup"><span data-stu-id="48c1f-128">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="48c1f-129">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="48c1f-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="48c1f-130">下面是 Test-CsTopology 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="48c1f-130">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="48c1f-131">测试计算机上的复制可能不是最新的。</span><span class="sxs-lookup"><span data-stu-id="48c1f-131">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="48c1f-132">您可以通过运行 Get-CsManagementStoreReplicationStatus cmdlet 来检查计算机的当前复制状态：</span><span class="sxs-lookup"><span data-stu-id="48c1f-132">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="48c1f-133">如果复制状态不是最新的，则可以使用类似如下的命令手动强制执行复制：</span><span class="sxs-lookup"><span data-stu-id="48c1f-133">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="48c1f-134">可能必须启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="48c1f-134">The topology might have to be enabled.</span></span> <span data-ttu-id="48c1f-135">如果更改了 Lync Server 拓扑 (可能会影响本地计算机) 的更改，则必须启用新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="48c1f-135">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="48c1f-136">可以通过运行以下命令随时启用拓扑：</span><span class="sxs-lookup"><span data-stu-id="48c1f-136">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

