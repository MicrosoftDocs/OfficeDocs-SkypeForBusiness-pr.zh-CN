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
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112188"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>在对 Microsoft Teams 进行故障排除时使用日志文件
=================================================

有三种类型的日志文件由客户端自动生成，可利用它们来帮助对 Microsoft Teams 进行故障排除：

-   调试日志

-   媒体日志

-   桌面日志

通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。 在创建支持请求之前，如果已处理调试日志，Microsoft 可以快速开始排查问题。 **只有** **Microsoft** 请求时，才需要媒体或桌面日志。

> [!NOTE]
> 本文中的"调试 **日志** "一词是指用于故障排除的日志。 但是，为这些日志生成的文件的名称 **中包含术语诊断** 日志。  

下表概述了各种客户端及其关联的日志。 日志文件存储在特定于客户端和操作系统的位置。


|客户端 |调试|桌面|媒体|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。

<a name="debug-logs"></a>调试日志
---------------------------

这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。 调试日志由 Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成。 日志基于文本，从下而上读取。 可以使用任何基于文本的编辑器读取这些日志，并且登录到客户端时会创建新日志。

调试日志显示以下数据流：

-   登录

-   到中间层服务的连接请求

-   通话/对话

调试日志是使用以下特定于 OS 的方法生成的：

-   Windows：

      键盘快捷方式：Ctrl + Alt + Shift + 1

-   Mac OSX：

      键盘快捷方式：Option + Command + Shift+1

-   Linux：

      键盘快捷方式：Ctrl + Alt + Shift + 1

调试日志会自动下载到以下文件夹：

-   Windows：%userprofile%\\Downloads

-   Mac OSX：~/Downloads

-   Linux：~/Downloads

-   浏览器：系统将提示你将调试日志保存到默认保存位置

<a name="media-logs"></a>媒体日志
---------------------------

媒体日志包含有关 Teams 会议中音频、视频和屏幕共享的诊断数据。 它们对于链接到呼叫相关问题的支持案例是必需的。

默认情况下，媒体日志记录已关闭。 若要记录 Teams 会议的诊断数据，用户必须在 Teams 客户端中打开 该选项。 转到"**设置** 常规"，选中"为会议诊断启用日志记录 (需要重新启动 Teams) 复选框，重新启动 Teams 并  >  重现问题。  

下表概述了媒体日志位置。 将日志文件发送给 Microsoft 支持人员时，请验证日志文件的时间戳，确保日志涵盖重现问题的时间范围。

|客户端 |位置 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

下面是生成的日志文件及其包含的信息的列表。

|日志文件名  |说明  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | 包含与媒体堆栈有关的信息。 这包括通道状态，例如分辨率、使用的解码器、编码器，以及发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 状态。         |
|rtmcontrol.msrtc-0-2415069487.blog      |记录与远程控制操作相关的信息，例如提供控制时时间戳和鼠标指针信息。          |
|Teams_MediaStackETW-2-U-xr-U.etl      |记录媒体堆栈跟踪事件。         |
|Debug-0-s2790420889.blog    | 包含与媒体代理有关的信息，包括呈现质量。          |
|tscalling-0-2061129496.blog   |在 ts-calling API 中记录事件。       |

<a name="desktop-logs"></a>桌面日志
---------------------

桌面日志也称为启动程序日志，包含桌面客户端与浏览器之间发生的日志数据。 与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。 日志基于文本，可以使用任何基于文本的编辑器以自上而下的格式读取。

Windows：

 - 右键单击 **系统任务栏** 中的 Microsoft Teams 图标，然后选择"**获取日志"。**

Mac OsX：

 - 从 **"帮助"** 下拉菜单 **中选择"** 获取日志"。

Linux：

 - 单击系统托盘 **中的 Microsoft Teams** 图标，然后选择"**获取日志"。**

|客户端 |位置 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)