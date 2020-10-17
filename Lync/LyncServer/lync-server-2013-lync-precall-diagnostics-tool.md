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
ms.openlocfilehash: 19051eb183dc12f091de0d90ebb707bc6cee8fc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525149"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="8f338-102">Lync Server 2013 中的 lync PreCall 诊断工具</span><span class="sxs-lookup"><span data-stu-id="8f338-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f338-103">_**上次修改的主题：** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="8f338-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="8f338-104">Lync PreCall 诊断工具 (PCD) 是一种基于客户端的应用程序，它允许您查看网络的当前状态在即将进行的企业语音呼叫中可能会影响音频质量。</span><span class="sxs-lookup"><span data-stu-id="8f338-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="8f338-105">PCD 在网络的最后一个跃点可能是最弱 (的情况下非常有用，例如，在公共 WiFi 网络或家庭用户) 上的便携式电脑。</span><span class="sxs-lookup"><span data-stu-id="8f338-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="8f338-106">PCD 创建一个可遍历此网络最终网段的小型数据包流。</span><span class="sxs-lookup"><span data-stu-id="8f338-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="8f338-107">然后，该工具将分析数据包流，以估计沿此段流量的抖动和丢失可能影响呼叫质量的方式，然后提供报告。</span><span class="sxs-lookup"><span data-stu-id="8f338-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="8f338-108">可以在客户端上连续运行 PCD，甚至在发出呼叫时也可以。</span><span class="sxs-lookup"><span data-stu-id="8f338-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="8f338-109">数据包流对带宽的影响不大。</span><span class="sxs-lookup"><span data-stu-id="8f338-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="8f338-110">**1.1 版本的 PCD 的最新版本包括以下增强功能：**</span><span class="sxs-lookup"><span data-stu-id="8f338-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="8f338-111">支持较长的密码，该密码现在最长可为127个字符</span><span class="sxs-lookup"><span data-stu-id="8f338-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="8f338-112">对身份验证登录问题的其他诊断</span><span class="sxs-lookup"><span data-stu-id="8f338-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="8f338-113">对 Lync 混合部署的更好支持</span><span class="sxs-lookup"><span data-stu-id="8f338-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="8f338-114">凭据选取器的更新</span><span class="sxs-lookup"><span data-stu-id="8f338-114">Updates to credential picker</span></span>

  - <span data-ttu-id="8f338-115">稳定性改进</span><span class="sxs-lookup"><span data-stu-id="8f338-115">Stability improvements</span></span>

<span data-ttu-id="8f338-116">感谢你的反馈。</span><span class="sxs-lookup"><span data-stu-id="8f338-116">We appreciate any feedback.</span></span> <span data-ttu-id="8f338-117">请在上将所有支持问题或问题发送到 [PCD 反馈](mailto:pcdfb@microsoft.com) 别名 <pcdfb@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="8f338-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="8f338-118">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="8f338-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="8f338-119">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="8f338-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="8f338-120">Lync PCD 系统要求</span><span class="sxs-lookup"><span data-stu-id="8f338-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="8f338-121">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="8f338-121">Lync PCD Features</span></span>

  - <span data-ttu-id="8f338-122">运行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="8f338-122">Running Lync PCD</span></span>

  - <span data-ttu-id="8f338-123">卸载 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="8f338-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="8f338-124">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="8f338-124">Lync PCD Versions</span></span>

<span data-ttu-id="8f338-125">本主题介绍了此工具的以下版本，可免费下载：</span><span class="sxs-lookup"><span data-stu-id="8f338-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="8f338-126">Windows 桌面应用程序 ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)) </span><span class="sxs-lookup"><span data-stu-id="8f338-126">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="8f338-127">Lync PCD 系统要求</span><span class="sxs-lookup"><span data-stu-id="8f338-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f338-128">PCD 要求将统一通信 Web API () UCWA 安装和配置为支持 Lync Server 部署中的移动客户端。</span><span class="sxs-lookup"><span data-stu-id="8f338-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="8f338-129">UCWA 与 Lync Server 一起安装。</span><span class="sxs-lookup"><span data-stu-id="8f338-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="8f338-130">Windows 桌面应用程序要求</span><span class="sxs-lookup"><span data-stu-id="8f338-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="8f338-131">任何版本的 Windows 7 或 Windows 8 操作系统</span><span class="sxs-lookup"><span data-stu-id="8f338-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="8f338-132">Microsoft .NET Framework 4.5 可在 [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="8f338-132">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="8f338-133">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="8f338-133">Lync PCD Features</span></span>

<span data-ttu-id="8f338-134">Lync PCD 包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="8f338-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="8f338-135">按需运行 (2 分钟猝发) </span><span class="sxs-lookup"><span data-stu-id="8f338-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="8f338-136">在捕捉视图) 模式下，在 (始终保持在24小时内运行</span><span class="sxs-lookup"><span data-stu-id="8f338-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="8f338-137">测试运行的历史视图</span><span class="sxs-lookup"><span data-stu-id="8f338-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="8f338-138">仅 (Lync PCD for Windows 8 中诊断登录失败) </span><span class="sxs-lookup"><span data-stu-id="8f338-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="8f338-139">![Lync PCD 功能登录进度屏幕截图](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登录进度屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="8f338-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="8f338-140">网络指标（网络 MOS、数据包丢失和 Interarrival 抖动以及全屏显示和捕捉视图中的图形视图。</span><span class="sxs-lookup"><span data-stu-id="8f338-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="8f338-141">**全屏视图**</span><span class="sxs-lookup"><span data-stu-id="8f338-141">**Full screen view**</span></span>

<span data-ttu-id="8f338-142">![PreCall 诊断工具测试结果关系图](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 诊断工具测试结果关系图")</span><span class="sxs-lookup"><span data-stu-id="8f338-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="8f338-143">**快照视图**</span><span class="sxs-lookup"><span data-stu-id="8f338-143">**Snapped view**</span></span>

<span data-ttu-id="8f338-144">![PreCall 诊断工具利用率测试结果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 诊断工具利用率测试结果")</span><span class="sxs-lookup"><span data-stu-id="8f338-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="8f338-145">运行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="8f338-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="8f338-146">运行 Windows 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="8f338-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="8f338-147">若要在 Windows 7 系统上启动 PCD，请从 "**开始**" 菜单中选择 " **PreCall Diagnostics** "。</span><span class="sxs-lookup"><span data-stu-id="8f338-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="8f338-148">若要在 Windows 8 系统上启动 PCD，请在 "开始" 屏幕上选择该图标，或搜索 "PreCall Diagnostics"。</span><span class="sxs-lookup"><span data-stu-id="8f338-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="8f338-149">![PreCall 诊断工具图标](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 诊断工具图标")</span><span class="sxs-lookup"><span data-stu-id="8f338-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="8f338-150">工具启动后，选择提供凭据的首选方法，并在 " **PreCall 诊断工具选项** " 对话框中选择 "网络操作模式"，然后选择 **"确定"**：</span><span class="sxs-lookup"><span data-stu-id="8f338-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="8f338-151">选择 " **开始测试** " 按钮以开始运行诊断。</span><span class="sxs-lookup"><span data-stu-id="8f338-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="8f338-152">如果选择 " **使用网络凭据** " 选项，测试将立即开始。</span><span class="sxs-lookup"><span data-stu-id="8f338-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="8f338-153">如果选择 " **让我输入我的凭据** " 选项，则将打开 " **Windows 安全性** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="8f338-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="8f338-154">输入凭据后，将开始测试。</span><span class="sxs-lookup"><span data-stu-id="8f338-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="8f338-155">卸载 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="8f338-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="8f338-156">若要删除 Lync PCD，请按照适用于您的操作系统的过程操作：</span><span class="sxs-lookup"><span data-stu-id="8f338-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="8f338-157">在 Windows 7 系统上，打开 " **控制面板**"，选择 " **程序和功能**"，然后双击 " **Lync 2013 PreCall Diagnostics**"。</span><span class="sxs-lookup"><span data-stu-id="8f338-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="8f338-158">在 Windows 8 系统上，右键单击 "PCD" 磁贴，然后单击 "开始" 屏幕底部的 "应用程序栏" 中的 " **卸载** "。</span><span class="sxs-lookup"><span data-stu-id="8f338-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

