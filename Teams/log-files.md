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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650825"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="96c17-103">在对 Microsoft Teams 进行故障排除时使用日志文件</span><span class="sxs-lookup"><span data-stu-id="96c17-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="96c17-104">客户端会自动生成三种类型的日志文件，可以利用它们协助对 Microsoft Teams 进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="96c17-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="96c17-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="96c17-105">Debug logs</span></span>

-   <span data-ttu-id="96c17-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="96c17-106">Media logs</span></span>

-   <span data-ttu-id="96c17-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="96c17-107">Desktop logs</span></span>

<span data-ttu-id="96c17-108">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="96c17-109">在创建支持请求之前准备好这些日志，Microsoft 就可以快速开始对问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="96c17-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="96c17-110">仅当 Microsoft 要求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="96c17-111">下表概括列出了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="96c17-112">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="96c17-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="96c17-113">客户端</span><span class="sxs-lookup"><span data-stu-id="96c17-113">Client</span></span> |<span data-ttu-id="96c17-114">调试</span><span class="sxs-lookup"><span data-stu-id="96c17-114">Debug</span></span>|<span data-ttu-id="96c17-115">桌面</span><span class="sxs-lookup"><span data-stu-id="96c17-115">Desktop</span></span>|<span data-ttu-id="96c17-116">媒体</span><span class="sxs-lookup"><span data-stu-id="96c17-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="96c17-117">Web</span><span class="sxs-lookup"><span data-stu-id="96c17-117">Web</span></span>    |<span data-ttu-id="96c17-118">X</span><span class="sxs-lookup"><span data-stu-id="96c17-118">X</span></span>         |-         |-         |
|<span data-ttu-id="96c17-119">Windows</span><span class="sxs-lookup"><span data-stu-id="96c17-119">Windows</span></span>     |<span data-ttu-id="96c17-120">X</span><span class="sxs-lookup"><span data-stu-id="96c17-120">X</span></span>         |<span data-ttu-id="96c17-121">X</span><span class="sxs-lookup"><span data-stu-id="96c17-121">X</span></span>         |<span data-ttu-id="96c17-122">X</span><span class="sxs-lookup"><span data-stu-id="96c17-122">X</span></span>         |
|<span data-ttu-id="96c17-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="96c17-123">Mac OSX</span></span>     |<span data-ttu-id="96c17-124">X</span><span class="sxs-lookup"><span data-stu-id="96c17-124">X</span></span>         |<span data-ttu-id="96c17-125">X</span><span class="sxs-lookup"><span data-stu-id="96c17-125">X</span></span>         |<span data-ttu-id="96c17-126">X</span><span class="sxs-lookup"><span data-stu-id="96c17-126">X</span></span>         |
|<span data-ttu-id="96c17-127">Linux</span><span class="sxs-lookup"><span data-stu-id="96c17-127">Linux</span></span>     |<span data-ttu-id="96c17-128">X</span><span class="sxs-lookup"><span data-stu-id="96c17-128">X</span></span>         |<span data-ttu-id="96c17-129">X</span><span class="sxs-lookup"><span data-stu-id="96c17-129">X</span></span>         |<span data-ttu-id="96c17-130">X</span><span class="sxs-lookup"><span data-stu-id="96c17-130">X</span></span>         |
|<span data-ttu-id="96c17-131">iOS</span><span class="sxs-lookup"><span data-stu-id="96c17-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="96c17-132">Android</span><span class="sxs-lookup"><span data-stu-id="96c17-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="96c17-133">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="96c17-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="96c17-134">调试日志</span><span class="sxs-lookup"><span data-stu-id="96c17-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="96c17-135">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="96c17-136">Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成调试日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="96c17-137">日志是基于文本的，可以自下而上读取。</span><span class="sxs-lookup"><span data-stu-id="96c17-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="96c17-138">可以使用任何基于文本的编辑器读取这些日志，登录客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="96c17-139">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="96c17-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="96c17-140">登录</span><span class="sxs-lookup"><span data-stu-id="96c17-140">Login</span></span>

-   <span data-ttu-id="96c17-141">向中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="96c17-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="96c17-142">通话/对话</span><span class="sxs-lookup"><span data-stu-id="96c17-142">Call/conversation</span></span>

<span data-ttu-id="96c17-143">可使用以下操作系统特定的方法生成调试日志：</span><span class="sxs-lookup"><span data-stu-id="96c17-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="96c17-144">Windows：</span><span class="sxs-lookup"><span data-stu-id="96c17-144">Windows:</span></span>

      <span data-ttu-id="96c17-145">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="96c17-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="96c17-146">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="96c17-146">Mac OSX:</span></span>

      <span data-ttu-id="96c17-147">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="96c17-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="96c17-148">厂商</span><span class="sxs-lookup"><span data-stu-id="96c17-148">Linux:</span></span>

      <span data-ttu-id="96c17-149">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="96c17-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="96c17-150">调试日志会自动下载到以下文件夹。</span><span class="sxs-lookup"><span data-stu-id="96c17-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="96c17-151">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="96c17-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="96c17-152">Mac OSX： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="96c17-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="96c17-153">Linux： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="96c17-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="96c17-154">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="96c17-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="96c17-155">媒体日志</span><span class="sxs-lookup"><span data-stu-id="96c17-155">Media logs</span></span>
---------------------------

<span data-ttu-id="96c17-156">媒体日志包含有关团队会议中的音频、视频和屏幕共享的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="96c17-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="96c17-157">它们对于链接到调用相关问题的支持案例是必需的。</span><span class="sxs-lookup"><span data-stu-id="96c17-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="96c17-158">默认情况下，媒体日志记录处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="96c17-158">Media logging is turned off by default.</span></span> <span data-ttu-id="96c17-159">若要记录团队会议的诊断数据，用户必须打开团队客户端中的选项。</span><span class="sxs-lookup"><span data-stu-id="96c17-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="96c17-160">转到 "**设置**  >  **常规**"，选中 "**为会议诊断启用日志记录" (需要重新启动团队**) 复选框，然后重新启动团队并重现该问题。</span><span class="sxs-lookup"><span data-stu-id="96c17-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="96c17-161">下表列出了媒体日志位置。</span><span class="sxs-lookup"><span data-stu-id="96c17-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="96c17-162">将日志文件发送给 Microsoft 支持时，请验证日志文件的时间戳，以确保在重现问题时日志覆盖了时间范围。</span><span class="sxs-lookup"><span data-stu-id="96c17-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="96c17-163">客户端</span><span class="sxs-lookup"><span data-stu-id="96c17-163">Client</span></span> |<span data-ttu-id="96c17-164">位置</span><span class="sxs-lookup"><span data-stu-id="96c17-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="96c17-165">Windows</span><span class="sxs-lookup"><span data-stu-id="96c17-165">Windows</span></span>     |<span data-ttu-id="96c17-166">%appdata%\Microsoft\Teams\media-stack \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="96c17-167">%appdata%\Microsoft\Teams\skylib \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="96c17-168">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="96c17-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="96c17-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="96c17-169">Mac OSX</span></span>     |<span data-ttu-id="96c17-170">~/Library/application support 支持/Microsoft/团队/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="96c17-171">~/Library/application support 支持/Microsoft/团队/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="96c17-172">Linux</span><span class="sxs-lookup"><span data-stu-id="96c17-172">Linux</span></span>       |<span data-ttu-id="96c17-173">~/.config/Microsoft/Microsoft 团队/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="96c17-174">~/.config/Microsoft/Microsoft 团队/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="96c17-175">下面列出了生成的日志文件及其包含的信息。</span><span class="sxs-lookup"><span data-stu-id="96c17-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="96c17-176">日志文件名</span><span class="sxs-lookup"><span data-stu-id="96c17-176">Log file name</span></span>  |<span data-ttu-id="96c17-177">说明</span><span class="sxs-lookup"><span data-stu-id="96c17-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="96c17-178">Msrtc-s1039525249 的团队</span><span class="sxs-lookup"><span data-stu-id="96c17-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="96c17-179">包含与媒体堆栈相关的信息。</span><span class="sxs-lookup"><span data-stu-id="96c17-179">Contains information related to the media stack.</span></span> <span data-ttu-id="96c17-180">这包括通道状态（如分辨率、使用的解码器和编码器）和发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 会话状态。</span><span class="sxs-lookup"><span data-stu-id="96c17-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="96c17-181">rtmcontrol msrtc-2415069487. 博客</span><span class="sxs-lookup"><span data-stu-id="96c17-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="96c17-182">记录与远程控制操作相关的信息，例如控制所提供的时间戳，以及鼠标指针信息。</span><span class="sxs-lookup"><span data-stu-id="96c17-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="96c17-183">Teams_MediaStackETW-2-U-xr-U</span><span class="sxs-lookup"><span data-stu-id="96c17-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="96c17-184">记录媒体堆栈跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="96c17-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="96c17-185">Debug-0-s2790420889</span><span class="sxs-lookup"><span data-stu-id="96c17-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="96c17-186">包含与媒体代理相关的信息，包括呈现质量。</span><span class="sxs-lookup"><span data-stu-id="96c17-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="96c17-187">tscalling-0-2061129496</span><span class="sxs-lookup"><span data-stu-id="96c17-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="96c17-188">在 ts 调用 API 中记录事件。</span><span class="sxs-lookup"><span data-stu-id="96c17-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="96c17-189">桌面日志</span><span class="sxs-lookup"><span data-stu-id="96c17-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="96c17-190">桌面日志（也称为引导程序日志）包含桌面客户端和浏览器之间生成的日志数据。</span><span class="sxs-lookup"><span data-stu-id="96c17-190">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="96c17-191">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="96c17-191">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="96c17-192">这些日志是基于文本的，可以使用任何基于文本的编辑器以自上而下的方式读取。</span><span class="sxs-lookup"><span data-stu-id="96c17-192">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="96c17-193">Windows：</span><span class="sxs-lookup"><span data-stu-id="96c17-193">Windows:</span></span>

1.  <span data-ttu-id="96c17-194">右键单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"</span><span class="sxs-lookup"><span data-stu-id="96c17-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="96c17-195">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="96c17-195">Mac OsX:</span></span>

1.  <span data-ttu-id="96c17-196">从 **“帮助”** 下拉菜单中选择 **“获取日志”**</span><span class="sxs-lookup"><span data-stu-id="96c17-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="96c17-197">厂商</span><span class="sxs-lookup"><span data-stu-id="96c17-197">Linux:</span></span>

1.  <span data-ttu-id="96c17-198">单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"</span><span class="sxs-lookup"><span data-stu-id="96c17-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="96c17-199">客户端</span><span class="sxs-lookup"><span data-stu-id="96c17-199">Client</span></span> |<span data-ttu-id="96c17-200">位置</span><span class="sxs-lookup"><span data-stu-id="96c17-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="96c17-201">Windows</span><span class="sxs-lookup"><span data-stu-id="96c17-201">Windows</span></span>     |<span data-ttu-id="96c17-202">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="96c17-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="96c17-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="96c17-203">Mac OSX</span></span>     |<span data-ttu-id="96c17-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="96c17-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="96c17-205">Linux</span><span class="sxs-lookup"><span data-stu-id="96c17-205">Linux</span></span>       |<span data-ttu-id="96c17-206">~/.config/Microsoft/Microsoft 团队/logs.txt</span><span class="sxs-lookup"><span data-stu-id="96c17-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="96c17-207">相关主题</span><span class="sxs-lookup"><span data-stu-id="96c17-207">Related topics</span></span>

[<span data-ttu-id="96c17-208">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="96c17-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
