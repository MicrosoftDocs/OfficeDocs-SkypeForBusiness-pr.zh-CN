---
title: 在对 Microsoft Teams 进行故障排除时使用日志文件
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: 了解 Microsoft Teams 生成的调试、媒体和桌面日志，可以在哪里找到它们，以及它们如何帮助进行故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95d28bac036476c417ccbe7929a23ab9fb37f3a8
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018897"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="5e006-103">在对 Microsoft Teams 进行故障排除时使用日志文件</span><span class="sxs-lookup"><span data-stu-id="5e006-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="5e006-104">客户端会自动生成三种类型的日志文件，可以利用它们协助对 Microsoft Teams 进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5e006-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="5e006-105">调试日志</span><span class="sxs-lookup"><span data-stu-id="5e006-105">Debug logs</span></span>

-   <span data-ttu-id="5e006-106">媒体日志</span><span class="sxs-lookup"><span data-stu-id="5e006-106">Media logs</span></span>

-   <span data-ttu-id="5e006-107">桌面日志</span><span class="sxs-lookup"><span data-stu-id="5e006-107">Desktop logs</span></span>

<span data-ttu-id="5e006-108">通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。</span><span class="sxs-lookup"><span data-stu-id="5e006-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="5e006-109">在创建支持请求之前准备好这些日志，Microsoft 就可以快速开始对问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5e006-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="5e006-110">仅当 Microsoft 要求时，才需要媒体或桌面日志。</span><span class="sxs-lookup"><span data-stu-id="5e006-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="5e006-111">下表概括列出了各种客户端及其关联的日志。</span><span class="sxs-lookup"><span data-stu-id="5e006-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="5e006-112">日志文件存储在特定于客户端和操作系统的位置。</span><span class="sxs-lookup"><span data-stu-id="5e006-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="5e006-113">客户端</span><span class="sxs-lookup"><span data-stu-id="5e006-113">Client</span></span> |<span data-ttu-id="5e006-114">调试</span><span class="sxs-lookup"><span data-stu-id="5e006-114">Debug</span></span>|<span data-ttu-id="5e006-115">桌面</span><span class="sxs-lookup"><span data-stu-id="5e006-115">Desktop</span></span>|<span data-ttu-id="5e006-116">媒体</span><span class="sxs-lookup"><span data-stu-id="5e006-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="5e006-117">Web</span><span class="sxs-lookup"><span data-stu-id="5e006-117">Web</span></span>    |<span data-ttu-id="5e006-118">X</span><span class="sxs-lookup"><span data-stu-id="5e006-118">X</span></span>         |-         |-         |
|<span data-ttu-id="5e006-119">Windows</span><span class="sxs-lookup"><span data-stu-id="5e006-119">Windows</span></span>     |<span data-ttu-id="5e006-120">X</span><span class="sxs-lookup"><span data-stu-id="5e006-120">X</span></span>         |<span data-ttu-id="5e006-121">X</span><span class="sxs-lookup"><span data-stu-id="5e006-121">X</span></span>         |<span data-ttu-id="5e006-122">X</span><span class="sxs-lookup"><span data-stu-id="5e006-122">X</span></span>         |
|<span data-ttu-id="5e006-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5e006-123">Mac OSX</span></span>     |<span data-ttu-id="5e006-124">X</span><span class="sxs-lookup"><span data-stu-id="5e006-124">X</span></span>         |<span data-ttu-id="5e006-125">X</span><span class="sxs-lookup"><span data-stu-id="5e006-125">X</span></span>         |<span data-ttu-id="5e006-126">X</span><span class="sxs-lookup"><span data-stu-id="5e006-126">X</span></span>         |
|<span data-ttu-id="5e006-127">iOS</span><span class="sxs-lookup"><span data-stu-id="5e006-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="5e006-128">Android</span><span class="sxs-lookup"><span data-stu-id="5e006-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="5e006-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5e006-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="5e006-130">有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="5e006-130">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="5e006-131">调试日志</span><span class="sxs-lookup"><span data-stu-id="5e006-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="5e006-132">这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="5e006-132">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="5e006-133">调试日志所产生的 Windows 和 Mac 的桌面客户端以及基于浏览器客户端。</span><span class="sxs-lookup"><span data-stu-id="5e006-133">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="5e006-134">日志是基于文本的，可以自下而上读取。</span><span class="sxs-lookup"><span data-stu-id="5e006-134">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="5e006-135">可以使用任何基于文本的编辑器读取这些日志，登录客户端时会创建新日志。</span><span class="sxs-lookup"><span data-stu-id="5e006-135">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="5e006-136">调试日志显示以下数据流：</span><span class="sxs-lookup"><span data-stu-id="5e006-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="5e006-137">登录</span><span class="sxs-lookup"><span data-stu-id="5e006-137">Login</span></span>

-   <span data-ttu-id="5e006-138">向中间层服务的连接请求</span><span class="sxs-lookup"><span data-stu-id="5e006-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="5e006-139">通话/对话</span><span class="sxs-lookup"><span data-stu-id="5e006-139">Call/conversation</span></span>

<span data-ttu-id="5e006-140">可使用以下操作系统特定的方法生成调试日志：</span><span class="sxs-lookup"><span data-stu-id="5e006-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="5e006-141">Windows：</span><span class="sxs-lookup"><span data-stu-id="5e006-141">Windows:</span></span>

    1.  <span data-ttu-id="5e006-142">右键单击应用任务栏中的 **Microsoft Teams图标**，选择 **“获取日志”**</span><span class="sxs-lookup"><span data-stu-id="5e006-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="5e006-143">从 **“帮助”** 下拉菜单中选择 **“获取日志”**</span><span class="sxs-lookup"><span data-stu-id="5e006-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="5e006-144">键盘快捷方式：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="5e006-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="5e006-145">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="5e006-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="5e006-146">从 **“帮助”** 下拉菜单中选择 **“获取日志”**</span><span class="sxs-lookup"><span data-stu-id="5e006-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="5e006-147">键盘快捷方式：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="5e006-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="5e006-148">调试日志会自动下载到以下文件夹。</span><span class="sxs-lookup"><span data-stu-id="5e006-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="5e006-149">Windows：%userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="5e006-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="5e006-150">Mac OSX：Downloads</span><span class="sxs-lookup"><span data-stu-id="5e006-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="5e006-151">浏览器：系统将提示你将调试日志保存到默认保存位置</span><span class="sxs-lookup"><span data-stu-id="5e006-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="5e006-152">媒体日志</span><span class="sxs-lookup"><span data-stu-id="5e006-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="5e006-153">媒体日志包含有关音频、视频和屏幕共享的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="5e006-153">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="5e006-154">仅当要求时支持案例才需要它们，且只能由 Microsoft 检查。</span><span class="sxs-lookup"><span data-stu-id="5e006-154">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="5e006-155">下表概括列出了日志位置。</span><span class="sxs-lookup"><span data-stu-id="5e006-155">The following table outlines the log location.</span></span>


|<span data-ttu-id="5e006-156">客户端</span><span class="sxs-lookup"><span data-stu-id="5e006-156">Client</span></span> |<span data-ttu-id="5e006-157">位置</span><span class="sxs-lookup"><span data-stu-id="5e006-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5e006-158">Windows</span><span class="sxs-lookup"><span data-stu-id="5e006-158">Windows</span></span>     |<span data-ttu-id="5e006-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="5e006-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="5e006-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5e006-160">Mac OSX</span></span>     |<span data-ttu-id="5e006-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="5e006-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="5e006-162">桌面日志</span><span class="sxs-lookup"><span data-stu-id="5e006-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="5e006-163">桌面日志（也称为引导程序日志）包含桌面客户端和浏览器之间生成的日志数据。</span><span class="sxs-lookup"><span data-stu-id="5e006-163">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="5e006-164">与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。</span><span class="sxs-lookup"><span data-stu-id="5e006-164">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="5e006-165">这些日志是基于文本的，可以使用任何基于文本的编辑器以自上而下的方式读取。</span><span class="sxs-lookup"><span data-stu-id="5e006-165">The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="5e006-166">客户端</span><span class="sxs-lookup"><span data-stu-id="5e006-166">Client</span></span> |<span data-ttu-id="5e006-167">位置</span><span class="sxs-lookup"><span data-stu-id="5e006-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="5e006-168">Windows</span><span class="sxs-lookup"><span data-stu-id="5e006-168">Windows</span></span>     |<span data-ttu-id="5e006-169">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="5e006-169">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="5e006-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="5e006-170">Mac OSX</span></span>     |<span data-ttu-id="5e006-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="5e006-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
