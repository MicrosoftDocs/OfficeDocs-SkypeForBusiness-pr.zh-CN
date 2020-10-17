---
title: Lync Server 2013：测试观察程序节点配置
description: Lync Server 2013：测试观察程序节点配置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546838"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="323ef-103">在 Lync Server 2013 中测试观察程序节点配置</span><span class="sxs-lookup"><span data-stu-id="323ef-103">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="323ef-104">_**上次修改的主题：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="323ef-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="323ef-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="323ef-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="323ef-106">每天</span><span class="sxs-lookup"><span data-stu-id="323ef-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="323ef-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="323ef-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="323ef-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="323ef-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="323ef-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="323ef-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="323ef-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="323ef-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="323ef-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>new-cswatchernodeconfiguration</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="323ef-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="323ef-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="323ef-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="323ef-113">说明</span><span class="sxs-lookup"><span data-stu-id="323ef-113">Description</span></span>

<span data-ttu-id="323ef-114">如果您使用 Microsoft System Center Operations Manager 来监视 Lync Server 2013，则可以选择设置 "观察程序节点"：定期和自动运行综合事务以验证 Lync Server 是否按预期方式工作的计算机。</span><span class="sxs-lookup"><span data-stu-id="323ef-114">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="323ef-115">观察程序节点分配给池，并通过使用 **new-cswatchernodeconfiguration** cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="323ef-115">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="323ef-116">请注意，如果正在使用 System Center Operations Manager，那么无需安装观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="323ef-116">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="323ef-117">您仍可以在不使用观察程序节点的情况下监视系统。</span><span class="sxs-lookup"><span data-stu-id="323ef-117">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="323ef-118">唯一的区别在于，要运行的任何合成事务都必须手动调用，而不是由 Operations Manager 自动调用。</span><span class="sxs-lookup"><span data-stu-id="323ef-118">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="323ef-119">**New-cswatchernodeconfiguration** cmdlet 使您能够验证是否已正确配置观察程序节点，并将其分配给有效的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="323ef-119">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="323ef-120">请注意，必须在观察程序节点本身上运行 **new-cswatchernodeconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="323ef-120">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="323ef-121">无法对远程计算机运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="323ef-121">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="323ef-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="323ef-122">Running the test</span></span>

<span data-ttu-id="323ef-123">以下命令验证组织中使用的每个观察程序节点的配置设置。</span><span class="sxs-lookup"><span data-stu-id="323ef-123">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="323ef-124">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="323ef-124">Determining success or failure</span></span>

<span data-ttu-id="323ef-125">以下成功的示例输出显示了具有四台边缘服务器的系统。</span><span class="sxs-lookup"><span data-stu-id="323ef-125">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="323ef-126">对照拓扑验证目标池 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="323ef-126">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="323ef-127">成功：拓扑中存在目标池 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="323ef-127">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="323ef-128">成功：目标池 atl-cs-001.litwareinc.com 已安装注册器角色。</span><span class="sxs-lookup"><span data-stu-id="323ef-128">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="323ef-129">成功：目标池 atl-cs-001.litwareinc.com 是受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="323ef-129">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="323ef-130">成功：5061目标池 atl-cs-001.litwareinc.com 的端口号正确。</span><span class="sxs-lookup"><span data-stu-id="323ef-130">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="323ef-131">已启动在观察程序节点配置中检查缺少的池。</span><span class="sxs-lookup"><span data-stu-id="323ef-131">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="323ef-132">如果检测到任何错误，则会将其打印出来。</span><span class="sxs-lookup"><span data-stu-id="323ef-132">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="323ef-133">在观察程序节点配置中检查缺少的池已完成。</span><span class="sxs-lookup"><span data-stu-id="323ef-133">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="323ef-134">已启动对观察程序节点安装创建的观察程序节点注册表项的检查。</span><span class="sxs-lookup"><span data-stu-id="323ef-134">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="323ef-135">如果检测到任何错误，则会将其打印出来。</span><span class="sxs-lookup"><span data-stu-id="323ef-135">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="323ef-136">检查由观察程序节点安装创建的观察程序节点注册表项是否已完成。</span><span class="sxs-lookup"><span data-stu-id="323ef-136">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="323ef-137">检测到的身份验证类型为 "协商"。</span><span class="sxs-lookup"><span data-stu-id="323ef-137">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="323ef-138">已成功验证测试用户的凭据 sip 是否存在： user1@ atl-cs-001.litwareinc.com in credential management store。</span><span class="sxs-lookup"><span data-stu-id="323ef-138">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="323ef-139">已成功验证测试用户的凭据 sip 是否存在： user2@ atl-cs-001.litwareinc.com in credential management store。</span><span class="sxs-lookup"><span data-stu-id="323ef-139">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="323ef-140">已启动在观察程序节点配置中检查缺少的池。</span><span class="sxs-lookup"><span data-stu-id="323ef-140">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="323ef-141">如果检测到任何错误，则会将其打印出来。</span><span class="sxs-lookup"><span data-stu-id="323ef-141">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="323ef-142">警告：池 atl-cs-001.litwareinc.com 具有注册器</span><span class="sxs-lookup"><span data-stu-id="323ef-142">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="323ef-143">已安装角色，但没有为其配置的测试用户。</span><span class="sxs-lookup"><span data-stu-id="323ef-143">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="323ef-144">在观察程序节点配置中检查缺少的池已完成。</span><span class="sxs-lookup"><span data-stu-id="323ef-144">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="323ef-145">检查由观察程序节点安装所创建的观察程序节点注册表项是</span><span class="sxs-lookup"><span data-stu-id="323ef-145">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="323ef-146">启动.</span><span class="sxs-lookup"><span data-stu-id="323ef-146">started.</span></span> <span data-ttu-id="323ef-147">如果检测到任何错误，则会将其打印出来。</span><span class="sxs-lookup"><span data-stu-id="323ef-147">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="323ef-148">Test-CsWatcherNodeConfiguration：在中找不到运行状况注册表项</span><span class="sxs-lookup"><span data-stu-id="323ef-148">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="323ef-149">\\Microsoft \\ 实时通信的软件。</span><span class="sxs-lookup"><span data-stu-id="323ef-149">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="323ef-150">请确保观察程序节点 .msi 是</span><span class="sxs-lookup"><span data-stu-id="323ef-150">Make sure watcher node .msi is</span></span>

<span data-ttu-id="323ef-151">正确安装。</span><span class="sxs-lookup"><span data-stu-id="323ef-151">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="323ef-152">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="323ef-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="323ef-153">以下是 **测试 new-cswatchernodeconfiguration** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="323ef-153">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="323ef-154">未正确安装观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="323ef-154">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="323ef-155">未配置任何测试用户。</span><span class="sxs-lookup"><span data-stu-id="323ef-155">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="323ef-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="323ef-156">See Also</span></span>


[<span data-ttu-id="323ef-157">New-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="323ef-157">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="323ef-158">新 New-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="323ef-158">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="323ef-159">New-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="323ef-159">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="323ef-160">New-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="323ef-160">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

