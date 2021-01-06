---
title: 在对 Microsoft Teams 进行故障排除时使用日志文件
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 了解 Microsoft Teams 生成的调试、媒体和桌面日志，可以在哪里找到它们，以及它们如何帮助进行故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761090"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="f420b-103">在对 Microsoft Teams 进行故障排除时使用日志文件</span><span class="sxs-lookup"><span data-stu-id="f420b-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="f420b-104">客户端自动生成三种类型的日志文件，可利用它们来帮助排查 Microsoft Teams 问题：</span><span class="sxs-lookup"><span data-stu-id="f420b-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="f420b-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="f420b-105">Debug logs</span></span>

-   <span data-ttu-id="f420b-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="f420b-106">Media logs</span></span>

-   <span data-ttu-id="f420b-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="f420b-107">Desktop logs</span></span>

<span data-ttu-id="f420b-108">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="f420b-109">在创建支持请求之前，将调试日志放在手边后，Microsoft 可以快速开始排查问题。</span><span class="sxs-lookup"><span data-stu-id="f420b-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="f420b-110">**只有** **Microsoft** 提出请求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="f420b-111">本文中的" **调试** 日志"一词是指用于故障排除的日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="f420b-112">但是，为这些日志生成的文件的名称中 **将包含诊断日志** 一词。</span><span class="sxs-lookup"><span data-stu-id="f420b-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="f420b-113">下表概述了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="f420b-114">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="f420b-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="f420b-115">客户端</span><span class="sxs-lookup"><span data-stu-id="f420b-115">Client</span></span> |<span data-ttu-id="f420b-116">调试</span><span class="sxs-lookup"><span data-stu-id="f420b-116">Debug</span></span>|<span data-ttu-id="f420b-117">桌面</span><span class="sxs-lookup"><span data-stu-id="f420b-117">Desktop</span></span>|<span data-ttu-id="f420b-118">媒体</span><span class="sxs-lookup"><span data-stu-id="f420b-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="f420b-119">Web</span><span class="sxs-lookup"><span data-stu-id="f420b-119">Web</span></span>    |<span data-ttu-id="f420b-120">X</span><span class="sxs-lookup"><span data-stu-id="f420b-120">X</span></span>         |-         |-         |
|<span data-ttu-id="f420b-121">Windows</span><span class="sxs-lookup"><span data-stu-id="f420b-121">Windows</span></span>     |<span data-ttu-id="f420b-122">X</span><span class="sxs-lookup"><span data-stu-id="f420b-122">X</span></span>         |<span data-ttu-id="f420b-123">X</span><span class="sxs-lookup"><span data-stu-id="f420b-123">X</span></span>         |<span data-ttu-id="f420b-124">X</span><span class="sxs-lookup"><span data-stu-id="f420b-124">X</span></span>         |
|<span data-ttu-id="f420b-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f420b-125">Mac OSX</span></span>     |<span data-ttu-id="f420b-126">X</span><span class="sxs-lookup"><span data-stu-id="f420b-126">X</span></span>         |<span data-ttu-id="f420b-127">X</span><span class="sxs-lookup"><span data-stu-id="f420b-127">X</span></span>         |<span data-ttu-id="f420b-128">X</span><span class="sxs-lookup"><span data-stu-id="f420b-128">X</span></span>         |
|<span data-ttu-id="f420b-129">Linux</span><span class="sxs-lookup"><span data-stu-id="f420b-129">Linux</span></span>     |<span data-ttu-id="f420b-130">X</span><span class="sxs-lookup"><span data-stu-id="f420b-130">X</span></span>         |<span data-ttu-id="f420b-131">X</span><span class="sxs-lookup"><span data-stu-id="f420b-131">X</span></span>         |<span data-ttu-id="f420b-132">X</span><span class="sxs-lookup"><span data-stu-id="f420b-132">X</span></span>         |
|<span data-ttu-id="f420b-133">iOS</span><span class="sxs-lookup"><span data-stu-id="f420b-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="f420b-134">Android</span><span class="sxs-lookup"><span data-stu-id="f420b-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="f420b-135">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="f420b-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="f420b-136">调试日志</span><span class="sxs-lookup"><span data-stu-id="f420b-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="f420b-137">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="f420b-138">调试日志由 Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成。</span><span class="sxs-lookup"><span data-stu-id="f420b-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="f420b-139">日志基于文本，从下而上读取。</span><span class="sxs-lookup"><span data-stu-id="f420b-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="f420b-140">可以使用任何基于文本的编辑器读取这些日志，在登录到客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="f420b-141">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="f420b-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="f420b-142">登录</span><span class="sxs-lookup"><span data-stu-id="f420b-142">Login</span></span>

-   <span data-ttu-id="f420b-143">到中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="f420b-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="f420b-144">通话/对话</span><span class="sxs-lookup"><span data-stu-id="f420b-144">Call/conversation</span></span>

<span data-ttu-id="f420b-145">调试日志是使用以下特定于 OS 的方法生成的：</span><span class="sxs-lookup"><span data-stu-id="f420b-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="f420b-146">Windows：</span><span class="sxs-lookup"><span data-stu-id="f420b-146">Windows:</span></span>

      <span data-ttu-id="f420b-147">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f420b-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="f420b-148">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="f420b-148">Mac OSX:</span></span>

      <span data-ttu-id="f420b-149">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="f420b-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="f420b-150">Linux：</span><span class="sxs-lookup"><span data-stu-id="f420b-150">Linux:</span></span>

      <span data-ttu-id="f420b-151">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f420b-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="f420b-152">调试日志会自动下载到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="f420b-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="f420b-153">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="f420b-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="f420b-154">Mac OSX：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="f420b-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="f420b-155">Linux：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="f420b-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="f420b-156">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="f420b-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="f420b-157">媒体日志</span><span class="sxs-lookup"><span data-stu-id="f420b-157">Media logs</span></span>
---------------------------

<span data-ttu-id="f420b-158">媒体日志包含有关 Teams 会议中音频、视频和屏幕共享的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="f420b-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="f420b-159">它们对于链接到呼叫相关问题的支持案例是必需的。</span><span class="sxs-lookup"><span data-stu-id="f420b-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="f420b-160">默认情况下，媒体日志记录已关闭。</span><span class="sxs-lookup"><span data-stu-id="f420b-160">Media logging is turned off by default.</span></span> <span data-ttu-id="f420b-161">若要记录 Teams 会议的诊断数据，用户必须在 Teams 客户端中启用该选项。</span><span class="sxs-lookup"><span data-stu-id="f420b-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="f420b-162">转到"**设置** 常规"，选中"为会议诊断启用日志记录  >  **(需要重新启动 Teams**) 复选框，重新启动 Teams 并重现问题。</span><span class="sxs-lookup"><span data-stu-id="f420b-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="f420b-163">下表概述了媒体日志位置。</span><span class="sxs-lookup"><span data-stu-id="f420b-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="f420b-164">将日志文件发送给 Microsoft 支持人员时，请验证日志文件的时间戳，确保日志涵盖重现问题的时间范围。</span><span class="sxs-lookup"><span data-stu-id="f420b-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="f420b-165">客户端</span><span class="sxs-lookup"><span data-stu-id="f420b-165">Client</span></span> |<span data-ttu-id="f420b-166">位置</span><span class="sxs-lookup"><span data-stu-id="f420b-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f420b-167">Windows</span><span class="sxs-lookup"><span data-stu-id="f420b-167">Windows</span></span>     |<span data-ttu-id="f420b-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="f420b-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="f420b-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="f420b-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="f420b-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f420b-171">Mac OSX</span></span>     |<span data-ttu-id="f420b-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="f420b-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="f420b-174">Linux</span><span class="sxs-lookup"><span data-stu-id="f420b-174">Linux</span></span>       |<span data-ttu-id="f420b-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="f420b-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="f420b-177">下面是生成的日志文件及其包含的信息的列表。</span><span class="sxs-lookup"><span data-stu-id="f420b-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="f420b-178">日志文件名</span><span class="sxs-lookup"><span data-stu-id="f420b-178">Log file name</span></span>  |<span data-ttu-id="f420b-179">描述</span><span class="sxs-lookup"><span data-stu-id="f420b-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f420b-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="f420b-181">包含与媒体堆栈有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f420b-181">Contains information related to the media stack.</span></span> <span data-ttu-id="f420b-182">这包括通道状态，例如分辨率、使用的解码器、编码器以及发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 会话状态。</span><span class="sxs-lookup"><span data-stu-id="f420b-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="f420b-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="f420b-184">记录与远程控制操作相关的信息，例如，提供控制时时间戳和鼠标指针信息。</span><span class="sxs-lookup"><span data-stu-id="f420b-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="f420b-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="f420b-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="f420b-186">记录媒体堆栈跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="f420b-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="f420b-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="f420b-188">包含与媒体代理有关的信息，包括呈现质量。</span><span class="sxs-lookup"><span data-stu-id="f420b-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="f420b-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="f420b-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="f420b-190">在调用 ts 的 API 中记录事件。</span><span class="sxs-lookup"><span data-stu-id="f420b-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="f420b-191">桌面日志</span><span class="sxs-lookup"><span data-stu-id="f420b-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="f420b-192">桌面日志也称为启动程序日志，包含桌面客户端与浏览器之间发生的日志数据。</span><span class="sxs-lookup"><span data-stu-id="f420b-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="f420b-193">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="f420b-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="f420b-194">日志是基于文本的，可以使用任何基于文本的编辑器以自上而下的格式读取。</span><span class="sxs-lookup"><span data-stu-id="f420b-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="f420b-195">Windows：</span><span class="sxs-lookup"><span data-stu-id="f420b-195">Windows:</span></span>

 - <span data-ttu-id="f420b-196">右键单击 **系统任务栏** 中的 Microsoft Teams 图标，然后选择"**获取日志"。**</span><span class="sxs-lookup"><span data-stu-id="f420b-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="f420b-197">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="f420b-197">Mac OsX:</span></span>

 - <span data-ttu-id="f420b-198">从 **"帮助"** 下拉菜单 **中选择** "获取日志"。</span><span class="sxs-lookup"><span data-stu-id="f420b-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="f420b-199">Linux：</span><span class="sxs-lookup"><span data-stu-id="f420b-199">Linux:</span></span>

 - <span data-ttu-id="f420b-200">单击系统托盘 **中的 Microsoft Teams** 图标，然后选择"**获取日志"。**</span><span class="sxs-lookup"><span data-stu-id="f420b-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="f420b-201">客户端</span><span class="sxs-lookup"><span data-stu-id="f420b-201">Client</span></span> |<span data-ttu-id="f420b-202">位置</span><span class="sxs-lookup"><span data-stu-id="f420b-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f420b-203">Windows</span><span class="sxs-lookup"><span data-stu-id="f420b-203">Windows</span></span>     |<span data-ttu-id="f420b-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="f420b-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="f420b-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f420b-205">Mac OSX</span></span>     |<span data-ttu-id="f420b-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="f420b-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="f420b-207">Linux</span><span class="sxs-lookup"><span data-stu-id="f420b-207">Linux</span></span>       |<span data-ttu-id="f420b-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="f420b-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="f420b-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="f420b-209">Related topics</span></span>

[<span data-ttu-id="f420b-210">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="f420b-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
