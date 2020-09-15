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
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>在对 Microsoft Teams 进行故障排除时使用日志文件
=================================================

客户端会自动生成三种类型的日志文件，可以利用它们协助对 Microsoft Teams 进行故障排除。

-   调试日志

-   媒体日志

-   桌面日志

通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。 在创建支持请求之前准备好这些日志，Microsoft 就可以快速开始对问题进行故障排除。 仅当 Microsoft 要求时，才需要媒体或桌面日志。

下表概括列出了各种客户端及其关联的日志。 日志文件存储在特定于客户端和操作系统的位置。


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

这些是最常见的日志，所有 Microsoft 支持案例都需要这些日志。 Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成调试日志。 日志是基于文本的，可以自下而上读取。 可以使用任何基于文本的编辑器读取这些日志，登录客户端时会创建新日志。

调试日志显示以下数据流：

-   登录

-   向中间层服务的连接请求

-   通话/对话

可使用以下操作系统特定的方法生成调试日志：

-   Windows：

      键盘快捷方式：Ctrl + Alt + Shift + 1

-   Mac OSX：

      键盘快捷方式：Option + Command + Shift+1

-   厂商

      键盘快捷方式：Ctrl + Alt + Shift + 1

调试日志会自动下载到以下文件夹。

-   Windows：%userprofile%\\Downloads

-   Mac OSX： ~/Downloads

-   Linux： ~/Downloads

-   浏览器：系统将提示你将调试日志保存到默认保存位置

<a name="media-logs"></a>媒体日志
---------------------------

媒体日志包含有关团队会议中的音频、视频和屏幕共享的诊断数据。 仅当要求时支持案例才需要它们，且只能由 Microsoft 检查。 

默认情况下，媒体日志记录处于关闭状态。 若要记录团队会议的诊断数据，用户必须打开团队客户端中的选项。 转到 "**设置**  >  **常规**"，选中 "**启用会议诊断的日志记录 (需要重新启动团队**) 复选框，然后重新启动团队。

下表列出了日志位置。

|客户端 |位置 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. 博客         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. 博客
|            |%appdata%\Microsoft\Teams\media-stack \\ * .etl         |
|Mac OSX     |~/Library/application support 支持/Microsoft/团队/media-stack/*. 博客         |
|            |~/Library/application support 支持/Microsoft/团队/skylib/*. 博客         |
|Linux       |~/.config/Microsoft/Microsoft 团队/media-stack/*. 博客         |
|            |~/.config/Microsoft/Microsoft 团队/skylib/*. 博客         |

下面列出了生成的日志文件及其包含的信息。

|日志文件名  |说明  |
|---------|---------|
|Msrtc-s1039525249 的团队     | 包含与媒体堆栈相关的信息。 这包括通道状态（如分辨率、使用的解码器和编码器）和发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 会话状态。         |
|rtmcontrol msrtc-2415069487. 博客      |记录与远程控制操作相关的信息，例如控制所提供的时间戳，以及鼠标指针信息。          |
|Teams_MediaStackETW-2-U-xr-U      |记录媒体堆栈跟踪事件。         |
|Debug-0-s2790420889    | 包含与媒体代理相关的信息，包括呈现质量。          |
|tscalling-0-2061129496   |在 ts 调用 API 中记录事件。       |

<a name="desktop-logs"></a>桌面日志
---------------------

桌面日志（也称为引导程序日志）包含桌面客户端和浏览器之间生成的日志数据。 与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。 这些日志是基于文本的，可以使用任何基于文本的编辑器以自上而下的方式读取。

Windows：

1.  右键单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"

Mac OsX：

1.  从 **“帮助”** 下拉菜单中选择 **“获取日志”**

厂商

1.  单击系统任务栏中的 " **Microsoft 团队**" 图标，选择 "**获取日志**"

|客户端 |位置 |
|---------|---------|
|Windows     |% appdata% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft 团队/logs.txt         |


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

