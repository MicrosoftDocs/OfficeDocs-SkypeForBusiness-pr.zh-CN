---
title: Lync Server 2013： Lync PreCall 诊断工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="77a13-102">Lync Server 2013 中的 lync PreCall 诊断工具</span><span class="sxs-lookup"><span data-stu-id="77a13-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77a13-103">_**主题上次修改时间：** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="77a13-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="77a13-104">Lync PreCall 诊断工具（PCD）是基于客户端的应用程序，可让你查看网络的当前状态如何影响未来的企业语音通话中的音频质量。</span><span class="sxs-lookup"><span data-stu-id="77a13-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="77a13-105">在网络的最后一个跃点可能是最弱的情况下（例如，在公共 WiFi 网络或家庭用户上使用膝上型电脑），PCD 非常有用。</span><span class="sxs-lookup"><span data-stu-id="77a13-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="77a13-106">PCD 创建一个小型数据包流，该流遍历网络的这最后一条路。</span><span class="sxs-lookup"><span data-stu-id="77a13-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="77a13-107">然后，该工具将分析数据包流，以估计沿此段腿的抖动和损失可能会影响呼叫质量，然后提供报告。</span><span class="sxs-lookup"><span data-stu-id="77a13-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="77a13-108">你可以在客户端上持续运行 PCD，即使在通话时也是如此。</span><span class="sxs-lookup"><span data-stu-id="77a13-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="77a13-109">数据包流对带宽没有显著影响。</span><span class="sxs-lookup"><span data-stu-id="77a13-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="77a13-110">**PCD 版本1.1 的最新版本包括以下增强功能：**</span><span class="sxs-lookup"><span data-stu-id="77a13-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="77a13-111">支持较长的密码，该密码现在最多可达127个字符</span><span class="sxs-lookup"><span data-stu-id="77a13-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="77a13-112">针对身份验证登录问题的其他诊断</span><span class="sxs-lookup"><span data-stu-id="77a13-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="77a13-113">更好地支持 Lync 混合部署</span><span class="sxs-lookup"><span data-stu-id="77a13-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="77a13-114">对凭据选取器的更新</span><span class="sxs-lookup"><span data-stu-id="77a13-114">Updates to credential picker</span></span>

  - <span data-ttu-id="77a13-115">稳定性改进</span><span class="sxs-lookup"><span data-stu-id="77a13-115">Stability improvements</span></span>

<span data-ttu-id="77a13-116">我们非常感谢您的反馈。</span><span class="sxs-lookup"><span data-stu-id="77a13-116">We appreciate any feedback.</span></span> <span data-ttu-id="77a13-117">请将所有支持问题或问题发送到[PCD 反馈](mailto:pcdfb@microsoft.com)别名<pcdfb@microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="77a13-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="77a13-118">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="77a13-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="77a13-119">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="77a13-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="77a13-120">Lync PCD 系统要求</span><span class="sxs-lookup"><span data-stu-id="77a13-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="77a13-121">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="77a13-121">Lync PCD Features</span></span>

  - <span data-ttu-id="77a13-122">运行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="77a13-122">Running Lync PCD</span></span>

  - <span data-ttu-id="77a13-123">卸载 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="77a13-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="77a13-124">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="77a13-124">Lync PCD Versions</span></span>

<span data-ttu-id="77a13-125">本主题介绍以下版本的工具，可供免费下载：</span><span class="sxs-lookup"><span data-stu-id="77a13-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="77a13-126">Windows 桌面应用（[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)）</span><span class="sxs-lookup"><span data-stu-id="77a13-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="77a13-127">Lync PCD 系统要求</span><span class="sxs-lookup"><span data-stu-id="77a13-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77a13-128">PCD 要求在 Lync Server 部署中安装和配置统一通信 Web API （UCWA）以支持移动客户端。</span><span class="sxs-lookup"><span data-stu-id="77a13-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="77a13-129">UCWA 与 Lync Server 一起安装。</span><span class="sxs-lookup"><span data-stu-id="77a13-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="77a13-130">Windows 桌面应用要求</span><span class="sxs-lookup"><span data-stu-id="77a13-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="77a13-131">Windows 7 或 Windows 8 操作系统的任何版本</span><span class="sxs-lookup"><span data-stu-id="77a13-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="77a13-132">Microsoft .NET Framework 4.5 可在[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="77a13-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="77a13-133">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="77a13-133">Lync PCD Features</span></span>

<span data-ttu-id="77a13-134">Lync PCD 包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="77a13-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="77a13-135">默认按需运行（2分钟爆发）</span><span class="sxs-lookup"><span data-stu-id="77a13-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="77a13-136">在始终打开的情况下运行（最多24小时，在贴靠视图中）模式</span><span class="sxs-lookup"><span data-stu-id="77a13-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="77a13-137">测试运行的历史视图</span><span class="sxs-lookup"><span data-stu-id="77a13-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="77a13-138">诊断登录失败（仅适用于 Windows 8 的 Lync PCD）</span><span class="sxs-lookup"><span data-stu-id="77a13-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="77a13-139">![Lync PCD 功能登录进度屏幕截图](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登录进度屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="77a13-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="77a13-140">网络指标的图形化视图-以全屏和贴靠视图显示网络 MOS、数据包丢失和 Interarrival 抖动。</span><span class="sxs-lookup"><span data-stu-id="77a13-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="77a13-141">**全屏视图**</span><span class="sxs-lookup"><span data-stu-id="77a13-141">**Full screen view**</span></span>

<span data-ttu-id="77a13-142">![PreCall Diagnostic 工具测试结果图](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic 工具测试结果图")</span><span class="sxs-lookup"><span data-stu-id="77a13-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="77a13-143">**贴靠视图**</span><span class="sxs-lookup"><span data-stu-id="77a13-143">**Snapped view**</span></span>

<span data-ttu-id="77a13-144">![PreCall Diagnostic 工具利用率测试结果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic 工具利用率测试结果")</span><span class="sxs-lookup"><span data-stu-id="77a13-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="77a13-145">运行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="77a13-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="77a13-146">运行 Windows 桌面应用</span><span class="sxs-lookup"><span data-stu-id="77a13-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="77a13-147">若要在 Windows 7 系统上启动 PCD，请从 "**开始**" 菜单中选择 " **PreCall 诊断**"。</span><span class="sxs-lookup"><span data-stu-id="77a13-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="77a13-148">若要在 Windows 8 系统上启动 PCD，请在 "开始" 屏幕上选择该图标，或搜索 "PreCall Diagnostics"。</span><span class="sxs-lookup"><span data-stu-id="77a13-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="77a13-149">![PreCall Diagnostic 工具图标](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic 工具图标")</span><span class="sxs-lookup"><span data-stu-id="77a13-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="77a13-150">当工具启动时，选择提供凭据的首选方法，然后在 " **PreCall 诊断工具选项**" 对话框中选择 "网络操作模式"，然后选择 **"确定"**：</span><span class="sxs-lookup"><span data-stu-id="77a13-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="77a13-151">选择 "**开始测试**" 按钮以开始运行诊断。</span><span class="sxs-lookup"><span data-stu-id="77a13-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="77a13-152">如果选择 "**使用网络凭据**" 选项，测试将立即开始。</span><span class="sxs-lookup"><span data-stu-id="77a13-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="77a13-153">如果选择 "**让我输入我的凭据**" 选项，则会打开 " **Windows 安全**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="77a13-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="77a13-154">输入凭据后，测试开始。</span><span class="sxs-lookup"><span data-stu-id="77a13-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="77a13-155">卸载 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="77a13-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="77a13-156">若要删除 Lync PCD，请按照操作系统的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="77a13-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="77a13-157">在 Windows 7 系统上，打开 "**控制面板**"，选择 "**程序和功能**"，然后双击 " **Lync 2013 PreCall 诊断**"。</span><span class="sxs-lookup"><span data-stu-id="77a13-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="77a13-158">在 Windows 8 系统上，右键单击 "PCD" 磁贴，然后单击 "开始" 屏幕底部的应用栏中的 "**卸载**"。</span><span class="sxs-lookup"><span data-stu-id="77a13-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

