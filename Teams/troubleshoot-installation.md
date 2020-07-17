---
title: 解决 Windows 上的 Microsoft Teams 安装和更新问题
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何解决 Windows 上 Teams 桌面客户端应用的安装和更新问题。
ms.openlocfilehash: 7b8d4984a8ee40f9a013155ad28b682e000260ba
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086138"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="3701e-103">解决 Windows 上的 Microsoft Teams 安装和更新问题</span><span class="sxs-lookup"><span data-stu-id="3701e-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="3701e-104">本文提供有关如何诊断和解决在 Windows 上运行的 Teams 桌面客户端应用的安装和更新问题的指南。</span><span class="sxs-lookup"><span data-stu-id="3701e-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="3701e-105">检查 Teams 是否已成功更新</span><span class="sxs-lookup"><span data-stu-id="3701e-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="3701e-106">按照以下步骤检查是否已成功安装 Teams 更新。</span><span class="sxs-lookup"><span data-stu-id="3701e-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="3701e-107">在 Teams 中，选择你的个人资料图片，然后单击“**关于**” > “**版本**”。</span><span class="sxs-lookup"><span data-stu-id="3701e-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="3701e-108">在同一菜单上，单击“**检查更新**”。</span><span class="sxs-lookup"><span data-stu-id="3701e-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="3701e-109">等待应用顶部的横幅指示需要“刷新”Teams。</span><span class="sxs-lookup"><span data-stu-id="3701e-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="3701e-110">该链接应在此进程下载 Teams 新版本后大约 1 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="3701e-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="3701e-111">通过该横幅，你还可以知道自己是否已在运行最新版本，如果是，则无需进行更新。</span><span class="sxs-lookup"><span data-stu-id="3701e-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="3701e-112">单击横幅上的刷新链接。</span><span class="sxs-lookup"><span data-stu-id="3701e-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="3701e-113">等待 Teams 重新启动，然后重复步骤 1 以查看应用是否已更新。</span><span class="sxs-lookup"><span data-stu-id="3701e-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="3701e-114">如果看到失败消息，或者版本号与步骤 4 中的相同，则表示更新进程失败。</span><span class="sxs-lookup"><span data-stu-id="3701e-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="3701e-115">解决安装和更新问题</span><span class="sxs-lookup"><span data-stu-id="3701e-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="3701e-116">解决安装问题</span><span class="sxs-lookup"><span data-stu-id="3701e-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="3701e-117">安装 Teams 后，Teams 安装程序会将事件序列记录到 %LocalAppData%\SquirrelTemp\SquirrelSetup.log。</span><span class="sxs-lookup"><span data-stu-id="3701e-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="3701e-118">首先要查找错误消息或日志末尾附近的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="3701e-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="3701e-119">请注意，日志开头的调用堆栈可能并不意味着存在安装问题。</span><span class="sxs-lookup"><span data-stu-id="3701e-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="3701e-120">更简单的方式是将你的日志与成功安装（即使是在另一台计算机上）后的日志进行比较，查看预期效果。</span><span class="sxs-lookup"><span data-stu-id="3701e-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="3701e-121">如果 SquirrelSetup 未指明原因，或者如果你需要更多信息以解决问题，请参阅[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="3701e-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="3701e-122">解决升级问题</span><span class="sxs-lookup"><span data-stu-id="3701e-122">Troubleshoot update issues</span></span>

<span data-ttu-id="3701e-123">成功安装 Teams 后，日志位置将从 %LocalAppData%\SquirrelTemp 切换到 %AppData%\Microsoft\Teams。</span><span class="sxs-lookup"><span data-stu-id="3701e-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %AppData%\Microsoft\Teams.</span></span> <span data-ttu-id="3701e-124">在这里，有两个需要关注的日志文件：SquirrelSetup.log 和 logs.txt。</span><span class="sxs-lookup"><span data-stu-id="3701e-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="3701e-125">这里的 SquirrelSetup.log 文件是由 Update.exe 写入的，后者是为 Teams 应用服务的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="3701e-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="3701e-126">Logs.txt 文件用于 Teams 应用（具体来说，是 Teams.exe）记录重要应用程序事件。</span><span class="sxs-lookup"><span data-stu-id="3701e-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="3701e-127">它可能包含失败信息。</span><span class="sxs-lookup"><span data-stu-id="3701e-127">It will likely contain failure information.</span></span>

<span data-ttu-id="3701e-128">这些日志文件包含个人身份信息 (PII)，因此不会发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3701e-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="3701e-129">Teams 可以自动启动更新进程（具体取决于策略），或者，用户可以通过访问其个人资料图片 >“**检查更新**”来手动检查更新。</span><span class="sxs-lookup"><span data-stu-id="3701e-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="3701e-130">两种方法均使用以下事件序列。</span><span class="sxs-lookup"><span data-stu-id="3701e-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="3701e-131">**检查是否有更新**。</span><span class="sxs-lookup"><span data-stu-id="3701e-131">**Check for updates**.</span></span> <span data-ttu-id="3701e-132">Teams 提出 web 请求，包括当前应用版本和部署铃声信息。</span><span class="sxs-lookup"><span data-stu-id="3701e-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="3701e-133">此步骤旨在获取下载链接。</span><span class="sxs-lookup"><span data-stu-id="3701e-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="3701e-134">此步骤中的失败将记录在 Logs.txt 中。</span><span class="sxs-lookup"><span data-stu-id="3701e-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="3701e-135">**下载更新**。</span><span class="sxs-lookup"><span data-stu-id="3701e-135">**Download update**.</span></span> <span data-ttu-id="3701e-136">Teams 将使用从步骤 1 中获得的下载链接下载更新。</span><span class="sxs-lookup"><span data-stu-id="3701e-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="3701e-137">下载完成后，Teams 将调用 Update.exe 来暂存下载。</span><span class="sxs-lookup"><span data-stu-id="3701e-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="3701e-138">下载失败也记录在 Logs.txt 中。</span><span class="sxs-lookup"><span data-stu-id="3701e-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="3701e-139">**暂存更新**。</span><span class="sxs-lookup"><span data-stu-id="3701e-139">**Stage the update**.</span></span> <span data-ttu-id="3701e-140">下载的内容将经过验证，并由 Update.exe 解压缩到中间文件夹 %LocalAppData%\Microsoft\Teams\stage) 中。</span><span class="sxs-lookup"><span data-stu-id="3701e-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="3701e-141">此步骤中的失败将记录在 SquirrelTemp.log 中。</span><span class="sxs-lookup"><span data-stu-id="3701e-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="3701e-142">**安装更新**。</span><span class="sxs-lookup"><span data-stu-id="3701e-142">**Install the update**.</span></span> <span data-ttu-id="3701e-143">可通过多种方式启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="3701e-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="3701e-144">用户登录时，系统会自动启动 Teams，或者，可以通过快捷方式启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="3701e-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="3701e-145">在此步骤中，Update.exe 会检查暂存文件夹是否存在，再次验证内容，并执行文件操作来取消暂存应用。</span><span class="sxs-lookup"><span data-stu-id="3701e-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="3701e-146">%LocalAppData%\Microsoft\Teams\current 中的旧应用程序文件夹将备份到 %LocalAppData%\Microsoft\Teams\previous，且暂存文件夹将重命名为“current”。</span><span class="sxs-lookup"><span data-stu-id="3701e-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="3701e-147">此步骤中的失败将记录在 SquirrelTemp.log 中。</span><span class="sxs-lookup"><span data-stu-id="3701e-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="3701e-148">如果 SquirrelTemp.log 或 Logs.txt 没有包含足以确定基本原因的信息，而且你需要更多信息来解决问题，请转至[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="3701e-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="3701e-149">收集和分析应用程序和系统日志</span><span class="sxs-lookup"><span data-stu-id="3701e-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="3701e-150">本节介绍如何收集和分析应用程序和系统日志，以获取更全面的信息来解决问题。</span><span class="sxs-lookup"><span data-stu-id="3701e-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="3701e-151">可使用 Sysinternals 工具来完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3701e-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="3701e-152">要了解更多信息，请参阅 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。</span><span class="sxs-lookup"><span data-stu-id="3701e-152">To learn more, see [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="3701e-153">收集日志</span><span class="sxs-lookup"><span data-stu-id="3701e-153">Collect logs</span></span>

1. <span data-ttu-id="3701e-154">下载 [Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。</span><span class="sxs-lookup"><span data-stu-id="3701e-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="3701e-155">将 zip 文件提取到本地驱动器上的 % TEMP% 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3701e-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="3701e-156">打开提升的命令提示符，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3701e-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="3701e-157">运行以下命令以转至 TEMP 文件夹：</span><span class="sxs-lookup"><span data-stu-id="3701e-157">Run the following to go to your TEMP folder:</span></span>

        ```console
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="3701e-158">复制安装和应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="3701e-158">Copy the setup and application logs.</span></span> <span data-ttu-id="3701e-159">请注意，根据故障点，某些日志可能不会显示。</span><span class="sxs-lookup"><span data-stu-id="3701e-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="3701e-160">运行以下命令以捕获打开的句柄。</span><span class="sxs-lookup"><span data-stu-id="3701e-160">Run the following to capture the open handles.</span></span>

        ```console
        handle > handles.txt
        ```

    4. <span data-ttu-id="3701e-161">运行以下命令以捕获打开的 DLL。</span><span class="sxs-lookup"><span data-stu-id="3701e-161">Run the following to capture the opened DLLs.</span></span>

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="3701e-162">运行以下命令以捕获正在运行的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="3701e-162">Run the following to capture the drivers that are running.</span></span>

        ```console
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="3701e-163">运行以下命令以捕获 Teams 文件夹的访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="3701e-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="3701e-164">分析日志（适用于高级用户）</span><span class="sxs-lookup"><span data-stu-id="3701e-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="3701e-165">更新失败可能会导致无法预测的应用行为。</span><span class="sxs-lookup"><span data-stu-id="3701e-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="3701e-166">例如，用户可能无法退出 Teams、拥有过时的 Teams 版本或无法启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="3701e-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="3701e-167">如果你在更新过程中遇到问题，请先在 SquirrelTemp.log 中查找原因。</span><span class="sxs-lookup"><span data-stu-id="3701e-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="3701e-168">下面列出了几种不同类型的更新失败（从最常见到最不常见），以及如何使用日志对它们进行分析和故障排除。</span><span class="sxs-lookup"><span data-stu-id="3701e-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="3701e-169">无法退出 Teams</span><span class="sxs-lookup"><span data-stu-id="3701e-169">Unable to exit Teams</span></span>

<span data-ttu-id="3701e-170">当 Teams 确定需要将自身更新到较新版本时，它会下载并暂存新应用，然后等待机会，在计算机下次空闲时重新启动。</span><span class="sxs-lookup"><span data-stu-id="3701e-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="3701e-171">此过程中的一个常见问题是，当另一个进程或文件系统驱动程序锁定了 Teams.exe 进程时，会导致其无法退出。</span><span class="sxs-lookup"><span data-stu-id="3701e-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="3701e-172">因此，Teams 应用就无法被新下载和暂存的应用取代。</span><span class="sxs-lookup"><span data-stu-id="3701e-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="3701e-173">疑难解答提示：</span><span class="sxs-lookup"><span data-stu-id="3701e-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="3701e-174">要确认这是就是你遇到的问题，请退出 Teams（在任务栏上右键单击 Teams，然后单击“**退出**”）。</span><span class="sxs-lookup"><span data-stu-id="3701e-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="3701e-175">然后，在 Windows 中打开任务管理器，查看 Teams 的实例是否仍在运行。</span><span class="sxs-lookup"><span data-stu-id="3701e-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="3701e-176">如果你不在发生此问题的计算机上，请检查从发生此问题的计算机上收集的 SquirrelTemp，并查找“Program: Unable to terminate the process in the log”条目。</span><span class="sxs-lookup"><span data-stu-id="3701e-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="3701e-177">要确定导致 Teams.exe 无法退出的原因，请查找 Dlls.txt 和 Handles.txt 日志。</span><span class="sxs-lookup"><span data-stu-id="3701e-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="3701e-178">这些日志会告诉你阻止 Teams 退出的进程。</span><span class="sxs-lookup"><span data-stu-id="3701e-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="3701e-179">导致 Teams 无法退出的另一个可能原因是内核模式文件系统筛选器驱动程序。</span><span class="sxs-lookup"><span data-stu-id="3701e-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="3701e-180">可以使用 SysInternals 工具 [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)，通过运行 ```procdump -mk <pid>```（其中，<pid> 是从任务管理器中获取的进程 ID）收集内核模式进程转储。</span><span class="sxs-lookup"><span data-stu-id="3701e-180">Use the SysInternals tool, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="3701e-181">你也可以检查 Driverquery.txt 日志文件，查看是否有可能干扰 Teams 的活动筛选器驱动程序。</span><span class="sxs-lookup"><span data-stu-id="3701e-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="3701e-182">要从此状态还原，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="3701e-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="3701e-183">文件权限</span><span class="sxs-lookup"><span data-stu-id="3701e-183">File permissions</span></span>

<span data-ttu-id="3701e-184">在整个安装和更新过程中，Teams 会在用户配置文件中创建大量子文件夹和文件。</span><span class="sxs-lookup"><span data-stu-id="3701e-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="3701e-185">由于应用程序和更新程序是以非提升用户的身份运行的，因此必须对以下文件夹授予读取和写入权限：</span><span class="sxs-lookup"><span data-stu-id="3701e-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="3701e-186">文件夹</span><span class="sxs-lookup"><span data-stu-id="3701e-186">Folder</span></span>  |<span data-ttu-id="3701e-187">使用方</span><span class="sxs-lookup"><span data-stu-id="3701e-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="3701e-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="3701e-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="3701e-189">Teams 安装程序（例如，Teams_Windows_x64.exe）在安装阶段使用</span><span class="sxs-lookup"><span data-stu-id="3701e-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="3701e-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="3701e-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="3701e-191">Teams 更新程序 (Update.exe) 在更新过程中用于提取和暂存应用包</span><span class="sxs-lookup"><span data-stu-id="3701e-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="3701e-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="3701e-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="3701e-193">Teams 应用 (Teams.exe) 用于保存设置、应用状态和（预先暂存的）已下载更新包</span><span class="sxs-lookup"><span data-stu-id="3701e-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="3701e-194">如果 Teams 由于无法写入文件而被拒绝访问，另一个软件应用程序可能会产生干扰，或者安全描述符条目可能会限制对文件夹的写入权限。</span><span class="sxs-lookup"><span data-stu-id="3701e-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="3701e-195">疑难解答提示：</span><span class="sxs-lookup"><span data-stu-id="3701e-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="3701e-196">在 SquirrelTemp.log 或 Logs.txt 中查找“access denied”的证据。</span><span class="sxs-lookup"><span data-stu-id="3701e-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="3701e-197">检查这些文件，了解是否曾尝试写入文件但失败。</span><span class="sxs-lookup"><span data-stu-id="3701e-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="3701e-198">打开 Icacls.txt，查找阻止非管理员用户写入操作的有效访问控制项 (ACE)。这通常是一个 DACL 项。</span><span class="sxs-lookup"><span data-stu-id="3701e-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="3701e-199">有关详细信息，请参阅 [icacls 文档](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)。</span><span class="sxs-lookup"><span data-stu-id="3701e-199">For more information, see the [icacls documentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="3701e-200">文件损坏</span><span class="sxs-lookup"><span data-stu-id="3701e-200">File corrupted</span></span>

<span data-ttu-id="3701e-201">在某些情况下，加密软件可能会更改 %LocalAppData%\Microsoft\Teams 文件夹中的文件，进而导致 Teams 无法启动。</span><span class="sxs-lookup"><span data-stu-id="3701e-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="3701e-202">这种情况可能在任何时候发生，即使不在更新应用时也不例外。</span><span class="sxs-lookup"><span data-stu-id="3701e-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="3701e-203">遗憾的是，如果文件损坏，从此状态恢复的唯一方法是卸载并重新安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="3701e-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3701e-204">如果使用上述任何步骤均无法确定问题的根本原因，则可能需要尝试 [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) 会话。</span><span class="sxs-lookup"><span data-stu-id="3701e-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="3701e-205">Process Monitor 是一个 Sysinternals 工具，可以记录对注册表和文件系统的访问。</span><span class="sxs-lookup"><span data-stu-id="3701e-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3701e-206">相关主题</span><span class="sxs-lookup"><span data-stu-id="3701e-206">Related topics</span></span>

- [<span data-ttu-id="3701e-207">获取 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="3701e-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="3701e-208">Teams 客户端更新</span><span class="sxs-lookup"><span data-stu-id="3701e-208">Teams client updates</span></span>](teams-client-update.md)
- [<span data-ttu-id="3701e-209">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="3701e-209">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)