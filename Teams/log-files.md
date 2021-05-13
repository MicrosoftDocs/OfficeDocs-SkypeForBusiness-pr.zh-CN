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
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337739"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="46d32-103">使用日志文件监视和排查Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46d32-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="46d32-104">有三种类型的日志文件由客户端自动生成，可利用它们来帮助监视和排查Teams：</span><span class="sxs-lookup"><span data-stu-id="46d32-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="46d32-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="46d32-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="46d32-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="46d32-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="46d32-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="46d32-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="46d32-108">本文介绍三个日志及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="46d32-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="46d32-109">有关排查特定问题的信息，请参阅：Teams[故障排除。](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="46d32-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="46d32-110">若要了解如何联系支持人员，请参阅 [获取支持](/microsoft-365/business-video/get-help-support)。</span><span class="sxs-lookup"><span data-stu-id="46d32-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="46d32-111">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="46d32-112">在创建支持请求之前，如果已处理调试日志，Microsoft 可以快速开始排查问题。</span><span class="sxs-lookup"><span data-stu-id="46d32-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="46d32-113">**只有** **Microsoft** 请求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="46d32-114">本文中的"调试 **日志** "一词是指用于故障排除的日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="46d32-115">但是，为这些日志生成的文件的名称 **中包含术语诊断** 日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="46d32-116">下表概述了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="46d32-117">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="46d32-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="46d32-118">客户端</span><span class="sxs-lookup"><span data-stu-id="46d32-118">Client</span></span> |<span data-ttu-id="46d32-119">调试</span><span class="sxs-lookup"><span data-stu-id="46d32-119">Debug</span></span>|<span data-ttu-id="46d32-120">桌面</span><span class="sxs-lookup"><span data-stu-id="46d32-120">Desktop</span></span>|<span data-ttu-id="46d32-121">媒体</span><span class="sxs-lookup"><span data-stu-id="46d32-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="46d32-122">Web</span><span class="sxs-lookup"><span data-stu-id="46d32-122">Web</span></span>    |<span data-ttu-id="46d32-123">X</span><span class="sxs-lookup"><span data-stu-id="46d32-123">X</span></span>         |-         |-         |
|<span data-ttu-id="46d32-124">Windows</span><span class="sxs-lookup"><span data-stu-id="46d32-124">Windows</span></span>     |<span data-ttu-id="46d32-125">X</span><span class="sxs-lookup"><span data-stu-id="46d32-125">X</span></span>         |<span data-ttu-id="46d32-126">X</span><span class="sxs-lookup"><span data-stu-id="46d32-126">X</span></span>         |<span data-ttu-id="46d32-127">X</span><span class="sxs-lookup"><span data-stu-id="46d32-127">X</span></span>         |
|<span data-ttu-id="46d32-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="46d32-128">Mac OSX</span></span>     |<span data-ttu-id="46d32-129">X</span><span class="sxs-lookup"><span data-stu-id="46d32-129">X</span></span>         |<span data-ttu-id="46d32-130">X</span><span class="sxs-lookup"><span data-stu-id="46d32-130">X</span></span>         |<span data-ttu-id="46d32-131">X</span><span class="sxs-lookup"><span data-stu-id="46d32-131">X</span></span>         |
|<span data-ttu-id="46d32-132">Linux</span><span class="sxs-lookup"><span data-stu-id="46d32-132">Linux</span></span>     |<span data-ttu-id="46d32-133">X</span><span class="sxs-lookup"><span data-stu-id="46d32-133">X</span></span>         |<span data-ttu-id="46d32-134">X</span><span class="sxs-lookup"><span data-stu-id="46d32-134">X</span></span>         |<span data-ttu-id="46d32-135">X</span><span class="sxs-lookup"><span data-stu-id="46d32-135">X</span></span>         |
|<span data-ttu-id="46d32-136">iOS</span><span class="sxs-lookup"><span data-stu-id="46d32-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="46d32-137">Android</span><span class="sxs-lookup"><span data-stu-id="46d32-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="46d32-138">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="46d32-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="46d32-139">调试日志</span><span class="sxs-lookup"><span data-stu-id="46d32-139">Debug logs</span></span>

<span data-ttu-id="46d32-140">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="46d32-141">调试日志由 Windows Mac 桌面客户端以及基于浏览器的客户端生成。</span><span class="sxs-lookup"><span data-stu-id="46d32-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="46d32-142">日志基于文本，从下而上读取。</span><span class="sxs-lookup"><span data-stu-id="46d32-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="46d32-143">可以使用任何基于文本的编辑器读取这些日志，并且登录到客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="46d32-144">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="46d32-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="46d32-145">登录</span><span class="sxs-lookup"><span data-stu-id="46d32-145">Login</span></span>

-   <span data-ttu-id="46d32-146">到中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="46d32-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="46d32-147">通话/对话</span><span class="sxs-lookup"><span data-stu-id="46d32-147">Call/conversation</span></span>

<span data-ttu-id="46d32-148">调试日志是使用以下特定于 OS 的方法生成的：</span><span class="sxs-lookup"><span data-stu-id="46d32-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="46d32-149">Windows：</span><span class="sxs-lookup"><span data-stu-id="46d32-149">Windows:</span></span>

      <span data-ttu-id="46d32-150">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="46d32-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="46d32-151">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="46d32-151">Mac OSX:</span></span>

      <span data-ttu-id="46d32-152">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="46d32-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="46d32-153">Linux：</span><span class="sxs-lookup"><span data-stu-id="46d32-153">Linux:</span></span>

      <span data-ttu-id="46d32-154">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="46d32-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="46d32-155">调试日志会自动下载到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="46d32-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="46d32-156">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="46d32-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="46d32-157">Mac OSX：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="46d32-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="46d32-158">Linux：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="46d32-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="46d32-159">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="46d32-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="46d32-160">媒体日志</span><span class="sxs-lookup"><span data-stu-id="46d32-160">Media logs</span></span>

<span data-ttu-id="46d32-161">媒体日志包含有关会议中音频、视频和屏幕共享的Teams数据。</span><span class="sxs-lookup"><span data-stu-id="46d32-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="46d32-162">它们对于链接到呼叫相关问题的支持案例是必需的。</span><span class="sxs-lookup"><span data-stu-id="46d32-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="46d32-163">默认情况下，媒体日志记录已关闭。</span><span class="sxs-lookup"><span data-stu-id="46d32-163">Media logging is turned off by default.</span></span> <span data-ttu-id="46d32-164">若要记录会议Teams数据，用户必须在客户端中打开Teams选项。</span><span class="sxs-lookup"><span data-stu-id="46d32-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="46d32-165">转到 **"设置** 常规"，选中"为会议诊断启用日志记录 ("Teams) "复选框，重新启动Teams并重现  >  问题。 </span><span class="sxs-lookup"><span data-stu-id="46d32-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="46d32-166">下表概述了媒体日志位置。</span><span class="sxs-lookup"><span data-stu-id="46d32-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="46d32-167">将日志文件发送给 Microsoft 支持人员时，请验证日志文件的时间戳，确保日志涵盖重现问题的时间范围。</span><span class="sxs-lookup"><span data-stu-id="46d32-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="46d32-168">客户端</span><span class="sxs-lookup"><span data-stu-id="46d32-168">Client</span></span> |<span data-ttu-id="46d32-169">位置</span><span class="sxs-lookup"><span data-stu-id="46d32-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="46d32-170">Windows</span><span class="sxs-lookup"><span data-stu-id="46d32-170">Windows</span></span>     |<span data-ttu-id="46d32-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="46d32-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="46d32-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="46d32-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="46d32-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="46d32-174">Mac OSX</span></span>     |<span data-ttu-id="46d32-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="46d32-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="46d32-177">Linux</span><span class="sxs-lookup"><span data-stu-id="46d32-177">Linux</span></span>       |<span data-ttu-id="46d32-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="46d32-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="46d32-180">下面是生成的日志文件及其包含的信息的列表。</span><span class="sxs-lookup"><span data-stu-id="46d32-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="46d32-181">日志文件名</span><span class="sxs-lookup"><span data-stu-id="46d32-181">Log file name</span></span>  |<span data-ttu-id="46d32-182">说明</span><span class="sxs-lookup"><span data-stu-id="46d32-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="46d32-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="46d32-184">包含与媒体堆栈有关的信息。</span><span class="sxs-lookup"><span data-stu-id="46d32-184">Contains information related to the media stack.</span></span> <span data-ttu-id="46d32-185">这包括通道状态，例如分辨率、使用的解码器、编码器，以及发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 状态。</span><span class="sxs-lookup"><span data-stu-id="46d32-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="46d32-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="46d32-187">记录与远程控制操作相关的信息，例如提供控制时时间戳和鼠标指针信息。</span><span class="sxs-lookup"><span data-stu-id="46d32-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="46d32-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="46d32-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="46d32-189">记录媒体堆栈跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="46d32-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="46d32-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="46d32-191">包含与媒体代理有关的信息，包括呈现质量。</span><span class="sxs-lookup"><span data-stu-id="46d32-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="46d32-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="46d32-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="46d32-193">在 ts-calling API 中记录事件。</span><span class="sxs-lookup"><span data-stu-id="46d32-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="46d32-194">桌面日志</span><span class="sxs-lookup"><span data-stu-id="46d32-194">Desktop logs</span></span>

<span data-ttu-id="46d32-195">桌面日志也称为启动程序日志，包含桌面客户端与浏览器之间发生的日志数据。</span><span class="sxs-lookup"><span data-stu-id="46d32-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="46d32-196">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="46d32-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="46d32-197">日志基于文本，可以使用任何基于文本的编辑器以自上而下的格式读取。</span><span class="sxs-lookup"><span data-stu-id="46d32-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="46d32-198">Windows：</span><span class="sxs-lookup"><span data-stu-id="46d32-198">Windows:</span></span>

 - <span data-ttu-id="46d32-199">右 **键单击Microsoft Teams** 任务栏中的"日志"图标，然后选择"**获取日志"。**</span><span class="sxs-lookup"><span data-stu-id="46d32-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="46d32-200">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="46d32-200">Mac OsX:</span></span>

 - <span data-ttu-id="46d32-201">从 **"帮助"** 下拉菜单 **中选择"** 获取日志"。</span><span class="sxs-lookup"><span data-stu-id="46d32-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="46d32-202">Linux：</span><span class="sxs-lookup"><span data-stu-id="46d32-202">Linux:</span></span>

 - <span data-ttu-id="46d32-203">单击系统 **Microsoft Teams** 中的"日志"图标，然后选择"**获取日志"。**</span><span class="sxs-lookup"><span data-stu-id="46d32-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="46d32-204">客户端</span><span class="sxs-lookup"><span data-stu-id="46d32-204">Client</span></span> |<span data-ttu-id="46d32-205">位置</span><span class="sxs-lookup"><span data-stu-id="46d32-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="46d32-206">Windows</span><span class="sxs-lookup"><span data-stu-id="46d32-206">Windows</span></span>     |<span data-ttu-id="46d32-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="46d32-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="46d32-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="46d32-208">Mac OSX</span></span>     |<span data-ttu-id="46d32-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="46d32-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="46d32-210">Linux</span><span class="sxs-lookup"><span data-stu-id="46d32-210">Linux</span></span>       |<span data-ttu-id="46d32-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="46d32-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="46d32-212">浏览器跟踪</span><span class="sxs-lookup"><span data-stu-id="46d32-212">Browser trace</span></span>

<span data-ttu-id="46d32-213">对于某些类别的错误，Microsoft 支持可能会要求你收集浏览器跟踪。</span><span class="sxs-lookup"><span data-stu-id="46d32-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="46d32-214">此信息提供有关发生错误时客户端Teams状态的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="46d32-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="46d32-215">在开始浏览器跟踪之前，请确保已登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="46d32-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="46d32-216">在开始跟踪之前，必须这样做，以便跟踪不包含敏感的登录信息。</span><span class="sxs-lookup"><span data-stu-id="46d32-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="46d32-217">登录后，根据浏览器情况选择以下链接之一，然后按照提供的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="46d32-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="46d32-218">Chrome & Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="46d32-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="46d32-219">Edge</span><span class="sxs-lookup"><span data-stu-id="46d32-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="46d32-220">Safari</span><span class="sxs-lookup"><span data-stu-id="46d32-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="46d32-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="46d32-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="46d32-222">在步骤中，将 Azure 门户的所有引用替换为 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="46d32-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="46d32-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="46d32-223">Related topics</span></span>

[<span data-ttu-id="46d32-224">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="46d32-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
