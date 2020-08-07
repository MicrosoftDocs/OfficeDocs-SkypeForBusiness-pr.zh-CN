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
ms.openlocfilehash: f13acc1a401a6753b335c17fe0cd8a7984849216
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582105"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="5983a-103">在对 Microsoft Teams 进行故障排除时使用日志文件</span><span class="sxs-lookup"><span data-stu-id="5983a-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="5983a-104">客户端会自动生成三种类型的日志文件，可以利用它们协助对 Microsoft Teams 进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5983a-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="5983a-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="5983a-105">Debug logs</span></span>

-   <span data-ttu-id="5983a-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="5983a-106">Media logs</span></span>

-   <span data-ttu-id="5983a-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="5983a-107">Desktop logs</span></span>

<span data-ttu-id="5983a-108">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="5983a-109">在创建支持请求之前准备好这些日志，Microsoft 就可以快速开始对问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5983a-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="5983a-110">仅当 Microsoft 要求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="5983a-111">下表概括列出了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="5983a-112">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="5983a-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="5983a-113">客户端</span><span class="sxs-lookup"><span data-stu-id="5983a-113">Client</span></span> |<span data-ttu-id="5983a-114">调试</span><span class="sxs-lookup"><span data-stu-id="5983a-114">Debug</span></span>|<span data-ttu-id="5983a-115">桌面</span><span class="sxs-lookup"><span data-stu-id="5983a-115">Desktop</span></span>|<span data-ttu-id="5983a-116">媒体</span><span class="sxs-lookup"><span data-stu-id="5983a-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="5983a-117">Web</span><span class="sxs-lookup"><span data-stu-id="5983a-117">Web</span></span>    |<span data-ttu-id="5983a-118">X</span><span class="sxs-lookup"><span data-stu-id="5983a-118">X</span></span>         |-         |-         |
|<span data-ttu-id="5983a-119">Windows</span><span class="sxs-lookup"><span data-stu-id="5983a-119">Windows</span></span>     |<span data-ttu-id="5983a-120">X</span><span class="sxs-lookup"><span data-stu-id="5983a-120">X</span></span>         |<span data-ttu-id="5983a-121">X</span><span class="sxs-lookup"><span data-stu-id="5983a-121">X</span></span>         |<span data-ttu-id="5983a-122">X</span><span class="sxs-lookup"><span data-stu-id="5983a-122">X</span></span>         |
|<span data-ttu-id="5983a-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5983a-123">Mac OSX</span></span>     |<span data-ttu-id="5983a-124">X</span><span class="sxs-lookup"><span data-stu-id="5983a-124">X</span></span>         |<span data-ttu-id="5983a-125">X</span><span class="sxs-lookup"><span data-stu-id="5983a-125">X</span></span>         |<span data-ttu-id="5983a-126">X</span><span class="sxs-lookup"><span data-stu-id="5983a-126">X</span></span>         |
|<span data-ttu-id="5983a-127">Linux</span><span class="sxs-lookup"><span data-stu-id="5983a-127">Linux</span></span>     |<span data-ttu-id="5983a-128">X</span><span class="sxs-lookup"><span data-stu-id="5983a-128">X</span></span>         |<span data-ttu-id="5983a-129">X</span><span class="sxs-lookup"><span data-stu-id="5983a-129">X</span></span>         |<span data-ttu-id="5983a-130">X</span><span class="sxs-lookup"><span data-stu-id="5983a-130">X</span></span>         |
|<span data-ttu-id="5983a-131">iOS</span><span class="sxs-lookup"><span data-stu-id="5983a-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="5983a-132">Android</span><span class="sxs-lookup"><span data-stu-id="5983a-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="5983a-133">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="5983a-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="5983a-134">调试日志</span><span class="sxs-lookup"><span data-stu-id="5983a-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="5983a-135">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="5983a-136">Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成调试日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="5983a-137">日志是基于文本的，可以自下而上读取。</span><span class="sxs-lookup"><span data-stu-id="5983a-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="5983a-138">可以使用任何基于文本的编辑器读取这些日志，登录客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="5983a-139">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="5983a-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="5983a-140">登录</span><span class="sxs-lookup"><span data-stu-id="5983a-140">Login</span></span>

-   <span data-ttu-id="5983a-141">向中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="5983a-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="5983a-142">通话/对话</span><span class="sxs-lookup"><span data-stu-id="5983a-142">Call/conversation</span></span>

<span data-ttu-id="5983a-143">可使用以下操作系统特定的方法生成调试日志：</span><span class="sxs-lookup"><span data-stu-id="5983a-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="5983a-144">Windows：</span><span class="sxs-lookup"><span data-stu-id="5983a-144">Windows:</span></span>

      <span data-ttu-id="5983a-145">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="5983a-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="5983a-146">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="5983a-146">Mac OSX:</span></span>

      <span data-ttu-id="5983a-147">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="5983a-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="5983a-148">厂商</span><span class="sxs-lookup"><span data-stu-id="5983a-148">Linux:</span></span>

      <span data-ttu-id="5983a-149">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="5983a-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="5983a-150">调试日志会自动下载到以下文件夹。</span><span class="sxs-lookup"><span data-stu-id="5983a-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="5983a-151">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="5983a-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="5983a-152">Mac OSX：Downloads</span><span class="sxs-lookup"><span data-stu-id="5983a-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="5983a-153">Linux： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="5983a-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="5983a-154">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="5983a-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="5983a-155">媒体日志</span><span class="sxs-lookup"><span data-stu-id="5983a-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="5983a-156">媒体日志包含有关音频、视频和屏幕共享的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="5983a-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="5983a-157">仅当要求时支持案例才需要它们，且只能由 Microsoft 检查。</span><span class="sxs-lookup"><span data-stu-id="5983a-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="5983a-158">下表概括列出了日志位置。</span><span class="sxs-lookup"><span data-stu-id="5983a-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="5983a-159">客户端</span><span class="sxs-lookup"><span data-stu-id="5983a-159">Client</span></span> |<span data-ttu-id="5983a-160">位置</span><span class="sxs-lookup"><span data-stu-id="5983a-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5983a-161">Windows</span><span class="sxs-lookup"><span data-stu-id="5983a-161">Windows</span></span>     |<span data-ttu-id="5983a-162">%appdata%\Microsoft\Teams\media-stack \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="5983a-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="5983a-163">%appdata%\Microsoft\Teams\skylib \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="5983a-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="5983a-164">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="5983a-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="5983a-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5983a-165">Mac OSX</span></span>     |<span data-ttu-id="5983a-166">~/Library/application support 支持/Microsoft/团队/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="5983a-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5983a-167">~/Library/application support 支持/Microsoft/团队/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="5983a-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="5983a-168">Linux</span><span class="sxs-lookup"><span data-stu-id="5983a-168">Linux</span></span>       |<span data-ttu-id="5983a-169">~/.config/Microsoft/Microsoft 团队/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="5983a-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="5983a-170">~/.config/Microsoft/Microsoft 团队/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="5983a-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="5983a-171">桌面日志</span><span class="sxs-lookup"><span data-stu-id="5983a-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="5983a-172">桌面日志（也称为引导程序日志）包含桌面客户端和浏览器之间生成的日志数据。</span><span class="sxs-lookup"><span data-stu-id="5983a-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="5983a-173">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="5983a-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="5983a-174">这些日志是基于文本的，可以使用任何基于文本的编辑器以自上而下的方式读取。</span><span class="sxs-lookup"><span data-stu-id="5983a-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="5983a-175">Windows：</span><span class="sxs-lookup"><span data-stu-id="5983a-175">Windows:</span></span>

1.  <span data-ttu-id="5983a-176">右键单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"</span><span class="sxs-lookup"><span data-stu-id="5983a-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="5983a-177">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="5983a-177">Mac OsX:</span></span>

1.  <span data-ttu-id="5983a-178">从 **“帮助”** 下拉菜单中选择 **“获取日志”**</span><span class="sxs-lookup"><span data-stu-id="5983a-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="5983a-179">厂商</span><span class="sxs-lookup"><span data-stu-id="5983a-179">Linux:</span></span>

1.  <span data-ttu-id="5983a-180">单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"</span><span class="sxs-lookup"><span data-stu-id="5983a-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="5983a-181">客户端</span><span class="sxs-lookup"><span data-stu-id="5983a-181">Client</span></span> |<span data-ttu-id="5983a-182">位置</span><span class="sxs-lookup"><span data-stu-id="5983a-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5983a-183">Windows</span><span class="sxs-lookup"><span data-stu-id="5983a-183">Windows</span></span>     |<span data-ttu-id="5983a-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="5983a-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="5983a-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5983a-185">Mac OSX</span></span>     |<span data-ttu-id="5983a-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5983a-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="5983a-187">Linux</span><span class="sxs-lookup"><span data-stu-id="5983a-187">Linux</span></span>       |<span data-ttu-id="5983a-188">~/.config/Microsoft/Microsoft 团队/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5983a-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="5983a-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="5983a-189">Related topics</span></span>

[<span data-ttu-id="5983a-190">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="5983a-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

