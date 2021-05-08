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
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264872"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="3378d-103">在对 Microsoft Teams 进行故障排除时使用日志文件</span><span class="sxs-lookup"><span data-stu-id="3378d-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="3378d-104">有三种类型的日志文件由客户端自动生成，可利用它们来帮助排查Microsoft Teams：</span><span class="sxs-lookup"><span data-stu-id="3378d-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="3378d-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="3378d-105">Debug logs</span></span>

-   <span data-ttu-id="3378d-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="3378d-106">Media logs</span></span>

-   <span data-ttu-id="3378d-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="3378d-107">Desktop logs</span></span>

<span data-ttu-id="3378d-108">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="3378d-109">在创建支持请求之前，如果已处理调试日志，Microsoft 可以快速开始排查问题。</span><span class="sxs-lookup"><span data-stu-id="3378d-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="3378d-110">**只有** **Microsoft** 请求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="3378d-111">本文中的"调试 **日志** "一词是指用于故障排除的日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="3378d-112">但是，为这些日志生成的文件的名称 **中包含术语诊断** 日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="3378d-113">下表概述了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="3378d-114">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="3378d-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="3378d-115">客户端</span><span class="sxs-lookup"><span data-stu-id="3378d-115">Client</span></span> |<span data-ttu-id="3378d-116">调试</span><span class="sxs-lookup"><span data-stu-id="3378d-116">Debug</span></span>|<span data-ttu-id="3378d-117">桌面</span><span class="sxs-lookup"><span data-stu-id="3378d-117">Desktop</span></span>|<span data-ttu-id="3378d-118">媒体</span><span class="sxs-lookup"><span data-stu-id="3378d-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="3378d-119">Web</span><span class="sxs-lookup"><span data-stu-id="3378d-119">Web</span></span>    |<span data-ttu-id="3378d-120">X</span><span class="sxs-lookup"><span data-stu-id="3378d-120">X</span></span>         |-         |-         |
|<span data-ttu-id="3378d-121">Windows</span><span class="sxs-lookup"><span data-stu-id="3378d-121">Windows</span></span>     |<span data-ttu-id="3378d-122">X</span><span class="sxs-lookup"><span data-stu-id="3378d-122">X</span></span>         |<span data-ttu-id="3378d-123">X</span><span class="sxs-lookup"><span data-stu-id="3378d-123">X</span></span>         |<span data-ttu-id="3378d-124">X</span><span class="sxs-lookup"><span data-stu-id="3378d-124">X</span></span>         |
|<span data-ttu-id="3378d-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3378d-125">Mac OSX</span></span>     |<span data-ttu-id="3378d-126">X</span><span class="sxs-lookup"><span data-stu-id="3378d-126">X</span></span>         |<span data-ttu-id="3378d-127">X</span><span class="sxs-lookup"><span data-stu-id="3378d-127">X</span></span>         |<span data-ttu-id="3378d-128">X</span><span class="sxs-lookup"><span data-stu-id="3378d-128">X</span></span>         |
|<span data-ttu-id="3378d-129">Linux</span><span class="sxs-lookup"><span data-stu-id="3378d-129">Linux</span></span>     |<span data-ttu-id="3378d-130">X</span><span class="sxs-lookup"><span data-stu-id="3378d-130">X</span></span>         |<span data-ttu-id="3378d-131">X</span><span class="sxs-lookup"><span data-stu-id="3378d-131">X</span></span>         |<span data-ttu-id="3378d-132">X</span><span class="sxs-lookup"><span data-stu-id="3378d-132">X</span></span>         |
|<span data-ttu-id="3378d-133">iOS</span><span class="sxs-lookup"><span data-stu-id="3378d-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="3378d-134">Android</span><span class="sxs-lookup"><span data-stu-id="3378d-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="3378d-135">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="3378d-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="3378d-136">调试日志</span><span class="sxs-lookup"><span data-stu-id="3378d-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="3378d-137">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="3378d-138">调试日志由 Windows Mac 桌面客户端以及基于浏览器的客户端生成。</span><span class="sxs-lookup"><span data-stu-id="3378d-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="3378d-139">日志基于文本，从下而上读取。</span><span class="sxs-lookup"><span data-stu-id="3378d-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="3378d-140">可以使用任何基于文本的编辑器读取这些日志，并且登录到客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="3378d-141">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="3378d-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="3378d-142">登录</span><span class="sxs-lookup"><span data-stu-id="3378d-142">Login</span></span>

-   <span data-ttu-id="3378d-143">到中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="3378d-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="3378d-144">通话/对话</span><span class="sxs-lookup"><span data-stu-id="3378d-144">Call/conversation</span></span>

<span data-ttu-id="3378d-145">调试日志是使用以下特定于 OS 的方法生成的：</span><span class="sxs-lookup"><span data-stu-id="3378d-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="3378d-146">Windows：</span><span class="sxs-lookup"><span data-stu-id="3378d-146">Windows:</span></span>

      <span data-ttu-id="3378d-147">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="3378d-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="3378d-148">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="3378d-148">Mac OSX:</span></span>

      <span data-ttu-id="3378d-149">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="3378d-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="3378d-150">Linux：</span><span class="sxs-lookup"><span data-stu-id="3378d-150">Linux:</span></span>

      <span data-ttu-id="3378d-151">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="3378d-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="3378d-152">调试日志会自动下载到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="3378d-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="3378d-153">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="3378d-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="3378d-154">Mac OSX：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="3378d-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="3378d-155">Linux：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="3378d-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="3378d-156">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="3378d-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="3378d-157">媒体日志</span><span class="sxs-lookup"><span data-stu-id="3378d-157">Media logs</span></span>
---------------------------

<span data-ttu-id="3378d-158">媒体日志包含有关会议中音频、视频和屏幕共享的Teams数据。</span><span class="sxs-lookup"><span data-stu-id="3378d-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="3378d-159">它们对于链接到呼叫相关问题的支持案例是必需的。</span><span class="sxs-lookup"><span data-stu-id="3378d-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="3378d-160">默认情况下，媒体日志记录已关闭。</span><span class="sxs-lookup"><span data-stu-id="3378d-160">Media logging is turned off by default.</span></span> <span data-ttu-id="3378d-161">若要记录会议Teams数据，用户必须在客户端中打开Teams选项。</span><span class="sxs-lookup"><span data-stu-id="3378d-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="3378d-162">转到 **"设置** 常规"，选中"为会议诊断启用日志记录 ("Teams) "复选框，重新启动Teams并重现  >  问题。 </span><span class="sxs-lookup"><span data-stu-id="3378d-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="3378d-163">下表概述了媒体日志位置。</span><span class="sxs-lookup"><span data-stu-id="3378d-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="3378d-164">将日志文件发送给 Microsoft 支持人员时，请验证日志文件的时间戳，确保日志涵盖重现问题的时间范围。</span><span class="sxs-lookup"><span data-stu-id="3378d-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="3378d-165">客户端</span><span class="sxs-lookup"><span data-stu-id="3378d-165">Client</span></span> |<span data-ttu-id="3378d-166">位置</span><span class="sxs-lookup"><span data-stu-id="3378d-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="3378d-167">Windows</span><span class="sxs-lookup"><span data-stu-id="3378d-167">Windows</span></span>     |<span data-ttu-id="3378d-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="3378d-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="3378d-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="3378d-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="3378d-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3378d-171">Mac OSX</span></span>     |<span data-ttu-id="3378d-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="3378d-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="3378d-174">Linux</span><span class="sxs-lookup"><span data-stu-id="3378d-174">Linux</span></span>       |<span data-ttu-id="3378d-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="3378d-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="3378d-177">下面是生成的日志文件及其包含的信息的列表。</span><span class="sxs-lookup"><span data-stu-id="3378d-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="3378d-178">日志文件名</span><span class="sxs-lookup"><span data-stu-id="3378d-178">Log file name</span></span>  |<span data-ttu-id="3378d-179">说明</span><span class="sxs-lookup"><span data-stu-id="3378d-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="3378d-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="3378d-181">包含与媒体堆栈有关的信息。</span><span class="sxs-lookup"><span data-stu-id="3378d-181">Contains information related to the media stack.</span></span> <span data-ttu-id="3378d-182">这包括通道状态，例如分辨率、使用的解码器、编码器，以及发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 状态。</span><span class="sxs-lookup"><span data-stu-id="3378d-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="3378d-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="3378d-184">记录与远程控制操作相关的信息，例如提供控制时时间戳和鼠标指针信息。</span><span class="sxs-lookup"><span data-stu-id="3378d-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="3378d-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="3378d-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="3378d-186">记录媒体堆栈跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="3378d-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="3378d-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="3378d-188">包含与媒体代理有关的信息，包括呈现质量。</span><span class="sxs-lookup"><span data-stu-id="3378d-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="3378d-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="3378d-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="3378d-190">在 ts-calling API 中记录事件。</span><span class="sxs-lookup"><span data-stu-id="3378d-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="3378d-191">桌面日志</span><span class="sxs-lookup"><span data-stu-id="3378d-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="3378d-192">桌面日志也称为启动程序日志，包含桌面客户端与浏览器之间发生的日志数据。</span><span class="sxs-lookup"><span data-stu-id="3378d-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="3378d-193">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="3378d-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="3378d-194">日志基于文本，可以使用任何基于文本的编辑器以自上而下的格式读取。</span><span class="sxs-lookup"><span data-stu-id="3378d-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="3378d-195">Windows：</span><span class="sxs-lookup"><span data-stu-id="3378d-195">Windows:</span></span>

 - <span data-ttu-id="3378d-196">右 **键单击Microsoft Teams** 任务栏中的"日志"图标，然后选择"**获取日志"。**</span><span class="sxs-lookup"><span data-stu-id="3378d-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="3378d-197">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="3378d-197">Mac OsX:</span></span>

 - <span data-ttu-id="3378d-198">从 **"帮助"** 下拉菜单 **中选择"** 获取日志"。</span><span class="sxs-lookup"><span data-stu-id="3378d-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="3378d-199">Linux：</span><span class="sxs-lookup"><span data-stu-id="3378d-199">Linux:</span></span>

 - <span data-ttu-id="3378d-200">单击系统 **Microsoft Teams** 中的"日志"图标，然后选择"**获取日志"。**</span><span class="sxs-lookup"><span data-stu-id="3378d-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="3378d-201">客户端</span><span class="sxs-lookup"><span data-stu-id="3378d-201">Client</span></span> |<span data-ttu-id="3378d-202">位置</span><span class="sxs-lookup"><span data-stu-id="3378d-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="3378d-203">Windows</span><span class="sxs-lookup"><span data-stu-id="3378d-203">Windows</span></span>     |<span data-ttu-id="3378d-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="3378d-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="3378d-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3378d-205">Mac OSX</span></span>     |<span data-ttu-id="3378d-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="3378d-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="3378d-207">Linux</span><span class="sxs-lookup"><span data-stu-id="3378d-207">Linux</span></span>       |<span data-ttu-id="3378d-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="3378d-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="3378d-209">浏览器跟踪</span><span class="sxs-lookup"><span data-stu-id="3378d-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="3378d-210">对于某些类别的错误，Microsoft 支持可能会要求你收集浏览器跟踪。</span><span class="sxs-lookup"><span data-stu-id="3378d-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="3378d-211">此信息提供有关发生错误时客户端Teams状态的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="3378d-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="3378d-212">在开始浏览器跟踪之前，请确保已登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="3378d-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="3378d-213">在开始跟踪之前，必须这样做，以便跟踪不包含敏感的登录信息。</span><span class="sxs-lookup"><span data-stu-id="3378d-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="3378d-214">登录后，根据浏览器情况选择以下链接之一，然后按照提供的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="3378d-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="3378d-215">Chrome & Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="3378d-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="3378d-216">Edge</span><span class="sxs-lookup"><span data-stu-id="3378d-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="3378d-217">Safari</span><span class="sxs-lookup"><span data-stu-id="3378d-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="3378d-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="3378d-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="3378d-219">在步骤中，将 Azure 门户的所有引用替换为 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="3378d-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3378d-220">相关主题</span><span class="sxs-lookup"><span data-stu-id="3378d-220">Related topics</span></span>

[<span data-ttu-id="3378d-221">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="3378d-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
