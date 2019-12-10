---
title: 解决 Windows 上的 Microsoft 团队安装和更新问题
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何解决 Windows 上的团队桌面客户端应用的安装和更新问题。
ms.openlocfilehash: 812beb3471a1d4ee2cbc1e8e7f7b36b2a42e0e2d
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39920144"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="68cb6-103">解决 Windows 上的 Microsoft 团队安装和更新问题</span><span class="sxs-lookup"><span data-stu-id="68cb6-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="68cb6-104">本文提供了有关如何诊断和解决 Windows 上运行的团队桌面客户端应用的安装和更新问题的指南。</span><span class="sxs-lookup"><span data-stu-id="68cb6-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="68cb6-105">检查团队是否已成功更新</span><span class="sxs-lookup"><span data-stu-id="68cb6-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="68cb6-106">按照以下步骤检查团队更新是否已成功安装。</span><span class="sxs-lookup"><span data-stu-id="68cb6-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="68cb6-107">在 "团队" 中，选择您的个人资料图片，然后单击 "**关于** > **版本**"。</span><span class="sxs-lookup"><span data-stu-id="68cb6-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="68cb6-108">在同一菜单上，单击 "**检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="68cb6-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="68cb6-109">请等待应用顶部的横幅，以指示需要团队的 "刷新"。</span><span class="sxs-lookup"><span data-stu-id="68cb6-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="68cb6-110">在此过程下载新版本的团队时，该链接稍后应显示大约一分钟。</span><span class="sxs-lookup"><span data-stu-id="68cb6-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="68cb6-111">横幅还让你知道是否已运行最新版本，在这种情况下，不需要更新。</span><span class="sxs-lookup"><span data-stu-id="68cb6-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="68cb6-112">单击横幅中的 "刷新" 链接。</span><span class="sxs-lookup"><span data-stu-id="68cb6-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="68cb6-113">等待团队重新启动，然后重复步骤1以查看是否更新了应用。</span><span class="sxs-lookup"><span data-stu-id="68cb6-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="68cb6-114">如果您看到一条错误消息，或者版本号与步骤4中的版本号相同，则更新过程失败。</span><span class="sxs-lookup"><span data-stu-id="68cb6-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="68cb6-115">解决安装和更新问题</span><span class="sxs-lookup"><span data-stu-id="68cb6-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="68cb6-116">解决安装问题</span><span class="sxs-lookup"><span data-stu-id="68cb6-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="68cb6-117">在安装团队时，团队安装程序会将事件序列记录到%LocalAppData%\SquirrelTemp\SquirrelSetup.log。</span><span class="sxs-lookup"><span data-stu-id="68cb6-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="68cb6-118">要查找的第一件事是出现一条错误消息或一个靠近日志末尾的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="68cb6-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="68cb6-119">请注意，日志开头的调用堆栈可能并不意味着存在安装问题。</span><span class="sxs-lookup"><span data-stu-id="68cb6-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="68cb6-120">将日志与日志进行比较比从成功安装（甚至在另一台计算机上）到日志，以查看预期效果。</span><span class="sxs-lookup"><span data-stu-id="68cb6-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="68cb6-121">如果 SquirrelSetup 未指明原因，或者你需要详细信息来解决该问题，请参阅[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="68cb6-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="68cb6-122">更新问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="68cb6-122">Troubleshoot update issues</span></span>

<span data-ttu-id="68cb6-123">成功安装团队后，日志位置将从%LocalAppData%\SquirrelTemp 切换到%AppData%\Microsoft\Teams。</span><span class="sxs-lookup"><span data-stu-id="68cb6-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %AppData%\Microsoft\Teams.</span></span> <span data-ttu-id="68cb6-124">在此位置，有两个感兴趣的日志文件： SquirrelSetup 和 .log。</span><span class="sxs-lookup"><span data-stu-id="68cb6-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="68cb6-125">此位置的 SquirrelSetup 文件由 update.exe 编写，后者是为团队应用服务的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="68cb6-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="68cb6-126">"团队" 应用（特别是 "团队 .exe"）使用日志 .txt 文件记录重要的应用程序事件。</span><span class="sxs-lookup"><span data-stu-id="68cb6-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="68cb6-127">它可能会包含失败信息。</span><span class="sxs-lookup"><span data-stu-id="68cb6-127">It will likely contain failure information.</span></span>

<span data-ttu-id="68cb6-128">这些日志文件包含个人身份信息（PII），因此它们不会发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="68cb6-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="68cb6-129">团队可以自动启动更新过程（具体取决于策略），或者用户可以通过转到其个人资料图片来手动检查更新 >**检查是否有更新**。</span><span class="sxs-lookup"><span data-stu-id="68cb6-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="68cb6-130">这两种方法都使用以下事件序列。</span><span class="sxs-lookup"><span data-stu-id="68cb6-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="68cb6-131">**检查更新**。</span><span class="sxs-lookup"><span data-stu-id="68cb6-131">**Check for updates**.</span></span> <span data-ttu-id="68cb6-132">团队发出 web 请求，包括当前应用版本和部署震铃信息。</span><span class="sxs-lookup"><span data-stu-id="68cb6-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="68cb6-133">此步骤的目标是获取下载链接。</span><span class="sxs-lookup"><span data-stu-id="68cb6-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="68cb6-134">此步骤中的失败记录在 ".txt" 中。</span><span class="sxs-lookup"><span data-stu-id="68cb6-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="68cb6-135">**下载更新**。</span><span class="sxs-lookup"><span data-stu-id="68cb6-135">**Download update**.</span></span> <span data-ttu-id="68cb6-136">团队使用从步骤1获取的下载链接下载更新。</span><span class="sxs-lookup"><span data-stu-id="68cb6-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="68cb6-137">下载完成后，团队将调用 update.exe 以暂存下载。</span><span class="sxs-lookup"><span data-stu-id="68cb6-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="68cb6-138">日志 .txt 中也会记录下载失败。</span><span class="sxs-lookup"><span data-stu-id="68cb6-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="68cb6-139">**暂存更新**。</span><span class="sxs-lookup"><span data-stu-id="68cb6-139">**Stage the update**.</span></span> <span data-ttu-id="68cb6-140">下载的内容将验证并解压缩到中间文件夹%LocalAppData%\Microsoft\Teams\stage）中，该文件夹由 update.exe 完成。</span><span class="sxs-lookup"><span data-stu-id="68cb6-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="68cb6-141">此步骤中的失败记录在 SquirrelTemp 中。</span><span class="sxs-lookup"><span data-stu-id="68cb6-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="68cb6-142">**安装更新**。</span><span class="sxs-lookup"><span data-stu-id="68cb6-142">**Install the update**.</span></span> <span data-ttu-id="68cb6-143">有多种方法可以启动团队。</span><span class="sxs-lookup"><span data-stu-id="68cb6-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="68cb6-144">当用户登录时，系统会自动启动团队，或者你可以通过快捷方式启动团队。</span><span class="sxs-lookup"><span data-stu-id="68cb6-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="68cb6-145">在此步骤中，update.exe 检查是否存在暂存文件夹，再次验证内容，并执行文件操作来取消暂存应用。</span><span class="sxs-lookup"><span data-stu-id="68cb6-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="68cb6-146">%LocalAppData%\Microsoft\Teams\current 中的旧应用程序文件夹将备份到%LocalAppData%\Microsoft\Teams\previous，并将 "暂存" 文件夹重命名为 "当前"。</span><span class="sxs-lookup"><span data-stu-id="68cb6-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="68cb6-147">此步骤中的失败记录在 SquirrelTemp 中。</span><span class="sxs-lookup"><span data-stu-id="68cb6-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="68cb6-148">如果 SquirrelTemp 或 .log 不包含足够的信息来确定基础原因，并且你需要更多的信息来解决该问题，请转到 "[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)"。</span><span class="sxs-lookup"><span data-stu-id="68cb6-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="68cb6-149">收集和分析应用程序和系统日志</span><span class="sxs-lookup"><span data-stu-id="68cb6-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="68cb6-150">本部分介绍了如何收集和分析应用程序和系统日志，以获取更全面的信息来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="68cb6-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="68cb6-151">您将使用 Sysinternals 工具完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="68cb6-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="68cb6-152">若要了解详细信息，请参阅[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。</span><span class="sxs-lookup"><span data-stu-id="68cb6-152">To learn more, see [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="68cb6-153">收集日志</span><span class="sxs-lookup"><span data-stu-id="68cb6-153">Collect logs</span></span>

1. <span data-ttu-id="68cb6-154">下载[Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。</span><span class="sxs-lookup"><span data-stu-id="68cb6-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="68cb6-155">将 zip 文件解压缩到本地驱动器上的% TEMP% 文件夹。</span><span class="sxs-lookup"><span data-stu-id="68cb6-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="68cb6-156">打开提升的命令提示符，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="68cb6-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="68cb6-157">运行以下操作以转到 TEMP 文件夹：</span><span class="sxs-lookup"><span data-stu-id="68cb6-157">Run the following to go to your TEMP folder:</span></span>

        ```
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="68cb6-158">复制设置和应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="68cb6-158">Copy the setup and application logs.</span></span> <span data-ttu-id="68cb6-159">请注意，根据故障点，某些日志可能不存在。</span><span class="sxs-lookup"><span data-stu-id="68cb6-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="68cb6-160">运行以下操作以捕获打开的句柄。</span><span class="sxs-lookup"><span data-stu-id="68cb6-160">Run the following to capture the open handles.</span></span>

        ```
        handle > handles.txt
        ```

    4. <span data-ttu-id="68cb6-161">运行以下操作以捕获打开的 Dll。</span><span class="sxs-lookup"><span data-stu-id="68cb6-161">Run the following to capture the opened DLLs.</span></span>

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="68cb6-162">运行以下操作以捕获正在运行的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="68cb6-162">Run the following to capture the drivers that are running.</span></span>

        ```
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="68cb6-163">运行以下操作以捕获 "团队" 文件夹的访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="68cb6-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="68cb6-164">分析日志（适用于高级用户）</span><span class="sxs-lookup"><span data-stu-id="68cb6-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="68cb6-165">失败的更新会导致不可预测的应用行为。</span><span class="sxs-lookup"><span data-stu-id="68cb6-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="68cb6-166">例如，用户可能无法退出团队、拥有团队的陈旧版本或无法启动团队。</span><span class="sxs-lookup"><span data-stu-id="68cb6-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="68cb6-167">如果您在更新过程中遇到问题，第一个查找原因的位置是 SquirrelTemp。</span><span class="sxs-lookup"><span data-stu-id="68cb6-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="68cb6-168">下面是不同类型的更新失败内容，按从最常见到最不常见的列表列出，以及如何使用日志分析和排除它们。</span><span class="sxs-lookup"><span data-stu-id="68cb6-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="68cb6-169">无法退出团队</span><span class="sxs-lookup"><span data-stu-id="68cb6-169">Unable to exit Teams</span></span>

<span data-ttu-id="68cb6-170">当团队认为需要将其自身更新为较新的版本时，它会下载并阶段新应用，然后等待商机在下次计算机空闲时重新启动它。</span><span class="sxs-lookup"><span data-stu-id="68cb6-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="68cb6-171">此过程中的一个常见问题是当另一个进程或文件系统驱动程序锁定了团队 .exe 进程时，这将阻止团队 .exe 退出。</span><span class="sxs-lookup"><span data-stu-id="68cb6-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="68cb6-172">因此，不能将团队应用替换为新下载和暂存的应用。</span><span class="sxs-lookup"><span data-stu-id="68cb6-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="68cb6-173">疑难解答提示：</span><span class="sxs-lookup"><span data-stu-id="68cb6-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="68cb6-174">若要确认这是你遇到的问题，请退出团队（右键单击任务栏上的 "团队"，然后单击 "**退出**"）。</span><span class="sxs-lookup"><span data-stu-id="68cb6-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="68cb6-175">然后，在 Windows 中打开任务管理器，以查看团队实例是否仍在运行。</span><span class="sxs-lookup"><span data-stu-id="68cb6-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="68cb6-176">如果你不在遇到此问题的计算机上，请检查从遇到此问题的计算机收集的 SquirrelTemp，并查找 "程序：无法终止日志中的进程" 条目。</span><span class="sxs-lookup"><span data-stu-id="68cb6-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="68cb6-177">若要确定哪些人正在阻止团队成员退出，请查看 Dll 并处理 .txt 日志。</span><span class="sxs-lookup"><span data-stu-id="68cb6-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="68cb6-178">这将告诉你阻止团队退出的流程。</span><span class="sxs-lookup"><span data-stu-id="68cb6-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="68cb6-179">可防止团队退出的另一个原因是内核模式文件系统筛选器驱动程序。</span><span class="sxs-lookup"><span data-stu-id="68cb6-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="68cb6-180">使用 SysInternals 工具[ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)，通过运行```procdump -mk <pid>```来收集内核模式进程转储，其中<pid>是从任务管理器获取的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="68cb6-180">Use the SysInternals tool, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="68cb6-181">你还可以检查 Driverquery 日志文件，查看可能会干扰团队的活动筛选器驱动程序。</span><span class="sxs-lookup"><span data-stu-id="68cb6-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="68cb6-182">若要从该状态恢复，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="68cb6-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="68cb6-183">文件权限</span><span class="sxs-lookup"><span data-stu-id="68cb6-183">File permissions</span></span>

<span data-ttu-id="68cb6-184">在整个安装和更新过程中，团队会在用户的配置文件中创建许多子文件夹和文件。</span><span class="sxs-lookup"><span data-stu-id="68cb6-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="68cb6-185">由于应用和更新程序作为非提升用户运行，因此必须在以下文件夹上授予 read 和 write 权限：</span><span class="sxs-lookup"><span data-stu-id="68cb6-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="68cb6-186">收藏夹</span><span class="sxs-lookup"><span data-stu-id="68cb6-186">Folder</span></span>  |<span data-ttu-id="68cb6-187">使用者</span><span class="sxs-lookup"><span data-stu-id="68cb6-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="68cb6-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="68cb6-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="68cb6-189">安装阶段中的团队安装程序（例如，Teams_Windows_x64）</span><span class="sxs-lookup"><span data-stu-id="68cb6-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="68cb6-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="68cb6-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="68cb6-191">团队更新程序（update.exe），用于在更新过程中提取并暂存应用包</span><span class="sxs-lookup"><span data-stu-id="68cb6-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="68cb6-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="68cb6-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="68cb6-193">用于保存设置、应用状态和已下载（预暂存）的更新程序包的团队应用（团队 .exe）</span><span class="sxs-lookup"><span data-stu-id="68cb6-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="68cb6-194">如果团队因无法写入文件而被拒绝访问，则另一个软件应用程序可能会干扰，或者安全描述符条目可能会限制对文件夹的写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="68cb6-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="68cb6-195">疑难解答提示：</span><span class="sxs-lookup"><span data-stu-id="68cb6-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="68cb6-196">在 SquirrelTemp 或 readme.txt 中查找 "拒绝访问" 证据。</span><span class="sxs-lookup"><span data-stu-id="68cb6-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="68cb6-197">检查这些文件，查看是否有尝试写入失败的文件。</span><span class="sxs-lookup"><span data-stu-id="68cb6-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="68cb6-198">打开 Icacls 并查找有效的访问控制条目（ACE），该条目由非管理员用户阻止写入操作。通常，这是一个 DACL 条目。</span><span class="sxs-lookup"><span data-stu-id="68cb6-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="68cb6-199">有关详细信息，请参阅[icacls 文档](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)。</span><span class="sxs-lookup"><span data-stu-id="68cb6-199">For more information, see the [icacls documentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="68cb6-200">文件已损坏</span><span class="sxs-lookup"><span data-stu-id="68cb6-200">File corrupted</span></span>

<span data-ttu-id="68cb6-201">在某些情况下，加密软件可以更改%LocalAppData%\Microsoft\Teams 文件夹中的文件，这可以防止团队启动。</span><span class="sxs-lookup"><span data-stu-id="68cb6-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="68cb6-202">这可能会在任何时间发生，即使应用未更新也是如此。</span><span class="sxs-lookup"><span data-stu-id="68cb6-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="68cb6-203">遗憾的是，当文件损坏时，从该状态恢复的唯一方法是卸载并重新安装团队。</span><span class="sxs-lookup"><span data-stu-id="68cb6-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="68cb6-204">如果你无法使用以下任一步骤确定问题的基本原因，你可能需要尝试[进程监视器](https://docs.microsoft.com/sysinternals/downloads/procmon)会话。</span><span class="sxs-lookup"><span data-stu-id="68cb6-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="68cb6-205">进程监视器是记录对注册表和文件系统的访问的 Sysinternals 工具。</span><span class="sxs-lookup"><span data-stu-id="68cb6-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="68cb6-206">相关主题</span><span class="sxs-lookup"><span data-stu-id="68cb6-206">Related topics</span></span>

- [<span data-ttu-id="68cb6-207">获取 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="68cb6-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="68cb6-208">Teams 客户端更新</span><span class="sxs-lookup"><span data-stu-id="68cb6-208">Teams client updates</span></span>](teams-client-update.md)