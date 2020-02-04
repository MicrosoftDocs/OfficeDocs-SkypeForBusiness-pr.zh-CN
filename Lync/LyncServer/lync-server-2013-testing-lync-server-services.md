---
title: Lync Server 2013：测试 Lync Server 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdafd84f5a8edd21d6e62433d028ed735e37a37d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="7a575-102">在 Lync Server 2013 中测试 Lync Server 服务</span><span class="sxs-lookup"><span data-stu-id="7a575-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a575-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7a575-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a575-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="7a575-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7a575-105">每天</span><span class="sxs-lookup"><span data-stu-id="7a575-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a575-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="7a575-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7a575-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a575-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a575-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="7a575-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7a575-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="7a575-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7a575-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsComputer cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7a575-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="7a575-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7a575-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7a575-112">说明</span><span class="sxs-lookup"><span data-stu-id="7a575-112">Description</span></span>

<span data-ttu-id="7a575-113">测试 CsComputer 验证本地计算机上运行的所有 Lync Server 2013 服务的状态。</span><span class="sxs-lookup"><span data-stu-id="7a575-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="7a575-114">（测试 CsComputer 只能在本地运行，不能从 Windows PowerShell 的远程实例运行。）该 cmdlet 还检查是否在计算机上打开相应的防火墙端口，并确定安装 Lync Server 2013 时创建的 Active Directory 组是否已添加到相应的本地组。</span><span class="sxs-lookup"><span data-stu-id="7a575-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="7a575-115">例如，CsComputer 将验证 Active Directory 组 RTCUniversalUserAdmins 是否已添加到管理员组。</span><span class="sxs-lookup"><span data-stu-id="7a575-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="7a575-116">有关详细信息，请参阅[CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="7a575-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7a575-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="7a575-117">Running the test</span></span>

<span data-ttu-id="7a575-118">CsComputer cmdlet 只能在本地计算机上运行，因此不能从 Windows PowerShell 的远程实例调用 Test CsComputer。</span><span class="sxs-lookup"><span data-stu-id="7a575-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="7a575-119">默认情况下，CsComputer 在屏幕上显示非常少的输出，而由 cmdlet 返回的信息将写入 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="7a575-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7a575-120">因此，我们建议你在运行 Test CsComputer 时随时包括 Verbose 参数和 Report 参数。</span><span class="sxs-lookup"><span data-stu-id="7a575-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="7a575-121">在运行 cmdlet 时，Verbose 参数将在屏幕上提供稍有更详细的输出。</span><span class="sxs-lookup"><span data-stu-id="7a575-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="7a575-122">Report 参数允许你为由 Test CsComputer 生成的 HTML 文件指定文件路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="7a575-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="7a575-123">如果不包含报表参数，则 HTML 文件将自动保存到 "用户" 文件夹，并获得类似于以下内容的名称： ce84964a-c4da-4622-ad34-c54ff3ed361f。</span><span class="sxs-lookup"><span data-stu-id="7a575-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7a575-124">以下示例命令运行 Test-CsComputer 并将输出保存到名为 C：\\Logs\\ComputerTest 的文件中：</span><span class="sxs-lookup"><span data-stu-id="7a575-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="7a575-125">有关详细信息，请参阅[CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="7a575-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7a575-126">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="7a575-126">Determining success or failure</span></span>

<span data-ttu-id="7a575-127">由于执行的验证检查次数，CsComputer 不会报告简单的 **"是"、"测试成功**" 或 "**否"，测试失败**。</span><span class="sxs-lookup"><span data-stu-id="7a575-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="7a575-128">而是必须通过使用 Internet Explorer 确定每个测试的成功或失败来查看生成的 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="7a575-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7a575-129">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="7a575-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="7a575-130">下面是测试 CsComputer 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="7a575-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="7a575-131">测试计算机可能未启用，无法与 Lync Server 配合使用。</span><span class="sxs-lookup"><span data-stu-id="7a575-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="7a575-132">如果计算机上的 Lync Server 服务或服务器角色已更改且 CsComputer cmdlet 未运行，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7a575-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="7a575-133">若要解决此问题，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7a575-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="7a575-134">测试计算机上的复制可能不是最新的。</span><span class="sxs-lookup"><span data-stu-id="7a575-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="7a575-135">你可以通过运行 CsManagementStoreReplicationStatus cmdlet 检查计算机的当前复制状态：</span><span class="sxs-lookup"><span data-stu-id="7a575-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="7a575-136">如果复制状态不是最新，则可以通过使用类似下面的命令手动强制执行复制：</span><span class="sxs-lookup"><span data-stu-id="7a575-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="7a575-137">可能必须启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="7a575-137">The topology might have to be enabled.</span></span> <span data-ttu-id="7a575-138">如果更改 Lync Server 拓扑（可能会影响本地计算机的更改），则必须启用新拓扑。</span><span class="sxs-lookup"><span data-stu-id="7a575-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="7a575-139">可以通过运行以下命令随时启用拓扑：</span><span class="sxs-lookup"><span data-stu-id="7a575-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

