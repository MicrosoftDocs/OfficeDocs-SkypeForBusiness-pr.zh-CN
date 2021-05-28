---
title: 在对 Microsoft Teams 进行故障排除时使用日志文件
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 了解调试、媒体和桌面日志Microsoft Teams、可在何处找到它们，以及它们如何帮助进行监视和故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689690"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="d5ce7-103">使用日志文件监视和排查Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d5ce7-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="d5ce7-104">有三种类型的日志文件由客户端自动生成，可利用它们来帮助监视和排查Teams：</span><span class="sxs-lookup"><span data-stu-id="d5ce7-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="d5ce7-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="d5ce7-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="d5ce7-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="d5ce7-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="d5ce7-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="d5ce7-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="d5ce7-108">本文介绍这些日志及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="d5ce7-109">有关排查特定问题的信息，请参阅：Teams[故障排除。](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="d5ce7-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="d5ce7-110">若要了解如何联系支持人员，请参阅 [获取支持](/microsoft-365/business-video/get-help-support)。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="d5ce7-111">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="d5ce7-112">在创建支持请求之前，如果已处理调试日志，Microsoft 可以快速开始排查问题。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="d5ce7-113">**只有** **Microsoft** 请求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="d5ce7-114">本文中的"调试 **日志** "一词是指用于故障排除的日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="d5ce7-115">但是，为这些日志生成的文件的名称 **中包含术语诊断** 日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="d5ce7-116">收集和启用日志记录</span><span class="sxs-lookup"><span data-stu-id="d5ce7-116">Collect and enable logging</span></span>

<span data-ttu-id="d5ce7-117">出现问题时，必须收集日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="d5ce7-118">只需单击几下鼠标，即可将日志收集在一起。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="d5ce7-119">Windows：右键单击系统任务栏中的Teams图标，然后选择"收集 **支持文件"。**</span><span class="sxs-lookup"><span data-stu-id="d5ce7-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="d5ce7-120">Mac：选择"帮助"菜单，然后选择"**收集支持文件"。**</span><span class="sxs-lookup"><span data-stu-id="d5ce7-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="d5ce7-121">调试、桌面和媒体日志将收集到一个文件夹中，其名称为 MSTeams 诊断日志 <local data and time> 。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="d5ce7-122">向 Microsoft 支持人员提出支持请求时，可以压缩和共享此文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="d5ce7-123">该文件夹将包含桌面、会议 (媒体) 和调试 (Web) 。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="d5ce7-124">可以使用以下键盘快捷方式收集文件：</span><span class="sxs-lookup"><span data-stu-id="d5ce7-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="d5ce7-125">Windows：Crtl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="d5ce7-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="d5ce7-126">Mac：Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="d5ce7-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="d5ce7-127">默认情况下，媒体日志记录已关闭。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-127">Media logging is turned off by default.</span></span> <span data-ttu-id="d5ce7-128">若要启用媒体日志记录，用户必须在客户端中Teams选项。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="d5ce7-129">转到 **"设置**  >  **常规**"，然后选择"为会议诊断启用日志记录 **(重启Teams) 。**</span><span class="sxs-lookup"><span data-stu-id="d5ce7-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="d5ce7-130">必须Teams客户端才能开始日志记录。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="d5ce7-131">如果启用了媒体日志记录，"会议"文件夹中将包含其他文件，这些文件是调查音频和视频问题所必需的。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="d5ce7-132">如果未启用媒体日志记录，则可用日志数有限。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="d5ce7-133">下表概述了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="d5ce7-134">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="d5ce7-135">客户端</span><span class="sxs-lookup"><span data-stu-id="d5ce7-135">Client</span></span> |<span data-ttu-id="d5ce7-136">调试</span><span class="sxs-lookup"><span data-stu-id="d5ce7-136">Debug</span></span>|<span data-ttu-id="d5ce7-137">桌面</span><span class="sxs-lookup"><span data-stu-id="d5ce7-137">Desktop</span></span>|<span data-ttu-id="d5ce7-138">媒体</span><span class="sxs-lookup"><span data-stu-id="d5ce7-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="d5ce7-139">Web</span><span class="sxs-lookup"><span data-stu-id="d5ce7-139">Web</span></span>    |<span data-ttu-id="d5ce7-140">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-140">X</span></span>         |-         |-         |
|<span data-ttu-id="d5ce7-141">Windows</span><span class="sxs-lookup"><span data-stu-id="d5ce7-141">Windows</span></span>     |<span data-ttu-id="d5ce7-142">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-142">X</span></span>         |<span data-ttu-id="d5ce7-143">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-143">X</span></span>         |<span data-ttu-id="d5ce7-144">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-144">X</span></span>         |
|<span data-ttu-id="d5ce7-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d5ce7-145">Mac OSX</span></span>     |<span data-ttu-id="d5ce7-146">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-146">X</span></span>         |<span data-ttu-id="d5ce7-147">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-147">X</span></span>         |<span data-ttu-id="d5ce7-148">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-148">X</span></span>         |
|<span data-ttu-id="d5ce7-149">Linux</span><span class="sxs-lookup"><span data-stu-id="d5ce7-149">Linux</span></span>     |<span data-ttu-id="d5ce7-150">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-150">X</span></span>         |<span data-ttu-id="d5ce7-151">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-151">X</span></span>         |<span data-ttu-id="d5ce7-152">X</span><span class="sxs-lookup"><span data-stu-id="d5ce7-152">X</span></span>         |
|<span data-ttu-id="d5ce7-153">iOS</span><span class="sxs-lookup"><span data-stu-id="d5ce7-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="d5ce7-154">Android</span><span class="sxs-lookup"><span data-stu-id="d5ce7-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="d5ce7-155">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="d5ce7-156">调试日志</span><span class="sxs-lookup"><span data-stu-id="d5ce7-156">Debug logs</span></span>

<span data-ttu-id="d5ce7-157">请参阅收集和 _启用日志记录_ 部分，Windows和 Mac 说明。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="d5ce7-158">调试日志由 Windows Mac 桌面客户端以及基于浏览器的客户端生成。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="d5ce7-159">日志基于文本，从下而上读取。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="d5ce7-160">可以使用任何基于文本的编辑器读取这些日志，并且登录到客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="d5ce7-161">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="d5ce7-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="d5ce7-162">登录</span><span class="sxs-lookup"><span data-stu-id="d5ce7-162">Login</span></span>

-   <span data-ttu-id="d5ce7-163">到中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="d5ce7-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="d5ce7-164">通话/对话</span><span class="sxs-lookup"><span data-stu-id="d5ce7-164">Call/conversation</span></span>

<span data-ttu-id="d5ce7-165">收集 Linux 日志：键盘快捷方式：Ctrl + Alt + Shift + 1 文件将在 ~/Downloads 中提供</span><span class="sxs-lookup"><span data-stu-id="d5ce7-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="d5ce7-166">收集浏览器日志：键盘快捷方式：Crtl + Alt + Shift + 1 %userprofile%\Downloads 中提供文件</span><span class="sxs-lookup"><span data-stu-id="d5ce7-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="d5ce7-167">媒体日志</span><span class="sxs-lookup"><span data-stu-id="d5ce7-167">Media logs</span></span>

<span data-ttu-id="d5ce7-168">请参阅收集和 _启用日志记录_ 部分，Windows和 Mac 说明。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="d5ce7-169">媒体日志包含有关会议中音频、视频和屏幕共享的Teams数据。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="d5ce7-170">它们对于链接到呼叫相关问题的支持案例是必需的。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="d5ce7-171">默认情况下，媒体日志记录已关闭。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-171">Media logging is turned off by default.</span></span> <span data-ttu-id="d5ce7-172">若要记录会议Teams数据，用户必须在客户端中打开Teams选项。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="d5ce7-173">转到 **"设置** 常规"，选中"为会议诊断启用日志记录 ("Teams) "复选框，重新启动Teams并重现  >  问题。 </span><span class="sxs-lookup"><span data-stu-id="d5ce7-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="d5ce7-174">将日志文件发送给 Microsoft 支持人员时，请验证日志文件的时间戳，确保日志涵盖重现问题的时间范围。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="d5ce7-175">收集 Linux 日志：这些文件将在 ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog 和 *~/.config/Microsoft/Microsoft Teams/skylib/*.blog 中提供。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="d5ce7-176">下面是生成的日志文件及其包含的信息的列表。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="d5ce7-177">日志文件名</span><span class="sxs-lookup"><span data-stu-id="d5ce7-177">Log file name</span></span>  |<span data-ttu-id="d5ce7-178">说明</span><span class="sxs-lookup"><span data-stu-id="d5ce7-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d5ce7-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="d5ce7-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="d5ce7-180">包含与媒体堆栈有关的信息。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-180">Contains information related to the media stack.</span></span> <span data-ttu-id="d5ce7-181">这包括通道状态，例如分辨率、使用的解码器、编码器，以及发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 状态。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="d5ce7-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="d5ce7-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="d5ce7-183">记录与远程控制操作相关的信息，例如提供控制时时间戳和鼠标指针信息。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="d5ce7-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="d5ce7-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="d5ce7-185">记录媒体堆栈跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="d5ce7-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="d5ce7-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="d5ce7-187">包含与媒体代理有关的信息，包括呈现质量。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="d5ce7-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="d5ce7-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="d5ce7-189">在 ts-calling API 中记录事件。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="d5ce7-190">桌面日志</span><span class="sxs-lookup"><span data-stu-id="d5ce7-190">Desktop logs</span></span>

<span data-ttu-id="d5ce7-191">请参阅收集和 _启用日志记录_ 部分，Windows和 Mac 说明。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="d5ce7-192">桌面日志也称为启动程序日志，包含桌面客户端与浏览器之间发生的日志数据。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="d5ce7-193">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="d5ce7-194">日志基于文本，可以使用任何基于文本的编辑器以自上而下的格式读取。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="d5ce7-195">若要收集 Linux 的日志：单击系统Microsoft Teams中的"日志"图标，然后选择"获取 **日志"。**</span><span class="sxs-lookup"><span data-stu-id="d5ce7-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="d5ce7-196">这些文件将在 ~/.config/Microsoft/Microsoft Teams/logs.txt 中提供。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="d5ce7-197">浏览器跟踪</span><span class="sxs-lookup"><span data-stu-id="d5ce7-197">Browser trace</span></span>

<span data-ttu-id="d5ce7-198">对于某些类别的错误，Microsoft 支持可能会要求你收集浏览器跟踪。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="d5ce7-199">此信息提供有关发生错误时客户端Teams状态的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="d5ce7-200">在开始浏览器跟踪之前，请确保已登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="d5ce7-201">在开始跟踪之前，必须这样做，以便跟踪不包含敏感的登录信息。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="d5ce7-202">登录后，根据浏览器情况选择以下链接之一，然后按照提供的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="d5ce7-203">Chrome & Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="d5ce7-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="d5ce7-204">Edge</span><span class="sxs-lookup"><span data-stu-id="d5ce7-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="d5ce7-205">Safari</span><span class="sxs-lookup"><span data-stu-id="d5ce7-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="d5ce7-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="d5ce7-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="d5ce7-207">在步骤中，将 Azure 门户的所有引用替换为 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="d5ce7-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d5ce7-208">相关主题</span><span class="sxs-lookup"><span data-stu-id="d5ce7-208">Related topics</span></span>

[<span data-ttu-id="d5ce7-209">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="d5ce7-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
