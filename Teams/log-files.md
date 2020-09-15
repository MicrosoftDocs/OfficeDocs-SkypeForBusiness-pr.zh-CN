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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766756"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="74e64-103">在对 Microsoft Teams 进行故障排除时使用日志文件</span><span class="sxs-lookup"><span data-stu-id="74e64-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="74e64-104">客户端会自动生成三种类型的日志文件，可以利用它们协助对 Microsoft Teams 进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="74e64-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="74e64-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="74e64-105">Debug logs</span></span>

-   <span data-ttu-id="74e64-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="74e64-106">Media logs</span></span>

-   <span data-ttu-id="74e64-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="74e64-107">Desktop logs</span></span>

<span data-ttu-id="74e64-108">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="74e64-109">在创建支持请求之前准备好这些日志，Microsoft 就可以快速开始对问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="74e64-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="74e64-110">仅当 Microsoft 要求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="74e64-111">下表概括列出了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="74e64-112">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="74e64-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="74e64-113">客户端</span><span class="sxs-lookup"><span data-stu-id="74e64-113">Client</span></span> |<span data-ttu-id="74e64-114">调试</span><span class="sxs-lookup"><span data-stu-id="74e64-114">Debug</span></span>|<span data-ttu-id="74e64-115">桌面</span><span class="sxs-lookup"><span data-stu-id="74e64-115">Desktop</span></span>|<span data-ttu-id="74e64-116">媒体</span><span class="sxs-lookup"><span data-stu-id="74e64-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="74e64-117">Web</span><span class="sxs-lookup"><span data-stu-id="74e64-117">Web</span></span>    |<span data-ttu-id="74e64-118">X</span><span class="sxs-lookup"><span data-stu-id="74e64-118">X</span></span>         |-         |-         |
|<span data-ttu-id="74e64-119">Windows</span><span class="sxs-lookup"><span data-stu-id="74e64-119">Windows</span></span>     |<span data-ttu-id="74e64-120">X</span><span class="sxs-lookup"><span data-stu-id="74e64-120">X</span></span>         |<span data-ttu-id="74e64-121">X</span><span class="sxs-lookup"><span data-stu-id="74e64-121">X</span></span>         |<span data-ttu-id="74e64-122">X</span><span class="sxs-lookup"><span data-stu-id="74e64-122">X</span></span>         |
|<span data-ttu-id="74e64-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="74e64-123">Mac OSX</span></span>     |<span data-ttu-id="74e64-124">X</span><span class="sxs-lookup"><span data-stu-id="74e64-124">X</span></span>         |<span data-ttu-id="74e64-125">X</span><span class="sxs-lookup"><span data-stu-id="74e64-125">X</span></span>         |<span data-ttu-id="74e64-126">X</span><span class="sxs-lookup"><span data-stu-id="74e64-126">X</span></span>         |
|<span data-ttu-id="74e64-127">Linux</span><span class="sxs-lookup"><span data-stu-id="74e64-127">Linux</span></span>     |<span data-ttu-id="74e64-128">X</span><span class="sxs-lookup"><span data-stu-id="74e64-128">X</span></span>         |<span data-ttu-id="74e64-129">X</span><span class="sxs-lookup"><span data-stu-id="74e64-129">X</span></span>         |<span data-ttu-id="74e64-130">X</span><span class="sxs-lookup"><span data-stu-id="74e64-130">X</span></span>         |
|<span data-ttu-id="74e64-131">iOS</span><span class="sxs-lookup"><span data-stu-id="74e64-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="74e64-132">Android</span><span class="sxs-lookup"><span data-stu-id="74e64-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="74e64-133">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="74e64-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="74e64-134">调试日志</span><span class="sxs-lookup"><span data-stu-id="74e64-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="74e64-135">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="74e64-136">Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成调试日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="74e64-137">日志是基于文本的，可以自下而上读取。</span><span class="sxs-lookup"><span data-stu-id="74e64-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="74e64-138">可以使用任何基于文本的编辑器读取这些日志，登录客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="74e64-139">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="74e64-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="74e64-140">登录</span><span class="sxs-lookup"><span data-stu-id="74e64-140">Login</span></span>

-   <span data-ttu-id="74e64-141">向中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="74e64-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="74e64-142">通话/对话</span><span class="sxs-lookup"><span data-stu-id="74e64-142">Call/conversation</span></span>

<span data-ttu-id="74e64-143">可使用以下操作系统特定的方法生成调试日志：</span><span class="sxs-lookup"><span data-stu-id="74e64-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="74e64-144">Windows：</span><span class="sxs-lookup"><span data-stu-id="74e64-144">Windows:</span></span>

      <span data-ttu-id="74e64-145">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="74e64-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="74e64-146">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="74e64-146">Mac OSX:</span></span>

      <span data-ttu-id="74e64-147">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="74e64-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="74e64-148">厂商</span><span class="sxs-lookup"><span data-stu-id="74e64-148">Linux:</span></span>

      <span data-ttu-id="74e64-149">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="74e64-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="74e64-150">调试日志会自动下载到以下文件夹。</span><span class="sxs-lookup"><span data-stu-id="74e64-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="74e64-151">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="74e64-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="74e64-152">Mac OSX： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="74e64-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="74e64-153">Linux： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="74e64-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="74e64-154">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="74e64-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="74e64-155">媒体日志</span><span class="sxs-lookup"><span data-stu-id="74e64-155">Media logs</span></span>
---------------------------

<span data-ttu-id="74e64-156">媒体日志包含有关团队会议中的音频、视频和屏幕共享的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="74e64-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="74e64-157">仅当要求时支持案例才需要它们，且只能由 Microsoft 检查。</span><span class="sxs-lookup"><span data-stu-id="74e64-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> 

<span data-ttu-id="74e64-158">默认情况下，媒体日志记录处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="74e64-158">Media logging is turned off by default.</span></span> <span data-ttu-id="74e64-159">若要记录团队会议的诊断数据，用户必须打开团队客户端中的选项。</span><span class="sxs-lookup"><span data-stu-id="74e64-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="74e64-160">转到 "**设置**  >  **常规**"，选中 "**启用会议诊断的日志记录 (需要重新启动团队**) 复选框，然后重新启动团队。</span><span class="sxs-lookup"><span data-stu-id="74e64-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams.</span></span>

<span data-ttu-id="74e64-161">下表列出了日志位置。</span><span class="sxs-lookup"><span data-stu-id="74e64-161">The following table outlines the log locations.</span></span>

|<span data-ttu-id="74e64-162">客户端</span><span class="sxs-lookup"><span data-stu-id="74e64-162">Client</span></span> |<span data-ttu-id="74e64-163">位置</span><span class="sxs-lookup"><span data-stu-id="74e64-163">Location</span></span> |
|---------|---------|
|<span data-ttu-id="74e64-164">Windows</span><span class="sxs-lookup"><span data-stu-id="74e64-164">Windows</span></span>     |<span data-ttu-id="74e64-165">%appdata%\Microsoft\Teams\media-stack \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-165">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="74e64-166">%appdata%\Microsoft\Teams\skylib \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-166">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="74e64-167">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="74e64-167">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="74e64-168">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="74e64-168">Mac OSX</span></span>     |<span data-ttu-id="74e64-169">~/Library/application support 支持/Microsoft/团队/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-169">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="74e64-170">~/Library/application support 支持/Microsoft/团队/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-170">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="74e64-171">Linux</span><span class="sxs-lookup"><span data-stu-id="74e64-171">Linux</span></span>       |<span data-ttu-id="74e64-172">~/.config/Microsoft/Microsoft 团队/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-172">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="74e64-173">~/.config/Microsoft/Microsoft 团队/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-173">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="74e64-174">下面列出了生成的日志文件及其包含的信息。</span><span class="sxs-lookup"><span data-stu-id="74e64-174">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="74e64-175">日志文件名</span><span class="sxs-lookup"><span data-stu-id="74e64-175">Log file name</span></span>  |<span data-ttu-id="74e64-176">说明</span><span class="sxs-lookup"><span data-stu-id="74e64-176">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="74e64-177">Msrtc-s1039525249 的团队</span><span class="sxs-lookup"><span data-stu-id="74e64-177">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="74e64-178">包含与媒体堆栈相关的信息。</span><span class="sxs-lookup"><span data-stu-id="74e64-178">Contains information related to the media stack.</span></span> <span data-ttu-id="74e64-179">这包括通道状态（如分辨率、使用的解码器和编码器）和发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 会话状态。</span><span class="sxs-lookup"><span data-stu-id="74e64-179">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="74e64-180">rtmcontrol msrtc-2415069487. 博客</span><span class="sxs-lookup"><span data-stu-id="74e64-180">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="74e64-181">记录与远程控制操作相关的信息，例如控制所提供的时间戳，以及鼠标指针信息。</span><span class="sxs-lookup"><span data-stu-id="74e64-181">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="74e64-182">Teams_MediaStackETW-2-U-xr-U</span><span class="sxs-lookup"><span data-stu-id="74e64-182">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="74e64-183">记录媒体堆栈跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="74e64-183">Records media stack trace events.</span></span>         |
|<span data-ttu-id="74e64-184">Debug-0-s2790420889</span><span class="sxs-lookup"><span data-stu-id="74e64-184">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="74e64-185">包含与媒体代理相关的信息，包括呈现质量。</span><span class="sxs-lookup"><span data-stu-id="74e64-185">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="74e64-186">tscalling-0-2061129496</span><span class="sxs-lookup"><span data-stu-id="74e64-186">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="74e64-187">在 ts 调用 API 中记录事件。</span><span class="sxs-lookup"><span data-stu-id="74e64-187">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="74e64-188">桌面日志</span><span class="sxs-lookup"><span data-stu-id="74e64-188">Desktop logs</span></span>
---------------------

<span data-ttu-id="74e64-189">桌面日志（也称为引导程序日志）包含桌面客户端和浏览器之间生成的日志数据。</span><span class="sxs-lookup"><span data-stu-id="74e64-189">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="74e64-190">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="74e64-190">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="74e64-191">这些日志是基于文本的，可以使用任何基于文本的编辑器以自上而下的方式读取。</span><span class="sxs-lookup"><span data-stu-id="74e64-191">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="74e64-192">Windows：</span><span class="sxs-lookup"><span data-stu-id="74e64-192">Windows:</span></span>

1.  <span data-ttu-id="74e64-193">右键单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"</span><span class="sxs-lookup"><span data-stu-id="74e64-193">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="74e64-194">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="74e64-194">Mac OsX:</span></span>

1.  <span data-ttu-id="74e64-195">从 **“帮助”** 下拉菜单中选择 **“获取日志”**</span><span class="sxs-lookup"><span data-stu-id="74e64-195">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="74e64-196">厂商</span><span class="sxs-lookup"><span data-stu-id="74e64-196">Linux:</span></span>

1.  <span data-ttu-id="74e64-197">单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"</span><span class="sxs-lookup"><span data-stu-id="74e64-197">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="74e64-198">客户端</span><span class="sxs-lookup"><span data-stu-id="74e64-198">Client</span></span> |<span data-ttu-id="74e64-199">位置</span><span class="sxs-lookup"><span data-stu-id="74e64-199">Location</span></span> |
|---------|---------|
|<span data-ttu-id="74e64-200">Windows</span><span class="sxs-lookup"><span data-stu-id="74e64-200">Windows</span></span>     |<span data-ttu-id="74e64-201">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="74e64-201">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="74e64-202">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="74e64-202">Mac OSX</span></span>     |<span data-ttu-id="74e64-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="74e64-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="74e64-204">Linux</span><span class="sxs-lookup"><span data-stu-id="74e64-204">Linux</span></span>       |<span data-ttu-id="74e64-205">~/.config/Microsoft/Microsoft 团队/logs.txt</span><span class="sxs-lookup"><span data-stu-id="74e64-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="74e64-206">相关主题</span><span class="sxs-lookup"><span data-stu-id="74e64-206">Related topics</span></span>

[<span data-ttu-id="74e64-207">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="74e64-207">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

